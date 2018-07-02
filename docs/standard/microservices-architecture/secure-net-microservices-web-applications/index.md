---
title: Sécurisation des microservices .NET et des applications web
description: Architecture des microservices .NET pour les applications .NET en conteneur | Sécurisation des microservices .NET et des applications web
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: ccdf6ecc30979e953d42a403c2c988780394df96
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106695"
---
# <a name="securing-net-microservices-and-web-applications"></a><span data-ttu-id="58f9a-103">Sécurisation des microservices .NET et des applications web</span><span class="sxs-lookup"><span data-stu-id="58f9a-103">Securing .NET Microservices and Web Applications</span></span>

<span data-ttu-id="58f9a-104">Il est souvent nécessaire de limiter l’accès aux ressources et aux API exposées par un service à certains utilisateurs ou clients approuvés.</span><span class="sxs-lookup"><span data-stu-id="58f9a-104">It is often necessary for resources and APIs exposed by a service to be limited to certain trusted users or clients.</span></span> <span data-ttu-id="58f9a-105">La première étape d’une telle décision d’approbation au niveau des API passe par l’authentification.</span><span class="sxs-lookup"><span data-stu-id="58f9a-105">The first step to making these sorts of API-level trust decisions is authentication.</span></span> <span data-ttu-id="58f9a-106">L’authentification est le processus qui consiste à vérifier de manière fiable l’identité d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="58f9a-106">Authentication is the process of reliably ascertaining a user’s identity.</span></span>

<span data-ttu-id="58f9a-107">Dans les scénarios de microservice, l’authentification est généralement gérée de façon centralisée.</span><span class="sxs-lookup"><span data-stu-id="58f9a-107">In microservice scenarios, authentication is typically handled centrally.</span></span> <span data-ttu-id="58f9a-108">Si vous utilisez une passerelle d’API, celle-ci est parfaitement indiquée pour l’authentification, comme l’illustre la figure 11-1.</span><span class="sxs-lookup"><span data-stu-id="58f9a-108">If you are using an API Gateway, the gateway is a good place to authenticate, as shown in Figure 11-1.</span></span> <span data-ttu-id="58f9a-109">Si vous utilisez cette approche, vérifiez que les différents microservices ne sont pas directement accessibles (sans la passerelle d’API), à moins qu’un dispositif de sécurité supplémentaire ait été mis en place pour authentifier les messages en provenance ou non de la passerelle.</span><span class="sxs-lookup"><span data-stu-id="58f9a-109">If you use this approach, make sure that the individual microservices cannot be reached directly (without the API Gateway) unless additional security is in place to authenticate messages whether they come from the gateway or not.</span></span>

![](./media/image1.png)

<span data-ttu-id="58f9a-110">**Figure 11-1** :</span><span class="sxs-lookup"><span data-stu-id="58f9a-110">**Figure 11-1**.</span></span> <span data-ttu-id="58f9a-111">authentification centralisée avec une passerelle d’API</span><span class="sxs-lookup"><span data-stu-id="58f9a-111">Centralized authentication with an API Gateway</span></span>

<span data-ttu-id="58f9a-112">Si les services sont directement accessibles, il est possible d’authentifier les utilisateurs à l’aide d’un service d’authentification comme Azure Active Directory ou un microservice d’authentification dédié faisant office de service d’émission jeton de sécurité (STS).</span><span class="sxs-lookup"><span data-stu-id="58f9a-112">If services can be accessed directly, an authentication service like Azure Active Directory or a dedicated authentication microservice acting as a security token service (STS) can be used to authenticate users.</span></span> <span data-ttu-id="58f9a-113">Les décisions d’approbation sont partagées entre les services au moyen de jetons de sécurité ou de cookies.</span><span class="sxs-lookup"><span data-stu-id="58f9a-113">Trust decisions are shared between services with security tokens or cookies.</span></span> <span data-ttu-id="58f9a-114">(Elles peuvent être partagées entre applications, si nécessaire, dans ASP.NET Core avec les [services de protection des données](https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing#sharing-authentication-cookies-between-applications).) Ce modèle est illustré dans la figure 11-2.</span><span class="sxs-lookup"><span data-stu-id="58f9a-114">(These can be shared between applications, if needed, in ASP.NET Core with [data protection services](https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing#sharing-authentication-cookies-between-applications).) This pattern is illustrated in Figure 11-2.</span></span>

![](./media/image2.png)

<span data-ttu-id="58f9a-115">**(Figure 11-2)**  :</span><span class="sxs-lookup"><span data-stu-id="58f9a-115">**Figure 11-2**.</span></span> <span data-ttu-id="58f9a-116">authentification par un microservice d’identité ; l’approbation est partagée à l’aide d’un jeton d’autorisation</span><span class="sxs-lookup"><span data-stu-id="58f9a-116">Authentication by identity microservice; trust is shared using an authorization token</span></span>

## <a name="authenticating-using-aspnet-core-identity"></a><span data-ttu-id="58f9a-117">Authentification à l’aide d’ASP.NET Core Identity</span><span class="sxs-lookup"><span data-stu-id="58f9a-117">Authenticating using ASP.NET Core Identity</span></span>

<span data-ttu-id="58f9a-118">Dans ASP.NET Core, le principal mécanisme d’identification des utilisateurs d’une application est le système d’appartenance [ASP.NET Core Identity](https://docs.microsoft.com/aspnet/core/security/authentication/identity).</span><span class="sxs-lookup"><span data-stu-id="58f9a-118">The primary mechanism in ASP.NET Core for identifying an application’s users is the [ASP.NET Core Identity](https://docs.microsoft.com/aspnet/core/security/authentication/identity) membership system.</span></span> <span data-ttu-id="58f9a-119">ASP.NET Core Identity stocke les informations utilisateur (notamment les informations de connexion, les rôles et les revendications) dans un magasin de données configuré par le développeur.</span><span class="sxs-lookup"><span data-stu-id="58f9a-119">ASP.NET Core Identity stores user information (including sign-in information, roles, and claims) in a data store configured by the developer.</span></span> <span data-ttu-id="58f9a-120">En règle générale, le magasin de données d’ASP.NET Core Identity est un magasin Entity Framework fourni avec le package Microsoft.AspNetCore.Identity.EntityFrameworkCore.</span><span class="sxs-lookup"><span data-stu-id="58f9a-120">Typically, the ASP.NET Core Identity data store is an Entity Framework store provided in the Microsoft.AspNetCore.Identity.EntityFrameworkCore package.</span></span> <span data-ttu-id="58f9a-121">Cependant, il est possible d’utiliser des magasins personnalisés ou d’autres packages tiers pour stocker les informations d’identité dans le Stockage Table Azure, DocumentDB ou à d’autres emplacements.</span><span class="sxs-lookup"><span data-stu-id="58f9a-121">However, custom stores or other third-party packages can be used to store identity information in Azure Table Storage, DocumentDB, or other locations.</span></span>

<span data-ttu-id="58f9a-122">Le code ci-dessous est extrait du modèle de projet d’application web ASP.NET Core avec l’authentification de compte d’utilisateur individuel sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="58f9a-122">The following code is taken from the ASP.NET Core Web Application project template with individual user account authentication selected.</span></span> <span data-ttu-id="58f9a-123">Il montre comment configurer ASP.NET Core Identity en utilisant EntityFramework.Core dans la méthode Startup.ConfigureServices.</span><span class="sxs-lookup"><span data-stu-id="58f9a-123">It shows how to configure ASP.NET Core Identity using EntityFramework.Core in the Startup.ConfigureServices method.</span></span>

```csharp
services.AddDbContext<ApplicationDbContext>(options =>
    options.UseSqlServer(Configuration.GetConnectionString("DefaultConnection")));
    services.AddIdentity<ApplicationUser, IdentityRole>()
        .AddEntityFrameworkStores<ApplicationDbContext>()
        .AddDefaultTokenProviders();
```

<span data-ttu-id="58f9a-124">Une fois ASP.NET Core Identity configuré, il convient de l’activer en appelant app.UseIdentity dans la méthode Startup.Configure du service.</span><span class="sxs-lookup"><span data-stu-id="58f9a-124">Once ASP.NET Core Identity is configured, you enable it by calling app.UseIdentity in the service’s Startup.Configure method.</span></span>

<span data-ttu-id="58f9a-125">L’utilisation d’ASP.NET Code Identity autorise plusieurs scénarios :</span><span class="sxs-lookup"><span data-stu-id="58f9a-125">Using ASP.NET Code Identity enables several scenarios:</span></span>

-   <span data-ttu-id="58f9a-126">Création d’informations utilisateur à l’aide du type UserManager (userManager.CreateAsync).</span><span class="sxs-lookup"><span data-stu-id="58f9a-126">Create new user information using the UserManager type (userManager.CreateAsync).</span></span>

-   <span data-ttu-id="58f9a-127">Authentification des utilisateurs à l’aide du type SignInManager.</span><span class="sxs-lookup"><span data-stu-id="58f9a-127">Authenticate users using the SignInManager type.</span></span> <span data-ttu-id="58f9a-128">Vous pouvez utiliser signInManager.SignInAsync pour permettre aux utilisateurs de se connecter directement ou signInManager.PasswordSignInAsync pour vérifier que leur mot de passe est correct avant de les connecter.</span><span class="sxs-lookup"><span data-stu-id="58f9a-128">You can use signInManager.SignInAsync to sign in directly, or signInManager.PasswordSignInAsync to confirm the user’s password is correct and then sign them in.</span></span>

-   <span data-ttu-id="58f9a-129">Identification d’un utilisateur en fonction des informations stockées dans un cookie (qui est lu par l’intergiciel ASP.NET Core Identity) de telle sorte que les requêtes suivantes d’un navigateur incluent l’identité et les revendications de l’utilisateur connecté.</span><span class="sxs-lookup"><span data-stu-id="58f9a-129">Identify a user based on information stored in a cookie (which is read by ASP.NET Core Identity middleware) so that subsequent requests from a browser will include a signed-in user’s identity and claims.</span></span>

<span data-ttu-id="58f9a-130">Par ailleurs, ASP.NET Core Identity prend en charge l’[authentification à deux facteurs](https://docs.microsoft.com/aspnet/core/security/authentication/2fa).</span><span class="sxs-lookup"><span data-stu-id="58f9a-130">ASP.NET Core Identity also supports [two-factor authentication](https://docs.microsoft.com/aspnet/core/security/authentication/2fa).</span></span>

<span data-ttu-id="58f9a-131">Pour les scénarios d’authentification qui utilisent un magasin de données utilisateur local et qui conservent l’identité entre les requêtes au moyen de cookies (comme c’est généralement le cas avec les applications web MVC), ASP.NET Core Identity est une solution recommandée.</span><span class="sxs-lookup"><span data-stu-id="58f9a-131">For authentication scenarios that make use of a local user data store and that persist identity between requests using cookies (as is typical for MVC web applications), ASP.NET Core Identity is a recommended solution.</span></span>

## <a name="authenticating-using-external-providers"></a><span data-ttu-id="58f9a-132">Authentification à l’aide de fournisseurs externes</span><span class="sxs-lookup"><span data-stu-id="58f9a-132">Authenticating using external providers</span></span>

<span data-ttu-id="58f9a-133">ASP.NET Core prend aussi en charge l’utilisation de [fournisseurs d’authentification externes](https://docs.microsoft.com/aspnet/core/security/authentication/social/) pour permettre aux utilisateurs de se connecter via des flux [OAuth 2.0](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2).</span><span class="sxs-lookup"><span data-stu-id="58f9a-133">ASP.NET Core also supports using [external authentication providers](https://docs.microsoft.com/aspnet/core/security/authentication/social/) to let users log in via [OAuth 2.0](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2) flows.</span></span> <span data-ttu-id="58f9a-134">Cela signifie que les utilisateurs peuvent se connecter en utilisant les processus d’authentification existants de certains fournisseurs tels que Microsoft, Google, Facebook ou Twitter et associer ces identités à une identité ASP.NET Core dans votre application.</span><span class="sxs-lookup"><span data-stu-id="58f9a-134">This means that users can log in using existing authentication processes from providers like Microsoft, Google, Facebook, or Twitter and associate those identities with an ASP.NET Core identity in your application.</span></span>

<span data-ttu-id="58f9a-135">Pour utiliser l’authentification externe, vous devez intégrer l’intergiciel (middleware) d’authentification approprié au pipeline de traitement des requêtes HTTP de votre application.</span><span class="sxs-lookup"><span data-stu-id="58f9a-135">To use external authentication, you include the appropriate authentication middleware in your application’s HTTP request processing pipeline.</span></span> <span data-ttu-id="58f9a-136">Cet intergiciel est chargé de gérer les requêtes pour retourner les itinéraires d’URI du fournisseur d’authentification, capturant ainsi les informations d’identité et les mettant à disposition via la méthode SignInManager.GetExternalLoginInfo.</span><span class="sxs-lookup"><span data-stu-id="58f9a-136">This middleware is responsible for handling requests to return URI routes from the authentication provider, capturing identity information, and making it available via the SignInManager.GetExternalLoginInfo method.</span></span>

<span data-ttu-id="58f9a-137">Les fournisseurs d’authentification externes courants et les packages NuGet qui leur sont associés vous sont présentés ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="58f9a-137">Popular external authentication providers and their associated NuGet packages are shown below.</span></span>

<span data-ttu-id="58f9a-138">**Microsoft :** Microsoft.AspNetCore.Authentication.MicrosoftAccount</span><span class="sxs-lookup"><span data-stu-id="58f9a-138">**Microsoft:** Microsoft.AspNetCore.Authentication.MicrosoftAccount</span></span>

<span data-ttu-id="58f9a-139">**Google :** Microsoft.AspNetCore.Authentication.Google</span><span class="sxs-lookup"><span data-stu-id="58f9a-139">**Google:** Microsoft.AspNetCore.Authentication.Google</span></span>

<span data-ttu-id="58f9a-140">**Facebook :** Microsoft.AspNetCore.Authentication.Facebook</span><span class="sxs-lookup"><span data-stu-id="58f9a-140">**Facebook:** Microsoft.AspNetCore.Authentication.Facebook</span></span>

<span data-ttu-id="58f9a-141">**Twitter :** Microsoft.AspNetCore.Authentication.Twitter</span><span class="sxs-lookup"><span data-stu-id="58f9a-141">**Twitter:** Microsoft.AspNetCore.Authentication.Twitter</span></span>

<span data-ttu-id="58f9a-142">Dans tous les cas, l’intergiciel est inscrit avec un appel à une méthode d’inscription similaire à app.Use{ExternalProvider}Authentication dans Startup.Configure.</span><span class="sxs-lookup"><span data-stu-id="58f9a-142">In all cases, the middleware is registered with a call to a registration method similar to app.Use{ExternalProvider}Authentication in Startup.Configure.</span></span> <span data-ttu-id="58f9a-143">Ces méthodes d’inscription prennent un objet d’options qui contient un ID d’application et des informations confidentielles (par exemple, un mot de passe), selon les besoins du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="58f9a-143">These registration methods take an options object that contains an application ID and secret information (a password, for instance), as needed by the provider.</span></span> <span data-ttu-id="58f9a-144">Les fournisseurs d’authentification externes exigent l’inscription des applications (comme expliqué dans la [documentation ASP.NET Core](https://docs.microsoft.com/aspnet/core/security/authentication/social/)) de façon à faire savoir aux utilisateurs quelle application demande l’accès à leur identité.</span><span class="sxs-lookup"><span data-stu-id="58f9a-144">External authentication providers require the application to be registered (as explained in [ASP.NET Core documentation](https://docs.microsoft.com/aspnet/core/security/authentication/social/)) so that they can inform the user what application is requesting access to their identity.</span></span>

<span data-ttu-id="58f9a-145">Une fois que l’intergiciel est inscrit dans Startup.Configure, vous pouvez inviter les utilisateurs à se connecter à partir de n’importe quelle action de contrôleur.</span><span class="sxs-lookup"><span data-stu-id="58f9a-145">Once the middleware is registered in Startup.Configure, you can prompt users to log in from any controller action.</span></span> <span data-ttu-id="58f9a-146">Pour ce faire, vous devez créer un objet AuthenticationProperties contenant le nom du fournisseur d’authentification et une URL de redirection.</span><span class="sxs-lookup"><span data-stu-id="58f9a-146">To do this, you create an AuthenticationProperties object that includes the authentication provider’s name and a redirect URL.</span></span> <span data-ttu-id="58f9a-147">Retournez ensuite une réponse de test qui transmet l’objet AuthenticationProperties.</span><span class="sxs-lookup"><span data-stu-id="58f9a-147">You then return a Challenge response that passes the AuthenticationProperties object.</span></span> <span data-ttu-id="58f9a-148">Le code ci-dessous illustre cela.</span><span class="sxs-lookup"><span data-stu-id="58f9a-148">The following code shows an example of this.</span></span>

```csharp
var properties = _signInManager.ConfigureExternalAuthenticationProperties(provider,
    redirectUrl);
return Challenge(properties, provider);
```

<span data-ttu-id="58f9a-149">Le paramètre redirectUrl comprend l’URL vers laquelle le fournisseur externe doit rediriger l’utilisateur une fois celui-ci authentifié.</span><span class="sxs-lookup"><span data-stu-id="58f9a-149">The redirectUrl parameter includes the URL that the external provider should redirect to once the user has authenticated.</span></span> <span data-ttu-id="58f9a-150">L’URL doit représenter une action qui va connecter l’utilisateur à partir d’informations d’identité externes, comme dans l’exemple simplifié ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="58f9a-150">The URL should represent an action that will sign the user in based on external identity information, as in the following simplified example:</span></span>

```csharp
// Sign in the user with this external login provider if the user
// already has a login.
var result = await _signInManager.ExternalLoginSignInAsync(info.LoginProvider, info.ProviderKey, isPersistent: false);

if (result.Succeeded)
{
    return RedirectToLocal(returnUrl);
}
else
{
    ApplicationUser newUser = new ApplicationUser
    {
        // The user object can be constructed with claims from the
        // external authentication provider, combined with information
        // supplied by the user after they have authenticated with
        // the external provider.
        UserName = info.Principal.FindFirstValue(ClaimTypes.Name),
        Email = info.Principal.FindFirstValue(ClaimTypes.Email)
    };
    var identityResult = await _userManager.CreateAsync(newUser);
    if (identityResult.Succeeded)
    {
        identityResult = await _userManager.AddLoginAsync(newUser, info);
        if (identityResult.Succeeded)
        {
            await _signInManager.SignInAsync(newUser, isPersistent: false);
        }
        return RedirectToLocal(returnUrl);
    }
}
```

<span data-ttu-id="58f9a-151">Si vous optez pour l’option d’authentification **Compte d’utilisateur individuel** au moment de créer le projet d’application web ASP.NET Code dans Visual Studio, l’ensemble du code nécessaire à la connexion avec un fournisseur externe est déjà présent dans le projet, comme le montre la figure 11-3.</span><span class="sxs-lookup"><span data-stu-id="58f9a-151">If you choose the **Individual User Account** authentication option when you create the ASP.NET Code web application project in Visual Studio, all the code necessary to sign in with an external provider is already in the project, as shown in Figure 11-3.</span></span>

![https://msdnshared.blob.core.windows.net/media/2016/10/new-web-app.png](./media/image3.png)

<span data-ttu-id="58f9a-152">**(Figure 11-3)**  :</span><span class="sxs-lookup"><span data-stu-id="58f9a-152">**Figure 11-3**.</span></span> <span data-ttu-id="58f9a-153">sélection d’une option visant à utiliser l’authentification externe pendant la création d’un projet d’application web</span><span class="sxs-lookup"><span data-stu-id="58f9a-153">Selecting an option for using external authentication when creating a web application project</span></span>

<span data-ttu-id="58f9a-154">Outre les fournisseurs d’authentification externe mentionnés ci-dessus, il existe des packages tiers qui proposent un intergiciel permettant l’utilisation d’un nombre bien plus important de fournisseurs d’authentification externe.</span><span class="sxs-lookup"><span data-stu-id="58f9a-154">In addition to the external authentication providers listed previously, third-party packages are available that provide middleware for using many more external authentication providers.</span></span> <span data-ttu-id="58f9a-155">Pour obtenir la liste, consultez le dépôt [AspNet.Security.OAuth.Providers](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src) sur GitHub.</span><span class="sxs-lookup"><span data-stu-id="58f9a-155">For a list, see the [AspNet.Security.OAuth.Providers](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src) repo on GitHub.</span></span>

<span data-ttu-id="58f9a-156">Bien entendu, vous pouvez aussi créer votre propre intergiciel d’authentification externe.</span><span class="sxs-lookup"><span data-stu-id="58f9a-156">It is also possible, of course, to create your own external authentication middleware.</span></span>

## <a name="authenticating-with-bearer-tokens"></a><span data-ttu-id="58f9a-157">Authentification avec des jetons du porteur</span><span class="sxs-lookup"><span data-stu-id="58f9a-157">Authenticating with bearer tokens</span></span>

<span data-ttu-id="58f9a-158">L’authentification avec ASP.NET Core Identity (ou Identity couplé à des fournisseurs d’authentification externe) est parfaitement adaptée à de nombreux scénarios d’application web dans lesquels il est approprié de stocker les informations utilisateur dans un cookie.</span><span class="sxs-lookup"><span data-stu-id="58f9a-158">Authenticating with ASP.NET Core Identity (or Identity plus external authentication providers) works well for many web application scenarios in which storing user information in a cookie is appropriate.</span></span> <span data-ttu-id="58f9a-159">En revanche, dans d’autres scénarios, il n’est pas commun de conserver et de transmettre les données au moyen de cookies.</span><span class="sxs-lookup"><span data-stu-id="58f9a-159">In other scenarios, though, cookies are not a natural means of persisting and transmitting data.</span></span>

<span data-ttu-id="58f9a-160">Par exemple, dans une API web ASP.NET Core qui expose les points de terminaison RESTful potentiellement accessibles par des applications à page unique, des clients natifs, voire d’autres API web, l’authentification par jeton du porteur est généralement privilégiée.</span><span class="sxs-lookup"><span data-stu-id="58f9a-160">For example, in an ASP.NET Core Web API that exposes RESTful endpoints that might be accessed by Single Page Applications (SPAs), by native clients, or even by other Web APIs, you typically want to use bearer token authentication instead.</span></span> <span data-ttu-id="58f9a-161">Les applications de ce type n’utilisent pas de cookies, mais elles peuvent facilement récupérer un jeton du porteur et l’inclure dans l’en-tête d’autorisation des requêtes suivantes.</span><span class="sxs-lookup"><span data-stu-id="58f9a-161">These types of applications do not work with cookies, but can easily retrieve a bearer token and include it in the authorization header of subsequent requests.</span></span> <span data-ttu-id="58f9a-162">Pour activer l’authentification par jeton, ASP.NET Core prend en charge plusieurs options en vue d’utiliser [OAuth 2.0](https://oauth.net/2/) et [OpenID Connect](https://openid.net/connect/).</span><span class="sxs-lookup"><span data-stu-id="58f9a-162">To enable token authentication, ASP.NET Core supports several options for using [OAuth 2.0](https://oauth.net/2/) and [OpenID Connect](https://openid.net/connect/).</span></span>

## <a name="authenticating-with-an-openid-connect-or-oauth-20-identity-provider"></a><span data-ttu-id="58f9a-163">Authentification avec un fournisseur d’identité OpenID Connect ou OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="58f9a-163">Authenticating with an OpenID Connect or OAuth 2.0 Identity provider</span></span>

<span data-ttu-id="58f9a-164">Si les informations utilisateur sont stockées dans Azure Active Directory ou une autre solution d’identité qui prend en charge OpenID Connect ou OAuth 2.0, vous pouvez utiliser le package Microsoft.AspNetCore.Authentication.OpenIdConnect pour une authentification à l’aide du flux de travail OpenID Connect.</span><span class="sxs-lookup"><span data-stu-id="58f9a-164">If user information is stored in Azure Active Directory or another identity solution that supports OpenID Connect or OAuth 2.0, you can use the Microsoft.AspNetCore.Authentication.OpenIdConnect package to authenticate using the OpenID Connect workflow.</span></span> <span data-ttu-id="58f9a-165">Par exemple, pour s’[authentifier auprès d’Azure Active Directory](https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/), une application web ASP.NET Core peut utiliser l’intergiciel de ce package, comme dans l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="58f9a-165">For example, to [authenticate against Azure Active Directory](https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/), an ASP.NET Core web application can use middleware from that package as shown in the following example:</span></span>

```csharp
// Configure the OWIN pipeline to use OpenID Connect auth
app.UseOpenIdConnectAuthentication(new OpenIdConnectOptions
{
    ClientId = Configuration["AzureAD:ClientId"],
    Authority = String.Format(Configuration["AzureAd:AadInstance"],
    Configuration["AzureAd:Tenant"]),
    ResponseType = OpenIdConnectResponseType.IdToken,
    PostLogoutRedirectUri = Configuration["AzureAd:PostLogoutRedirectUri"]
});
```

<span data-ttu-id="58f9a-166">Les valeurs de configuration sont les valeurs d’Azure Active Directory créées au moment où votre application est [inscrite en tant que client Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios#basics-of-registering-an-application-in-azure-ad).</span><span class="sxs-lookup"><span data-stu-id="58f9a-166">The configuration values are Azure Active Directory values that are created when your application is [registered as an Azure AD client](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios#basics-of-registering-an-application-in-azure-ad).</span></span> <span data-ttu-id="58f9a-167">Un même ID client peut être partagé entre plusieurs microservices d’une application s’ils doivent tous authentifier les utilisateurs authentifiés via Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="58f9a-167">A single client ID can be shared among multiple microservices in an application if they all need to authenticate users authenticated via Azure Active Directory.</span></span>

<span data-ttu-id="58f9a-168">Notez que lorsque vous utilisez ce flux de travail, l’intergiciel ASP.NET Core Identity n’est pas nécessaire dans la mesure où le stockage des informations utilisateur et l’authentification sont assurés par Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="58f9a-168">Note that when you use this workflow, the ASP.NET Core Identity middleware is not needed, because all user information storage and authentication is handled by Azure Active Directory.</span></span>

## <a name="issuing-security-tokens-from-an-aspnet-core-service"></a><span data-ttu-id="58f9a-169">Émission de jetons de sécurité à partir d’un service ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="58f9a-169">Issuing security tokens from an ASP.NET Core service</span></span>

<span data-ttu-id="58f9a-170">Si vous préférez émettre des jetons de sécurité pour les utilisateurs locaux d’ASP.NET Core Identity plutôt que de faire appel à un fournisseur d’identité externe, vous pouvez profiter de quelques bibliothèques intéressantes.</span><span class="sxs-lookup"><span data-stu-id="58f9a-170">If you prefer to issue security tokens for local ASP.NET Core Identity users rather than using an external identity provider, you can take advantage of some good third-party libraries.</span></span>

<span data-ttu-id="58f9a-171">[IdentityServer4](https://github.com/IdentityServer/IdentityServer4) et [OpenIddict](https://github.com/openiddict/openiddict-core) sont des fournisseurs OpenID Connect qui s’intègrent facilement à ASP.NET Core Identity pour vous permettre d’émettre des jetons de sécurité à partir d’un service ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="58f9a-171">[IdentityServer4](https://github.com/IdentityServer/IdentityServer4) and [OpenIddict](https://github.com/openiddict/openiddict-core) are OpenID Connect providers that integrate easily with ASP.NET Core Identity to let you issue security tokens from an ASP.NET Core service.</span></span> <span data-ttu-id="58f9a-172">La [documentation IdentityServer4](https://identityserver4.readthedocs.io/en/release/) explique en détail comment utiliser la bibliothèque.</span><span class="sxs-lookup"><span data-stu-id="58f9a-172">The [IdentityServer4 documentation](https://identityserver4.readthedocs.io/en/release/) has in-depth instructions for using the library.</span></span> <span data-ttu-id="58f9a-173">Ceci étant, voici sommairement comment émettre des jetons à l’aide d’IdentityServer4 :</span><span class="sxs-lookup"><span data-stu-id="58f9a-173">However, the basic steps to using IdentityServer4 to issue tokens are as follows.</span></span>

1.  <span data-ttu-id="58f9a-174">Appelez app.UseIdentityServer dans la méthode Startup.Configure pour ajouter IdentityServer4 au pipeline de traitement des requêtes HTTP de l’application.</span><span class="sxs-lookup"><span data-stu-id="58f9a-174">You call app.UseIdentityServer in the Startup.Configure method to add IdentityServer4 to the application’s HTTP request processing pipeline.</span></span> <span data-ttu-id="58f9a-175">Cela permet à la bibliothèque de remettre les requêtes aux points de terminaison OpenID Connect et OAuth2 comme connect/token.</span><span class="sxs-lookup"><span data-stu-id="58f9a-175">This lets the library serve requests to OpenID Connect and OAuth2 endpoints like /connect/token.</span></span>

2.  <span data-ttu-id="58f9a-176">Configurez IdentityServer4 dans Startup.ConfigureServices en effectuant un appel à services.AddIdentityServer.</span><span class="sxs-lookup"><span data-stu-id="58f9a-176">You configure IdentityServer4 in Startup.ConfigureServices by making a call to services.AddIdentityServer.</span></span>

3.  <span data-ttu-id="58f9a-177">Configurez le serveur d’identité en fournissant les données suivantes :</span><span class="sxs-lookup"><span data-stu-id="58f9a-177">You configure identity server by providing the following data:</span></span>

-   <span data-ttu-id="58f9a-178">Les [informations d’identification](https://identityserver4.readthedocs.io/en/release/topics/crypto.html) à utiliser pour la signature.</span><span class="sxs-lookup"><span data-stu-id="58f9a-178">The [credentials](https://identityserver4.readthedocs.io/en/release/topics/crypto.html) to use for signing.</span></span>

-   <span data-ttu-id="58f9a-179">Les [ressources d’identité et d’API](https://identityserver4.readthedocs.io/en/release/topics/resources.html) auxquelles les utilisateurs pourraient demander à accéder :</span><span class="sxs-lookup"><span data-stu-id="58f9a-179">The [Identity and API resources](https://identityserver4.readthedocs.io/en/release/topics/resources.html) that users might request access to:</span></span>

<!-- -->

-   <span data-ttu-id="58f9a-180">Les ressources d’API représentent les données protégées ou les fonctionnalités auxquelles un utilisateur peut accéder avec un jeton d’accès.</span><span class="sxs-lookup"><span data-stu-id="58f9a-180">API resources represent protected data or functionality that a user can access with an access token.</span></span> <span data-ttu-id="58f9a-181">Par exemple, il peut s’agit d’une API web (ou un ensemble d’API) qui nécessite une autorisation.</span><span class="sxs-lookup"><span data-stu-id="58f9a-181">An example of an API resource would be a web API (or set of APIs) that requires authorization.</span></span>

-   <span data-ttu-id="58f9a-182">Les ressources d’identité représentent les informations (revendications) qui sont fournies à un client pour identifier un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="58f9a-182">Identity resources represent information (claims) that are given to a client to identify a user.</span></span> <span data-ttu-id="58f9a-183">Les revendications peuvent inclure le nom d’utilisateur, l’adresse de messagerie, etc.</span><span class="sxs-lookup"><span data-stu-id="58f9a-183">The claims might include the user name, email address, and so on.</span></span>

<!-- -->

-   <span data-ttu-id="58f9a-184">Les [clients](https://identityserver4.readthedocs.io/en/release/topics/clients.html) appelés à se connecter pour demander des jetons.</span><span class="sxs-lookup"><span data-stu-id="58f9a-184">The [clients](https://identityserver4.readthedocs.io/en/release/topics/clients.html) that will be connecting in order to request tokens.</span></span>

-   <span data-ttu-id="58f9a-185">Le mécanisme de stockage des informations de l’utilisateur, tel que [ASP.NET Core Identity](https://identityserver4.readthedocs.io/en/release/quickstarts/6_aspnet_identity.html) ou une solution équivalente.</span><span class="sxs-lookup"><span data-stu-id="58f9a-185">The storage mechanism for user information, such as [ASP.NET Core Identity](https://identityserver4.readthedocs.io/en/release/quickstarts/6_aspnet_identity.html) or an alternative.</span></span>

<span data-ttu-id="58f9a-186">Au moment de spécifier les clients et les ressources que doit utiliser IdentityServer4, vous pouvez transmettre une collection IEnumerable&lt;T&gt; du type approprié aux méthodes qui acceptent les magasins de clients ou de ressources en mémoire.</span><span class="sxs-lookup"><span data-stu-id="58f9a-186">When you specify clients and resources for IdentityServer4 to use, you can pass an IEnumerable&lt;T&gt; collection of the appropriate type to methods that take in-memory client or resource stores.</span></span> <span data-ttu-id="58f9a-187">Pour les scénarios plus complexes, vous pouvez aussi indiquer des types de fournisseurs de clients ou de ressources via l’injection de dépendances.</span><span class="sxs-lookup"><span data-stu-id="58f9a-187">Or for more complex scenarios, you can provide client or resource provider types via Dependency Injection.</span></span>

<span data-ttu-id="58f9a-188">Voici un exemple de configuration qui vise à faire utiliser à IdentityServer4 les ressources et les clients en mémoire fournis par un type IClientStore personnalisé :</span><span class="sxs-lookup"><span data-stu-id="58f9a-188">A sample configuration for IdentityServer4 to use in-memory resources and clients provided by a custom IClientStore type might look like the following example:</span></span>

```csharp
// Add IdentityServer services
services.AddSingleton<IClientStore, CustomClientStore>();
services.AddIdentityServer()
    .AddSigningCredential("CN=sts")
    .AddInMemoryApiResources(MyApiResourceProvider.GetAllResources())
    .AddAspNetIdentity<ApplicationUser>();
```

## <a name="consuming-security-tokens"></a><span data-ttu-id="58f9a-189">Utilisation de jetons de sécurité</span><span class="sxs-lookup"><span data-stu-id="58f9a-189">Consuming security tokens</span></span>

<span data-ttu-id="58f9a-190">L’authentification auprès d’un point de terminaison OpenID Connect ou l’émission de vos propres jetons de sécurité recouvrent certains scénarios.</span><span class="sxs-lookup"><span data-stu-id="58f9a-190">Authenticating against an OpenID Connect endpoint or issuing your own security tokens covers some scenarios.</span></span> <span data-ttu-id="58f9a-191">Mais qu’en est-il d’un service qui doit simplement limiter l’accès aux utilisateurs disposant de jetons de sécurité valides qui ont été fournis par un autre service ?</span><span class="sxs-lookup"><span data-stu-id="58f9a-191">But what about a service that simply needs to limit access to those users who have valid security tokens that were provided by a different service?</span></span>

<span data-ttu-id="58f9a-192">Pour ce scénario, l’intergiciel d’authentification qui gère les jetons JWT est disponible dans le package Microsoft.AspNetCore.Authentication.JwtBearer.</span><span class="sxs-lookup"><span data-stu-id="58f9a-192">For that scenario, authentication middleware that handles JWT tokens is available in the Microsoft.AspNetCore.Authentication.JwtBearer package.</span></span> <span data-ttu-id="58f9a-193">JWT est l’acronyme de « [JSON Web Token](https://tools.ietf.org/html/rfc7519) » (jeton web JSON). Il s’agit d’un format de jeton de sécurité courant (défini par la norme RFC 7519) destiné à communiquer les revendications de sécurité.</span><span class="sxs-lookup"><span data-stu-id="58f9a-193">JWT stands for "[JSON Web Token](https://tools.ietf.org/html/rfc7519)" and is a common security token format (defined by RFC 7519) for communicating security claims.</span></span> <span data-ttu-id="58f9a-194">L’exemple simple présenté ci-dessous montre comment utiliser les jetons de ce type avec l’intergiciel.</span><span class="sxs-lookup"><span data-stu-id="58f9a-194">A simple example of how to use middleware to consume such tokens might look like the following example.</span></span> <span data-ttu-id="58f9a-195">Ce code doit précéder les appels à l’intergiciel ASP.NET Core MVC (appn.UseMvc).</span><span class="sxs-lookup"><span data-stu-id="58f9a-195">This code must precede calls to ASP.NET Core MVC middleware (app.UseMvc).</span></span>

```csharp
app.UseJwtBearerAuthentication(new JwtBearerOptions()
{
    Audience = "http://localhost:5001/",
    Authority = "http://localhost:5000/",
    AutomaticAuthenticate = true
});
```

<span data-ttu-id="58f9a-196">Les paramètres utilisés dans ce cas sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="58f9a-196">The parameters in this usage are:</span></span>

-   <span data-ttu-id="58f9a-197">Audience représente le récepteur du jeton entrant ou la ressource à laquelle le jeton accorde l’accès.</span><span class="sxs-lookup"><span data-stu-id="58f9a-197">Audience represents the receiver of the incoming token or the resource that the token grants access to.</span></span> <span data-ttu-id="58f9a-198">Si la valeur spécifiée dans ce paramètre ne correspond pas à celle du paramètre aud du jeton, celui-ci est rejeté.</span><span class="sxs-lookup"><span data-stu-id="58f9a-198">If the value specified in this parameter does not match the aud parameter in the token, the token will be rejected.</span></span>

-   <span data-ttu-id="58f9a-199">Authority est l’adresse du serveur d’authentification émetteur de jetons.</span><span class="sxs-lookup"><span data-stu-id="58f9a-199">Authority is the address of the token-issuing authentication server.</span></span> <span data-ttu-id="58f9a-200">L’intergiciel d’authentification du porteur de jeton JWT utilise cet URI pour obtenir la clé publique qui permet de valider la signature du jeton.</span><span class="sxs-lookup"><span data-stu-id="58f9a-200">The JWT bearer authentication middleware uses this URI to get the public key that can be used to validate the token's signature.</span></span> <span data-ttu-id="58f9a-201">Par ailleurs, l’intergiciel vérifie que la valeur du paramètre iss du jeton correspond à cet URI.</span><span class="sxs-lookup"><span data-stu-id="58f9a-201">The middleware also confirms that the iss parameter in the token matches this URI.</span></span>

-   <span data-ttu-id="58f9a-202">AutomaticAuthenticate est une valeur booléenne qui indique si l’utilisateur défini par le jeton doit être connecté automatiquement.</span><span class="sxs-lookup"><span data-stu-id="58f9a-202">AutomaticAuthenticate is a Boolean value that indicates whether the user defined by the token should be automatically signed in.</span></span>

<span data-ttu-id="58f9a-203">Un autre paramètre, RequireHttpsMetadata, n’est pas utilisé dans cet exemple.</span><span class="sxs-lookup"><span data-stu-id="58f9a-203">Another parameter, RequireHttpsMetadata, is not used in this example.</span></span> <span data-ttu-id="58f9a-204">Il est utile pour les tests ; la valeur false est affectée à ce paramètre pour effectuer des tests dans des environnements dépourvus de certificats.</span><span class="sxs-lookup"><span data-stu-id="58f9a-204">It is useful for testing purposes; you set this parameter to false so that you can test in environments where you do not have certificates.</span></span> <span data-ttu-id="58f9a-205">Dans les déploiements réels, les jetons du porteur JWT doivent toujours être transmis uniquement sur HTTPS.</span><span class="sxs-lookup"><span data-stu-id="58f9a-205">In real-world deployments, JWT bearer tokens should always be passed only over HTTPS.</span></span>

<span data-ttu-id="58f9a-206">Quand cet intergiciel est en place, les jetons JWT sont automatiquement extraits des en-têtes d’autorisation.</span><span class="sxs-lookup"><span data-stu-id="58f9a-206">With this middleware in place, JWT tokens are automatically extracted from authorization headers.</span></span> <span data-ttu-id="58f9a-207">Ils sont ensuite désérialisés, validés (en utilisant les valeurs des paramètres Audience et Authority) puis stockés en tant qu’informations utilisateur pour être référencées par la suite par des actions MVC ou des filtres d’autorisation.</span><span class="sxs-lookup"><span data-stu-id="58f9a-207">They are then deserialized, validated (using the values in the Audience and Authority parameters), and stored as user information to be referenced later by MVC actions or authorization filters.</span></span>

<span data-ttu-id="58f9a-208">L’intergiciel d’authentification du porteur JWT peut aussi prendre en charge des scénarios plus avancés, tels que l’utilisation d’un certificat local pour valider un jeton si l’autorité n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="58f9a-208">The JWT bearer authentication middleware can also support more advanced scenarios, such as using a local certificate to validate a token if the authority is not available.</span></span> <span data-ttu-id="58f9a-209">Pour ce scénario, vous pouvez spécifier un objet TokenValidationParameters dans l’objet JwtBearerOptions.</span><span class="sxs-lookup"><span data-stu-id="58f9a-209">For this scenario, you can specify a TokenValidationParameters object in the JwtBearerOptions object.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="58f9a-210">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="58f9a-210">Additional resources</span></span>

-   <span data-ttu-id="58f9a-211">**Partage des cookies entre les applications**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing\#sharing-authentication-cookies-between-applications*](https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing#sharing-authentication-cookies-between-applications)</span><span class="sxs-lookup"><span data-stu-id="58f9a-211">**Sharing cookies between applications**
[*https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing\#sharing-authentication-cookies-between-applications*](https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing#sharing-authentication-cookies-between-applications)</span></span>

-   <span data-ttu-id="58f9a-212">**Présentation d’Identity**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/identity*](https://docs.microsoft.com/aspnet/core/security/authentication/identity)</span><span class="sxs-lookup"><span data-stu-id="58f9a-212">**Introduction to Identity**
[*https://docs.microsoft.com/aspnet/core/security/authentication/identity*](https://docs.microsoft.com/aspnet/core/security/authentication/identity)</span></span>

-   <span data-ttu-id="58f9a-213">**Rick Anderson. Authentification à 2 facteurs avec SMS**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/2fa*](https://docs.microsoft.com/aspnet/core/security/authentication/2fa)</span><span class="sxs-lookup"><span data-stu-id="58f9a-213">**Rick Anderson. Two-factor authentication with SMS**
[*https://docs.microsoft.com/aspnet/core/security/authentication/2fa*](https://docs.microsoft.com/aspnet/core/security/authentication/2fa)</span></span>

-   <span data-ttu-id="58f9a-214">**Activation de l’authentification à l’aide de Facebook, de Google et d’autres fournisseurs externes**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/social/*](https://docs.microsoft.com/aspnet/core/security/authentication/social/)</span><span class="sxs-lookup"><span data-stu-id="58f9a-214">**Enabling authentication using Facebook, Google and other external providers**
[*https://docs.microsoft.com/aspnet/core/security/authentication/social/*](https://docs.microsoft.com/aspnet/core/security/authentication/social/)</span></span>

-   <span data-ttu-id="58f9a-215">**Michell Anicas. Présentation d’OAuth 2**
    [*https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2*](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2)</span><span class="sxs-lookup"><span data-stu-id="58f9a-215">**Michell Anicas. An Introduction to OAuth 2**
[*https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2*](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2)</span></span>

-   <span data-ttu-id="58f9a-216">**AspNet.Security.OAuth.Providers** (dépôt GitHub pour fournisseurs d’autorisation OAuth ASP.NET :</span><span class="sxs-lookup"><span data-stu-id="58f9a-216">**AspNet.Security.OAuth.Providers** (GitHub repo for ASP.NET OAuth providers.</span></span>
    [*https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src*](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src)

-   <span data-ttu-id="58f9a-217">**Danny Strockis. Intégration d’Azure AD dans une application web ASP.NET Core**
    [*https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/*](https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/)</span><span class="sxs-lookup"><span data-stu-id="58f9a-217">**Danny Strockis. Integrating Azure AD into an ASP.NET Core web app**
[*https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/*](https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/)</span></span>

-   <span data-ttu-id="58f9a-218">**IdentityServer4. Documentation officielle**
    [*https://identityserver4.readthedocs.io/en/release/*](https://identityserver4.readthedocs.io/en/release/)</span><span class="sxs-lookup"><span data-stu-id="58f9a-218">**IdentityServer4. Official documentation**
[*https://identityserver4.readthedocs.io/en/release/*](https://identityserver4.readthedocs.io/en/release/)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="58f9a-219">[Précédent](../implement-resilient-applications/monitor-app-health.md)
[Suivant](authorization-net-microservices-web-applications.md)</span><span class="sxs-lookup"><span data-stu-id="58f9a-219">[Previous](../implement-resilient-applications/monitor-app-health.md)
[Next](authorization-net-microservices-web-applications.md)</span></span>

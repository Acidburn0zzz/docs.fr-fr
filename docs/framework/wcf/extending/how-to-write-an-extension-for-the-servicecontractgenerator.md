---
title: 'Comment : écrire une extension pour le ServiceContractGenerator'
ms.date: 03/30/2017
ms.assetid: 876ca823-bd16-4bdf-9e0f-02092df90e51
ms.openlocfilehash: 43105553739e104ab862b3be3cf2082fbf6d499f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33488658"
---
# <a name="how-to-write-an-extension-for-the-servicecontractgenerator"></a><span data-ttu-id="66b96-102">Comment : écrire une extension pour le ServiceContractGenerator</span><span class="sxs-lookup"><span data-stu-id="66b96-102">How to: Write an Extension for the ServiceContractGenerator</span></span>
<span data-ttu-id="66b96-103">Cette rubrique décrit comment écrire une extension pour le <xref:System.ServiceModel.Description.ServiceContractGenerator>.</span><span class="sxs-lookup"><span data-stu-id="66b96-103">This topic describes how to write an extension for the <xref:System.ServiceModel.Description.ServiceContractGenerator>.</span></span> <span data-ttu-id="66b96-104">Cela peut être fait en implémentant l'interface <xref:System.ServiceModel.Description.IOperationContractGenerationExtension> sur un comportement d'opération ou en implémentant l'interface <xref:System.ServiceModel.Description.IServiceContractGenerationExtension> sur un comportement de contrat.</span><span class="sxs-lookup"><span data-stu-id="66b96-104">This can be done by implementing the <xref:System.ServiceModel.Description.IOperationContractGenerationExtension> interface on an operation behavior or implementing the <xref:System.ServiceModel.Description.IServiceContractGenerationExtension> interface on a contract behavior.</span></span> <span data-ttu-id="66b96-105">Cette rubrique indique comment implémenter l'interface <xref:System.ServiceModel.Description.IServiceContractGenerationExtension> sur un comportement du contrat.</span><span class="sxs-lookup"><span data-stu-id="66b96-105">This topic shows how to implement the <xref:System.ServiceModel.Description.IServiceContractGenerationExtension> interface on a contract behavior.</span></span>  
  
 <span data-ttu-id="66b96-106">Le <xref:System.ServiceModel.Description.ServiceContractGenerator> génère des contrats de service, des types de clients et des configurations clientes à partir d'instances <xref:System.ServiceModel.Description.ServiceEndpoint>, <xref:System.ServiceModel.Description.ContractDescription> et <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="66b96-106">The <xref:System.ServiceModel.Description.ServiceContractGenerator> generates service contracts, client types, and client configurations from <xref:System.ServiceModel.Description.ServiceEndpoint>, <xref:System.ServiceModel.Description.ContractDescription>, and <xref:System.ServiceModel.Channels.Binding> instances.</span></span> <span data-ttu-id="66b96-107">En général, vous importez des instances <xref:System.ServiceModel.Description.ServiceEndpoint>, <xref:System.ServiceModel.Description.ContractDescription> et <xref:System.ServiceModel.Channels.Binding> à partir de métadonnées de service, puis vous utilisez ces instances pour générer du code pour appeler le service.</span><span class="sxs-lookup"><span data-stu-id="66b96-107">Typically, you import <xref:System.ServiceModel.Description.ServiceEndpoint>, <xref:System.ServiceModel.Description.ContractDescription>, and <xref:System.ServiceModel.Channels.Binding> instances from service metadata and then use these instances to generate code to call the service.</span></span> <span data-ttu-id="66b96-108">Dans cet exemple, une implémentation <xref:System.ServiceModel.Description.IWsdlImportExtension> est utilisée pour traiter les annotations WSDL puis ajouter des extensions de génération de code aux contrats importés afin de produire des commentaires sur le code généré.</span><span class="sxs-lookup"><span data-stu-id="66b96-108">In this example, an <xref:System.ServiceModel.Description.IWsdlImportExtension> implementation is used to process WSDL annotations and then add code generation extensions to the imported contracts to generate comments on the generated code.</span></span>  
  
### <a name="to-write-an-extension-for-the-servicecontractgenerator"></a><span data-ttu-id="66b96-109">Pour écrire une extension pour le ServiceContractGenerator</span><span class="sxs-lookup"><span data-stu-id="66b96-109">To write an extension for the ServiceContractGenerator</span></span>  
  
1.  <span data-ttu-id="66b96-110">Implémentez <xref:System.ServiceModel.Description.IServiceContractGenerationExtension>.</span><span class="sxs-lookup"><span data-stu-id="66b96-110">Implement <xref:System.ServiceModel.Description.IServiceContractGenerationExtension>.</span></span> <span data-ttu-id="66b96-111">Pour modifier le contrat de service généré, utilisez l'instance <xref:System.ServiceModel.Description.ServiceContractGenerationContext> passée dans la méthode <xref:System.ServiceModel.Description.IServiceContractGenerationExtension.GenerateContract%28System.ServiceModel.Description.ServiceContractGenerationContext%29>.</span><span class="sxs-lookup"><span data-stu-id="66b96-111">To modify the generated service contract, use the <xref:System.ServiceModel.Description.ServiceContractGenerationContext> instance passed into the <xref:System.ServiceModel.Description.IServiceContractGenerationExtension.GenerateContract%28System.ServiceModel.Description.ServiceContractGenerationContext%29> method.</span></span>  
  
    ```  
    public void GenerateContract(ServiceContractGenerationContext context)  
    {  
        Console.WriteLine("In generate contract.");  
    context.ContractType.Comments.AddRange(Formatter.FormatComments(commentText));  
    }  
    ```  
  
2.  <span data-ttu-id="66b96-112">Implémentez <xref:System.ServiceModel.Description.IWsdlImportExtension> sur la même classe.</span><span class="sxs-lookup"><span data-stu-id="66b96-112">Implement <xref:System.ServiceModel.Description.IWsdlImportExtension> on the same class.</span></span> <span data-ttu-id="66b96-113">La méthode <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> peut traiter une extension WSDL spécifique (annotations WSDL dans ce cas) en ajoutant une extension de génération de code à l'instance <xref:System.ServiceModel.Description.ContractDescription> importée.</span><span class="sxs-lookup"><span data-stu-id="66b96-113">The <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> method can process a specific WSDL extension (WSDL annotations in this case) by adding a code generation extension to the imported <xref:System.ServiceModel.Description.ContractDescription> instance.</span></span>  
  
    ```  
    public void ImportContract(WsdlImporter importer, WsdlContractConversionContext context)  
       {  
                // Contract documentation  
             if (context.WsdlPortType.Documentation != null)  
             {  
                    context.Contract.Behaviors.Add(new WsdlDocumentationImporter(context.WsdlPortType.Documentation));  
             }  
             // Operation documentation  
             foreach (Operation operation in context.WsdlPortType.Operations)  
             {  
                if (operation.Documentation != null)  
                {  
                   OperationDescription operationDescription = context.Contract.Operations.Find(operation.Name);  
                   if (operationDescription != null)  
                   {  
                            operationDescription.Behaviors.Add(new WsdlDocumentationImporter(operation.Documentation));  
                   }  
                }  
             }  
          }  
          public void BeforeImport(ServiceDescriptionCollection wsdlDocuments, XmlSchemaSet xmlSchemas, ICollection<XmlElement> policy)   
            {  
                Console.WriteLine("BeforeImport called.");  
            }  
  
          public void ImportEndpoint(WsdlImporter importer, WsdlEndpointConversionContext context)   
            {  
                Console.WriteLine("ImportEndpoint called.");  
            }  
    ```  
  
3.  <span data-ttu-id="66b96-114">Ajoutez l'importateur WSDL à votre configuration cliente :</span><span class="sxs-lookup"><span data-stu-id="66b96-114">Add the WSDL importer to your client configuration.</span></span>  
  
    ```xml  
    <metadata>  
      <wsdlImporters>  
        <extension type="Microsoft.WCF.Documentation.WsdlDocumentationImporter, WsdlDocumentation" />  
      </wsdlImporters>  
    </metadata>  
    ```  
  
4.  <span data-ttu-id="66b96-115">Dans le code client, créez un `MetadataExchangeClient` et appelez `GetMetadata`.</span><span class="sxs-lookup"><span data-stu-id="66b96-115">In the client code, create a `MetadataExchangeClient` and call `GetMetadata`.</span></span>  
  
    ```  
    MetadataExchangeClient mexClient = new MetadataExchangeClient(metadataAddress);  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet metaDocs = mexClient.GetMetadata();  
    ```  
  
5.  <span data-ttu-id="66b96-116">Créez un `WsdlImporter` et appelez `ImportAllContracts`.</span><span class="sxs-lookup"><span data-stu-id="66b96-116">Create a `WsdlImporter` and call `ImportAllContracts`.</span></span>  
  
    ```  
    WsdlImporter importer = new WsdlImporter(metaDocs);            System.Collections.ObjectModel.Collection<ContractDescription> contracts = importer.ImportAllContracts();  
    ```  
  
6.  <span data-ttu-id="66b96-117">Créez un `ServiceContractGenerator` et appelez `GenerateServiceContractType` pour chaque contrat.</span><span class="sxs-lookup"><span data-stu-id="66b96-117">Create a `ServiceContractGenerator` and call `GenerateServiceContractType` for each contract.</span></span>  
  
    ```  
    ServiceContractGenerator generator = new ServiceContractGenerator();  
    foreach (ContractDescription contract in contracts)  
    {  
       generator.GenerateServiceContractType(contract);  
    }  
    if (generator.Errors.Count != 0)  
       throw new Exception("There were errors during code compilation.");  
    ```  
  
7.  <span data-ttu-id="66b96-118"><xref:System.ServiceModel.Description.IServiceContractGenerationExtension.GenerateContract%28System.ServiceModel.Description.ServiceContractGenerationContext%29> est appelée automatiquement pour chaque comportement de contrat sur un contrat donné qui implémente <xref:System.ServiceModel.Description.IServiceContractGenerationExtension>.</span><span class="sxs-lookup"><span data-stu-id="66b96-118"><xref:System.ServiceModel.Description.IServiceContractGenerationExtension.GenerateContract%28System.ServiceModel.Description.ServiceContractGenerationContext%29> is called automatically for each contract behavior on a given contract that implements <xref:System.ServiceModel.Description.IServiceContractGenerationExtension>.</span></span> <span data-ttu-id="66b96-119">Cette méthode peut ensuite modifier le <xref:System.ServiceModel.Description.ServiceContractGenerationContext> passé.</span><span class="sxs-lookup"><span data-stu-id="66b96-119">This method can then modify the <xref:System.ServiceModel.Description.ServiceContractGenerationContext> passed in.</span></span> <span data-ttu-id="66b96-120">Dans cet exemple les commentaires sont ajoutés.</span><span class="sxs-lookup"><span data-stu-id="66b96-120">In this example comments are added.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66b96-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="66b96-121">See Also</span></span>  
 [<span data-ttu-id="66b96-122">Métadonnées</span><span class="sxs-lookup"><span data-stu-id="66b96-122">Metadata</span></span>](../../../../docs/framework/wcf/feature-details/metadata.md)  
 [<span data-ttu-id="66b96-123">Guide pratique pour importer un WSDL personnalisé</span><span class="sxs-lookup"><span data-stu-id="66b96-123">How to: Import Custom WSDL</span></span>](../../../../docs/framework/wcf/extending/how-to-import-custom-wsdl.md)

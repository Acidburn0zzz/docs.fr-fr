---
title: 'Comment : instancier un objet TimeZoneInfo'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- instantiating time zone objects
- time zone objects [.NET Framework], instantiation
ms.assetid: 8cb620e5-c6a6-4267-a52e-beeb73cd1a34
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e15e7f8968d7edf87ae3cd709d8fb26a2f49826a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-instantiate-a-timezoneinfo-object"></a>Comment : instancier un objet TimeZoneInfo

La façon la plus courante pour instancier un objet <xref:System.TimeZoneInfo> consiste à récupérer les informations le concernant à partir du registre. Cette rubrique explique comment instancier un objet <xref:System.TimeZoneInfo> à partir du registre système local.

### <a name="to-instantiate-a-timezoneinfo-object"></a>Pour instancier un objet TimeZoneInfo

1. Déclarez un objet <xref:System.TimeZoneInfo> .

2. Appelez le `static` (`Shared` en Visual Basic) <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A?displayProperty=nameWithType> (méthode).

3. Gérez toutes les exceptions levées par la méthode, en particulier l’exception <xref:System.TimeZoneNotFoundException> qui est levée si le fuseau horaire n’est pas défini dans le registre.

## <a name="example"></a>Exemple

Le code suivant récupère un objet <xref:System.TimeZoneInfo> qui représente le fuseau horaire EST et affiche l’heure EST qui correspond à l’heure locale.

[!code-csharp[System.TimeZone2.Concepts#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#5)]
[!code-vb[System.TimeZone2.Concepts#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#5)]

Le <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A?displayProperty=nameWithType> paramètre unique de la méthode est l’identificateur du fuseau horaire que vous souhaitez récupérer, qui correspond à l’objet <xref:System.TimeZoneInfo.Id%2A?displayProperty=nameWithType> propriété. L'identificateur de fuseau horaire est un champ clé qui identifie le fuseau horaire de manière unique. Alors que la plupart des clés sont relativement courtes, l'identificateur de fuseau horaire est long. Dans la plupart des cas, sa valeur correspond à la propriété <xref:System.TimeZoneInfo.StandardName%2A> d’un objet <xref:System.TimeZoneInfo> , qui est utilisée pour fournir le nom de l’heure standard du fuseau horaire. Toutefois, il existe des exceptions. Pour vous assurer que l’identificateur fourni est valide, il est recommandé d’énumérer les fuseaux horaires disponibles sur votre système et de noter les identificateurs associés. Pour voir un exemple, consultez [How to: Enumerate time zones present on a computer](../../../docs/standard/datetime/enumerate-time-zones.md). La rubrique [Finding the time zones defined on a local system](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md) contient également une liste d’identificateurs de fuseau horaire sélectionnés.

Si le fuseau horaire est trouvé, la méthode renvoie son objet <xref:System.TimeZoneInfo> . Si le fuseau horaire n’est pas trouvé, la méthode lève une exception <xref:System.TimeZoneNotFoundException>. Si le fuseau horaire est trouvé, mais que ses données sont endommagées ou incomplètes, la méthode lève une exception <xref:System.InvalidTimeZoneException>.

Si votre application repose sur un fuseau horaire qui doit être présent, vous devez d’abord appeler la méthode <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> pour récupérer les informations de fuseau horaire à partir du registre. Si l’appel de méthode échoue, votre gestionnaire d’exceptions doit alors créer une nouvelle instance du fuseau horaire ou le recréer en désérialisant un objet <xref:System.TimeZoneInfo> sérialisé. Consultez [Comment : restaurer des fuseaux horaires dans une ressource incorporée](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md) pour obtenir un exemple.

## <a name="see-also"></a>Voir aussi

[Dates, heures et fuseaux horaires](../../../docs/standard/datetime/index.md)
[recherche des fuseaux horaires définis sur un système local](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
[Comment : accéder aux objets de zone prédéfinis UTC et l’heure locale](../../../docs/standard/datetime/access-utc-and-local.md)

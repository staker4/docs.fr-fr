---
title: dataContractSerializer
ms.date: 03/30/2017
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
ms.openlocfilehash: 933d49092c392fa293468d546e521bf7ed858376
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54539842"
---
# <a name="datacontractserializer"></a>dataContractSerializer
Contient les données de configuration correspondant au <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<endpointBehaviors>  
\<behavior>  
\<dataContractSerializer>  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a>Attributs et éléments  
 Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.  
  
### <a name="attributes"></a>Attributs  
  
|Élément|Description|  
|-------------|-----------------|  
|ignoreExtensionDataObject|Valeur booléenne qui spécifie si les données fournies par le point de terminaison doivent être ignorées lorsqu'il est sérialisé ou désérialisé.|  
|maxItemsInObjectGraph|Entier indiquant le nombre maximal d'éléments à sérialiser ou à désérialiser.|  
  
### <a name="child-elements"></a>Éléments enfants  
 Aucun.  
  
### <a name="parent-elements"></a>Éléments parents  
  
|Élément|Description|  
|-------------|-----------------|  
|[\<behavior>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Spécifie un comportement de point de terminaison.|  
  
## <a name="remarks"></a>Notes  
 Pour plus d'informations les types connus, consultez la documentation <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
> [!CAUTION]
>  L'élément de comportement (si présent) `<dataContractSerializer>` doit toujours apparaître avant l'élément de comportement `<enableWebScript>` dans le fichier de configuration. Sinon, le comportement résultant n'est pas défini.  
  
## <a name="see-also"></a>Voir aussi
- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [Types connus de contrats de données](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [Transfert de données et sérialisation](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)

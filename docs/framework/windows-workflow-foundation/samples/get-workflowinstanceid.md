---
title: Obtenir WorkflowInstanceId
ms.date: 03/30/2017
ms.assetid: bd7eea3b-1c28-4b84-9a67-003bc553aa81
ms.openlocfilehash: 6725ed92bf785e5b7f7d61332944fcce8427388a
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2018
ms.locfileid: "47112255"
---
# <a name="get-workflowinstanceid"></a>Obtenir WorkflowInstanceId
Cet exemple montre comment utiliser l'activité personnalisée `GetWorkflowInstanceId` pour retourner l'ID d'instance de workflow.  
  
## <a name="demonstrates"></a>Démonstrations  
 Développement de l'activité personnalisée, comment accéder à l'instance de workflow.  
  
## <a name="discussion"></a>Discussion  
 L'obtention de l'ID d'instance d'un workflow en cours d'exécution requiert l'écriture de code. Si vous souhaitez écrire un workflow complètement déclaratif, vous avez besoin d'une activité qui puisse retourner l'ID d'instance de workflow afin que l'activité puisse être référencée dans le workflow pour fournir une expérience de création de workflow complètement déclaratif. De nombreux scénarios requièrent l'accès à l'ID d'instance, par exemple à des fins d'enregistrement ou d'audit, ou pour exécuter une corrélation au niveau de l'application en retournant l'ID d'instance à un client pour une future association (par exemple, en utilisant cette activité à l'intérieur d'une activité SendReply).  
  
 `GetWorkflowInstanceId` est implémenté comme un <xref:System.Activities.CodeActivity%601> parce qu'il doit retourner une valeur de type <xref:System.Guid>, et il doit avoir accès au <xref:System.Activities.CodeActivityContext> pour l'obtention de l'ID d'instance du workflow. Son implémentation est assez basique.  
  
```  
public sealed class GetWorkflowInstanceId : CodeActivity<Guid>  
{  
protected override Guid Execute(CodeActivityContext context)  
        {  
            return context.WorkflowInstanceId;  
        }  
}  
```  
  
> [!IMPORTANT]
>  Les exemples peuvent déjà être installés sur votre ordinateur. Recherchez le répertoire (par défaut) suivant avant de continuer.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si ce répertoire n’existe pas, accédez à [Windows Communication Foundation (WCF) et des exemples de Windows Workflow Foundation (WF) pour .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) pour télécharger tous les Windows Communication Foundation (WCF) et [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemples. Cet exemple se trouve dans le répertoire suivant.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\GetWorkflowInstanceId`

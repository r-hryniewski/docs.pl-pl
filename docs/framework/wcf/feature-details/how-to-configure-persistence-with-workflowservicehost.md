---
title: 'Porady: Konfigurowanie trwałości za pomocą elementu WorkflowServiceHost'
ms.date: 03/30/2017
ms.assetid: e31cd4df-13a3-4a9a-9be8-5243e0055356
ms.openlocfilehash: 628a6b57b2d356aadadd96ebec312ef979aca6df
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/04/2018
ms.locfileid: "43501632"
---
# <a name="how-to-configure-persistence-with-workflowservicehost"></a>Porady: Konfigurowanie trwałości za pomocą elementu WorkflowServiceHost
W tym temacie opisano sposób konfigurowania funkcji Store wystąpienia przepływu pracy SQL, aby włączyć opcję trwałości dla przepływów pracy hostowanych w <xref:System.ServiceModel.Activities.WorkflowServiceHost> przy użyciu pliku konfiguracji. Przed użyciem funkcji Store wystąpienia przepływu pracy SQL należy utworzyć bazę danych SQL jest używany, aby utrwalić wystąpienia przepływu pracy. Aby uzyskać więcej informacji, zobacz [porady: Włączanie stanów trwałych programu SQL dla przepływów pracy i usług przepływu pracy](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).  
  
### <a name="to-configure-the-sql-workflow-instance-store-in-configuration"></a>Aby skonfigurować Store wystąpienia przepływu pracy SQL w konfiguracji  
  
1.  Właściwości magazynu wystąpień przepływu pracy SQL można skonfigurować za pomocą <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, zachowanie usługi, które umożliwia zmianę ustawień konfiguracji XML. W poniższym przykładzie konfiguracji pokazuje, jak skonfigurować Magazyn wystąpień przepływu pracy SQL za pomocą <`sqlWorkflowInstanceStore`> zachowania elementu w pliku konfiguracji.  
  
    ```xml  
    <serviceBehaviors>  
        <behavior name="">  
            <sqlWorkflowInstanceStore   
                 connectionString="provider=System.Data.SqlClient;Data Source=(local);Initial Catalog=DefaultPersistenceProviderDb;Integrated Security=True;Async=true"  
                 instanceEncodingOption="GZip | None"  
                 instanceCompletionAction="DeleteAll | DeleteNothing"  
                 instanceLockedExceptionAction="NoRetry | SimpleRetry | AggressiveRetry"  
                 hostLockRenewalPeriod="00:00:30"   
                 runnableInstancesDetectionPeriod="00:00:05">  
            <sqlWorkflowInstanceStore/>  
        </behavior>  
    </serviceBehaviors>  
    ```  
  
     Aby uzyskać więcej informacji na temat konfigurowania magazynu wystąpień przepływu pracy SQL, zobacz [porady: Włączanie stanów trwałych programu SQL dla przepływów pracy i usług przepływu pracy](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md). Aby uzyskać więcej informacji na temat poszczególnych ustawień dla <`sqlWorkflowInstanceStore`> element zachowania, zobacz [Store wystąpienia przepływu pracy SQL](../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md). AppFabric w systemie Windows Server udostępnia własny magazyn trwałości. Aby uzyskać więcej informacji, zobacz [systemu Windows Server App Fabric trwałości](https://go.microsoft.com/fwlink/?LinkId=193121).  
  
    > [!NOTE]
    >  W poprzednim przykładzie konfiguracja użyto uproszczona konfiguracja. Aby uzyskać więcej informacji, zobacz [uproszczona konfiguracja](../../../../docs/framework/wcf/simplified-configuration.md)  
  
### <a name="to-configure-the-sql-workflow-instance-store-in-code"></a>Aby skonfigurować Store wystąpienia przepływu pracy SQL w kodzie  
  
1.  Właściwości magazynu wystąpień przepływu pracy SQL można skonfigurować za pomocą <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, zachowanie usługi, które umożliwia zmianę ustawień za pomocą kodu. Poniższy przykład pokazuje, jak skonfigurować Magazyn wystąpień przepływu pracy SQL przy użyciu <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> zachowania elementu w kodzie  
  
    ```csharp  
    host.Description.Behaviors.Add(new SqlWorkflowInstanceStoreBehavior  
    {  
       ConnectionString = "provider=System.Data.SqlClient;Data Source=(local);Initial Catalog=DefaultPersistenceProviderDb;Integrated Security=True;Async=true",  
       InstanceEncodingOption = "GZip | None",  
       InstanceCompletionAction = "DeleteAll | DeleteNothing",  
       InstanceLockedExceptionAction = "NoRetry | SimpleRetry | AggressiveRetry",  
       HostLockRenewalPeriod = new TimeSpan(00, 00, 30),  
       RunnableInstancesDetectionPeriod = new TimeSpan(00, 00, 05)  
    });  
    ```  
  
     Aby uzyskać więcej informacji na temat konfigurowania magazynu wystąpień przepływu pracy SQL, zobacz [porady: Włączanie stanów trwałych programu SQL dla przepływów pracy i usług przepływu pracy](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md). Aby uzyskać więcej informacji na temat poszczególnych ustawień <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> zachowanie elementu, zobacz [Store wystąpienia przepływu pracy SQL](../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md). AppFabric w systemie Windows Server udostępnia własny magazyn trwałości. Aby uzyskać więcej informacji, zobacz [systemu Windows Server App Fabric trwałości](https://go.microsoft.com/fwlink/?LinkId=193121).  
  
    > [!NOTE]
    >  W poprzednim przykładzie konfiguracja użyto uproszczona konfiguracja. Aby uzyskać więcej informacji, zobacz [uproszczona konfiguracja](../../../../docs/framework/wcf/simplified-configuration.md)  
  
     Przykład sposobu konfigurowania trwałości programowo zobacz [porady: Włączanie stanów trwałych dla przepływów pracy i usług przepływu pracy](../../../../docs/framework/windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md).  
  
## <a name="see-also"></a>Zobacz też  
 [Usługi przepływu pracy](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [Trwałość przepływu pracy](../../../../docs/framework/windows-workflow-foundation/workflow-persistence.md)  
 [Windows Server AppFabric trwałości](https://go.microsoft.com/fwlink/?LinkId=193121)

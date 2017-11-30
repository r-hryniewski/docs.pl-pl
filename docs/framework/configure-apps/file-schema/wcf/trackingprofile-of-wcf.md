---
title: '&lt;trackingProfile&gt; w WCF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 09b651c2-c0d2-4850-a101-b0e009a1dc3a
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a4c317a4fcf4efb2f1b8210faa768cc290a784c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="lttrackingprofilegt-of-wcf"></a><span data-ttu-id="003e4-102">&lt;trackingProfile&gt; w WCF</span><span class="sxs-lookup"><span data-stu-id="003e4-102">&lt;trackingProfile&gt; of WCF</span></span>
<span data-ttu-id="003e4-103">Reprezentuje sekcję konfiguracji do tworzenia subskrypcji do śledzenia rekordów w uczestnika śledzenia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="003e4-103">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="003e4-104">Profil śledzenia zawiera śledzenia zapytań, pozwalające uczestnikiem śledzenia do subskrybowania zdarzenia przepływu pracy, które są emitowane po zmianie stanu wystąpienia przepływu pracy w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="003e4-104">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="003e4-105">Kwerendy zdefiniowane w profilu śledzenia sekcji zdefiniować rodzaje zdarzenia, które są zwracane w subskrypcji.</span><span class="sxs-lookup"><span data-stu-id="003e4-105">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>  
  
 <span data-ttu-id="003e4-106">Aby uzyskać więcej informacji w śledzenia przepływu pracy i jego konfiguracja, zobacz [przepływu pracy śledzenia i śledzenia](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) i [śledzenia profile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="003e4-106">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="003e4-107">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="003e4-107">\<system.serviceModel></span></span>  
<span data-ttu-id="003e4-108">\<Śledzenie ></span><span class="sxs-lookup"><span data-stu-id="003e4-108">\<tracking></span></span>  
<span data-ttu-id="003e4-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="003e4-109">\<trackingProfile></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="003e4-110">Składnia</span><span class="sxs-lookup"><span data-stu-id="003e4-110">Syntax</span></span>  
  
```xml
   <system.serviceModel>  <tracking>      <trackingProfile name="String">      <workflow activityDefinitionId="String">          <activityScheduledQueries>             <activityScheduledQuery activityName="String"                 childActivityName="String"/>          </activityScheduledQueries>             <activityStateQuery activityName="String" />                <arguments>                   <argument name="String"/>                </arguments>                <states>                   <state name="String"/>                </states>                <variables>                   <variable name="String"/>                </variables>          </activityStateQueries>          <bookmarkResumptionQueries>             <bookmarkResumptionQuery name="String" />          </bookmarkResumptionQueries>          <cancelRequestQueries>             <cancelRequestQuery activityName="String"                 childActivityName="String"/>          </cancelRequestQueries>          <customTrackingQueries>             <customTrackingQuery activityName="String"                 name="String"/>          </customTrackingQueries>          <faultPropagationQueries>             <faultPropagationQuery activityName="String"                 faultHandlerActivityName="String"/>          </faultPropagationQueries>         <workflowInstanceQueries>            <workflowInstanceQuery>              <states>                 <state name="String"/>              </states>          </workflowInstanceQuery>        </workflowInstanceQueries>      </workflow>    </trackingProfile>           </profiles>  </tracking></system.serviceModel>    
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="003e4-111">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="003e4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="003e4-112">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="003e4-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="003e4-113">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="003e4-113">Attributes</span></span>  
  
|<span data-ttu-id="003e4-114">Atrybut</span><span class="sxs-lookup"><span data-stu-id="003e4-114">Attribute</span></span>|<span data-ttu-id="003e4-115">Opis</span><span class="sxs-lookup"><span data-stu-id="003e4-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="003e4-116">nazwa</span><span class="sxs-lookup"><span data-stu-id="003e4-116">name</span></span>|<span data-ttu-id="003e4-117">Ciąg określający nazwę profilu śledzenia.</span><span class="sxs-lookup"><span data-stu-id="003e4-117">A string that specifies the name of the tracking profile.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="003e4-118">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="003e4-118">Child Elements</span></span>  
  
|<span data-ttu-id="003e4-119">Element</span><span class="sxs-lookup"><span data-stu-id="003e4-119">Element</span></span>|<span data-ttu-id="003e4-120">Opis</span><span class="sxs-lookup"><span data-stu-id="003e4-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="003e4-121">\<Uczestnicy ></span><span class="sxs-lookup"><span data-stu-id="003e4-121">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)|<span data-ttu-id="003e4-122">Element konfiguracji, który zawiera wszystkie zapytania dla określonego przepływu pracy identyfikowane przez `a HYPERLINK "http://msdn.microsoft.com/en-us/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx" ctivityDefinitionId` właściwości.</span><span class="sxs-lookup"><span data-stu-id="003e4-122">A configuration element that contains all queries for a specific workflow identified by the `a HYPERLINK "http://msdn.microsoft.com/en-us/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx" ctivityDefinitionId` property.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="003e4-123">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="003e4-123">Parent Elements</span></span>  
  
|<span data-ttu-id="003e4-124">Element</span><span class="sxs-lookup"><span data-stu-id="003e4-124">Element</span></span>|<span data-ttu-id="003e4-125">Opis</span><span class="sxs-lookup"><span data-stu-id="003e4-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="003e4-126">\<Śledzenie ></span><span class="sxs-lookup"><span data-stu-id="003e4-126">\<tracking></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/tracking.md)|<span data-ttu-id="003e4-127">Reprezentuje sekcję konfiguracji do definiowania ustawień śledzenia dla usługi przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="003e4-127">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="003e4-128">Uwagi</span><span class="sxs-lookup"><span data-stu-id="003e4-128">Remarks</span></span>  
 <span data-ttu-id="003e4-129">Śledzenie profile zawiera śledzenia zapytań, pozwalające uczestnikiem śledzenia do subskrybowania zdarzenia przepływu pracy, które są emitowane po zmianie stanu wystąpienia przepływu pracy w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="003e4-129">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="003e4-130">W zależności od potrzeb może zapisu profil przybliżonego, które subskrybuje niewielkiego zestawu zmian stanu wysokiego poziomu przepływ pracy.</span><span class="sxs-lookup"><span data-stu-id="003e4-130">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="003e4-131">Z drugiej strony można utworzyć bardzo określony profil którego wynikowego zdarzenia są rozbudowanych, odtworzenie przepływ wykonania szczegółowe później.</span><span class="sxs-lookup"><span data-stu-id="003e4-131">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="003e4-132">Profile śledzenia mają strukturę jako deklaratywne subskrypcji dla śledzenia rekordy, które umożliwiają zapytania dla rekordów śledzenie wersję wykonawczą przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="003e4-132">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="003e4-133">Istnieje kilka typów zapytania, które zezwala na subskrybować różnych klas HYPERLINK "http://msdn.microsoft.com/en-us/library/system.activities.tracking.trackingrecord (VS.100).aspx" TrackingRecord obiektów.</span><span class="sxs-lookup"><span data-stu-id="003e4-133">There are a handful of query types that allow you subscribe to different classes of  HYPERLINK "http://msdn.microsoft.com/en-us/library/system.activities.tracking.trackingrecord(VS.100).aspx" TrackingRecord objects.</span></span> <span data-ttu-id="003e4-134">Aby uzyskać pełną listę zapytań, zobacz [ \<uczestników >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md) i [śledzenia profile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)...</span><span class="sxs-lookup"><span data-stu-id="003e4-134">For a complete list of queries, see [\<participants>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md) and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)..</span></span>  
  
 <span data-ttu-id="003e4-135">W poniższym przykładzie przedstawiono profilu śledzenia w pliku konfiguracji, który umożliwia śledzenie uczestnika do subskrybowania `Started` i `Completed` zdarzeń przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="003e4-135">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
```xml  
<system.serviceModel>  
  <tracking>    
    <trackingProfile name="Sample Tracking Profile">  
      <workflow activityDefinitionId="*">  
         <workflowInstanceQueries>  
            <workflowInstanceQuery>  
            <states>  
              <state name="Started"/>  
              <state name="Completed"/>  
            </states>  
          </workflowInstanceQuery>  
        </workflowInstanceQueries>  
      </workflow>  
    </trackingProfile>          
   </profiles>  
  </tracking>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="003e4-136">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="003e4-136">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileElement>  
 <xref:System.Activities.Tracking.TrackingProfile>  
 [<span data-ttu-id="003e4-137">Przepływ pracy, kontrola i śledzenie</span><span class="sxs-lookup"><span data-stu-id="003e4-137">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="003e4-138">Profile śledzenia</span><span class="sxs-lookup"><span data-stu-id="003e4-138">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
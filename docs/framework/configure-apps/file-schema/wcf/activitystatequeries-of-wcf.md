---
title: '&lt;activityStateQueries&gt; w WCF'
ms.date: 10/08/2018
ms.assetid: 9e45db49-ed85-4fdf-bd65-0d5477e31823
ms.openlocfilehash: 081dc297912ed5735dd51111936b85b61f463d2d
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49123244"
---
# <a name="ltactivitystatequeriesgt-of-wcf"></a>&lt;activityStateQueries&gt; w WCF

Reprezentuje kolekcję zapytań, które są używane do śledzenia zmian cyklem życia działań, które tworzą wystąpienie przepływu pracy. Na przykład chcesz do śledzenia za każdym razem, gdy kończy działanie "Wyślij wiadomość E-Mail", w ramach wystąpienie przepływu pracy. To zapytanie jest niezbędne do śledzenia uczestnika do subskrybowania obiektów rekordu stanu działania. Stany do subskrybowania są wyszczególnione w ActivityStates.

Aby uzyskać więcej informacji na podstawie śledzenia zapytań profilu zobacz [profile śledzenia](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).

\<system.serviceModel>  
\<Śledzenie >  
\<profile >  
\<trackingProfile>  
\<przepływ pracy >  
\<activityStateQueries >  

## <a name="syntax"></a>Składnia  
  
```xml
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityStateQueries>
          <activityStateQuery activityName="String">
            <arguments>
              <argument name="String"/>
            </arguments>
            <states>
              <state name="String"/>
            </states>
            <variables>
              <variable name="String"/>
            </variables>
          </activityStateQuery>
        </activityStateQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  

## <a name="attributes-and-elements"></a>Atrybuty i elementy

W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.
  
### <a name="attributes"></a>Atrybuty  

Brak.  

### <a name="child-elements"></a>Elementy podrzędne

|Element|Opis|
|-------------|-----------------|
|[\<activityStateQuery >](activitystatequery-of-wcf.md)|Zapytanie, które jest używane do śledzenia obsługi błędów występujących w ramach działania.  To zdarzenie występuje, każdym razem FaultHandler przetwarza błąd wystąpienia.|

### <a name="parent-elements"></a>Elementy nadrzędne

|Element|Opis|
|-------------|-----------------|
|[\<przepływ pracy >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|Element konfiguracji, który zawiera wszystkie zapytania dla określonego przepływu pracy identyfikowane przez `activityDefinitionId` właściwości.|

## <a name="see-also"></a>Zobacz także

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection>    
- <xref:System.Activities.Tracking.ActivityStateQuery>    
- [Kontrola i śledzenie przepływu pracy](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
- [Profile śledzenia](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

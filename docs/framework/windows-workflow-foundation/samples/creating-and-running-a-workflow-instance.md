---
title: "Tworzenie i uruchamianie wystąpienia przepływu pracy"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19d27f47-0491-4569-8f53-51bc1d940e80
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d53becfc126f1acee4759ddff956b4435c9aa769
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="creating-and-running-a-workflow-instance"></a><span data-ttu-id="5bf8b-102">Tworzenie i uruchamianie wystąpienia przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="5bf8b-102">Creating and Running a Workflow Instance</span></span>
<span data-ttu-id="5bf8b-103">Ten przykład przedstawia sposób uruchomienia wystąpienia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="5bf8b-103">This sample shows how to run a workflow instance.</span></span> <span data-ttu-id="5bf8b-104">Widoczny jest sposób ją wykonać synchronicznego i asynchronicznego.</span><span class="sxs-lookup"><span data-stu-id="5bf8b-104">It shows how to execute it synchronously and asynchronously.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="5bf8b-105">Demonstracje</span><span class="sxs-lookup"><span data-stu-id="5bf8b-105">Demonstrates</span></span>  
 <span data-ttu-id="5bf8b-106"><xref:System.Activities.WorkflowInvoker>, <xref:System.Activities.WorkflowApplication>.</span><span class="sxs-lookup"><span data-stu-id="5bf8b-106"><xref:System.Activities.WorkflowInvoker>, <xref:System.Activities.WorkflowApplication>.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="5bf8b-107">Omówienie</span><span class="sxs-lookup"><span data-stu-id="5bf8b-107">Discussion</span></span>  
 <span data-ttu-id="5bf8b-108">Pierwsza część próbki używa <xref:System.Activities.WorkflowInvoker.Invoke%2A>.</span><span class="sxs-lookup"><span data-stu-id="5bf8b-108">The first part of the sample uses <xref:System.Activities.WorkflowInvoker.Invoke%2A>.</span></span> <span data-ttu-id="5bf8b-109">Jest to najbardziej podstawową metodą wykonania przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="5bf8b-109">This is the most basic way to execute a workflow.</span></span> <span data-ttu-id="5bf8b-110">Przepływy pracy wykonywane przy <xref:System.Activities.WorkflowInvoker.Invoke%2A> są wykonywane synchronicznie.</span><span class="sxs-lookup"><span data-stu-id="5bf8b-110">Workflows executed with <xref:System.Activities.WorkflowInvoker.Invoke%2A> are executed synchronously.</span></span>  
  
 <span data-ttu-id="5bf8b-111">Druga część próbki używa <xref:System.Activities.WorkflowApplication> klasy.</span><span class="sxs-lookup"><span data-stu-id="5bf8b-111">The second part of the sample uses the <xref:System.Activities.WorkflowApplication> class.</span></span> <span data-ttu-id="5bf8b-112"><xref:System.Activities.WorkflowApplication>pozwala na większą kontrolę nad każde wystąpienie, w tym możliwość interakcji z uruchomionym przepływem pracy i Uruchom przepływ pracy asynchronicznie.</span><span class="sxs-lookup"><span data-stu-id="5bf8b-112"><xref:System.Activities.WorkflowApplication> enables you to have more control over each instance, including the ability to interact with the running workflow and to run the workflow asynchronously.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5bf8b-113">Próbki mogą być zainstalowane na tym komputerze.</span><span class="sxs-lookup"><span data-stu-id="5bf8b-113">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5bf8b-114">Przed kontynuowaniem sprawdź, czy są dostępne dla następującego katalogu (ustawienie domyślne).</span><span class="sxs-lookup"><span data-stu-id="5bf8b-114">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5bf8b-115">Jeśli ten katalog nie istnieje, przejdź do [Windows Communication Foundation (WCF) i Windows Workflow Foundation (WF) przykłady dla programu .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) pobrać wszystkie [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] próbek.</span><span class="sxs-lookup"><span data-stu-id="5bf8b-115">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5bf8b-116">W tym przykładzie znajduje się w następującym katalogu.</span><span class="sxs-lookup"><span data-stu-id="5bf8b-116">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\CreatingWorkflowInstances`  
  
## <a name="see-also"></a><span data-ttu-id="5bf8b-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5bf8b-117">See Also</span></span>  
 [<span data-ttu-id="5bf8b-118">Przy użyciu WorkflowInvoker i działanie obiektu WorkflowApplication</span><span class="sxs-lookup"><span data-stu-id="5bf8b-118">Using WorkflowInvoker and WorkflowApplication</span></span>](../../../../docs/framework/windows-workflow-foundation/using-workflowinvoker-and-workflowapplication.md)
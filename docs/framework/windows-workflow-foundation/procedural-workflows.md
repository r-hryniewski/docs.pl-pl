---
title: "Procedurach przepływów pracy"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52401de9-9115-472d-8fd9-047af6a072b9
caps.latest.revision: "17"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9e8f517b68695457c2819612bbd092b5ea03c5f5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="procedural-workflows"></a><span data-ttu-id="49310-102">Procedurach przepływów pracy</span><span class="sxs-lookup"><span data-stu-id="49310-102">Procedural Workflows</span></span>
<span data-ttu-id="49310-103">Procedurach przepływów pracy za pomocą metod sterowanie przepływem podobne do tych w procedurach języków.</span><span class="sxs-lookup"><span data-stu-id="49310-103">Procedural workflows use flow-control methods similar to those found in procedural languages.</span></span> <span data-ttu-id="49310-104">Konstrukcje te obejmują `While` i `If`.</span><span class="sxs-lookup"><span data-stu-id="49310-104">These constructs include `While` and `If`.</span></span> <span data-ttu-id="49310-105">Te przepływy pracy mogą być za darmo składane, takich jak przy użyciu innych działań kontroli przepływu <xref:System.Activities.Statements.Flowchart> i <xref:System.Activities.Statements.Sequence>.</span><span class="sxs-lookup"><span data-stu-id="49310-105">These workflows can be freely composed using other flow control activities such as <xref:System.Activities.Statements.Flowchart> and <xref:System.Activities.Statements.Sequence>.</span></span>  
  
## <a name="controlling-execution-flow"></a><span data-ttu-id="49310-106">Sterowanie przepływem wykonywania</span><span class="sxs-lookup"><span data-stu-id="49310-106">Controlling Execution Flow</span></span>  
 <span data-ttu-id="49310-107">Biblioteka działań przepływu pracy ma działania dla większości metod sterowanie przepływem używana w procedurach języków modelowania.</span><span class="sxs-lookup"><span data-stu-id="49310-107">The workflow activity library has activities for modeling most flow-control methods used in procedural languages.</span></span> <span data-ttu-id="49310-108">Należą do nich następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="49310-108">These include:</span></span>  
  
-   <xref:System.Activities.Statements.While>  
  
-   <xref:System.Activities.Statements.DoWhile>  
  
-   <xref:System.Activities.Statements.ForEach%601>  
  
-   <xref:System.Activities.Statements.Parallel>  
  
-   <xref:System.Activities.Statements.ParallelForEach%601>  
  
-   <xref:System.Activities.Statements.If>  
  
-   <xref:System.Activities.Statements.Switch%601>  
  
-   <xref:System.Activities.Statements.Pick>  
  
 <span data-ttu-id="49310-109">Aby użyć działania przepływu sterowania, przeciągnij i upuść je z **działania** przybornika do działania złożonego wewnątrz okna projektanta.</span><span class="sxs-lookup"><span data-stu-id="49310-109">To use flow control activities, drag and drop them from the **Activity** toolbox into a composite activity inside the designer window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="49310-110">Jeśli przy użyciu [!INCLUDE[dublin](../../../includes/dublin-md.md)] do przepływów pracy hosta na farmie sieci Web AppFabric przeniesie wystąpień między różnymi serwerami AppFabric.</span><span class="sxs-lookup"><span data-stu-id="49310-110">If using the [!INCLUDE[dublin](../../../includes/dublin-md.md)] to host workflows on a Web farm, AppFabric will move instances between different AppFabric servers.</span></span> <span data-ttu-id="49310-111">Wymaga to, że zasoby mogą być współużytkowane przez wszystkie węzły.</span><span class="sxs-lookup"><span data-stu-id="49310-111">This requires that the resources are able to be shared between all nodes.</span></span>  <span data-ttu-id="49310-112">Żaden z domyślnych działań przepływu pracy NET 4 nie zawiera żadnych operacji, które uzyskują dostęp do zasobów lokalnych.</span><span class="sxs-lookup"><span data-stu-id="49310-112">None of the default NET 4 workflow activities contain any operations that access local resources.</span></span> <span data-ttu-id="49310-113">Ponieważ AppFabric nie oferuje dowolny mechanizm można oznaczyć jako nieruchomości przepływu pracy, Projektant nie należy utworzyć niestandardowych działań, które się nie powieść, gdy przepływ pracy zostanie przesunięty.</span><span class="sxs-lookup"><span data-stu-id="49310-113">Since AppFabric does not offer any mechanism to mark a workflow as immovable, a developer must not create custom activities that fail when a workflow is moved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49310-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="49310-114">See Also</span></span>  
 [<span data-ttu-id="49310-115">Schemat blokowy przepływów pracy</span><span class="sxs-lookup"><span data-stu-id="49310-115">Flowchart Workflows</span></span>](../../../docs/framework/windows-workflow-foundation/flowchart-workflows.md)
---
title: 'Porady: pobieranie informacji konflikt jednostki'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 9a02b608-e7bb-4041-a452-a7fed26fd008
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 26f3ec3736b04eeffc1cd741e2c06a39ef7f1a0d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-retrieve-entity-conflict-information"></a><span data-ttu-id="628a0-102">Porady: pobieranie informacji konflikt jednostki</span><span class="sxs-lookup"><span data-stu-id="628a0-102">How to: Retrieve Entity Conflict Information</span></span>
<span data-ttu-id="628a0-103">Można użyć obiektów <xref:System.Data.Linq.ObjectChangeConflict> klasę, aby podać informacje o konfliktach ujawniony przez <xref:System.Data.Linq.ChangeConflictException> wyjątków.</span><span class="sxs-lookup"><span data-stu-id="628a0-103">You can use objects of the <xref:System.Data.Linq.ObjectChangeConflict> class to provide information about conflicts revealed by <xref:System.Data.Linq.ChangeConflictException> exceptions.</span></span> <span data-ttu-id="628a0-104">Aby uzyskać więcej informacji, zobacz [optymistycznej współbieżności: omówienie](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="628a0-104">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="628a0-105">Przykład</span><span class="sxs-lookup"><span data-stu-id="628a0-105">Example</span></span>  
 <span data-ttu-id="628a0-106">Poniższy przykład iterację listę wszystkich konfliktów.</span><span class="sxs-lookup"><span data-stu-id="628a0-106">The following example iterates through a list of accumulated conflicts.</span></span>  
  
 [!code-csharp[System.Data.Linq.ObjectChangeConflict#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.objectchangeconflict/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.ObjectChangeConflict#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.objectchangeconflict/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="628a0-107">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="628a0-107">See Also</span></span>  
 [<span data-ttu-id="628a0-108">Porady: Zarządzanie konfliktów zmian</span><span class="sxs-lookup"><span data-stu-id="628a0-108">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
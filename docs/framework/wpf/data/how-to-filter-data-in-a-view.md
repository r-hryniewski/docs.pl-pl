---
title: "Jak filtrować dane w widoku"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- views [WPF], filtering data
- filtering data in views [WPF]
- data binding [WPF], filtering data in views
ms.assetid: c76e8606-4cc4-45a8-9110-e2ec66dc6afd
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: de51aa83af71027ce86909a15f3ceee58fb47814
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-filter-data-in-a-view"></a><span data-ttu-id="ef9c7-102">Jak filtrować dane w widoku</span><span class="sxs-lookup"><span data-stu-id="ef9c7-102">How to: Filter Data in a View</span></span>
<span data-ttu-id="ef9c7-103">Ten przykład przedstawia sposób filtrowania danych widoku.</span><span class="sxs-lookup"><span data-stu-id="ef9c7-103">This example shows how to filter data in a view.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef9c7-104">Przykład</span><span class="sxs-lookup"><span data-stu-id="ef9c7-104">Example</span></span>  
 <span data-ttu-id="ef9c7-105">Aby utworzyć filtr, zdefiniuj metodę, która zawiera logikę filtrowania.</span><span class="sxs-lookup"><span data-stu-id="ef9c7-105">To create a filter, define a method that provides the filtering logic.</span></span> <span data-ttu-id="ef9c7-106">Metoda jest używana jako wywołania zwrotnego i przyjmuje parametr typu `object`.</span><span class="sxs-lookup"><span data-stu-id="ef9c7-106">The method is used as a callback and accepts a parameter of type `object`.</span></span> <span data-ttu-id="ef9c7-107">Następująca metoda zwraca wszystkie `Order` obiekty z `filled` właściwością "No" filtrowanie pozostałe obiekty.</span><span class="sxs-lookup"><span data-stu-id="ef9c7-107">The following method returns all the `Order` objects with the `filled` property set to "No", filtering out the rest of the objects.</span></span>  
  
 [!code-csharp[SortFilter#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#2)]
 [!code-vb[SortFilter#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#2)]  
  
 <span data-ttu-id="ef9c7-108">Można użyć filtru, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="ef9c7-108">You can then apply the filter, as shown in the following example.</span></span> <span data-ttu-id="ef9c7-109">W tym przykładzie `myCollectionView` jest <xref:System.Windows.Data.ListCollectionView> obiektu.</span><span class="sxs-lookup"><span data-stu-id="ef9c7-109">In this example, `myCollectionView` is a <xref:System.Windows.Data.ListCollectionView> object.</span></span>  
  
 [!code-csharp[SortFilter#Filter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#filter)]
 [!code-vb[SortFilter#Filter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#filter)]  
  
 <span data-ttu-id="ef9c7-110">Aby cofnąć filtrowania, można ustawić <xref:System.Windows.Data.CollectionView.Filter%2A> właściwości `null`:</span><span class="sxs-lookup"><span data-stu-id="ef9c7-110">To undo filtering, you can set the <xref:System.Windows.Data.CollectionView.Filter%2A> property to `null`:</span></span>  
  
 [!code-csharp[SortFilter#Unfilter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#unfilter)]
 [!code-vb[SortFilter#Unfilter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#unfilter)]  
  
 <span data-ttu-id="ef9c7-111">Aby dowiedzieć się, jak utworzyć lub uzyskać widoku, zobacz [uzyskać widok domyślny zbierania danych](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md).</span><span class="sxs-lookup"><span data-stu-id="ef9c7-111">For information about how to create or obtain a view, see [Get the Default View of a Data Collection](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md).</span></span> <span data-ttu-id="ef9c7-112">Aby uzyskać pełny przykład, zobacz [sortowanie i filtrowanie elementów w przykładowym widoku](http://go.microsoft.com/fwlink/?LinkID=160040).</span><span class="sxs-lookup"><span data-stu-id="ef9c7-112">For the complete example, see [Sorting and Filtering Items in a View Sample](http://go.microsoft.com/fwlink/?LinkID=160040).</span></span>  
  
 <span data-ttu-id="ef9c7-113">Jeśli obiekt widoku pochodzi z <xref:System.Windows.Data.CollectionViewSource> obiekt zastosował logikę filtrowania przez ustawienie programu obsługi zdarzeń dla <xref:System.Windows.Data.CollectionViewSource.Filter> zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="ef9c7-113">If your view object comes from a <xref:System.Windows.Data.CollectionViewSource> object, you apply filtering logic by setting an event handler for the <xref:System.Windows.Data.CollectionViewSource.Filter> event.</span></span> <span data-ttu-id="ef9c7-114">W poniższym przykładzie `listingDataView` jest wystąpieniem <xref:System.Windows.Data.CollectionViewSource>.</span><span class="sxs-lookup"><span data-stu-id="ef9c7-114">In the following example, `listingDataView` is an instance of <xref:System.Windows.Data.CollectionViewSource>.</span></span>  
  
 [!code-csharp[DataBindingLab#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 <span data-ttu-id="ef9c7-115">Poniżej pokazano implementacji przykładu `ShowOnlyBargainsFilter` filtru programu obsługi zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="ef9c7-115">The following shows the implementation of the example `ShowOnlyBargainsFilter` filter event handler.</span></span> <span data-ttu-id="ef9c7-116">Ten program obsługi zdarzeń używa <xref:System.Windows.Data.FilterEventArgs.Accepted%2A> właściwość, aby odfiltrować `AuctionItem` obiektów, które mają `CurrentPrice` 25 lub większą.</span><span class="sxs-lookup"><span data-stu-id="ef9c7-116">This event handler uses the <xref:System.Windows.Data.FilterEventArgs.Accepted%2A> property to filter out `AuctionItem` objects that have a `CurrentPrice` of $25 or greater.</span></span>  
  
 [!code-csharp[DataBindingLab#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="ef9c7-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ef9c7-117">See Also</span></span>  
 <xref:System.Windows.Data.CollectionView.CanFilter%2A>  
 <xref:System.Windows.Data.BindingListCollectionView.CustomFilter%2A>  
 [<span data-ttu-id="ef9c7-118">Omówienie powiązania danych</span><span class="sxs-lookup"><span data-stu-id="ef9c7-118">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="ef9c7-119">Sortowanie danych w widoku</span><span class="sxs-lookup"><span data-stu-id="ef9c7-119">Sort Data in a View</span></span>](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)  
 [<span data-ttu-id="ef9c7-120">Tematy porad</span><span class="sxs-lookup"><span data-stu-id="ef9c7-120">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
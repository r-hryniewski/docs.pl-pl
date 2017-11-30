---
title: "Jak sklonować drukarkę"
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
- print queues [WPF]
- cloning printers [WPF]
- printers [WPF], cloning
- print queues [WPF], cloning
- cloning print queues [WPF]
ms.assetid: dd6997c9-fe04-40f8-88a6-92e3ac0889eb
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 303cb9c1c5b6521839987a56cdc008eac0559cf1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-clone-a-printer"></a><span data-ttu-id="b10e3-102">Jak sklonować drukarkę</span><span class="sxs-lookup"><span data-stu-id="b10e3-102">How to: Clone a Printer</span></span>
<span data-ttu-id="b10e3-103">Większość firm będzie w pewnym momencie zakupu wiele drukarek tego samego modelu.</span><span class="sxs-lookup"><span data-stu-id="b10e3-103">Most businesses will, at some point, buy multiple printers of the same model.</span></span> <span data-ttu-id="b10e3-104">Zazwyczaj te są wszystkie zainstalowane przy użyciu ustawień konfiguracyjnych niemal identyczne.</span><span class="sxs-lookup"><span data-stu-id="b10e3-104">Typically, these are all installed with virtually identical configuration settings.</span></span> <span data-ttu-id="b10e3-105">Instalowanie poszczególnych drukarek może być czasochłonne i podatne na błąd.</span><span class="sxs-lookup"><span data-stu-id="b10e3-105">Installing each printer can be time-consuming and error prone.</span></span> <span data-ttu-id="b10e3-106"><xref:System.Printing.IndexedProperties?displayProperty=nameWithType> Przestrzeni nazw i <xref:System.Printing.PrintServer.InstallPrintQueue%2A> klasy, które są dostępne z [!INCLUDE[TLA#tla_avalonwinfx](../../../../includes/tlasharptla-avalonwinfx-md.md)] umożliwia teraz instalować dowolną liczbę kolejek wydruku dodatkowe, które są klonowane z istniejącej kolejki wydruku.</span><span class="sxs-lookup"><span data-stu-id="b10e3-106">The <xref:System.Printing.IndexedProperties?displayProperty=nameWithType> namespace and the <xref:System.Printing.PrintServer.InstallPrintQueue%2A> class that are exposed with [!INCLUDE[TLA#tla_avalonwinfx](../../../../includes/tlasharptla-avalonwinfx-md.md)] makes it possible to instantly install any number of additional print queues that are cloned from an existing print queue.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b10e3-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="b10e3-107">Example</span></span>  
 <span data-ttu-id="b10e3-108">W poniższym przykładzie drugi kolejki wydruku został sklonowany z istniejącej kolejki wydruku.</span><span class="sxs-lookup"><span data-stu-id="b10e3-108">In the example below, a second print queue is cloned from an existing print queue.</span></span> <span data-ttu-id="b10e3-109">Drugi różni się od pierwszego tylko w jego nazwę, lokalizacji, port i stanu udostępnionego.</span><span class="sxs-lookup"><span data-stu-id="b10e3-109">The second differs from the first only in its name, location, port, and shared status.</span></span> <span data-ttu-id="b10e3-110">Oto główne kroki w ten sposób.</span><span class="sxs-lookup"><span data-stu-id="b10e3-110">The major steps for doing this are as follows.</span></span>  
  
1.  <span data-ttu-id="b10e3-111">Utwórz <xref:System.Printing.PrintQueue> obiektu dla istniejącej drukarki, która ma zostać sklonowany.</span><span class="sxs-lookup"><span data-stu-id="b10e3-111">Create a <xref:System.Printing.PrintQueue> object for the existing printer that is going to be cloned.</span></span>  
  
2.  <span data-ttu-id="b10e3-112">Utwórz <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> z <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> z <xref:System.Printing.PrintQueue>.</span><span class="sxs-lookup"><span data-stu-id="b10e3-112">Create a <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> from the <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> of the <xref:System.Printing.PrintQueue>.</span></span> <span data-ttu-id="b10e3-113"><xref:System.Collections.DictionaryEntry.Value%2A> Właściwości każdego wpisu w tym słowniku jest obiektem jednego z jego typów pochodnych <xref:System.Printing.IndexedProperties.PrintProperty>.</span><span class="sxs-lookup"><span data-stu-id="b10e3-113">The <xref:System.Collections.DictionaryEntry.Value%2A> property of each entry in this dictionary is an object of one of the types derived from <xref:System.Printing.IndexedProperties.PrintProperty>.</span></span> <span data-ttu-id="b10e3-114">Istnieją dwa sposoby ustawiania wartości wpisu w tym słowniku.</span><span class="sxs-lookup"><span data-stu-id="b10e3-114">There are two ways to set the value of an entry in this dictionary.</span></span>  
  
    -   <span data-ttu-id="b10e3-115">Użyj słownika **Usuń** i <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> metody Usuń wpis, a następnie dodaj go ponownie z żądaną wartość.</span><span class="sxs-lookup"><span data-stu-id="b10e3-115">Use the dictionary's **Remove** and <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> methods to remove the entry and then re-add it with the desired value.</span></span>  
  
    -   <span data-ttu-id="b10e3-116">Użyj słownika <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="b10e3-116">Use the dictionary's <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A> method.</span></span>  
  
     <span data-ttu-id="b10e3-117">W poniższym przykładzie przedstawiono w obu kierunkach.</span><span class="sxs-lookup"><span data-stu-id="b10e3-117">The example below illustrates both ways.</span></span>  
  
3.  <span data-ttu-id="b10e3-118">Utwórz <xref:System.Printing.IndexedProperties.PrintBooleanProperty> obiektu i ustawić jej <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> do "IsShared" i jego <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> do `true`.</span><span class="sxs-lookup"><span data-stu-id="b10e3-118">Create a <xref:System.Printing.IndexedProperties.PrintBooleanProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "IsShared" and its <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> to `true`.</span></span>  
  
4.  <span data-ttu-id="b10e3-119">Użyj <xref:System.Printing.IndexedProperties.PrintBooleanProperty> była wartość <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>dla wpisu "IsShared".</span><span class="sxs-lookup"><span data-stu-id="b10e3-119">Use the <xref:System.Printing.IndexedProperties.PrintBooleanProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "IsShared" entry.</span></span>  
  
5.  <span data-ttu-id="b10e3-120">Utwórz <xref:System.Printing.IndexedProperties.PrintStringProperty> obiektu i ustawić jej <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> do "ShareName" i jego <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> do odpowiedniej <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="b10e3-120">Create a <xref:System.Printing.IndexedProperties.PrintStringProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "ShareName" and its <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> to an appropriate <xref:System.String>.</span></span>  
  
6.  <span data-ttu-id="b10e3-121">Użyj <xref:System.Printing.IndexedProperties.PrintStringProperty> była wartość <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>jego wpis "ShareName".</span><span class="sxs-lookup"><span data-stu-id="b10e3-121">Use the <xref:System.Printing.IndexedProperties.PrintStringProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "ShareName" entry.</span></span>  
  
7.  <span data-ttu-id="b10e3-122">Utworzyć inną <xref:System.Printing.IndexedProperties.PrintStringProperty> obiektu i ustawić jej <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> do "Lokalizacja" i jego <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> do odpowiedniej <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="b10e3-122">Create another <xref:System.Printing.IndexedProperties.PrintStringProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "Location" and its <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> to an appropriate <xref:System.String>.</span></span>  
  
8.  <span data-ttu-id="b10e3-123">Użyj drugi <xref:System.Printing.IndexedProperties.PrintStringProperty> była wartość <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>jego wpis "Lokalizacja".</span><span class="sxs-lookup"><span data-stu-id="b10e3-123">Use the second <xref:System.Printing.IndexedProperties.PrintStringProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "Location" entry.</span></span>  
  
9. <span data-ttu-id="b10e3-124">Utwórz tablicę <xref:System.String>s.</span><span class="sxs-lookup"><span data-stu-id="b10e3-124">Create an array of <xref:System.String>s.</span></span> <span data-ttu-id="b10e3-125">Każdy element jest to nazwa portu na serwerze.</span><span class="sxs-lookup"><span data-stu-id="b10e3-125">Each item is the name of a port on the server.</span></span>  
  
10. <span data-ttu-id="b10e3-126">Użyj <xref:System.Printing.PrintServer.InstallPrintQueue%2A> do zainstalowania nowej drukarki przy użyciu nowych wartości.</span><span class="sxs-lookup"><span data-stu-id="b10e3-126">Use <xref:System.Printing.PrintServer.InstallPrintQueue%2A> to install the new printer with the new values.</span></span>  
  
 <span data-ttu-id="b10e3-127">Przykładem jest poniżej.</span><span class="sxs-lookup"><span data-stu-id="b10e3-127">An example is below.</span></span>  
  
 [!code-csharp[ClonePrinter#ClonePrinter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClonePrinter/CSharp/Program.cs#cloneprinter)]
 [!code-vb[ClonePrinter#ClonePrinter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClonePrinter/visualbasic/program.vb#cloneprinter)]  
  
## <a name="see-also"></a><span data-ttu-id="b10e3-128">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b10e3-128">See Also</span></span>  
 <xref:System.Printing.IndexedProperties>  
 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>  
 <xref:System.Printing.LocalPrintServer>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Collections.DictionaryEntry>  
 [<span data-ttu-id="b10e3-129">Dokumentów na platformie WPF</span><span class="sxs-lookup"><span data-stu-id="b10e3-129">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="b10e3-130">Omówienie drukowania</span><span class="sxs-lookup"><span data-stu-id="b10e3-130">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)
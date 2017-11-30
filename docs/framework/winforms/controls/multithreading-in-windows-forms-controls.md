---
title: "Wielowątkowość w formantach formularzy systemu Windows"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c4651ca9707dcf0fac2edea0f004275cfcf18cf2
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/22/2017
---
# <a name="multithreading-in-windows-forms-controls"></a><span data-ttu-id="a8626-102">Wielowątkowość w formantach formularzy systemu Windows</span><span class="sxs-lookup"><span data-stu-id="a8626-102">Multithreading in Windows Forms Controls</span></span>
<span data-ttu-id="a8626-103">W wielu aplikacjach możesz wprowadzić interfejsu użytkownika (UI) poprawę reakcji, wykonując czas operacji w innym wątku.</span><span class="sxs-lookup"><span data-stu-id="a8626-103">In many applications, you can make your user interface (UI) more responsive by performing time-consuming operations on another thread.</span></span> <span data-ttu-id="a8626-104">Wiele narzędzi dostępnych dla wielowątkowości formantów formularzy systemu Windows, w tym <xref:System.Threading> przestrzeni nazw, <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> metody i `BackgroundWorker` składnika.</span><span class="sxs-lookup"><span data-stu-id="a8626-104">A number of tools are available for multithreading your Windows Forms controls, including the <xref:System.Threading> namespace, the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method, and the `BackgroundWorker` component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8626-105">`BackgroundWorker` Składnika zastępuje i dodaje funkcje do <xref:System.Threading> przestrzeni nazw i <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> metody, jednak te pozostają dla zgodności z poprzednimi wersjami i użycia w przyszłości, jeśli zostanie wybrana.</span><span class="sxs-lookup"><span data-stu-id="a8626-105">The `BackgroundWorker` component replaces and adds functionality to the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method; however, these are retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="a8626-106">Aby uzyskać więcej informacji, zobacz [BackgroundWorker — informacje o składniku](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a8626-106">For more information, see [BackgroundWorker Component Overview](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a8626-107">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="a8626-107">In This Section</span></span>  
 [<span data-ttu-id="a8626-108">Porady: wykonywać bezpieczne wątkowo wywołania formantów formularzy systemu Windows</span><span class="sxs-lookup"><span data-stu-id="a8626-108">How to: Make Thread-Safe Calls to Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 <span data-ttu-id="a8626-109">Pokazuje, jak nawiązać bezpieczne wątkowo wywołania formantów formularzy systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="a8626-109">Shows how to make thread-safe calls to Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="a8626-110">Porady: użycie wątku w tle do wyszukiwania plików</span><span class="sxs-lookup"><span data-stu-id="a8626-110">How to: Use a Background Thread to Search for Files</span></span>](../../../../docs/framework/winforms/controls/how-to-use-a-background-thread-to-search-for-files.md)  
 <span data-ttu-id="a8626-111">Przedstawia sposób użycia <xref:System.Threading> przestrzeni nazw i <xref:System.Windows.Forms.Control.BeginInvoke%2A> metody do wyszukiwania plików asynchronicznie.</span><span class="sxs-lookup"><span data-stu-id="a8626-111">Shows how to use the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A> method to search for files asynchronously.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="a8626-112">Tematy pomocy</span><span class="sxs-lookup"><span data-stu-id="a8626-112">Reference</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="a8626-113">Dokumenty składnik, który hermetyzuje wątku roboczego dla operacji asynchronicznych.</span><span class="sxs-lookup"><span data-stu-id="a8626-113">Documents a component that encapsulates a worker thread for asynchronous operations.</span></span>  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 <span data-ttu-id="a8626-114">Dokumenty jak ładowanie dźwięku asynchronicznie.</span><span class="sxs-lookup"><span data-stu-id="a8626-114">Documents how to load a sound asynchronously.</span></span>  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 <span data-ttu-id="a8626-115">Omówiono sposób asynchronicznie ładowania obrazu.</span><span class="sxs-lookup"><span data-stu-id="a8626-115">Documents how to load an image asynchronously.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a8626-116">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="a8626-116">Related Sections</span></span>  
 [<span data-ttu-id="a8626-117">Porady: uruchamianie operacji w tle</span><span class="sxs-lookup"><span data-stu-id="a8626-117">How to: Run an Operation in the Background</span></span>](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 <span data-ttu-id="a8626-118">Pokazuje, jak wykonać czasochłonna operacja z <xref:System.ComponentModel.BackgroundWorker> składnika.</span><span class="sxs-lookup"><span data-stu-id="a8626-118">Shows how to perform a time-consuming operation with the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
 [<span data-ttu-id="a8626-119">Omówienie BackgroundWorker — składnik</span><span class="sxs-lookup"><span data-stu-id="a8626-119">BackgroundWorker Component Overview</span></span>](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md)  
 <span data-ttu-id="a8626-120">Udostępnia tematy, które opisują sposób użycia <xref:System.ComponentModel.BackgroundWorker> składnika dla operacji asynchronicznych.</span><span class="sxs-lookup"><span data-stu-id="a8626-120">Provides topics that describe how to use the <xref:System.ComponentModel.BackgroundWorker> component for asynchronous operations.</span></span>
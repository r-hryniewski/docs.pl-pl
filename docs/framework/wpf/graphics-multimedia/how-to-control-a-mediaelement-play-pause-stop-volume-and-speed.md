---
title: "Jak kontrolować MediaElement (odtwórz, pauza, zatrzymaj, głośność i prędkość)"
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
- playback of media [WPF], controlling
- controlling playback of media [WPF]
- multimedia [WPF], controlling playback of media
- media [WPF], controlling playback of
ms.assetid: 6885a730-e054-4c16-8c1e-ffe17b1f7c32
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7362c57afa3d5615ffaa0616823a954a2d577cfe
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-control-a-mediaelement-play-pause-stop-volume-and-speed"></a><span data-ttu-id="11340-102">Jak kontrolować MediaElement (odtwórz, pauza, zatrzymaj, głośność i prędkość)</span><span class="sxs-lookup"><span data-stu-id="11340-102">How to: Control a MediaElement (Play, Pause, Stop, Volume, and Speed)</span></span>
<span data-ttu-id="11340-103">Poniższy przykład przedstawia sposób odtwarzaniem nośnika przy użyciu <xref:System.Windows.Controls.MediaElement>.</span><span class="sxs-lookup"><span data-stu-id="11340-103">The following example shows how to control playback of media using a <xref:System.Windows.Controls.MediaElement>.</span></span> <span data-ttu-id="11340-104">W przykładzie jest tworzony proste media player, który służy do odtwarzania, wstrzymać, zatrzymać i pominąć i z powrotem na nośniku, a także dopasować stosunek wolumin i szybkości.</span><span class="sxs-lookup"><span data-stu-id="11340-104">The example creates a simple media player that allows you to play, pause, stop, and skip back and forth in the media as well as adjust the volume and speed ratio.</span></span>  
  
## <a name="example"></a><span data-ttu-id="11340-105">Przykład</span><span class="sxs-lookup"><span data-stu-id="11340-105">Example</span></span>  
 <span data-ttu-id="11340-106">Poniższy kod tworzy interfejsu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="11340-106">The code below creates the UI.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="11340-107"><xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> Właściwość <xref:System.Windows.Controls.MediaElement> musi mieć ustawioną `Manual` aby można było interaktywnie zatrzymać, wstrzymywanie i odtwarzanie multimediów.</span><span class="sxs-lookup"><span data-stu-id="11340-107">The <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> property of <xref:System.Windows.Controls.MediaElement> must be set to `Manual` in order to be able to interactively stop, pause, and play the media.</span></span>  
  
 [!code-xaml[MediaGallery_snip#MediaElementExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="11340-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="11340-108">Example</span></span>  
 <span data-ttu-id="11340-109">Poniższy kod implementuje funkcje próbka formantów interfejsu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="11340-109">The code below implements the functionality of the sample UI controls.</span></span> <span data-ttu-id="11340-110"><xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, I <xref:System.Windows.Controls.MediaElement.Stop%2A> metody są używane do odpowiednio odtwarzania, wstrzymywanie i zatrzymywanie nośnika.</span><span class="sxs-lookup"><span data-stu-id="11340-110">The <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, and <xref:System.Windows.Controls.MediaElement.Stop%2A> methods are used to respectively play, pause and stop the media.</span></span> <span data-ttu-id="11340-111">Zmiana <xref:System.Windows.Controls.MediaElement.Position%2A> właściwość <xref:System.Windows.Controls.MediaElement> pozwala na pominięcie na nośniku.</span><span class="sxs-lookup"><span data-stu-id="11340-111">Changing the <xref:System.Windows.Controls.MediaElement.Position%2A> property of the <xref:System.Windows.Controls.MediaElement> allows you to skip around in the media.</span></span> <span data-ttu-id="11340-112">Na koniec <xref:System.Windows.Controls.MediaElement.Volume%2A> i <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> właściwości są używane do dostosowywania woluminu i odtwarzania szybkość nośnika.</span><span class="sxs-lookup"><span data-stu-id="11340-112">Finally, the <xref:System.Windows.Controls.MediaElement.Volume%2A> and <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> properties are used to adjust the volume and playback speed of the media.</span></span>  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="11340-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="11340-113">See Also</span></span>  
 [<span data-ttu-id="11340-114">Kontrolowanie MediaElement przy użyciu scenorysu</span><span class="sxs-lookup"><span data-stu-id="11340-114">Control a MediaElement by Using a Storyboard</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-by-using-a-storyboard.md)
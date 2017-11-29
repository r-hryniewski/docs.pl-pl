---
title: "Rozszerz szklaną klatkę na aplikację WPF"
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
- applications [WPF], extending glass frames into
- graphics [WPF], extending glass frames into applications
- extending glass frames into applications [WPF]
- glass frames [WPF], extending into applications
ms.assetid: 74388a3a-4b69-4a9d-ba1f-e107636bd660
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d943d0b91d6f740144399d758a5ed80460f0eb6d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="extend-glass-frame-into-a-wpf-application"></a><span data-ttu-id="f04d8-102">Rozszerz szklaną klatkę na aplikację WPF</span><span class="sxs-lookup"><span data-stu-id="f04d8-102">Extend Glass Frame Into a WPF Application</span></span>
<span data-ttu-id="f04d8-103">W tym temacie przedstawiono sposób rozszerzyć [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)] szkła ramki do obszaru klienckiego [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] aplikacji.</span><span class="sxs-lookup"><span data-stu-id="f04d8-103">This topic demonstrates how to extend the [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)] glass frame into the client area of a [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f04d8-104">W tym przykładzie będzie działać tylko na [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] maszyny z systemem Menedżera okien pulpitu (DWM) z szkła włączone.</span><span class="sxs-lookup"><span data-stu-id="f04d8-104">This example will only work on a [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] machine running the Desktop Window Manager (DWM) with glass enabled.</span></span> [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)]<span data-ttu-id="f04d8-105">Home edition podstawowa nie obsługuje efekt szkła przezroczysty.</span><span class="sxs-lookup"><span data-stu-id="f04d8-105"> Home Basic edition does not support the transparent glass effect.</span></span> <span data-ttu-id="f04d8-106">Obszary, które zwykle pozbawia efekt szkła przezroczysty na inne wersje [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] są renderowane przezroczystości.</span><span class="sxs-lookup"><span data-stu-id="f04d8-106">Areas that would typically render with the transparent glass effect on other editions of [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] are rendered opaque.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f04d8-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="f04d8-107">Example</span></span>  
 <span data-ttu-id="f04d8-108">Na poniższym obrazie przedstawiono szkła ramki rozszerzony do adresu pasek programu Internet Explorer 7.</span><span class="sxs-lookup"><span data-stu-id="f04d8-108">The following image illustrates the glass frame extended into the address bar of Internet Explorer 7.</span></span>  
  
 <span data-ttu-id="f04d8-109">**Program Internet Explorer z rozszerzonego szkła ramki za paska adresu.**</span><span class="sxs-lookup"><span data-stu-id="f04d8-109">**Internet Explorer with extended glass frame behind address bar.**</span></span>  
  
 <span data-ttu-id="f04d8-110">![IE7 szkła ramki rozszerzony poza pasek adresu. ] (../../../../docs/framework/wpf/graphics-multimedia/media/ie7glasstopbar.PNG "IE7glasstopbar")</span><span class="sxs-lookup"><span data-stu-id="f04d8-110">![IE7 with glass frame extended behind address bar.](../../../../docs/framework/wpf/graphics-multimedia/media/ie7glasstopbar.PNG "IE7glasstopbar")</span></span>  
  
 <span data-ttu-id="f04d8-111">Aby rozszerzyć szkła ramki na [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aplikacji, dostęp do niezarządzanego [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] jest wymagana.</span><span class="sxs-lookup"><span data-stu-id="f04d8-111">To extend the glass frame on a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application, access to unmanaged [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] is needed.</span></span> <span data-ttu-id="f04d8-112">Poniższy przykładowy kod jest wywołanie platformy (pinvoke) dla dwóch [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] spełnić w celu rozszerzenia ramki do obszaru klienckiego.</span><span class="sxs-lookup"><span data-stu-id="f04d8-112">The following code example does a Platform Invoke (pinvoke) for the two [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] needed to extend the frame into the client area.</span></span> <span data-ttu-id="f04d8-113">Każdy z tych [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] został zadeklarowany w klasie o nazwie **NonClientRegionAPI**.</span><span class="sxs-lookup"><span data-stu-id="f04d8-113">Each of these [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] are declared in a class called **NonClientRegionAPI**.</span></span>  
  
```csharp  
[StructLayout(LayoutKind.Sequential)]  
public struct MARGINS  
{  
    public int cxLeftWidth;      // width of left border that retains its size  
    public int cxRightWidth;     // width of right border that retains its size  
    public int cyTopHeight;      // height of top border that retains its size  
    public int cyBottomHeight;   // height of bottom border that retains its size  
};  
  
[DllImport("DwmApi.dll")]  
public static extern int DwmExtendFrameIntoClientArea(  
    IntPtr hwnd,  
    ref MARGINS pMarInset);  
```  
  
```vb  
<StructLayout(LayoutKind.Sequential)>  
        Public Structure MARGINS  
            Public cxLeftWidth As Integer ' width of left border that retains its size  
            Public cxRightWidth As Integer ' width of right border that retains its size  
            Public cyTopHeight As Integer ' height of top border that retains its size  
            Public cyBottomHeight As Integer ' height of bottom border that retains its size  
        End Structure  
  
        <DllImport("DwmApi.dll")>  
        Public Shared Function DwmExtendFrameIntoClientArea(ByVal hwnd As IntPtr, ByRef pMarInset As MARGINS) As Integer  
        End Function  
```  
  
 <span data-ttu-id="f04d8-114">[DwmExtendFrameIntoClientArea](https://msdn.microsoft.com/library/aa969512.aspx) jest funkcja Menedżera okien pulpitu, rozszerzający ramki do obszaru klienckiego.</span><span class="sxs-lookup"><span data-stu-id="f04d8-114">[DwmExtendFrameIntoClientArea](https://msdn.microsoft.com/library/aa969512.aspx) is the DWM function that extends the frame into the client area.</span></span> <span data-ttu-id="f04d8-115">Trwa dwóch parametrów; uchwyt okna i [MARGINESY](https://msdn.microsoft.com/library/bb773244.aspx) struktury.</span><span class="sxs-lookup"><span data-stu-id="f04d8-115">It takes two parameters; a window handle and a [MARGINS](https://msdn.microsoft.com/library/bb773244.aspx) structure.</span></span> <span data-ttu-id="f04d8-116">[MARGINESY](https://msdn.microsoft.com/library/bb773244.aspx) informuje Menedżera okien pulpitu, ile bardzo ramki powinien zostać rozszerzony do obszaru klienckiego.</span><span class="sxs-lookup"><span data-stu-id="f04d8-116">[MARGINS](https://msdn.microsoft.com/library/bb773244.aspx) is used to tell the DWM how much extra the frame should be extended into the client area.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f04d8-117">Przykład</span><span class="sxs-lookup"><span data-stu-id="f04d8-117">Example</span></span>  
 <span data-ttu-id="f04d8-118">Aby użyć [DwmExtendFrameIntoClientArea](https://msdn.microsoft.com/library/aa969512.aspx) funkcji, należy uzyskać uchwytu okna.</span><span class="sxs-lookup"><span data-stu-id="f04d8-118">To use the [DwmExtendFrameIntoClientArea](https://msdn.microsoft.com/library/aa969512.aspx) function, a window handle must be obtained.</span></span> <span data-ttu-id="f04d8-119">W [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], można uzyskać uchwytu okna <xref:System.Windows.Interop.HwndSource.Handle%2A> właściwość <xref:System.Windows.Interop.HwndSource>.</span><span class="sxs-lookup"><span data-stu-id="f04d8-119">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], the window handle can be obtained from the <xref:System.Windows.Interop.HwndSource.Handle%2A> property of an <xref:System.Windows.Interop.HwndSource>.</span></span> <span data-ttu-id="f04d8-120">W poniższym przykładzie ramki jest rozszerzony do obszaru klienckiego na <xref:System.Windows.FrameworkElement.Loaded> zdarzenia okna.</span><span class="sxs-lookup"><span data-stu-id="f04d8-120">In the following example, the frame is extended into the client area on the <xref:System.Windows.FrameworkElement.Loaded> event of the window.</span></span>  
  
```csharp  
void OnLoaded(object sender, RoutedEventArgs e)  
{  
   try  
   {  
      // Obtain the window handle for WPF application  
      IntPtr mainWindowPtr = new WindowInteropHelper(this).Handle;  
      HwndSource mainWindowSrc = HwndSource.FromHwnd(mainWindowPtr);  
      mainWindowSrc.CompositionTarget.BackgroundColor = Color.FromArgb(0, 0, 0, 0);  
  
      // Get System Dpi  
      System.Drawing.Graphics desktop = System.Drawing.Graphics.FromHwnd(mainWindowPtr);  
      float DesktopDpiX = desktop.DpiX;  
      float DesktopDpiY = desktop.DpiY;  
  
      // Set Margins  
      NonClientRegionAPI.MARGINS margins = new NonClientRegionAPI.MARGINS();  
  
      // Extend glass frame into client area  
      // Note that the default desktop Dpi is 96dpi. The  margins are  
      // adjusted for the system Dpi.  
      margins.cxLeftWidth = Convert.ToInt32(5 * (DesktopDpiX / 96));  
      margins.cxRightWidth = Convert.ToInt32(5 * (DesktopDpiX / 96));  
      margins.cyTopHeight = Convert.ToInt32(((int)topBar.ActualHeight + 5) * (DesktopDpiX / 96));  
      margins.cyBottomHeight = Convert.ToInt32(5 * (DesktopDpiX / 96));  
  
      int hr = NonClientRegionAPI.DwmExtendFrameIntoClientArea(mainWindowSrc.Handle, ref margins);  
      //  
      if (hr < 0)  
      {  
         //DwmExtendFrameIntoClientArea Failed  
      }  
   }  
   // If not Vista, paint background white.  
   catch (DllNotFoundException)  
   {  
      Application.Current.MainWindow.Background = Brushes.White;  
   }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="f04d8-121">Przykład</span><span class="sxs-lookup"><span data-stu-id="f04d8-121">Example</span></span>  
 <span data-ttu-id="f04d8-122">W poniższym przykładzie przedstawiono prosty okna, w którym ramki jest rozszerzony do obszaru klienckiego.</span><span class="sxs-lookup"><span data-stu-id="f04d8-122">The following example shows a simple window in which the frame is extended into the client area.</span></span> <span data-ttu-id="f04d8-123">Ramki jest rozszerzona za górnej krawędzi, która zawiera dwa <xref:System.Windows.Controls.TextBox> obiektów.</span><span class="sxs-lookup"><span data-stu-id="f04d8-123">The frame is extended behind the top border that contains the two <xref:System.Windows.Controls.TextBox> objects.</span></span>  
  
```xaml  
<Window x:Class="SDKSample.Window1"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    Title="Extended Glass in WPF" Height="300" Width="400"   
    Loaded="OnLoaded" Background="Transparent"  
    >  
  <Grid ShowGridLines="True">  
    <DockPanel Name="mainDock">  
      <!-- The border is used to compute the rendered height with margins.  
           topBar contents will be displayed on the extended glass frame.-->  
      <Border Name="topBar" DockPanel.Dock="Top" >  
        <Grid Name="grid">  
          <Grid.ColumnDefinitions>  
            <ColumnDefinition MinWidth="100" Width="*"/>  
            <ColumnDefinition Width="Auto"/>  
          </Grid.ColumnDefinitions>  
          <TextBox Grid.Column="0" MinWidth="100" Margin="0,0,10,5">Path</TextBox>  
          <TextBox Grid.Column="1" MinWidth="75" Margin="0,0,0,5">Search</TextBox>  
        </Grid>  
      </Border>  
      <Grid DockPanel.Dock="Top" >  
        <Grid.ColumnDefinitions>  
          <ColumnDefinition/>  
        </Grid.ColumnDefinitions>  
        <TextBox Grid.Column="0" AcceptsReturn="True"/>  
      </Grid>  
    </DockPanel>  
  </Grid>  
</Window>  
```  
  
 <span data-ttu-id="f04d8-124">Na poniższym obrazie przedstawiono szkła ramki rozszerzone do postaci [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aplikacji.</span><span class="sxs-lookup"><span data-stu-id="f04d8-124">The following image illustrates the glass frame extended into a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application.</span></span>  
  
 <span data-ttu-id="f04d8-125">**Szkła ramki rozszerzone do postaci**[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]**aplikacji.** </span><span class="sxs-lookup"><span data-stu-id="f04d8-125">**Glass Frame Extended into a**  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]  **Application.**</span></span>  
  
 <span data-ttu-id="f04d8-126">![Szkła ramki rozszerzonych w aplikacji WPF. ] (../../../../docs/framework/wpf/graphics-multimedia/media/wpfextendedglassintoclient.PNG "WPFextendedGlassIntoClient")</span><span class="sxs-lookup"><span data-stu-id="f04d8-126">![Glass Frame Extended into a WPF application.](../../../../docs/framework/wpf/graphics-multimedia/media/wpfextendedglassintoclient.PNG "WPFextendedGlassIntoClient")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f04d8-127">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f04d8-127">See Also</span></span>  
 [<span data-ttu-id="f04d8-128">Omówienie Menedżera okien pulpitu</span><span class="sxs-lookup"><span data-stu-id="f04d8-128">Desktop Window Manager Overview</span></span>](https://msdn.microsoft.com/library/aa969540.aspx)  
 [<span data-ttu-id="f04d8-129">Omówienie rozmycia Menedżera okien pulpitu</span><span class="sxs-lookup"><span data-stu-id="f04d8-129">Desktop Window Manager Blur Overview</span></span>](https://msdn.microsoft.com/library/aa969537.aspx)  
 [<span data-ttu-id="f04d8-130">DwmExtendFrameIntoClientArea</span><span class="sxs-lookup"><span data-stu-id="f04d8-130">DwmExtendFrameIntoClientArea</span></span>](https://msdn.microsoft.com/library/aa969512.aspx)
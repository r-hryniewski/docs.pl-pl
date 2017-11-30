---
title: "Jak użyć przestrzeni nazw XML w powiązaniu danych"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f98d174fd0bd8ea28c7b72cec25b5b16f2b76c51
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a><span data-ttu-id="0d4ea-102">Jak użyć przestrzeni nazw XML w powiązaniu danych</span><span class="sxs-lookup"><span data-stu-id="0d4ea-102">How to: Use XML Namespaces in Data Binding</span></span>
## <a name="example"></a><span data-ttu-id="0d4ea-103">Przykład</span><span class="sxs-lookup"><span data-stu-id="0d4ea-103">Example</span></span>  
 <span data-ttu-id="0d4ea-104">W tym przykładzie pokazano, jak obsługiwać określony w przestrzeni nazw Twojej [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] źródle powiązania.</span><span class="sxs-lookup"><span data-stu-id="0d4ea-104">This example shows how to handle namespaces specified in your [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] binding source.</span></span>  
  
 <span data-ttu-id="0d4ea-105">Jeśli Twoje [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] dane mają następujące [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] definicję przestrzeni nazw:</span><span class="sxs-lookup"><span data-stu-id="0d4ea-105">If your [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data has the following [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace definition:</span></span>  
  
 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`  
  
 <span data-ttu-id="0d4ea-106">Można użyć <xref:System.Windows.Data.XmlNamespaceMapping> element do mapowania do przestrzeni nazw <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, jak w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="0d4ea-106">You can use the <xref:System.Windows.Data.XmlNamespaceMapping> element to map the namespace to a <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, as in the following example.</span></span> <span data-ttu-id="0d4ea-107">Następnie można użyć <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> do odwoływania się do [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="0d4ea-107">You can then use the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> to refer to the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace.</span></span> <span data-ttu-id="0d4ea-108"><xref:System.Windows.Controls.ListBox> w tym przykładzie wyświetlane są *tytuł* i *dc:date* każdego *elementu*.</span><span class="sxs-lookup"><span data-stu-id="0d4ea-108">The <xref:System.Windows.Controls.ListBox> in this example displays the *title* and *dc:date* of each *item*.</span></span>  
  
 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]  
  
 <span data-ttu-id="0d4ea-109">Należy pamiętać, że <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> użytkownika nie ma zgodne z działaniem używanym w [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] źródła; w przypadku zmiany prefiks w [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] źródła mapowanie nadal działa.</span><span class="sxs-lookup"><span data-stu-id="0d4ea-109">Note that the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> you specify does not have to match the one used in the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] source; if the prefix changes in the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] source your mapping still works.</span></span>  
  
 <span data-ttu-id="0d4ea-110">W tym przykładzie [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] dane pochodzą z usługi sieci web, ale <xref:System.Windows.Data.XmlNamespaceMapping> element współdziała również z wbudowanym [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] lub [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] osadzonego pliku danych.</span><span class="sxs-lookup"><span data-stu-id="0d4ea-110">In this particular example, the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data comes from a web service, but the <xref:System.Windows.Data.XmlNamespaceMapping> element also works with inline [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] or [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data in an embedded file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d4ea-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0d4ea-111">See Also</span></span>  
 [<span data-ttu-id="0d4ea-112">Powiązania danych XML przy użyciu XMLDataProvider i kwerendy XPath</span><span class="sxs-lookup"><span data-stu-id="0d4ea-112">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)  
 [<span data-ttu-id="0d4ea-113">Omówienie powiązania danych</span><span class="sxs-lookup"><span data-stu-id="0d4ea-113">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="0d4ea-114">Tematy porad</span><span class="sxs-lookup"><span data-stu-id="0d4ea-114">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
---
title: Tworzenie dostawcy automatyzacji interfejsu użytkownika po stronie klienta
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, creating client-side provider
- client-side UI Automation provider, creating
ms.assetid: d91edaf2-be28-41ec-a508-af421cb43c3d
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: 76fa74a31e7198d0f380a4db71a4789fd7b0a31a
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/26/2018
ms.locfileid: "47196112"
---
# <a name="create-a-client-side-ui-automation-provider"></a>Tworzenie dostawcy automatyzacji interfejsu użytkownika po stronie klienta
> [!NOTE]
>  Ta dokumentacja jest przeznaczona dla deweloperów .NET Framework, którzy chcą używać zarządzanych [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] klas zdefiniowanych w <xref:System.Windows.Automation> przestrzeni nazw. Aby uzyskać najnowsze informacje o [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], zobacz [Windows Automation API: automatyzacji interfejsu użytkownika](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Ten temat zawiera przykładowy kod, który pokazuje, jak do implementowania dostawcy automatyzacji interfejsu użytkownika po stronie klienta.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład kodu mogą być wbudowane w [!INCLUDE[TLA#tla_dll](../../../includes/tlasharptla-dll-md.md)] implementującej bardzo prostego dostawcy po stronie klienta dla okna konsoli. Kod nie ma wszystkie przydatne funkcje, ale jest jedynie do zademonstrowania określonych podstawowe kroki w procesie konfigurowania zestawów dostawcy, które mogą być rejestrowane przez aplikację kliencką automatyzacji interfejsu użytkownika.  
  
 [!code-csharp[UIAClientSideProvider_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/CSProviderProgram.cs#101)]
 [!code-vb[UIAClientSideProvider_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/csproviderprogram.vb#101)]  
  
## <a name="see-also"></a>Zobacz też  
 [Przegląd dostawców automatyzacji interfejsu użytkownika](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)  
 [Rejestrowanie zestawów dostawcy po stronie klienta](../../../docs/framework/ui-automation/register-a-client-side-provider-assembly.md)

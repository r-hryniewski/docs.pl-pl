---
title: '&lt;customCookieHandler&gt;'
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: 51ca91de5c77727f5f5506118461d19354f12c14
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/06/2018
ms.locfileid: "48836423"
---
# <a name="ltcustomcookiehandlergt"></a>&lt;customCookieHandler&gt;
Ustawia typ procedury obsługi niestandardowego pliku cookie. Ten element może być tylko obecne Jeśli `mode` atrybutu `<cookieHandler>` element jest "Niestandardowy". Niestandardowy typ musi pochodzić od <xref:System.IdentityModel.Services.CookieHandler> klasy.  
  
 \<system.identityModel.services >  
\<federationConfiguration >  
\<cookieHandler >  
\<customCookieHandler >  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Custom">  
      <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" >  
      </customCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|— typ|Określa typ niestandardowy, który pochodzi od klasy <xref:System.IdentityModel.Services.CookieHandler> klasy. Aby uzyskać więcej informacji o sposobie określania `type` atrybutów, zobacz [odwołań do typu niestandardowego](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).|  
  
### <a name="child-elements"></a>Elementy podrzędne  
 Brak  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<cookieHandler >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|Konfiguruje <xref:System.IdentityModel.Services.CookieHandler> , <xref:System.IdentityModel.Services.SessionAuthenticationModule> używa na odczytywanie i zapisywanie plików cookie.|  
  
## <a name="remarks"></a>Uwagi  
 Po określeniu obsługi niestandardowych plików cookie przez ustawienie `mode` atrybutu `<cookieHandler>` element na "Niestandardowe", należy określić typ obsługi niestandardowych plików cookie, umieszczając `<customCookieHandler>` elementu podrzędnego, który odwołuje się typ procedury obsługi plików cookie. Ten element nie może być określony, gdy `mode` atrybut jest ustawiony na "Fragmentaryczne" lub "Default". Programy obsługi niestandardowych plików cookie musi pochodzić od klasy <xref:System.IdentityModel.Services.CookieHandler> klasy.  
  
 `<customCookieHandler>` Element jest reprezentowany przez <xref:System.IdentityModel.Configuration.CustomTypeElement> klasy.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład umożliwia skonfigurowanie tego Zabronić używania obsługi niestandardowych plików cookie, typu `MyNamespace.MyCustomCookieHandler`.  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.IdentityModel.Services.CookieHandler>

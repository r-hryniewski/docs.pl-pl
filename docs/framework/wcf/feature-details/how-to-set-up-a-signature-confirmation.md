---
title: 'Instrukcje: Konfigurowanie potwierdzenia sygnatury'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- signature confirmation
- WCF, security
ms.assetid: 2424c137-c7c2-4aa9-8d5d-a066e12fefda
ms.openlocfilehash: d7076917e48124b2501826ecb0ac7599c663ba7f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33491992"
---
# <a name="how-to-set-up-a-signature-confirmation"></a>Instrukcje: Konfigurowanie potwierdzenia sygnatury
*Potwierdzenie podpisu* jest mechanizm inicjatora komunikat upewnić się, że odebranej odpowiedzi został wygenerowany w odpowiedzi na nadawcy oryginalnej wiadomości. Potwierdzenie podpisu jest zdefiniowany w specyfikacji WS-Security 1.1. Jeśli punkt końcowy obsługuje WS-Security 1.0, nie można użyć potwierdzenia podpisu.  
  
 Poniższe procedury Określ sposób włączania potwierdzenie podpisu przy użyciu <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>. Korzystając z tej samej procedury <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>. Procedura bazując na podstawowe kroki w [jak: utworzyć niestandardowego powiązania za pomocą elementu SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
### <a name="to-enable-signature-confirmation-in-code"></a>Aby włączyć potwierdzenia podpisu w kodzie  
  
1.  Utworzenie wystąpienia <xref:System.ServiceModel.Channels.BindingElementCollection> klasy.  
  
2.  Utwórz wystąpienie <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> klasy.  
  
3.  Ustaw <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> do `true`.  
  
4.  Dodaj element zabezpieczeń do kolekcji powiązania.  
  
5.  Tworzenie niestandardowego powiązania, jak określono w [porady: Tworzenie niestandardowego powiązania za pomocą elementu SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
### <a name="to-enable-signature-confirmation-in-configuration"></a>Aby włączyć potwierdzenia podpisu w konfiguracji  
  
1.  Dodaj `<customBinding>` elementu `<bindings>` sekcji pliku konfiguracji.  
  
2.  Dodaj `<binding>` element i ustaw nazwę atrybutu odpowiednią wartość.  
  
3.  Dodaj odpowiedni element kodowania. W poniższym przykładzie dodano `<TextMessageEncoding>` elementu.  
  
4.  Dodaj `<security>` element podrzędny i zestaw `requireSignatureConfirmation` atrybutu `true`.  
  
5.  Opcjonalna. Aby włączyć potwierdzenia podpisu podczas ładowania początkowego programu, Dodaj [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element podrzędny i zestaw `equireSignatureConfirmation` atrybutu `true`.  
  
6.  Dodaj element odpowiednie transportu. W poniższym przykładzie dodano [ \<httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md):  
  
    ```xml  
    <bindings>  
      <customBinding>  
        <binding name="SignatureConfirmationBinding">  
          <security requireSignatureConfirmation="true">  
            <secureConversationBootstrap requireSignatureConfirmation="true" />  
              </security>  
           <textMessageEncoding />  
             <httpTransport />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
## <a name="example"></a>Przykład  
 Poniższy kod tworzy wystąpienie <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> i ustawia <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> właściwości `true`. Należy pamiętać, że w tym przykładzie nie używa `<secureConversationBootstrap>` elementu w poprzednim przykładzie. W przykładzie pokazano potwierdzenia podpisu, korzystając z tokenu systemu Windows (protokołu Kerberos). W takim przypadku podpisu klienta jest zwracany w odpowiedzi wszystkie usługi i został potwierdzony przez klienta.  
  
 [!code-csharp[c_SignatureConfirmation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_signatureconfirmation/cs/source.cs#1)]
 [!code-vb[c_SignatureConfirmation#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_signatureconfirmation/vb/source.vb#1)]  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>  
 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>  
 <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>  
 [Instrukcje: tworzenie niestandardowego powiązania za pomocą elementu SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [Instrukcje: tworzenie elementu SecurityBindingElement dla określonego trybu uwierzytelniania](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)

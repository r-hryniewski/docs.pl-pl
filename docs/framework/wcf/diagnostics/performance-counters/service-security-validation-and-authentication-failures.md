---
title: 'Usługa: Błędy walidacji i uwierzytelniania'
ms.date: 03/30/2017
ms.assetid: 55c98268-b1ad-459d-851b-25ef52248187
ms.openlocfilehash: ba8da3ae6be6bd089690359f19e153da1e0b54fc
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/25/2018
ms.locfileid: "50039994"
---
# <a name="service-security-validation-and-authentication-failures"></a>Usługa: Błędy walidacji i uwierzytelniania
Nazwa licznika: błędy walidacji zabezpieczeń i uwierzytelniania  
  
## <a name="description"></a>Opis  
 Ten licznik jest zwiększany, gdy komunikat zostanie odrzucony, ze względu na problem z zabezpieczeniami nie pasuje do żadnego licznika "Zabezpieczenia połączeń nie masz praw". Takie problemy obejmują:  
  
-   Nie można odczytać tokenu klienta z komunikatu.  
  
-   Token klienta nie powiodło się uwierzytelnianie (na przykład,, nieprawidłowe hasło).  
  
-   Weryfikacja podpisu nie powiodła się (na przykład,, wiadomości zostały zmodyfikowane).  
  
-   Komunikat jest duplikatem z poprzedniej wersji, która może się zdarzyć podczas ataku powtarzania.  
  
-   Wystąpił błąd odszyfrowywania.  
  
-   Niektóre wymagane elementy (na przykład,, brak sygnatur czasowych lub zaszyfrowanych danych, blokowanie) brakuje wiadomości.  
  
-   Wystąpił błąd podczas uzgadniania TLSNEGO/SPNEGO.

---
title: 'Instrukcje: Używanie programu Svcutil.exe do pobierania dokumentów metadanych'
ms.date: 03/30/2017
ms.assetid: 15524274-3167-4627-b722-d6cedb9fa8c6
ms.openlocfilehash: 6643f0a5dba98afcef38870cf24d91e7d69a1440
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/26/2018
ms.locfileid: "47195423"
---
# <a name="how-to-use-svcutilexe-to-download-metadata-documents"></a>Instrukcje: Używanie programu Svcutil.exe do pobierania dokumentów metadanych
Umożliwia Svcutil.exe do pobierania metadanych z uruchomionymi usługami i zapisać metadane do plików lokalnych. HTTP i HTTPS URL schematów, Svcutil.exe podejmie próbę pobrania metadanych przy użyciu usługi WS-MetadataExchange i [odnajdywania usług sieci Web XML](https://go.microsoft.com/fwlink/?LinkId=94950). Dla innych schematów adresów URL Svcutil.exe używa tylko protokołu WS-MetadataExchange.  
  
 Domyślnie korzysta z powiązań zdefiniowanych w Svcutil.exe <xref:System.ServiceModel.Description.MetadataExchangeBindings> klasy. Aby skonfigurować powiązania, używany dla protokołu WS-MetadataExchange, należy zdefiniować punkt końcowy klienta w pliku konfiguracji dla Svcutil.exe (svcutil.exe.config) używa `IMetadataExchange` kontraktu i który ma taką samą nazwę jak jednolity identyfikator zasobów (URI) Schemat adresu punktu końcowego metadanych.  
  
> [!CAUTION]
> Podczas uruchamiania Svcutil.exe można pobrać metadanych dotyczących usługi, który udostępnia dwa różne usług kontraktów, każdy z nich zawiera operację o takiej samej nazwie, Svcutil.exe wyświetla komunikat o błędzie informujący o tym, "Nie można uzyskać metadanych z..." Na przykład, jeśli masz usługę, która udostępnia kontraktu usługi o nazwie `ICarService` zawierający operacją `Get(Car c)` i tej samej usłudze udostępnia kontraktu usługi o nazwie `IBookService` zawierający operacją `Get(Book b)`. Aby obejść ten problem, wykonaj jedną z następujących czynności:
>
> - Zmień nazwę jednej z operacji.
> - Ustaw <xref:System.ServiceModel.OperationContractAttribute.Name%2A> na inną nazwę.
> - Wartość jednej z operacji w przestrzeni nazw za pomocą różnych nazw <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> właściwości.
  
## <a name="to-download-metadata-using-svcutilexe"></a>Aby pobrać metadane przy użyciu Svcutil.exe  
  
1.  Znajdź narzędzia Svcutil.exe w następującej lokalizacji:  
  
     C:\Program Files\Microsoft SDKs\Windows\v1.0.\bin  
  
2.  W wierszu polecenia Uruchom narzędzie przy użyciu następującego formatu.  
  
    ```  
    svcutil.exe /t:metadata  <url>* | <epr>  
    ```  
  
     Należy określić `/t:metadata` umożliwiający pobranie metadanych. W przeciwnym razie wygenerowany kod klienta i konfiguracji.  
  
3.  <`url`> Argument określa adres URL punktu końcowego usługi, który udostępnia metadane lub dokumentu z metadanymi hostowanego w trybie online. <`epr`> Argument określa ścieżkę do pliku XML, który zawiera WS-Addressing `EndpointAddress` dla punktu końcowego usługi, która obsługuje WS-MetadataExchange.  
  
 Aby uzyskać więcej opcji dotyczących używania tego narzędzia do pobierania metadanych, zobacz [narzędzia narzędzie metadanych elementu ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
## <a name="example"></a>Przykład  
 Następujące polecenie pobiera dokumentów metadanych z uruchomioną usługę.  
  
```  
svcutil /t:metadata http://service/metadataEndpoint  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Narzędzie do obsługi metadanych elementu ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)

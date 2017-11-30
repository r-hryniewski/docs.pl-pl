---
title: 'Instrukcje: Konfigurowanie portu z certyfikatem SSL'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SSL
- WCF, security mode
- WCF, security
ms.assetid: b8abcc8e-a5f5-4317-aca5-01e3c40ab24d
caps.latest.revision: "18"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c67ed21a8e4a9170d72ce842505e7695b11c26c9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-configure-a-port-with-an-ssl-certificate"></a><span data-ttu-id="9ece7-102">Instrukcje: Konfigurowanie portu z certyfikatem SSL</span><span class="sxs-lookup"><span data-stu-id="9ece7-102">How to: Configure a Port with an SSL Certificate</span></span>
<span data-ttu-id="9ece7-103">Podczas tworzenia własnym hostowanej [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] usługi z <xref:System.ServiceModel.WSHttpBinding> zabezpieczenia transportu używa klasy, należy również skonfigurować port za pomocą certyfikatu X.509.</span><span class="sxs-lookup"><span data-stu-id="9ece7-103">When creating a self-hosted [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service with the <xref:System.ServiceModel.WSHttpBinding> class that uses transport security, you must also configure a port with an X.509 certificate.</span></span> <span data-ttu-id="9ece7-104">Jeśli nie utworzysz samodzielnie hostowana usługa, może obsługiwać usługi na Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="9ece7-104">If you are not creating a self-hosted service, you can host your service on Internet Information Services (IIS).</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="9ece7-105">[Zabezpieczenia transportu HTTP](../../../../docs/framework/wcf/feature-details/http-transport-security.md).</span><span class="sxs-lookup"><span data-stu-id="9ece7-105"> [HTTP Transport Security](../../../../docs/framework/wcf/feature-details/http-transport-security.md).</span></span>  
  
 <span data-ttu-id="9ece7-106">Aby skonfigurować port, narzędzia, których używasz zależy od systemu operacyjnego, który działa na tym komputerze.</span><span class="sxs-lookup"><span data-stu-id="9ece7-106">To configure a port, the tool you use depends on the operating system that is running on your machine.</span></span>  
  
 <span data-ttu-id="9ece7-107">Jeśli używasz [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] lub [!INCLUDE[wxp](../../../../includes/wxp-md.md)], użyj narzędzia HttpCfg.exe.</span><span class="sxs-lookup"><span data-stu-id="9ece7-107">If you are running [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use the HttpCfg.exe tool.</span></span> <span data-ttu-id="9ece7-108">Z [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] to narzędzie jest zainstalowany.</span><span class="sxs-lookup"><span data-stu-id="9ece7-108">With [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] this tool is installed.</span></span> <span data-ttu-id="9ece7-109">Z [!INCLUDE[wxp](../../../../includes/wxp-md.md)], możesz pobrać narzędzia z [narzędzia obsługi systemu Windows XP Service Pack 2](http://go.microsoft.com/fwlink/?LinkId=88606).</span><span class="sxs-lookup"><span data-stu-id="9ece7-109">With [!INCLUDE[wxp](../../../../includes/wxp-md.md)], you can download the tool at [Windows XP Service Pack 2 Support Tools](http://go.microsoft.com/fwlink/?LinkId=88606).</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="9ece7-110">[Omówienie tak](http://go.microsoft.com/fwlink/?LinkId=88605).</span><span class="sxs-lookup"><span data-stu-id="9ece7-110"> [Httpcfg Overview](http://go.microsoft.com/fwlink/?LinkId=88605).</span></span> <span data-ttu-id="9ece7-111">[Dokumentacji narzędzia obsługi systemu Windows](http://go.microsoft.com/fwlink/?LinkId=94840) opisano składnię narzędzia Httpcfg.exe.</span><span class="sxs-lookup"><span data-stu-id="9ece7-111">The [Windows Support Tools documentation](http://go.microsoft.com/fwlink/?LinkId=94840) explains the syntax for the Httpcfg.exe tool.</span></span>  
  
 <span data-ttu-id="9ece7-112">Jeśli używasz [!INCLUDE[wv](../../../../includes/wv-md.md)], użyj narzędzia Netsh.exe, która jest już zainstalowana.</span><span class="sxs-lookup"><span data-stu-id="9ece7-112">If you are running [!INCLUDE[wv](../../../../includes/wv-md.md)], use the Netsh.exe tool that is already installed.</span></span>  
  
 <span data-ttu-id="9ece7-113">W tym temacie opisano sposób wykonania kilku procedur:</span><span class="sxs-lookup"><span data-stu-id="9ece7-113">This topic describes how to accomplish several procedures:</span></span>  
  
-   <span data-ttu-id="9ece7-114">Określanie konfiguracji portu bieżącego komputera.</span><span class="sxs-lookup"><span data-stu-id="9ece7-114">Determining a computer's current port configuration.</span></span>  
  
-   <span data-ttu-id="9ece7-115">Pobieranie odcisku palca certyfikatu (niezbędne do dwóch poniższych procedur).</span><span class="sxs-lookup"><span data-stu-id="9ece7-115">Getting a certificate's thumbprint (necessary for the following two procedures).</span></span>  
  
-   <span data-ttu-id="9ece7-116">Powiązania certyfikatu SSL do konfiguracji portów.</span><span class="sxs-lookup"><span data-stu-id="9ece7-116">Binding an SSL certificate to a port configuration.</span></span>  
  
-   <span data-ttu-id="9ece7-117">Powiązania certyfikatu SSL do konfiguracji portów i pomocnicze certyfikaty klienta.</span><span class="sxs-lookup"><span data-stu-id="9ece7-117">Binding an SSL certificate to a port configuration and supporting client certificates.</span></span>  
  
-   <span data-ttu-id="9ece7-118">Usunięcie certyfikatu SSL z numeru portu.</span><span class="sxs-lookup"><span data-stu-id="9ece7-118">Deleting an SSL certificate from a port number.</span></span>  
  
 <span data-ttu-id="9ece7-119">Należy pamiętać, że zmodyfikowanie certyfikaty przechowywane na komputerze wymaga uprawnień administracyjnych.</span><span class="sxs-lookup"><span data-stu-id="9ece7-119">Note that modifying certificates stored on the computer requires administrative privileges.</span></span>  
  
### <a name="to-determine-how-ports-are-configured"></a><span data-ttu-id="9ece7-120">Aby określić, jak skonfigurować porty</span><span class="sxs-lookup"><span data-stu-id="9ece7-120">To determine how ports are configured</span></span>  
  
1.  <span data-ttu-id="9ece7-121">W [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] lub [!INCLUDE[wxp](../../../../includes/wxp-md.md)], użyj narzędzia HttpCfg.exe, aby wyświetlić bieżącą konfigurację portu, przy użyciu **zapytania** i **ssl** zmienia, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="9ece7-121">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use the HttpCfg.exe tool to view the current port configuration, using the **query** and **ssl** switches, as shown in the following example.</span></span>  
  
    ```  
    httpcfg query ssl  
    ```  
  
2.  <span data-ttu-id="9ece7-122">W [!INCLUDE[wv](../../../../includes/wv-md.md)], użyj narzędzia Netsh.exe Aby wyświetlić bieżącą konfigurację portów, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="9ece7-122">In [!INCLUDE[wv](../../../../includes/wv-md.md)], use the Netsh.exe tool to view the current port configuration, as shown in the following example.</span></span>  
  
    ```  
    netsh http show sslcert  
    ```  
  
### <a name="to-get-a-certificates-thumbprint"></a><span data-ttu-id="9ece7-123">Aby uzyskać odcisk palca certyfikatu</span><span class="sxs-lookup"><span data-stu-id="9ece7-123">To get a certificate's thumbprint</span></span>  
  
1.  <span data-ttu-id="9ece7-124">Użyj przystawki certyfikatów konsoli MMC można znaleźć certyfikatu X.509, który ma zamierzony cel uwierzytelniania klienta.</span><span class="sxs-lookup"><span data-stu-id="9ece7-124">Use the Certificates MMC snap-in to find an X.509 certificate that has an intended purpose of client authentication.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="9ece7-125">[Porady: wyświetlanie certyfikatów w przystawce programu MMC](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="9ece7-125"> [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>  
  
2.  <span data-ttu-id="9ece7-126">Dostęp do odcisk palca certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="9ece7-126">Access the certificate's thumbprint.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="9ece7-127">[Porady: Pobieranie odcisku palca certyfikatu](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="9ece7-127"> [How to: Retrieve the Thumbprint of a Certificate](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
3.  <span data-ttu-id="9ece7-128">Skopiuj odcisk palca certyfikatu do edytora tekstu, takiego jak Notatnik.</span><span class="sxs-lookup"><span data-stu-id="9ece7-128">Copy the thumbprint of the certificate into a text editor, such as Notepad.</span></span>  
  
4.  <span data-ttu-id="9ece7-129">Usuń wszystkie spacje między znaków szesnastkowych.</span><span class="sxs-lookup"><span data-stu-id="9ece7-129">Remove all spaces between the hexadecimal characters.</span></span> <span data-ttu-id="9ece7-130">Co w tym celu należy korzystać z funkcji znajdowania i zamieniania edytora tekstowego i Zastąp każdego miejsca znak null.</span><span class="sxs-lookup"><span data-stu-id="9ece7-130">One way to accomplish this is to use the text editor's find-and-replace feature and replace each space with a null character.</span></span>  
  
### <a name="to-bind-an-ssl-certificate-to-a-port-number"></a><span data-ttu-id="9ece7-131">Aby powiązać certyfikatu SSL z numeru portu</span><span class="sxs-lookup"><span data-stu-id="9ece7-131">To bind an SSL certificate to a port number</span></span>  
  
1.  <span data-ttu-id="9ece7-132">W [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] lub [!INCLUDE[wxp](../../../../includes/wxp-md.md)], użyj narzędzia HttpCfg.exe w trybie "set" w magazynie Secure Sockets Layer (SSL), aby powiązać certyfikat z numeru portu.</span><span class="sxs-lookup"><span data-stu-id="9ece7-132">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use the HttpCfg.exe tool in "set" mode on the Secure Sockets Layer (SSL) store to bind the certificate to a port number.</span></span> <span data-ttu-id="9ece7-133">Narzędzie używana odcisk palca certyfikatu, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="9ece7-133">The tool uses the thumbprint to identify the certificate, as shown in the following example.</span></span>  
  
    ```  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
    -   <span data-ttu-id="9ece7-134">**-I** przełącznik ma składnię `IP`:`port` i powoduje, że narzędzie, aby ustawić certyfikat z portem 8012 komputera.</span><span class="sxs-lookup"><span data-stu-id="9ece7-134">The **-i** switch has the syntax of `IP`:`port` and instructs the tool to set the certificate to port 8012 of the computer.</span></span> <span data-ttu-id="9ece7-135">Opcjonalnie cztery zera, które Poprzedź numer można również zastąpić rzeczywisty adres IP komputera.</span><span class="sxs-lookup"><span data-stu-id="9ece7-135">Optionally, the four zeroes that precede the number can also be replaced by the actual IP address of the computer.</span></span>  
  
    -   <span data-ttu-id="9ece7-136">**-H** przełącznik określa odcisk palca certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="9ece7-136">The **-h** switch specifies the thumbprint of the certificate.</span></span>  
  
2.  <span data-ttu-id="9ece7-137">W [!INCLUDE[wv](../../../../includes/wv-md.md)], użyj narzędzia Netsh.exe, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="9ece7-137">In [!INCLUDE[wv](../../../../includes/wv-md.md)], use the Netsh.exe tool, as shown in the following example.</span></span>  
  
    ```  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF}   
    ```  
  
    -   <span data-ttu-id="9ece7-138">**Skrót certyfikatu** parametr określa odcisk palca certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="9ece7-138">The **certhash** parameter specifies the thumbprint of the certificate.</span></span>  
  
    -   <span data-ttu-id="9ece7-139">**Ipport** parametr określa adres IP i port, a funkcje podobnie jak **-i** przełącznika narzędzia Httpcfg.exe opisem.</span><span class="sxs-lookup"><span data-stu-id="9ece7-139">The **ipport** parameter specifies the IP address and port, and functions just like the **-i** switch of the Httpcfg.exe tool described.</span></span>  
  
    -   <span data-ttu-id="9ece7-140">**Appid** parametru jest identyfikatorem GUID, który może służyć do identyfikowania będący właścicielem aplikacji.</span><span class="sxs-lookup"><span data-stu-id="9ece7-140">The **appid** parameter is a GUID that can be used to identify the owning application.</span></span>  
  
### <a name="to-bind-an-ssl-certificate-to-a-port-number-and-support-client-certificates"></a><span data-ttu-id="9ece7-141">Aby powiązać certyfikatu SSL z numeru portu i obsługują certyfikaty klientów</span><span class="sxs-lookup"><span data-stu-id="9ece7-141">To bind an SSL certificate to a port number and support client certificates</span></span>  
  
1.  <span data-ttu-id="9ece7-142">W [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] lub [!INCLUDE[wxp](../../../../includes/wxp-md.md)], do obsługi klientów, którzy uwierzytelniania za pomocą certyfikatów X.509 w przypadku warstwy transportu, wykonaj poprzednią procedurę, ale przekazać dodatkowy parametr wiersza polecenia do HttpCfg.exe, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="9ece7-142">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], to support clients that authenticate with X.509 certificates at the transport layer, follow the preceding procedure but pass an additional command-line parameter to HttpCfg.exe, as shown in the following example.</span></span>  
  
    ```  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6 -f 2  
    ```  
  
     <span data-ttu-id="9ece7-143">**-F** przełącznik ma składnię `n` gdzie n jest liczbą z zakresu od 1 do 7.</span><span class="sxs-lookup"><span data-stu-id="9ece7-143">The **-f** switch has the syntax of `n` where n is a number between 1 and 7.</span></span> <span data-ttu-id="9ece7-144">Wartość 2, jak pokazano w poprzednim przykładzie, włącza certyfikaty klienta w przypadku warstwy transportu.</span><span class="sxs-lookup"><span data-stu-id="9ece7-144">A value of 2, as shown in the preceding example, enables client certificates at the transport layer.</span></span> <span data-ttu-id="9ece7-145">Wartość 3 umożliwia certyfikaty klienta i mapuje te certyfikaty, konto systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="9ece7-145">A value of 3 enables client certificates and maps those certificates to a Windows account.</span></span> <span data-ttu-id="9ece7-146">Zapoznaj się z pomocą HttpCfg.exe zachowania innych wartości.</span><span class="sxs-lookup"><span data-stu-id="9ece7-146">See HttpCfg.exe Help for the behavior of other values.</span></span>  
  
2.  <span data-ttu-id="9ece7-147">W [!INCLUDE[wv](../../../../includes/wv-md.md)], do obsługi klientów, którzy uwierzytelniania za pomocą certyfikatów X.509 w przypadku warstwy transportu, wykonaj poprzednią procedurę, ale z parametrem dodatkowe, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="9ece7-147">In [!INCLUDE[wv](../../../../includes/wv-md.md)], to support clients that authenticate with X.509 certificates at the transport layer, follow the preceding procedure, but with an additional parameter, as shown in the following example.</span></span>  
  
    ```  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF} clientcertnegotiation=enable  
    ```  
  
### <a name="to-delete-an-ssl-certificate-from-a-port-number"></a><span data-ttu-id="9ece7-148">Aby usunąć certyfikat SSL z numeru portu</span><span class="sxs-lookup"><span data-stu-id="9ece7-148">To delete an SSL certificate from a port number</span></span>  
  
1.  <span data-ttu-id="9ece7-149">Użyj narzędzia HttpCfg.exe lub Netsh.exe zawiera portów i odciski palców wszystkie powiązania na komputerze.</span><span class="sxs-lookup"><span data-stu-id="9ece7-149">Use the HttpCfg.exe or Netsh.exe tool to see the ports and thumbprints of all bindings on the computer.</span></span> <span data-ttu-id="9ece7-150">Aby wydrukować dane na dysku, użyj znaku przekierowania ">", jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="9ece7-150">To print the information to disk, use the redirection character ">", as shown in the following example.</span></span>  
  
    ```  
    httpcfg query ssl>myMachinePorts.txt  
    ```  
  
2.  <span data-ttu-id="9ece7-151">W [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] lub [!INCLUDE[wxp](../../../../includes/wxp-md.md)], użyj narzędzia HttpCfg.exe z **usunąć** i **ssl** słów kluczowych.</span><span class="sxs-lookup"><span data-stu-id="9ece7-151">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use the HttpCfg.exe tool with the **delete** and **ssl** keywords.</span></span> <span data-ttu-id="9ece7-152">Użyj **-i** przełącznika `IP`:`port` numer i **-h** przełącznika do określania odcisku palca.</span><span class="sxs-lookup"><span data-stu-id="9ece7-152">Use the **-i** switch to specify the `IP`:`port` number, and the **-h** switch to specify the thumbprint.</span></span>  
  
    ```  
    httpcfg delete ssl -i 0.0.0.0:8005 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
3.  <span data-ttu-id="9ece7-153">W [!INCLUDE[wv](../../../../includes/wv-md.md)], użyj narzędzia Netsh.exe, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="9ece7-153">In [!INCLUDE[wv](../../../../includes/wv-md.md)], use the Netsh.exe tool, as shown in the following example.</span></span>  
  
    ```  
    Netsh http delete sslcert ipport=0.0.0.0:8005  
    ```  
  
## <a name="example"></a><span data-ttu-id="9ece7-154">Przykład</span><span class="sxs-lookup"><span data-stu-id="9ece7-154">Example</span></span>  
 <span data-ttu-id="9ece7-155">Poniższy kod przedstawia sposób tworzenia hostowanie Samoobsługowe przy użyciu <xref:System.ServiceModel.WSHttpBinding> klasy ustawienia zabezpieczeń transportu.</span><span class="sxs-lookup"><span data-stu-id="9ece7-155">The following code shows how to create a self-hosted service using the <xref:System.ServiceModel.WSHttpBinding> class set to transport security.</span></span> <span data-ttu-id="9ece7-156">Podczas tworzenia aplikacji, należy określić numer portu w adresie.</span><span class="sxs-lookup"><span data-stu-id="9ece7-156">When creating an application, specify the port number in the address.</span></span>  
  
 [!code-csharp[c_WsHttpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wshttpservice/cs/source.cs#3)]
 [!code-vb[c_WsHttpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wshttpservice/vb/source.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="9ece7-157">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9ece7-157">See Also</span></span>  
 [<span data-ttu-id="9ece7-158">Zabezpieczenia transportu HTTP</span><span class="sxs-lookup"><span data-stu-id="9ece7-158">HTTP Transport Security</span></span>](../../../../docs/framework/wcf/feature-details/http-transport-security.md)
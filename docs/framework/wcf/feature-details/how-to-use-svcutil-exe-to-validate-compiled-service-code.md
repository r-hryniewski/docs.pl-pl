---
title: "Instrukcje: Weryfikacja skompilowanego kodu usługi za pomocą programu Svcutil.exe"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d0d820fb-41c2-45b8-8f22-0fa5aeebbbaa
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8ea14631208f755b45a27ff323b7d875c1ae5cd8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-use-svcutilexe-to-validate-compiled-service-code"></a><span data-ttu-id="166e2-102">Instrukcje: Weryfikacja skompilowanego kodu usługi za pomocą programu Svcutil.exe</span><span class="sxs-lookup"><span data-stu-id="166e2-102">How to: Use Svcutil.exe to Validate Compiled Service Code</span></span>
<span data-ttu-id="166e2-103">Można użyć [narzędzie narzędzia metadanych elementu ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) do wykrywania błędów w implementacji usługi i konfiguracji bez obsługującego usługę.</span><span class="sxs-lookup"><span data-stu-id="166e2-103">You can use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to detect errors in service implementations and configurations without hosting the service.</span></span>  
  
### <a name="to-validate-a-service"></a><span data-ttu-id="166e2-104">Aby sprawdzić poprawność usługi</span><span class="sxs-lookup"><span data-stu-id="166e2-104">To validate a service</span></span>  
  
1.  <span data-ttu-id="166e2-105">Kompilacji usługi do pliku wykonywalnego i jeden lub więcej zestawów zależnych.</span><span class="sxs-lookup"><span data-stu-id="166e2-105">Compile your service into an executable file and one or more dependent assemblies.</span></span>  
  
2.  <span data-ttu-id="166e2-106">Otwórz wiersz polecenia z zestawu SDK</span><span class="sxs-lookup"><span data-stu-id="166e2-106">Open an SDK command prompt</span></span>  
  
3.  <span data-ttu-id="166e2-107">W wierszu polecenia Uruchom narzędzie Svcutil.exe w następującym formacie.</span><span class="sxs-lookup"><span data-stu-id="166e2-107">At the command prompt, launch the Svcutil.exe tool using the following format.</span></span> <span data-ttu-id="166e2-108">Aby uzyskać więcej informacji o różnych parametrów, zobacz Validationsection usługi z [narzędzie narzędzia metadanych elementu ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tematu.</span><span class="sxs-lookup"><span data-stu-id="166e2-108">For more information on the various parameters, see the Service Validationsection of the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) topic.</span></span>  
  
    ```  
    svcutil.exe /validate /serviceName:<serviceConfigName>  <assemblyPath>*  
    ```  
  
     <span data-ttu-id="166e2-109">Należy użyć `/serviceName` możliwość wskazania nazwy konfiguracji usługi, który chcesz zweryfikować.</span><span class="sxs-lookup"><span data-stu-id="166e2-109">You must use the `/serviceName` option to indicate the configuration name of the service you want to validate.</span></span>  
  
     <span data-ttu-id="166e2-110">`assemblyPath` Argument określa ścieżkę do pliku wykonywalnego dla usług i jeden lub więcej zestawów zawierających typów usług do sprawdzenia poprawności.</span><span class="sxs-lookup"><span data-stu-id="166e2-110">The `assemblyPath` argument specifies the path to the executable file for the service and one or more assemblies that contain the service types to be validated.</span></span> <span data-ttu-id="166e2-111">Wykonywalny zestaw musi mieć skojarzony plik konfiguracji zapewnienie konfiguracji usługi.</span><span class="sxs-lookup"><span data-stu-id="166e2-111">The executable assembly must have an associated configuration file to provide the service configuration.</span></span> <span data-ttu-id="166e2-112">Standardowa wiersza polecenia symboli wieloznacznych służy do nadania wiele zestawów.</span><span class="sxs-lookup"><span data-stu-id="166e2-112">You can use standard command-line wildcards to provide multiple assemblies.</span></span>  
  
## <a name="example"></a><span data-ttu-id="166e2-113">Przykład</span><span class="sxs-lookup"><span data-stu-id="166e2-113">Example</span></span>  
 <span data-ttu-id="166e2-114">Polecenie myServiceName usługi zaimplementowana w pliku wykonywalnym myServiceHost.exe.</span><span class="sxs-lookup"><span data-stu-id="166e2-114">The following command the service myServiceName implemented in the myServiceHost.exe executable file.</span></span>  <span data-ttu-id="166e2-115">Plik konfiguracji usługi (myServiceHost.exe.config) są ładowane automatycznie.</span><span class="sxs-lookup"><span data-stu-id="166e2-115">The configuration file for the service (myServiceHost.exe.config) is automatically loaded.</span></span>  
  
```  
svcutil /validate /serviceName:myServiceName myServiceHost.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="166e2-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="166e2-116">See Also</span></span>  
 [<span data-ttu-id="166e2-117">Narzędzie do obsługi metadanych elementu ServiceModel (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="166e2-117">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
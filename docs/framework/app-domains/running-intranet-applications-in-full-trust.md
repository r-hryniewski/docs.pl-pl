---
title: "Uruchamianie aplikacji intranetowych w trybie pełnego zaufania"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- full trust, running intranet applications in
- intranet applications, running in full trust
- running intranet applications in full trust
ms.assetid: ee13c0a8-ab02-49f7-b8fb-9eab16c6c4f0
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 58eeda82c66ecda6ffd714e808b006634ccba804
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="running-intranet-applications-in-full-trust"></a><span data-ttu-id="e62ca-102">Uruchamianie aplikacji intranetowych w trybie pełnego zaufania</span><span class="sxs-lookup"><span data-stu-id="e62ca-102">Running Intranet Applications in Full Trust</span></span>
<span data-ttu-id="e62ca-103">W programie .NET Framework w wersji 3.5 Service Pack 1 (SP1), aplikacji i ich zestawy bibliotek mogą być uruchamiane jako zestawy pełnego zaufania z udziału sieciowego.</span><span class="sxs-lookup"><span data-stu-id="e62ca-103">Starting with the .NET Framework version 3.5 Service Pack 1 (SP1), applications and their library assemblies can be run as full-trust assemblies from a network share.</span></span> <span data-ttu-id="e62ca-104"><xref:System.Security.SecurityZone.MyComputer>dowód strefy jest automatycznie dodawany do zestawów, które są ładowane z udziału w sieci intranet.</span><span class="sxs-lookup"><span data-stu-id="e62ca-104"><xref:System.Security.SecurityZone.MyComputer> zone evidence is automatically added to assemblies that are loaded from a share on the intranet.</span></span> <span data-ttu-id="e62ca-105">To świadectwo zapewnia te zestawy, takie same udzielić zestaw (co jest zazwyczaj pełnego zaufania) jako zestawy, które znajdują się na komputerze.</span><span class="sxs-lookup"><span data-stu-id="e62ca-105">This evidence gives those assemblies the same grant set (which is typically full trust) as the assemblies that reside on the computer.</span></span> <span data-ttu-id="e62ca-106">Ta funkcja nie ma zastosowania do aplikacji ClickOnce lub aplikacje, które są zaprojektowane do uruchamiania na hoście.</span><span class="sxs-lookup"><span data-stu-id="e62ca-106">This functionality does not apply to ClickOnce applications or to applications that are designed to run on a host.</span></span>  
  
## <a name="rules-for-library-assemblies"></a><span data-ttu-id="e62ca-107">Zasady zestawy bibliotek</span><span class="sxs-lookup"><span data-stu-id="e62ca-107">Rules for Library Assemblies</span></span>  
 <span data-ttu-id="e62ca-108">Zestawy, które zostały załadowane przez plik wykonywalny w udziale sieciowym mają zastosowanie następujące reguły:</span><span class="sxs-lookup"><span data-stu-id="e62ca-108">The following rules apply to assemblies that are loaded by an executable on a network share:</span></span>  
  
-   <span data-ttu-id="e62ca-109">Zestawy bibliotek musi znajdować się w tym samym folderze co zestawu pliku wykonywalnego.</span><span class="sxs-lookup"><span data-stu-id="e62ca-109">Library assemblies must reside in the same folder as the executable assembly.</span></span> <span data-ttu-id="e62ca-110">Zestawy, które znajdują się w podfolderze lub odwołuje się z inną ścieżką nie podano zestaw uprawnień pełnego zaufania.</span><span class="sxs-lookup"><span data-stu-id="e62ca-110">Assemblies that reside in a subfolder or are referenced on a different path are not given the full-trust grant set.</span></span>  
  
-   <span data-ttu-id="e62ca-111">Jeśli plik wykonywalny opóźnienie do pobrania zestawu, należy użyć tej samej ścieżki, które zostało użyte do uruchomienia pliku wykonywalnego.</span><span class="sxs-lookup"><span data-stu-id="e62ca-111">If the executable delay-loads an assembly, it must use the same path that was used to start the executable.</span></span> <span data-ttu-id="e62ca-112">Na przykład jeśli udział \\ \\ *komputera sieciowego*\\*udostępnianie* jest zamapowane na literę dysku i plik wykonywalny uruchamiany z tej ścieżki, zestawy, które są ładowane przez plik wykonywalny przy użyciu ścieżki sieciowej zostanie nie można przyznać pełne zaufanie.</span><span class="sxs-lookup"><span data-stu-id="e62ca-112">For example, if the share \\\\*network-computer*\\*share* is mapped to a drive letter and the executable is run from that path, assemblies that are loaded by the executable by using the network path will not be granted full trust.</span></span> <span data-ttu-id="e62ca-113">Aby załadować z opóźnieniem zestawu w <xref:System.Security.SecurityZone.MyComputer> strefy, plik wykonywalny, należy użyć ścieżki litery dysku.</span><span class="sxs-lookup"><span data-stu-id="e62ca-113">To delay-load an assembly in the <xref:System.Security.SecurityZone.MyComputer> zone, the executable must use the drive letter path.</span></span>  
  
## <a name="restoring-the-former-intranet-policy"></a><span data-ttu-id="e62ca-114">Przywracanie zasad wcześniejsze sieci Intranet</span><span class="sxs-lookup"><span data-stu-id="e62ca-114">Restoring the Former Intranet Policy</span></span>  
 <span data-ttu-id="e62ca-115">We wcześniejszych wersjach programu .NET Framework, zestawy udostępnione zostały przyznane <xref:System.Security.SecurityZone.Intranet> dowód strefy.</span><span class="sxs-lookup"><span data-stu-id="e62ca-115">In earlier versions of the .NET Framework, shared assemblies were granted <xref:System.Security.SecurityZone.Intranet> zone evidence.</span></span> <span data-ttu-id="e62ca-116">Konieczne było określić zasady zabezpieczeń dostępu kodu, aby przyznać pełne zaufanie do zestawu w udziale.</span><span class="sxs-lookup"><span data-stu-id="e62ca-116">You had to specify code access security policy to grant full trust to an assembly on a share.</span></span>  
  
 <span data-ttu-id="e62ca-117">To nowe zachowanie jest ustawieniem domyślnym dla zestawów sieci intranet.</span><span class="sxs-lookup"><span data-stu-id="e62ca-117">This new behavior is the default for intranet assemblies.</span></span> <span data-ttu-id="e62ca-118">Możesz wrócić do wcześniejszych zachowanie udostępniania <xref:System.Security.SecurityZone.Intranet> dowód, ustawiając klucz rejestru, która ma zastosowanie do wszystkich aplikacji na komputerze.</span><span class="sxs-lookup"><span data-stu-id="e62ca-118">You can return to the earlier behavior of providing <xref:System.Security.SecurityZone.Intranet> evidence by setting a registry key that applies to all applications on the computer.</span></span> <span data-ttu-id="e62ca-119">Ten proces jest inny dla komputerów 32-bitowe i 64-bitowe:</span><span class="sxs-lookup"><span data-stu-id="e62ca-119">This process is different for 32-bit and 64-bit computers:</span></span>  
  
-   <span data-ttu-id="e62ca-120">Na komputerach z 32-bitowy, utwórz podklucz w obszarze HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. NETFramework klucz w rejestrze systemu.</span><span class="sxs-lookup"><span data-stu-id="e62ca-120">On 32-bit computers, create a subkey under the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework key in the system registry.</span></span> <span data-ttu-id="e62ca-121">Nazwa klucza LegacyMyComputerZone za pomocą wartość DWORD na 1.</span><span class="sxs-lookup"><span data-stu-id="e62ca-121">Use the key name LegacyMyComputerZone with a DWORD value of 1.</span></span>  
  
-   <span data-ttu-id="e62ca-122">Na komputerach 64-bitowych, utwórz podklucz w obszarze HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. NETFramework klucz w rejestrze systemu.</span><span class="sxs-lookup"><span data-stu-id="e62ca-122">On 64-bit computers, create a subkey under the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework key in the system registry.</span></span> <span data-ttu-id="e62ca-123">Nazwa klucza LegacyMyComputerZone za pomocą wartość DWORD na 1.</span><span class="sxs-lookup"><span data-stu-id="e62ca-123">Use the key name LegacyMyComputerZone with a DWORD value of 1.</span></span> <span data-ttu-id="e62ca-124">Utwórz podklucz tym samym obszarze HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\. Klucz NETFramework.</span><span class="sxs-lookup"><span data-stu-id="e62ca-124">Create the same subkey under the HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\.NETFramework key.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e62ca-125">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e62ca-125">See Also</span></span>  
 [<span data-ttu-id="e62ca-126">Programowanie za pomocą zestawów</span><span class="sxs-lookup"><span data-stu-id="e62ca-126">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)
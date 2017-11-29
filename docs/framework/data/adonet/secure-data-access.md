---
title: "Bezpieczny dostęp do danych"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 473ebd69-21a3-4627-b95e-4e04d035c56f
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: c713cc8e5f3d7e81b196820e0a25fde0018b6c80
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="secure-data-access"></a><span data-ttu-id="b0ea2-102">Bezpieczny dostęp do danych</span><span class="sxs-lookup"><span data-stu-id="b0ea2-102">Secure Data Access</span></span>
<span data-ttu-id="b0ea2-103">Aby napisać bezpiecznego kodu ADO.NET, należy zapoznać mechanizmy zabezpieczeń dostępne w odpowiedni magazyn danych lub bazy danych.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-103">To write secure ADO.NET code, you have to understand the security mechanisms available in the underlying data store, or database.</span></span> <span data-ttu-id="b0ea2-104">Należy również wziąć pod uwagę ryzyko związane z innych funkcji lub składniki, które mogą zawierać aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-104">You also need to consider the security implications of other features or components that your application may contain.</span></span>  
  
## <a name="authentication-authorization-and-permissions"></a><span data-ttu-id="b0ea2-105">Uwierzytelnianie, autoryzację i uprawnień</span><span class="sxs-lookup"><span data-stu-id="b0ea2-105">Authentication, Authorization and Permissions</span></span>  
 <span data-ttu-id="b0ea2-106">Podczas łączenia z programem Microsoft SQL Server, używając uwierzytelniania systemu Windows, znanej także jako zintegrowanych zabezpieczeń, której ma zostać użyta tożsamość bieżącego aktywnego użytkownika systemu Windows, a nie przekazywanie identyfikator użytkownika i hasło.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-106">When connecting to Microsoft SQL Server, you can use Windows Authentication, also known as Integrated Security, which uses the identity of the current active Windows user rather than passing a user ID and password.</span></span> <span data-ttu-id="b0ea2-107">Zdecydowanie zalecane jest używanie uwierzytelniania systemu Windows, ponieważ poświadczenia użytkownika nie są widoczne w parametrach połączenia.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-107">Using Windows Authentication is highly recommended because user credentials are not exposed in the connection string.</span></span> <span data-ttu-id="b0ea2-108">Jeśli za pomocą uwierzytelniania systemu Windows nie może połączyć się z serwerem SQL, następnie należy rozważyć utworzenie parametry połączenia w czasie wykonywania za pomocą <xref:System.Data.SqlClient.SqlConnectionStringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-108">If you cannot use Windows Authentication to connect to SQL Server, then consider creating connection strings at run time using the <xref:System.Data.SqlClient.SqlConnectionStringBuilder>.</span></span>  
  
 <span data-ttu-id="b0ea2-109">Poświadczenia używane do uwierzytelniania muszą być obsługiwane inaczej w zależności od typu aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-109">The credentials used for authentication need to be handled differently based on the type of application.</span></span> <span data-ttu-id="b0ea2-110">Na przykład w aplikacji formularzy systemu Windows, monit o podanie informacji o uwierzytelnianiu użytkownika lub poświadczenia systemu Windows użytkownika mogą być używane.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-110">For example, in a Windows Forms application, the user can be prompted to supply authentication information, or the user's Windows credentials can be used.</span></span> <span data-ttu-id="b0ea2-111">Jednak do aplikacji sieci Web, często uzyskuje dostęp do danych przy użyciu poświadczeń dostarczonych przez samą aplikację, a nie przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-111">However, a Web application often accesses data using credentials supplied by the application itself rather than by the user.</span></span>  
  
 <span data-ttu-id="b0ea2-112">Po uwierzytelnieniu użytkowników zakres ich działania jest zależna od przyznano uprawnienia do nich.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-112">Once users have been authenticated, the scope of their actions depends on the permissions that have been granted to them.</span></span> <span data-ttu-id="b0ea2-113">Zawsze postępuj zgodnie z zasadą najniższych uprawnień i udzielić tylko te uprawnienia, które są absolutnie niezbędne.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-113">Always follow the principle of least privilege and grant only permissions that are absolutely necessary.</span></span>  
  
 <span data-ttu-id="b0ea2-114">Aby uzyskać więcej informacji zobacz następujące zasoby.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-114">For more information, see the following resources.</span></span>  
  
|<span data-ttu-id="b0ea2-115">Zasób</span><span class="sxs-lookup"><span data-stu-id="b0ea2-115">Resource</span></span>|<span data-ttu-id="b0ea2-116">Opis</span><span class="sxs-lookup"><span data-stu-id="b0ea2-116">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="b0ea2-117">Ochrona informacji o połączeniu</span><span class="sxs-lookup"><span data-stu-id="b0ea2-117">Protecting Connection Information</span></span>](../../../../docs/framework/data/adonet/protecting-connection-information.md)|<span data-ttu-id="b0ea2-118">Zawiera opis najlepszych rozwiązań dotyczących zabezpieczeń i techniki chroniące informacje dotyczące połączenia, na przykład szyfrowania parametrów połączenia za pomocą konfiguracji chronionych.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-118">Describes security best practices and techniques for protecting connection information, such as using protected configuration to encrypt connection strings.</span></span>|  
|[<span data-ttu-id="b0ea2-119">Zalecenia dotyczące strategii dostępu do danych</span><span class="sxs-lookup"><span data-stu-id="b0ea2-119">Recommendations for Data Access Strategies</span></span>](http://msdn.microsoft.com/en-us/72411f32-d12a-4de8-b961-e54fca7faaf5)|<span data-ttu-id="b0ea2-120">Zawiera zalecenia dotyczące uzyskiwania dostępu do danych i wykonywanie operacji bazy danych.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-120">Provides recommendations for accessing data and performing database operations.</span></span>|  
|[<span data-ttu-id="b0ea2-121">Konstruktorzy ciągów połączenia</span><span class="sxs-lookup"><span data-stu-id="b0ea2-121">Connection String Builders</span></span>](../../../../docs/framework/data/adonet/connection-string-builders.md)|<span data-ttu-id="b0ea2-122">Zawiera opis sposobu tworzenia parametrów połączenia z danych wejściowych użytkownika w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-122">Describes how to build connection strings from user input at run time.</span></span>|  
|[<span data-ttu-id="b0ea2-123">Przegląd zabezpieczeń serwera SQL</span><span class="sxs-lookup"><span data-stu-id="b0ea2-123">Overview of SQL Server Security</span></span>](../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)|<span data-ttu-id="b0ea2-124">W tym artykule opisano architekturę zabezpieczeń programu SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-124">Describes the SQL Server security architecture.</span></span>|  
  
## <a name="parameterized-commands-and-sql-injection"></a><span data-ttu-id="b0ea2-125">Sparametryzowanych poleceń i iniekcja kodu SQL</span><span class="sxs-lookup"><span data-stu-id="b0ea2-125">Parameterized Commands and SQL Injection</span></span>  
 <span data-ttu-id="b0ea2-126">Za pomocą sparametryzowanych poleceń chroni przed atakami iniekcji kodu SQL, w których osoba atakująca "injects" polecenia w instrukcji SQL zabezpieczenia dokonywania na serwerze.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-126">Using parameterized commands helps guard against SQL injection attacks, in which an attacker "injects" a command into a SQL statement that compromises security on the server.</span></span> <span data-ttu-id="b0ea2-127">Sparametryzowanych poleceń chronią przed ataku polegającego na iniekcji SQL, zapewniając, że wartości odebranych z zewnętrznego źródła są przekazywane jako tylko wartości i nie jest częścią instrukcji języka Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-127">Parameterized commands guard against a SQL injection attack by ensuring that values received from an external source are passed as values only, and not part of the Transact-SQL statement.</span></span> <span data-ttu-id="b0ea2-128">W związku z tym poleceń języka Transact-SQL do wartości nie są wykonywane w źródle danych.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-128">As a result, Transact-SQL commands inserted into a value are not executed at the data source.</span></span> <span data-ttu-id="b0ea2-129">Zamiast są one oceniane wyłącznie jako wartość parametru.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-129">Rather, they are evaluated solely as a parameter value.</span></span> <span data-ttu-id="b0ea2-130">Oprócz zabezpieczeń zapewnianych sparametryzowanych poleceń zapewniają wygodną metodę organizowania wartości przekazane za pomocą instrukcji języka Transact-SQL lub procedury składowanej.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-130">In addition to the security benefits, parameterized commands provide a convenient method for organizing values passed with a Transact-SQL statement or to a stored procedure.</span></span>  
  
 <span data-ttu-id="b0ea2-131">Aby uzyskać więcej informacji na temat używania sparametryzowanych poleceń zobacz następujące zasoby.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-131">For more information on using parameterized commands, see the following resources.</span></span>  
  
|<span data-ttu-id="b0ea2-132">Zasób</span><span class="sxs-lookup"><span data-stu-id="b0ea2-132">Resource</span></span>|<span data-ttu-id="b0ea2-133">Opis</span><span class="sxs-lookup"><span data-stu-id="b0ea2-133">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="b0ea2-134">Element DataAdapter parametrów</span><span class="sxs-lookup"><span data-stu-id="b0ea2-134">DataAdapter Parameters</span></span>](../../../../docs/framework/data/adonet/dataadapter-parameters.md)|<span data-ttu-id="b0ea2-135">Informacje dotyczące używania parametrów z `DataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-135">Describes how to use parameters with a `DataAdapter`.</span></span>|  
|[<span data-ttu-id="b0ea2-136">Modyfikowanie danych w procedurach składowanych</span><span class="sxs-lookup"><span data-stu-id="b0ea2-136">Modifying Data with Stored Procedures</span></span>](../../../../docs/framework/data/adonet/modifying-data-with-stored-procedures.md)|<span data-ttu-id="b0ea2-137">Opisuje sposób określić parametry i uzyskiwanie wartości zwracanej.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-137">Describes how to specify parameters and obtain a return value.</span></span>|  
|[<span data-ttu-id="b0ea2-138">Zarządzanie uprawnieniami w procedurach składowanych w programie SQL Server</span><span class="sxs-lookup"><span data-stu-id="b0ea2-138">Managing Permissions with Stored Procedures in SQL Server</span></span>](../../../../docs/framework/data/adonet/sql/managing-permissions-with-stored-procedures-in-sql-server.md)|<span data-ttu-id="b0ea2-139">Informacje dotyczące używania procedur składowanych serwera SQL w celu hermetyzacji dostępu do danych.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-139">Describes how to use SQL Server stored procedures to encapsulate data access.</span></span>|  
  
## <a name="script-exploits"></a><span data-ttu-id="b0ea2-140">Luk w skryptach</span><span class="sxs-lookup"><span data-stu-id="b0ea2-140">Script Exploits</span></span>  
 <span data-ttu-id="b0ea2-141">Wykorzystać skryptu jest innej formy iniekcji używającej złośliwego znaków wstawione do strony sieci Web.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-141">A script exploit is another form of injection that uses malicious characters inserted into a Web page.</span></span> <span data-ttu-id="b0ea2-142">Przeglądarka nie można zweryfikować wstawione znaki i będzie przetwarzać je jako część strony.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-142">The browser does not validate the inserted characters and will process them as part of the page.</span></span>  
  
 <span data-ttu-id="b0ea2-143">Aby uzyskać więcej informacji zobacz następujące zasoby.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-143">For more information, see the following resources.</span></span>  
  
|<span data-ttu-id="b0ea2-144">Zasób</span><span class="sxs-lookup"><span data-stu-id="b0ea2-144">Resource</span></span>|<span data-ttu-id="b0ea2-145">Opis</span><span class="sxs-lookup"><span data-stu-id="b0ea2-145">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="b0ea2-146">Przegląd luki w zabezpieczeniach skryptu</span><span class="sxs-lookup"><span data-stu-id="b0ea2-146">Script Exploits Overview</span></span>](http://msdn.microsoft.com/library/772c7312-211a-4eb3-8d6e-eec0aa1dcc07)|<span data-ttu-id="b0ea2-147">Opisuje sposób chronią przed skryptów i instrukcji SQL luki w zabezpieczeniach.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-147">Describes how to guard against scripting and SQL statement exploits.</span></span>|  
  
## <a name="probing-attacks"></a><span data-ttu-id="b0ea2-148">Sondowanie ataków</span><span class="sxs-lookup"><span data-stu-id="b0ea2-148">Probing Attacks</span></span>  
 <span data-ttu-id="b0ea2-149">Osoby atakujące często używają informacji z wyjątku, takie jak nazwa serwera, bazy danych lub tabeli, aby zainstalować ataku na system.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-149">Attackers often use information from an exception, such as the name of your server, database, or table, to mount an attack on your system.</span></span> <span data-ttu-id="b0ea2-150">Ponieważ wyjątków mogą zawierać określone informacje na temat aplikacji lub źródła danych, można zabezpieczyć źródła danych i aplikacji lepiej chroniony przez udostępnianie tylko istotnych informacji klientowi.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-150">Because exceptions can contain specific information about your application or data source, you can help keep your application and data source better protected by only exposing essential information to the client.</span></span>  
  
 <span data-ttu-id="b0ea2-151">Aby uzyskać więcej informacji zobacz następujące zasoby.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-151">For more information, see the following resources.</span></span>  
  
|<span data-ttu-id="b0ea2-152">Zasób</span><span class="sxs-lookup"><span data-stu-id="b0ea2-152">Resource</span></span>|<span data-ttu-id="b0ea2-153">Opis</span><span class="sxs-lookup"><span data-stu-id="b0ea2-153">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="b0ea2-154">Podstawowe założenia obsługi wyjątków</span><span class="sxs-lookup"><span data-stu-id="b0ea2-154">Exception Handling Fundamentals</span></span>](../../../../docs/standard/exceptions/exception-handling-fundamentals.md)|<span data-ttu-id="b0ea2-155">Opisuje podstawowe formy Obsługa wyjątków strukturalnych try/catch/finally.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-155">Describes the basic forms of try/catch/finally structured exception handling.</span></span>|  
|[<span data-ttu-id="b0ea2-156">Najlepsze praktyki dotyczące wyjątków</span><span class="sxs-lookup"><span data-stu-id="b0ea2-156">Best Practices for Exceptions</span></span>](../../../../docs/standard/exceptions/best-practices-for-exceptions.md)|<span data-ttu-id="b0ea2-157">Opis najlepszych rozwiązań do obsługi wyjątków.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-157">Describes best practices for handling exceptions.</span></span>|  
  
## <a name="protecting-microsoft-access-and-excel-data-sources"></a><span data-ttu-id="b0ea2-158">Ochrona programu Microsoft Access i źródeł danych</span><span class="sxs-lookup"><span data-stu-id="b0ea2-158">Protecting Microsoft Access and Excel Data Sources</span></span>  
 <span data-ttu-id="b0ea2-159">Programu Microsoft Access i Microsoft Excel może działać jako magazyn danych na potrzeby aplikacji ADO.NET, gdy wymagania dotyczące zabezpieczeń są minimalne lub nie istnieje.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-159">Microsoft Access and Microsoft Excel can act as a data store for an ADO.NET application when security requirements are minimal or nonexistent.</span></span> <span data-ttu-id="b0ea2-160">Ich funkcje zabezpieczeń dla przed intruzami, ale nie powinno być stosowane do więcej niż zniechęcić meddling przez użytkowników w organizacji uninformed.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-160">Their security features are effective for deterrence, but should not be relied upon to do more than discourage meddling by uninformed users.</span></span> <span data-ttu-id="b0ea2-161">Pliki danych fizycznych dostępu i Excel istnieje w systemie plików, a musi być dostępny dla wszystkich użytkowników.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-161">The physical data files for Access and Excel exist on the file system, and must be accessible to all users.</span></span> <span data-ttu-id="b0ea2-162">Z tego powodu narażony na ataki, mogącymi skutkować kradzieżą lub utraty danych, ponieważ pliki można łatwo skopiować lub zmodyfikować.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-162">This makes them vulnerable to attacks that could result in theft or data loss since the files can be easily copied or altered.</span></span> <span data-ttu-id="b0ea2-163">Gdy wymagana jest niezawodna zabezpieczeń, użyj programu SQL Server lub innej bazy danych na serwerze której pliki danych fizycznych nie są do odczytu z systemu plików.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-163">When robust security is required, use SQL Server or another server-based database where the physical data files are not readable from the file system.</span></span>  
  
 <span data-ttu-id="b0ea2-164">Aby uzyskać więcej informacji dotyczących ochrony danych programu Access i Excel zobacz następujące zasoby.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-164">For more information on protecting Access and Excel data, see the following resources.</span></span>  
  
|<span data-ttu-id="b0ea2-165">Zasób</span><span class="sxs-lookup"><span data-stu-id="b0ea2-165">Resource</span></span>|<span data-ttu-id="b0ea2-166">Opis</span><span class="sxs-lookup"><span data-stu-id="b0ea2-166">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="b0ea2-167">Zagadnienia dotyczące zabezpieczeń i wskazówki dotyczące Access 2007</span><span class="sxs-lookup"><span data-stu-id="b0ea2-167">Security Considerations and Guidance for Access 2007</span></span>](http://go.microsoft.com/fwlink/?LinkId=98354)|<span data-ttu-id="b0ea2-168">Opisuje metody zabezpieczeń Access 2007, takie szyfrowania plików, administrowania hasła Konwertowanie bazy danych na nowy format ACCDB i ACCDE i korzystanie z innych opcji zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-168">Describes security techniques for Access 2007 such encrypting files, administering passwords, converting databases to the new ACCDB and ACCDE formats, and using other security options.</span></span>|  
|[<span data-ttu-id="b0ea2-169">Ochrona dostępu do bazy danych z zabezpieczeń na poziomie użytkownika (MDB)</span><span class="sxs-lookup"><span data-stu-id="b0ea2-169">Help Protect an Access database with User-Level Security (MDB)</span></span>](http://go.microsoft.com/fwlink/?LinkId=47697)|<span data-ttu-id="b0ea2-170">Dotyczy 2003 dostępu.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-170">Applies to Access 2003.</span></span> <span data-ttu-id="b0ea2-171">Zawiera instrukcje dotyczące wdrażania zabezpieczeń na poziomie użytkownika do ochrony danych w programie Access 2003.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-171">Provides instructions for implementing user-level security to protect data in Access 2003.</span></span>|  
|[<span data-ttu-id="b0ea2-172">Opis roli pliki z informacjami o grupie roboczej w zabezpieczenia dostępu</span><span class="sxs-lookup"><span data-stu-id="b0ea2-172">Understanding the Role of Workgroup Information Files in Access Security</span></span>](http://support.microsoft.com/kb/305542)|<span data-ttu-id="b0ea2-173">W zabezpieczenia 2003 dostęp wyjaśniono roli i relacji tego pliku.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-173">Explains the role and relationship of the workgroup information file in Access 2003 security.</span></span>|  
|[<span data-ttu-id="b0ea2-174">Często zadawane pytania dotyczące zabezpieczeń firmy Microsoft dostęp dla programu Microsoft Access w wersji 2.0 za pomocą 2000</span><span class="sxs-lookup"><span data-stu-id="b0ea2-174">Frequently Asked Questions About Microsoft Access Security for Microsoft Access versions 2.0 through 2000</span></span>](http://go.microsoft.com/fwlink/?LinkId=47698)|<span data-ttu-id="b0ea2-175">W wersji do pobrania firmy Microsoft dostęp zabezpieczeń często zadawane pytania.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-175">Downloadable version of the Microsoft Access Security FAQ.</span></span>|  
|[<span data-ttu-id="b0ea2-176">Rozwiązywanie problemów dotyczących zabezpieczeń i ochrony</span><span class="sxs-lookup"><span data-stu-id="b0ea2-176">Troubleshoot Security and Protection</span></span>](http://go.microsoft.com/fwlink/?LinkId=47703)|<span data-ttu-id="b0ea2-177">Przedstawia informacje o rozwiązania typowych problemów z zabezpieczeniami w programie Excel 2003.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-177">Presents solutions to common problems with security in Excel 2003.</span></span>|  
  
## <a name="enterprise-services"></a><span data-ttu-id="b0ea2-178">Usługi w przedsiębiorstwie</span><span class="sxs-lookup"><span data-stu-id="b0ea2-178">Enterprise Services</span></span>  
 <span data-ttu-id="b0ea2-179">COM + zawiera własną model zabezpieczeń, który polega na konta systemu Windows NT i personifikacji procesu/wątku.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-179">COM+ contains its own security model that relies on Windows NT accounts and process/thread impersonation.</span></span> <span data-ttu-id="b0ea2-180"><xref:System.EnterpriseServices> Przestrzeń nazw zawiera otoki, umożliwiających aplikacjom .NET integracji kodu zarządzanego z zabezpieczeń usług COM + za pośrednictwem <xref:System.EnterpriseServices.ServicedComponent> klasy.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-180">The <xref:System.EnterpriseServices> namespace provides wrappers that allow .NET applications to integrate managed code with COM+ security services through the <xref:System.EnterpriseServices.ServicedComponent> class.</span></span>  
  
 <span data-ttu-id="b0ea2-181">Aby uzyskać więcej informacji zobacz następujące zasoby.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-181">For more information, see the following resource.</span></span>  
  
|<span data-ttu-id="b0ea2-182">Zasób</span><span class="sxs-lookup"><span data-stu-id="b0ea2-182">Resource</span></span>|<span data-ttu-id="b0ea2-183">Opis</span><span class="sxs-lookup"><span data-stu-id="b0ea2-183">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="b0ea2-184">COM + opartej na rolach zabezpieczeń i .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b0ea2-184">COM+ Role-Based Security and the .NET Framework</span></span>](http://msdn.microsoft.com/en-us/02ab22ef-e5e2-4d29-b33a-6e03d94c4981)|<span data-ttu-id="b0ea2-185">W tym artykule omówiono sposobu integracji z usługami zabezpieczeń COM + kodu zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-185">Discusses how to integrate managed code with COM+ security services.</span></span>|  
  
## <a name="interoperating-with-unmanaged-code"></a><span data-ttu-id="b0ea2-186">Współdziałanie z kodem niezarządzanym</span><span class="sxs-lookup"><span data-stu-id="b0ea2-186">Interoperating with Unmanaged Code</span></span>  
 <span data-ttu-id="b0ea2-187">.NET Framework zapewnia do interakcji z kodem niezarządzanym, w tym modelu COM składników, COM + usług, bibliotek typu zewnętrznego i wiele usług systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-187">The .NET Framework provides for interaction with unmanaged code, including COM components, COM+ services, external type libraries, and many operating system services.</span></span> <span data-ttu-id="b0ea2-188">Praca z kodem niezarządzanym obejmuje będzie zewnątrz zabezpieczeń dla zarządzanego kodu.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-188">Working with unmanaged code involves going outside the security perimeter for managed code.</span></span> <span data-ttu-id="b0ea2-189">Zarówno w kodzie, jak i każdy kod wywołujący go musi mieć niezarządzanych uprawnień kodu (<xref:System.Security.Permissions.SecurityPermission> z <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> określona flaga).</span><span class="sxs-lookup"><span data-stu-id="b0ea2-189">Both your code and any code that calls it must have unmanaged code permission (<xref:System.Security.Permissions.SecurityPermission> with the <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> flag specified).</span></span> <span data-ttu-id="b0ea2-190">Niezarządzany kod można wprowadzać luk w zabezpieczeniach niezamierzone do aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-190">Unmanaged code can introduce unintended security vulnerabilities into your application.</span></span> <span data-ttu-id="b0ea2-191">W związku z tym należy unikać współdziałanie z kodem niezarządzanym, chyba że jest bezwzględnie konieczne.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-191">Therefore, you should avoid interoperating with unmanaged code unless it is absolutely necessary.</span></span>  
  
 <span data-ttu-id="b0ea2-192">Aby uzyskać więcej informacji zobacz następujące zasoby.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-192">For more information, see the following resources.</span></span>  
  
|<span data-ttu-id="b0ea2-193">Zasób</span><span class="sxs-lookup"><span data-stu-id="b0ea2-193">Resource</span></span>|<span data-ttu-id="b0ea2-194">Opis</span><span class="sxs-lookup"><span data-stu-id="b0ea2-194">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="b0ea2-195">Współdziałanie z kodem niezarządzanym</span><span class="sxs-lookup"><span data-stu-id="b0ea2-195">Interoperating with Unmanaged Code</span></span>](../../../../docs/framework/interop/index.md)|<span data-ttu-id="b0ea2-196">Zawiera tematów opisujących sposób udostępnianie składników modelu COM aplikacji .NET Framework i udostępnianie składników .NET Framework modelowi COM.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-196">Contains topics describing how to expose COM components to the .NET Framework and how to expose .NET Framework components to COM.</span></span>|  
|[<span data-ttu-id="b0ea2-197">Współdziałanie COM zaawansowane</span><span class="sxs-lookup"><span data-stu-id="b0ea2-197">Advanced COM Interoperability</span></span>](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb)|<span data-ttu-id="b0ea2-198">Zawiera tematy zaawansowane, takie jak podstawowe zestawy międzyoperacyjne, wątków i przekazywanie niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="b0ea2-198">Contains advanced topics such as primary interop assemblies, threading and custom marshaling.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b0ea2-199">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b0ea2-199">See Also</span></span>  
 [<span data-ttu-id="b0ea2-200">Zabezpieczanie aplikacji ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b0ea2-200">Securing ADO.NET Applications</span></span>](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="b0ea2-201">Zabezpieczenia serwera SQL</span><span class="sxs-lookup"><span data-stu-id="b0ea2-201">SQL Server Security</span></span>](../../../../docs/framework/data/adonet/sql/sql-server-security.md)  
 [<span data-ttu-id="b0ea2-202">Zalecenia dotyczące strategii dostępu do danych</span><span class="sxs-lookup"><span data-stu-id="b0ea2-202">Recommendations for Data Access Strategies</span></span>](http://msdn.microsoft.com/en-us/72411f32-d12a-4de8-b961-e54fca7faaf5)  
 [<span data-ttu-id="b0ea2-203">Ochrona informacji o połączeniu</span><span class="sxs-lookup"><span data-stu-id="b0ea2-203">Protecting Connection Information</span></span>](../../../../docs/framework/data/adonet/protecting-connection-information.md)  
 [<span data-ttu-id="b0ea2-204">Konstruktorzy ciągów połączenia</span><span class="sxs-lookup"><span data-stu-id="b0ea2-204">Connection String Builders</span></span>](../../../../docs/framework/data/adonet/connection-string-builders.md)  
 [<span data-ttu-id="b0ea2-205">ADO.NET zarządzanego dostawcy i zestawu danych w Centrum deweloperów</span><span class="sxs-lookup"><span data-stu-id="b0ea2-205">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
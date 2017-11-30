---
title: "Porady: Włączanie programu WIF dla aplikacji usługi sieci Web WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bfc64b3d-64e9-4093-a6a4-72e933917af7
caps.latest.revision: "6"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 7db69de994770e122dd4a4233b9a44d572c32344
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-enable-wif-for-a-wcf-web-service-application"></a><span data-ttu-id="a0f5b-102">Porady: Włączanie programu WIF dla aplikacji usługi sieci Web WCF</span><span class="sxs-lookup"><span data-stu-id="a0f5b-102">How To: Enable WIF for a WCF Web Service Application</span></span>
## <a name="applies-to"></a><span data-ttu-id="a0f5b-103">Dotyczy:</span><span class="sxs-lookup"><span data-stu-id="a0f5b-103">Applies To</span></span>  
  
-   <span data-ttu-id="a0f5b-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="a0f5b-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="a0f5b-105">Microsoft® Windows® Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="a0f5b-105">Microsoft® Windows® Communication Foundation (WCF)</span></span>  
  
## <a name="summary"></a><span data-ttu-id="a0f5b-106">Podsumowanie</span><span class="sxs-lookup"><span data-stu-id="a0f5b-106">Summary</span></span>  
 <span data-ttu-id="a0f5b-107">Niniejszy instruktaż zawiera szczegółowe procedury krok po kroku służące do włączania środowiska WIF w usłudze internetowej WCF.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-107">This How-To provides detailed step-by-step procedures for enabling WIF in a WCF web service.</span></span> <span data-ttu-id="a0f5b-108">Znajdują się tu również instrukcje testowania aplikacji pozwalające sprawdzić, czy usługa internetowa poprawnie przedstawia oświadczenia w trakcie działania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-108">It also provides instructions for how to test the application to verify that the web service is correctly presenting claims when the application is run.</span></span> <span data-ttu-id="a0f5b-109">Instruktaż nie zawiera szczegółowych instrukcji tworzenia usługi tokenów zabezpieczających (STS). Zamiast tego wykorzystuje deweloperską usługę STS wbudowaną w narzędziu Tożsamość i dostęp.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-109">This How-To does not have detailed instructions for creating a Security Token Service (STS), and instead uses the Development STS that comes with the Identity and Access tool.</span></span> <span data-ttu-id="a0f5b-110">Deweloperska usługa STS nie wykonuje faktycznego uwierzytelniania i jest przeznaczona tylko do celów testowych.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-110">The Development STS does not perform real authentication and is intended for testing purposes only.</span></span> <span data-ttu-id="a0f5b-111">Narzędzie Tożsamość i dostęp jest koniecznie do ukończenia całego instruktażu.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-111">You will need to install the Identity and Access tool to complete this How-To.</span></span> <span data-ttu-id="a0f5b-112">Można go pobrać z następującej lokalizacji: [tożsamości i dostępu do narzędzia](http://go.microsoft.com/fwlink/?LinkID=245849)</span><span class="sxs-lookup"><span data-stu-id="a0f5b-112">It can be downloaded from the following location: [Identity and Access Tool](http://go.microsoft.com/fwlink/?LinkID=245849)</span></span>  
  
## <a name="contents"></a><span data-ttu-id="a0f5b-113">Spis treści</span><span class="sxs-lookup"><span data-stu-id="a0f5b-113">Contents</span></span>  
  
-   <span data-ttu-id="a0f5b-114">Cele</span><span class="sxs-lookup"><span data-stu-id="a0f5b-114">Objectives</span></span>  
  
-   <span data-ttu-id="a0f5b-115">Omówienie</span><span class="sxs-lookup"><span data-stu-id="a0f5b-115">Overview</span></span>  
  
-   <span data-ttu-id="a0f5b-116">Zestawienie czynności</span><span class="sxs-lookup"><span data-stu-id="a0f5b-116">Summary of Steps</span></span>  
  
-   <span data-ttu-id="a0f5b-117">Krok 1 — Utworzenie prostej usługi WCF</span><span class="sxs-lookup"><span data-stu-id="a0f5b-117">Step 1 – Create a Simple WCF Service</span></span>  
  
-   <span data-ttu-id="a0f5b-118">Krok 2 — Utworzenie aplikacji klienckiej dla usługi WCF</span><span class="sxs-lookup"><span data-stu-id="a0f5b-118">Step 2 – Create a Client Application for the WCF Service</span></span>  
  
-   <span data-ttu-id="a0f5b-119">Krok 3 — Przetestowanie rozwiązania</span><span class="sxs-lookup"><span data-stu-id="a0f5b-119">Step 3 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="a0f5b-120">Cele</span><span class="sxs-lookup"><span data-stu-id="a0f5b-120">Objectives</span></span>  
  
-   <span data-ttu-id="a0f5b-121">Utworzenie usługi WCF wymagającej wystawionych tokenów</span><span class="sxs-lookup"><span data-stu-id="a0f5b-121">Create a WCF service that requires issued tokens</span></span>  
  
-   <span data-ttu-id="a0f5b-122">Utworzenie klienta WCF, który wymaga tokenu od usługi STS, po czym przekazuje go do usługi WCF</span><span class="sxs-lookup"><span data-stu-id="a0f5b-122">Create a WCF client that requests a token from an STS and passes it to the WCF service</span></span>  
  
## <a name="overview"></a><span data-ttu-id="a0f5b-123">Omówienie</span><span class="sxs-lookup"><span data-stu-id="a0f5b-123">Overview</span></span>  
 <span data-ttu-id="a0f5b-124">Ten instruktaż ma pokazać, jak programista może używać funkcji federacyjnego uwierzytelniania podczas tworzenia usług WCF.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-124">This How-To is intended to demonstrate how a developer can use federated authentication when developing WCF services.</span></span> <span data-ttu-id="a0f5b-125">Oto kilka najważniejszych zalet stosowania mechanizmu federacji w usługach WCF:</span><span class="sxs-lookup"><span data-stu-id="a0f5b-125">Some of the benefits of using federation in WCF services include:</span></span>  
  
1.  <span data-ttu-id="a0f5b-126">Wyprowadzenie logiki uwierzytelniania poza kod usługi WCF</span><span class="sxs-lookup"><span data-stu-id="a0f5b-126">Factoring authentication logic out of WCF service code</span></span>  
  
2.  <span data-ttu-id="a0f5b-127">Wykorzystanie istniejących rozwiązań do zarządzania tożsamościami</span><span class="sxs-lookup"><span data-stu-id="a0f5b-127">Re-using existing identity management solutions</span></span>  
  
3.  <span data-ttu-id="a0f5b-128">Współpraca z innymi systemami zarządzania tożsamością</span><span class="sxs-lookup"><span data-stu-id="a0f5b-128">Interoperability with other identity solutions</span></span>  
  
4.  <span data-ttu-id="a0f5b-129">Elastyczność i odporność na przyszłe zmiany</span><span class="sxs-lookup"><span data-stu-id="a0f5b-129">Flexibility and resilience to future changes</span></span>  
  
 <span data-ttu-id="a0f5b-130">Środowisko WIF wraz z towarzyszącym narzędziem Tożsamość i dostęp ułatwia tworzenie oraz testowanie usług WCF dzięki wykorzystaniu funkcjonalności federacyjnego uwierzytelniania. Pokazano to poniżej.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-130">WIF and the associated Identity and Access tool make it easier to develop and test a WCF service using federated authentication, as the following steps demonstrate.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="a0f5b-131">Zestawienie czynności</span><span class="sxs-lookup"><span data-stu-id="a0f5b-131">Summary of Steps</span></span>  
  
-   <span data-ttu-id="a0f5b-132">Krok 1 — Utworzenie prostej usługi WCF</span><span class="sxs-lookup"><span data-stu-id="a0f5b-132">Step 1 – Create a Simple WCF Service</span></span>  
  
-   <span data-ttu-id="a0f5b-133">Krok 2 — Utworzenie aplikacji klienckiej dla usługi WCF</span><span class="sxs-lookup"><span data-stu-id="a0f5b-133">Step 2 – Create a Client Application for the WCF Service</span></span>  
  
-   <span data-ttu-id="a0f5b-134">Krok 3 — Przetestowanie rozwiązania</span><span class="sxs-lookup"><span data-stu-id="a0f5b-134">Step 3 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-wcf-service"></a><span data-ttu-id="a0f5b-135">Krok 1 — Utworzenie prostej usługi WCF</span><span class="sxs-lookup"><span data-stu-id="a0f5b-135">Step 1 – Create a Simple WCF Service</span></span>  
 <span data-ttu-id="a0f5b-136">W tym kroku utworzysz nową usługę WCF, która wykorzystuje deweloperską usługę STS dołączoną do narzędzia Tożsamość i dostęp.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-136">In this step, you will create a new WCF service that uses the Development STS that is included with the Identity and Access tool.</span></span>  
  
#### <a name="to-create-a-simple-wcf-service"></a><span data-ttu-id="a0f5b-137">Aby utworzyć prostą usługę WCF</span><span class="sxs-lookup"><span data-stu-id="a0f5b-137">To create a simple WCF service</span></span>  
  
1.  <span data-ttu-id="a0f5b-138">Uruchom program Visual Studio w trybie podwyższonych uprawnień jako administrator.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-138">Start Visual Studio in elevated mode as administrator.</span></span>  
  
2.  <span data-ttu-id="a0f5b-139">W programie Visual Studio, kliknij przycisk **pliku**, kliknij przycisk **nowy**, a następnie kliknij przycisk **projektu**.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-139">In Visual Studio, click **File**, click **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="a0f5b-140">W **nowy projekt** okna, kliknij przycisk **aplikacji usługi WCF**.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-140">In the **New Project** window, click **WCF Service Application**.</span></span>  
  
4.  <span data-ttu-id="a0f5b-141">W **nazwa**, wprowadź `TestService` i naciśnij klawisz **OK**.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-141">In **Name**, enter `TestService` and press **OK**.</span></span>  
  
5.  <span data-ttu-id="a0f5b-142">Kliknij prawym przyciskiem myszy **TestService** projektu w obszarze **Eksploratora rozwiązań**, a następnie wybierz pozycję **tożsamościami i dostępem**.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-142">Right-click the **TestService** project under **Solution Explorer**, then select **Identity and Access**.</span></span>  
  
6.  <span data-ttu-id="a0f5b-143">**Tożsamościami i dostępem** zostanie wyświetlone okno.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-143">The **Identity and Access** window appears.</span></span> <span data-ttu-id="a0f5b-144">W obszarze **dostawców**, wybierz pozycję **testowania aplikacji z lokalnej usługi STS programowanie**, następnie kliknij przycisk **Zastosuj**.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-144">Under **Providers**, select **Test your application with the Local Development STS**, then click **Apply**.</span></span> <span data-ttu-id="a0f5b-145">Tożsamość i narzędzia dostępu do konfigurowania usługi do używania WIF i zewnętrzny uwierzytelniania do rozwoju lokalnej usługi STS (**LocalSTS**) przez dodanie elementów konfiguracji do *Web.config* pliku.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-145">The Identity and Access Tool configures the service to use WIF and to outsource authentication to the local development STS (**LocalSTS**) by adding configuration elements to the *Web.config* file.</span></span>  
  
7.  <span data-ttu-id="a0f5b-146">W *Service1.svc.cs* plików, dodawanie `using` dyrektywy dla **System.Security.Claims** przestrzeni nazw i Zastąp istniejący kod poniżej, a następnie zapisz plik:</span><span class="sxs-lookup"><span data-stu-id="a0f5b-146">In the *Service1.svc.cs* file, add a `using` directive for the **System.Security.Claims** namespace and replace the existing code with the following, then save the file:</span></span>  
  
    ```csharp  
    public class Service1 : IService1  
    {  
        public string ComputeResponse(string input)  
        {  
            // Get the caller's identity from ClaimsPrincipal.Current  
            ClaimsPrincipal claimsPrincipal = OperationContext.Current.ClaimsPrincipal;  
  
            // Start generating the output  
            StringBuilder builder = new StringBuilder();  
            builder.AppendLine("Computed by ClaimsAwareWebService");  
            builder.AppendLine("Input received from client:" + input);  
  
            if (claimsPrincipal != null)  
            {  
                // Display the claims from the caller. Do not use this code in a production application.  
                ClaimsIdentity identity = claimsPrincipal.Identity as ClaimsIdentity;  
                builder.AppendLine("Client Name:" + identity.Name);  
                builder.AppendLine("IsAuthenticated:" + identity.IsAuthenticated);  
                builder.AppendLine("The service received the following issued claims of the client:");  
  
                // Iterate over the caller’s claims and append to the output  
                foreach (Claim claim in claimsPrincipal.Claims)  
                {  
                    builder.AppendLine("ClaimType :" + claim.Type + "   ClaimValue:" + claim.Value);  
                }  
            }  
  
            return builder.ToString();  
        }  
    }  
    ```  
  
     <span data-ttu-id="a0f5b-147">`ComputeResponse` Metoda Wyświetla właściwości różne oświadczenia, które są wystawiane przez **LocalSTS**.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-147">The `ComputeResponse` method displays the properties of various claims that are issued by **LocalSTS**.</span></span>  
  
8.  <span data-ttu-id="a0f5b-148">W *IService1.cs* pliku, Zastąp istniejący kod następującym kodem, a następnie zapisz plik:</span><span class="sxs-lookup"><span data-stu-id="a0f5b-148">In the *IService1.cs* file, replace the existing code with the following, then save the file:</span></span>  
  
    ```csharp  
    [ServiceContract]  
    public interface IService1  
    {  
        [OperationContract]  
        string ComputeResponse(string input);  
    }  
    ```  
  
9. <span data-ttu-id="a0f5b-149">Skompiluj projekt.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-149">Build the project.</span></span>  
  
10. <span data-ttu-id="a0f5b-150">Naciśnij klawisz **Ctrl-F5** do uruchamiania usługi bez konieczności uruchamiania debugera.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-150">Press **Ctrl-F5** to run the service without starting the debugger.</span></span> <span data-ttu-id="a0f5b-151">Należy otworzyć stronę sieci Web na potrzeby usługi i sprawdź, czy **LocalSTS** działa przez wyszukiwanie w obszarze powiadomień (na pasku zadań).</span><span class="sxs-lookup"><span data-stu-id="a0f5b-151">A Web page should open for the service and you can verify that **LocalSTS** is running by looking in the notification area (system tray).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="a0f5b-152">Zarówno **TestService** i **LocalSTS** musi być uruchomiona podczas dodawania odwołania do usługi do aplikacji klienckiej w następnym kroku.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-152">Both **TestService** and **LocalSTS** must be running when you add the service reference to the client application in the next step.</span></span>  
  
## <a name="step-2--create-a-client-application-for-the-wcf-service"></a><span data-ttu-id="a0f5b-153">Krok 2 — Utworzenie aplikacji klienckiej dla usługi WCF</span><span class="sxs-lookup"><span data-stu-id="a0f5b-153">Step 2 – Create a Client Application for the WCF Service</span></span>  
 <span data-ttu-id="a0f5b-154">W tym kroku utworzysz aplikację konsoli, która za pomocą deweloperskiej usługi STS będzie się uwierzytelniać w usłudze WCF utworzonej w poprzednim kroku.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-154">In this step, you will create a console application that uses the Development STS to authenticate with the WCF service you created in the previous step.</span></span>  
  
#### <a name="to-create-a-client-application"></a><span data-ttu-id="a0f5b-155">Aby utworzyć aplikację kliencką</span><span class="sxs-lookup"><span data-stu-id="a0f5b-155">To create a client application</span></span>  
  
1.  <span data-ttu-id="a0f5b-156">W programie Visual Studio, kliknij prawym przyciskiem myszy rozwiązanie, kliknij przycisk **Dodaj**, a następnie kliknij przycisk **nowy projekt**.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-156">In Visual Studio, right-click on the solution, click **Add**, and then click **New Project**.</span></span>  
  
2.  <span data-ttu-id="a0f5b-157">W **Dodawanie nowego projektu** wybierz **aplikacji konsoli** z **Visual C#** szablony list, wprowadź `Client`, a następnie naciśnij klawisz **OK**.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-157">In the **Add New Project** window, select **Console Application** from the **Visual C#** templates list, enter `Client`, and then press **OK**.</span></span> <span data-ttu-id="a0f5b-158">Nowy projekt zostanie utworzony w folderze rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-158">The new project will be created in your solution folder.</span></span>  
  
3.  <span data-ttu-id="a0f5b-159">Kliknij prawym przyciskiem myszy **odwołania** w obszarze **klienta** projektu, a następnie kliknij przycisk **Dodaj odwołanie do usługi**.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-159">Right-click on **References** under the **Client** project, and then click **Add Service Reference**.</span></span>  
  
4.  <span data-ttu-id="a0f5b-160">W **Dodaj odwołanie do usługi** okna, kliknij strzałkę listy rozwijanej w **odnajdowania** przycisk **usług w rozwiązaniu**.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-160">In the **Add Service Reference** window, click the drop-down arrow on the **Discover** button and click **Services in Solution**.</span></span> <span data-ttu-id="a0f5b-161">**Adres** zostaną wypełnione automatycznie z usługą WCF został utworzony wcześniej, i **Namespace** zostanie ustawiona do **ServiceReference1**.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-161">The **Address** will automatically populate with the WCF service you created earlier, and the **Namespace** will be set to **ServiceReference1**.</span></span> <span data-ttu-id="a0f5b-162">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-162">Click **OK**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="a0f5b-163">Zarówno **TestService** i **LocalSTS** musi być uruchomiona podczas dodawania odwołania do usługi do klienta.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-163">Both **TestService** and **LocalSTS** must be running when you add the service reference to the client.</span></span>  
  
5.  <span data-ttu-id="a0f5b-164">Program Visual Studio wygeneruje klasy serwera proxy dla usługi WCF i doda wszystkie niezbędne parametry odwołań.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-164">Visual Studio will generate proxy classes for the WCF service, and add all of the necessary reference information.</span></span> <span data-ttu-id="a0f5b-165">Spowoduje to również dodanie elementów do *App.config* plik, aby skonfigurować klienta do pobrania tokenu z STS do uwierzytelniania w usłudze.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-165">It will also add elements to the *App.config* file to configure the client to get a token from the STS to authenticate with the service.</span></span> <span data-ttu-id="a0f5b-166">Po zakończeniu tego procesu **Program.cs** plik zostanie otwarty.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-166">When this process is finished, the **Program.cs** file will open.</span></span> <span data-ttu-id="a0f5b-167">Dodaj `using` dyrektywy dla **System.ServiceModel** i drugi dla **Client.ServiceReference1**, Zastąp **Main** metodę z następującym kodem, a następnie Zapisz plik:</span><span class="sxs-lookup"><span data-stu-id="a0f5b-167">Add a `using` directive for **System.ServiceModel** and another for **Client.ServiceReference1**, replace the **Main** method with the following code, then save the file:</span></span>  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        // Create the client for the service  
        Service1Client client = new Service1Client();  
        Console.WriteLine("-------------WCF Client Application--------------\n");  
  
        while (!ShouldQuitApplication())  
        {  
            try  
            {  
                Console.WriteLine(client.ComputeResponse("Hello World"));  
            }  
            catch (CommunicationException e)  
            {  
                Console.WriteLine(e.Message);  
                Console.WriteLine(e.StackTrace);  
                Exception ex = e.InnerException;  
                while (ex != null)  
                {  
                    Console.WriteLine("===========================");  
                    Console.WriteLine(ex.Message);  
                    Console.WriteLine(ex.StackTrace);  
                    ex = ex.InnerException;  
                }  
            }  
            catch (TimeoutException)  
            {  
                Console.WriteLine("Timed out...");  
            }  
            catch (Exception e)  
            {  
                Console.WriteLine("An unexpected exception occurred.");  
                Console.WriteLine(e.StackTrace);  
            }  
        }  
  
        client.Close();  
  
        if (client != null)  
        {  
            client.Abort();  
        }  
    }  
  
    static bool ShouldQuitApplication()  
    {  
        Console.WriteLine("---------------------------------------------------------------------");  
        Console.WriteLine("Press Enter key to invoke service, any other key to quit application:");  
        Console.WriteLine("----------------------------------------------------------------------");  
  
        ConsoleKeyInfo keyInfo = Console.ReadKey();  
        if (keyInfo.Key == ConsoleKey.Enter)  
            return false;  
        return true;  
    }  
    ```  
  
6.  <span data-ttu-id="a0f5b-168">Otwórz *App.config* i Dodaj następujący kod XML jako pierwszy element podrzędny w `<system.serviceModel>` elementu, a następnie zapisz ten plik:</span><span class="sxs-lookup"><span data-stu-id="a0f5b-168">Open the *App.config* file and add the following XML as the first child element under the `<system.serviceModel>` element, then save the file:</span></span>  
  
    ```xml  
    <behaviors>  
       <endpointBehaviors>  
         <behavior>  
           <clientCredentials>  
             <serviceCertificate>  
               <authentication certificateValidationMode="None"/>  
             </serviceCertificate>  
           </clientCredentials>  
         </behavior>  
       </endpointBehaviors>  
     </behaviors>  
    ```  
  
     <span data-ttu-id="a0f5b-169">Spowoduje to wyłączenie mechanizmu sprawdzania poprawności certyfikatów.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-169">This disables certificate validation.</span></span>  
  
7.  <span data-ttu-id="a0f5b-170">Kliknij prawym przyciskiem myszy **TestService** rozwiązania i kliknij pozycję **Ustaw projekty startowe**.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-170">Right-click the **TestService** solution and click on **Set StartUp Projects**.</span></span> <span data-ttu-id="a0f5b-171">**Projekt startowy** zostanie otwarta strona właściwości.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-171">The **Startup Project** property page opens.</span></span> <span data-ttu-id="a0f5b-172">W **projekt startowy** strony właściwości, wybierz opcję **wiele projektów startowych** kliknięcie w **akcji** dla każdego projektu i wybierz pole **Start** z menu rozwijanego.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-172">In the **Startup Project** property page, select **Multiple startup projects** then click in the **Action** field for each project and select **Start** from the drop-down menu.</span></span> <span data-ttu-id="a0f5b-173">Kliknij przycisk **OK** Aby zapisać ustawienia.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-173">Click **OK** to save the settings.</span></span>  
  
8.  <span data-ttu-id="a0f5b-174">Skompiluj rozwiązanie.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-174">Build the solution.</span></span>  
  
## <a name="step-3--test-your-solution"></a><span data-ttu-id="a0f5b-175">Krok 3 — Przetestowanie rozwiązania</span><span class="sxs-lookup"><span data-stu-id="a0f5b-175">Step 3 – Test Your Solution</span></span>  
 <span data-ttu-id="a0f5b-176">W tym kroku przetestujesz aplikację WCF korzystającą ze środowiska WIF i sprawdzisz, czy są prezentowane oświadczenia.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-176">In this step you will test your WIF-enabled WCF application and verify that claims are presented.</span></span>  
  
#### <a name="to-test-your-wif-enabled-wcf-application-for-claims"></a><span data-ttu-id="a0f5b-177">Aby przetestować aplikację WCF używającą środowiska WIF pod kątem oświadczeń</span><span class="sxs-lookup"><span data-stu-id="a0f5b-177">To test your WIF-enabled WCF application for claims</span></span>  
  
1.  <span data-ttu-id="a0f5b-178">Naciśnij klawisz **F5** Aby skompilować i uruchomić aplikację.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-178">Press **F5** to build and run the application.</span></span> <span data-ttu-id="a0f5b-179">Powinny być prezentowane z okna konsoli i następujący tekst: **naciśnij klawisz Enter, klucz do wywołania usługi, dowolny klawisz, aby zakończyć pracę aplikacji:**</span><span class="sxs-lookup"><span data-stu-id="a0f5b-179">You should be presented with a console window, and the following text: **Press Enter key to invoke service, any other key to quit application:**</span></span>  
  
2.  <span data-ttu-id="a0f5b-180">Naciśnij klawisz **Enter**, oraz następujących informacji oświadczeń powinny być wyświetlane w konsoli:</span><span class="sxs-lookup"><span data-stu-id="a0f5b-180">Press **Enter**, and the following claims information should appear in the console:</span></span>  
  
    ```  
    Computed by Service1  
    Input received from client: Hello World  
    Client Name: Terry  
    IsAuthenticated: True  
    The service received the following issued claims of the client:  
    ClaimType :http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name    ClaimValue:Terry  
    ClaimType :http://schema.xmlsoap.org/ws/2005/05/identity/claims/surname    ClaimValue:Adams  
    ClaimType :http://schemas.microsoft.com/ws/2008/06/identity/claims/role    ClaimValue:developer  
    ClaimType :http://schemas.xmlsoap.org/ws/2005/05/identity/claims/emailaddress    ClaimValue:terry@contoso.com  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="a0f5b-181">Zarówno **TestService** i **LocalSTS** musi być uruchomiona przed naciśnięciem przycisku **Enter**.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-181">Both **TestService** and **LocalSTS** must be running before you press **Enter**.</span></span> <span data-ttu-id="a0f5b-182">Należy otworzyć stronę sieci Web na potrzeby usługi i sprawdź, czy **LocalSTS** działa przez wyszukiwanie w obszarze powiadomień (na pasku zadań).</span><span class="sxs-lookup"><span data-stu-id="a0f5b-182">A Web page should open for the service and you can verify that **LocalSTS** is running by looking in the notification area (system tray).</span></span>  
  
3.  <span data-ttu-id="a0f5b-183">Jeśli te oświadczenia widać w konsoli, dokonano pomyślnego uwierzytelnienia w usłudze STS pozwalającego na wyświetlanie oświadczeń z usługi WCF.</span><span class="sxs-lookup"><span data-stu-id="a0f5b-183">If these claims appear in the console, you have successfully authenticated with the STS to display claims from the WCF service.</span></span>
---
title: "Środowisko uruchomieniowe pakietu magazynu"
description: "W tym temacie opisano magazynie pakietów środowiska uruchomieniowego i manifestów docelowy używana przez .NET Core."
keywords: ".NET i .NET core dotnet magazynu, magazynie pakietów środowiska wykonawczego"
author: bleroy
ms.author: mairaw
ms.date: 08/12/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 9521d8b4-25fc-412b-a65b-4c975ebf6bfd
ms.openlocfilehash: 607f8259fa6d8488a7fccf3c7d90b6cf40d5f237
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="runtime-package-store"></a><span data-ttu-id="0514c-104">Środowisko uruchomieniowe pakietu magazynu</span><span class="sxs-lookup"><span data-stu-id="0514c-104">Runtime package store</span></span>

<span data-ttu-id="0514c-105">Począwszy od programu .NET Core 2.0 jest możliwe pakietu i wdrażanie aplikacji pod kątem znanych zestawu pakietów, które istnieją w środowisku docelowym.</span><span class="sxs-lookup"><span data-stu-id="0514c-105">Starting with .NET Core 2.0, it's possible to package and deploy apps against a known set of packages that exist in the target environment.</span></span> <span data-ttu-id="0514c-106">Zalety są szybsze wdrożeń, niższe użycie miejsca na dysku i uruchamiania lepszą wydajność w niektórych przypadkach.</span><span class="sxs-lookup"><span data-stu-id="0514c-106">The benefits are faster deployments, lower disk space use, and improved startup performance in some cases.</span></span>

<span data-ttu-id="0514c-107">Ta funkcja jest zaimplementowany jako *Magazyn pakietu środowiska uruchomieniowego*, czyli katalogu na dysku przechowywania pakietów (zazwyczaj na */usr/local/share/dotnet/store* na macOS/Linux i *C: / Program plików/dotnet/store* w systemie Windows).</span><span class="sxs-lookup"><span data-stu-id="0514c-107">This feature is implemented as a *runtime package store*, which is a directory on disk where packages are stored (typically at */usr/local/share/dotnet/store* on macOS/Linux and *C:/Program Files/dotnet/store* on Windows).</span></span> <span data-ttu-id="0514c-108">W tym katalogu są podkatalogi dla architektury i [platform docelowych](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="0514c-108">Under this directory, there are subdirectories for architectures and [target frameworks](../../standard/frameworks.md).</span></span> <span data-ttu-id="0514c-109">Układ pliku jest podobny sposób, który [NuGet zasoby zostały przedstawione na dysku](/nuget/create-packages/supporting-multiple-target-frameworks#framework-version-folder-structure):</span><span class="sxs-lookup"><span data-stu-id="0514c-109">The file layout is similar to the way that [NuGet assets are laid out on disk](/nuget/create-packages/supporting-multiple-target-frameworks#framework-version-folder-structure):</span></span>

<span data-ttu-id="0514c-110">\dotnet</span><span class="sxs-lookup"><span data-stu-id="0514c-110">\dotnet</span></span>   
<span data-ttu-id="0514c-111">&nbsp;&nbsp;\store</span><span class="sxs-lookup"><span data-stu-id="0514c-111">&nbsp;&nbsp;\store</span></span>   
<span data-ttu-id="0514c-112">&nbsp;&nbsp;&nbsp;&nbsp;\x64</span><span class="sxs-lookup"><span data-stu-id="0514c-112">&nbsp;&nbsp;&nbsp;&nbsp;\x64</span></span>   
<span data-ttu-id="0514c-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\netcoreapp2.0</span><span class="sxs-lookup"><span data-stu-id="0514c-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\netcoreapp2.0</span></span>   
<span data-ttu-id="0514c-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\Microsoft.applicationinsights</span><span class="sxs-lookup"><span data-stu-id="0514c-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\microsoft.applicationinsights</span></span>   
<span data-ttu-id="0514c-115">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\Microsoft.aspnetcore</span><span class="sxs-lookup"><span data-stu-id="0514c-115">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\microsoft.aspnetcore</span></span>   
<span data-ttu-id="0514c-116">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;...</span><span class="sxs-lookup"><span data-stu-id="0514c-116">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;...</span></span>   
<span data-ttu-id="0514c-117">&nbsp;&nbsp;&nbsp;&nbsp;\x86</span><span class="sxs-lookup"><span data-stu-id="0514c-117">&nbsp;&nbsp;&nbsp;&nbsp;\x86</span></span>   
<span data-ttu-id="0514c-118">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\netcoreapp2.0</span><span class="sxs-lookup"><span data-stu-id="0514c-118">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\netcoreapp2.0</span></span>   
<span data-ttu-id="0514c-119">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\Microsoft.applicationinsights</span><span class="sxs-lookup"><span data-stu-id="0514c-119">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\microsoft.applicationinsights</span></span>   
<span data-ttu-id="0514c-120">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\Microsoft.aspnetcore</span><span class="sxs-lookup"><span data-stu-id="0514c-120">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\microsoft.aspnetcore</span></span>   
<span data-ttu-id="0514c-121">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;...</span><span class="sxs-lookup"><span data-stu-id="0514c-121">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;...</span></span>   

<span data-ttu-id="0514c-122">A *manifest docelowej* plik zawiera listę pakietów w magazynie pakietów środowiska wykonawczego.</span><span class="sxs-lookup"><span data-stu-id="0514c-122">A *target manifest* file lists the packages in the runtime package store.</span></span> <span data-ttu-id="0514c-123">Umożliwiają deweloperom tego manifestu podczas publikowania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="0514c-123">Developers can target this manifest when publishing their app.</span></span> <span data-ttu-id="0514c-124">Manifest docelowy jest zwykle zapewniany przez właściciela środowiska produkcyjnego docelowych.</span><span class="sxs-lookup"><span data-stu-id="0514c-124">The target manifest is typically provided by the owner of the targeted production environment.</span></span>

## <a name="preparing-a-runtime-environment"></a><span data-ttu-id="0514c-125">Przygotowywanie środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="0514c-125">Preparing a runtime environment</span></span>

<span data-ttu-id="0514c-126">Administrator środowiska uruchomieniowego można zoptymalizować aplikacje dla wdrożeń szybsze i dolnym użycie miejsca na dysku według budynków magazynie pakietów środowiska uruchomieniowego i odpowiednie manifest docelowej.</span><span class="sxs-lookup"><span data-stu-id="0514c-126">The administrator of a runtime environment can optimize apps for faster deployments and lower disk space use by building a runtime package store and the corresponding target manifest.</span></span>

<span data-ttu-id="0514c-127">Pierwszym krokiem jest utworzenie *manifestu sklepu pakietu* który zawiera listę pakietów, które tworzą magazyn pakietu środowiska wykonawczego.</span><span class="sxs-lookup"><span data-stu-id="0514c-127">The first step is to create a *package store manifest* that lists the packages that compose the runtime package store.</span></span> <span data-ttu-id="0514c-128">Ten format jest zgodny z formatem pliku projektu (*csproj*).</span><span class="sxs-lookup"><span data-stu-id="0514c-128">This file format is compatible with the project file format (*csproj*).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <ItemGroup>
    <PackageReference Include="<NUGET_PACKAGE>" Version="<VERSION>" />
    <!-- Include additional packages here -->
  </ItemGroup>
</Project>
```

<span data-ttu-id="0514c-129">**Przykład**</span><span class="sxs-lookup"><span data-stu-id="0514c-129">**Example**</span></span>

<span data-ttu-id="0514c-130">Następujące manifest przykład w magazynie pakietów (*packages.csproj*) służy do dodawania [ `Newtonsoft.Json` ](https://www.nuget.org/packages/Newtonsoft.Json/) i [ `Moq` ](https://www.nuget.org/packages/moq/) do magazynu pakiet środowiska uruchomieniowego:</span><span class="sxs-lookup"><span data-stu-id="0514c-130">The following example package store manifest (*packages.csproj*) is used to add [`Newtonsoft.Json`](https://www.nuget.org/packages/Newtonsoft.Json/) and [`Moq`](https://www.nuget.org/packages/moq/) to a runtime package store:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="10.0.3" />
    <PackageReference Include="Moq" Version="4.7.63" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="0514c-131">Udostępnić Magazyn pakietu środowiska uruchomieniowego, wykonując `dotnet store` z manifestu sklepu pakietu, środowisko uruchomieniowe i framework:</span><span class="sxs-lookup"><span data-stu-id="0514c-131">Provision the runtime package store by executing `dotnet store` with the package store manifest, runtime, and framework:</span></span>

```console
dotnet store --manifest <PATH_TO_MANIFEST_FILE> --runtime <RUNTIME_IDENTIFIER> --framework <FRAMEWORK>
```

<span data-ttu-id="0514c-132">**Przykład**</span><span class="sxs-lookup"><span data-stu-id="0514c-132">**Example**</span></span>

```console
dotnet store --manifest packages.csproj --runtime win10-x64 --framework netcoreapp2.0 --framework-version 2.0.0
```

<span data-ttu-id="0514c-133">Wiele ścieżek manifestu sklepu pakietu docelowych można przekazać do pojedynczego [ `dotnet store` ](../tools/dotnet-store.md) polecenia powtarzając opcja i ścieżki w poleceniu.</span><span class="sxs-lookup"><span data-stu-id="0514c-133">You can pass multiple target package store manifest paths to a single [`dotnet store`](../tools/dotnet-store.md) command by repeating the option and path in the command.</span></span>

<span data-ttu-id="0514c-134">Domyślnie dane wyjściowe polecenia jest magazynem pakietu w obszarze *.dotnet/store* podkatalogu profilu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="0514c-134">By default, the output of the command is a package store under the *.dotnet/store* subdirectory of the user's profile.</span></span> <span data-ttu-id="0514c-135">Możesz określić inną lokalizację przy użyciu `--output <OUTPUT_DIRECTORY>` opcji.</span><span class="sxs-lookup"><span data-stu-id="0514c-135">You can specify a different location using the `--output <OUTPUT_DIRECTORY>` option.</span></span> <span data-ttu-id="0514c-136">Katalog główny magazynu zawiera manifest docelowej *artifact.xml* pliku.</span><span class="sxs-lookup"><span data-stu-id="0514c-136">The root directory of the store contains a target manifest *artifact.xml* file.</span></span> <span data-ttu-id="0514c-137">Ten plik można udostępnić do pobrania i jest używany przez autorów aplikacji, które ma być docelowa tego magazynu podczas publikowania.</span><span class="sxs-lookup"><span data-stu-id="0514c-137">This file can be made available for download and be used by app authors who want to target this store when publishing.</span></span>

<span data-ttu-id="0514c-138">**Przykład**</span><span class="sxs-lookup"><span data-stu-id="0514c-138">**Example**</span></span>

<span data-ttu-id="0514c-139">Następujące *artifact.xml* jest generowany po uruchomieniu w poprzednim przykładzie.</span><span class="sxs-lookup"><span data-stu-id="0514c-139">The following *artifact.xml* file is produced after running the previous example.</span></span> <span data-ttu-id="0514c-140">Należy pamiętać, że [ `Castle.Core` ](https://www.nuget.org/packages/Castle.Core/) zależą od elementu `Moq`, tak, aby go zostało automatycznie uwzględnione w *artifacts.xml* pliku manifestu.</span><span class="sxs-lookup"><span data-stu-id="0514c-140">Note that [`Castle.Core`](https://www.nuget.org/packages/Castle.Core/) is a dependency of `Moq`, so it's included automatically and appears in the *artifacts.xml* manifest file.</span></span>

```xml
<StoreArtifacts>
  <Package Id="Newtonsoft.Json" Version="10.0.3" />
  <Package Id="Castle.Core" Version="4.1.0" />
  <Package Id="Moq" Version="4.7.63" />
</StoreArtifacts>
```

## <a name="publishing-an-app-against-a-target-manifest"></a><span data-ttu-id="0514c-141">Publikowanie aplikacji dla manifest docelowego</span><span class="sxs-lookup"><span data-stu-id="0514c-141">Publishing an app against a target manifest</span></span>

<span data-ttu-id="0514c-142">Jeśli masz manifestu pliku na dysku docelowym, określ ścieżkę do pliku podczas publikowania aplikacji za pomocą [ `dotnet publish` ](../tools/dotnet-publish.md) polecenia:</span><span class="sxs-lookup"><span data-stu-id="0514c-142">If you have a target manifest file on disk, you specify the path to the file when publishing your app with the [`dotnet publish`](../tools/dotnet-publish.md) command:</span></span>

```console
dotnet publish --manifest <PATH_TO_MANIFEST_FILE>
```

<span data-ttu-id="0514c-143">**Przykład**</span><span class="sxs-lookup"><span data-stu-id="0514c-143">**Example**</span></span>

```console
dotnet publish --manifest manifest.xml
```

<span data-ttu-id="0514c-144">Wynikowa opublikowanej aplikacji można wdrożyć na środowisku pakietów opisanego w manifeście docelowej.</span><span class="sxs-lookup"><span data-stu-id="0514c-144">You deploy the resulting published app to an environment that has the packages described in the target manifest.</span></span> <span data-ttu-id="0514c-145">Niepowodzenie w tym przypadku powoduje niepowodzenie uruchomienia aplikacji.</span><span class="sxs-lookup"><span data-stu-id="0514c-145">Failing to do so results in the app failing to start.</span></span>

<span data-ttu-id="0514c-146">Określ wiele manifestów docelowego podczas publikowania aplikacji przez powtarzające się opcja i ścieżki (na przykład `--manifest manifest1.xml --manifest manifest2.xml`).</span><span class="sxs-lookup"><span data-stu-id="0514c-146">Specify multiple target manifests when publishing an app by repeating the option and path (for example, `--manifest manifest1.xml --manifest manifest2.xml`).</span></span> <span data-ttu-id="0514c-147">Po wykonaniu tej aplikacji jest usuwane Unii pakietów określona w plikach manifestu docelowy dostarczony do polecenia.</span><span class="sxs-lookup"><span data-stu-id="0514c-147">When you do so, the app is trimmed for the union of packages specified in the target manifest files provided to the command.</span></span>

## <a name="specifying-target-manifests-in-the-project-file"></a><span data-ttu-id="0514c-148">Określanie docelowej manifesty w pliku projektu</span><span class="sxs-lookup"><span data-stu-id="0514c-148">Specifying target manifests in the project file</span></span>

<span data-ttu-id="0514c-149">Zamiast określania docelowych manifesty z [ `dotnet publish` ](../tools/dotnet-publish.md) ma je określić w pliku projektu jako Rozdzielana średnikami lista ścieżek w ramach polecenie  **\<TargetManifestFiles >** tagu.</span><span class="sxs-lookup"><span data-stu-id="0514c-149">An alternative to specifying target manifests with the [`dotnet publish`](../tools/dotnet-publish.md) command is to specify them in the project file as a semicolon-separated list of paths under a **\<TargetManifestFiles>** tag.</span></span>

```xml
<PropertyGroup>
  <TargetManifestFiles>manifest1.xml;manifest2.xml</TargetManifestFiles>
</PropertyGroup>
```

<span data-ttu-id="0514c-150">Określ docelowy manifesty w pliku projektu tylko wtedy, gdy dobrze znane, takich jak .NET Core projektów środowiska docelowego dla aplikacji.</span><span class="sxs-lookup"><span data-stu-id="0514c-150">Specify the target manifests in the project file only when the target environment for the app is well-known, such as for .NET Core projects.</span></span> <span data-ttu-id="0514c-151">Nie jest to w przypadku projektów open source.</span><span class="sxs-lookup"><span data-stu-id="0514c-151">This isn't the case for open-source projects.</span></span> <span data-ttu-id="0514c-152">Użytkownicy projekt typu open source zwykle go wdrożyć w różnych środowiskach.</span><span class="sxs-lookup"><span data-stu-id="0514c-152">The users of an open-source project typically deploy it to different production environments.</span></span> <span data-ttu-id="0514c-153">Tych środowisk produkcyjnych zazwyczaj mają różne zestawy wstępnie zainstalowane pakiety.</span><span class="sxs-lookup"><span data-stu-id="0514c-153">These production environments generally have different sets of packages pre-installed.</span></span> <span data-ttu-id="0514c-154">Nie można wprowadzić założenia dotyczące manifestu docelowego w takich środowiskach, należy użyć `--manifest` opcji [ `dotnet publish` ](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="0514c-154">You can't make assumptions about the target manifest in such environments, so you should use the `--manifest` option of [`dotnet publish`](../tools/dotnet-publish.md).</span></span>

## <a name="aspnet-core-implicit-store"></a><span data-ttu-id="0514c-155">Niejawne magazynu platformy ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0514c-155">ASP.NET Core implicit store</span></span>

<span data-ttu-id="0514c-156">Funkcja Magazyn pakietu środowiska uruchomieniowego służy niejawnie przez aplikację ASP.NET Core gdy aplikacja jest wdrożona jako [wdrożenia framework zależne (stacje)](index.md#framework-dependent-deployments-fdd) aplikacji.</span><span class="sxs-lookup"><span data-stu-id="0514c-156">The runtime package store feature is used implicitly by an ASP.NET Core app when the app is deployed as a [framework-dependent deployment (FDD)](index.md#framework-dependent-deployments-fdd) app.</span></span> <span data-ttu-id="0514c-157">Obiekty docelowe w [ `Microsoft.NET.Sdk.Web` ](https://github.com/aspnet/websdk) obejmują manifestów odwołujące się do niejawnego magazynie pakietów w systemie docelowym.</span><span class="sxs-lookup"><span data-stu-id="0514c-157">The targets in [`Microsoft.NET.Sdk.Web`](https://github.com/aspnet/websdk) include manifests referencing the implicit package store on the target system.</span></span> <span data-ttu-id="0514c-158">Ponadto dowolną aplikację Dyskietki, która jest zależna od `Microsoft.AspNetCore.All` pakietu wyniki w opublikowanej aplikacji, który zawiera tylko aplikacji i jej zasoby i nie pakiety wymienione w `Microsoft.AspNetCore.All` metapackage.</span><span class="sxs-lookup"><span data-stu-id="0514c-158">Additionally, any FDD app that depends on the `Microsoft.AspNetCore.All` package results in a published app that contains only the app and its assets and not the packages listed in the `Microsoft.AspNetCore.All` metapackage.</span></span> <span data-ttu-id="0514c-159">Zakłada się, że pakiety są obecne w systemie docelowym.</span><span class="sxs-lookup"><span data-stu-id="0514c-159">It's assumed that those packages are present on the target system.</span></span>

<span data-ttu-id="0514c-160">Magazyn pakietu środowiska uruchomieniowego jest zainstalowana na hoście, po zainstalowaniu programu .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="0514c-160">The runtime package store is installed on the host when the .NET Core SDK is installed.</span></span> <span data-ttu-id="0514c-161">Inne instalatorów może udostępnić magazyn środowisko uruchomieniowe pakietu, w tym Zip/tarball instalacji programu .NET Core SDK `apt-get`, Red Hat Yum, .NET Core systemu Windows serwer obsługujący pakietu i instalacje magazynie pakietów ręcznego środowiska wykonawczego.</span><span class="sxs-lookup"><span data-stu-id="0514c-161">Other installers may provide the runtime package store, including Zip/tarball installations of the .NET Core SDK, `apt-get`, Red Hat Yum, the .NET Core Windows Server Hosting bundle, and manual runtime package store installations.</span></span>

<span data-ttu-id="0514c-162">W przypadku wdrażania [wdrożenia framework zależne (stacje)](index.md#framework-dependent-deployments-fdd) aplikacji, upewnij się, że środowisko docelowe ma zainstalowany zestaw .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="0514c-162">When deploying a [framework-dependent deployment (FDD)](index.md#framework-dependent-deployments-fdd) app, make sure that the target environment has the .NET Core SDK installed.</span></span> <span data-ttu-id="0514c-163">Jeśli aplikacja jest wdrażana w środowisku, który nie zawiera platformy ASP.NET Core, można zrezygnować z magazynu niejawne, określając  **\<PublishWithAspNetCoreTargetManifest >** ustawioną `false` w pliku projektu, jak w programie Poniższy przykład:</span><span class="sxs-lookup"><span data-stu-id="0514c-163">If the app is deployed to an environment that doesn't include ASP.NET Core, you can opt out of the implicit store by specifying  **\<PublishWithAspNetCoreTargetManifest>** set to `false` in the project file as in the following example:</span></span>

```xml
<PropertyGroup>
  <PublishWithAspNetCoreTargetManifest>false</PublishWithAspNetCoreTargetManifest>
</PropertyGroup>
```

> [!NOTE] 
> <span data-ttu-id="0514c-164">Dla [niezależne wdrożenia (SCD)](index.md#self-contained-deployments-scd) aplikacji, zakłada się, że w systemie docelowym musi nie zawiera wymaganych pakietów manifestu.</span><span class="sxs-lookup"><span data-stu-id="0514c-164">For [self-contained deployment (SCD)](index.md#self-contained-deployments-scd) apps, it's assumed that the target system doesn't necessarily contain the required manifest packages.</span></span> <span data-ttu-id="0514c-165">W związku z tym  **\<PublishWithAspNetCoreTargetManifest >** nie można ustawić `true` SCD aplikacji.</span><span class="sxs-lookup"><span data-stu-id="0514c-165">Therefore, **\<PublishWithAspNetCoreTargetManifest>** cannot be set to `true` for an SCD app.</span></span>

<span data-ttu-id="0514c-166">W przypadku wdrożenia aplikacji z zależnością manifestu, który istnieje we wdrożeniu (znajduje się w zestawie *bin* folderu), magazynie pakietów środowiska uruchomieniowego *nie jest używana* na hoście dla tego zestawu.</span><span class="sxs-lookup"><span data-stu-id="0514c-166">If you deploy an application with a manifest dependency that's present in the deployment (the assembly is present in the *bin* folder), the runtime package store *isn't used* on the host for that assembly.</span></span> <span data-ttu-id="0514c-167">*Bin* folderu zestaw jest używany niezależnie od jej obecności w magazynie pakietów środowiska uruchomieniowego na hoście.</span><span class="sxs-lookup"><span data-stu-id="0514c-167">The *bin* folder assembly is used regardless of its presence in the runtime package store on the host.</span></span>

<span data-ttu-id="0514c-168">Wersja zależności wskazane w manifeście musi być zgodna wersja zależności w magazynie pakietów środowiska wykonawczego.</span><span class="sxs-lookup"><span data-stu-id="0514c-168">The version of the dependency indicated in the manifest must match the version of the dependency in the runtime package store.</span></span> <span data-ttu-id="0514c-169">Jeśli masz niezgodność wersji między zależności w manifeście docelowych i wersji, który istnieje w magazynie pakietów środowiska uruchomieniowego i aplikacji nie zawiera wymaganej wersji pakietu w jego wdrażania, aplikacja nie powiedzie się.</span><span class="sxs-lookup"><span data-stu-id="0514c-169">If you have a version mismatch between the dependency in the target manifest and the version that exists in the runtime package store and the app doesn't include the required version of the package in its deployment, the app fails to start.</span></span> <span data-ttu-id="0514c-170">Wyjątek zawiera nazwę manifestu docelowych, wymagane zestawu magazynie pakietów środowiska wykonawczego, która pomaga w rozwiązywaniu problemów niezgodność.</span><span class="sxs-lookup"><span data-stu-id="0514c-170">The exception includes the name of the target manifest that called for the runtime package store assembly, which helps you troubleshoot the mismatch.</span></span>

<span data-ttu-id="0514c-171">Gdy wdrożenie jest *przycięty* przy publikowaniu, określonych wersji manifestu pakietów, należy wskazać zostały wstrzymane z publikowanych danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="0514c-171">When the deployment is *trimmed* on publish, only the specific versions of the manifest packages you indicate are withheld from the published output.</span></span> <span data-ttu-id="0514c-172">Pakiety w wersji wskazane musi być obecny na hoście aplikacji do uruchomienia.</span><span class="sxs-lookup"><span data-stu-id="0514c-172">The packages at the versions indicated must be present on the host for the app to start.</span></span>

## <a name="see-also"></a><span data-ttu-id="0514c-173">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="0514c-173">See also</span></span>
 [<span data-ttu-id="0514c-174">DotNet-publikowania</span><span class="sxs-lookup"><span data-stu-id="0514c-174">dotnet-publish</span></span>](../tools/dotnet-publish.md)  
 [<span data-ttu-id="0514c-175">Magazyn DotNet</span><span class="sxs-lookup"><span data-stu-id="0514c-175">dotnet-store</span></span>](../tools/dotnet-store.md)  
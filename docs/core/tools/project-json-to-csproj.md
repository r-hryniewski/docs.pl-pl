---
title: "Porównanie pliku Project.JSON i csproj - .NET Core"
description: "Zobacz mapowania między elementami pliku project.json i csproj."
keywords: Plik Project.JSON lub csproj, .NET Core, programu MSBuild
author: natemcmaster
ms.author: mairaw
ms.date: 03/13/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 79c50621-a24a-4e64-bbb9-b953113e841c
ms.openlocfilehash: 0f82e82c6a11220e24c85cef19bc131e12c77bf0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="a-mapping-between-projectjson-and-csproj-properties"></a><span data-ttu-id="cbbbf-104">Mapowanie między właściwości pliku project.json i csproj</span><span class="sxs-lookup"><span data-stu-id="cbbbf-104">A mapping between project.json and csproj properties</span></span>

<span data-ttu-id="cbbbf-105">Przez [McMaster alternatywny](https://github.com/natemcmaster)</span><span class="sxs-lookup"><span data-stu-id="cbbbf-105">By [Nate McMaster](https://github.com/natemcmaster)</span></span>

<span data-ttu-id="cbbbf-106">Podczas tworzenia narzędzi platformy .NET Core projektowania ważne zmiany w już obsługiwać *project.json* pliki i zamiast tego Przenieś projektów .NET Core na format programu MSBuild/csproj.</span><span class="sxs-lookup"><span data-stu-id="cbbbf-106">During the development of the .NET Core tooling, an important design change was made to no longer support *project.json* files and instead move the .NET Core projects to the MSBuild/csproj format.</span></span>

<span data-ttu-id="cbbbf-107">W tym artykule przedstawiono sposób ustawienia w *project.json* są reprezentowane w formacie programu MSBuild/csproj, więc można poznać sposoby użycia nowego formatu i zrozumieć ich zmiany wprowadzone przez narzędzia migracji podczas uaktualniania projektu do Najnowsza wersja narzędzi.</span><span class="sxs-lookup"><span data-stu-id="cbbbf-107">This article shows how the settings in *project.json* are represented in the MSBuild/csproj format so you can learn how to use the new format and understand the changes made by the migration tools when you're upgrading your project to the latest version of the tooling.</span></span> 
 
## <a name="the-csproj-format"></a><span data-ttu-id="cbbbf-108">Csproj format</span><span class="sxs-lookup"><span data-stu-id="cbbbf-108">The csproj format</span></span>

<span data-ttu-id="cbbbf-109">Nowy format \*csproj, to format opartych na języku XML.</span><span class="sxs-lookup"><span data-stu-id="cbbbf-109">The new format, \*.csproj, is an XML-based format.</span></span> <span data-ttu-id="cbbbf-110">W poniższym przykładzie pokazano węzeł główny projekt .NET Core za pomocą `Microsoft.NET.Sdk`.</span><span class="sxs-lookup"><span data-stu-id="cbbbf-110">The following example shows the root node of a .NET Core project using the `Microsoft.NET.Sdk`.</span></span> <span data-ttu-id="cbbbf-111">Dla projektów sieci web jest używany zestaw SDK `Microsoft.NET.Sdk.Web`.</span><span class="sxs-lookup"><span data-stu-id="cbbbf-111">For web projects, the SDK used is `Microsoft.NET.Sdk.Web`.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
...
</Project>
```

## <a name="common-top-level-properties"></a><span data-ttu-id="cbbbf-112">Wspólne właściwości najwyższego poziomu</span><span class="sxs-lookup"><span data-stu-id="cbbbf-112">Common top-level properties</span></span>

### <a name="name"></a><span data-ttu-id="cbbbf-113">nazwa</span><span class="sxs-lookup"><span data-stu-id="cbbbf-113">name</span></span>
```json
{
  "name": "MyProjectName"
}
```

<span data-ttu-id="cbbbf-114">Nie jest już obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="cbbbf-114">No longer supported.</span></span> <span data-ttu-id="cbbbf-115">W csproj jest to określane za pomocą nazwy pliku projektu, który został zdefiniowany przez nazwę katalogu.</span><span class="sxs-lookup"><span data-stu-id="cbbbf-115">In csproj, this is determined by the project filename, which is defined by the directory name.</span></span> <span data-ttu-id="cbbbf-116">Na przykład `MyProjectName.csproj`.</span><span class="sxs-lookup"><span data-stu-id="cbbbf-116">For example, `MyProjectName.csproj`.</span></span>

<span data-ttu-id="cbbbf-117">Domyślnie, nazwa pliku projektu określa również wartość `<AssemblyName>` i `<PackageId>` właściwości.</span><span class="sxs-lookup"><span data-stu-id="cbbbf-117">By default, the project filename also specifies the value of the `<AssemblyName>` and `<PackageId>` properties.</span></span> 

```xml
<PropertyGroup>
  <AssemblyName>MyProjectName</AssemblyName>
  <PackageId>MyProjectName</PackageId>
</PropertyGroup>
```

<span data-ttu-id="cbbbf-118">`<AssemblyName>` Będzie mieć wartość inną niż `<PackageId>` Jeśli `buildOptions\outputName` właściwość została zdefiniowana w pliku project.json.</span><span class="sxs-lookup"><span data-stu-id="cbbbf-118">The `<AssemblyName>` will have a different value than `<PackageId>` if `buildOptions\outputName` property was defined in project.json.</span></span> <span data-ttu-id="cbbbf-119">Aby uzyskać więcej informacji, zobacz [inne typowe opcje kompilacji](#other-common-build-options).</span><span class="sxs-lookup"><span data-stu-id="cbbbf-119">For more information, see [Other common build options](#other-common-build-options).</span></span>

### <a name="version"></a><span data-ttu-id="cbbbf-120">version</span><span class="sxs-lookup"><span data-stu-id="cbbbf-120">version</span></span>

```json
{
  "version": "1.0.0-alpha-*"
}
```
<span data-ttu-id="cbbbf-121">Użyj `VersionPrefix` i `VersionSuffix` właściwości:</span><span class="sxs-lookup"><span data-stu-id="cbbbf-121">Use the `VersionPrefix` and `VersionSuffix` properties:</span></span>

```xml
<PropertyGroup>
  <VersionPrefix>1.0.0</VersionPrefix>
  <VersionSuffix>alpha</VersionSuffix>
</PropertyGroup>
```

<span data-ttu-id="cbbbf-122">Można również użyć `Version` właściwości, ale mogą zastąpić ustawienia wersji podczas pakowania:</span><span class="sxs-lookup"><span data-stu-id="cbbbf-122">You can also use the `Version` property, but this may override version settings during packaging:</span></span>

```xml
<PropertyGroup>
  <Version>1.0.0-alpha</Version>
</PropertyGroup>
```

### <a name="other-common-root-level-options"></a><span data-ttu-id="cbbbf-123">Inne typowe opcje poziomu głównego</span><span class="sxs-lookup"><span data-stu-id="cbbbf-123">Other common root-level options</span></span>

```json
{
  "authors": [ "Anne", "Bob" ],
  "company": "Contoso",
  "language": "en-US",
  "title": "My library",
  "description": "This is my library.\r\nAnd it's really great!",
  "copyright": "Nugetizer 3000",
  "userSecretsId": "xyz123"
}
```

```xml
<PropertyGroup>
  <Authors>Anne;Bob</Authors>
  <Company>Contoso</Company>
  <NeutralLanguage>en-US</NeutralLanguage>
  <AssemblyTitle>My library</AssemblyTitle>
  <Description>This is my library.
And it's really great!</Description>
  <Copyright>Nugetizer 3000</Copyright>
  <UserSecretsId>xyz123</UserSecretsId>
</PropertyGroup>
```

## <a name="frameworks"></a><span data-ttu-id="cbbbf-124">Struktury</span><span class="sxs-lookup"><span data-stu-id="cbbbf-124">frameworks</span></span>

### <a name="one-target-framework"></a><span data-ttu-id="cbbbf-125">Jeden element docelowy framework</span><span class="sxs-lookup"><span data-stu-id="cbbbf-125">One target framework</span></span>
```json
{
  "frameworks": {
    "netcoreapp1.0": {}
  }
}
```

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp1.0</TargetFramework>
</PropertyGroup>
```

### <a name="multiple-target-frameworks"></a><span data-ttu-id="cbbbf-126">Wiele platform docelowych</span><span class="sxs-lookup"><span data-stu-id="cbbbf-126">Multiple target frameworks</span></span>

```json
{
  "frameworks": {
    "netcoreapp1.0": {},
    "net451": {}
  }
}
```

<span data-ttu-id="cbbbf-127">Użyj `TargetFrameworks` właściwości, aby zdefiniować listę docelowych platform.</span><span class="sxs-lookup"><span data-stu-id="cbbbf-127">Use the `TargetFrameworks` property to define your list of target frameworks.</span></span> <span data-ttu-id="cbbbf-128">Użyj średnika do rozdzielania wielu wartości framework.</span><span class="sxs-lookup"><span data-stu-id="cbbbf-128">Use semi-colon to separate multiple framework values.</span></span> 

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp1.0;net451</TargetFrameworks>
</PropertyGroup>
```

## <a name="dependencies"></a><span data-ttu-id="cbbbf-129">zależności</span><span class="sxs-lookup"><span data-stu-id="cbbbf-129">dependencies</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cbbbf-130">Jeśli zależność jest **projektu** i nie jest pakiet format jest inny.</span><span class="sxs-lookup"><span data-stu-id="cbbbf-130">If the dependency is a **project** and not a package, the format is different.</span></span> <span data-ttu-id="cbbbf-131">Aby uzyskać więcej informacji, zobacz [typ zależności](#dependency-type) sekcji.</span><span class="sxs-lookup"><span data-stu-id="cbbbf-131">For more information, see the [dependency type](#dependency-type) section.</span></span>

### <a name="netstandardlibrary-metapackage"></a><span data-ttu-id="cbbbf-132">NETStandard.Library metapackage</span><span class="sxs-lookup"><span data-stu-id="cbbbf-132">NETStandard.Library metapackage</span></span>

```json
{
  "dependencies": {
    "NETStandard.Library": "1.6.0"
  }
}
```

```xml
<PropertyGroup>
  <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
</PropertyGroup>
```

### <a name="microsoftnetcoreapp-metapackage"></a><span data-ttu-id="cbbbf-133">Microsoft.NETCore.App metapackage</span><span class="sxs-lookup"><span data-stu-id="cbbbf-133">Microsoft.NETCore.App metapackage</span></span>

```json
{
  "dependencies": {
    "Microsoft.NETCore.App": "1.0.0"
  }
}
```

```xml
<PropertyGroup>
  <RuntimeFrameworkVersion>1.0.3</RuntimeFrameworkVersion>
</PropertyGroup>
```

<span data-ttu-id="cbbbf-134">Należy pamiętać, że `<RuntimeFrameworkVersion>` wartość migrowanych projektu jest określana przez wersję zestawu SDK został zainstalowany.</span><span class="sxs-lookup"><span data-stu-id="cbbbf-134">Note that the `<RuntimeFrameworkVersion>` value in the migrated project is determined by the version of the SDK you have installed.</span></span>

### <a name="top-level-dependencies"></a><span data-ttu-id="cbbbf-135">Zależności najwyższego poziomu</span><span class="sxs-lookup"><span data-stu-id="cbbbf-135">Top-level dependencies</span></span>
```json
{
  "dependencies": {
    "Microsoft.AspNetCore": "1.1.0"
  }
}
```

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.AspNetCore" Version="1.1.0" />
</ItemGroup>
```

### <a name="per-framework-dependencies"></a><span data-ttu-id="cbbbf-136">Zależności na framework</span><span class="sxs-lookup"><span data-stu-id="cbbbf-136">Per-framework dependencies</span></span>
```json
{
  "framework": {
    "net451": {
      "dependencies": {
        "System.Collections.Immutable": "1.3.1"
      }
    },
    "netstandard1.5": {
      "dependencies": {
        "Newtonsoft.Json": "9.0.1"
      }
    }
  }
}
```

```xml
<ItemGroup Condition="'$(TargetFramework)'=='net451'">
  <PackageReference Include="System.Collections.Immutable" Version="1.3.1" />
</ItemGroup>

<ItemGroup Condition="'$(TargetFramework)'=='netstandard1.5'">
  <PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
</ItemGroup>
```

### <a name="imports"></a><span data-ttu-id="cbbbf-137">importy</span><span class="sxs-lookup"><span data-stu-id="cbbbf-137">imports</span></span>

```json
{
  "dependencies": {
    "YamlDotNet": "4.0.1-pre309"
  },
  "frameworks": {
    "netcoreapp1.0": {
      "imports": [
        "dnxcore50",
        "dotnet"
      ]
    }
  }
}
```

```xml
<PropertyGroup>
  <PackageTargetFallback>dnxcore50;dotnet</PackageTargetFallback>
</PropertyGroup>
<ItemGroup>
  <PackageReference Include="YamlDotNet" Version="4.0.1-pre309" />
</ItemGroup>
```

### <a name="dependency-type"></a><span data-ttu-id="cbbbf-138">Typ zależności</span><span class="sxs-lookup"><span data-stu-id="cbbbf-138">dependency type</span></span>

#### <a name="type-project"></a><span data-ttu-id="cbbbf-139">Typ: Projekt</span><span class="sxs-lookup"><span data-stu-id="cbbbf-139">type: project</span></span>
```json
{
  "dependencies": {
    "MyOtherProject": "1.0.0-*",
    "AnotherProject": {
      "type": "project"
    }
  }
}
```

```xml
<ItemGroup>
  <ProjectReference Include="..\MyOtherProject\MyOtherProject.csproj" />
  <ProjectReference Include="..\AnotherProject\AnotherProject.csproj" />
</ItemGroup>
```

> [!NOTE]
> <span data-ttu-id="cbbbf-140">Spowoduje to przerwanie sposób który `dotnet pack --version-suffix $suffix` Określa wersję zależności odwołania projektu.</span><span class="sxs-lookup"><span data-stu-id="cbbbf-140">This will break the way that `dotnet pack --version-suffix $suffix` determines the dependency version of a project reference.</span></span>


#### <a name="type-build"></a><span data-ttu-id="cbbbf-141">Typ: kompilacji</span><span class="sxs-lookup"><span data-stu-id="cbbbf-141">type: build</span></span>
```json
{
  "dependencies": {
    "Microsoft.EntityFrameworkCore.Design": {
      "version": "1.1.0",
      "type": "build"
    }
  }
}
```

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.EntityFrameworkCore.Design" Version="1.1.0" PrivateAssets="All" />
</ItemGroup>
```

#### <a name="type-platform"></a><span data-ttu-id="cbbbf-142">Typ: platforma</span><span class="sxs-lookup"><span data-stu-id="cbbbf-142">type: platform</span></span>
```json
{
  "dependencies": {
    "Microsoft.NETCore.App": {
      "version": "1.1.0",
      "type": "platform"
    }
  }
}
```

<span data-ttu-id="cbbbf-143">Nie ma odpowiednika w csproj.</span><span class="sxs-lookup"><span data-stu-id="cbbbf-143">There is no equivalent in csproj.</span></span> 

## <a name="runtimes"></a><span data-ttu-id="cbbbf-144">środowisk uruchomieniowych</span><span class="sxs-lookup"><span data-stu-id="cbbbf-144">runtimes</span></span>
```json
{
  "runtimes": {
    "win7-x64": {},
    "osx.10.11-x64": {},
    "ubuntu.16.04-x64": {}
  }
}
```

```xml
<PropertyGroup>
  <RuntimeIdentifiers>win7-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
</PropertyGroup>
```

### <a name="standalone-apps-self-contained-deployment"></a><span data-ttu-id="cbbbf-145">Aplikacje autonomiczne (wdrożenie niezależne)</span><span class="sxs-lookup"><span data-stu-id="cbbbf-145">Standalone apps (self-contained deployment)</span></span>
<span data-ttu-id="cbbbf-146">W pliku project.json definiowanie `runtimes` oznacza, że sekcja aplikacja była autonomiczny podczas tworzenia i publikowania.</span><span class="sxs-lookup"><span data-stu-id="cbbbf-146">In project.json, defining a `runtimes` section means the app was standalone during build and publish.</span></span>
<span data-ttu-id="cbbbf-147">W programie MSBuild, wszystkie projekty są *przenośne* podczas kompilacji, ale mogą być publikowane jako autonomiczny.</span><span class="sxs-lookup"><span data-stu-id="cbbbf-147">In MSBuild, all projects are *portable* during build, but can be published as standalone.</span></span>

`dotnet publish --framework netcoreapp1.0 --runtime osx.10.11-x64`

<span data-ttu-id="cbbbf-148">Aby uzyskać więcej informacji, zobacz [niezależne wdrożeń (SCD)](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="cbbbf-148">For more information, see [Self-contained deployments (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span>

## <a name="tools"></a><span data-ttu-id="cbbbf-149">narzędzia</span><span class="sxs-lookup"><span data-stu-id="cbbbf-149">tools</span></span>
```json
{
  "tools": {
    "Microsoft.EntityFrameworkCore.Tools.DotNet": "1.0.0-*"
  }
}
```

```xml
<ItemGroup>
  <DotNetCliToolReference Include="Microsoft.EntityFrameworkCore.Tools.DotNet" Version="1.0.0" />
</ItemGroup>
```

> [!NOTE]
> <span data-ttu-id="cbbbf-150">`imports`narzędzia nie są obsługiwane w csproj.</span><span class="sxs-lookup"><span data-stu-id="cbbbf-150">`imports` on tools are not supported in csproj.</span></span> <span data-ttu-id="cbbbf-151">Narzędzia, które wymagają importów nie będzie działać z nowym `Microsoft.NET.Sdk`.</span><span class="sxs-lookup"><span data-stu-id="cbbbf-151">Tools that need imports will not work with the new `Microsoft.NET.Sdk`.</span></span>

## <a name="buildoptions"></a><span data-ttu-id="cbbbf-152">buildOptions</span><span class="sxs-lookup"><span data-stu-id="cbbbf-152">buildOptions</span></span>

<span data-ttu-id="cbbbf-153">Zobacz też [pliki](#files).</span><span class="sxs-lookup"><span data-stu-id="cbbbf-153">See also [Files](#files).</span></span>

### <a name="emitentrypoint"></a><span data-ttu-id="cbbbf-154">emitEntryPoint</span><span class="sxs-lookup"><span data-stu-id="cbbbf-154">emitEntryPoint</span></span>

```json
{
  "buildOptions": {
    "emitEntryPoint": true
  }
}
```

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="cbbbf-155">Jeśli `emitEntryPoint` został `false`, wartość `OutputType` jest konwertowana na `Library`, która jest wartość domyślna:</span><span class="sxs-lookup"><span data-stu-id="cbbbf-155">If `emitEntryPoint` was `false`, the value of `OutputType` is converted to `Library`, which is the default value:</span></span>

```json
{
  "buildOptions": {
    "emitEntryPoint": false
  }
}
```

```xml
<PropertyGroup>
  <OutputType>Library</OutputType>
  <!-- or, omit altogether. It defaults to 'Library' -->
</PropertyGroup>
```

### <a name="keyfile"></a><span data-ttu-id="cbbbf-156">Plik klucza</span><span class="sxs-lookup"><span data-stu-id="cbbbf-156">keyFile</span></span>

```json
{
  "buildOptions": {
    "keyFile": "MyKey.snk"
  }
}
```

<span data-ttu-id="cbbbf-157">`keyFile` Element rozwijany do trzech właściwości w programie MSBuild:</span><span class="sxs-lookup"><span data-stu-id="cbbbf-157">The `keyFile` element expands to three properties in MSBuild:</span></span>

```xml
<PropertyGroup>
  <AssemblyOriginatorKeyFile>MyKey.snk</AssemblyOriginatorKeyFile>
  <SignAssembly>true</SignAssembly>
  <PublicSign Condition="'$(OS)' != 'Windows_NT'">true</PublicSign>
</PropertyGroup>
```

### <a name="other-common-build-options"></a><span data-ttu-id="cbbbf-158">Inne typowe opcje kompilacji</span><span class="sxs-lookup"><span data-stu-id="cbbbf-158">Other common build options</span></span>

```json
{
  "buildOptions": {
    "warningsAsErrors": true,
    "nowarn": ["CS0168", "CS0219"],
    "xmlDoc": true,
    "preserveCompilationContext": true,
    "outputName": "Different.AssemblyName",
    "debugType": "portable",
    "allowUnsafe": true,
    "define": ["TEST", "OTHERCONDITION"]
  }
}
```

```xml
<PropertyGroup>
  <TreatWarningsAsErrors>true</TreatWarningsAsErrors>
  <NoWarn>$(NoWarn);CS0168;CS0219</NoWarn>
  <GenerateDocumentationFile>true</GenerateDocumentationFile>
  <PreserveCompilationContext>true</PreserveCompilationContext>
  <AssemblyName>Different.AssemblyName</AssemblyName>
  <DebugType>portable</DebugType>
  <AllowUnsafeBlocks>true</AllowUnsafeBlocks>
  <DefineConstants>$(DefineConstants);TEST;OTHERCONDITION</DefineConstants>
</PropertyGroup>
```

## <a name="packoptions"></a><span data-ttu-id="cbbbf-159">packOptions</span><span class="sxs-lookup"><span data-stu-id="cbbbf-159">packOptions</span></span>

<span data-ttu-id="cbbbf-160">Zobacz też [pliki](#files).</span><span class="sxs-lookup"><span data-stu-id="cbbbf-160">See also [Files](#files).</span></span>

### <a name="common-pack-options"></a><span data-ttu-id="cbbbf-161">Typowe opcje pakietu</span><span class="sxs-lookup"><span data-stu-id="cbbbf-161">Common pack options</span></span>

```json
{
  "packOptions": {    
    "summary": "numl is a machine learning library intended to ease the use of using standard modeling techniques for both prediction and clustering.",
    "tags": ["machine learning", "framework"],
    "releaseNotes": "Version 0.9.12-beta",
    "iconUrl": "http://numl.net/images/ico.png",
    "projectUrl": "http://numl.net",
    "licenseUrl": "https://raw.githubusercontent.com/sethjuarez/numl/master/LICENSE.md",
    "requireLicenseAcceptance": false,
    "repository": {
      "type": "git",
      "url": "https://raw.githubusercontent.com/sethjuarez/numl"
    },
    "owners": ["Seth Juarez"]
  }
}
```

```xml
<PropertyGroup>
  <!-- summary is not migrated from project.json, but you can use the <Description> property for that if needed. -->
  <PackageTags>machine learning;framework</PackageTags>
  <PackageReleaseNotes>Version 0.9.12-beta</PackageReleaseNotes>
  <PackageIconUrl>http://numl.net/images/ico.png</PackageIconUrl>
  <PackageProjectUrl>http://numl.net</PackageProjectUrl>
  <PackageLicenseUrl>https://raw.githubusercontent.com/sethjuarez/numl/master/LICENSE.md</PackageLicenseUrl>
  <PackageRequireLicenseAcceptance>false</PackageRequireLicenseAcceptance>
  <RepositoryType>git</RepositoryType>
  <RepositoryUrl>https://raw.githubusercontent.com/sethjuarez/numl</RepositoryUrl>
  <!-- owners is not supported in MSBuild -->
</PropertyGroup>
```

<span data-ttu-id="cbbbf-162">Nie ma odpowiednika dla `owners` elementu w programie MSBuild.</span><span class="sxs-lookup"><span data-stu-id="cbbbf-162">There is no equivalent for the `owners` element in MSBuild.</span></span> <span data-ttu-id="cbbbf-163">Dla `summary`, można użyć programu MSBuild `<Description>` właściwości, nawet jeśli wartość `summary` nie są migrowane automatycznie z tą właściwością, ponieważ tej właściwości jest zamapowany na [ `description` ](#-other-common-root-level-options) elementu.</span><span class="sxs-lookup"><span data-stu-id="cbbbf-163">For `summary`, you can use the MSBuild `<Description>` property, even though the value of `summary` is not migrated automatically to that property, since that property is mapped to the [`description`](#-other-common-root-level-options) element.</span></span>

## <a name="scripts"></a><span data-ttu-id="cbbbf-164">skrypty</span><span class="sxs-lookup"><span data-stu-id="cbbbf-164">scripts</span></span>

```json
{
  "scripts": {
    "precompile": "generateCode.cmd",
    "postpublish": [ "obfuscate.cmd", "removeTempFiles.cmd" ]
  }
}
```

<span data-ttu-id="cbbbf-165">Są w ich odpowiednik w programie MSBuild [cele](/visualstudio/msbuild/msbuild-targets):</span><span class="sxs-lookup"><span data-stu-id="cbbbf-165">Their equivalent in MSBuild are [targets](/visualstudio/msbuild/msbuild-targets):</span></span>

```xml
<Target Name="MyPreCompileTarget" BeforeTargets="Build">
  <Exec Command="generateCode.cmd" />
</Target>

<Target Name="MyPostCompileTarget" AfterTargets="Publish">
  <Exec Command="obfuscate.cmd" />
  <Exec Command="removeTempFiles.cmd" />
</Target>
```


## <a name="runtimeoptions"></a><span data-ttu-id="cbbbf-166">runtimeOptions</span><span class="sxs-lookup"><span data-stu-id="cbbbf-166">runtimeOptions</span></span>

```json
{
  "runtimeOptions": {
    "configProperties": {
      "System.GC.Server": true,
      "System.GC.Concurrent": true,
      "System.GC.RetainVM": true,
      "System.Threading.ThreadPool.MinThreads": 4,
      "System.Threading.ThreadPool.MaxThreads": 25
    }
  }
}
```

<span data-ttu-id="cbbbf-167">Wszystkie ustawienia w tej grupie, z wyjątkiem właściwości "System.GC.Server" są umieszczane w pliku o nazwie *runtimeconfig.template.json* w folderze projektu z opcjami unosiło do obiektu głównego podczas procesu migracji:</span><span class="sxs-lookup"><span data-stu-id="cbbbf-167">All settings in this group, except for the "System.GC.Server" property, are placed into a file called *runtimeconfig.template.json* in the project folder, with options lifted to the root object during the migration process:</span></span>

```json
{
  "configProperties": {
    "System.GC.Concurrent": true,
    "System.GC.RetainVM": true,
    "System.Threading.ThreadPool.MinThreads": 4,
    "System.Threading.ThreadPool.MaxThreads": 25
  }
}
```

<span data-ttu-id="cbbbf-168">Właściwość "System.GC.Server" jest migrowane w plik csproj:</span><span class="sxs-lookup"><span data-stu-id="cbbbf-168">The "System.GC.Server" property is migrated into the csproj file:</span></span>
```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
</PropertyGroup>
```

<span data-ttu-id="cbbbf-169">Jednak te wartości można ustawić w csproj, jak również właściwości programu MSBuild:</span><span class="sxs-lookup"><span data-stu-id="cbbbf-169">However, you can set all those values in the csproj as well as MSBuild properties:</span></span>
```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
  <ConcurrentGarbageCollection>true</ConcurrentGarbageCollection>
  <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
  <ThreadPoolMaxThreads>25</ThreadPoolMaxThreads>
</PropertyGroup>
```

## <a name="shared"></a><span data-ttu-id="cbbbf-170">udostępnione</span><span class="sxs-lookup"><span data-stu-id="cbbbf-170">shared</span></span>
```json
{
  "shared": "shared/**/*.cs"
}
```

<span data-ttu-id="cbbbf-171">Nieobsługiwane w csproj.</span><span class="sxs-lookup"><span data-stu-id="cbbbf-171">Not supported in csproj.</span></span> <span data-ttu-id="cbbbf-172">Zamiast tego należy utworzyć dołączać pliki zawartości w Twojej *.nuspec* pliku.</span><span class="sxs-lookup"><span data-stu-id="cbbbf-172">You must instead create include content files in your *.nuspec* file.</span></span> <span data-ttu-id="cbbbf-173">Aby uzyskać więcej informacji, zobacz [plików zawartości w tym](/nuget/schema/nuspec#including-content-files).</span><span class="sxs-lookup"><span data-stu-id="cbbbf-173">For more information, see [Including content files](/nuget/schema/nuspec#including-content-files).</span></span>

## <a name="files"></a><span data-ttu-id="cbbbf-174">— pliki</span><span class="sxs-lookup"><span data-stu-id="cbbbf-174">files</span></span>

<span data-ttu-id="cbbbf-175">W *project.json*, kompilacji i dodatkiem Service pack, może zostać rozszerzony do kompilacji i osadzone w różnych folderach.</span><span class="sxs-lookup"><span data-stu-id="cbbbf-175">In *project.json*, build and pack could be extended to compile and embed from different folders.</span></span>
<span data-ttu-id="cbbbf-176">W programie MSBuild, odbywa się przy użyciu [elementów](/visualstudio/msbuild/common-msbuild-project-items).</span><span class="sxs-lookup"><span data-stu-id="cbbbf-176">In MSBuild, this is done using [items](/visualstudio/msbuild/common-msbuild-project-items).</span></span> <span data-ttu-id="cbbbf-177">Poniższy przykład jest typowych konwersji:</span><span class="sxs-lookup"><span data-stu-id="cbbbf-177">The following example is a common conversion:</span></span>

```json
{
  "buildOptions": {
    "compile": {
      "copyToOutput": "notes.txt",
      "include": "../Shared/*.cs",
      "exclude": "../Shared/Not/*.cs"
    },
    "embed": {
      "include": "../Shared/*.resx"
    }
  },
  "packOptions": {
    "include": "Views/",
    "mappings": {
      "some/path/in/project.txt": "in/package.txt"
    }
  },
  "publishOptions": {
    "include": [
      "files/",
      "publishnotes.txt"
    ]
  }
}
```

```xml
<ItemGroup>
  <Compile Include="..\Shared\*.cs" Exclude="..\Shared\Not\*.cs" />
  <EmbeddedResource Include="..\Shared\*.resx" />
  <Content Include="Views\**\*" PackagePath="%(Identity)" />
  <None Include="some/path/in/project.txt" Pack="true" PackagePath="in/package.txt" />
  
  <None Include="notes.txt" CopyToOutputDirectory="Always" />
  <!-- CopyToOutputDirectory = { Always, PreserveNewest, Never } -->

  <Content Include="files\**\*" CopyToPublishDirectory="PreserveNewest" />
  <None Include="publishnotes.txt" CopyToPublishDirectory="Always" />
  <!-- CopyToPublishDirectory = { Always, PreserveNewest, Never } -->
</ItemGroup>
```

> [!NOTE]
> <span data-ttu-id="cbbbf-178">Wiele domyślnych [wzorce globbing](https://en.wikipedia.org/wiki/Glob_(programming)) są automatycznie dodawane przez zestaw SDK .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cbbbf-178">Many of the default [globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are added automatically by the .NET Core SDK.</span></span>
> <span data-ttu-id="cbbbf-179">Aby uzyskać więcej informacji, zobacz [domyślne wartości elementu skompilować](https://aka.ms/sdkimplicititems).</span><span class="sxs-lookup"><span data-stu-id="cbbbf-179">For more information, see [Default Compile Item Values](https://aka.ms/sdkimplicititems).</span></span>

<span data-ttu-id="cbbbf-180">Wszystkie MSBuild `ItemGroup` elementy obsługują `Include`, `Exclude`, i `Remove`.</span><span class="sxs-lookup"><span data-stu-id="cbbbf-180">All MSBuild `ItemGroup` elements support `Include`, `Exclude`, and `Remove`.</span></span>

<span data-ttu-id="cbbbf-181">Układ pakietu wewnątrz .nupkg można modyfikować przy `PackagePath="path"`.</span><span class="sxs-lookup"><span data-stu-id="cbbbf-181">Package layout inside the .nupkg can be modified with `PackagePath="path"`.</span></span>

<span data-ttu-id="cbbbf-182">Z wyjątkiem `Content`, większość grup elementów wymagają jawnie Dodawanie `Pack="true"` do uwzględnienia w pakiecie.</span><span class="sxs-lookup"><span data-stu-id="cbbbf-182">Except for `Content`, most item groups require explicitly adding `Pack="true"` to be included in the package.</span></span> <span data-ttu-id="cbbbf-183">`Content`będą umieszczane w *zawartości* folderu w pakiecie, ponieważ program MSBuild `<IncludeContentInPack>` właściwość jest ustawiona na `true` domyślnie.</span><span class="sxs-lookup"><span data-stu-id="cbbbf-183">`Content` will be put in the *content* folder in a package since the MSBuild `<IncludeContentInPack>` property is set to `true` by default.</span></span> <span data-ttu-id="cbbbf-184">Aby uzyskać więcej informacji, zobacz [tym do zawartości w pakiecie](/nuget/schema/msbuild-targets#including-content-in-a-package).</span><span class="sxs-lookup"><span data-stu-id="cbbbf-184">For more information, see [Including content in a package](/nuget/schema/msbuild-targets#including-content-in-a-package).</span></span>

<span data-ttu-id="cbbbf-185">`PackagePath="%(Identity)"`to krótkie sposób ustawienia do ścieżki pliku projektu względna ścieżka pakietu.</span><span class="sxs-lookup"><span data-stu-id="cbbbf-185">`PackagePath="%(Identity)"` is a short way of setting package path to the project-relative file path.</span></span>

## <a name="testrunner"></a><span data-ttu-id="cbbbf-186">testRunner</span><span class="sxs-lookup"><span data-stu-id="cbbbf-186">testRunner</span></span>

### <a name="xunit"></a><span data-ttu-id="cbbbf-187">xUnit</span><span class="sxs-lookup"><span data-stu-id="cbbbf-187">xUnit</span></span>

```json
{
  "testRunner": "xunit",
  "dependencies": {
    "dotnet-test-xunit": "<any>"
  }
}
```

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.0.0-*" />
  <PackageReference Include="xunit" Version="2.2.0-*" />
  <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0-*" />
</ItemGroup>
```

### <a name="mstest"></a><span data-ttu-id="cbbbf-188">MSTest</span><span class="sxs-lookup"><span data-stu-id="cbbbf-188">MSTest</span></span>

```json
{
  "testRunner": "mstest",
  "dependencies": {
    "dotnet-test-mstest": "<any>"
  }
}
```

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.0.0-*" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.12-*" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.11-*" />
</ItemGroup>
```

## <a name="see-also"></a><span data-ttu-id="cbbbf-189">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="cbbbf-189">See Also</span></span>

[<span data-ttu-id="cbbbf-190">Ogólne omówienie zmian w interfejsu wiersza polecenia</span><span class="sxs-lookup"><span data-stu-id="cbbbf-190">High-level overview of changes in CLI</span></span>](../tools/cli-msbuild-architecture.md)
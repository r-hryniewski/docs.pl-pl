---
title: IMetaDataAssemblyEmit — Interfejs
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit
helpviewer_keywords:
- IMetaDataAssemblyEmit interface [.NET Framework metadata]
ms.assetid: 34fb03cc-2285-4a45-ac48-ad993b7a921a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bda949db469d4b8629e54c9e5907da23ac7e169b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449380"
---
# <a name="imetadataassemblyemit-interface"></a>IMetaDataAssemblyEmit — Interfejs
Udostępnia metody, które obsługują modelu własny opis używany przez środowisko uruchomieniowe języka wspólnego do rozwiązania i użycie zasobów.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[DefineAssembly, metoda](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md)|Strukturę danych zestaw zawierający metadane dla określonego zestawu i zwraca token skojarzone metadane.|  
|[DefineAssemblyRef, metoda](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)|Tworzy `AssemblyRef` struktury zawierającej metadanych dla zestawu, który odwołuje się ten zestaw i zwraca token skojarzone metadane.|  
|[DefineExportedType, metoda](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)|Tworzy `ExportedType` struktury zawierający metadane dla określonej wyeksportowanego typu i zwraca token skojarzone metadane.|  
|[DefineFile, metoda](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)|Tworzy `File` struktury metadane zawierające metadanych dla zestawu odwołuje się ten zestaw i zwraca token skojarzone metadane.|  
|[DefineManifestResource, metoda](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md)|Tworzy `ManifestResource` struktury metadane zawierające dla określonego zasobu manifestu i zwraca token skojarzone metadane.|  
|[SetAssemblyProps, metoda](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setassemblyprops-method.md)|Modyfikuje określony `Assembly` struktura metadanych.|  
|[SetAssemblyRefProps, metoda](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setassemblyrefprops-method.md)|Modyfikuje określony `AssemblyRef` struktura metadanych.|  
|[SetExportedTypeProps, metoda](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setexportedtypeprops-method.md)|Modyfikuje określony `ExportedType` struktura metadanych.|  
|[SetFileProps, metoda](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setfileprops-method.md)|Modyfikuje określony `File` struktura metadanych.|  
|[SetManifestResourceProps, metoda](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setmanifestresourceprops-method.md)|Modyfikuje określony `ManifestResource` struktura metadanych.|  
  
## <a name="remarks"></a>Uwagi  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** Cor.h  
  
 **Biblioteka:** używany jako zasób w MsCorEE.dll  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz też  
 [Interfejsy metadanych](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [IMetaDataAssemblyImport, interfejs](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)

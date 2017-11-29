---
title: "Kolejność elementów członkowskich danych"
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
helpviewer_keywords: data contracts [WCF], ordering members
ms.assetid: 0658a47d-b6e5-4ae0-ba72-ababc3c6ff33
caps.latest.revision: "17"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 06b311f0ca8e9b0a298cd1d9a5e87ff96d13a787
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="data-member-order"></a><span data-ttu-id="41a88-102">Kolejność elementów członkowskich danych</span><span class="sxs-lookup"><span data-stu-id="41a88-102">Data Member Order</span></span>
<span data-ttu-id="41a88-103">W niektórych aplikacjach warto wiedzieć, kolejność, są wysyłane dane z różnych elementów członkowskich danych lub oczekiwano do odebrania (na przykład kolejności, w którym dane są wyświetlane w serializacji XML).</span><span class="sxs-lookup"><span data-stu-id="41a88-103">In some applications, it is useful to know the order in which data from the various data members is sent or is expected to be received (such as the order in which data appears in the serialized XML).</span></span> <span data-ttu-id="41a88-104">Czasami może być konieczna zmiana tej kolejności.</span><span class="sxs-lookup"><span data-stu-id="41a88-104">Sometimes it may be necessary to change this order.</span></span> <span data-ttu-id="41a88-105">W tym temacie wyjaśniono reguły porządkowania.</span><span class="sxs-lookup"><span data-stu-id="41a88-105">This topic explains the ordering rules.</span></span>  
  
## <a name="basic-rules"></a><span data-ttu-id="41a88-106">Podstawowe zasady</span><span class="sxs-lookup"><span data-stu-id="41a88-106">Basic Rules</span></span>  
 <span data-ttu-id="41a88-107">Podstawowe reguły porządkowania danych obejmują:</span><span class="sxs-lookup"><span data-stu-id="41a88-107">The basic rules for data ordering include:</span></span>  
  
-   <span data-ttu-id="41a88-108">Typ kontraktu danych jest częścią hierarchii dziedziczenia, elementy członkowskie danych z jego typów podstawowych są zawsze pierwszy w kolejności.</span><span class="sxs-lookup"><span data-stu-id="41a88-108">If a data contract type is a part of an inheritance hierarchy, data members of its base types are always first in the order.</span></span>  
  
-   <span data-ttu-id="41a88-109">Następnie w kolejności są bieżącego typu elementy członkowskie danych, które nie mają <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> właściwość <xref:System.Runtime.Serialization.DataMemberAttribute> atrybut, w kolejności alfabetycznej.</span><span class="sxs-lookup"><span data-stu-id="41a88-109">Next in order are the current type’s data members that do not have the <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> property of the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute set, in alphabetical order.</span></span>  
  
-   <span data-ttu-id="41a88-110">Następnie są elementy członkowskie danych, które mają <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> właściwość <xref:System.Runtime.Serialization.DataMemberAttribute> atrybutu.</span><span class="sxs-lookup"><span data-stu-id="41a88-110">Next are any data members that have the <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> property of the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute set.</span></span> <span data-ttu-id="41a88-111">Są one uporządkowane według wartości `Order` właściwości pierwszy, a następnie alfabetycznie, jeśli istnieje więcej niż jeden element członkowski określony `Order` wartość.</span><span class="sxs-lookup"><span data-stu-id="41a88-111">These are ordered by the value of the `Order` property first and then alphabetically if there is more than one member of a certain `Order` value.</span></span> <span data-ttu-id="41a88-112">Kolejność wartości mogą być pominięte.</span><span class="sxs-lookup"><span data-stu-id="41a88-112">Order values may be skipped.</span></span>  
  
 <span data-ttu-id="41a88-113">Alfabetycznie nawiązaniu przez wywołanie metody <xref:System.String.CompareOrdinal%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="41a88-113">Alphabetical order is established by calling the <xref:System.String.CompareOrdinal%2A> method.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="41a88-114">Przykłady</span><span class="sxs-lookup"><span data-stu-id="41a88-114">Examples</span></span>  
 <span data-ttu-id="41a88-115">Rozważmy poniższy kod.</span><span class="sxs-lookup"><span data-stu-id="41a88-115">Consider the following code.</span></span>  
  
 [!code-csharp[C_DataContractNames#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#4)]
 [!code-vb[C_DataContractNames#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#4)]  
  
 <span data-ttu-id="41a88-116">Kod XML, tworzone jest podobny do następującego.</span><span class="sxs-lookup"><span data-stu-id="41a88-116">The XML produced is similar to the following.</span></span>  
  
```xml  
<DerivedType>  
    <!-- Zebra is a base data member, and appears first. -->  
    <zebra/>   
  
    <!-- Cat has no Order, appears alphabetically first. -->  
    <cat/>  
  
   <!-- Dog has no Order, appears alphabetically last. -->  
    <dog/>   
  
    <!-- Bird is the member with the smallest Order value -->  
    <bird/>  
  
    <!-- Albatross has the next Order value, alphabetically first. -->  
    <albatross/>  
  
    <!-- Parrot, with the next Order value, alphabetically last. -->  
     <parrot/>  
  
    <!-- Antelope is the member with the highest Order value. Note that   
    Order=2 is skipped -->  
     <antelope/>   
</DerivedType>  
```  
  
## <a name="see-also"></a><span data-ttu-id="41a88-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="41a88-117">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractAttribute>  
 [<span data-ttu-id="41a88-118">Równoważność kontraktów danych</span><span class="sxs-lookup"><span data-stu-id="41a88-118">Data Contract Equivalence</span></span>](../../../../docs/framework/wcf/feature-details/data-contract-equivalence.md)  
 [<span data-ttu-id="41a88-119">Używanie kontraktów danych</span><span class="sxs-lookup"><span data-stu-id="41a88-119">Using Data Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)
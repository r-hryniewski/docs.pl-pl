---
title: Zabezpieczenia zachowania
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19710ae3-f197-4d28-ba9d-52e465006819
caps.latest.revision: "5"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 9182c95b9770cac94b2a747e277fcd0cc02b387f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="behavior-security"></a><span data-ttu-id="3079a-102">Zabezpieczenia zachowania</span><span class="sxs-lookup"><span data-stu-id="3079a-102">Behavior Security</span></span>
<span data-ttu-id="3079a-103">Ta sekcja zawiera przykłady ilustrujące konfigurowania zabezpieczeń dla zachowania usługi.</span><span class="sxs-lookup"><span data-stu-id="3079a-103">This section includes samples that demonstrate configuring security for service behaviors.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3079a-104">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="3079a-104">In This Section</span></span>  
 [<span data-ttu-id="3079a-105">Zachowanie inspekcji usługi</span><span class="sxs-lookup"><span data-stu-id="3079a-105">Service Auditing Behavior</span></span>](../../../../docs/framework/wcf/samples/service-auditing-behavior.md)  
 <span data-ttu-id="3079a-106">W tym przykładzie przedstawiono sposób użycia <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> Aby włączyć inspekcję zdarzeń zabezpieczenia podczas operacji usługi.</span><span class="sxs-lookup"><span data-stu-id="3079a-106">This sample demonstrates how to use the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> to enable auditing of security events during service operations.</span></span>  
  
 [<span data-ttu-id="3079a-107">Dostawca członkostwa i ról</span><span class="sxs-lookup"><span data-stu-id="3079a-107">Membership and Role Provider</span></span>](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)  
 <span data-ttu-id="3079a-108">W tym przykładzie pokazano, jak używać usługi [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] dostawców członkostwa i ról w celu uwierzytelniania i autoryzacji klientów.</span><span class="sxs-lookup"><span data-stu-id="3079a-108">This sample demonstrates how a service can use the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership and role providers to authenticate and authorize clients.</span></span>  
  
 [<span data-ttu-id="3079a-109">Autoryzowanie dostępu do operacji usługi</span><span class="sxs-lookup"><span data-stu-id="3079a-109">Authorizing Access to Service Operations</span></span>](../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)  
 <span data-ttu-id="3079a-110">W tym przykładzie przedstawiono sposób użycia [ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) umożliwia korzystanie z <xref:System.Security.Permissions.PrincipalPermissionAttribute> atrybut do autoryzowania dostępu do operacji usługi.</span><span class="sxs-lookup"><span data-stu-id="3079a-110">This sample demonstrates how to use the [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) to enable use of the <xref:System.Security.Permissions.PrincipalPermissionAttribute> attribute to authorize access to service operations.</span></span>  
  
 [<span data-ttu-id="3079a-111">Personifikowanie klienta</span><span class="sxs-lookup"><span data-stu-id="3079a-111">Impersonating the Client</span></span>](../../../../docs/framework/wcf/samples/impersonating-the-client.md)  
 <span data-ttu-id="3079a-112">W tym przykładzie pokazano, jak dokonać personifikacji aplikacji obiektu wywołującego w usłudze, aby usługa może uzyskiwać dostęp do zasobów systemu imieniu wywołującego.</span><span class="sxs-lookup"><span data-stu-id="3079a-112">This sample demonstrates how to impersonate the caller application at the service so that the service can access system resources on behalf of the caller.</span></span>
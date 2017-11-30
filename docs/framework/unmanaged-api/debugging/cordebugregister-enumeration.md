---
title: "CorDebugRegister — Wyliczenie"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugRegister
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugRegister
helpviewer_keywords: CorDebugRegister enumeration [.NET Framework debugging]
ms.assetid: 003bb138-7960-4291-ac88-0d87e470ff70
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: aa9cbd0feaddf5c091bd1f724860cddbd5b11054
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugregister-enumeration"></a><span data-ttu-id="b4a04-102">CorDebugRegister — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="b4a04-102">CorDebugRegister Enumeration</span></span>
<span data-ttu-id="b4a04-103">Określa, rejestruje skojarzony z danym procesor.</span><span class="sxs-lookup"><span data-stu-id="b4a04-103">Specifies the registers associated with a given processor architecture.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4a04-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="b4a04-104">Syntax</span></span>  
  
```  
typedef enum CorDebugRegister {  
  
    REGISTER_INSTRUCTION_POINTER = 0,  
    REGISTER_STACK_POINTER,  
    REGISTER_FRAME_POINTER,  
  
    REGISTER_X86_EIP = 0,  
    REGISTER_X86_ESP,  
    REGISTER_X86_EBP,  
  
    REGISTER_X86_EAX,  
    REGISTER_X86_ECX,  
    REGISTER_X86_EDX,  
    REGISTER_X86_EBX,  
  
    REGISTER_X86_ESI,  
    REGISTER_X86_EDI,  
  
    REGISTER_X86_FPSTACK_0,  
    REGISTER_X86_FPSTACK_1,  
    REGISTER_X86_FPSTACK_2,  
    REGISTER_X86_FPSTACK_3,  
    REGISTER_X86_FPSTACK_4,  
    REGISTER_X86_FPSTACK_5,  
    REGISTER_X86_FPSTACK_6,  
    REGISTER_X86_FPSTACK_7,  
  
    REGISTER_AMD64_RIP = 0,  
    REGISTER_AMD64_RSP,  
    REGISTER_AMD64_RBP,  
    REGISTER_AMD64_RAX,  
    REGISTER_AMD64_RCX,  
    REGISTER_AMD64_RDX,  
    REGISTER_AMD64_RBX,  
    REGISTER_AMD64_RSI,  
    REGISTER_AMD64_RDI,  
    REGISTER_AMD64_R8,  
    REGISTER_AMD64_R9,  
    REGISTER_AMD64_R10,  
    REGISTER_AMD64_R11,  
    REGISTER_AMD64_R12,  
    REGISTER_AMD64_R13,  
    REGISTER_AMD64_R14,  
    REGISTER_AMD64_R15,  
  
    REGISTER_AMD64_XMM0,  
    REGISTER_AMD64_XMM1,  
    REGISTER_AMD64_XMM2,  
    REGISTER_AMD64_XMM3,  
    REGISTER_AMD64_XMM4,  
    REGISTER_AMD64_XMM5,  
    REGISTER_AMD64_XMM6,  
    REGISTER_AMD64_XMM7,  
    REGISTER_AMD64_XMM8,  
    REGISTER_AMD64_XMM9,  
    REGISTER_AMD64_XMM10,  
    REGISTER_AMD64_XMM11,  
    REGISTER_AMD64_XMM12,  
    REGISTER_AMD64_XMM13,  
    REGISTER_AMD64_XMM14,  
    REGISTER_AMD64_XMM15,  
  
    REGISTER_IA64_BSP = REGISTER_FRAME_POINTER,  
    REGISTER_IA64_R0  = REGISTER_IA64_BSP + 1,  
    REGISTER_IA64_F0  = REGISTER_IA64_R0  + 128,  
    REGISTER_ARM_PC = 0,  
    REGISTER_ARM_SP,  
    REGISTER_ARM_R0,  
    REGISTER_ARM_R1,  
    REGISTER_ARM_R2,  
    REGISTER_ARM_R3,  
    REGISTER_ARM_R4,  
    REGISTER_ARM_R5,  
    REGISTER_ARM_R6,  
    REGISTER_ARM_R7,  
    REGISTER_ARM_R8,  
    REGISTER_ARM_R9,  
    REGISTER_ARM_R10,  
    REGISTER_ARM_R11,  
    REGISTER_ARM_R12,  
    REGISTER_ARM_LR,  
  
} CorDebugRegister;  
```  
  
## <a name="members"></a><span data-ttu-id="b4a04-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="b4a04-105">Members</span></span>  
  
|<span data-ttu-id="b4a04-106">Element członkowski</span><span class="sxs-lookup"><span data-stu-id="b4a04-106">Member</span></span>|<span data-ttu-id="b4a04-107">Opis</span><span class="sxs-lookup"><span data-stu-id="b4a04-107">Description</span></span>|  
|------------|-----------------|  
|`REGISTER_INSTRUCTION_POINTER`|<span data-ttu-id="b4a04-108">Wskaźnik instrukcji zarejestrować dowolnego procesora.</span><span class="sxs-lookup"><span data-stu-id="b4a04-108">An instruction pointer register on any processor.</span></span>|  
|`REGISTER_STACK_POINTER`|<span data-ttu-id="b4a04-109">Wskaźnik stosu zarejestrować dowolnego procesora.</span><span class="sxs-lookup"><span data-stu-id="b4a04-109">A stack pointer register on any processor.</span></span>|  
|`REGISTER_FRAME_POINTER`|<span data-ttu-id="b4a04-110">Rejestr wskaźnika ramki za dowolnego procesora.</span><span class="sxs-lookup"><span data-stu-id="b4a04-110">A frame pointer register on any processor.</span></span>|  
|`REGISTER_X86_EIP`|<span data-ttu-id="b4a04-111">Rejestr wskaźnika instrukcji na x86 procesora.</span><span class="sxs-lookup"><span data-stu-id="b4a04-111">The instruction pointer register on the x86 processor.</span></span>|  
|`REGISTER_X86_ESP`|<span data-ttu-id="b4a04-112">Rejestr wskaźnika stosu na x86 procesora.</span><span class="sxs-lookup"><span data-stu-id="b4a04-112">The stack pointer register on the x86 processor.</span></span>|  
|`REGISTER_X86_EBP`|<span data-ttu-id="b4a04-113">Rejestr podstawowego wskaźnika na x86 procesora.</span><span class="sxs-lookup"><span data-stu-id="b4a04-113">The base pointer register on the x86 processor.</span></span>|  
|`REGISTER_X86_EAX`|<span data-ttu-id="b4a04-114">Rejestr danych A na x86 procesora.</span><span class="sxs-lookup"><span data-stu-id="b4a04-114">The A data register on the x86 processor.</span></span>|  
|`REGISTER_X86_ECX`|<span data-ttu-id="b4a04-115">Rejestr danych C na x86 procesora.</span><span class="sxs-lookup"><span data-stu-id="b4a04-115">The C data register on the x86 processor.</span></span>|  
|`REGISTER_X86_EDX`|<span data-ttu-id="b4a04-116">Rejestr danych D na x86 procesora.</span><span class="sxs-lookup"><span data-stu-id="b4a04-116">The D data register on the x86 processor.</span></span>|  
|`REGISTER_X86_EBX`|<span data-ttu-id="b4a04-117">Rejestr danych B na x86 procesora.</span><span class="sxs-lookup"><span data-stu-id="b4a04-117">The B data register on the x86 processor.</span></span>|  
|`REGISTER_X86_ESI`|<span data-ttu-id="b4a04-118">Źródło indeks rejestru w x86 procesora.</span><span class="sxs-lookup"><span data-stu-id="b4a04-118">The source index register on the x86 processor.</span></span>|  
|`REGISTER_X86_EDI`|<span data-ttu-id="b4a04-119">Rejestr indeksu docelowego na x86 procesora.</span><span class="sxs-lookup"><span data-stu-id="b4a04-119">The destination index register on the x86 processor.</span></span>|  
|`REGISTER_X86_FPSTACK_0`|<span data-ttu-id="b4a04-120">Procesor rejestru 0 na x86 liczb zmiennoprzecinkowych (FP) stosu.</span><span class="sxs-lookup"><span data-stu-id="b4a04-120">The stack register 0 on the x86 floating-point (FP) processor.</span></span>|  
|`REGISTER_X86_FPSTACK_1`|<span data-ttu-id="b4a04-121">Stos #1 zarejestrować x86 FP procesora.</span><span class="sxs-lookup"><span data-stu-id="b4a04-121">The #1 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_2`|<span data-ttu-id="b4a04-122">Stos #2 zarejestrować x86 FP procesora.</span><span class="sxs-lookup"><span data-stu-id="b4a04-122">The #2 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_3`|<span data-ttu-id="b4a04-123">Stos #3 zarejestrować x86 FP procesora.</span><span class="sxs-lookup"><span data-stu-id="b4a04-123">The #3 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_4`|<span data-ttu-id="b4a04-124">Stos #4 zarejestrować x86 FP procesora.</span><span class="sxs-lookup"><span data-stu-id="b4a04-124">The #4 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_5`|<span data-ttu-id="b4a04-125">Stos #5 zarejestrować x86 FP procesora.</span><span class="sxs-lookup"><span data-stu-id="b4a04-125">The #5 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_6`|<span data-ttu-id="b4a04-126">Stos #6 zarejestrować x86 FP procesora.</span><span class="sxs-lookup"><span data-stu-id="b4a04-126">The #6 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_7`|<span data-ttu-id="b4a04-127">Stos #7 zarejestrować x86 FP procesora.</span><span class="sxs-lookup"><span data-stu-id="b4a04-127">The #7 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_AMD64_RIP`|<span data-ttu-id="b4a04-128">Wskaźnik instrukcji zarejestrować na procesorem AMD64.</span><span class="sxs-lookup"><span data-stu-id="b4a04-128">The instruction pointer register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RSP`|<span data-ttu-id="b4a04-129">Wskaźnik stosu zarejestrować na procesorem AMD64.</span><span class="sxs-lookup"><span data-stu-id="b4a04-129">The stack pointer register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RBP`|<span data-ttu-id="b4a04-130">Rejestr podstawowego wskaźnika na procesorem AMD64.</span><span class="sxs-lookup"><span data-stu-id="b4a04-130">The base pointer register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RAX`|<span data-ttu-id="b4a04-131">Rejestr danych A na procesorem AMD64.</span><span class="sxs-lookup"><span data-stu-id="b4a04-131">The A data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RCX`|<span data-ttu-id="b4a04-132">Zarejestruj dane C na procesorem AMD64.</span><span class="sxs-lookup"><span data-stu-id="b4a04-132">The C data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RDX`|<span data-ttu-id="b4a04-133">Zarejestruj dane D na procesorem AMD64.</span><span class="sxs-lookup"><span data-stu-id="b4a04-133">The D data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RBX`|<span data-ttu-id="b4a04-134">Zarejestruj dane B na procesorem AMD64.</span><span class="sxs-lookup"><span data-stu-id="b4a04-134">The B data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RSI`|<span data-ttu-id="b4a04-135">Indeks źródła zarejestrować na procesorem AMD64.</span><span class="sxs-lookup"><span data-stu-id="b4a04-135">The source index register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RDI`|<span data-ttu-id="b4a04-136">Indeksu docelowego zarejestrować na procesorem AMD64.</span><span class="sxs-lookup"><span data-stu-id="b4a04-136">The destination index register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R8`|<span data-ttu-id="b4a04-137">Zarejestruj dane #8 na procesorem AMD64.</span><span class="sxs-lookup"><span data-stu-id="b4a04-137">The #8 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R9`|<span data-ttu-id="b4a04-138">Zarejestruj dane #9 na procesorem AMD64.</span><span class="sxs-lookup"><span data-stu-id="b4a04-138">The #9 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R10`|<span data-ttu-id="b4a04-139">Zarejestruj dane #10 na procesorem AMD64.</span><span class="sxs-lookup"><span data-stu-id="b4a04-139">The #10 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R11`|<span data-ttu-id="b4a04-140">Zarejestruj dane #11 na procesorem AMD64.</span><span class="sxs-lookup"><span data-stu-id="b4a04-140">The #11 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R12`|<span data-ttu-id="b4a04-141">Zarejestruj dane #12 na procesorem AMD64.</span><span class="sxs-lookup"><span data-stu-id="b4a04-141">The #12 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R13`|<span data-ttu-id="b4a04-142">Zarejestruj dane #13 na procesorem AMD64.</span><span class="sxs-lookup"><span data-stu-id="b4a04-142">The #13 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R14`|<span data-ttu-id="b4a04-143">Zarejestruj dane #14 na procesorem AMD64.</span><span class="sxs-lookup"><span data-stu-id="b4a04-143">The #14 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R15`|<span data-ttu-id="b4a04-144">Zarejestruj dane #15 na procesorem AMD64.</span><span class="sxs-lookup"><span data-stu-id="b4a04-144">The #15 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM0`|<span data-ttu-id="b4a04-145">Zarejestruj #0 multimediów na procesorem AMD64.</span><span class="sxs-lookup"><span data-stu-id="b4a04-145">The #0 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM1`|<span data-ttu-id="b4a04-146">Zarejestruj #1 multimedialnych na procesorem AMD64.</span><span class="sxs-lookup"><span data-stu-id="b4a04-146">The #1 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM2`|<span data-ttu-id="b4a04-147">Zarejestruj #2 multimedialnych na procesorem AMD64.</span><span class="sxs-lookup"><span data-stu-id="b4a04-147">The #2 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM3`|<span data-ttu-id="b4a04-148">Zarejestruj #3 multimedialnych na procesorem AMD64.</span><span class="sxs-lookup"><span data-stu-id="b4a04-148">The #3 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM4`|<span data-ttu-id="b4a04-149">Zarejestruj #4 multimedialnych na procesorem AMD64.</span><span class="sxs-lookup"><span data-stu-id="b4a04-149">The #4 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM5`|<span data-ttu-id="b4a04-150">Zarejestruj #5 multimedialnych na procesorem AMD64.</span><span class="sxs-lookup"><span data-stu-id="b4a04-150">The #5 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM6`|<span data-ttu-id="b4a04-151">Zarejestruj #6 multimedialnych na procesorem AMD64.</span><span class="sxs-lookup"><span data-stu-id="b4a04-151">The #6 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM7`|<span data-ttu-id="b4a04-152">Zarejestruj #7 multimedialnych na procesorem AMD64.</span><span class="sxs-lookup"><span data-stu-id="b4a04-152">The #7 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM8`|<span data-ttu-id="b4a04-153">Zarejestruj #8 multimedialnych na procesorem AMD64.</span><span class="sxs-lookup"><span data-stu-id="b4a04-153">The #8 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM9`|<span data-ttu-id="b4a04-154">Zarejestruj #9 multimedialnych na procesorem AMD64.</span><span class="sxs-lookup"><span data-stu-id="b4a04-154">The #9 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM10`|<span data-ttu-id="b4a04-155">Zarejestruj #10 multimedialnych na procesorem AMD64.</span><span class="sxs-lookup"><span data-stu-id="b4a04-155">The #10 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM11`|<span data-ttu-id="b4a04-156">Zarejestruj #11 multimedialnych na procesorem AMD64.</span><span class="sxs-lookup"><span data-stu-id="b4a04-156">The #11 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM12`|<span data-ttu-id="b4a04-157">Zarejestruj #12 multimedialnych na procesorem AMD64.</span><span class="sxs-lookup"><span data-stu-id="b4a04-157">The #12 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM13`|<span data-ttu-id="b4a04-158">Zarejestruj #13 multimedialnych na procesorem AMD64.</span><span class="sxs-lookup"><span data-stu-id="b4a04-158">The #13 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM14`|<span data-ttu-id="b4a04-159">Zarejestruj #14 multimedialnych na procesorem AMD64.</span><span class="sxs-lookup"><span data-stu-id="b4a04-159">The #14 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM15`|<span data-ttu-id="b4a04-160">Zarejestruj #15 multimedialnych na procesorem AMD64.</span><span class="sxs-lookup"><span data-stu-id="b4a04-160">The #15 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_IA64_BSP`|<span data-ttu-id="b4a04-161">Wskaźnik stosu zarejestrować w procesorze IA-64.</span><span class="sxs-lookup"><span data-stu-id="b4a04-161">The stack pointer register on the IA-64 processor.</span></span>|  
|`REGISTER_IA64_R0`|<span data-ttu-id="b4a04-162">Zarejestruj dane #0 na procesorze IA-64.</span><span class="sxs-lookup"><span data-stu-id="b4a04-162">The #0 data register on the IA-64 processor.</span></span>|  
|`REGISTER_IA64_F0`|<span data-ttu-id="b4a04-163">Zarejestruj dane FP #0 na procesorze IA-64.</span><span class="sxs-lookup"><span data-stu-id="b4a04-163">The #0 FP data register on the IA-64 processor.</span></span>|  
|`REGISTER_ARM_PC`|<span data-ttu-id="b4a04-164">Licznik programu Zarejestruj (R15) w procesorze ARM.</span><span class="sxs-lookup"><span data-stu-id="b4a04-164">The program counter register (R15) on the ARM processor.</span></span>|  
|`REGISTER_ARM_SP`|<span data-ttu-id="b4a04-165">Wskaźnik stosu Zarejestruj (R13) w procesorze ARM.</span><span class="sxs-lookup"><span data-stu-id="b4a04-165">The stack pointer register (R13) on the ARM processor.</span></span>|  
|`REGISTER_ARM_R0`|<span data-ttu-id="b4a04-166">Dane rejestru R0 na procesor ARM.</span><span class="sxs-lookup"><span data-stu-id="b4a04-166">Data register R0 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R1`|<span data-ttu-id="b4a04-167">Dane rejestru R1 na procesor ARM.</span><span class="sxs-lookup"><span data-stu-id="b4a04-167">Data register R1 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R2`|<span data-ttu-id="b4a04-168">Dane rejestru R2 na procesor ARM.</span><span class="sxs-lookup"><span data-stu-id="b4a04-168">Data register R2 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R3`|<span data-ttu-id="b4a04-169">Dane rejestru R3 na procesor ARM.</span><span class="sxs-lookup"><span data-stu-id="b4a04-169">Data register R3 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R4`|<span data-ttu-id="b4a04-170">Zarejestruj R4 na procesor ARM.</span><span class="sxs-lookup"><span data-stu-id="b4a04-170">Register R4 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R5`|<span data-ttu-id="b4a04-171">Zarejestruj R5 na procesor ARM.</span><span class="sxs-lookup"><span data-stu-id="b4a04-171">Register R5 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R6`|<span data-ttu-id="b4a04-172">Zarejestruj R6 na procesor ARM.</span><span class="sxs-lookup"><span data-stu-id="b4a04-172">Register R6 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R7`|<span data-ttu-id="b4a04-173">Zarejestruj R7 (MINIATURA wskaźnika ramki) na procesor ARM.</span><span class="sxs-lookup"><span data-stu-id="b4a04-173">Register R7 (the THUMB frame pointer) on the ARM processor.</span></span>|  
|`REGISTER_ARM_R8`|<span data-ttu-id="b4a04-174">Zarejestruj R8 na procesor ARM.</span><span class="sxs-lookup"><span data-stu-id="b4a04-174">Register R8 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R9`|<span data-ttu-id="b4a04-175">Zarejestruj R9 na procesor ARM.</span><span class="sxs-lookup"><span data-stu-id="b4a04-175">Register R9 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R10`|<span data-ttu-id="b4a04-176">Zarejestruj R10 na procesor ARM.</span><span class="sxs-lookup"><span data-stu-id="b4a04-176">Register R10 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R11`|<span data-ttu-id="b4a04-177">Wskaźnik ramki na procesor ARM.</span><span class="sxs-lookup"><span data-stu-id="b4a04-177">The frame pointer on the ARM processor.</span></span>|  
|`REGISTER_ARM_R12`|<span data-ttu-id="b4a04-178">Zarejestruj R12 na procesor ARM.</span><span class="sxs-lookup"><span data-stu-id="b4a04-178">Register R12 on the ARM processor.</span></span>|  
|`REGISTER_ARM_LR`|<span data-ttu-id="b4a04-179">Rejestr łącza (R14) w procesorze ARM.</span><span class="sxs-lookup"><span data-stu-id="b4a04-179">The link register (R14) on the ARM processor.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4a04-180">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b4a04-180">Remarks</span></span>  
 <span data-ttu-id="b4a04-181">Rejestruje 128 danych ogólnego przeznaczenia i 128 rejestrów zmiennoprzecinkowych danych na procesor IA-64, ale tylko wartości `REGISTER_IA64_R0` i `REGISTER_IA64_F0` są udostępniane.</span><span class="sxs-lookup"><span data-stu-id="b4a04-181">There are 128 general-purpose data registers and 128 floating-point data registers on the IA-64 processor, but only values `REGISTER_IA64_R0` and `REGISTER_IA64_F0` are provided.</span></span> <span data-ttu-id="b4a04-182">Inne wartości mogą być określane w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="b4a04-182">The other values can be determined as follows:</span></span>  
  
-   <span data-ttu-id="b4a04-183">Dodaj numer rejestru `REGISTER_IA64_R0` wartości `REGISTER_IA64_R1` za pośrednictwem `REGISTER_IA64_R127`, które odpowiadają rejestru #1 danych za pomocą rejestru #127 danych w procesorze IA-64.</span><span class="sxs-lookup"><span data-stu-id="b4a04-183">Add the register number to `REGISTER_IA64_R0` for values `REGISTER_IA64_R1` through `REGISTER_IA64_R127`, which correspond to the #1 data register through the #127 data register on the IA-64 processor.</span></span>  
  
-   <span data-ttu-id="b4a04-184">Dodaj numer rejestru `REGISTER_IA64_F0` wartości `REGISTER_IA64_F1` za pośrednictwem `REGISTER_IA64_F127`, która odpowiada Rejestr danych FP #1 do #127 rejestr FP danych w procesorze IA-64.</span><span class="sxs-lookup"><span data-stu-id="b4a04-184">Add the register number to `REGISTER_IA64_F0` for values `REGISTER_IA64_F1` through `REGISTER_IA64_F127`, which correspond to the #1 FP data register through the #127 FP data register on the IA-64 processor.</span></span>  
  
 <span data-ttu-id="b4a04-185">Na przykład, jeśli należy określić rejestr #83 danych w procesorze IA-64, użyj `REGISTER_IA64_R0` + 83.</span><span class="sxs-lookup"><span data-stu-id="b4a04-185">For example, if you need to specify the #83 data register on the IA-64 processor, use `REGISTER_IA64_R0` + 83.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4a04-186">Wymagania</span><span class="sxs-lookup"><span data-stu-id="b4a04-186">Requirements</span></span>  
 <span data-ttu-id="b4a04-187">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4a04-187">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4a04-188">**Nagłówek:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b4a04-188">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b4a04-189">**Biblioteka:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4a04-189">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4a04-190">**Wersje programu .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4a04-190">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4a04-191">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b4a04-191">See Also</span></span>  
 [<span data-ttu-id="b4a04-192">Debugowanie — wyliczenia</span><span class="sxs-lookup"><span data-stu-id="b4a04-192">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
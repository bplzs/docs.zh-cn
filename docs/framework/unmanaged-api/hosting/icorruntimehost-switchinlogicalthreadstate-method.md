---
title: "ICorRuntimeHost::SwitchInLogicalThreadState 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.SwitchInLogicalThreadState
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::SwitchInLogicalThreadState
helpviewer_keywords:
- ICorRuntimeHost::SwitchInLogicalThreadState method [.NET Framework hosting]
- SwitchInLogicalThreadState method [.NET Framework hosting]
ms.assetid: 7df1e492-8014-43ea-80d1-a4743e9b1c17
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b17927498c5f9000d6c7c0e32d46f6f87a9c78af
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icorruntimehostswitchinlogicalthreadstate-method"></a><span data-ttu-id="65b4b-102">ICorRuntimeHost::SwitchInLogicalThreadState 方法</span><span class="sxs-lookup"><span data-stu-id="65b4b-102">ICorRuntimeHost::SwitchInLogicalThreadState Method</span></span>
<span data-ttu-id="65b4b-103">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="65b4b-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65b4b-104">语法</span><span class="sxs-lookup"><span data-stu-id="65b4b-104">Syntax</span></span>  
  
```  
HRESULT SwitchInLogicalThreadState(  
    [in] DWORD *pFiberCookie  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="65b4b-105">参数</span><span class="sxs-lookup"><span data-stu-id="65b4b-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="65b4b-106">[in]指示要使用纤程的 cookie。</span><span class="sxs-lookup"><span data-stu-id="65b4b-106">[in] Cookie that indicates the fiber to use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65b4b-107">要求</span><span class="sxs-lookup"><span data-stu-id="65b4b-107">Requirements</span></span>  
 <span data-ttu-id="65b4b-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="65b4b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65b4b-109">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="65b4b-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="65b4b-110">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="65b4b-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="65b4b-111">**.NET framework 版本：** 1.0、 1.1</span><span class="sxs-lookup"><span data-stu-id="65b4b-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65b4b-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="65b4b-112">See Also</span></span>  
 [<span data-ttu-id="65b4b-113">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="65b4b-113">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
---
title: "ICorProfilerInfo::GetCurrentThreadID 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetCurrentThreadID
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetCurrentThreadID
helpviewer_keywords:
- GetCurrentThreadID method, ICorProfilerInfo interface [.NET Framework profiling]
- ICorProfilerInfo::GetCurrentThreadID method [.NET Framework profiling]
ms.assetid: 39bbdb30-6a7a-4202-8da3-67ae9a0ab3a8
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 055a5f56f076cc29ca7ce5d45ecedd650e8f2f44
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfogetcurrentthreadid-method"></a><span data-ttu-id="1aa64-102">ICorProfilerInfo::GetCurrentThreadID 方法</span><span class="sxs-lookup"><span data-stu-id="1aa64-102">ICorProfilerInfo::GetCurrentThreadID Method</span></span>
<span data-ttu-id="1aa64-103">如果它是一个托管的线程，请获取当前线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="1aa64-103">Gets the ID of the current thread, if it is a managed thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1aa64-104">语法</span><span class="sxs-lookup"><span data-stu-id="1aa64-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentThreadID(  
    [out] ThreadID *pThreadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1aa64-105">参数</span><span class="sxs-lookup"><span data-stu-id="1aa64-105">Parameters</span></span>  
 `pThreadId`  
 <span data-ttu-id="1aa64-106">[out]指向托管线程的返回 ID 的指针。</span><span class="sxs-lookup"><span data-stu-id="1aa64-106">[out] A pointer to the returned ID of the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1aa64-107">备注</span><span class="sxs-lookup"><span data-stu-id="1aa64-107">Remarks</span></span>  
 <span data-ttu-id="1aa64-108">如果当前线程在内部运行时线程或其他非托管的线程， `GetCurrentThreadID` HRESULT，并返回的值的形式返回 CORPROF_E_NOT_MANAGED_THREAD`pThreadId`参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="1aa64-108">If the current thread is an internal runtime thread or other unmanaged thread, `GetCurrentThreadID` returns CORPROF_E_NOT_MANAGED_THREAD as the HRESULT, and the returned value of the `pThreadId` parameter will be null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1aa64-109">要求</span><span class="sxs-lookup"><span data-stu-id="1aa64-109">Requirements</span></span>  
 <span data-ttu-id="1aa64-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1aa64-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1aa64-111">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1aa64-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1aa64-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1aa64-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1aa64-113">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1aa64-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1aa64-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1aa64-114">See Also</span></span>  
 [<span data-ttu-id="1aa64-115">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="1aa64-115">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
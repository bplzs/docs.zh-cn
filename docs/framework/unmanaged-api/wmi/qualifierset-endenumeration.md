---
title: "QualifierSet_EndEnumeration 函数 （非托管 API 参考）"
description: "QualifierSet_EndEnumeration 函数将终止枚举。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: QualifierSet_EndEnumeration
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: QualifierSet_EndEnumeration
helpviewer_keywords: QualifierSet_EndEnumeration function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7868a0c0ba5abb880af201ce73b35f5ffed6f223
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2017
---
# <a name="qualifiersetendenumeration-function"></a><span data-ttu-id="6da94-103">QualifierSet_EndEnumeration 函数</span><span class="sxs-lookup"><span data-stu-id="6da94-103">QualifierSet_EndEnumeration function</span></span>
<span data-ttu-id="6da94-104">终止通过调用开始枚举[QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md)函数。</span><span class="sxs-lookup"><span data-stu-id="6da94-104">Terminates the enumeration begun with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="6da94-105">语法</span><span class="sxs-lookup"><span data-stu-id="6da94-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr
); 
```  

## <a name="parameters"></a><span data-ttu-id="6da94-106">参数</span><span class="sxs-lookup"><span data-stu-id="6da94-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="6da94-107">[in]未使用此参数。</span><span class="sxs-lookup"><span data-stu-id="6da94-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="6da94-108">[in]指向的指针[IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx)实例。</span><span class="sxs-lookup"><span data-stu-id="6da94-108">[in] A pointer to an [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="6da94-109">返回值</span><span class="sxs-lookup"><span data-stu-id="6da94-109">Return value</span></span>

<span data-ttu-id="6da94-110">此函数返回以下值用定义*WbemCli.h*标头文件，也可以为常量在中定义你的代码：</span><span class="sxs-lookup"><span data-stu-id="6da94-110">The following value returned by this function is defined in the *WbemCli.h* header file, or you can define it as a constant in your code:</span></span>

|<span data-ttu-id="6da94-111">返回的常量</span><span class="sxs-lookup"><span data-stu-id="6da94-111">Constant</span></span>  |<span data-ttu-id="6da94-112">值</span><span class="sxs-lookup"><span data-stu-id="6da94-112">Value</span></span>  |<span data-ttu-id="6da94-113">描述</span><span class="sxs-lookup"><span data-stu-id="6da94-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | <span data-ttu-id="6da94-114">0</span><span class="sxs-lookup"><span data-stu-id="6da94-114">0</span></span> | <span data-ttu-id="6da94-115">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="6da94-115">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="6da94-116">备注</span><span class="sxs-lookup"><span data-stu-id="6da94-116">Remarks</span></span>

<span data-ttu-id="6da94-117">此函数包装对的调用[IWbemQualifierSet::EndEnumeration](https://msdn.microsoft.com/library/aa391865(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="6da94-117">This function wraps a call to the [IWbemQualifierSet::EndEnumeration](https://msdn.microsoft.com/library/aa391865(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="6da94-118">此调用是建议，但不是要求。</span><span class="sxs-lookup"><span data-stu-id="6da94-118">This call is recommended, but not required.</span></span> <span data-ttu-id="6da94-119">它立即释放枚举与关联的资源。</span><span class="sxs-lookup"><span data-stu-id="6da94-119">It immediately releases resources associated with the enumeration.</span></span>

## <a name="requirements"></a><span data-ttu-id="6da94-120">要求</span><span class="sxs-lookup"><span data-stu-id="6da94-120">Requirements</span></span>  

<span data-ttu-id="6da94-121">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6da94-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="6da94-122">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="6da94-122">**Header:** WMINet_Utils.idl</span></span>  
  
<span data-ttu-id="6da94-123">**.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6da94-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6da94-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="6da94-124">See also</span></span>  
[<span data-ttu-id="6da94-125">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="6da94-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
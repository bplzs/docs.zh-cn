---
title: "ISymUnmanagedMethod::GetToken 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedMethod.GetToken
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedMethod::GetToken
helpviewer_keywords:
- ISymUnmanagedMethod::GetToken method [.NET Framework debugging]
- GetToken method, ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: 4effbe95-c36e-4a45-8b2a-ee21339415fb
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b3cbcd27d42928223411a31dbb68e6d1dd0391fd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedmethodgettoken-method"></a><span data-ttu-id="d9839-102">ISymUnmanagedMethod::GetToken 方法</span><span class="sxs-lookup"><span data-stu-id="d9839-102">ISymUnmanagedMethod::GetToken Method</span></span>
<span data-ttu-id="d9839-103">返回此方法的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="d9839-103">Returns the metadata token for this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9839-104">语法</span><span class="sxs-lookup"><span data-stu-id="d9839-104">Syntax</span></span>  
  
```  
HRESULT GetToken(  
   [out, retval]  mdMethodDef  *pToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d9839-105">参数</span><span class="sxs-lookup"><span data-stu-id="d9839-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="d9839-106">[out]指向的指针`mdMethodDef`接收大小，以字符为单位，包含的元数据所需的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="d9839-106">[out] A pointer to a `mdMethodDef` that receives the size, in characters, of the buffer required to contain the metadata.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d9839-107">返回值</span><span class="sxs-lookup"><span data-stu-id="d9839-107">Return Value</span></span>  
 <span data-ttu-id="d9839-108">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="d9839-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9839-109">要求</span><span class="sxs-lookup"><span data-stu-id="d9839-109">Requirements</span></span>  
 <span data-ttu-id="d9839-110">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d9839-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9839-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d9839-111">See Also</span></span>  
 [<span data-ttu-id="d9839-112">ISymUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="d9839-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
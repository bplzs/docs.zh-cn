---
title: "ICLRMetaHost 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHost
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHost
helpviewer_keywords: ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: c627fcdd-fc4f-4b1c-8e91-df8536f627d8
topic_type: apiref
caps.latest.revision: "28"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d271a69847e3bd4dc972ed8e697b8cd15f049fb9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrmetahost-interface"></a><span data-ttu-id="8e34d-102">ICLRMetaHost 接口</span><span class="sxs-lookup"><span data-stu-id="8e34d-102">ICLRMetaHost Interface</span></span>
<span data-ttu-id="8e34d-103">提供一些方法，返回特定版本的公共语言运行时 (CLR) 基于其版本号，列表所有已安装的 Clr 中，列出在指定的进程中加载的所有运行时，发现用于编译的程序集、 退出进程的 CLR 版本使用正常的运行时关闭和查询旧的 API 绑定。</span><span class="sxs-lookup"><span data-stu-id="8e34d-103">Provides methods that return a specific version of the common language runtime (CLR) based on its version number, list all installed CLRs, list all runtimes that are loaded in a specified process, discover the CLR version used to compile an assembly, exit a process with a clean runtime shutdown, and query legacy API binding.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8e34d-104">方法</span><span class="sxs-lookup"><span data-stu-id="8e34d-104">Methods</span></span>  
  
|<span data-ttu-id="8e34d-105">方法</span><span class="sxs-lookup"><span data-stu-id="8e34d-105">Method</span></span>|<span data-ttu-id="8e34d-106">描述</span><span class="sxs-lookup"><span data-stu-id="8e34d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8e34d-107">EnumerateInstalledRuntimes 方法</span><span class="sxs-lookup"><span data-stu-id="8e34d-107">EnumerateInstalledRuntimes Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateinstalledruntimes-method.md)|<span data-ttu-id="8e34d-108">返回一个包含有效的枚举[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)的计算机安装每个 CLR 版本的接口指针。</span><span class="sxs-lookup"><span data-stu-id="8e34d-108">Returns an enumeration that contains a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface pointer for each CLR version that is installed on a computer.</span></span>|  
|[<span data-ttu-id="8e34d-109">EnumerateLoadedRuntimes 方法</span><span class="sxs-lookup"><span data-stu-id="8e34d-109">EnumerateLoadedRuntimes Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateloadedruntimes-method.md)|<span data-ttu-id="8e34d-110">返回一个包含有效的枚举[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)给定进程中加载每个 CLR 的接口指针。</span><span class="sxs-lookup"><span data-stu-id="8e34d-110">Returns an enumeration that contains a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface pointer for each CLR that is loaded in a given process.</span></span> <span data-ttu-id="8e34d-111">此方法取代[GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)。</span><span class="sxs-lookup"><span data-stu-id="8e34d-111">This method supersedes [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md).</span></span>|  
|[<span data-ttu-id="8e34d-112">ExitProcess 方法</span><span class="sxs-lookup"><span data-stu-id="8e34d-112">ExitProcess Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md)|<span data-ttu-id="8e34d-113">尝试正常关闭所有已加载的运行时，然后终止该进程。</span><span class="sxs-lookup"><span data-stu-id="8e34d-113">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="8e34d-114">取代[CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="8e34d-114">Supersedes the [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) function.</span></span>|  
|[<span data-ttu-id="8e34d-115">GetRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="8e34d-115">GetRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md)|<span data-ttu-id="8e34d-116">获取[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)与特定的 CLR 版本相对应的接口。</span><span class="sxs-lookup"><span data-stu-id="8e34d-116">Gets the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that corresponds to a particular CLR version.</span></span> <span data-ttu-id="8e34d-117">此方法取代[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)函数用于[STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)标志。</span><span class="sxs-lookup"><span data-stu-id="8e34d-117">This method supersedes the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function used with the [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) flag.</span></span>|  
|[<span data-ttu-id="8e34d-118">GetVersionFromFile 方法</span><span class="sxs-lookup"><span data-stu-id="8e34d-118">GetVersionFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getversionfromfile-method.md)|<span data-ttu-id="8e34d-119">获取程序集的原始.NET Framework 编译版本 （存储在元数据），将给定文件路径。</span><span class="sxs-lookup"><span data-stu-id="8e34d-119">Gets the assembly's original .NET Framework compilation version (stored in the metadata), given its file path.</span></span> <span data-ttu-id="8e34d-120">此方法取代[GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md)。</span><span class="sxs-lookup"><span data-stu-id="8e34d-120">This method supersedes [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md).</span></span>|  
|[<span data-ttu-id="8e34d-121">QueryLegacyV2RuntimeBinding 方法</span><span class="sxs-lookup"><span data-stu-id="8e34d-121">QueryLegacyV2RuntimeBinding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-querylegacyv2runtimebinding-method.md)|<span data-ttu-id="8e34d-122">返回表示旧式激活策略具有已绑定到，例如通过使用的运行时的接口`useLegacyV2RuntimeActivationPolicy`属性[\<启动 > 元素](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)配置文件项，直接使用通过旧激活 Api 或通过调用[iclrruntimeinfo:: Bindaslegacyv2runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="8e34d-122">Returns an interface that represents a runtime to which legacy activation policy has been bound, for example by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) configuration file entry, by direct use of the legacy activation APIs, or by calling the [ICLRRuntimeInfo::BindAsLegacyV2Runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) method.</span></span>|  
|[<span data-ttu-id="8e34d-123">RequestRuntimeLoadedNotification 方法</span><span class="sxs-lookup"><span data-stu-id="8e34d-123">RequestRuntimeLoadedNotification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-requestruntimeloadednotification-method.md)|<span data-ttu-id="8e34d-124">当首次加载，但尚未启动的 CLR 版本，可确保对指定的函数指针的回调。</span><span class="sxs-lookup"><span data-stu-id="8e34d-124">Guarantees a callback to the specified function pointer when a CLR version is first loaded, but not yet started.</span></span> <span data-ttu-id="8e34d-125">此方法取代[LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)</span><span class="sxs-lookup"><span data-stu-id="8e34d-125">This method supersedes [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e34d-126">备注</span><span class="sxs-lookup"><span data-stu-id="8e34d-126">Remarks</span></span>  
 <span data-ttu-id="8e34d-127">若要获取此接口的实例的唯一方法是通过调用[CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md)函数，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8e34d-127">The only way to get an instance of this interface is by calling the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function as follows:</span></span>  
  
```  
ICLRMetaHost *pMetaHost = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHost,  
                   IID_ICLRMetaHost, (LPVOID*)&pMetaHost);  
```  
  
## <a name="requirements"></a><span data-ttu-id="8e34d-128">要求</span><span class="sxs-lookup"><span data-stu-id="8e34d-128">Requirements</span></span>  
 <span data-ttu-id="8e34d-129">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8e34d-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e34d-130">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="8e34d-130">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8e34d-131">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8e34d-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8e34d-132">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e34d-132">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e34d-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8e34d-133">See Also</span></span>  
 [<span data-ttu-id="8e34d-134">承载接口</span><span class="sxs-lookup"><span data-stu-id="8e34d-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="8e34d-135">承载</span><span class="sxs-lookup"><span data-stu-id="8e34d-135">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
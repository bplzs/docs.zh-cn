---
title: IDefinitionIdentity 接口
ms.date: 03/30/2017
api_name:
- IDefinitionIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionIdentity
helpviewer_keywords:
- IDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: ce5ba888-5fbe-4efd-91cf-f0ff94d8428b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 401c23e44cc473d0a27a82a00343852693cb0f2e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429340"
---
# <a name="idefinitionidentity-interface"></a>IDefinitionIdentity 接口
表示在当前范围内定义应用程序的代码的唯一签名。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|到新获取的接口指针`IDefinitionIdentity`对象，它等同于此`IDefinitionIdentity`，除指定的属性更改外。|  
|`IDefinitionIdentity::EnumAttributes`|获取到的接口指针[IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)对象，其中包含与此关联的特性`IDefinitionIdentity`。|  
|`IDefinitionIdentity::GetAttribute`|获取具有指定名称的属性的值中指定的命名空间。|  
|`IDefinitionIdentity::SetAttribute`|设置为指定的值指定的命名空间中具有指定的名称的属性。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Isolation.h  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [合成接口](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)

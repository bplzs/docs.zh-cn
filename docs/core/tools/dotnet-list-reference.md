---
title: dotnet list reference 命令 - .NET Core CLI
description: dotnet list reference 命令可便于列出项目间引用。
ms.date: 12/03/2018
ms.openlocfilehash: 58b4e07abfe95d1febdd54d117825ecedf502e61
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53152588"
---
# <a name="dotnet-list-reference"></a>dotnet list reference

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet list reference` - 列出项目到项目引用。

## <a name="synopsis"></a>摘要

`dotnet list [<PROJECT>] reference [-h|--help]`

## <a name="description"></a>说明

使用 `dotnet list reference` 命令可方便地列出给定项目或解决方案的项目引用。

## <a name="arguments"></a>自变量

* **`PROJECT`**

  指定用于列出引用的项目文件。 如果未指定，此命令会搜索当前目录，以获取项目文件。

## <a name="options"></a>选项

* **`-h|--help`**

  打印出有关命令的简短帮助。

## <a name="examples"></a>示例

* 列出指定项目的项目引用：

  ```console
  dotnet list app/app.csproj reference
  ```

* 列出当前目录中的项目的项目引用：

  ```console
  dotnet list reference
  ```
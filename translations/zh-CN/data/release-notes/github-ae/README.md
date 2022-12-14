---
ms.openlocfilehash: 78f03188cb76fd34ffd5670585758bb8c9c2a47d
ms.sourcegitcommit: 47bd0e48c7dba1dde49baff60bc1eddc91ab10c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2022
ms.locfileid: "145098643"
---
# GitHub AE 版本说明

已呈现在此处： https://docs.github.com/en/github-ae@latest/admin/release-notes

## 工作原理

### 占位符内容文件

内容文件存在于 `content/admin/release-notes.md` 中。 它有一个特殊的前辅文属性 `layout: release-notes`，无 Markdown 内容。 发行说明的来源来自 YAML 数据。

### YAML 来源

发行说明的源数据位于此目录 (`data/release-notes/github-ae`) 中。

目录按月命名。 YAML 文件由每周发布的数据命名。

必须在每个 YAML 文件中设置一个名为 `currentWeek` 的布尔属性。 每次不超过一个文件可将此属性设置为真。

请注意，补丁文件可由可选的 `deprecated: true` 属性单独废弃（即在文档网站上隐藏）。

### 中间件处理

YAML 数据由 `middleware/contextualizers/release-notes.js` 处理和排序，并添加到 `context` 对象。

### 布局

`context` 对象数据由 `components/release-notes` 呈现。

发行说明页在 `stylesheets/release-notes.scss` 中使用 CSS 自定义设计。

### 架构

验证 YAML 数据的架构存在于 `tests/helpers/schemas/ghae-release-notes-schema.js` 中。 查看架构文件来了解必需和可选的属性。

架构在 `tests/linting/lint-files.js` 中执行测试。 如果数据未通过验证，测试将失败。

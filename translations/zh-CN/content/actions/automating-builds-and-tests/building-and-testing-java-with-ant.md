---
title: 使用 Ant 构建和测试 Java
intro: 您可以在 GitHub Actions 中创建持续集成 (CI) 工作流程，以使用 Ant 构建和测试 Java 项目。
redirect_from:
  - /actions/language-and-framework-guides/building-and-testing-java-with-ant
  - /actions/guides/building-and-testing-java-with-ant
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
  ghec: '*'
type: tutorial
topics:
  - CI
  - Java
  - Ant
shortTitle: Build & test Java & Ant
ms.openlocfilehash: d1e73fdce7bf23bf1b86ec3eb4d0f8acd9b6d292
ms.sourcegitcommit: 47bd0e48c7dba1dde49baff60bc1eddc91ab10c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2022
ms.locfileid: '145084729'
---
{% data reusables.actions.enterprise-beta %} {% data reusables.actions.enterprise-github-hosted-runners %}

## 简介

本指南介绍如何使用 Ant 构建系统为 Java 项目创建执行持续集成 (CI) 的工作流程。 您创建的工作流程将允许您查看拉取请求提交何时会在默认分支上导致构建或测试失败； 这个方法可帮助确保您的代码始终是健康的。 您可以扩展 CI 工作流程以从工作流程运行上传构件。

{% ifversion ghae %} {% data reusables.actions.self-hosted-runners-software %} {% else %} {% data variables.product.prodname_dotcom %} 托管的运行器有一个带有预安装软件的工具缓存，其中包括 Java 开发工具包 (JDK) 和 Ant。 有关 JDK 和 Ant 的软件和预安装版本的列表，请参阅“[{% data variables.product.prodname_dotcom %} 托管的运行器规范](/actions/reference/specifications-for-github-hosted-runners/#supported-software)”。
{% endif %}

## 先决条件

您应该熟悉 YAML 和 {% data variables.product.prodname_actions %} 的语法。 有关详细信息，请参阅：
- “[{% data variables.product.prodname_actions %} 工作流语法](/actions/automating-your-workflow-with-github-actions/workflow-syntax-for-github-actions)”
- “[了解 {% data variables.product.prodname_actions %}](/actions/learn-github-actions)”

建议您对 Java 和 Ant 框架有个基本的了解。 有关详细信息，请参阅 [Apache Ant 手册](https://ant.apache.org/manual/)。

{% data reusables.actions.enterprise-setup-prereq %}

## 使用 Ant 入门工作流程

{% data variables.product.prodname_dotcom %} 提供有 Ant 入门工作流程，适用于大多数基于 Ant 的 Java 项目。 有关详细信息，请参阅 [Ant 入门工作流](https://github.com/actions/starter-workflows/blob/main/ci/ant.yml)。

要快速开始，您可以在创建新工作流程时选择预配置的 Ant 入门工作流程。 有关详细信息，请参阅“[{% data variables.product.prodname_actions %} 快速入门](/actions/quickstart)”。

也可以通过在存储库的 `.github/workflows` 目录中创建新文件来手动添加此工作流。

```yaml{:copy}
name: Java CI

on: [push]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - uses: {% data reusables.actions.action-checkout %}
      - name: Set up JDK 11
        uses: {% data reusables.actions.action-setup-java %}
        with:
          java-version: '11'
          distribution: 'adopt'
      - name: Build with Ant
        run: ant -noinput -buildfile build.xml
```

此工作流程执行以下步骤：

1. `checkout` 步骤在运行器上下载存储库的副本。
2. `setup-java` 步骤通过 Adoptium 配置 Java 11 JDK。
3. “使用 Ant 构建”步骤以非交互模式运行 `build.xml` 中的默认目标。

在创建构建和测试工作流程时，默认入门工作流程是很好的起点，然后您可以自定义入门工作流程以满足项目的需求。

{% data reusables.actions.example-github-runner %}

{% data reusables.actions.java-jvm-architecture %}

## 构建和测试代码

您可以使用与本地相同的命令来构建和测试代码。

入门工作流将运行“build.xml”文件中指定的默认目标。  默认目标通常设置为将类、运行测试和包类设置为其可分发格式，例如 JAR 文件。

如果使用不同的命令来构建项目，或者想要运行不同的目标，则可以指定这些命令。 例如，你可能想要运行在 `_build-ci.xml_` 文件中配置的 `jar` 目标。

```yaml{:copy}
steps:
  - uses: {% data reusables.actions.action-checkout %}
  - uses: {% data reusables.actions.action-setup-java %}
    with:
      java-version: '11'
      distribution: 'adopt'
  - name: Run the Ant jar target
    run: ant -noinput -buildfile build-ci.xml jar
```

## 将工作流数据打包为构件

构建成功且测试通过后，您可能想要上传生成的 Java 包作为构件。 这会将构建的包存储为工作流程运行的一部分，并允许您下载它们。 构件可帮助您在拉取请求合并之前在本地环境中测试并调试它们。 有关详细信息，请参阅“[使用项目保留工作流数据](/actions/automating-your-workflow-with-github-actions/persisting-workflow-data-using-artifacts)”。

Ant 通常会在 `build/jar` 目录中创建 JAR、EAR 或 WAR 等输出文件。 可以使用 `upload-artifact` 操作上传该目录的内容。

```yaml{:copy}
steps:
  - uses: {% data reusables.actions.action-checkout %}
  - uses: {% data reusables.actions.action-setup-java %}
    with:
      java-version: '11'
      distribution: 'adopt'
  
  - run: ant -noinput -buildfile build.xml
  - uses: {% data reusables.actions.action-upload-artifact %}
    with:
      name: Package
      path: build/jar
```

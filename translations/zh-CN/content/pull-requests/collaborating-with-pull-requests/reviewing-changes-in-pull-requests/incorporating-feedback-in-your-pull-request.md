---
title: 在拉取请求中加入反馈
intro: 当审查者建议拉取请求中的更改时，您可以自动将这些更改合并到拉取请求中，或者开一个议题来跟踪范围外的建议。
redirect_from:
  - /github/collaborating-with-issues-and-pull-requests/reviewing-changes-in-pull-requests/incorporating-feedback-in-your-pull-request
  - /articles/incorporating-feedback-in-your-pull-request
  - /github/collaborating-with-issues-and-pull-requests/incorporating-feedback-in-your-pull-request
  - /github/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/incorporating-feedback-in-your-pull-request
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
  ghec: '*'
topics:
  - Pull requests
shortTitle: Incorporate feedback
ms.openlocfilehash: b94c7ddc682b1e53077770877140eb2a218a19de
ms.sourcegitcommit: 47bd0e48c7dba1dde49baff60bc1eddc91ab10c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2022
ms.locfileid: '145130072'
---
## 应用建议的更改

其他人可对您的拉取请求提出具体的更改建议。 如果您可以写入仓库，便可直接在拉取请求中应用这些提议的更改。 如果拉取请求创建自复刻，并且作者允许维护员编辑，则您也可以应用提议的更改（如果您可以写入上游仓库）。 有关详细信息，请参阅“[评论拉取请求](/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/commenting-on-a-pull-request)”和“[允许更改从分支创建的拉取请求分支](/pull-requests/collaborating-with-pull-requests/working-with-forks/allowing-changes-to-a-pull-request-branch-created-from-a-fork)”。

要快速将多项提议的更改合并到单一提交，您也可以批量应用提议的更改。 应用一项或一批提议的更改会在拉取请求的比较分支上创建一个提交。

在提交中提议了更改的每个人都是该提交的联合作者。 提议的更改的应用者将是提交的联合作者兼提交者。 有关 Git 中术语提交者的更多信息，请参阅 _Pro Git_ 图书网站中的“[Git 基础 - 查看提交历史记录](https://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History)”。

{% data reusables.repositories.sidebar-pr %}
2. 在拉取请求列表中，单击要对其应用提议的更改的拉取请求。
3. 导航到您要应用的第一个提议的更改。
    - 若要在自己的提交中应用更改，请单击“提交建议”。
  ![“提交建议”按钮](/assets/images/help/pull_requests/commit-suggestion-button.png)
    - 若要将建议添加到一批更改，请单击“添加建议到批次”。 继续添加要包含在单一提交中的更改提议。 添加完建议的更改后，单击“提交建议”。
  ![添加建议到批次按钮](/assets/images/help/pull_requests/add-suggestion-to-batch.png)
4. 在提交消息字段中，输入简短、有意义的提交消息，以描述对文件的更改。
![提交消息字段](/assets/images/help/pull_requests/suggested-change-commit-message-field.png)
5. 单击“提交更改”。
![提交更改按钮](/assets/images/help/pull_requests/commit-changes-button.png)

## 重新请求审核

{% data reusables.pull_requests.re-request-review %}

## 为范围外建议开一个议题

如果有人建议更改您的拉取请求，并且更改超出拉请求的范围，则可以新开一个议题来跟踪反馈。 有关详细信息，请参阅“[从评论创建问题](/github/managing-your-work-on-github/opening-an-issue-from-a-comment)”。

## 延伸阅读

- [关于拉取请求审查](/github/collaborating-with-issues-and-pull-requests/about-pull-request-reviews)
- “[审查拉取请求中的建议更改](/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/reviewing-proposed-changes-in-a-pull-request)”
- [评论拉取请求](/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/commenting-on-a-pull-request)
- [请求拉取请求审查](/github/collaborating-with-issues-and-pull-requests/requesting-a-pull-request-review)
- [从评论创建问题](/github/managing-your-work-on-github/opening-an-issue-from-a-comment)

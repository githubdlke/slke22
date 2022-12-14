---
title: Trabalhar com hooks pre-receive
intro: Os *ganchos pré-recebimento* impõem regras para contribuições antes que o push dos commits seja efetuado em um repositório.
redirect_from:
  - /github/collaborating-with-issues-and-pull-requests/collaborating-on-repositories-with-code-quality-features/working-with-pre-receive-hooks
  - /articles/working-with-pre-receive-hooks
  - /github/collaborating-with-issues-and-pull-requests/working-with-pre-receive-hooks
  - /github/collaborating-with-pull-requests/collaborating-on-repositories-with-code-quality-features/working-with-pre-receive-hooks
versions:
  ghes: '*'
shortTitle: Pre-receive hooks
ms.openlocfilehash: 6ca26aed9e9d92abfb6d742f7f4ca968c442b447
ms.sourcegitcommit: 47bd0e48c7dba1dde49baff60bc1eddc91ab10c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/05/2022
ms.locfileid: '146332589'
---
Os hooks pre-receive executam testes em um código do qual foi feito push em um repositório, para garantir que as contribuições atendam à política do repositório ou da organização. Se o conteúdo do commit passar nos testes, o push será aceito no repositório. Caso o conteúdo do commit não passe nos testes, o push não será aceito.

Se o push não for aceito, você receberá uma mensagem de erro correspondente ao hook pre-receive com falha.

```shell
$ git push
Counting objects: 3, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 916 bytes | 0 bytes/s, done.
Total 3 (delta 0), reused 0 (delta 0)
remote: always_reject.sh: failed with exit status 1
remote: error: rejecting all pushes
To https://54.204.174.51/hodor/nope.git
 ! [remote rejected] main -> main (pre-receive hook declined)
error: failed to push some refs to 'https://54.204.174.51/hodor/nope.git'
```

![Mensagem de erro sobre hook pre-receive com falha](/assets/images/help/pull_requests/pre-receive-hook-failed-error.png)

O administrador de site do {% data variables.product.product_name %} pode criar e remover hooks pre-receive da organização ou do repositório e permitir que os administradores da organização ou do repositório habilitem ou desabilitem hooks pre-receive. Para obter mais informações, confira "[Como usar ganchos de pré-recebimento para impor uma política](/enterprise/admin/guides/developer-workflow/using-pre-receive-hooks-to-enforce-policy)".

---
title: Auditar de usuários em toda a sua empresa
intro: 'O painel do log de auditoria mostra aos administradores do site as ações realizadas por todos os usuários e organizações de toda a sua empresa dentro do mês atual e dos seis meses anteriores. O log de auditoria inclui detalhes como quem realizou a ação, qual foi a ação e quando a ação foi realizada.'
redirect_from:
  - /enterprise/admin/guides/user-management/auditing-users-across-an-organization
  - /enterprise/admin/user-management/auditing-users-across-your-instance
  - /admin/user-management/auditing-users-across-your-instance
  - /admin/user-management/auditing-users-across-your-enterprise
versions:
  ghes: '*'
  ghae: '*'
type: how_to
topics:
  - Auditing
  - Enterprise
  - Organizations
  - Security
  - User account
shortTitle: Audit users
ms.openlocfilehash: 18ea00b69f452ff496670fbd31e41bb8038cc46d
ms.sourcegitcommit: 47bd0e48c7dba1dde49baff60bc1eddc91ab10c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/05/2022
ms.locfileid: '146331685'
---
## Acessar o log de auditoria

O painel de log de auditoria oferece uma exibição visual de dados de auditoria na sua empresa.

![Painel de log de auditoria da instância](/assets/images/enterprise/site-admin-settings/audit-log-dashboard-admin-center.png)

{% data reusables.enterprise-accounts.access-enterprise %} {% data reusables.enterprise-accounts.settings-tab %} {% data reusables.enterprise-accounts.audit-log-tab %}

No mapa, você pode aplicar zoom e visão panorâmica para ver os eventos do mundo todo. Posicione o mouse sobre um país para ver a contagem de eventos ocorridos nele.

## Pesquisar eventos na sua empresa

O log de auditoria lista as seguintes informações sobre as ações feitas na sua empresa:

* [O repositório](#search-based-on-the-repository) no qual uma ação foi executada
* [O usuário](#search-based-on-the-user) que executou a ação
* [A organização](#search-based-on-the-organization) a qual uma ação pertencia
* [A ação](#search-based-on-the-action-performed) executada
* [O país](#search-based-on-the-location) em que a ação foi executada
* [A data e a hora](#search-based-on-the-time-of-action) em que a ação ocorreu

{% warning %}

**Observações:**

- Embora não seja possível usar texto para pesquisar entradas de auditoria, você pode criar consultas de pesquisa usando filtros diversificados. {% data variables.product.product_name %} é compatível com muitos operadores para fazer pesquisa em {% data variables.product.product_name %}. Para obter mais informações, confira "[Sobre a pesquisa no {% data variables.product.prodname_dotcom %}](/github/searching-for-information-on-github/about-searching-on-github)".
- Os registros de auditoria estão disponíveis para o mês atual e todos os dias dos seis meses anteriores.

{% endwarning %}

### Pesquisar com base no repositório

O qualificador `repo` limita as ações a um repositório específico pertencente à sua organização. Por exemplo:

* `repo:my-org/our-repo` localiza todos os eventos que ocorreram no repositório `our-repo` na organização `my-org`.
* `repo:my-org/our-repo repo:my-org/another-repo` localiza todos os eventos que ocorreram nos repositórios `our-repo` e `another-repo` na organização `my-org`.
* `-repo:my-org/not-this-repo` exclui todos os eventos que ocorreram no repositório `not-this-repo` na organização `my-org`.

É preciso incluir o nome da organização no qualificador `repo`. A pesquisa de apenas `repo:our-repo` não funcionará.

### Pesquisar com base no usuário

O qualificador `actor` define o escopo de eventos com base no membro da organização que executou a ação. Por exemplo:

* `actor:octocat` localiza todos os eventos realizados por `octocat`.
* `actor:octocat actor:hubot` localiza todos os eventos realizados por `octocat` e `hubot`.
* `-actor:hubot` exclui todos os eventos realizados por `hubot`.

Só é possível usar um nome de usuário do {% data variables.product.product_name %}, não o nome verdadeiro da pessoa.

### Pesquisar com base na organização

O qualificador `org` limita as ações a uma organização específica. Por exemplo:

* `org:my-org` localiza todos os eventos ocorridos na organização `my-org`.
* `org:my-org action:team` localiza todos os eventos da equipe executados na organização `my-org`.
* `-org:my-org` exclui todos os eventos ocorridos na organização `my-org`.

### Pesquisar com base na ação

O qualificador `action` procura eventos específicos, agrupados em categorias. Para obter informações sobre os eventos associados a essas categorias, confira "[Auditar eventos de log para sua empresa](/admin/monitoring-activity-in-your-enterprise/reviewing-audit-logs-for-your-enterprise/audit-log-events-for-your-enterprise)".

| Nome da categoria | Descrição
|------------------|-------------------
| `hook` | Tem todas as atividades relacionadas a webhooks.
| `org` | Tem todas as atividades relacionadas à associação na organização.
| `repo` | Tem todas as atividades relacionadas aos repositórios pertencentes à organização.
| `team` | Tem todas as atividades relacionadas às equipes na organização.

Você pode pesquisar conjuntos específicos de ações usando esses termos. Por exemplo:

* `action:team` localiza todos os eventos agrupados na categoria da equipe.
* `-action:billing` exclui todos os eventos na categoria de cobrança.

Cada categoria tem um conjunto de eventos associados que você pode usar no filtro. Por exemplo:

* `action:team.create` localiza todos os eventos em que uma equipe foi criada.
* `-action:billing.change_email` exclui todos os eventos em que o email de cobrança foi alterado.

### Pesquisar com base no local

O qualificador `country` filtra as ações pelo país de origem.
- Você pode usar o código de duas letras do país ou o nome completo.
- Países com duas ou mais palavras devem ficar entre aspas. Por exemplo:
  * `country:de` localiza todos os eventos ocorridos na Alemanha.
  * `country:Mexico` localiza todos os eventos ocorridos no México.
  * `country:"United States"` localiza todos os eventos ocorridos nos Estados Unidos.

### Pesquisar com base na hora da ação

O qualificador `created` filtra as ações no momento em que elas ocorreram.
- Defina datas usando o formato `YYYY-MM-DD`, ou seja, ano, seguido do mês e do dia.
- As datas dão suporte aos [qualificadores maior que, menor que e intervalo](/enterprise/user/articles/search-syntax). Por exemplo:
  * `created:2014-07-08` localiza todos os eventos ocorridos em 8 de julho de 2014.
  * `created:>=2014-07-01` localiza todos os eventos ocorridos em 8 de julho de 2014 ou após essa data.
  * `created:<=2014-07-01` localiza todos os eventos ocorridos em 8 de julho de 2014 ou antes dessa data.
  * `created:2014-07-01..2014-07-31` localiza todos os eventos ocorridos no mês de julho de 2014.

---
title: Acerca de los gráficos del repositorio
intro: Los gráficos del repositorio te ayudan a ver y analizar datos para tu repositorio.
redirect_from:
  - /articles/using-graphs
  - /articles/about-repository-graphs
  - /github/visualizing-repository-data-with-graphs/about-repository-graphs
  - /github/visualizing-repository-data-with-graphs/accessing-basic-repository-data/about-repository-graphs
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
  ghec: '*'
topics:
  - Repositories
ms.openlocfilehash: a8e2b228e4729e0c86d0234aadc7f0eebab7d2d5
ms.sourcegitcommit: 47bd0e48c7dba1dde49baff60bc1eddc91ab10c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2022
ms.locfileid: '145136632'
---
Los gráficos de un repositorio le dan información sobre el tráfico de {% ifversion fpt or ghec %}, los proyectos que dependen del repositorio, {% endif %} los colaboradores y las confirmaciones para el repositorio y la red y las bifurcaciones de un repositorio. Si tú mantienes un repositorio, puedes usar estos datos para comprender mejor quién está usando tu repositorio y por qué lo están usando.

{% ifversion fpt or ghec %}

Algunos gráficos del repositorio solo están disponibles en repositorios públicos con {% data variables.product.prodname_free_user %}:
- Pulso
- Colaboradores
- Tráfico
- Confirmaciones
- Frecuencia de código
- Red

Todos los otros gráficos del repositorio están disponibles en todos los repositorios. Cada gráfico del repositorio está disponible en repositorios públicos y privados con {% data variables.product.prodname_pro %}, {% data variables.product.prodname_team %} y {% data variables.product.prodname_ghe_cloud %}. {% data reusables.gated-features.more-info %}

{% endif %}

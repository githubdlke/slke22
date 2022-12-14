---
title: Solucionar problemas de conectividade
intro: 'Se você estiver tendo problemas para se conectar ao {% data variables.product.prodname_dotcom %}, use a ferramenta {% data variables.product.prodname_debug %} para diagnosticá-los.'
redirect_from:
  - /articles/troubleshooting-connectivity-problems
  - /github/getting-started-with-github/troubleshooting-connectivity-problems
  - /github/getting-started-with-github/using-github/troubleshooting-connectivity-problems
versions:
  fpt: '*'
  ghec: '*'
shortTitle: Connectivity problems
ms.openlocfilehash: 77e88f4721c5dfa9cdde22ddee23a9188785e994
ms.sourcegitcommit: 47bd0e48c7dba1dde49baff60bc1eddc91ab10c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/05/2022
ms.locfileid: '145065581'
---
Geralmente, os problemas de conexão ocorrem devido à configuração de um firewall, um servidor proxy, uma rede corporativa ou outra rede que bloqueia o {% data variables.product.prodname_dotcom %}.

## Permitir endereços IP de {% data variables.product.prodname_dotcom %}

Certifique-se de que sua rede está configurada para permitir endereços IP de {% data variables.product.prodname_dotcom %}. Para obter mais informações, confira "[Sobre endereços IP do {% data variables.product.prodname_dotcom %}](/articles/about-github-s-ip-addresses)".

## Usar a rede de uma empresa ou organização

Se você estiver tendo problemas de conectividade na rede da sua empresa ou organização, verifique com o administrador da rede se há regras em vigor na rede para bloquear certos tráficos. Se houver regras em vigor, peça ao seu administrador de rede para permitir o tráfego para {% data variables.product.prodname_dotcom %}.

## Solucionar problemas com o captcha

Se você não conseguir verificar o captcha:
- Confira se o JavaScript está habilitado no seu navegador.
- Confira se há suporte para o seu navegador. Caso contrário, atualize-o ou instale outro compatível. Para obter uma lista dos navegadores com suporte, veja "[Navegadores com suporte](/articles/supported-browsers)".
- Sua configuração de rede não deve bloquear https://octocaptcha.com/ nem https://arkoselabs.com/. Se você está atrás de um firewall corporativo, entre em contato com o administrador de TI para permitir esses domínios. Para verificar o acesso a esses domínios, acesse https://octocaptcha.com/test e verifique se o texto "Conexão feita com êxito!" é exibido e, em seguida, acesse https://client-demo.arkoselabs.com/github e verifique se você consegue carregar o captcha.
- Confira se o navegador não tem plugins ou extensões que possam estar inferindo com o GitHub. Se for o caso, desabilite plugins ou extensões temporariamente durante a verificação do captcha.

## Alternar métodos de clonagem

Alternar da clonagem via SSH para a clonagem via HTTPS (ou vice-versa) pode melhorar a conectividade. Para obter mais informações, veja "[Solução de problemas de erros de clonagem](/repositories/creating-and-managing-repositories/troubleshooting-cloning-errors)".

Se você estiver se deparando com tempos limite com o SSH, veja "[Erro: número de arquivo inválido](/articles/error-bad-file-number)".

## Solucionar problemas de downloads lentos e conexões intermitentemente lentas

O {% data variables.product.prodname_dotcom %} não aumenta a largura de banda por usuário.

Se a conexão está lenta em alguns horários do dia, mas não em outros, o motivo mais provável é o congestionamento da rede. Como o {% data variables.product.prodname_dotcom %} não resolve congestionamento de rede, é recomendável escalonar o problema para o provedor de serviço de internet.

## Solucionar problemas com o {% data variables.product.prodname_debug %}

Se você seguiu todas as sugestões de solução de problemas acima e ainda está tendo problemas de conexão, siga as instruções no site do {% data variables.product.prodname_debug %} para fazer testes e enviar um relatório para o suporte do {% data variables.product.prodname_dotcom %}. Para obter mais informações, confira [{% data variables.product.prodname_debug %}](https://github-debug.com/).

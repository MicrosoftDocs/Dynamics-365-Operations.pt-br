---
title: O que há de novo ou mudou no aplicativo móvel Warehouse Management
description: Este tópico lista os recursos novos e alterados para cada versão lançada do aplicativo móvel Warehouse Management para o Microsoft Dynamics 365 Supply Chain Management.
author: ivanv-microsoft
ms.date: 06/07/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ivanv
ms.search.validFrom: 2021-06-07
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 61124728942c0b8162de9f687ae752773c47d07e
ms.sourcegitcommit: 4cbd83e21a78459e4711a2dedba0f5a7acc3c841
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2021
ms.locfileid: "6261762"
---
# <a name="whats-new-or-changed-in-the-warehouse-management-mobile-app"></a>O que há de novo ou mudou no aplicativo móvel Warehouse Management

[!include [banner](../includes/banner.md)]

Este tópico lista recursos novos, correções, aprimoramentos e problemas conhecidos para cada versão lançada do aplicativo móvel Warehouse Management para o Microsoft Dynamics 365 Supply Chain Management.

## <a name="version-2060"></a>Versão 2.0.6.0

### <a name="new-features-fixes-and-improvements-in-version-2060"></a>Novos recursos, correções e aprimoramentos na versão 2.0.6.0

Esta versão introduz os novos recursos, correções e aprimoramentos a seguir:

- O modo de demonstração agora mostra todos os rótulos no idioma do dispositivo.
- É menos provável que você receba a seguinte mensagem de erro: "Não é possível encontrar uma exibição adequada para o tamanho especificado."
- A altura mínima para cartões de trabalho foi aumentada (para casos em que três ou menos campos estão configurados para aparecer na lista de trabalho).
- As margens (em degradê) na parte inferior dos cartões de detalhes foram melhoradas.
- Os símbolos inválidos em arquivos XML que são trocados com o servidor agora são tratados adequadamente. (Por exemplo, caracteres não imprimíveis agora são tratados adequadamente e não fazem mais com que o aplicativo pare de responder.)
- Os erros HTTP (como "erro 503") quando uma solicitação de servidor é enviada agora são tratados adequadamente.
- Enquanto um erro está sendo mostrado, a lista de opções não é mais mostrada automaticamente para controles de caixa combinação.
- O aplicativo não para mais de responder por causa da orientação de exibição selecionada nas configurações do usuário.
- As imagens do produto agora são mostradas em ambientes de autoatendimento. (Esta alteração aplica-se apenas a versões de baixa resolução. O serviço de gerenciamento de arquivos não permite imagens em tamanho real em ambientes de autoatendimento.)
- Um problema que envolvia separações curtas de quantidade zero foi corrigido.
- O aplicativo não para mais de responder quando um cartão de detalhes mostra vários campos idênticos.

### <a name="known-issues-in-version-2060"></a>Problemas conhecidos na versão 2.0.6.0

Os seguintes problemas conhecidos existem nesta versão:

- O aplicativo (especialmente a lista de trabalho) torna-se mais lento com o tempo.
- **Versão do Windows:** quando uma pistola USB é usada para digitalizar no Windows, resultados inconsistentes fazem com que os símbolos digitalizados sejam misturados.

## <a name="version-2050"></a>Versão 2.0.5.0

Esta versão introduz os novos recursos, correções e aprimoramentos a seguir:

- O segredo do cliente não está mais escondido na configuração de definições de conexão.
- Agora você pode manter pressionado qualquer texto para vê-lo completamente.
- A mensagem de erro quando não há permissões de armazenamento foi melhorada.
- Novas sequências de controle foram adicionadas para alguns fluxos.
- O botão de envio não fica mais disponível incorretamente devido ao tamanho da janela.
- Os controles deslizantes agora podem continuar em telas menores quando são usados tamanhos de botões maiores.
- A sobreposição de quatro botões não aparece mais cortada.
- O teclado agora dá suporte ao botão delete.
- Um problema de brilho que pode ocorrer quando o teclado é pressionado foi corrigido.
- Vários problemas de dados de demonstração foram corrigidos.
- Um problema que afetava campos numéricos na página de detalhes foi corrigido.
- O teclado virtual não desaparece mais ocasionalmente em alguns dispositivos.
- Vários bugs de interface de usuário foram corrigidos, como bugs que afetavam a cor de fundo e posicionamento.
- A interface do usuário no idioma russo foi melhorada.
- Vários problemas que fizeram com que o sistema parasse de responder foram corrigidos.
- Um problema relacionado à reabertura da calculadora foi corrigido.
- **Versão do Android:** um problema que fazia com que o Android 4.4 parasse de responder na inicialização foi corrigido.
- **Versão do Android:** o dimensionamento mínimo foi reduzido para 50%.

## <a name="version-2040"></a>Versão 2.0.4.0

A versão 2.0.4.0 foi a primeira versão geralmente disponível do aplicativo móvel Warehouse Management.

### <a name="new-features-fixes-and-improvements-in-version-2040"></a>Novos recursos, correções e aprimoramentos na versão 2.0.4.0

Esta versão introduz os seguintes novos recursos, correções e aprimoramentos que não estavam disponíveis na versão prévia:

- Se um cartão de detalhes incluir dois rótulos que tenham dados idênticos, um dos rótulos será oculto.
- Os caracteres especiais agora são mostrados por padrão, e a opção de escondê-los foi removida das configurações do usuário.
- Os botões de envio desativados agora são mostrados como não disponíveis na exibição compacta portátil.
- Uma alteração na lógica de sequenciamento para controles garante um dimensionamento mais suave entre os dispositivos. Portanto, há menos necessidade de ajustar o dimensionamento de fontes ou botões.
- O tema de cor padrão foi alterado para *Escuro*.
- O ícone ausente para o botão de envio desativado foi adicionado na exibição da faixa de exibições.
- Exceções de tempo agora levam você para a página de conexão em vez de mostrar um erro em linha.
- Se nenhuma ação de envio estiver disponível (como **OK**, **Sim**, **Aceitar**, **Concluído** ou **Finalizado**), o botão de envio será desativado.
- A estabilidade do aplicativo foi melhorada.
- Há uma correção para vulnerabilidade de segurança [CVE-2021-26701](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-26701).
- **Versão do Windows:** foi corrigido um problema no Windows, no qual os menus não respondiam mais depois que a janela era redimensionada.

### <a name="known-issue-in-version-2040"></a>Problemas conhecidos na versão 2.0.4.0

O seguinte problema conhecido existe nesta versão:

- Esta versão tem um problema com dispositivos que usam Android 4.4. Você pode ter problemas quando usar o aplicativo nesta versão do Android.

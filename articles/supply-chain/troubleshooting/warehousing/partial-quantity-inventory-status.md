---
title: Fazer alteração de status de estoque para trabalho com quantidade parcial
description: Esta página explica como criar um item de menu com as configurações apropriadas para permitir que os trabalhadores façam uma alteração de status de estoque para a quantidade parcial de um lote.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 056ce412955808ddf126025ad917b874c54a5e62
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475530"
---
# <a name="enable-inventory-status-change-for-partial-quantity-work"></a>Habilitar alteração de status de estoque para trabalho com quantidade parcial

## <a name="symptoms"></a>Sintomas

Você precisa fazer uma alteração de status de estoque para uma quantidade parcial de um lote.

## <a name="resolution"></a>Resolução

Para permitir que os trabalhadores façam essa mudança, é possível criar um item de menu para o aplicativo móvel Gerenciamento de Depósito. Na página **Itens de menu do dispositivo móvel**, crie (ou edite) um item de menu que tenha as seguintes configurações:

- **Modo:** *Trabalho*
- **Usar trabalho existente:** *Não*
- **Processo de criação de trabalho:** *Movimento*
- **Exibir status do estoque:** *Sim*

Você pode definir outros campos na página conforme necessário.

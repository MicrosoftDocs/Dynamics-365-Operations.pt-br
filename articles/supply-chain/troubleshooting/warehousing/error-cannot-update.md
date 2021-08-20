---
title: Um erro ocorre quando o local é selecionado durante um registro de lista de retirada
description: Um erro ocorre quando o local é selecionado durante um registro de lista de retirada.
author: perlynne
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WMSPickingRegistration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: da5905fb7ed1e890c85e891843379aa07de3279bd8972d6fc57136aa703c9ea4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6762785"
---
# <a name="an-error-occurs-when-the-location-is-selected-during-picking-list-registration"></a>Um erro ocorre quando o local é selecionado durante um registro de lista de retirada

Número da base de dados de conhecimento: 4613106

## <a name="symptoms"></a>Sintomas

Este problema ocorre quando seu sistema está configurado para reservar pedidos de venda automaticamente. Se você tentar selecionar o local para uma linha de registro de lista de retirada, você recebe a seguinte mensagem de erro ao usar os processos de reserva do gerenciamento de armazém (WMS):

> Não é possível atualizar a quantidade com as novas dimensões

Este problema pode ocorrer porque você não tem inventário em mãos suficiente em um local específico.

## <a name="resolution"></a>Resolução

O sistema está agindo como esperado.

Em situações em que você usa o processo de reserva em nível de armazém, se o inventário em mãos não puder ser reservado em todos os níveis de dimensão do inventário, e você não tem inventário em mãos suficiente em um local específico, recomendamos que você use o processo de reserva manual na linha de retirada. Você pode então usar a função *Reservar lote* para distribuir as reservas inferiores, tal como local, para todas as quantidades em mãos disponíveis.

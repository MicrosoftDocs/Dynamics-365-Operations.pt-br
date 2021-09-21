---
title: O peso da carga pode conter apenas números positivos
description: Ao processar o trabalho entre locais, você pode receber um erro com relação ao peso da carga e ao cancelamento da sua atualização. Siga estas etapas para corrigir o problema.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 8ea1f6679a521e3e8683b8e5f18f509e98044414
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475568"
---
# <a name="load-weight-error-and-update-canceled-when-processing-work-between-locations"></a>Erro de peso de carga e atualização cancelada ao processar o trabalho entre locais

## <a name="symptoms"></a>Sintomas

Se houver trabalho aberto ao processar o trabalho de locais de embalagem para locais de preparo ou de locais de preparo para locais de doca, você poderá receber o seguinte erro:

> O campo "Peso da carga" (=-%1) pode conter apenas números positivos. A atualização foi cancelada.

## <a name="resolution"></a>Resolução

Para corrigir esse problema, acesso **Administração do sistema \> Tarefas periódicas \> Banco de dados \> Verificação de consistência** e execute o processo para **Verificação de consistência do peso da carga do depósito**.

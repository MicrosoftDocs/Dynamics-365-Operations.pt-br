---
title: Erro ao alterar o status de Informado como concluído para Finalizado
description: Você pode receber um erro ao alterar o status de uma ordem de produção de Informado como concluído para Finalizado. Esta página explica como mitigar o problema.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 744637f5cccffe44b85f77c1a9df2034012fac40
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475586"
---
# <a name="error-when-changing-status-of-production-order-from-reported-as-finished-to-end"></a>Erro ao alterar o status da ordem de produção de Informado como concluído para Finalizado

## <a name="symptoms"></a>Sintomas

Quando o status de uma ordem de produção é alterado de Informado como concluído para Finalizado, você recebe uma das seguintes mensagens de erro:

> Conflito de atualização. O custo padrão não corresponde ao valor do estoque financeiro após a atualização.

> Ocorreu um erro crítico na função InventCostMovement.checkVariance.

## <a name="cause"></a>Causa

Esse problema ocorre porque os dados subjacentes foram alterados por outro processo. O processo tentará atualizar os dados até cinco vezes. Se o conflito persistir após cinco tentativas, você receberá uma das mensagens listadas abaixo.

## <a name="resolution"></a>Resolução

Esse comportamento é por design. Para atenuar o problema, retome o trabalho em lote. A execução deve ser finalizada.

Se o trabalho em lote falhar consistentemente depois de retomá-lo, verifique se a precisão do arredondamento para a moeda padrão do razão é compatível com o arredondamento que é aplicado aos valores na tabela InventSum. Se a precisão de arredondamento foi alterada para um valor não compatível, você provavelmente deve alterá-lo de volta para um valor compatível. Procure **ModifiedDateTime**. Em geral, nesse caso, o valor mostrará se a precisão do arredondamento foi alterada recentemente.

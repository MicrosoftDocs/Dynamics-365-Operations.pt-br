---
title: Reverter configurações em diários e linhas
description: Este tópico aborda por que uma entrada de estorno que foi inserida em um diário geral pode não ser incluída na transação lançada.
author: kweekley
ms.date: 04/29/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-5-05
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 74020f6fc9b0fa8e05a1e2a09fd13dcd60490dc0
ms.sourcegitcommit: 817716c2e96f24af0ef1d7d5323afdeccdc602f3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2021
ms.locfileid: "6028548"
---
# <a name="reverse-settings-on-journals-and-lines"></a>Reverter configurações em diários e linhas

[!include [banner](../includes/banner.md)]

Este tópico aborda por que uma entrada de estorno que foi inserida em um diário geral pode não ser incluída na transação lançada.  

## <a name="symptom"></a>Sintoma

Um diário geral inclui uma entrada de estorno e a data de estorno no diário. Quando você lança o diário, nenhum dos comprovantes é revertido. Por que isso ocorre?

## <a name="resolution"></a>Resolução

Quando o diário é lançado, o processo de estorno examina apenas as configurações de **Entrada de estorno** e **Data de estorno** na seção **Linhas** do comprovante. Essa abordagem permite que um diário inclua alguns comprovantes que estejam marcados para estorno e outros que não estejam.

Os valores do diário são usados somente como padrões ao adicionar *novas* linhas. A alteração dos valores no diário não afeta as linhas existentes. Neste exemplo, as linhas do comprovante foram inseridas primeiro. Ao inserir os detalhes da linha antes de designar o diário como estorno, a designação como entrada e data de estorno não será aplicada a nenhuma linha existente.

A alteração da entrada de estorno ou da data de estorno em uma linha existente propaga essa alteração para outras linhas no mesmo comprovante. Para otimizar o desempenho, a grade não é atualizada após a propagação de alterações para outras linhas. Você pode exibir os valores atualizados atualizando a grade.



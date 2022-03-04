---
title: Discrepâncias de dados das linhas de ordem de compra
description: Você vê discrepâncias ou corrupção de dados nas linhas de ordem de compra.
author: SmithaNataraj
ms.date: 12/07/2021
ms.topic: troubleshooting
ms.search.form: PurchLineManualCorrection, PurchTable, PurchLine, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-12-07
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: ee2cb9a07c8a00a92c71e3e99d8ec20aa27fb20e
ms.sourcegitcommit: b9799a58d6ec221df86788bc37c4fbd28b435e89
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2022
ms.locfileid: "8100795"
---
# <a name="purchase-order-line-data-discrepancies"></a>Discrepâncias de dados das linhas de ordem de compra

## <a name="symptoms"></a>Sintomas

Ao inspecionar as linhas de uma ordem de compra, você observa um ou mais dos seguintes problemas:

- Há uma discrepância ou corrupção de dados em pendências de linhas de ordem de compra (entrega ou fatura).
- Há corrupção em uma linha de ordem de compra ou no status do cabeçalho.
- Não é possível faturar uma ordem de compra porque, por exemplo, você recebe uma ou mais das seguintes mensagens de erro:

    - "Parado (erro): a transação já foi lançada."
    - "A quantidade não pode ser faturada porque as transações de estoque com status Recebido são insuficientes."
    - "Transações de estoque insuficientes com o status "Comprado" para a %0 quantidade %1 do item."

- Não é possível finalizar ou fechar uma ordem de compra por conta de, por exemplo, um dos seguintes problemas:

    - O botão **Finalizar** não está disponível.
    - Não é possível cancelar a quantidade encomendada de uma linha da ordem de compra para uma ordem de compra que está em um estado confirmado e recebido.

## <a name="cause"></a>Causa

Esses problemas geralmente são causados por corrupção ou uma discrepância de dados nas quantidades pendentes para uma ou mais linhas de ordem de compra.

## <a name="resolution"></a>Resolução

Geralmente, você pode corrigir esses problemas atualizando o status da compra, a entrega pendente e/ou as faturas pendentes para as linhas de ordem de compra relevantes, conforme descrito no procedimento a seguir.

1. Vá para **Compras e fornecimento \> Tarefas periódicas \> Limpeza \> Corrigir linhas de ordem de compra manualmente**.
1. No campo **Ordem de compra**, localize e selecione a ordem de compra que está causando problemas.
1. Na seção **Linhas de ordem de compra**, selecione uma linha na qual você encontrou uma discrepância.
1. Na seção **Transações de estoque**, inspecione os dados mostrados. Se você observar qualquer inconsistência entre uma linha de ordem de compra e suas transações de estoque, selecione um dos seguintes comandos no Painel de Ações, dependendo de onde as inconsistências forem mostradas:

    - **Recalcular \> Recalcular entrega pendente** – Atualize automaticamente os status do cabeçalho e da linha de ordem de compra. Essa função funciona apenas para linhas de ordem de compra em estoque (ou seja, linhas nas quais o item está em estoque). Não há suporte atualmente para itens não estocados e itens de peso variável.
    - **Recalcular \> Recalcular fatura pendente** – Atualize automaticamente os status do cabeçalho e da linha de ordem de compra. Essa função funciona apenas para linhas de ordem de compra em estoque (ou seja, linhas nas quais o item está em estoque). Não há suporte atualmente para itens não estocados e itens de peso variável.
    - **Recalcular \> Recalcular status** – Recalcule o status da linha selecionada. Esse cálculo é baseado na lógica existente. Portanto, os status do cabeçalho e da ordem de compra serão atualizado conforme necessário, com base no novo status da linha de ordem de compra.

1. Se ainda houver inconsistências nas quantidades pendentes, você poderá usar os campos a seguir para editá-las diretamente, conforme necessário:

    - Entrega pendente
    - Lembrete de entrega de estoque
    - A faturar
    - Pendência de fatura de estoque

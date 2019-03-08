---
title: Liquidações do razão
description: Este tópico explica como usar a página de liquidações do razão para liquidar as transações do razão e pagamentos revertidos.
author: mikefalkner
manager: aolson
ms.date: 09/28/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransSettlement
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-11-30
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: b02a1a066913c9959e9a55e78789e5ff1a175c56
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "308474"
---
# <a name="ledger-settlements"></a>Liquidações do razão

[!include [banner](../includes/banner.md)]

Liquidações do razão permitem combinar transações de débito e crédito na contabilidade e marcá-los como liquidados. Assim, você pode garantir que as transações relacionadas sejam excluídas. Você também pode reverter se pagamentos forem feitos por engano.

## <a name="enable-advanced-ledger-settlements"></a>Habilitar liquidações de razão avançado

A página de liquidações de razão avançada fornece funcionalidades adicionais por filtragem e seleção de transações. Para habilitar a página de liquidações de razão avançado, siga estas etapas.

1. Selecione **Contabilidade** \> **Configuração do razão** \> **Parâmetros da contabilidade**. 
2. Na guia **Liquidações do razão**, defina a opção **Pagamento adiantado contábil** como **Sim** para ativar a funcionalidade avançada do razão. A página **Liquidações do razão** será usada quando você selecionar **Liquidações do razão** nas **Tarefas periódicas**. 
3. Você deve inserir a lista de contas a ser usada para pagamentos de contabilidade para cada plano de contas. Esta lista é usada para filtrar a lista de transações que aparecem na página **Liquidações do razão**. Na lista **Plano de contas**, selecione um plano de contas, e depois selecione **Novo** para adicionar novas contas à lista.

## <a name="settle-transactions-by-using-the-advanced-ledger-settlements-page"></a>Liquide transações usando a página de liquidações do razão avançada

Para liquidar as transações do razão, siga estas etapas.

1. Selecione **Contabilidade** \> **Tarefas periódicas** \> **Liquidações do razão**.
2. Definir filtros na parte superior da página:

    - Selecione um intervalo de datas, ou selecione **Código do intervalo de data** para preencher automaticamente o intervalo de datas.
    - Altere o nível de lançamento conforme necessário.
    - Para mostrar separadamente a conta contábil e dimensões, selecione um conjunto de dimensão financeira.

3. Selecione **Exibir transações** para mostrar todas as transações que correspondem aos filtros definidos e a lista de contas que você especificou quando configurar o plano de contas na seção a anterior. Se você alterar qualquer um desses conjuntos de filtros de dimensões, você deve selecionar **Exibir transações** novamente.
4. Selecione uma ou mais linhas que você estiver considerando para liquidação. O campo **Valor selecionado** na parte superior da página aumenta ou diminui a quantidade total nas linhas selecionadas.
5. Depois de terminar a seleção das transações, selecione **Marcar selecionada**. Uma marca de seleção é exibida na coluna **Marcado** para cada transação selecionada. Além disso, o valor do campo **Valor marcado** na parte superior da grade aumenta ou diminui a quantidade total nas linhas marcadas.
6. Quando o **Valor marcado** for **0** (zero), selecione **Transações marcadas de liquidez**. O status das transações marcadas é atualizado para **Liquidado**.

## <a name="make-transactions-easier-to-find"></a>Torne as transações mais fáceis de serem encontradas

A página **Liquidações do razão** inclui recursos que facilitem a visualização das transações que você precisa para liquidação.

- O botão **Desmarcar selecionado** desmarca o campo **Marcado** para todas as linhas selecionadas.
- O filtro **Marcado** permite filtrar as transações baseadas no campo **Marcado**, elas sendo marcadas ou excluídas.
- O filtro **Status** permite filtrar as transações baseadas em seu status como **Liquidado** ou **Não liquidado**.
- O botão **Ordenar pelo valor absoluto** permite classificar os valores pelo valor absoluto, permitindo agrupar os débitos e créditos com a mesma quantidade.

## <a name="reverse-a-settlement"></a>Reverter uma liquidação

Você pode reverter um pagamento feito por engano.

1. Siga as etapas 1 a 3 na seção “Definir transações usando a página de liquidações do razão padrão” para mostrar as transações que você está procurando.
2. No filtro **Status**, selecione **Liquidado**.
3. Selecione uma ou mais linhas que você estiver considerando para estorno. O campo **Valor selecionado** na parte superior da página aumenta ou diminui a quantidade total nas linhas selecionadas.
4. Depois de terminar a seleção das transações, selecione **Marcar selecionada**. Uma marca de seleção é exibida na coluna **Marcado** para cada transação selecionada. Além disso, o valor do campo **Valor marcado** na parte superior da página aumenta ou diminui a quantidade total nas linhas marcadas.
5. Quando o **Valor marcado** for **0** (zero), selecione **Transações marcadas de estorno**. O status das transações marcadas é atualizado para **Não liquidado**.

## <a name="update-the-list-of-accounts-that-are-included-in-the-list-of-transactions"></a>Atualizar a lista de contas que são incluídas na lista de transações

Selecione **Contas contábeis de pagamento** para abrir uma caixa de diálogo onde você pode editar as contas que são incluídas na lista de transações. Selecione **Novo** para adicionar novas contas à lista. Esta lista é usada para filtrar a lista de transações que aparecem na página **Liquidações do razão**.

---
title: Liquidações de razão
description: Este artigo explica como usar a página de liquidações do razão para liquidar as transações do razão e pagamentos revertidos.
author: kweekley
ms.date: 11/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerTransSettlement
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-11-30
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: 6357629f83873437eb62a4839fafd8efd98fffc1
ms.sourcegitcommit: 9041fa6e00ecbdf1a1880659d9bdfff4d888f20e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/22/2022
ms.locfileid: "9800622"
---
# <a name="ledger-settlements"></a>Liquidações do razão

[!include [banner](../includes/banner.md)]

Liquidações do razão é o processo de combinar transações de débito e crédito na contabilidade. A liquidação dos valores de débito e crédito é usada para reconciliar o saldo da conta do razão com as transações detalhadas que compõem esse saldo.

As transações liquidadas podem ser excluídas de consultas e relatórios. Dessa forma, é mais fácil analisar as transações do razão abertas que compõem o saldo da conta do razão.

> [!IMPORTANT] 
> Os módulos das contas a pagar (AP) e contas a receber (AR) também possuem liquidação de faturas e pagamentos. Quando a liquidação ocorre nos livros auxiliares AR e AP, as entradas no razão correspondentes não são liquidadas automaticamente.

## <a name="ledger-settlement-features"></a>Recursos de liquidação do razão
No Microsoft Dynamics 365 Finance, versão 10.0.21, a opção **Habilitar liquidações do razão avançadas** foi removida da página **Parâmetros da contabilidade**. A liquidação do razão avançada agora está sempre habilitada.
Na versão de finanças 10.0.25, o **Reconhecimento entre a liquidação do razão e o recurso de fechamento do exercício** foi introduzido. Este recurso altera a funcionalidade fundamental na liquidação do razão e no fechamento do exercício da contabilidade. Antes de habilitar este recurso no espaço de trabalho **Gerenciamento de recurso**, consulte [Reconhecimento entre a liquidação do razão e o fechamento do exercício](awareness-between-ledger-settlement-year-end-close.md).

## <a name="set-up-ledger-settlement"></a>Configurar liquidação do razão
Você deve selecionar as contas principais para as quais deseja fazer liquidações no razão. Há duas maneiras de selecionar essas contas principais.

1. Vá para **Contabilidade** > **Configuração do razão** > **Parâmetros da contabilidade**.
2. Na guia **Liquidações do razão**, selecionar os gráficos de contas dos quais você deseja selecionar as contas principais.
3. Selecionar as contas principais para as quais executar a liquidação no razão. Como os gráficos de contas são globais, todas as empresas às quais estão atribuídos os gráficos de contas selecionados terão as mesmas contas principais selecionadas para liquidação no razão.

  - ou -

1. Acesse **Contabilidade** > **Tarefas periódicas** > **Liquidações do razão**.
2. Selecione **Contas de liquidação do razão**.
3. Na caixa de diálogo, selecionar os planos de contas e contas principais para liquidações no razão. Esta caixa de diálogo é um atalho. Todas as contas principais adicionadas aqui também serão refletidas na página **Parâmetros da contabilidade**.

Você pode usar os mesmos procedimentos básicos para remover contas principais da liquidação do razão a qualquer momento. A remoção de uma conta principal não tem efeito nas liquidações do razão anteriores. No entanto, a conta e as transações principais não aparecerão mais na página **Liquidação do razão**.

## <a name="settle-transactions"></a><a name="settle-transactions"></a>Liquidar transações
Para liquidar as transações do razão, siga estas etapas.

1. Acesse **Contabilidade** > **Tarefas periódicas** > **Liquidações do razão**.
2. Definir filtros na parte superior da página:

    - Selecione um intervalo de datas. Outra opção é selecionar o código do intervalo de datas para preencher automaticamente o intervalo de datas. Não é recomendável que você faça liquidações do razão para transações que cruzam anos fiscais.
    - Alterar o nível de lançamento conforme necessário. Não é possível liquidar transações em diferentes níveis de lançamento.
    - Para mostrar separadamente a conta principal e dimensões, selecionar um conjunto de dimensão financeira.

3. Selecione **Exibir transações** para mostrar todas as transações que correspondem aos filtros definidos e a lista de contas que você especificou quando configurar o plano de contas na seção a anterior.

    - Se você alterar qualquer um desses conjuntos de filtros de dimensões, você deve selecionar **Exibir transações** novamente.
    - Para filtrar as transações para uma conta principal individual, usar o filtro no campo **Conta do razão**. Não é recomendável que você faça liquidações do razão para transações que são lançadas em contas principais diferentes.

4. Selecionar linhas da liquidação. O valor no campo **Valor selecionado** na parte superior da página aumenta ou diminui para refletir a quantidade total nas linhas selecionadas.
5. Quando acabar de selecionar transações, selecione **Marcar selecionada**. Para cada transação selecionada, uma marca de seleção é exibida na coluna **Marcado**. Além disso, o valor no campo **Valor marcado** na parte superior da grade aumenta ou diminui para refletir a quantidade total nas linhas marcadas.
6. Quando o valor no campo **Valor marcado** for **0** (zero), selecione **Liquidar transações marcadas**. O status das transações marcadas é atualizado para **Liquidado**.

    > [!IMPORTANT]
    > Todas as transações marcadas para liquidação para a entidade legal ativa serão liquidadas, mesmo que não sejam mostradas no momento na página Liquidação do razão porque você aplicou um filtro.

## <a name="make-transactions-easier-to-find"></a>Torne as transações mais fáceis de serem encontradas
A página **Liquidações do razão** inclui recursos que facilitam a exibição das transações necessárias para liquidação.

- Use o filtro **Marcado** para filtrar transações dependendo se a caixa de seleção **Marcado** estiver selecionada para elas.
- Use o filtro **Status** para filtrar transações com base no status.
- Selecionar **Classificar por valor** para classificar os valores por valor absoluto. Dessa forma, você pode agrupar os débitos e os créditos que têm o mesmo valor.

## <a name="reverse-a-settlement"></a>Reverter uma liquidação
Você pode reverter um pagamento feito por engano.

1. Siga as etapas 1 a 3 na seção [Liquidar transações](#settle-transactions) para mostrar as transações do seu interesse.
2. No filtro **Status**, selecione **Liquidado**.
3. Selecionar linhas para estorno.
4. Selecione **Reverter transações marcadas**. O status de todas as transações com a mesma ID de liquidação é atualizado para **Não liquidado**.

    > [!IMPORTANT]
    > Todas as transações com a mesma ID de liquidação serão revertidas, mesmo que não estejam marcadas. Por exemplo, quatro linhas foram marcadas e liquidadas. As quatro linhas têm a mesma ID de liquidação. Se você marcar uma dessas quatro linhas e, depois, selecionar **Reverter transações marcadas**, as quatro linhas serão revertidas.

## <a name="unmark-for-selected-users"></a>Desmarcar para usuários selecionados
Selecione **Desmarcar para usuários selecionados** para desmarcar transações liquidadas do razão para todas as entidades legais por ID de usuário. Por exemplo, isso permitirá que um gerente de contabilidade desmarque transações para um usuário que saiu de férias antes de concluir a liquidação ou para um usuário que saiu da organização. A ação permitirá que essas transações sejam marcadas para liquidação por outro usuário.


## <a name="unmark-all-transactions"></a>Desmarcar todas as transações
Selecione **Desmarcar todas as transações** para desmarcar todas as transações liquidadas do razão para todos os usuários e entidades legais. Esta ação está disponível para a função de administrador.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]

---
title: "Previsão de fluxo de caixa"
description: "Este tópico fornece uma visão geral do processo de previsão de fluxo de caixa. Também explica como a previsão de fluxo de caixa é integrada a outros módulos no sistema."
author: saraschi
manager: AnnBe
ms.date: 05/15/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sarasch
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 75b47611f1c73a3fb771e63dc1dd12cadf8c4b32
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="cash-flow-forecasting"></a>Previsão de fluxo de caixa

[!include[banner](../includes/banner.md)]

É possível usar as ferramentas de previsão de fluxo de caixa para analisar o fluxo de caixa futuro e requisitos de moeda, de forma que você possa estimar a necessidade futura de caixa da empresa. Para obter uma previsão de fluxo de caixa, você deve concluir as seguintes tarefas:

- Identifique e liste todas as contas de liquidez. As contas de liquidez são as contas da empresa para pagamento à vista ou os equivalentes a pagamento à vista.
- Configurar o comportamento de previsões de transações que afetam as contas de liquidez da empresa.

Depois de concluir estas tarefas, você pode calcular e analisar previsões de fluxo de caixa e futuros requisitos de moeda.

## <a name="cash-flow-forecasting-integration"></a>Integração da previsão de fluxo de caixa

A previsão de fluxo de caixa pode ser integrada com Contabilidade, Contas a pagar, Contas a receber, Orçamento e gerenciamento de estoque. O processo de previsão usa informações de transação inseridas no sistema e o processo de cálculo prevê o efeito esperado de caixa de cada transação. Os seguintes tipos de transações são considerados quando o fluxo de caixa é calculado:

- **Ordens de venda** – Ordens de venda que ainda não foram faturadas e que resultam em vendas físicas ou financeiras.
- **Ordens de compra** – Ordens de compra que ainda não foram faturadas e que resultam em compras físicas ou financeiras.
- **Contas a receber** – Transações de cliente abertas (notas fiscais que não foram pagas).
- **Contas a pagar** – Transações do fornecedor abertas (notas fiscais que não foram pagas).
- **Transações do razão** – Transações onde será especificada que uma postagem futura ocorrerá.
- **Entradas de registro de orçamento** – Entradas de registro de orçamento marcadas para previsões de fluxo de caixa.
- **Previsões de demanda** – Linhas do modelo de previsão de estoque selecionadas para previsões de fluxo de caixa.
- **Previsões de fornecimento** – Linhas do modelo de previsão de estoque selecionadas para previsões de fluxo de caixa.

Embora não haja nenhuma integração direta com gerenciamento e contabilidade de projeto, há várias formas para incluir transações de projeto na previsão de fluxo de caixa. As notas fiscais de projeto são lançadas na previsão como parte das transações de cliente abertas. As ordens de venda e ordens de compra iniciadas pelo projeto são incluídas na previsão como ordens abertas após serem inseridas no sistema. Você também pode transferir previsões de projeto para um modelo de orçamento do razão. Esse modelo de orçamento de razão está incluído na previsão de fluxo de caixa como parte das entradas de registro de orçamento.

## <a name="configuration"></a>Configuração

Para configurar o processo de previsão de fluxo de caixa, use a página **Configuração da previsão de fluxo de caixa**. Nesta página, você especifica as contas de liquidez para rastrear e os comportamentos de previsão padrão de cada área.

### <a name="general-ledger"></a>Contabilidade

Primeiro você deve definir as contas de liquidez que você deseja acompanhar pela previsão de fluxo de caixa. Normalmente, essas contas de liquidez são contas principais associadas a contas bancárias que receberão e desembolsarão dinheiro. Na **Configuração da previsão de fluxo de caixa**, na guia **Contabilidade**, selecione as contas principais para incluir para previsões. Se uma conta bancária foi associada à conta principal na página **Conta bancária**, será mostrada no campo **Conta bancária**.

Você pode configurar uma previsão de fluxo de caixa dependente para uma conta principal que contém transações diretamente relacionadas a transações em outra conta principal. Cada linha que você adicionar na seção **Em contas dependentes** cria um valor de previsão de fluxo de caixa em uma conta principal dependente. Esse valor é uma porcentagem dos valores de fluxo de caixa da conta principal principal selecionada.

Primeiro, defina o campo **Conta principal** para a conta principal na qual as transações deviam ocorrer inicialmente. Defina o campo **Conta principal dependente** para a conta que será afetada pela transação inicial com a conta principal. Defina os valores apropriados para os outros campos na linha. Você pode alterar o valor no campo **Percentual** para refletir o efeito da conta principal primária na conta principal do dependente. Para uma previsão de venda ou de compra, selecione um valor de **Condições de pagamento** que seja comum para a maioria dos clientes ou fornecedores. Defina o campo **Tipo de lançamento** para o tipo de lançamento esperado que é relacionado à previsão do fluxo de caixa.

### <a name="accounts-payable"></a>Contas a Pagar

Você pode calcular a previsão de compras usando as opções de configuração na guia **Contas a pagar** da página **Configuração da previsão de fluxo de caixa**. Antes de configurar a previsão de fluxo de caixa para contas a pagar, você deve configurar condições de pagamento, grupos de fornecedores e de perfis de postagem de fornecedor.

Na seção **Padrões de previsão de compras**, selecione os comportamentos de compra padrão para a previsão de fluxo de caixa. Três campos determinam a hora do impacto de caixa: **Tempo entre a data de entrega e a data da fatura**, **Condições de pagamento** e **Tempo entre a data de vencimento da fatura e a data de pagamento**. A previsão usará a definição padrão para o campo **Condições de pagamento** somente se um valor não for especificado na transação. Use uma condição de pagamento para descrever o número mais comum de dias para cada parte do processo.

O campo **Contas de liquidez de pagamentos** especifica a conta de liquidez que é a mais usada normalmente para pagamentos. Use o campo **Porcentagem do valor para alocar a previsão de fluxo de caixa** para especificar se uma porcentagem de valores deve ser usada durante a previsão. Deixe este campo em branco se os valores totais de transação tiverem que ser usados durante a previsão.

Você pode substituir a configuração padrão do campo **Tempo entre a data de vencimento da fatura e a data de pagamento** para grupos de fornecedores específicos. A previsão usará o valor padrão da seção **Padrões de previsão de compras**, a menos que um valor diferente seja especificado para o grupo de fornecedores que está relacionado ao fornecedor na transação. Para substituir o valor padrão, selecione um grupo de fornecedores, e defina o novo valor para o campo **Tempo de compra**.

Você pode substituir a configuração padrão do campo **Conta de liquidez** para perfis de lançamento de fornecedor específicos. A previsão usará o valor padrão da seção **Padrões de previsão de compras**, a menos que uma conta de liquidez diferente seja especificada para o perfil de lançamento que está relacionado ao fornecedor na transação. Para substituir o valor padrão, selecione um perfil de postagem, e depois especifique a conta de liquidez que está prevista para ser afetada.

### <a name="accounts-receivable"></a>Contas a Receber

Você pode calcular a previsão de vendas usando as opções de configuração na guia **Contas a receber** da página **Configuração da previsão de fluxo de caixa**. Antes de configurar a previsão de fluxo de caixa para Contas a receber, você deve configurar condições de pagamento, grupos de clientes e de perfis de postagem de cliente.

Na seção **Padrões de previsão de vendas**, selecione os comportamentos de vendas padrão para a previsão de fluxo de caixa. Três campos determinam a hora do impacto de caixa: **Tempo entre a data de remessa e a data da fatura**, **Condições de pagamento** e **Tempo entre a data de vencimento da fatura e a data de pagamento**. A previsão usará a definição padrão do campo **Condições de pagamento** somente se um valor não for especificado na transação. Use uma condição de pagamento para descrever o número mais comum de dias para cada parte do processo. 

O campo **Contas de liquidez de pagamentos** especifica a conta de liquidez que é a mais usada normalmente para pagamentos. Use o campo **Porcentagem do valor para alocar a previsão de fluxo de caixa** para especificar se uma porcentagem de valores deve ser usada durante a previsão. Deixe este campo em branco se os valores totais de transação tiverem que ser usados durante a previsão.

Você pode substituir a configuração padrão do campo **Tempo entre a data de vencimento da fatura e a data de pagamento** para grupos de clientes específicos. A previsão usará o valor padrão da seção **Padrões de previsão de vendas**, a menos que um valor diferente seja especificado para o grupo de clientes que está relacionado ao cliente na transação. Para substituir o valor padrão, selecione um grupo de clientes, e defina o novo valor para o campo **Tempo de venda**.

Você pode substituir a configuração padrão do campo **Conta de liquidez** para perfis de lançamento de clientes específicos. A previsão usará o valor padrão da seção **Padrões de previsão de vendas**, a menos que uma conta de liquidez diferente seja especificada para o perfil de lançamento que está relacionado ao cliente na transação. Para substituir o valor padrão, selecione um perfil de postagem, e depois defina a conta de liquidez que está prevista para ser afetada.

### <a name="budgeting"></a>Orçamento

Os orçamentos criados a partir de modelos de orçamento podem ser incluídos nas previsões do fluxo de caixa. Na guia **Orçamento** da página **Configuração da previsão de fluxo de caixa**, selecione os modelos de orçamento para incluir na previsão. Por padrão, as novas entradas de registro de orçamento estão incluídas nas previsões depois que o modelo de orçamento é habilitado para a previsão de fluxo de caixa. A inclusão na previsão de fluxo de caixa pode ser substituída em entradas individuais do registro de orçamento.

### <a name="inventory-management"></a>Gerenciamento de estoque

A fonte e previsões de demanda de estoque podem ser incluídas em previsões de fluxo de caixa. Na guia **Gerenciamento de estoque** da página **Configuração da previsão de fluxo de caixa**, selecione os modelos de previsão para incluir na previsão de fluxo de caixa. A inclusão na previsão de fluxo de caixa pode ser substituída em linhas de previsão de demanda e suprimento individual.

### <a name="calculation"></a>Cálculo

Antes de exibir a análise de previsão de fluxo de caixa, você deve executar o processo de cálculo de fluxo de caixa. O processo de cálculo projetará os impactos futuros de dinheiro das transações inseridas.

Calcule a previsão de fluxo de caixa com a página **Calcular previsões de fluxo de caixa**. Você pode calcular a previsão de fluxo de caixa completa ou uma previsão de fluxo de caixa incremental. 

- Para limpar todas as transações de previsão de fluxo de caixa e recalcular, defina o campo **Método de cálculo de previsão de fluxo de caixa** como **Total**. Recomenda-se usar esta abordagem se você não tiver atualizado as previsões de fluxo de caixa durante um bom tempo. 
- Para atualizar informações existentes do fluxo de caixa somente para novas transações, defina o campo **Método de cálculo de previsão de fluxo de caixa** para **Novo**. A página mostrará a data em que o cálculo do fluxo de caixa foi executado pela última vez.

Você também pode usar o processamento em lotes para a previsão de fluxo de caixa. Para ajudar a garantir que a análise de previsão será atualizada regularmente, configure um processo em lote recorrente para o cálculo de previsão de fluxo de caixa.

### <a name="reporting"></a>Relatório

Após o cálculo de previsão de fluxo de caixa, é necessário atualizar informações associadas da entidade para o relatório analítico. Na página **Repositório de entidades**, selecione a medida, **Agregação de LedgerCovLiquidityMeasurement** e clique em **Atualizar**.

Há dois espaços de trabalho que contêm dados de previsão de fluxo de caixa. Um espaço de trabalho tem dados de todas as empresas, e outro espaço de trabalho tem dados somente da empresa atual.

O acesso ao espaço de trabalho de todas as empresas é controlado pelo direito **Exibir espaço de trabalho de todas as empresas do fluxo de caixa**. Por padrão, o espaço trabalho **Visão geral de caixa - todas as empresas** está disponível nas seguintes funções:

- Diretor executivo
- Diretor financeiro
- Controlador financeiro

O acesso ao espaço de trabalho para a empresa atual é controlado pelo direito **Exibir espaço de trabalho da empresa atual do fluxo de caixa**. Por padrão, o espaço de trabalho **Visão geral de caixa - empresa atual** está disponível nas seguintes funções:

- Contador
- Gerente de contabilidade
- Supervisor de contabilidade
- Gerente de contas a pagar
- Gerente de contas a receber

O espaço de trabalho **Visão geral de caixa – todas as empresas** mostra a análise da previsão de fluxo de caixa na moeda do sistema. A moeda do sistema e o tipo de taxa de câmbio de sistema usados para a análise são definidos na página **Parâmetros do sistema**. Este espaço de trabalho mostra uma visão geral dos saldos da conta bancária e de previsão de fluxo de caixa para todas as empresas. Um plano dos fluxos de entrada e de saída de caixa oferece uma visão geral dos movimentos futuros de caixa e os saldos na moeda do sistema, com informações detalhadas sobre as transações de previsão. Você também pode consultar os saldos da moeda previstos.

O espaço de trabalho **Visão geral de caixa – empresa atual** mostra a análise da previsão de fluxo de caixa na moeda contábil definida da empresa. A moeda contábil usada para a análise é definida na página **Razão**. Este espaço de trabalho mostra uma visão geral dos saldos da conta bancária e de previsão de fluxo de caixa para a empresa atual. Um plano dos fluxos de entrada e de saída de caixa oferece uma visão geral dos movimentos futuros de caixa e os saldos na moeda contábil, com informações detalhadas sobre as transações de previsão. Você também pode consultar os saldos da moeda previstos.

Para obter mais informações sobre a análise da previsão de fluxo de caixa, consulte o tópico de conteúdo Visão geral de caixa do Power BI.

Além disso, é possível exibir dados de previsão de fluxo de caixa para contas, ordens e itens específicos nas páginas seguintes:

- **Balancete**: Selecione **Previsões de fluxo de caixa** para exibir os fluxos de caixa futuros para a conta principal selecionada.
- **Todas as ordens de venda**: Na guia **Fatura**, selecione **Previsões de fluxo de caixa** para exibir o efeito esperado de caixa da ordem de venda selecionada.
- **Todas as ordens de compra**: Na guia **Fatura**, selecione **Previsões de fluxo de caixa** para exibir o efeito esperado de caixa da ordem de compra selecionada.
- **Previsão de fornecimento**: Selecione **Previsões de fluxo de caixa** para exibir os fluxos de caixa futuros associados à previsão de fornecimento de itens selecionada.
- **Previsão de demanda**: Selecione **Previsões de fluxo de caixa** para exibir os fluxos de caixa futuros associados à previsão de demanda de itens selecionada.



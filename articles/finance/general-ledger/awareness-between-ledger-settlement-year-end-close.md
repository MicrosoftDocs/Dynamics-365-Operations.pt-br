---
title: Reconhecimento entre a liquidação do razão e o fechamento do exercício
description: Este artigo fornece informações sobre aperfeiçoamentos que afetam as liquidações do razão e o fechamento anual da contabilidade.
author: kweekley
ms.date: 04/06/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-31
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: b0c454745bc02a101514d44a20bd47dad0c548d5
ms.sourcegitcommit: 2804b05214c87f76457608b5db072582ff339852
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2022
ms.locfileid: "9815674"
---
# <a name="awareness-between-ledger-settlement-and-year-end-close"></a>Reconhecimento entre a liquidação do razão e o fechamento do exercício

[!include [banner](../includes/banner.md)]


No Microsoft Dynamics 365 Finance versão 10.0.25, o recurso **Reconhecimento entre a liquidação do razão e o fechamento do exercício** está disponível no espaço de trabalho **Gerenciamento de recursos**. Este recurso adiciona dois aprimoramentos principais que afetam a liquidação do razão e o fechamento do ano da contabilidade.

Durante o fechamento do exercício da contabilidade, as transações do razão que foram liquidadas não serão mais incluídas no saldo inicial do próximo ano fiscal. Esse aperfeiçoamento garante que somente as transações do razão não liquidadas sejam incluídas no saldo inicial. É importante quando a reavaliação de moeda estrangeira da contabilidade é executada. A reavaliação de moeda estrangeira é executada somente para transações do razão com status **Não liquidado**. No entanto, antes da liberação do recurso **Reconhecimento entre a liquidação do razão e o recurso de fechamento do exercício**, o saldo inicial resumiu a transação com status **Liquidado** e **Não liquidado**; o status do valor resumido foi definido como **Não liquidado**.

A segunda melhoria permite lançar transações de saldo inicial detalhado durante o fechamento do exercício da contabilidade. Se a opção **Manter detalhes durante o fechamento do exercício** estiver definida como **Sim**, um saldo inicial separado será criado para cada transação do razão não liquidada. Essa configuração é definida para cada conta principal na configuração de liquidação do razão. Ao manter transações detalhadas do saldo inicial, você aumenta muito a capacidade de liquidar as transações do razão não liquidadas no próximo ano fiscal.

Para dar suporte aos novos aperfeiçoamentos, foram feitas alterações na liquidação do razão e no fechamento do exercício.

### <a name="changes-to-ledger-settlement"></a>Alterações na liquidação do razão

- A liquidação do razão deve ser feita em um ano fiscal.
- A liquidação do razão deve ser feita para transações em uma única conta principal. A conta principal é agora um filtro necessário na página **liquidação do razão**.
- Liquidações do razão e a reversão da liquidação do razão não podem ser feitas para transações lançadas em um exercício fechado (em outras palavras, o fechamento do exercício foi executado).

### <a name="changes-to-year-end-close"></a>Alterações no fechamento do exercício

- Um fechamento de exercício não poderá ser revertido se uma transação de saldo inicial for liquidada no próximo ano fiscal. Essa alteração se aplica quando um fechamento de exercício é revertido, ou quando um fechamento de exercício é executado novamente e a opção **Excluir entradas de fechamento do exercício existentes ao fechar novamente o ano** está definida como **Sim** em parâmetros da contabilidade.
- Se a opção **Manter detalhes durante o fechamento do exercício** estiver definida como **Sim** para qualquer conta de balanço na liquidação do razão, as transações de saldo inicial mais detalhadas serão criadas para essa conta principal.

## <a name="before-you-enable-the-feature"></a>Antes de habilitar o recurso

Devido às alterações na funcionalidade e no modelo de dados, é importante considerar os seguintes pontos antes de habilitar o recurso:

- Como somente as transações liquidadas são trazidas para o saldo inicial, você deve desliquidar transações do ano fiscal atual que são liquidadas com transações no ano fiscal anterior. As transações devem ser reliquidadas em relação a transações no ano fiscal atual. Isso pode ser feito por meio de uma entrada de ajuste no ano fiscal atual. O ajuste inverte os saldos iniciais resumidos e as compensações com a transação detalhada necessária para liquidar as entradas do razão no ano atual. 

  > [!IMPORTANT]
  > Se isso não for feito, você receberá o erro **sem saldo** quando executar o fechamento do final do ano para o ano fiscal atual. Se não for possível fazer a desliquidação e liquidar novamente as transações do razão com o mesmo ano fiscal, não habilite este recurso até que o fechamento do fim de ano seja concluído. Habilite o recurso imediatamente depois que o fechamento de fim de ano for concluído e antes que as novas transações do razão sejam liquidadas no próximo ano fiscal. 
  
- Todas as transações marcadas para liquidação, mas não liquidadas, serão automaticamente desmarcadas quando o recurso for habilitado. Para evitar a perda de trabalho, liquide todas as transações marcadas antes de habilitar o recurso.
- Algumas organizações executam o fechamento do exercício várias vezes para o mesmo ano fiscal. Não habilite o recurso se o fechamento do exercício já tiver sido executado uma vez e será executado novamente para o mesmo ano fiscal. O recurso deve estar habilitado para que você processe o fechamento do primeiro exercício ou depois de processar o fechamento do exercício para o ano fiscal.

  Se você desejar habilitar o recurso, mas o fechamento de exercício já tiver sido executado uma vez, você deverá reverter o fechamento do exercício antes de habilitar o recurso.

- Como a liquidação em contas principais não é mais permitida, ajuste o plano de contas ou os processos, conforme necessário, para garantir que a liquidação do razão possa ser feita na mesma conta principal.
- O recurso não poderá ser habilitado se o processo de fechamento de exercício do setor público estiver sendo usado.

## <a name="set-up-ledger-settlement"></a>Configurar liquidação do razão

Depois de habilitar o recurso e antes de executar o próximo fechamento de exercício, cada organização deve determinar se manterá os detalhes da transação durante o fechamento do exercício. A opção não tem impacto sobre os lançamentos de saldo inicial de processos de fechamento de exercício anterior.

A opção **Manter detalhes durante o fechamento do exercício** é definida para cada conta principal na página **Configuração de liquidação do razão**.

1.  Vá para **Contabilidade** > **Configuração do razão** > **Parâmetros da contabilidade**.
2.  Na guia **Liquidações do razão**, selecione **Contas de liquidação do razão**.

- ou -

1.  Acesse **Contabilidade** > **Tarefas periódicas** > **Liquidações do razão**.
2.  Selecione **Contas de liquidação do razão**.

Duas colunas foram adicionadas à página **Liquidações do razão**:
    
- **Tipo de conta principal**: esta coluna é somente para fins informativos. Ela mostra o tipo atribuído à conta principal.
- **Manter detalhes durante o fechamento do exercício**: por padrão, a opção está definida como **Não**. Ela só poderá ser definida como **Sim** se o valor na coluna **Tipo de conta principal** for **Balanço**, **Ativo** ou **Passivo**. Quando a opção for definida como **Não**, os saldos iniciais serão lançados no resumo, como é comum durante o fechamento do exercício. Se estiver definida como **Sim**, os saldos iniciais serão criados em detalhes para cada transação do razão que não esteja liquidada para a conta principal.

## <a name="year-end-close"></a>Fechamento do exercício

Ao executar o fechamento do exercício acessando **Contabilidade** > **Fechamento de período** > **Fechamento do exercício**, o processo cria os saldos iniciais para as contas principais definidas para liquidação do razão. Os saldos iniciais são criados em resumo ou detalhes, dependendo da configuração de liquidação do razão. O processo exclui as transações do razão que são liquidadas, independentemente de você lançar o saldo inicial para cada conta principal em resumo ou em detalhes.

Por exemplo, várias transações são lançadas na conta principal 130100 no ano fiscal 2021.

| Número do diário | Comprovante  | Data       | Tipo      | Conta contábil | Nome da conta        | Descrição       | Moeda | Valor na moeda de transação | Valor  | Valor na moeda de relatório |
|----------------|----------|------------|-----------|----------------|---------------------|-------------------|----------|--------------------------------|---------|------------------------------|
| 20853          | FTV-3000 | 03/12/2021  | Em operação | 130100-001-    | Contas a Receber | Taxa de serviço       | USD      | 100                            | 100     | 100                          |
| 20855          | FTV-3004 | 05/12/2021  | Em operação | 130100-002-    | Contas a Receber | Utilitários         | USD      | 175                            | 175     | 175                          |
| 20854          | CMV-4000 | 16/12/2021 | Em operação | 130100-001-    | Contas a Receber | Reembolso            | USD      | -100                           | -100    | -100                         |
| 20851          | ARP-8000 | 20/12/2021 | Em operação | 130100-002-    | Contas a Receber |                   | USD      | -0,88                          | -0,88   | -0,88                        |
| 20853          | ARPM0004 | 20/12/2021 | Em operação | 130100-002-    | Contas a Receber |                   | EUR      | -127,11                        | -174,12 | -174,12                      |
| 20856          | CMV-4010 | 21/12/2021 | Em operação | 130100-002-    | Contas a receber | Crédito por conta | USD      | -175                           | -175    | -175                         |
| 20857          | FTV-3011 | 28/12/2021 | Em operação | 130100-001-    | Contas a Receber | Utilitários         | USD      | 400                            | 400     | 400                          |
| 20910          | FTV-3020 | 29/12/2021 | Em operação | 130100-002-    | Contas a Receber | Serviço           | USD      | 300                            | 300     | 300                          |

Dessas transações, três são liquidadas durante a liquidação do razão.

Há uma fatura para 175 dólares americanos (USD 175). Essa fatura foi paga em euros (EUR) e um desconto à vista foi tirado.

| Número do diário | Comprovante  | Data       | Tipo      | Conta contábil | Nome da conta        | Descrição | Moeda | Valor na moeda de transação | Valor  | Valor na moeda de relatório |
|----------------|----------|------------|-----------|----------------|---------------------|-------------|----------|--------------------------------|---------|------------------------------|
| 20855          | FTV-3004 | 05/12/2021  | Em operação | 130100-002-    | Contas a Receber | Utilitários   | USD      | 175                            | 175     | 175                          |
| 20851          | ARP-8000 | 20/12/2021 | Em operação | 130100-002-    | Contas a Receber |             | USD      | -0,88                          | -0,88   | -0,88                        |
| 20853          | ARPM0004 | 20/12/2021 | Em operação | 130100-002-    | Contas a Receber |             | EUR      | -127,11                        | -174,12 | -174,12                      |

Os resultados da conta principal 130100 dependem do fato de o recurso estar habilitado antes da execução do fechamento do exercício. Se o recurso estiver habilitado, o resultado também dependerá da configuração da opção Manter detalhes durante o fechamento do exercício.

### <a name="the-feature-isnt-enabled"></a>O recurso não está habilitado
O fechamento do exercício cria três transações de saldo inicial para a conta principal 130100 em 2022. A soma das transações na moeda contábil é de USD 525.

| Número do diário | Comprovante  | Data     | Tipo    | Conta contábil | Nome da conta        | Descrição | Moeda | Valor na moeda de transação | Valor  | Valor na moeda de relatório |
|----------------|----------|----------|---------|----------------|---------------------|-------------|----------|--------------------------------|---------|------------------------------|
| 20910          | YEC_2021 | 1/1/2022 | Abertura | 130100-002-    | Contas a Receber |             | USD      | 299,12                         | 299,12  | 299,12                       |
| 20910          | YEC_2021 | 1/1/2022 | Abertura | 130100-001-    | Contas a Receber |             | USD      | 400                            | 400     | 400                          |
| 20910          | YEC_2021 | 1/1/2022 | Abertura | 130100-002-    | Contas a Receber |             | EUR      | -127,11                        | -174,12 | -174,12                      |

Embora a transação do pagamento de EUR -127,11 tenha sido liquidada no razão, a transação ainda é reportada como um saldo inicial.

### <a name="feature-is-enabled-and-keep-detail-during-year-end-close--no"></a>O recurso está habilitado e Manter detalhes durante o fechamento do exercício = Não

O fechamento do exercício cria duas transações de saldo inicial para a conta principal 130100 em 2022. A soma das transações na moeda contábil ainda é de USD 525, mas as transações liquidadas do razão são excluídas do saldo inicial. O valor total da conta 130100-002- é de USD 125, e não de USD 299,12; a transação de EUR 127,11/USD 174,12 é totalmente excluída.

| Número do diário | Comprovante  | Data     | Tipo    | Conta contábil | Nome da conta        | Descrição | Moeda | Valor na moeda de transação | Valor | Valor na moeda de relatório |
|----------------|----------|----------|---------|----------------|---------------------|-------------|----------|--------------------------------|--------|------------------------------|
| 20910          | YEC_2021 | 1/1/2022 | Abertura | 130100-002-    | Contas a Receber |             | USD      | 125                            | 125    | 125                          |
| 20910          | YEC_2021 | 1/1/2022 | Abertura | 130100-001-    | Contas a Receber |             | USD      | 400                            | 400    | 400                          |

### <a name="feature-is-enabled-and-keep-detail-during-year-end-close--yes"></a>O recurso está habilitado e Manter detalhes durante o fechamento do exercício = Sim

O fechamento do exercício cria cinco transações de saldo inicial para a conta principal 130100 em 2022. Uma transação de saldo inicial separada é criada para cada uma das cinco transações que não foram liquidadas. A soma das transações na moeda contábil ainda é de USD 525.

| Número do diário | Comprovante  | Data     | Tipo    | Conta contábil | Nome da conta        | Descrição       | Moeda | Valor na moeda de transação | Valor | Valor na moeda de relatório |
|----------------|----------|----------|---------|----------------|---------------------|-------------------|----------|--------------------------------|--------|------------------------------|
| 20910          | YEC_2021 | 1/1/2022 | Abertura | 130100-001-    | Contas a Receber | Taxa de serviço       | USD      | 100                            | 100    | 100                          |
| 20910          | YEC_2021 | 1/1/2022 | Abertura | 130100-001-    | Contas a Receber | Reembolso            | USD      | -100                           | -100   | -100                         |
| 20910          | YEC_2021 | 1/1/2022 | Abertura | 130100-002-    | Contas a Receber | Crédito por conta | USD      | -175                           | -175   | -175                         |
| 20910          | YEC_2021 | 1/1/2022 | Abertura | 130100-001-    | Contas a Receber | Utilitários         | USD      | 400                            | 400    | 400                          |
| 20910          | YEC_2021 | 1/1/2022 | Abertura | 130100-002-    | Contas a Receber | Serviço           | USD      | 300                            | 300    | 300                          |

Quando os detalhes da transação são mantidos, as transações detalhadas originais não são afetadas. Elas permanecem lançadas e não liquidadas no exercício que está sendo fechado. Uma cópia dessas transações é criada para o saldo inicial. Os valores a seguir das transações originais são copiados para as transações de saldo inicial.

- Conta contábil (a conta principal e todas as dimensões financeiras)
- Os valores na transação, contabilidade e moedas de relatório
- Descrição
- Nível de lançamento
- Tipo de lançamento

   > [!NOTE]
   > Nenhuma outra transação de saldo inicial recebe um tipo de lançamento. Portanto, o tipo de lançamento pode ser usado para diferenciar transações de abertura que foram apresentadas em detalhes.

Alguns campos das transações originais devem ser alterados nas transações de saldo inicial detalhadas. A data de transações de saldo inicial é sempre o primeiro dia do próximo ano fiscal. O número do diário deve ser alterado e o número do comprovante é alterado para o valor inserido na caixa de diálogo fechamento do exercício.

As informações das transações originais podem ser encontradas na página **Liquidação do razão**. Cada transação de saldo inicial detalhado mostra a coluna **Data da transação original** na grade. Esta coluna pode ajudá-lo a fazer a correspondência de transações no novo ano fiscal. Você pode selecionar **Exibir comprovante original** para reverter ao comprovante original completo.

## <a name="settle-transactions"></a><a name="settle-transactions"></a>Liquidar transações
Para liquidar as transações do razão, siga estas etapas.

1. Acesse **Contabilidade** > **Tarefas periódicas** > **Liquidações do razão**.
2.  Defina os filtros na parte superior da página.

    1. Selecione um intervalo de datas. Outra opção é selecionar o código do intervalo de datas para preencher automaticamente o intervalo de datas.

       - O intervalo de datas não pode cruzar anos fiscais. Se o intervalo de datas cruzar anos fiscais, nenhuma transação será mostrada quando você selecionar **Exibir transações**.
       - Se o intervalo de datas for em um exercício aberto, as transações poderão ser liquidadas e a liquidação poderá ser revertida. Se o intervalo de datas estiver em um exercício fechado ou se o fechamento do exercício for concluído, as transações serão mostradas, mas não poderão ser liquidadas ou não liquidadas. Você só pode desmarcar transações em um exercício fechado. Se o intervalo de datas estiver em um exercício fechado, os botões **Marcar selecionada**, **Liquidar transações marcadas** e **Reverter transações marcadas** não estarão disponíveis.

    2. Selecione a conta principal para mostrar transações. Este campo é obrigatório. A pesquisa mostra somente as contas principais que estão selecionadas na página **Liquidação do razão** para o plano de contas da empresa.
    3. Selecione o nível de lançamento. Não é possível liquidar transações em diferentes níveis de lançamento.
    4. Para mostrar a conta contábil e dimensões em colunas separadas, selecione um conjunto de dimensão financeira.

3.  Selecione **Exibir transações** para mostrar todas as transações que correspondam aos filtros definidos. Se você alterar qualquer um desses conjuntos de filtros de dimensões, você deve selecionar **Exibir transações** novamente.
4.  Selecionar linhas da liquidação. O valor no campo **Valor selecionado** na parte superior da página aumenta ou diminui para refletir a quantidade total nas linhas selecionadas.
5.  Quando acabar de selecionar transações, selecione **Marcar selecionada**. Para cada transação selecionada, uma marca de seleção é exibida na coluna **Marcado**. Além disso, o valor no campo **Valor marcado** na parte superior da grade aumenta ou diminui para refletir a quantidade total nas linhas marcadas.
6.  Quando o valor no campo **Valor marcado** for **0** (zero), selecione **Liquidar transações marcadas**.

    - A liquidação parcial não é permitida. Por exemplo, não é possível liquidar uma transação de débito de $100 com uma transação de crédito de $90. A transação de crédito de $10 restante também deve ser marcada para inclusão na liquidação.
    - Insira uma data de liquidação. A data deve ser igual ou posterior à data mais recente das transações marcadas para liquidação.

O status das transações marcadas é atualizado para **Liquidado**.

> [!IMPORTANT]
> Todas as transações marcadas para liquidação para a entidade legal ativa e a conta principal selecionada serão liquidadas. As transações não precisam aparecer na página. Elas serão liquidadas mesmo que estejam ocultas por causa de um filtro.

Alguns processos, como a reversão de uma transação, liquidam automaticamente transações do razão. Por exemplo, um pagamento e uma fatura são liquidados em Contas a receber e a liquidação gera uma ganho/perda realizada. A liquidação do pagamento e da fatura não liquida transações do razão, como transações da conta contábil de Contas a receber. No entanto, se o pagamento e a fatura forem não liquidados em Contas a receber, a entrada contábil revertida que foi lançada durante o estorno da liquidação de Contas a receber fará com que as entradas de contabilidade original e revertida sejam liquidadas no razão. Quando o recurso **Reconhecimento entre a liquidação do razão e o recurso de fechamento do exercício** estiver habilitado, a liquidação do razão de um estorno não ocorrerá automaticamente se a data do estorno estiver em um exercício diferente.

## <a name="use-excel-for-ledger-settlement"></a>Usar Excel para liquidação do razão

As transações mostradas na página **Liquidação do razão** podem ser exportadas para o Excel. No Excel, você pode filtrar ainda mais transações para determinar quais transações devem ser marcadas para liquidação.
Ambas as entidades de liquidação do razão exportam transações do razão somente para a conta principal selecionada na página **Liquidação do razão**. Embora as transações de exercícios fechados ainda possam ser marcadas ou desmarcadas usando o Excel, elas não podem ser liquidadas. Além disso, as transações liquidadas não podem ser revertidas para esse ano fiscal.

## <a name="make-transactions-easier-to-find"></a>Torne as transações mais fáceis de serem encontradas

A página **Liquidações do razão** inclui recursos que facilitam a exibição das transações necessárias para liquidação.

•   Use o filtro **Marcado** para filtrar transações dependendo se a caixa de seleção **Marcado** está selecionada para elas.
•   Use o filtro **Status** para filtrar transações com base no status.
•   Selecione **Classificar por valor absoluto** para classificar os valores por valor absoluto. Dessa forma, você pode agrupar os débitos e os créditos que têm o mesmo valor.

## <a name="reverse-a-settlement"></a>Reverter uma liquidação

Você pode reverter um pagamento feito por engano.

1.  Siga as etapas 1 a 3 na seção [Liquidar transações](#settle-transactions) para mostrar as transações do seu interesse.
2.  No filtro **Status**, selecione **Liquidado**.
3.  Selecionar linhas para estorno.
4.  Selecione **Reverter transações marcadas**. O status de todas as transações com a mesma ID de liquidação é atualizado para **Não liquidado**.

> [!IMPORTANT]
> Todas as transações com a mesma ID de liquidação serão revertidas, mesmo que não estejam marcadas. Por exemplo, quatro linhas foram marcadas e liquidadas. As quatro linhas têm a mesma ID de liquidação. Se você marcar uma dessas quatro linhas e, depois, selecionar **Reverter transações marcadas**, as quatro linhas serão revertidas.







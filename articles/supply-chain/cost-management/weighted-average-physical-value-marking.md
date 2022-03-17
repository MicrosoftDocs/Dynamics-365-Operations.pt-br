---
title: Média ponderada com valor físico e marcação
description: A média ponderada é um modelo de estoque com base no princípio da média ponderada, no qual as saídas do estoque são avaliadas no valor médio dos itens recebidos no estoque durante o período de fechamento de estoque, mais qualquer estoque disponível do período anterior.
author: AndersGirke
ms.date: 02/21/2022
ms.topic: article
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 65501
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6c124716b70be837573506a738ef2034397f2bda
ms.sourcegitcommit: addae271ddfc5a8b0721c23337f69916153db4cd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2022
ms.locfileid: "8330217"
---
# <a name="weighted-average-with-physical-value-and-marking"></a>Média ponderada com valor físico e marcação

[!include [banner](../includes/banner.md)]

A média ponderada é um modelo de estoque baseado em uma média que resulta da multiplicação de cada componente (transação de item) por um fator (preço de custo) que reflete sua importância (quantidade). Outra forma de dizer isso é que a média ponderada é um modelo de estoque que atribui o custo de transações de saída com base no valor médio de todo o estoque recebido durante o período, além de qualquer estoque disponível do período anterior.

Quando você executa um fechamento de estoque usando o modelo de estoque de média ponderada, há duas maneiras de criar uma liquidação. Em geral, todos os recebimentos são liquidados em relação a uma saída virtual, que armazena a quantidade e o valor totais recebidos. Essa saída virtual possui um recebimento virtual correspondente a partir do qual as saídas são liquidadas. Dessa forma, todas as saídas obtêm o mesmo custo médio. A saída e o recebimento virtuais podem ser vistos como uma transferência virtual, que é chamada de *transferência de fechamento de estoque de média ponderada*. Esse método de liquidação é chamado de *liquidação resumida de média ponderada*. Se houver somente um recebimento, todas as saídas poderão ser liquidadas a partir dele e a transferência virtual não será criada. Esse método de liquidação é chamado de *liquidação direta*. Qualquer estoque disponível após o fechamento do estoque é executado na média ponderada do período anterior e incluído no cálculo de média ponderada no próximo período.

Você pode substituir o princípio de média ponderada, marcando transações de estoque de forma que o recebimento de um item específico seja liquidado em relação a uma saída específica. Um fechamento de estoque periódico é exigido quando você usa o modelo de estoque de média ponderada para gerar liquidações e ajustar valores de acordo com o princípio de média ponderada. Até que você execute o processo de fechamento de estoque, as transações de saída são avaliadas na média de execução quando ocorreram atualizações físicas e financeiras. A menos que você esteja usando marcação, a média de execução é calculada quando a atualização física ou financeira é executada.

O método de custo de estoque da média ponderada é calculado pelo seguinte fórmula:

- Média ponderada = (\[Q1 × P1\] + \[Q2 × P2\] + \[Q *n* × P *n*\]) ÷ (Q1 + Q2 + Q *n*)

Q = quantidade da transação  
P = preço da transação

As liquidações são lançamentos de fechamento de estoque que ajustam as saídas para a média ponderada correta a partir da data de fechamento. Os seguintes exemplos ilustram o efeito do uso da média ponderada com cinco configurações diferentes:

- Liquidação direta de média ponderada sem a opção **Incluir valor físico**
- Liquidação resumida de média ponderada sem a opção **Incluir valor físico**
- Liquidação direta de média ponderada com a opção **Incluir valor físico**
- Liquidação resumida de média ponderada com a opção **Incluir valor físico**
- Média ponderada com a marcação

## <a name="weighted-average-direct-settlement-without-include-physical-value"></a>Liquidação direta de média ponderada sem incluir valor físico

O princípio de liquidação direta cria liquidações diretamente entre recebimentos e saídas sem criar outras transações de estoque. O sistema usa esse princípio de liquidação direta nestas situações:

- Um recebimento e uma ou mais saídas foram lançadas no período.
- Somente saídas foram lançadas no período e o estoque contém itens disponíveis de um fechamento anterior.

Neste exemplo, a caixa de seleção **Incluir valor físico** está desmarcada no **Grupo de modelos do item** para o produto liberado. A ilustração a seguir mostra estas transações:

- 1a. Recebimento físico de estoque para uma quantidade de 10 ao custo de BRL 10,00 cada.
- 1b. Recebimento financeiro de estoque para uma quantidade de 10 ao custo de BRL 10,00 cada.
- 2a. Recebimento físico de estoque para uma quantidade de 10 ao custo de BRL 20,00 cada.
- 3a. Saída física de estoque para uma quantidade de 1 ao preço de custo de USD 10,00 (média ponderada de transações lançadas financeiramente).
- 3b. Saída financeira de estoque para uma quantidade de 1 ao preço de custo de USD 10,00 (média ponderada de transações lançadas financeiramente).
- 4a. Saída física de estoque para uma quantidade 1 ao preço de custo de USD 10,00 cada (média de transações lançadas financeiramente).
- 4b. Saída financeira de estoque para uma quantidade 1 ao custo de USD 10,00 cada (média de execução de transações lançadas financeiramente).
- 5a. Saída física de estoque para uma quantidade 1 ao preço de custo de USD 10,00 cada (média de transações lançadas financeiramente).
- 6\. O fechamento de estoque é executado. Com base no método de média ponderada, o sistema usa o método de liquidação direta porque somente um recebimento é atualizado financeiramente no período. Neste exemplo, uma liquidação é criada entre 1b e 3b, e outra entre 1b e 4b. Nenhum ajuste é feito porque a média de execução é igual à média ponderada.

O diagrama a seguir ilustra essa série de transações com os efeitos de escolher o modelo de estoque de média ponderada e o princípio de liquidação direta sem a opção **Incluir valor físico**.

![DS de média ponderada sem Incluir Valor físico.](media/weighted-average-direct-settlement-without-include-physical-value.png)

**Chave para o diagrama**

- As transações de estoque são representadas por setas verticais.
- As transações físicas são representadas por setas cinza menores.
- As transações financeiras são representadas por setas mais longas em preto.
- Os recebimentos no estoque são representados por setas verticais sobre o eixo.
- Saídas fora do estoque são representadas por setas verticais abaixo do eixo.
- Cada nova transação de recebimento ou saída é designada por uma nova etiqueta.
- Cada seta vertical é rotulada com um identificador sequencial, como *1a*. Os identificadores indicam a ordem de lançamentos de transação de estoque na linha do tempo.
- Cada data no diagrama é separada por uma linha vertical preta fina. A data é indicada na parte inferior do diagrama.
- Os fechamentos de estoque são representados por uma linha tracejada vertical vermelha.
- As liquidações executadas pelo fechamento de estoque são representadas por linhas tracejadas diagonais de um recebimento para uma saída.

## <a name="weighted-average-summarized-settlement-without-the-include-physical-value-option"></a>Liquidação resumida de média ponderada sem a opção Incluir valor físico

Quando há vários recebimentos em um período, a média ponderada usa o princípio de liquidação resumido em que todos os recebimentos em um período de fechamento são resumidos em uma transação chamada *fechamento de estoque de média ponderada*. Todos os recebimentos do período serão liquidados em relação à saída da transação de estoque recém-criada. Todas as saídas para o período serão liquidadas em relação ao recebimento da nova transação de estoque. Se houver valor de estoque restante disponível depois do fechamento de estoque, o valor do estoque disponível será incluído na transação de recebimento de transações de fechamento de estoque de média ponderada.

As seguintes transações são ilustradas neste gráfico:

- 1a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 10,00 cada.
- 1b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 10,00 cada.
- 2a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 20,00 cada.
- 2b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 22,00 cada.
- 3a. Saída física de estoque para uma quantidade de 1 ao preço de custo de USD 16,00 (média ponderada de transações lançadas financeiramente).
- 3b. Saída financeira de estoque para uma quantidade de 1 ao preço de custo de USD 16,00 (média ponderada de transações lançadas financeiramente).
- 4a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 25,00 cada.
- 5a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 30,00 cada.
- 5b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 30,00 cada.
- 6a. Saída física de estoque para uma quantidade de 1 ao preço de custo de USD 23,00 (média ponderada de transações lançadas financeiramente).
- 7\. O fechamento de estoque é executado.
- 7a. A saída financeira de transação de fechamento de estoque de média ponderada é criada para somar as liquidações para todos os recebimentos financeiros de estoque.
  - A transação 1b é liquidada para uma quantidade 1 com um valor liquidado de USD 10,00.
  - A transação 2b é liquidada para uma quantidade 1 com um valor liquidado de USD 22,00.
  - A transação 5b é liquidada para uma quantidade 1 com um valor liquidado de USD 30,00.
  - A transação 7a é criada para uma quantidade 3 com um valor liquidado de USD 62,00. Esta transação desloca a soma das três transações de recibo financeiramente atualizadas no período.
- 7b. Um recebimento financeiro de transação de fechamento de estoque de média ponderada é criado como a compensação para saídas lançadas financeiramente.
  - A transação 3b é liquidada para uma quantidade 1 com um valor liquidado de USD 20,67. Essa transação é ajustada por USD 4,67 para passar o valor original de USD 16,00 para 20,67, que é a média ponderada de transações lançadas financeiramente para o período.
  - A transação 7b é criada para uma quantidade 1 com um valor liquidado de USD 20,67 para compensação 3b. Esta transação desloca a soma de uma transação de saída que é financeiramente atualizada no período.

O diagrama a seguir ilustra essa série de transações com os efeitos de escolher o modelo de estoque de média ponderada e o princípio de liquidação resumida sem a opção **Incluir valor físico**.

![SS de média ponderada sem Incluir valor físico.](media/weighted-average-summarized-settlement-without-include-physical-value.png)

**Chave para o diagrama**

- As transações de estoque são representadas por setas verticais.
- As transações físicas são representadas por setas cinza menores.
- As transações financeiras são representadas por setas mais longas em preto.
- Os recebimentos no estoque são representados por setas verticais sobre o eixo.
- Saídas fora do estoque são representadas por setas verticais abaixo do eixo.
- Cada nova transação de recebimento ou saída é designada por uma nova etiqueta.
- Cada seta vertical é rotulada com um identificador sequencial, como *1a*. Os identificadores indicam a ordem de lançamentos de transação de estoque na linha do tempo.
- Cada data no diagrama é separada por uma linha vertical preta fina. A data é indicada na parte inferior do diagrama.
- Os fechamentos de estoque são representados por uma linha tracejada vertical vermelha.
- As liquidações executadas pelo fechamento de estoque são representadas por linhas tracejadas diagonais de um recebimento para uma saída.

## <a name="weighted-average-direct-settlement-with-the-include-physical-value-option"></a>Liquidação direta de média ponderada com a opção Incluir valor físico

O parâmetro **Incluir valor físico** funciona de forma diferente com o modelo de inventário médio ponderado do que em versões anteriores do produto. Quando você selecionar a opção **Incluir valor físico** para um item no formulário **Grupo de modelos do item**, o sistema usará recebimentos atualizados fisicamente ao calcular o preço de custo de saída estimado ou média de execução. As saídas serão lançadas com base nesse preço de custo estimado durante o período. Durante o fechamento de estoque, os recebimentos atualizados financeiramente serão considerados somente no cálculo de média ponderada.

As seguintes transações são ilustradas neste gráfico:

- 1a. Recebimento físico de estoque para uma quantidade de 10 ao custo de BRL 10,00 cada.
- 1b. Recebimento financeiro de estoque para uma quantidade de 10 ao custo de BRL 10,00 cada.
- 2a. Recebimento físico de estoque para uma quantidade de 10 ao custo de BRL 20,00 cada.
- 3a. Saída física de estoque para uma quantidade de 1 ao preço de custo de USD 15,00 (média de transações lançadas financeiramente e fisicamente).
- 3b. Saída financeira de estoque para uma quantidade de 1 ao preço de custo de USD 15,00 (média de transações lançadas financeiramente e fisicamente).
- 4a. Saída física de estoque para uma quantidade 1 ao custo de USD 15,00 cada (média de execução de transações lançadas financeira e fisicamente).
- 4b. Saída financeira de estoque para uma quantidade de 1 ao preço de custo de USD 15,00 (média de transações lançadas financeiramente e fisicamente).
- 5a. Saída física de estoque para uma quantidade 1 ao custo de USD 15,00 cada (média de execução de transações lançadas financeira e fisicamente).
- 6\. O fechamento de estoque é executado. Com base no método de média ponderada, o sistema usa o método de liquidação direta porque somente um recebimento é atualizado financeiramente no período. Neste exemplo, uma liquidação é criada entre 1b e 3b, e outra entre 1b e 4b. As transações 3b e 4b são ajustadas por USD -5,00 para passar o valor para USD 10,00.

O diagrama a seguir ilustra essa série de transações com os efeitos de escolher o modelo de estoque de média ponderada e o princípio de liquidação direta com a opção **Incluir valor físico**.

![DS de média ponderada com Incluir valor físico.](media/weighted-average-direct-settlement-with-include-physical-value.png)

**Chave para o diagrama**

- As transações de estoque são representadas por setas verticais.
- As transações físicas são representadas por setas cinza menores.
- As transações financeiras são representadas por setas mais longas em preto.
- Os recebimentos no estoque são representados por setas verticais sobre o eixo.
- Saídas fora do estoque são representadas por setas verticais abaixo do eixo.
- Cada nova transação de recebimento ou saída é designada por uma nova etiqueta.
- Cada seta vertical é rotulada com um identificador sequencial, como *1a*. Os identificadores indicam a ordem de lançamentos de transação de estoque na linha do tempo.
- Cada data no diagrama é separada por uma linha vertical preta fina. A data é indicada na parte inferior do diagrama.
- Os fechamentos de estoque são representados por uma linha tracejada vertical vermelha.
- As liquidações executadas pelo fechamento de estoque são representadas por linhas tracejadas diagonais de um recebimento para uma saída.

## <a name="weighted-average-summarized-settlement-with-the-include-physical-value-option"></a>Liquidação resumida de média ponderada com a opção Incluir valor físico

O parâmetro **Incluir valor físico** funciona de forma diferente com a média ponderada do que nas versões anteriores. Marque a caixa de seleção **Incluir valor físico** para um item na página **Grupo de modelos do item**. Em seguida, o sistema usará os recebimentos atualizados fisicamente no cálculo do preço de custo estimado, ou a média em execução. As saídas serão lançadas com base nesse preço de custo estimado durante o período. Durante o fechamento de estoque, os recebimentos atualizados financeiramente serão considerados somente no cálculo de média ponderada. É recomendado um fechamento de estoque mensal ao usar o modelo de estoque de média ponderada. Nesse exemplo de liquidação resumida de média ponderada, o modelo de estoque é marcado para incluir valor físico.

As seguintes transações são ilustradas neste gráfico:

- 1a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 10,00 cada.
- 1b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 10,00 cada.
- 2a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 20,00 cada.
- 2b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 22,00 cada.
- 3a. Saída física de estoque para uma quantidade de 1 ao preço de custo de USD 16,00 (média de transações lançadas financeiramente e fisicamente).
- 3b. Saída financeira de estoque para uma quantidade de 1 ao preço de custo de USD 16,00 (média de transações lançadas financeiramente e fisicamente).
- 4a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 25,00 cada.
- 5a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 30,00 cada.
- 5b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 30,00 cada.
- 6a. Saída física de estoque para uma quantidade de 1 ao preço de custo de USD 23,67 (média de transações lançadas financeiramente e fisicamente).
- 7\. O fechamento de estoque é executado.
- 7a. A saída financeira de transação de fechamento de estoque de média ponderada é criada para somar as liquidações para todos os recebimentos financeiros de estoque.
  - A transação 1b é liquidada para uma quantidade 1 com um valor liquidado de USD 10,00.
  - A transação 2b é liquidada para uma quantidade 1 com um valor liquidado de USD 22,00.
  - A transação 5b é liquidada para uma quantidade 1 com um valor liquidado de USD 30,00.
  - A transação 7a é criada para uma quantidade 3 com um valor liquidado de USD 62,00.  
- 7b. Um recebimento financeiro de transação de fechamento de estoque de média ponderada é criado como a compensação para as transações de saída fechadas financeiramente.
  - A transação 3b é liquidada para uma quantidade 1 com um valor liquidado de USD 20,67. Essa transação é ajustada por USD 4,67 para passar o valor original de USD 16,00 para 20,67, que é a média ponderada de transações lançadas financeiramente para o período.
  - A transação 7b é criada para uma quantidade 1 com um valor liquidado de USD 20,67 para compensação 3b.

O diagrama a seguir ilustra essa série de transações com os efeitos de escolher o modelo de estoque de média ponderada e o princípio de liquidação resumida sem a opção **Incluir valor físico**.

![SS de média ponderada com Incluir valor físico.](media/weighted-average-summarized-settlement-with-include-physical-value.png)

**Chave para o diagrama**

- As transações de estoque são representadas por setas verticais.
- As transações físicas são representadas por setas cinza menores.
- As transações financeiras são representadas por setas mais longas em preto.
- Os recebimentos no estoque são representados por setas verticais sobre o eixo.
- Saídas fora do estoque são representadas por setas verticais abaixo do eixo.
- Cada nova transação de recebimento ou saída é designada por uma nova etiqueta.
- Cada seta vertical é rotulada com um identificador sequencial, como *1a*. Os identificadores indicam a ordem de lançamentos de transação de estoque na linha do tempo.
- Cada data no diagrama é separada por uma linha vertical preta fina. A data é indicada na parte inferior do diagrama.
- Os fechamentos de estoque são representados por uma linha tracejada vertical vermelha.
- As liquidações executadas pelo fechamento de estoque são representadas por linhas tracejadas diagonais de um recebimento para uma saída.

## <a name="weighted-average-with-marking"></a>Média ponderada com a marcação

A marcação é um processo que permite vincular ou marcar uma transação de saída para uma transação de recebimento. A marcação pode ocorrer antes ou depois que a transação for lançada. É possível usar a marcação quando desejar verificar o custo exato do estoque quando a transação é lançada ou quando o fechamento de estoque é executado.

Por exemplo, seu departamento de Atendimento ao Cliente aceitou uma ordem urgente de um cliente importante. Será necessário pagar mais por esse item para atender às solicitações do cliente, pois esta é uma ordem urgente. É necessário ter certeza de que o custo desse item de estoque é refletido na margem ou no custo dos produtos vendidos (COGS) para essa fatura de ordem de venda.

Quando a ordem de compra é lançada, o estoque é recebido ao custo de BRL 120,00. Por exemplo, esse documento de ordem de venda é marcado para a ordem de compra antes do lançamento da guia de remessa ou fatura. Em seguida, o COGS será de R$ 120,00 em vez do custo médio atual para o item. Se a guia de remessa de ordem de vendas ou a nota fiscal for lançada antes que a marcação ocorra, os COGS serão lançados no preço de custo médio.

Antes que fechamento de estoque seja executado, essas duas transações ainda podem ser marcadas uma para a outra.

Uma transação de recebimento é marcada para uma transação de saída. Em seguida, o método de validação selecionado para o grupo de modelo de item do item será desconsiderado e o sistema liquidará essas transações entre si.

É possível marcar uma transação de saída para um recebimento antes que a transação seja lançada. Você pode fazer isso em uma linha da ordem de venda na página **Detalhes da ordem de venda**. As transações de recebimento abertas são mostradas na página **Marcação**.

É possível marcar uma transação de saída para um recebimento após a transação ter sido lançada. Você pode corresponder ou marcar uma transação de saída para uma transação de recebimento aberta para um item inventariado de um diário de ajuste de estoque lançado.

As seguintes transações são ilustradas neste gráfico:

- 1a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 10,00 cada.
- 1b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 10,00 cada.
- 2a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 20,00 cada.
- 2b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 22,00 cada.
- 3a. Saída física de estoque para uma quantidade de 1 ao preço de custo de USD 16,00 (média ponderada de transações lançadas financeiramente).
- 3b. Saída financeira de estoque para uma quantidade de 1 ao preço de custo de USD 16,00 (média ponderada de transações lançadas financeiramente).
- 3c. Saída financeira de estoque para 3b está marcada para saída financeira de estoque para 2b.
- 4a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 25,00 cada.
- 5a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 30,00 cada.
- 5b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 30,00 cada.
- 6a. Saída física de estoque para uma quantidade de 1 ao preço de custo de USD 23,00 (média ponderada de transações lançadas financeiramente).
- 7\. O fechamento de estoque é executado. Com base no princípio de marcação que utiliza o método de média ponderada, as transações marcadas são liquidadas entre si. Neste exemplo, 3b é liquidado contra 2b, e um ajuste para USD 6,00 é lançado em 3b para trazer o valor para USD 22,00. Neste exemplo, nenhuma liquidação adicional é feita, pois o fechamento cria liquidações apenas para transações atualizadas financeiramente.

O diagrama a seguir ilustra essa série de transações com os efeitos de escolher o modelo de estoque de média ponderada com marcação.

![Média ponderada com Marcação.](media/weighted-average-with-marking.png)

**Chave para o diagrama**

- As transações de estoque são representadas por setas verticais.
- As transações físicas são representadas por setas cinza menores.
- As transações financeiras são representadas por setas mais longas em preto.
- Os recebimentos no estoque são representados por setas verticais sobre o eixo.
- Saídas fora do estoque são representadas por setas verticais abaixo do eixo.
- Cada nova transação de recebimento ou saída é designada por uma nova etiqueta.
- Cada seta vertical é rotulada com um identificador sequencial, como *1a*. Os identificadores indicam a ordem de lançamentos de transação de estoque na linha do tempo.
- Cada data no diagrama é separada por uma linha vertical preta fina. A data é indicada na parte inferior do diagrama.
- Os fechamentos de estoque são representados por uma linha tracejada vertical vermelha.
- As liquidações executadas pelo fechamento de estoque são representadas por linhas tracejadas diagonais de um recebimento para uma saída.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

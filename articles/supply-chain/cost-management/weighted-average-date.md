---
title: Data da média ponderada com Incluir valor físico e marcação
description: Data de média ponderada é um modelo de estoque baseado no princípio da média ponderada, onde saídas do estoque são avaliados no valor médio dos itens recebidos no estoque para cada dia separado do período de fechamento do estoque.
author: JennySong-SH
ms.date: 03/04/2022
ms.topic: article
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 28991
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1497cb08f4cc5a455c832b9bf125c309cd90aa3d
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8672112"
---
# <a name="weighted-average-date-with-include-physical-value-and-marking"></a>Data da média ponderada com Incluir valor físico e marcação

[!include [banner](../includes/banner.md)]

A *data da média ponderada* é um modelo de estoque baseado em uma média calculada com a multiplicação de cada componente (transação de item) por um fator (preço de custo) que reflete sua importância (quantidade) em cada dia do período. Em outras palavras, esse modelo de estoque atribui o custo de transações de saída com base no valor médio de todo o estoque recebido a cada dia, além de qualquer estoque disponível do dia anterior.

Quando você executa um fechamento de estoque usando o modelo de estoque da data da média ponderada, dois métodos podem ser usados para criar uma liquidação. Em geral, todos os recebimentos são liquidados em relação a uma saída virtual, que armazena a quantidade e o valor totais recebidos. Essa saída virtual possui um recebimento virtual correspondente a partir do qual as saídas são liquidadas. Dessa forma, todas as saídas obtêm o mesmo custo médio a cada dia. A saída virtual e o recebimento virtual podem ser considerados uma transferência virtual. Essa transferência virtual é chamada de *transferência de fechamento de estoque de média ponderada*. Portanto, esse método de liquidação é chamado de *liquidação resumida de média ponderada*. Se houver somente um recebimento, todas as saídas poderão ser liquidadas a partir dele, e a transferência virtual não é criada. Esse método de liquidação é chamado de *liquidação direta*. Qualquer estoque disponível após o fechamento do estoque é executado na média ponderada do último dia do período anterior e incluído no cálculo de data da média ponderada no próximo período.

Você pode substituir o princípio de data da média ponderada, marcando transações de estoque de forma que o recebimento de um item específico seja liquidado em relação a uma saída específica. Um fechamento de estoque periódico é exigido quando você usa o modelo de estoque de data da média ponderada para gerar liquidações e ajustar valores de acordo com o princípio de data da média ponderada. Até que você execute o processo de fechamento de estoque, as transações de saída são avaliadas na média de execução quando ocorreram atualizações físicas e financeiras. A menos que você esteja usando marcação, a média de execução é calculada quando a atualização física ou financeira é executada.

O método de custo de estoque da data da média ponderada é calculado pela seguinte fórmula a cada dia:

*Custo* = \[(*Q*<sub>*b*</sub> × *P*<sub>*b*</sub>) + &#x2211;<sub>*n*</sub>(*Q*<sub>*n*</sub> × *P*<sub>*n*</sub>)\] ÷ (*Q*<sub>*b*</sub> + &#x2211;<sub>*n*</sub>*Q*<sub>*n*</sub>)

- *Q* = quantidade da transação
- *P* = preço da transação

Em outras palavras, o custo da média ponderada é igual à quantidade inicial vezes o preço inicial, mais a soma de cada quantidade recebida, seu preço de recebimento, tudo dividido pela quantidade inicial mais a soma das quantidades recebidas.

Durante o fechamento do estoque, o cálculo é executado diariamente durante o período de fechamento.

> [!NOTE]
> Para mais informações sobre as liquidações, consulte [Fechamento de inventário](inventory-close.md).

Os seguintes exemplos mostram o efeito do uso da data da média ponderada com cinco configurações:

- Liquidação direta de data de média ponderada quando a opção **Incluir valor físico** não é usada
- Liquidação resumida de data de média ponderada quando a opção **Incluir valor físico** não é usada
- Liquidação direta de data de média ponderada quando a opção **Incluir valor físico** é usada
- Liquidação resumida de data de média ponderada quando a opção **Incluir valor físico** não é usada
- Data de média ponderada quando a marcação é usada

## <a name="weighted-average-date-direct-settlement-when-the-include-physical-value-option-isnt-used"></a>Liquidação direta de data de média ponderada quando a opção Incluir valor físico não é usada

O princípio de liquidação direta cria liquidações diretamente entre recebimentos e saídas sem criar outras transações de estoque. O sistema usa esse princípio de liquidação direta nestas situações:

- Um recebimento e uma ou mais saídas foram lançadas no período.
- Somente saídas foram lançadas no período e o estoque contém itens disponíveis de um fechamento anterior.

Neste exemplo, a caixa de seleção **Incluir valor físico** está desmarcada na página **Grupo de modelos do item** para o produto liberado. O diagrama a seguir mostra estas transações:

**Dia 1:**

- 1a. Recebimento físico de estoque para uma quantidade de 10 ao custo de BRL 10,00 cada.
- 1b. Recebimento financeiro de estoque para uma quantidade de 10 ao custo de BRL 10,00 cada.
- 2a. Recebimento físico de estoque para uma quantidade de 10 ao custo de BRL 20,00 cada.
- 3a. Saída física de estoque para uma quantidade de 1 ao preço de custo de USD 10,00 (média ponderada de transações lançadas financeiramente).
- 3b. Saída financeira de estoque para uma quantidade de 1 ao preço de custo de USD 10,00 (média ponderada de transações lançadas financeiramente).

**Dia 2:**

- 4a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 25,00 cada.
- 5a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 30,00 cada.
- 5b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 30,00 cada.
- 6a. Saída financeira de estoque para uma quantidade 1 ao custo de USD 20,00 cada (média de execução de transações lançadas financeiramente).

**Dia 3:**

- 7\. O fechamento de estoque é executado. Com base no método de data da média ponderada, o sistema usa o método de liquidação para 30 de dezembro (30/12) direta porque somente um recebimento é atualizado financeiramente em 30/12. Neste exemplo, uma liquidação é criada entre as transações 1b e 3b. É feito um ajuste de USD 10,00 para trazer o valor da transação 3B até 20,00. Nenhum ajuste ou liquidação é feito em 31 de dezembro (31/12) porque não há problemas atualizados financeiramente em 31/12.

O diagrama a seguir mostra essa série de transações e os efeitos de usar o modelo de estoque de média ponderada e o princípio de liquidação direta sem a opção **Incluir valor físico**.

![Liquidação direta de data de média ponderada sem a opção Incluir valor físico.](media/weighted-average-date-direct-settlement-without-include-physical-value.png)

**Chave para o diagrama:**

- As transações de estoque são representadas por setas verticais.
- As transações físicas são representadas por setas cinza menores.
- As transações financeiras são representadas por setas mais longas em preto.
- Os recebimentos no estoque são representados por setas verticais sobre o eixo.
- Saídas fora do estoque são representadas por setas verticais abaixo do eixo.
- Cada nova transação de recebimento ou saída é designada por uma nova etiqueta.
- Cada seta vertical é rotulada com um identificador sequencial, como *1a*. Os identificadores indicam a ordem de lançamentos de transação de estoque na linha do tempo.
- As datas são separadas por linhas verticais pretas finas. As datas são indicadas na parte inferior do diagrama.
- Os fechamentos de estoque são representados por linhas tracejadas verticais vermelhas.
- As liquidações executadas pelo fechamento de estoque são representadas por linhas tracejadas diagonais de um recebimento para uma saída.

## <a name="weighted-average-date-summarized-settlement-when-the-include-physical-value-option-isnt-used"></a>Liquidação resumida de data de média ponderada quando a opção Incluir valor físico não é usada

Quando há vários recebimentos em um período, a data da média ponderada usa o princípio de liquidação resumido em que todos os recebimentos em um único dia são resumidos em uma transação chamada *fechamento de estoque de média ponderada*. Todos os recebimentos do dia serão liquidados em relação à saída da transação de estoque recém-criada. Todas as saídas do dia serão liquidadas em relação ao recebimento da nova transação de estoque. Se houver valor de estoque restante disponível depois do fechamento de estoque, o valor do estoque disponível será incluído na transação de recebimento de transações de fechamento de estoque de média ponderada.

O diagrama a seguir mostra estas transações:

**Dia 1:**

- 1a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 10,00 cada.
- 1b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 10,00 cada.
- 2a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 20,00 cada.
- 2b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 22,00 cada.
- 3a. Saída física de estoque para uma quantidade de 1 ao preço de custo de USD 16,00 (média ponderada de transações lançadas financeiramente).
- 3b. Saída financeira de estoque para uma quantidade de 1 ao preço de custo de USD 16,00 (média ponderada de transações lançadas financeiramente).

**Dia 2:**

- 4a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 25,00 cada.
- 5a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 30,00 cada.
- 5b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 30,00 cada.
- 6a. Saída física de estoque para uma quantidade de 1 ao preço de custo de USD 23,00 (média ponderada de transações lançadas financeiramente).

**Dia 3:**

- 7\. O fechamento de estoque é executado.
- 7a. A saída financeira de transação de fechamento de estoque de média ponderada é criada para somar as liquidações para todos os recebimentos financeiros de estoque.

    - A transação 1b é liquidada para uma quantidade 1 com um valor liquidado de USD 10,00.
    - A transação 2b é liquidada para uma quantidade 1 com um valor liquidado de USD 22,00.
    - A transação 7a é criada para uma quantidade 2 com um valor liquidado de USD 32,00. Esta transação desloca a soma das duas transações de recibo financeiramente atualizadas no período.

- 7b. Um recebimento financeiro de transação de fechamento de estoque de média ponderada é criado como a compensação para saídas lançadas financeiramente.

    - A transação 3b é liquidada para uma quantidade 1 com um valor liquidado de USD 16,00. Esta transação não está ajustada porque é a média ponderada de transações lançadas financeiramente em 1º de dezembro (1/12).
    - A transação 7b é criada para uma quantidade 2 com um valor financeiro de USD 32,00 e um valor liquidado de USD 16,00 para a transação de compensação 3b. Esta transação desloca a soma de uma transação de saída que é financeiramente atualizada no período. A transação permanece aberta porque ainda existe uma disponível.

O diagrama a seguir mostra essa série de transações, e os efeitos do uso do modelo de estoque de média ponderada e do princípio de liquidação resumida, mas sem usar a opção **Incluir valor físico**.

![Liquidação resumida de data de média ponderada sem a opção Incluir valor físico.](media/weighted-average-date-summarized-settlement-without-include-physical-value.png)

**Chave para o diagrama:**

- As transações de estoque são representadas por setas verticais.
- As transações físicas são representadas por setas cinza menores.
- As transações financeiras são representadas por setas mais longas em preto.
- Os recebimentos no estoque são representados por setas verticais sobre o eixo.
- Saídas fora do estoque são representadas por setas verticais abaixo do eixo.
- Cada nova transação de recebimento ou saída é designada por uma nova etiqueta.
- Cada seta vertical é rotulada com um identificador sequencial, como *1a*. Os identificadores indicam a ordem de lançamentos de transação de estoque na linha do tempo.
- As datas são separadas por linhas verticais pretas finas. As datas são indicadas na parte inferior do diagrama.
- Os fechamentos de estoque são representados por linhas tracejadas verticais vermelhas.
- As liquidações executadas pelo fechamento de estoque são representadas por linhas tracejadas diagonais de um recebimento para uma saída.

## <a name="weighted-average-date-direct-settlement-when-the-include-physical-value-option-is-used"></a>Liquidação direta de data de média ponderada quando a opção Incluir valor físico é usada

Na versão atual do produto, a opção **Incluir valor físico** funciona de forma diferente com o modelo de estoque da média ponderada do que em versões anteriores. Quando você marca a caixa de seleção **Incluir valor físico** para um item na página **Grupo de modelos de item**, o sistema usa recebimentos atualizados fisicamente quando calcular o preço de custo estimado ou de custo médio. As saídas serão lançadas com base nesse preço de custo estimado durante o período. Durante o fechamento de estoque, somente os recebimentos atualizados financeiramente serão considerados somente no cálculo de média ponderada.

O diagrama a seguir mostra estas transações:

**Dia 1:**

- 1a. Recebimento físico de estoque para uma quantidade de 10 ao custo de BRL 10,00 cada.
- 1b. Recebimento financeiro de estoque para uma quantidade de 10 ao custo de BRL 10,00 cada.
- 2a. Recebimento físico de estoque para uma quantidade de 10 ao custo de BRL 20,00 cada.
- 3a. Saída física de estoque para uma quantidade de 1 ao preço de custo de USD 15,00 (média de transações lançadas financeiramente e fisicamente).
- 3b. Saída financeira de estoque para uma quantidade de 1 ao preço de custo de USD 15,00 (média de transações lançadas financeiramente e fisicamente).

**Dia 2:**

- 4a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 25,00 cada.
- 5a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 30,00 cada.
- 5b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 30,00 cada.
- 6a. Saída física de estoque para uma quantidade 1 ao custo de USD 21,25 cada (média de execução de transações lançadas financeira e fisicamente).

**Dia 3:**

- 7\. O fechamento de estoque é executado. Com base no método de data da média ponderada, o sistema usa o método de liquidação para 30 de dezembro (30/12) direta porque somente um recebimento é atualizado financeiramente em 30/12. Neste exemplo, uma liquidação é criada entre as transações 1b e 3b. Nenhum ajuste é feito para a saída em 30/12. Além disso, nenhum ajuste ou liquidação é feito em 31 de dezembro (31/12) porque não há problemas atualizados financeiramente em 31/12.

O diagrama a seguir mostra essa série de transações e os efeitos de usar o modelo de estoque de média ponderada e o princípio de liquidação direta com a opção **Incluir valor físico**.

![Liquidação direta de média ponderada com Incluir valor físico.](media/weighted-average-date-direct-settlement-with-include-physical-value.png)

**Chave para o diagrama:**

- As transações de estoque são representadas por setas verticais.
- As transações físicas são representadas por setas cinza menores.
- As transações financeiras são representadas por setas mais longas em preto.
- Os recebimentos no estoque são representados por setas verticais sobre o eixo.
- Saídas fora do estoque são representadas por setas verticais abaixo do eixo.
- Cada nova transação de recebimento ou saída é designada por uma nova etiqueta.
- Cada seta vertical é rotulada com um identificador sequencial, como *1a*. Os identificadores indicam a ordem de lançamentos de transação de estoque na linha do tempo.
- As datas são separadas por linhas verticais pretas finas. As datas são indicadas na parte inferior do diagrama.
- Os fechamentos de estoque são representados por linhas tracejadas verticais vermelhas.
- As liquidações executadas pelo fechamento de estoque são representadas por linhas tracejadas diagonais de um recebimento para uma saída.

## <a name="weighted-average-date-summarized-settlement-when-the-include-physical-value-option-is-used"></a>Liquidação resumida de data de média ponderada quando a opção Incluir valor físico não é usada

Na versão atual do produto, a opção **Incluir valor físico** funciona de forma diferente com a média ponderada do que em versões anteriores. Quando você marca a caixa de seleção **Incluir valor físico** para um item na página **Grupo de modelos de item**, o sistema usa recebimentos atualizados fisicamente quando calcular o preço de custo estimado ou de custo médio. As saídas serão lançadas com base nesse preço de custo estimado durante o período. Durante o fechamento de estoque, somente os recebimentos atualizados financeiramente serão considerados somente no cálculo de média ponderada. É recomendado um fechamento de estoque mensal ao usar o modelo de estoque de média ponderada. Nesse exemplo de liquidação resumida de data da média ponderada, o modelo de estoque é marcado para incluir valor físico.

O diagrama a seguir mostra estas transações:

**Dia 1:**

- 1a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 10,00 cada.
- 1b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 10,00 cada.
- 2a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 20,00 cada.
- 2b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 22,00 cada.
- 3a. Saída física de estoque para uma quantidade de 1 ao preço de custo de USD 16,00 (média de transações lançadas financeiramente e fisicamente).
- 3b. Saída financeira de estoque para uma quantidade de 1 ao preço de custo de USD 16,00 (média de transações lançadas financeiramente e fisicamente).

**Dia 2:**

- 4a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 25,00 cada.
- 5a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 30,00 cada.
- 5b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 30,00 cada.
- 6a. Saída física de estoque para uma quantidade de 1 ao preço de custo de USD 23,67 (média de transações lançadas financeiramente e fisicamente).

**Dia 3:**

- 7\. O fechamento de estoque é executado.
- 7a. A saída financeira de transação de fechamento de estoque de média ponderada é criada para somar as liquidações para todos os recebimentos financeiros de estoque.

    - A transação 1b é liquidada para uma quantidade 1 com um valor liquidado de USD 10,00.
    - A transação 2b é liquidada para uma quantidade 1 com um valor liquidado de USD 22,00.
    - A transação 7a é criada para uma quantidade 2 com um valor liquidado de USD 32,00. Esta transação desloca a soma das duas transações de recibo financeiramente atualizadas no período.

- 7b. Um recebimento financeiro de transação de fechamento de estoque de média ponderada é criado como a compensação para saídas lançadas financeiramente.

    - A transação 3b é liquidada para uma quantidade 1 com um valor liquidado de USD 16,00. Esta transação não está ajustada porque é a média ponderada de transações lançadas financeiramente em 1º de dezembro (1/12).
    - A transação 7b é criada para uma quantidade 2 com um valor financeiro de USD 32,00 e um valor liquidado de USD 16,00 para a transação de compensação 3b. Esta transação desloca a soma de uma transação de saída que é financeiramente atualizada no período. A transação permanece aberta porque ainda existe uma disponível.

O diagrama a seguir mostra essa série de transações e os efeitos de usar o modelo de estoque de média ponderada e o princípio de liquidação resumida sem a opção **Incluir valor físico**.

![Liquidação resumida de média ponderada com a opção Incluir valor físico.](media/weighted-average-date-summarized-settlement-with-include-physical-value.png)

**Chave para o diagrama:**

- As transações de estoque são representadas por setas verticais.
- As transações físicas são representadas por setas cinza menores.
- As transações financeiras são representadas por setas mais longas em preto.
- Os recebimentos no estoque são representados por setas verticais sobre o eixo.
- Saídas fora do estoque são representadas por setas verticais abaixo do eixo.
- Cada nova transação de recebimento ou saída é designada por uma nova etiqueta.
- Cada seta vertical é rotulada com um identificador sequencial, como *1a*. Os identificadores indicam a ordem de lançamentos de transação de estoque na linha do tempo.
- As datas são separadas por linhas verticais pretas finas. As datas são indicadas na parte inferior do diagrama.
- Os fechamentos de estoque são representados por linhas tracejadas verticais vermelhas.
- As liquidações executadas pelo fechamento de estoque são representadas por linhas tracejadas diagonais de um recebimento para uma saída.

## <a name="weighted-average-date-when-marking-is-used"></a>Data de média ponderada quando a marcação é usada

A marcação é um processo que permite vincular ou marcar uma transação de saída para uma transação de recebimento. A marcação pode ocorrer antes ou depois que a transação for lançada. É possível usar a marcação quando você desejar verificar o custo exato do estoque quando a transação é lançada ou quando o fechamento de estoque é executado.

Por exemplo, seu departamento de Atendimento ao Cliente aceitou uma ordem urgente de um cliente importante. Será necessário pagar mais por esse item para atender às solicitações do cliente, pois esta é uma ordem urgente. É necessário garantir que o custo desse item de estoque seja refletido na margem ou no custo dos produtos vendidos (COGS) para essa fatura de ordem de venda.

Quando a ordem de compra é lançada, o estoque é recebido ao custo de BRL 120,00. Se esse documento de ordem de venda for marcado para a ordem de compra antes da guia de remessa ou a fatura ser lançada, o COGS será USD 120,00, em vez do custo médio atual para o item. Se a marcação ocorrer depois que a guia de remessa de ordem de vendas ou a nota fiscal for lançada antes que a marcação ocorra, os COGS serão lançados no preço de custo médio.

Antes que fechamento de estoque seja executado, essas duas transações ainda podem ser marcadas uma para a outra.

Se uma transação de recebimento é marcada para uma transação de saída, o método de avaliação selecionado para o grupo de modelos do item é desconsiderado, e o sistema liquida essas transações entre si.

É possível marcar uma transação de saída para um recebimento antes que a transação seja lançada. Você pode fazer essa marcação em uma linha da ordem de venda na página **Detalhes da ordem de venda**. As transações de recebimento abertas são mostradas na página **Marcação**.

É possível marcar uma transação de saída para um recebimento depois que a transação for lançada. Você pode corresponder ou marcar uma transação de saída para uma transação de recebimento aberta para um item inventariado de um diário de ajuste de estoque lançado.

O diagrama a seguir mostra estas transações:

**Dia 1:**

- 1a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 10,00 cada.
- 1b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 10,00 cada.
- 2a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 20,00 cada.
- 2b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 22,00 cada.
- 3a. Saída física de estoque para uma quantidade de 1 ao preço de custo de USD 16,00 (média ponderada de transações lançadas financeiramente).
- 3b. Saída financeira de estoque para uma quantidade de 1 ao preço de custo de USD 16,00 (média ponderada de transações lançadas financeiramente).
- 3c. Saída financeira de estoque para a transação 3b está marcada para saída financeira de estoque para a transação 2b.

**Dia 2:**

- 4a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 25,00 cada.
- 5a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 30,00 cada.
- 5b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 30,00 cada.
- 6a. Saída física de estoque para uma quantidade de 1 ao preço de custo de USD 23,00 (média ponderada de transações lançadas financeiramente).

**Dia 3:**

- 7\. O fechamento de estoque é executado. Com base no princípio de marcação que utiliza o método de média ponderada, as transações marcadas são liquidadas entre si. Neste exemplo, 3b é liquidado contra a transação 2b, e um ajuste para USD 6,00 é lançado na transação 3b para trazer o valor para USD 22,00. Neste exemplo, nenhuma liquidação adicional é feita, pois o fechamento cria liquidações apenas para transações atualizadas financeiramente.

O diagrama a seguir mostra essa série de transações e os efeitos do uso do modelo de estoque de média ponderada e com marcação.

![Média ponderada com a marcação.](media/weighted-average-date-with-marking.png)

**Chave para o diagrama:**

- As transações de estoque são representadas por setas verticais.
- As transações físicas são representadas por setas cinza menores.
- As transações financeiras são representadas por setas mais longas em preto.
- Os recebimentos no estoque são representados por setas verticais sobre o eixo.
- Saídas fora do estoque são representadas por setas verticais abaixo do eixo.
- Cada nova transação de recebimento ou saída é designada por uma nova etiqueta.
- Cada seta vertical é rotulada com um identificador sequencial, como *1a*. Os identificadores indicam a ordem de lançamentos de transação de estoque na linha do tempo.
- As datas são separadas por linhas verticais pretas finas. As datas são indicadas na parte inferior do diagrama.
- Os fechamentos de estoque são representados por linhas tracejadas verticais vermelhas.
- As liquidações executadas pelo fechamento de estoque são representadas por linhas tracejadas diagonais de um recebimento para uma saída.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

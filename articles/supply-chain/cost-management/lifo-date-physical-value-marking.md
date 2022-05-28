---
title: Data UEPS com valor físico e marcação
description: A data UEPS (último a entrar, primeiro a sair) é um modelo de estoque baseado no princípio UEPS. As saídas do estoque são liquidadas em relação aos últimos recebimentos do estoque com base na data da transação de estoque. Ao usar a data UEPS, se não houver um recebimento antes da saída, a saída será liquidada com relação a qualquer recebimento que ocorra após a data da saída. Várias saídas na mesma data serão liquidadas na ordem última saída, último recebimento.
author: JennySong-SH
ms.date: 02/21/2022
ms.topic: article
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 51592
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8ca344e6ca81814e787046f6ece97625d035346d
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8671440"
---
# <a name="lifo-date-with-physical-value-and-marking"></a>Data UEPS com valor físico e marcação

[!include [banner](../includes/banner.md)]

A data UEPS (último a entrar, primeiro a sair) é um método de gerenciamento e validação de estoque em que o estoque produzido ou adquirido por último é vendido, usado ou descartado primeiro. Durante o processo de fechamento de estoque no Microsoft Dynamics 365 Supply Chain Management, o sistema criará liquidações nas quais o primeiro recebimento corresponde à primeira saída e assim por diante. Quando você usa o modelo de estoque de data UEPS (último a entrar, primeiro a sair), se não houver um recebimento antes da saída, a saída será liquidada com relação a recebimento ocorrido após a data da saída. As liquidações e o princípio de correspondência são baseados na data financeira das transações de estoque. Quando houver várias saídas na mesma data, elas serão liquidadas na ordem da última saída, último recebimento. Uma avaliação preliminar das liquidações e ajustes pode ser realizada executando o processo de recálculo de estoque.

Você pode substituir o princípio de data UEPS, marcando transações de estoque para que o recebimento de um item específico seja liquidado em relação a uma saída específica. Um fechamento de estoque periódico é exigido quando você usa o modelo de estoque de data UEPS para gerar liquidações e ajustar valores de acordo com o princípio UEPS. Até que você execute o processo de fechamento de estoque, as transações de saída são avaliadas na média de execução quando ocorreram atualizações físicas e financeiras. A menos que você esteja usando marcação, a média de execução é calculada quando a atualização física ou financeira é executada.

É recomendável um fechamento de estoque periódico ao usar o modelo de estoque de data UEPS.

Os seguintes exemplos mostram o efeito de usar a data UEPS nas três configurações:

- Data UEPS sem a opção **Incluir valor físico**
- Data UEPS com a opção **Incluir valor físico**
- Data UEPS com marcação

## <a name="lifo-date-without-the-include-physical-value-option"></a>Data UEPS sem a opção Incluir valor físico

Neste exemplo, o grupo de modelo de item não está marcado para incluir o valor físico. A ilustração a seguir mostra essas transações:

- 1a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 10,00 cada.
- 1b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 10,00 cada.
- 2a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 20,00 cada.
- 2b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 22,00 cada.
- 3a. Saída física de estoque para uma quantidade de 1 ao preço de custo de USD 16,00 (média ponderada de transações lançadas financeiramente).
- 3b. Saída financeira de estoque para uma quantidade de 1 ao preço de custo de USD 16,00 (média ponderada de transações lançadas financeiramente).
- 4a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 25,00 cada.
- 5a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 30,00 cada.
- 5b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 30,00 cada.
- 6a. Saída física de estoque para uma quantidade de 1 ao preço de custo de USD 23,00 (média ponderada de transações lançadas financeiramente)
- 7\. O fechamento de estoque é executado. Com base no método de data UEPS, a primeira saída atualizada financeiramente será liquidada no último recebimento atualizado financeiramente, começando pela primeira data e assim por diante. Neste exemplo, uma liquidação é criada entre 3b e 2b. Um ajuste de USD – 6,00 será feito para 3b, e o custo final resultante será USD 22,00.

A ilustração a seguir mostra os efeitos do modelo de estoque de data UEPS quando a opção **Incluir valor físico** não é usada.

![Data UEPS sem a opção Incluir valor físico.](media/lifo-date-without-include-physical-value.png)

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

## <a name="lifo-date-with-the-include-physical-value-option"></a>Data UEPS com a opção Incluir valor físico

Se a caixa de seleção **Incluir valor físico** for marcada para um item na página **Grupos de modelos do item**, o sistema usará as transações de recebimento físico e financeiro para calcular o preço de custo médio em execução. Quando aplicável, o sistema também ajusta a transação de saída atualizada fisicamente. Quando a caixa de seleção **Incluir valor físico** for desmarcada, o fechamento de estoque que usa o modelo de estoque de data UEPS liquidará somente transações atualizadas financeiramente.

Nesse exemplo, o grupo de modelo de item não está marcado para incluir o valor físico. 

A ilustração a seguir mostra estas transações:

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
- 7\. O fechamento de estoque é executado. Com base no método de data UEPS, a primeira saída atualizada financeiramente será liquidada no último recebimento atualizado financeiramente para cada data, começando pela primeira data e assim por diante. Neste exemplo, uma liquidação é criada entre 2b e 3b. Um ajuste de USD – 6,00 será feito para 3b, e o custo final resultante será USD 22,00. Além disso, a transação 6a será ajustada para o custo da transação de recebimento de 5b. O sistema não liquidará essas transações, já que o recebimento é atualizado fisicamente, mas não financeiramente. Em vez disso, somente um ajuste de USD-6,33 será lançado na transação de saída física e o custo ajustado resultante será de USD 30,00.

A ilustração a seguir mostra os efeitos do modelo de estoque UEPS quando a opção **Incluir valor físico** for usada.

![Data UEPS com a opção Incluir valor físico.](media/lifo-date-with-include-physical-value.png)

**Chave para o diagrama**

- As transações de estoque são representadas por setas verticais.
- As transações físicas são representadas por setas cinza menores.
- As transações financeiras são representadas por setas mais longas em preto.
- Os recebimentos no estoque são representados por setas verticais sobre o eixo.
- Saídas fora do estoque são representadas por setas verticais abaixo do eixo.
- Cada nova transação de recebimento ou saída é designada por uma nova etiqueta.
- Cada seta vertical é rotulada com um identificador sequencial, como *1a*. Os identificadores indicam a ordem de lançamentos de transação de estoque na linha do tempo.
- Cada data no diagrama é separada por uma linha vertical preta fina. A data é referida na parte inferior do diagrama.
- Os fechamentos de estoque são representados por uma linha tracejada vertical vermelha.
- As liquidações executadas pelo fechamento de estoque são representadas por linhas tracejadas diagonais de um recebimento para uma saída.

## <a name="lifo-date-with-marking"></a>Data UEPS com marcação

A marcação é um processo que permite vincular ou marcar uma transação de saída para uma transação de recebimento. A marcação pode ocorrer antes ou depois que a transação for lançada. É possível usar a marcação quando você desejar verificar o custo exato do estoque quando a transação é lançada ou quando o fechamento de estoque é executado. Por exemplo, o departamento de Atendimento ao Cliente aceitou uma ordem urgente de um cliente importante. Como esta é uma ordem urgente, você deverá pagar mais pelo item para atender à solicitação do cliente.

É necessário garantir que o custo do item de estoque seja refletido na margem ou no custo dos produtos vendidos (COGS) para essa fatura de ordem de venda. Quando a ordem de compra é lançada, o estoque é recebido ao custo de BRL 120,00. Se esse documento de ordem de vendas for marcado para a ordem de compra antes da guia de remessa ou a fatura ser lançada, o COGS será BRL 120,00, não o custo médio atual para o item. Se a guia de remessa de ordem de vendas ou a fatura for lançada antes que a marcação ocorra, os COGS serão lançados no preço de custo médio.

Antes que fechamento de estoque seja executado, essas duas transações ainda podem ser marcadas uma para a outra.

É possível marcar uma transação de saída para um recebimento antes que a transação seja lançada. Você pode fazer essa marcação de uma linha da ordem de venda na página **Detalhes da ordem de venda** ao selecionar **Marcação \> de estoque** na guia rápida **Linhas de ordem de venda**. Você pode exibir as transações de recebimento abertas na página **Marcação**.

É possível marcar uma transação de saída para um recebimento depois que a transação for lançada. Você pode corresponder ou marcar uma transação de saída para uma transação de recebimento aberta para um item inventariado de um diário de ajuste de estoque lançado.

A ilustração a seguir mostra essas transações:

- 1a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 10,00 cada.
- 1b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 10,00 cada.
- 2a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 20,00 cada.
- 2b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 22,00 cada.
- 3a. Saída física de estoque para uma quantidade de 1 ao preço de custo de USD 16,00 (média ponderada de transações lançadas financeiramente).
- 3b. Saída financeira de estoque para uma quantidade de 1 ao preço de custo de USD 16,00 (média ponderada de transações lançadas financeiramente).
- 3c. A saída financeira de estoque para 3b está marcada para saída financeira de estoque para 1b.
- 4a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 25,00 cada.
- 5a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 30,00 cada.
- 5b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 30,00 cada.
- 6a. Saída física de estoque para uma quantidade de 1 ao preço de custo de USD 23,00 (média ponderada de transações lançadas financeiramente)
- 7\. O fechamento de estoque é executado. Com base no princípio de marcação que utiliza o método de da UEPS, as transações marcadas serão liquidadas entre si. Neste exemplo, 3b é liquidado em relação a 1b, e um ajuste para USD -6,00 é lançado em 3b para passar o valor para USD 10,00. Neste exemplo, nenhuma liquidação adicional é feita, pois o fechamento cria liquidações somente para transações atualizadas financeiramente.

A ilustração a seguir mostra os efeitos do modelo de estoque de data UEPS quando é usada uma marcação entre saídas e recebimentos. 

![Data UEPS com marcação.](media/lifo-date-with-marking.png)

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
- As liquidações e marcações executadas pelo fechamento de estoque são representadas por linhas tracejadas diagonais de um recebimento para uma saída.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

---
title: UEPS com marcação e valor físico
description: Último a entrar, Primeiro a sair (UEPS) é um modelo de estoque no qual os últimos (mais recentes) recebimentos são emitidos primeiro. As saídas do estoque são liquidadas em relação aos últimos recebimentos do estoque com base na data da transação de estoque.
author: JennySong-SH
ms.date: 02/02/2022
ms.topic: article
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 55021
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c1acc103291c5d648ac7e179a598348cd9cc2a93
ms.sourcegitcommit: 6b209919de39c15e0ebe4abc9cbcd30618f2af0b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2022
ms.locfileid: "9135559"
---
# <a name="lifo-with-physical-value-and-marking"></a>UEPS com marcação e valor físico

[!include [banner](../includes/banner.md)]

Primeiro a entrar, primeiro a sair (PEPS) é um método de gerenciamento e validação de estoque no qual o estoque produzido ou adquirido primeiro é vendido, usado ou descartado primeiro. Durante o processo de fechamento de estoque no Microsoft Dynamics 365 Supply Chain Management, o sistema criará liquidações nas quais o último recebimento corresponde à primeira saída e assim por diante. As liquidações e o princípio de correspondência são baseados na data financeira das transações de estoque. Uma avaliação preliminar das liquidações e ajustes pode ser realizada executando o processo de recálculo de estoque.

Você pode substituir o princípio PEPS, fazendo marcações em transações de estoque de tal forma que o recebimento de um item específico seja liquidado em relação a uma saída específica. Um fechamento periódico de estoque é exigido quando você usa o modelo de estoque PEPS para gerar liquidações e ajustar valores de acordo com o princípio PEPS. Até que você execute o processo de fechamento de estoque, as transações de saída são avaliadas na média de execução quando ocorreram atualizações físicas e financeiras. A menos que você esteja usando marcação, a média de execução é calculada quando a atualização física ou financeira é executada.

Os exemplos a seguir mostram o efeito de usar o UEPS nas três configurações:

- UEPS sem a opção **Incluir valor físico**
- UEPS com a opção **Incluir valor físico**
- UEPS com marcação

## <a name="lifo-without-the-include-physical-value-option"></a>UEPS sem a opção Incluir valor físico

Neste exemplo, a caixa de seleção **Incluir valor físico** está desmarcada no grupo de modelos de item para o produto liberado. A ilustração a seguir mostra estas transações:

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
- 7\. O fechamento de estoque é executado. Com base no método PEPS, a primeira saída atualizada financeiramente será liquidada no último recebimento atualizado financeiramente e assim por diante. Neste exemplo, uma liquidação é criada entre 5b e 3b. Um ajuste de USD – 14,00 será feito para 3b, e o custo final resultante será USD 30,00.

A ilustração a seguir mostra os efeitos do modelo de estoque FIFO nesta série de transações quando a opção **Incluir valor físico** não é usada.

![PEPS sem a opção Incluir valor físico.](./media/lifo-without-including-physical-value.png)

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

## <a name="lifo-with-the-include-physical-value-option"></a>UEPS com a opção Incluir valor físico

Se a caixa de seleção **Incluir valor físico** for marcada para um item na página **Grupos de modelos do item**, o sistema usará as transações de recebimento físico e financeiro para calcular o preço de custo médio em execução. Quando aplicável, o sistema também ajusta a transação de saída atualizada fisicamente. Quando a caixa de seleção **Incluir valor físico** for desmarcada, o fechamento de estoque que usa o modelo de estoque PEPS liquidará somente transações que são atualizadas financeiramente.

A ilustração a seguir mostra essas transações:

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
- 7\. O fechamento de estoque é executado. Com base no método PEPS, a primeira saída atualizada financeiramente será liquidada no último recebimento atualizado financeiramente e assim por diante. Neste exemplo, uma liquidação é criada entre 3b e 5b. Um ajuste de USD – 14,00 será feito para 3b, e o custo final resultante será USD 30,00. Além disso, a transação 6a será ajustada para o custo da transação de recebimento de 4a. O sistema não liquidará essas transações, já que o recebimento é atualizado fisicamente, mas não financeiramente. Em vez disso, somente um ajuste de USD-1,33 será lançado na transação de saída física e o custo ajustado resultante será de USD 25,00.

A ilustração a seguir mostra os efeitos do modelo de estoque UEPS nesta série de transações quando a opção **Incluir valor físico** é usada.

![PEPS com a opção Incluir valor físico.](./media/lifo-with-included-physical-value.png)

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

## <a name="lifo-with-marking"></a>UEPS com marcação

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
- 3c. Saída financeira de estoque para 3b está marcada para saída financeira de estoque para 2b.
- 4a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 25,00 cada.
- 5a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 30,00 cada.
- 5b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 30,00 cada.
- 6a. Saída física de estoque para uma quantidade de 1 ao preço de custo de USD 23,00 (média ponderada de transações lançadas financeiramente)
- 7\. O fechamento de estoque é executado. Com base no princípio de marcação que utiliza o método PEPS, as transações selecionadas serão liquidadas uma em função da outra. Neste exemplo, 3b é liquidado contra 2b, e um ajuste para USD 6,00 é lançado em 3b para trazer o valor para USD 22,00. Neste exemplo, nenhuma liquidação adicional é feita, pois o fechamento cria liquidações somente para transações atualizadas financeiramente.

O novo preço de custo médio reflete a média das transações atualizadas financeira e fisicamente, em BRL 17,50.

A ilustração a seguir mostra os efeitos do modelo de estoque UEPS nesta série de transações quando a marcação entre saídas e recebimentos é usada.

![PEPS com marcação.](./media/lifo-with-marking.png)

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

---
title: Média ponderada com valor físico e marcação
description: A média ponderada é um modelo de estoque com base no princípio da média ponderada, no qual as saídas do estoque são avaliadas no valor médio dos itens recebidos no estoque durante o período de fechamento de estoque, mais qualquer estoque disponível do período anterior.
author: AndersGirke
manager: AnnBe
ms.date: 10/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 65501
ms.assetid: 25041ff0-bafe-484d-a94a-e1772ad43204
ms.search.region: Global
ms.search.industry: Retail
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bc70b9cffd8716bc1d90cdb611076b4fc0bf6b30
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "355670"
---
# <a name="weighted-average-with-physical-value-and-marking"></a>Média ponderada com valor físico e marcação

[!include [banner](../includes/banner.md)]

[!include [retail name](../includes/retail-name.md)]

A média ponderada é um modelo de estoque com base no princípio da média ponderada, no qual as saídas do estoque são avaliadas no valor médio dos itens recebidos no estoque durante o período de fechamento de estoque, mais qualquer estoque disponível do período anterior.

Quando você executa um fechamento de estoque, todos os recebimentos são liquidados contra uma saída virtual, que armazena a quantidade e o valor totais recebidos. Essa saída virtual possui um recebimento virtual correspondente a partir do qual as saídas são liquidadas. Dessa forma, todas as saídas obtêm o mesmo custo médio. A saída e o recebimento virtuais podem ser vistos como uma transferência virtual, que é chamada de transferência de fechamento de estoque de média ponderada.

Se houver somente um recebimento, todas as saídas poderão ser liquidadas a partir dele e a transferência virtual não será criada. 

Ao usar a média ponderada, é possível marcar as transações de estoque para que o recebimento de um item específico seja liquidado em vez de usar a regra da média ponderada. 

Recomendamos um fechamento de estoque mensal quando o modelo de estoque de média ponderada for usado. 

O método de custo de estoque da média ponderada é calculado pelo seguinte fórmula:
-   Média ponderada = (Q1\*P1 + Q2\*P2 + Qn\*Pn) / (Q1 + Q2 + Qn)

Transações de estoque deixando saídas de estoque. Isso inclui ordens de venda, diários de estoque, e ordens de produção, que ocorrem a um preço de custo estimado na data de lançamento. Esse preço de custo estimado também é referido como média em execução. No momento do fechamento de estoque, o sistema analisará as transações de estoque para períodos anteriores e atuais, além de determinar quais dos seguintes princípios de fechamento devem ser usados.
-   Liquidação direta
-   Liquidação resumida

As liquidações são lançamentos de fechamento de estoque que ajustam as saídas para a média ponderada correta a partir da data de fechamento. Os seguintes exemplos ilustram o efeito do uso da média ponderada com cinco configurações diferentes:
-   Liquidação direta de média ponderada sem a opção Incluir valor físico
-   Liquidação resumida de média ponderada sem a opção Incluir valor físico
-   Liquidação direta de média ponderada com a opção Incluir valor físico
-   Liquidação resumida de média ponderada com a opção Incluir valor físico
-   Média ponderada com a marcação

## <a name="weighted-average-direct-settlement-without-include-physical-value"></a>Liquidação direta de média ponderada sem incluir valor físico
O princípio de liquidação direta é o mesmo usado para a média ponderada em versões anteriores. O sistema liquidará diretamente entre recebimentos e saídas. O sistema usa esse princípio de liquidação direta em certas situações específicas:
-   Um recebimento e uma ou mais saídas foram lançadas no período
-   Somente saídas foram lançadas no período e o estoque contém itens disponíveis de um fechamento anterior

Foram lançados um recebimento e uma saída atualizados financeiramente no cenário das seções a seguir. Durante o fechamento de estoque, o sistema liquidará o recebimento diretamente contra a saída e não será necessário nenhum ajuste para o preço de custo na saída. As transações a seguir são ilustradas no gráfico.
-   1a. Recebimento físico de estoque atualizado para uma quantidade de 5 a BRL 10,00 cada
-   1b. Recebimento financeiro de estoque atualizado para uma quantidade de 5 a BRL 10,00 cada
-   2a. Saída física de estoque atualizada para uma quantidade de 2 a BRL 10,00 cada
-   2b. Saída financeira de estoque atualizada para uma quantidade de 2 a BRL 10,00 cada
-   3. O fechamento de estoque é executado usando o método de liquidação direta para liquidar o recebimento financeiro de estoque para a saída financeira de estoque.

O diagrama a seguir ilustra essa série de transações com os efeitos de escolher o Modelo de estoque de média ponderada e o princípio de liquidação direta sem a opção Incluir valor físico. 

![DS de média ponderada sem Incluir Valor Físico](./media/weightedaveragedirectsettlementwithoutincludephysicalvalue.gif) 

**Chave para o diagrama**
- As transações de estoque são representadas por setas verticais.
- Os recebimentos no estoque são representados por setas verticais sobre a linha do tempo.
- Saídas fora do estoque são representadas por setas verticais abaixo da linha do tempo.
- Acima (ou abaixo) de cada seta vertical, o valor da transação de estoque é especificado no formato de quantidade x preço unitário.
- Um valor de transação de estoque envolvido por colchetes indica que a transação de estoque é lançada fisicamente no estoque.
- Um valor de transação de estoque sem colchetes indica que a transação de estoque é lançada financeiramente no estoque.
- Cada nova transação de recebimento ou saída é designada com uma nova etiqueta.
- Cada seta vertical é rotulada com um identificador seqüencial, como *1a*. Os identificadores indicam a seqüência de lançamentos de transação de estoque na linha do tempo.
- Os fechamentos de estoque são representados por uma linha tracejada vertical vermelha e a etiqueta Fechamento de Estoque.
- As liquidações executadas pelo fechamento de estoque são representadas por setas vermelhas pontilhadas na diagonal de um recebimento para uma saída.

## <a name="weighted-average-summarized-settlement-without-the-include-physical-value-option"></a>Liquidação resumida de média ponderada sem a opção Incluir valor físico
A média ponderada usa o princípio de liquidação que todos os recebimentos em um período de fechamento são resumidos em uma transação chamada Fechamento de estoque de média ponderada. Todos os recebimentos para o período serão liquidados contra a saída da recém criada transação de transferência de estoque. Todas as saídas para o período serão liquidadas contra o recebimento da nova transação de transferência de estoque. Se o estoque disponível for positivo depois do fechamento de estoque, esse estoque disponível e o valor do estoque são resumidos na nova transação de transferência de estoque (recebimento). Se o estoque disponível for negativo depois do fechamento de estoque, o estoque disponível e o valor do estoque são a soma de saídas individuais que não foram liquidadas completamente. No cenário abaixo, vários recebimentos atualizados financeiramente e uma saída foram lançados. 

Durante o fechamento de estoque, o sistema gerará e lançará a transação de transferência de estoque resumida para liquidar todos os recebimentos para o período contra a transação de saída de transferência de estoque resumida. Todas as saídas lançadas para o período serão liquidadas contra a transação de recebimento de transferência de estoque resumido. A média ponderada é calculada em BRL 15,00. A saída foi lançada originalmente com um preço de custo estimado de R$ 14,67. Portanto, um ajuste de R$ 0,33 negativos será criado e lançado na saída. A partir da data de fechamento do estoque, o estoque disponível é de 3 peças com um valor de BRL 45,00. 

As transações a seguir são ilustradas no gráfico abaixo:
-   1a. Recebimento físico de estoque atualizado para uma quantidade de 2 ao custo de BRL 11,00 cada.
-   1b. Recebimento financeiro de estoque atualizado para uma quantidade de 2 ao custo de BRL 14,00 cada.
-   2a. Recebimento físico de estoque atualizado para uma quantidade de 1 ao custo de BRL 12,00 cada.
-   2b. Recebimento financeiro de estoque atualizado para uma quantidade de 1 ao custo de BRL 16,00 cada.
-   3a. Saída física de estoque atualizada para uma quantidade de 1 ao custo de BRL 14,67 cada (média ponderada).
-   3b. Saída financeira de estoque atualizada para uma quantidade de 1 ao custo de BRL 14,67 cada (média ponderada).
-   4a. Recebimento físico de estoque atualizado para uma quantidade de 1 ao custo de BRL 14,00 cada.
-   4b. Recebimento financeiro de estoque atualizado para uma quantidade de 1 ao custo de BRL 16,00 cada.
-   5. O fechamento de estoque é executado.
-   6a. Saída financeira de “transação de fechamento de estoque de média ponderada” é criada para somar as liquidações para todos os recebimentos financeiros de estoque.
-   6b. Recebimento financeiro de “transação de fechamento de estoque de média ponderada” é criado como compensação para 5a.

O diagrama a seguir ilustra essa série de transações com os efeitos de escolher o Modelo de estoque de média ponderada e o princípio de liquidação resumida sem a opção Incluir valor físico. 

![SS de média ponderada sem Incluir Valor Físico    ](./media/weightedaveragesummarizedsettlementwithoutincludephysicalvalue.gif) 

**Chave para o diagrama**
- As transações de estoque são representadas por setas verticais.
- Os recebimentos no estoque são representados por setas verticais sobre a linha do tempo.
- Saídas fora do estoque são representadas por setas verticais abaixo da linha do tempo.
- Acima (ou abaixo) de cada seta vertical, o valor da transação de estoque é especificado no formato de quantidade x preço unitário.
- Um valor de transação de estoque envolvido por colchetes indica que a transação de estoque é lançada fisicamente no estoque.
- Um valor de transação de estoque sem colchetes indica que a transação de estoque é lançada financeiramente no estoque.
- Cada nova transação de recebimento ou saída é designada com uma nova etiqueta.
- Cada seta vertical é rotulada com um identificador seqüencial, como *1a*. Os identificadores indicam a seqüência de lançamentos de transação de estoque na linha do tempo.
- Os fechamentos de estoque são representados por uma linha tracejada vertical vermelha e a etiqueta Fechamento de Estoque.
- As liquidações executadas pelo fechamento de estoque são representadas por setas vermelhas pontilhadas na diagonal de um recebimento para uma saída.
- As setas vermelhas ilustram as transações de recebimento liquidadas para a transação de saída criada pelo sistema.
- A seta verde representa a transação de recebimento de compensação gerada pelo sistema para a qual a transação de saída lançada originalmente é liquidada

## <a name="weighted-average-direct-settlement-with-the-include-physical-value-option"></a>Liquidação direta de média ponderada com a opção Incluir valor físico
O parâmetro Incluir valor físico funciona de forma diferente com o modelo de inventário médio ponderado do que em versões anteriores do produto. Marque a caixa Incluir valor físico para um item no formulário Grupo de modelo do item. Em seguida, o sistema usará os recebimentos atualizados fisicamente ao calcular o preço de custo estimado, ou a média em execução. As saídas serão lançadas com base nesse preço de custo estimado durante o período. Durante o fechamento de estoque, os recebimentos atualizados financeiramente serão considerados somente no cálculo de média ponderada. É recomendado um fechamento de estoque mensal ao usar o modelo de estoque de média ponderada. Nesse exemplo de liquidação direta de média ponderada, o grupo de modelo de item é marcado para incluir o valor físico. 

As transações a seguir são ilustradas no gráfico abaixo:
-   1a. Recebimento físico de estoque atualizado para uma quantidade de 1 ao custo de BRL 11,00 cada.
-   1b. Recebimento financeiro de estoque atualizado para uma quantidade de 1 ao custo de BRL 10,00 cada.
-   2a. Recebimento físico de estoque atualizado para uma quantidade de 1 ao custo de BRL 15,00 cada.
-   3a. Saída física de estoque atualizada para uma quantidade de 1 ao custo de BRL 12,50 cada (custo médio, uma vez que o valor de recebimento físico é considerado).
-   3b. Saída financeira de estoque atualizada para uma quantidade de 1 ao custo de BRL 12,50 cada (custo médio, uma vez que o valor de recebimento físico é considerado).
-   4. O fechamento de estoque é executado. Durante o fechamento de estoque, o sistema desconsiderará todas as transações de estoque que foram atualizadas fisicamente. Em vez disso, o princípio de liquidação direta será usado porque existe somente um recebimento financeiro. Um ajuste de BRL 2,50 será lançado para as transações de estoque que foram emitidas financeiramente a partir da data de fechamento de estoque. Depois do fechamento de estoque, o estoque disponível será uma quantidade de 1 com um preço de custo médio de BRL 15,00.

O diagrama a seguir ilustra essa série de transações com os efeitos de escolher o Modelo de estoque de média ponderada e o princípio de liquidação direta com a opção Incluir valor físico. 

![DS de média ponderada com Incluir Valor Físico](./media/weightedaveragedirectsettlementwithincludephysicalvalue.gif) 

**Chave para o diagrama**
- As transações de estoque são representadas por setas verticais.
- Os recebimentos no estoque são representados por setas verticais sobre a linha do tempo.
- Saídas fora do estoque são representadas por setas verticais abaixo da linha do tempo.
- Acima (ou abaixo) de cada seta vertical, o valor da transação de estoque é especificado no formato de quantidade x preço unitário.
- Um valor de transação de estoque envolvido por colchetes indica que a transação de estoque é lançada fisicamente no estoque.
- Um valor de transação de estoque sem colchetes indica que a transação de estoque é lançada financeiramente no estoque.
- Cada nova transação de recebimento ou saída é designada com uma nova etiqueta.
- Cada seta vertical é rotulada com um identificador seqüencial, como *1a*. Os identificadores indicam a seqüência de lançamentos de transação de estoque na linha do tempo.
- Os fechamentos de estoque são representados por uma linha tracejada vertical vermelha e a etiqueta Fechamento de Estoque.
- As liquidações executadas pelo fechamento de estoque são representadas por setas vermelhas pontilhadas na diagonal de um recebimento para uma saída.

## <a name="weighted-average-summarized-settlement-with-the-include-physical-value-option"></a>Liquidação resumida de média ponderada com a opção Incluir valor físico
O parâmetro Incluir valor físico funciona de forma diferente com a média ponderada do que nas versões anteriores. Marque a caixa Incluir valor físico para um item na página Grupo de modelo do item. Em seguida, o sistema usará os recebimentos atualizados fisicamente no cálculo do preço de custo estimado, ou a média em execução. As saídas serão lançadas com base nesse preço de custo estimado durante o período. Durante o fechamento de estoque, os recebimentos atualizados financeiramente serão considerados somente no cálculo de média ponderada. É recomendado um fechamento de estoque mensal ao usar o modelo de estoque de média ponderada. Nesse exemplo de liquidação resumida de média ponderada, o modelo de estoque é marcado para incluir valor físico. 

As transações a seguir são ilustradas no gráfico abaixo:
-   1a. Recebimento físico de estoque atualizado para uma quantidade de 2 ao custo de BRL 11,00 cada.
-   1b. Recebimento financeiro de estoque atualizado para uma quantidade de 2 ao custo de BRL 14,00 cada.
-   2. Recebimento físico de estoque atualizado para uma quantidade de 1 ao custo de BRL 10,00 cada.
-   3a. Recebimento físico de estoque atualizado para uma quantidade de 1 ao custo de BRL 12,00 cada.
-   3b. Recebimento financeiro de estoque atualizado para uma quantidade de 1 ao custo de BRL 16,00 cada.
-   4a. Saída física de estoque atualizada para uma quantidade de 1 ao custo de BRL 13,50 cada (custo médio, uma vez que o valor de recebimento físico é considerado).
-   4b. Saída financeira de estoque atualizada para uma quantidade de 1 ao custo de BRL 13,50 cada (custo médio, uma vez que o valor de recebimento físico é considerado).
-   5a. Recebimento físico de estoque atualizado para uma quantidade de 1 ao custo de BRL 14,00 cada.
-   5b. Recebimento financeiro de estoque atualizado para uma quantidade de 1 ao custo de BRL 16,00 cada.
-   6. O fechamento de estoque é executado. Durante o fechamento de estoque, o sistema desconsiderará todas as transações de estoque são atualizadas somente fisicamente. O princípio de liquidação resumida será usado porque existe somente um recebimento financeiro. Um ajuste de BRL 1,50 será lançado para as transações de estoque que foram emitidas financeiramente a partir da data de fechamento de estoque. Depois do fechamento de estoque, o estoque disponível será uma quantidade de 3 com um preço de custo médio de BRL 15,00.
-   7a. Saída financeira de “transação de fechamento de estoque de média ponderada” é criada para somar as liquidações para todos os recebimentos financeiros de estoque.
-   7b. Recebimento financeiro de “transação de fechamento de estoque de média ponderada” é criado como compensação para 5a.

O diagrama a seguir ilustra essa série de transações com os efeitos de escolher o Modelo de estoque de média ponderada e o princípio de liquidação resumida sem a opção Incluir valor físico. 

![SS de média ponderada com Incluir Valor Físico    ](./media/weightedaveragesummarizedsettlementwithincludephysicalvalue.gif) 

**Chave para o diagrama**
- As transações de estoque são representadas por setas verticais.
- Os recebimentos no estoque são representados por setas verticais sobre a linha do tempo.
- Saídas fora do estoque são representadas por setas verticais abaixo da linha do tempo.
- Acima (ou abaixo) de cada seta vertical, o valor da transação de estoque é especificado no formato de quantidade x preço unitário.
- Um valor de transação de estoque envolvido por colchetes indica que a transação de estoque é lançada fisicamente no estoque.
- Um valor de transação de estoque sem colchetes indica que a transação de estoque é lançada financeiramente no estoque.
- Cada nova transação de recebimento ou saída é designada com uma nova etiqueta.
- Cada seta vertical é rotulada com um identificador seqüencial, como 1a. Os identificadores indicam a seqüência de lançamentos de transação de estoque na linha do tempo.
- Os fechamentos de estoque são representados por uma linha tracejada vertical vermelha e a etiqueta Fechamento de Estoque.
- As liquidações executadas pelo fechamento de estoque são representadas por setas vermelhas pontilhadas na diagonal de um recebimento para uma saída.
- As setas vermelhas ilustram as transações de recebimento liquidadas para a transação de saída criada pelo sistema.
- A seta verde representa a transação de recebimento de compensação gerada pelo sistema para a qual a transação de saída lançada originalmente é liquidada

## <a name="weighted-average-with-marking"></a>Média ponderada com a marcação
A marcação é um processo que permite vincular ou marcar uma transação de saída para uma transação de recebimento. A marcação pode ocorrer antes ou depois que a transação for lançada. É possível usar a marcação quando desejar verificar o custo exato do estoque quando a transação é lançada ou quando o fechamento de estoque é executado. 

Por exemplo, seu departamento de Atendimento ao Cliente aceitou uma ordem urgente de um cliente importante. Será necessário pagar mais por esse item para atender as solicitações do cliente, pois esta é uma ordem de urgência. É necessário ter certeza de que o custo desse item de estoque é refletido na margem ou no custo dos produtos vendidos (COGS) para essa fatura de ordem de venda. 

Quando a ordem de compra é lançada, o estoque é recebido ao custo de BRL 120,00. Por exemplo, esse documento de ordem de venda é marcado para a ordem de compra antes do lançamento da guia de remessa ou fatura. Em seguida, o COGS será de R$ 120,00 em vez do custo médio atual para o item. Se a guia de remessa de ordem de vendas ou a nota fiscal for lançada antes que a marcação ocorra, os COGS serão lançados no preço de custo médio. 

Antes que fechamento de estoque seja executado, essas duas transações ainda podem ser marcadas uma para a outra. 

Uma transação de recebimento é marcada para uma transação de saída. Em seguida, o método de validação selecionado para o grupo de modelo de item do item será desconsiderado e o sistema liquidará essas transações entre si. 

É possível marcar uma transação de saída para um recebimento antes que a transação seja lançada. Você pode fazer isso em uma linha da ordem de venda na página Detalhes da ordem de venda. As transações de recebimento abertas são exibidas na página Marcação. 

É possível marcar uma transação de saída para um recebimento após a transação ter sido lançada. Você pode corresponder ou marcar uma transação de saída para uma transação de recebimento aberta para um item inventariado de um diário de ajuste de estoque lançado. 

As transações a seguir são ilustradas no gráfico abaixo:
-   1a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 10,00 cada.
-   1b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 10,00 cada.
-   2a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 20,00 cada.
-   2b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 20,00 cada.
-   3a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 25,00 cada.
-   4a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 30,00 cada.
-   4b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 30,00 cada.
-   5a. Saída física de estoque para uma quantidade de 1 a um preço de custo de BRL 21,25 (média de transações atualizadas financeiramente e fisicamente).
-   5b. Saída financeira para uma quantidade de 1 é marcada para o recebimento de estoque 2b antes da transação ser lançada. Essa transação é lançada com um preço de custo de BRL 20,00.
-   6a. Saída física de estoque para uma quantidade de 1 a um preço de custo de BRL 21,25 cada.
-   7 Fechamento de estoque executado. Uma vez que as transações atualizadas financeiramente são marcadas para um recebimento existente, essas transações são liquidadas uma para a outra e nenhum ajuste é feito.

O novo preço de custo médio reflete a média das transações atualizadas financeira e fisicamente em BRL 27,50. 

O diagrama a seguir ilustra essa série de transações com os efeitos de escolher o modelo de estoque de média ponderada com marcação. 

![Média ponderada com Marcação    ](./media/weightedaveragewithmarking.gif) 

**Chave para o diagrama**
- As transações de estoque são representadas por setas verticais.
- Os recebimentos no estoque são representados por setas verticais sobre a linha do tempo.
- Saídas fora do estoque são representadas por setas verticais abaixo da linha do tempo.
- Acima (ou abaixo) de cada seta vertical, o valor da transação de estoque é especificado no formato quantidade x preço unitário.
- Um valor de transação de estoque envolvido por colchetes indica que a transação de estoque é lançada fisicamente no estoque.
- Um valor de transação de estoque sem colchetes indica que a transação de estoque é lançada financeiramente no estoque.
- Cada nova transação de recebimento ou saída é designada com uma nova etiqueta.
- Cada seta vertical é rotulada com um identificador seqüencial, como *1a*. Os identificadores indicam a seqüência de lançamentos de transação de estoque na linha do tempo.
- Os fechamentos de estoque são representados por uma linha tracejada vertical vermelha e a etiqueta Fechamento de Estoque.
- As liquidações executadas pelo fechamento de estoque são representadas por setas vermelhas pontilhadas na diagonal de um recebimento para uma saída.






---
title: Visão geral sobre conciliação de faturas de contas a pagar
description: A conciliação de faturas de contas a pagar é o processo de conciliar as informações da fatura do fornecedor e do recebimento do produto.
author: abruer
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendInvoicePostingHistory
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "27361"
- intro-internal
ms.assetid: 9f3dace7-05d8-4974-8f85-aca2e224876c
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3c9f7c19d81a22feaeccc31a3f3d390b1a721485083c32e215b155e7896a06d7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6737421"
---
# <a name="accounts-payable-invoice-matching-overview"></a>Visão geral sobre conciliação de faturas de contas a pagar

[!include [banner](../includes/banner.md)]

A conciliação de faturas de contas a pagar é o processo de conciliar as informações da fatura do fornecedor e do recebimento do produto.

Ao conciliar documentos, as diferenças entre esses documentos são chamadas discrepâncias de conciliação. As discrepâncias de conciliação são comparadas com as tolerâncias especificadas. Se uma discrepância de conciliação exceder a porcentagem ou valor de tolerância, os ícones de variação na correspondência são exibidos na página Fatura de fornecedor e na página Histórico de fatura e detalhes de conciliação. 

Por exemplo, você insere uma ordem de compra com um item de linha para mil baterias pelo preço de 1,00 cada. A ordem de compra é aprovada e enviada para o fornecedor, que envia mil baterias. O fornecedor remete 1.000 baterias e você insere um recebimento de produtos para 1.000 baterias pelo preço de 1,00 cada. O custo de estoque das baterias é atualizado com esse preço. 

Uma fatura é recebida para 1.000 baterias pelo preço de 1,10 cada. A política da entidade legal permite uma tolerância de preço unitário líquido de 5 por cento para essa categoria de item. Um preço de 1,05 seria aceitável, mas 1,10 não. Quando você inserir as informações da fatura, uma discrepância na conciliação é identificada e você pode salvar a fatura até que a discrepância seja resolvida.

Você pode usar os seguintes tipos de conciliação de faturas de contas a pagar:

-   Conciliação de totais de fatura – Concilia os valores totais na fatura com valores totais da ordem de compra. Esse tipo de conciliação de faturas inclui o menor valor de detalhe, de forma que você possa usar esta opção para configurar os controles que minimizam o tempo da equipe que são necessários para rever as informações na conciliação de faturas.
-   Conciliação dupla – Concilia as informações sobre preços na fatura com as informações sobre preço na ordem de compra.
-   Conciliação tripla – Concilia as informações sobre preços na fatura com as informações sobre preço na ordem de compra. Também concilia as informações de quantidade na fatura com as informações de quantidade nos recebimentos de produtos que estão selecionados na fatura.
-   Conciliação de encargos – Concilia as informações de encargos (valores) na fatura com as informações de encargo (valores) na ordem de compra.

> [!NOTE]
> A validação de outros formulários de fatura pode ser feita usando as políticas de fatura do fornecedor. 

A conciliação dupla e a conciliação tripla conciliam as informações de preço pelo preço da unidade. Você também pode configurar essas políticas de conciliação para informações de preço de conciliação pelo preço total.
-   Conciliação de preço líquido unitário - Concilia as informações de preço para conciliações duplas ou triplas comparando o preço líquido unitário para cada linha na fatura com o preço líquido unitário na ordem de compra. O preço líquido unitário é determinado pela seguinte fórmula: Valor líquido da linha / Quantidade da linha
-   Conciliação dos totais de preço - Concilia as informações de preço para conciliações duplas ou triplas comparando o valor líquido (total do preço) para cada linha na fatura com o valor líquido na ordem de compra. O valor líquido é determinado pela seguinte fórmula: *(Preço unitário \* Quantidade da linha) + Encargos da linha - Descontos da linha*. Ao combinar os totais de preços por porcentagem, o sistema compara os valores usando a moeda da transação. Ao combinar totais de preço por valor, o sistema compara os valores usando a moeda contábil. Quando você fatura parcialmente uma linha da ordem de compra, a validação da conciliação de preço total ocorre na fatura dessa linha. 

Normalmente, os cálculos de conciliação de fatura são executados automaticamente quando você edita as faturas de fornecedor na página Fatura de fornecedor. Como alternativa, a conciliação de faturas pode ser executada sob demanda, conforme necessário. A conciliação de faturas sob demanda é controlada para a entidade legal pela função Atualizar automaticamente o status do cabeçalho da fatura para na página Parâmetros de contas a pagar na guia Validação de fatura. A conciliação de faturas também pode ser realizada como parte de um processo de revisão de fatura. Você pode exibir os resultados da conciliação de faturas na página Fatura de fornecedor e nas páginas de conciliação de faturas relacionadas.

## <a name="invoice-totals-matching"></a>Conciliação de totais de fatura
Você pode usar a conciliação de totais de fatura para ajudar a garantir que os valores totais da fatura não desviem dos valores esperados em um valor maior do que a variação aceitável. Seis totais são comparados na página Detalhes da conciliação de totais de fatura, conforme mostrado na tabela. Se a tolerância permitida para conciliação de totais da fatura for 20%, a porcentagem de variação de 100% para o valor do desconto total é considerada uma discrepância na conciliação.

| Campo Total    | Total da fatura real | Total da fatura esperado | Porcentagem de variação | Status de conciliação |
|----------------|----------------------|------------------------|---------------------|--------------|
| Saldo        | 495,00               | 495,00                 | 0%                  | Aprovado       |
| Desconto total | 0,00                 | 9,90                   | 100%                | Falhou       |
| Encargos        | 64,90                | 64,90                  | 0%                  | Aprovado       |
| Impostos      | 139,98               | 137,50                 | 2%                  | Aprovado       |
| Arredondamento      | 0,00                 | 0,00                   | 0%                  | Aprovado       |
| Valor da fatura | 699,88               | 687,50                 | 2%                  | Aprovado       |

A conciliação de totais de fatura é controlada para a entidade legal pela alternância dos totais de faturas de correspondência na página Parâmetros de contas a pagar. A conciliação é realizada nos totais da fatura esperada e nos totais da fatura real. Os totais de fatura esperados são calculados com base nos preços, encargos e informações de imposto da ordem de compra e das quantidades da fatura.

## <a name="two-way-price-totals-matching"></a>Conciliação de totais de preço dupla
Use a conciliação dupla para ajudar a garantir que a variação entre as informações de preço na ordem de compra e a invoice está dentro das tolerâncias aceitáveis. Você pode comparar as informações de preço para o valor líquido de cada linha da fatura e todas as linhas na fatura pendentes e lançadas anteriormente, com o valor líquido da linha da ordem de compra correspondente. Isso é chamado de conciliação de totais de preço. 

A conciliação de totais de preço podem ser baseada em uma porcentagem, um valor ou uma porcentagem e valor. 

Se uma porcentagem de tolerância do total de preço de compra for especificada, cinco campos são comparados, como mostra a tabela a seguir. Como a porcentagem de tolerância do total de preço de compra é 10%, a porcentagem de variação total do preço de 50% representa uma discrepância na conciliação.

| Status de conciliação | Valor líquido da fatura | Valor líquido esperado | Total de preço de compra não conciliado (valor de variação) | Porcentagem total de preço de compra não conciliado (porcentagem de variação) | Porcentagem de tolerância do total de preço de compra |
|--------------|--------------------|---------------------|--------------------------------------------------|-----------------------------------------------------------------|----------------------------------------|
| Aprovado       | 105,00             | 100,00              | 5,00                                             | 5%                                                              | 10%                                    |
| Falhou       | 150,00             | 100,00              | 50,00                                            | 50%                                                             | 10%                                    |

Se um valor de tolerância do total de preço de compra for especificado, cinco campos são comparados, como mostra a tabela a seguir. Como o valor de tolerância do total de preço de compra é 100,00%, o valor de variação do total do preço de 105,00 representa uma discrepância na conciliação.

| Status de conciliação | Valor líquido da fatura | Valor líquido esperado | Total de preço de compra não conciliado (valor de variação) | Total de preço de compra não conciliado na moeda contábil (valor de variação) | Tolerância do total de preço de compra |
|--------------|--------------------|---------------------|--------------------------------------------------|-------------------------------------------------------------------------|--------------------------------|
| Aprovado       | 150,00             | 100,00              | 50,00                                            | 50,00                                                                   | 100,00                         |
| Falhou       | 205,00             | 100,00              | 105,00                                           | 105,00                                                                  | 100,00                         |

Se a conciliação dos totais do preço estiver definida com uma tolerância de porcentagem e uma tolerância de valor, algumas vezes considerado um valor que não deve ser excedido, ambas tolerâncias são consideradas ao avaliar uma linha como discrepância de conciliação. Se a porcentagem ou o valor excederem a tolerância, como mostrado nas linhas 150,00 e 205,00 na tabela a seguir, a linha tem uma discrepância de conciliação.

| Status de conciliação | Valor líquido da fatura | Valor líquido esperado | Porcentagem total de preço de compra não conciliado (porcentagem de variação) | Porcentagem de tolerância do total de preço de compra | Total de preço de compra não conciliado na moeda contábil (valor de variação) | Tolerância do total de preço de compra |
|--------------|--------------------|---------------------|-----------------------------------------------------------------|----------------------------------------|-------------------------------------------------------------------------|--------------------------------|
| Aprovado       | 105,00             | 100,00              | 5%                                                              | 10%                                    | 5,00                                                                    | 100,00                         |
| Falhou       | 150,00             | 100,00              | 50%                                                             | 10%                                    | 50,00                                                                   | 100,00                         |
| Falhou       | 205,00             | 100,00              | 105%                                                            | 10%                                    | 105,00                                                                  | 100,00                         |

A conciliação dupla é controlada para a entidade legal no campo Política de conciliação de linha na página Parâmetros de contas a pagar. Dependendo da seleção no campo Permitir a substituição da política de conciliação, você pode selecionar a conciliação dupla para um fornecedor, item ou combinação de item e fornecedor específica na página Política de conciliação, e para uma ordem de compra específica na página Ordem de compra.

A conciliação de totais de preço é controlada para a entidade legal pela pelo campo Conciliar totais de preço na página Parâmetros de contas a pagar. A porcentagem e o valor de tolerância (valor que não deve ser excedido) do total do preço da compra também são especificados na página.

## <a name="two-way-net-unit-price-matching"></a>Conciliação de preço líquido unitário
Use a conciliação dupla para ajudar a garantir que a variação entre as informações de preço na ordem de compra e a invoice está dentro das tolerâncias aceitáveis. Você pode comparar as informações de preço unitário para o preço unitário de cada item na fatura. Isso é chamado de conciliação do preço líquido. 

Nove valores de linha são comparados na página Detalhes da conciliação de fatura, conforme mostrado na tabela. Se a tolerância de preço permitida para conciliação de preço é 10%, a variação 22,61% do preço unitário líquido será considerada uma discrepância na conciliação.

| Campo Linha                    | Valor da fatura | Valor da ordem de compra | Porcentagem de variação | Status de conciliação |
|-------------------------------|---------------|----------------------|---------------------|--------------|
| Preço unitário                    | 55,40         | 55,38                | 0%                  | Aprovado       |
| Unidade de preço                    | 1,00          | 1,00                 | 0%                  | Aprovado       |
| Encargos de compras          | 50,00         | 0,00                 | 100%                | Falhou       |
| Desconto                      | 0,00          | 0,00                 | 0%                  | Aprovado       |
| Percentual de desconto              | 0,00          | 0,00                 | 0%                  | Aprovado       |
| Desconto combinado            | 0,00          | 0,00                 | 0%                  | Aprovado       |
| Porcentagem de desconto combinado | 0,00          | 0,00                 | 0%                  | Aprovado       |
| Valor líquido                    | 271,60        | 221,52               | 22,61%              | Falhou       |
| Preço líquido unitário                | 67,9000       | 55,3800              | 22,61%              | Falhou       |

A conciliação dupla é controlada para a entidade legal no campo Política de conciliação de linha na página Parâmetros de contas a pagar. Dependendo da seleção no campo Permitir a substituição da política de conciliação, você pode selecionar a conciliação dupla para um fornecedor, item ou combinação de item e fornecedor específica na página Política de conciliação, e para uma ordem de compra específica na página Ordem de compra. 

A conciliação de preço líquido unitário é controlada para a entidade legal pelo campo Permitir validação de conciliação de fatura na página Parâmetros de contas a pagar. As porcentagens de tolerância de preços líquidos unitários podem ser configuradas para itens, grupos de itens, fornecedores, grupos de fornecedores, combinações de item e fornecedor ou entidade legal usando a página Tolerâncias de preço.

## <a name="two-way-price-totals-matching-and-net-unit-price-matching"></a>Conciliação de totais de preço dupla e conciliação de preços unitários líquidos
Você pode usar a conciliação de totais de preço e a conciliação de preços unitários juntas. Este exemplo supõe a seguinte configuração:

-   A tolerância de preço líquido unitário do item da unidade de USB é 10%.
-   A tolerância de conciliação para os preços totais são de 15% ou 500,00.

A ordem de compra contém a seguinte linha.

| Nº do item | Quantidade | Preço unitário | Valor líquido |
|-------------|----------|------------|------------|
| Unidade USB   | 1.000    | 10,00      | 10.000,00  |

Três faturas são lançadas, como mostra a tabela a seguir. Há uma discrepância na conciliação de faturas para a fatura 3 porque a variação de 1.880,00 excede o valor de tolerância do total de preço de compra de 500,00. Para a conciliação de totais de preço, o valor líquido da fatura inclui todas as faturas lançadas anteriormente para a fatura na qual você está trabalhando no momento.

| Nº do item          | Quantidade | Preço unitário | Valor líquido | Conciliação de preço | Conciliação de total de preço |
|----------------------|----------|------------|------------|-------------|-------------------|
| Fatura 1: unidade de USB | 800      | 10,80      | 8.640,00   | Aprovado      | Aprovado            |
| Fatura 2: unidade de USB | 100      | 10,80      | 1.080,00   | Aprovado      | Aprovado            |
| Fatura 3: unidade de USB | 200      | 10,80      | 2.160,00   | Aprovado      | Falhou            |
| Total                |          |            | 11.880,00  |             |                   |

## <a name="three-way-matching"></a>Conciliação tripla

Use a conciliação tripla para ajudar a garantir que a variação entre os informações de preço na ordem de compra e na fatura estejam dentro de tolerâncias aceitáveis e a garantir que a quantidade na fatura corresponda à quantidade nos recebimentos de produtos correspondentes.

Os mesmos valores de linha são comparados na página Detalhes da conciliação de fatura como para a conciliação dupla. Além de isso, a quantidade na fatura é conciliada com os recebimentos de produtos que você incluiu. Se a quantidade da fatura for diferente da quantidade recebimento de produtos conciliada, ocorrerá um erro de conciliação.

| Campo Linha                    | Valor da fatura | Valor da ordem de compra | Porcentagem de variação | Status de conciliação |
|-------------------------------|---------------|----------------------|---------------------|--------------|
| Preço unitário                    | 55,40         | 55,38                | 0%                  | Aprovado       |
| Unidade de preço                    | 1,00          | 1,00                 | 0%                  | Aprovado       |
| Encargos de compras          | 50,00         | 0,00                 | 100%                | Falhou       |
| Desconto                      | 0,00          | 0,00                 | 0%                  | Aprovado       |
| Percentual de desconto              | 0,00          | 0,00                 | 0%                  | Aprovado       |
| Desconto combinado            | 0,00          | 0,00                 | 0%                  | Aprovado       |
| Porcentagem de desconto combinado | 0,00          | 0,00                 | 0%                  | Aprovado       |
| Valor líquido                    | 271,60        | 221,52               | 22,61%              | Falhou       |
| Preço líquido unitário                | 67,9000       | 55,3800              | 22,61%              | Falhou       |

| Campo Linha                     | Valor da fatura | Status de conciliação |
|--------------------------------|---------------|--------------|
| Faturar quantidade               | 4,00          |              |
| Total de recebimentos de produtos conciliados | 0,00          | Falhou       |

A conciliação tripla é controlada para a entidade legal no campo Política de conciliação de linha na página Parâmetros de contas a pagar. Dependendo da seleção no campo Permitir a substituição da política de conciliação, você pode selecionar a conciliação tripla para um fornecedor, item ou combinação de item e fornecedor específica na página Política de conciliação, e para uma ordem de compra específica na página Ordem de compra.

## <a name="charges-matching"></a>Conciliação de encargos
Você pode usar a conciliação de encargos para ajudar a garantir que os valores de encargos não desviem dos valores esperados em um valor maior do que a porcentagem aceitável. Os valores totais para cada código de encargos que se aplicam à fatura e ordem de compra são comparados na página Comparar valores de encargos - Fatura: como mostra a tabela a seguir. Se a tolerância permitida para o código de encargos é 25%, a porcentagem de variação de 99.999.999.999,99% para o código de encargos de licença é considerada uma discrepância na conciliação.

> [!NOTE] 
> Uma porcentagem de variação de 99.999.999.999,99% significa que o valor esperado com base na ordem de compra é zero e o valor real na fatura é um valor positivo. 

| Status de conciliação de encargos | Código de encargos de fatura | Valor calculado de total real | Valor calculado de total esperado | Valor de variação | Porcentagem de variação | Porcentagem de tolerância |
|----------------------|----------------------|-------------------------------|---------------------------------|-----------------|---------------------|----------------------|
| Falhou               | Licença              | 25                            | 0                               | 25              | 99.999.999.999,99%  | 25%                  |
| Aprovado               | Frete              | 200                           | 200                             | 0               | 0%                  | 25%                  |
| Falhou               | Agilizar             | 4                             | 2                               | 2               | 100%                | 25%                  |

A conciliação de encargos é controlada para a entidade legal pela alternância dos encargos de correspondência na página Parâmetros de contas a pagar. Você pode configurar as porcentagens de tolerância de variação para os encargos na página Tolerâncias de encargos.

> [!NOTE]
> A conciliação de encargos é realizada somente nos códigos de encargos para os quais a opção Comparar ordem de compra com valores da fatura é selecionada na página Código de encargos.

## <a name="related-functionality"></a>Funcionalidade relacionada
Geralmente, as faturas de fornecedores se baseiam nos recebimentos de produtos, que representam os envios reais, em vez das ordens de compra. Às vezes, os valores faturados não coincidem com os valores da ordem de compra e, ocasionalmente, as quantidades enviadas não correspondem às quantidades faturadas. Você pode ajudar a gerenciar essas informações das seguintes maneiras:
-   Crie uma fatura do fornecedor com base em recebimentos de produtos. Os recebimentos de produtos são sugeridas automaticamente para faturas e você pode selecionar quais os recebimentos de produto a serem usados. Você também pode selecionar linhas de recebimento de produtos específicas para diversas ordens de compra, se precisar.
-   Exiba e aprove diferenças de quantidade entre a quantidade faturada na fatura e a quantidade recebida no recebimento de produtos. Se houver discrepâncias, você poderá salvar a fatura e depois, conciliá-la com o recebimento de produtos ou alterar a quantidade faturada para conciliar com a quantidade recebida.
-   Insira os valores da fatura que não foram incluídos na ordem de compra original, para que as informações da fatura sejam conciliadas com a fatura que você recebeu do fornecedor. Você pode comparar os encargos de ordens de compra com os encargos de faturas. Se necessário, é possível adicionar encargos às faturas e alocá-los nas linhas de fatura.
-   Exiba e aprove discrepâncias na conciliação de preços entre o preço unitário líquido da fatura e o preço unitário líquido da ordem de compra. Você pode configurar percentuais de tolerância de preços para entidades legais, fornecedores e itens. Se o preço da linha da fatura do fornecedor não estiver dentro da tolerância de preço aceitável, você poderá salvar a fatura até que seja aprovada para lançamento ou até receber uma correção do fornecedor.

Para obter mais informações, consulte [Políticas de conciliação tripla](three-way-matching-policies.md) e [Configurar a validação de conciliação de faturas de Contas a pagar](tasks/set-up-accounts-payable-invoice-matching-validation.md). 






[!INCLUDE[footer-include](../../includes/footer-banner.md)]

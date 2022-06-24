---
title: Materiais e taxas de embalagem
description: Este artigo fornece informações sobre as taxas de material de embalagem que são pagas para reciclar empresas em intervalos específicos.
author: Mirzaab
ms.date: 02/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventPackagingGroup, InventPackagingMaterialCode, InventPackagingMaterialFee, InventPackagingMaterialTrans, InventPackagingMaterialTransPurch, InventPackagingUnit
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2194
ms.assetid: 040b65dc-43c9-4256-b69f-b2d6e736fbe9
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2020-02-19
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 584bddeaedd461803bb9d62421cbb646178164a3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901724"
---
# <a name="packing-materials-and-fees"></a>Materiais e taxas de embalagem

[!include [banner](../includes/banner.md)]

As taxas de material de embalagem são pagas a uma empresa de reciclagem em intervalos específicos. Um valor é pago por unidade de peso para cada material com o qual a unidade de embalagem é feita. Apesar de as taxas de material de embalagem são calculadas e relatadas, mas nenhuma transação do razão é lançada, pois essas taxas não são consideradas como taxas que devam ser pagas a uma autoridade.

Os pesos e as taxas dos materiais de embalagem são calculados para as linhas de ordem de venda e compra.

Você pode definir uma ou mais unidades de embalagem para um único item, um grupo de itens (grupo de embalagem) ou todos os itens. Uma unidade de embalagem consiste em materiais de embalagem, seus pesos, além do número de itens incluídos na unidade de embalagem. Um código de material de embalagem é atribuído a cada tipo de material de embalagem definido. Com base no código de material de embalagem, você pode especificar um preço para um período específico. A taxa de material de embalagem é calculada com base nessas informações.

> [!NOTE]
> Mesmo que sua empresa não pague taxas de material de embalagem, você poderá usar a funcionalidade para calcular estatísticas de pesos dos materiais de embalagem.

## <a name="set-up-packing-material-allocation"></a><a name="allocations"></a>Configurar alocação de materiais de embalagem

Para poder calcular os pesos do material de embalagem, as taxas de material de embalagem ou ambas, você deve ativar o cálculo e definir quais materiais e taxas se aplicam a quais itens.

1. Ir para **Gerenciamento de estoque \> Configuração \> Parâmetros de gerenciamento de depósito e estoque**.
1. Na guia **Geral**, na seção **Material de embalagem**, defina a opção **Calcular taxas de material de embalagem** como **Sim**.
1. Acesse **Gerenciamento de estoque \> Configuração \> Material de embalagem \> Grupos de embalagem**, e crie todos os grupos de embalagem que você usa. Todos os itens de um grupo de embalagens usarão a mesma alocação de material de embalagem. Se você não usar grupos de embalagens, poderá ignorar esta etapa.

    > [!TIP]
    > Depois de criar os grupos de embalagens, é possível atribuir um grupo a cada produto conforme a necessidade. Acesse **Gerenciamento de informações sobre produtos \> Produtos \> Produtos liberados**, selecione um produto e, em seguida, na Guia Rápida **Gerenciar estoque**, no campo **Grupo de embalagens**, selecione o grupo de embalagem apropriado.

1. Acesse **Gerenciamento de estoque \> Configuração \> Material de embalagem \> Códigos de material de embalagem**, defina cada tipo de material de embalagem que você usa, e especifique a unidade que o material de embalagem é consumida quando você prepara os envios.
1. Acesse **Gerenciamento de estoque \> Configuração \> Material de embalagem \> Taxas de material de embalagem**, e defina uma taxa para cada tipo de material de embalagem que você acabou de definir. As taxas são calculadas com base no preço por unidade consumido.
1. Para alocar materiais de embalagem para itens, Acesse **Gerenciamento de estoque \> Configuração \> Material de embalagem \> Alocação de material de embalagem** e crie alocações. Você pode criar quantas alocações forem necessárias. Você pode alocar materiais de embalagem para itens individuais, grupos de itens (grupos de embalagens) ou todos os itens, dependendo de como as suas alocações devem ser detalhadas.

    Para cada alocação que você criar, siga estas etapas.

    1. Na Guia Rápida **Geral**, defina os seguintes campos:

        - **Código do item** – Selecione o escopo da alocação:

            - **Tabela** – Crie uma alocação para um único item específico.
            - **Grupo** – crie uma alocação para todos os itens que pertencem a um grupo de embalagens definido na página **Grupos de embalagem**.
            - **Tudo** – cria uma alocação para todos os itens.

            > [!NOTE]
            > Normalmente, você deve tornar todas as suas alocações no mesmo nível (**Tabela**, **Grupo** ou **Todos**). Se você usar mais de um nível, a alocação correspondente mais específica será usada para cada item. (O nível **Tabela** tem precedência sobre o nível **Grupo**, e esses dois níveis têm precedência sobre o nível **Todos**.)

        - **Relação de itens** – se você estiver alocando para um único item, selecione o item. Se você estiver alocando para um grupo de itens, selecione o grupo de embalagens. Se você estiver alocando para todos os itens, deixe este campo em branco.
        - **Configuração**, **Tamanho**, **Cor** e **Estilo** – insira valores para essas dimensões conforme necessário, para definir ainda mais o item para o qual você está alocando.
        - **Unidade de embalagem** – selecione a unidade na qual o item é empacotado quando o material de embalagem é usado. Essa unidade pode ser diferente da unidade em que o item foi comprado e armazenado.
        - **Fator de unidade de embalagem** – insira o fator de conversão usado para converter da unidade de estoque na unidade de embalagem. (A conversão usa a fórmula *Unidades de embalagem* = *Unidades de itens* × *Fator de unidade de embalagem*.)

    1. Na Guia Rápida **Material de embalagem**, adicione uma linha para cada peça de material de embalagem necessária para a alocação atual. Em cada linha, especifique o tipo de material (conforme definido na página **Códigos de material de embalagem**) e o valor que é consumido para cada unidade de remessa do item atual.

## <a name="packing-units-on-sales-order-lines"></a>Unidades de embalagem nas linhas da ordem de venda

Depois de [Ativar o cálculo de taxas de material de embalagem e configurar suas alocações](#allocations), o sistema verifica se as unidades de embalagem estão especificadas para cada item adicionado a uma ordem de venda. Em seguida, ele calcula as taxas necessárias. Quando um item é adicionado a uma ordem de venda, ocorre uma das seguintes etapas:

- **Se uma alocação de embalagem aplica-se ao item:** O sistema atualizará a linha de ordem de venda com a unidade de embalagem especificada e a quantidade de unidade de embalagem. (A quantidade de unidade de embalagem é calculada usando a fórmula *Quantidade de unidade de embalagem* = *Quantidade encomendada* ÷ *Número de itens da unidade de embalagem selecionada*.)
- **Se nenhuma alocação de embalagem aplica-se ao item:** Você poderá inserir manualmente uma unidade de embalagem e uma quantidade de unidade de embalagem na linha de ordem de venda.

Também é possível alterar a unidade de embalagem e a quantidade ao lançar a linha de ordem de venda. Essa funcionalidade é relevante se a linha de ordem de venda for apenas parcialmente entregue ou parcialmente faturada.

Quando você fatura a ordem de venda, o sistema cria transações de material de embalagem. As transações de material de embalagem contêm os pesos dos materiais de embalagem para a linha de venda. É possível alterar as transações após faturá-las. É possível criar novas transações.

## <a name="packing-units-on-purchase-order-lines"></a>Unidades de embalagem nas linhas da ordem de compra

O sistema não cria transações de material de embalagem para linhas de ordem de compra. Em vez disso, crie transações para as linhas da ordem de compra faturada manualmente na página **Transações de material de embalagem**.

## <a name="set-up-license-numbers-for-customers-that-are-charged-packing-material-fees"></a>Configurar números de licença para clientes com taxas de material de embalagem cobradas

Se as ordens de venda de um cliente específico devem incluir encargos para os materiais de embalagem usados para cada ordem, siga estas etapas.

1. Ir para **Contas recebíveis \> Clientes \> Todos os clientes**.
1. Selecione o cliente que deve ser cobrado pelos materiais de embalagem.
1. Na Guia Rápida **Fatura e entrega**, defina os seguintes campos:

    - Na seção **Imposto sobre vendas**, no campo **Número de licença do imposto de embalagem**, insira o número da licença da empresa.
    - Na seção **Taxa de material de embalagem**, no campo **Número de licença**, insira o número da licença da empresa.

Agora, quando você criar e faturar uma ordem de venda que inclui um ou mais itens que usam materiais de embalagem, a nota fiscal mostrará as taxas de material de embalagem.

Para os clientes que não devem pagar as taxas de material de embalagem, siga as mesmas etapas, mas apague os números de licença dos campos **Número de licença de obrigação de embalagem** e **Número da licença**. As notas fiscais de clientes que não pagam as taxas de material de embalagem mostram os pesos dos materiais de embalagem, mas não mostram as taxas.

Para gerar um relatório que mostre todas as taxas de material de embalagem que sua empresa deverá ter para um período específico, Acesse **Gerenciamento de estoque \> Consultas e relatórios \> Relatórios de material de embalagem \> Cálculo de taxa do material de embalagem**, especifique uma variedade de datas e selecione **OK**.

## <a name="print-packing-material-weights-on-invoices"></a>Imprimir os pesos do material de embalagem nas notas fiscais

Você pode imprimir os pesos do material de embalagem na fatura e indicar quem está pagando as taxas relacionadas. Os pesos são resumidos por código de embalagem.

1. Acesse **Contas a receber \> Configuração \> Parâmetros de contas a receber**.
1. Na guia **Atualizações**, na Guia Rápida **Nota fiscal**, defina a opção **imprimir peso do material de embalagem** como **Sim**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
---
title: Diários de estoque
description: Este tópico descreve como você pode usar diários de estoque para lançar vários tipos de transações de estoque físico.
author: perlynne
manager: AnnBe
ms.date: 04/05/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalBOM, InventJournalCount, InventJournalCountTag, InventJournalLossProfit, InventJournalMovement, InventJournalTransfer, WMSJournalTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 51631
ms.assetid: 3fedeaaf-502f-483c-93d2-ab266828189e
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a7acf4e5397ee7276b0f881f4859267371266de0
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2249531"
---
# <a name="inventory-journals"></a>Diários de estoque

[!include [banner](../includes/banner.md)]

[!include [retail name](../includes/retail-name.md)]

Este tópico descreve como você pode usar diários de estoque para lançar vários tipos de transações de estoque físico.

Os diários de estoque no Supply Chain Management são usados para lançar transações físicas do estoque de vários tipos, como lançamento de emissões e recebimentos, movimentações de estoque, criação de listas de materiais (BOMs) e reconciliação de estoque físico. Todos esses diários de estoque são usados de forma semelhante, mas são divididos em tipos diferentes.

## <a name="types-of-inventory-journals"></a>Tipos de diários de estoque
Os tipos de diário de estoque disponíveis são os seguintes:

-   Movimento
-   Ajuste de estoque
-   Transferência
-   BOM
-   Entrada de item
-   Entrada de produção
-   Contando
-   Contagem de etiquetas

### <a name="movement"></a>Movimento

Quando você usa um diário de movimentação de estoque, você pode adicionar custo a um item ao adicionar o estoque, mas é necessário alocar manualmente os custos adicionais para uma determinada conta contábil especificando uma contrapartida da contabilidade ao criar o diário. Esse tipo de diário de estoque é útil se você quiser substituir as contas de lançamento padrão.

### <a name="inventory-adjustment"></a>Ajuste de estoque

Ao usar um diário de ajuste de estoque, você pode adicionar o custo para um item ao adicionar o estoque. Os custos adicionais são lançados automaticamente em uma conta contábil específica, com base na configuração do perfil de lançamento do grupo de itens. Use este tipo de diário de estoque para atualizar ganhos e perdas para quantidades em estoque quando o item precisar manter a contrapartida padrão da contabilidade. Ao lançar um diário de ajuste de estoque, um recebimento ou saída de estoque é lançado, os valores de estoque são alterados, e as transações do razão são criadas.

### <a name="transfer"></a>Transferência

Você pode usar diários de transferência para transferir itens entre locais de estoque, lotes, ou variantes de produto sem associar nenhuma implicação de custo. Por exemplo, você pode transferir itens de um depósito para outro depósito na mesma empresa. Ao usar um diário de transferência, você deve especificar as dimensões de estoque "de" e "para" (por exemplo, para o site e o depósito). O estoque disponível para as dimensões de estoque definidas é alterado corretamente. As transferências de estoque refletem a movimentação imediata de material. Estoque em trânsito sem rastreamento. Se o estoque em trânsito precisar ser rastreado, você deve usar uma ordem de transferência por vez. Ao lançar um diário de transferência, duas transações de estoque são criadas para cada linha do diário:

-   Uma saída de estoque no local "de".
-   Um recebimento de estoque no local "para".

### <a name="bom"></a>BOM

Ao relatar uma BOM como concluída, você pode criar um diário de BOM. Ao usar um diário de BOM, você pode lançar a BOM diretamente. Este lançamento produz um recebimento de estoque do produto, juntamente com uma BOM associada e uma saída de estoque dos produtos que estão incluídos na BOM. Este tipo de diário de estoque é útil em cenários de produção simples ou de alto volume onde os roteiros não são necessários.

### <a name="item-arrival"></a>Entrada de item

Você pode usar o diário de entrada de item para registrar o recebimento de itens (por exemplo, ordens de compra). Um diário de entrada de itens pode ser criado como parte do gerenciamento de entrada na página **Visão geral da entrada**, ou você pode criar manualmente uma entrada de diário na página **Entrada de item**. Se você habilitar o nome do diário de entrada de itens para verificar os locais de separação, o Supply Chain Management procurará um local para os itens recebidos e, se houver espaço, gerará destinos de localização para os itens de entrada.

### <a name="production-input"></a>Entrada de produção

Os diários de entrada de produção trabalham como os diários de entrada de itens, mas são usados para ordens de produção.

### <a name="counting"></a>Contando

Os diários de contagem permitem corrigir o estoque disponível atual registrado para os itens ou grupos de itens e, em seguida, lançar a contagem física real, de modo que você possa fazer os ajustes necessários para reconciliar as diferenças. Você pode associar políticas de contagem com os grupos de contagem para ajudar os itens do grupo que têm diversas características, de modo que os itens possam ser incluídos em um diário de contagem. Por exemplo, você pode configurar grupos de contagem para itens com uma frequência específica, ou para contar itens quando o estoque ficar em um nível específico. Para obter informações sobre como definir grupos de contagem, consulte [Definir processos de contagem de estoque (Guia de tarefas)](tasks/define-inventory-counting-processes.md).

### <a name="tag-counting"></a>Contagem de etiquetas

Os diários de contagem de etiquetas são usados para atribuir uma etiqueta enumerada a um lote de contagem. A etiqueta deve conter um número de etiqueta, número de item, e quantidade de item. Para garantir que a etiqueta seja usada somente uma vez, e que todas as etiquetas sejam usadas, cada número de item deve ter um conjunto exclusivo de etiquetas com sua própria sequência numérica. Três valores de status podem ser definidos para cada etiqueta:

-   **Usado** – O número de item é contado para a etiqueta.
-   **Anulado** – O número de item é anulado para a etiqueta.
-   **Ausente** – O número de item está faltando para a etiqueta.

Quando você lança um diário de contagem de etiquetas, um novo diário de contagem é criado com base nas linhas do diário de contagem de etiquetas. Para obter mais informações sobre a contagem de etiquetas, consulte [Contagem de etiquetas de estoque](inventory-tag-counting.md).

## <a name="working-with-journals"></a>Trabalhando com diários
Um diário só pode ser acessado por um usuário de cada vez. Se vários usuários precisarem acessar os diários simultaneamente para criar linhas de diário, eles deverão selecionar os diários que não estão sendo usados no momento para impedir a substituição de informações. Em situações onde vários departamentos usam o mesmo tipo de diário, é útil criar vários nomes de diário (por exemplo, um por departamento). Também pode ser útil dividir os diários para que todas as rotinas de lançamento sejam inseridas no próprio diário de estoque exclusivo. Para rotinas de lançamento associadas a transações de estoque, crie um diário para ajustes de estoque periódicos e outro para a contagem de estoque.

## <a name="posting-journal-lines"></a>Lançando linhas de diário
Você pode lançar as linhas de diário que você cria a qualquer momento até que você tenha bloqueado um item de transações adicionais. Os dados que você insere em um diário permanecem nele mesmo que ele seja fechado sem lançar as linhas.

## <a name="data-entity-support-for-inventory-journals"></a>Suporte de entidade de dados para diários de estoque

As entidades de dados oferecem suporte para os seguintes tipos de situações de integração:
-    Serviço síncrono (OData)
-  Integração assíncrona

Para obter mais informações, consulte [Entidades de dados](../../dev-itpro/data-entities/data-entities.md).

> [!NOTE]
> Nem todos os diários de estoque são habilitados por OData, portanto, você não pode usar o conector de dados do Excel para fazer com que os dados sejam publicados, atualizados e importados novamente para o Supply Chain Management. 

Outra diferença entre as entidades de dados do diário é a capacidade de utilizar as entidades compostas, incluindo os dados do cabeçalho e da linha. Atualmente, você pode usar as entidades compostas para:
-   Diário de ajuste de estoque
-   Diários de movimento de estoque

Esses dois diários de estoque suportam somente o cenário *Inicializar estoque* como parte de um projeto de importação do gerenciamento de dados:
-  Quando um número do cabeçalho de diário não for especificado, mas uma sequência numérica for especificada para o tipo de diário, o trabalho de importação criará automaticamente cabeçalhos de diários de 1000 linhas. Por exemplo, a importação de 2020 linhas resultará nos seguintes três cabeçalhos do diário:
    -  Cabeçalho 1: conterá 1000 linhas
    -  Cabeçalho 2: conterá 1000 linhas
    -  Cabeçalho 3: conterá 20 linhas
-  Presume-se que há informações de linha exclusiva por dimensão de estoque, que pode ser um produto, armazenamento e dimensão de rastreamento. Portanto, não será possível importar as linhas de diário onde apenas o campo data de data é diferente das linhas dentro do mesmo projeto de importação.

## <a name="additional-resources"></a>Recursos adicionais

[Entidades de dados](../../dev-itpro/data-entities/data-entities.md)

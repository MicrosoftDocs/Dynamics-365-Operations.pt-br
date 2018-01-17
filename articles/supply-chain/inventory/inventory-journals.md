---
title: "Diários de estoque"
description: "Este artigo descreve como você pode usar diários de estoque para lançar vários tipos de transações de estoque físico."
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventJournalBOM, InventJournalCount, InventJournalCountTag, InventJournalLossProfit, InventJournalMovement, InventJournalTransfer, WMSJournalTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, Retail
ms.custom: 51631
ms.assetid: 3fedeaaf-502f-483c-93d2-ab266828189e
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 968bf9a243d0c0cc9f0dfec474cb207ca32f9eeb
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="inventory-journals"></a>Diários de estoque

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]


Este artigo descreve como você pode usar diários de estoque para lançar vários tipos de transações de estoque físico.

Os diários de estoque no Microsoft Dynamics 365 for Finance and Operations são usados para lançar transações de estoque físico de vários tipos, como lançamento de saídas e recebimentos, movimentos de estoque, criação de listas de materiais (BOMs), e reconciliação de estoque físico. Todos esses diários de estoque são usados de forma semelhante, mas são divididos em tipos diferentes.

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

Quando você usa um diário de movimentação de estoque, você pode adicionar custo a um item ao adicionar o estoque, mas é necessário alocar manualmente os custos adicionais para uma determinada conta contábil especificando uma contrapartida da contabilidade ao criar o diário. Esse tipo de diário de estoque é útil se você desejar lançar um item como despesa em relação a um departamento diferente, ou se você desejar remover os itens do estoque para fins de despesa.

### <a name="inventory-adjustment"></a>Ajuste de estoque

Ao usar um diário de ajuste de estoque, você pode adicionar o custo para um item ao adicionar o estoque. Os custos adicionais são lançados automaticamente em uma conta contábil específica, com base na configuração do perfil de lançamento do grupo de itens. Use este tipo de diário de estoque para atualizar ganhos e perdas para quantidades em estoque quando o item precisar manter a contrapartida padrão da contabilidade. Ao lançar um diário de ajuste de estoque, um recebimento ou saída de estoque é lançado, os valores de estoque são alterados, e as transações do razão são criadas.

### <a name="transfer"></a>Transferência

Você pode usar diários de transferência para transferir itens entre locais de estoque, lotes, ou variantes de produto sem associar nenhuma implicação de custo. Por exemplo, você pode transferir itens de um depósito para outro depósito na mesma empresa. Ao usar um diário de transferência, você deve especificar as dimensões de estoque "de" e "para" (por exemplo, para o site e o depósito). O estoque disponível para as dimensões de estoque definidas é alterado corretamente. As transferências de estoque refletem a movimentação imediata de material. Estoque em trânsito sem rastreamento. Se o estoque em trânsito precisar ser rastreado, você deve usar uma ordem de transferência por vez. Ao lançar um diário de transferência, duas transações de estoque são criadas para cada linha do diário:

-   Uma saída de estoque no local "de"
-   Um recebimento de estoque no local "para"

### <a name="bom"></a>BOM

Ao relatar uma BOM como concluída, você pode criar um diário de BOM. Ao usar um diário de BOM, você pode lançar a BOM diretamente. Este lançamento produz um recebimento de estoque do produto, juntamente com uma BOM associada e uma saída de estoque dos produtos que estão incluídos na BOM. Este tipo de diário de estoque é útil em cenários de produção simples ou de alto volume onde os roteiros não são necessários.

### <a name="item-arrival"></a>Entrada de item

Você pode usar o diário de entrada de item para registrar o recebimento de itens (por exemplo, ordens de compra). Um diário de entrada de itens pode ser criado como parte do gerenciamento de entrada na página **Visão geral da entrada**, ou você pode criar manualmente uma entrada de diário na página **Entrada de item**. Se você habilitar o nome do diário de entrada de itens para verificar os locais de separação, o Finance and Operations irá procurar um local para os itens recebidos e, se houver espaço, gerará destinos de localização para os itens de entrada.

### <a name="production-input"></a>Entrada de produção

Os diários de entrada de produção trabalham como os diários de entrada de itens, mas são usados para ordens de produção.

### <a name="counting"></a>Contando

Os diários de contagem permitem corrigir o estoque disponível registrado para os itens ou grupos de itens e, em seguida, lançar a contagem física atual, de modo que você possa fazer os ajustes necessários para reconciliar as diferenças. Você pode associar políticas de contagem com os grupos de contagem para ajudar os itens do grupo que têm diversas características, de modo que os itens possam ser incluídos em um diário de contagem. Por exemplo, você pode configurar grupos de contagem para itens com uma frequência específica, ou para contar itens quando o estoque ficar em um nível específico. Para obter informações sobre como definir grupos de contagem, consulte [Definir processos de contagem de estoque (Guia de tarefas)](tasks/define-inventory-counting-processes.md).

### <a name="tag-counting"></a>Contagem de etiquetas

Os diários de contagem de etiquetas são usados para atribuir uma etiqueta enumerada a um lote de contagem. A etiqueta deve conter um número de etiqueta, número de item, e quantidade de item. Para ajudar a garantir que a etiqueta seja usada somente uma vez, e que todas as etiquetas sejam usadas, cada número de item deve ter um conjunto exclusivo de etiquetas com sua própria sequência numérica. Três valores de status podem ser definidos para cada etiqueta:

-   **Usado** – O número de item é contado para a etiqueta.
-   **Anulado** – O número de item é anulado para a etiqueta.
-   **Ausente** – O número de item está faltando para a etiqueta.

Quando você lança um diário de contagem de etiquetas, um novo diário de contagem é criado com base nas linhas do diário de contagem de etiquetas. Para obter mais informações sobre a contagem de etiquetas, consulte [Contagem de etiquetas de estoque](inventory-tag-counting.md).

## <a name="working-with-journals"></a>Trabalhando com diários
Um diário só pode ser acessado por um usuário de cada vez. Se vários usuários precisarem acessar os diários simultaneamente para criar linhas de diário, eles deverão selecionar os diários que não estão sendo usados no momento para impedir a substituição de informações. Em situações onde vários departamentos usam o mesmo tipo de diário, é útil criar vários nomes de diário (por exemplo, um por departamento). Também pode ser útil dividir os diários para que todas as rotinas de lançamento sejam inseridas no próprio diário de estoque exclusivo. Para rotinas de lançamento associadas a transações de estoque, crie um diário para ajustes de estoque periódicos e outro para a contagem de estoque.

## <a name="posting-journal-lines"></a>Lançando linhas de diário
Você pode lançar as linhas de diário que você cria a qualquer momento até que você tenha bloqueado um item de transações adicionais. Os dados que você insere em um diário permanecem nele mesmo que ele seja fechado sem lançar as linhas.


---
title: Convenções
description: Este tópico descreve como configurar convenções para estabelecer como os custos devem ser contabilizados na Contabilidade de estoque global.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 97c27006ce95d0cd4551fec209f40328779b435b
ms.sourcegitcommit: 1e5a46271bf7fae2f958d2b1b666a8d2583e04a8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/25/2021
ms.locfileid: "7678582"
---
# <a name="conventions"></a>Convenções

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)] <!--KFM: Until 4/30/2022 -->

Uma convenção é um contêiner para um conjunto de políticas que afetam o comportamento do sistema. Com base nas suas necessidades comerciais, é necessário definir convenções usando uma combinação das diversas políticas que estabelecem como os custos devem ser contabilizados na Contabilidade de estoque global. É possível associar cada convenção a um ou mais razões para garantir a consistência nas políticas contábeis que são aplicadas nos razões.

Para configurar suas convenções, Acesse **Contabilidade de estoque global \> Configurar \> Convenções**. Em cada convenção, defina os seguintes campos:

- **Nome** – Insira o nome da convenção.
- **Descrição** – Insira uma descrição da linha da convenção.
- **Política de objeto de custo** – Selecione uma política de objeto de custo. Essas políticas determinam o nível de granularidade que o sistema aplica para calcular e manter o valor do estoque. As seguintes opções predefinidas estão disponíveis:

    - Produto
    - Produto – Site
    - Produto – Site – Depósito

    Por exemplo, se você selecionar *Produto – Site*, para cada movimentação de estoque (entrada ou saída), o sistema calculará e manterá o custo de estoque de cada produto no nível do site. Portanto, as movimentações de estoque em níveis mais baixos, como o nível do depósito, não afetam o valor do estoque. (Um exemplo de transferência em nível de depósito é uma transferência de itens entre dois depósitos em um único local.) Da mesma forma, não é possível visualizar o custo do estoque em um nível mais baixo, como o nível do depósito.

- **Política de base de medida de entrada** – Selecione uma política de base de medida de entrada. Estas políticas determinam os custos que devem fluir para a conta de estoque e os custos que devem ser cobrados. As seguintes opções são relevantes para as empresas comerciais:

    - **Histórico normal** – Todos os componentes de custo fluem para a conta de estoque.
    - **Padrão** – O custo padrão flui para as contas de estoque, e a diferença entre o custo aplicado e os custos reais é cobrada nas contas de variação. Se você quiser criar uma política de base de medida de entrada *padrão*, será necessário primeiro criar uma lista de preços em que a política pode procurar o custo padrão do item.
    - **Listas de preços** – A Contabilidade de estoque global oferece suporte à obtenção de preços de itens de várias entidades legais. É possível definir uma lista de preços que a política de base de medida de entrada usará. Desta forma, o sistema saberá onde procurar o preço do item. Siga estas etapas para configurar as listas de preços:

        1. No campo **Nome**, insira um nome.
        1. No campo **Descrição**, insira uma descrição.
        1. No campo **Tipo de avaliação de custo**, selecione um tipo de avaliação de custo (*Custo padrão* ou *Custo planejado*).
        1. No campo **Tipo de preço**, selecione um tipo de preço (*Custo*, *Compra* ou *Preço de venda*).
        1. Adicione uma versão de avaliação de custo.
        1. No Painel de ação, selecione **Preço** para validar os preços dos itens na lista de preços.

- **Política de suposição de fluxo de custos** – Selecione uma política de suposição de fluxo de custos. Essas políticas determinam como os custos são removidos do estoque e relatados como o custo dos produtos vendidos. As seguintes opções predefinidas estão disponíveis:

    - Média
    - Específico – Lote

    > [!NOTE]
    > A Contabilidade de estoque global é um sistema de inventário perpétuo. Portanto, o sistema rastreia o valor do estoque em uma base de transação por transação.

- **Política de elementos de custo** – É possível definir políticas de elemento de custo e vinculá-las a este campo. Um *elemento de custo* é o custo de um recurso que é consumido por um evento. É possível usar elementos de custo para rastrear e categorizar custos. Para criar políticas de elemento de custo, insira as informações nos seguintes locais:

    - Campo **Nome**
    - Campo **Descrição**
    - Lista **Elemento de custo**
    - Grade **Regras**

    Se você não quiser dividir ainda mais o valor do estoque, ainda será necessário criar uma lista de elementos de custo que tenha um único elemento de custo. Em seguida, é necessário criar uma política de elemento de custo para mapear todos os tipos de medida relevantes (componentes de custo) para esse elemento de custo.

---
title: "Pré-requisitos para custos padrão"
description: "Esse tópico descreve as etapas básicas para usar custos padrão."
author: AndersGirke
manager: AnnBe
ms.date: 01/17/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventStdCostConv, CostingVersion
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e63f2b4289b640e601492425331ea8f3804d139a
ms.openlocfilehash: 4f505a2de89863d1a12d415795fdfb82b3557bc0
ms.contentlocale: pt-br
ms.lasthandoff: 01/17/2018

---

# <a name="prerequisites-for-standard-costs"></a>Pré-requisitos para custos padrão

[!INCLUDE [banner](../includes/banner.md)]

Esse tópico descreve as etapas básicas para usar custos padrão. As etapas subsequentes dependem das operações da empresa. Por exemplo, as etapas diferem para um ambiente de não fabricação, um ambiente de fabricação que não usa roteiros e um ambiente de fabricação que usa roteiros. 

Para configurar custos padrão, siga estas etapas.

**1. Crie um grupo de modelos de item para custos padrão.**

Use a página **Grupos de modelos de item** para criar um novo grupo para custos padrão e atribuir um modelo de estoque de **Custo padrão**. O identificador para o grupo de modelos de item deve ser significativo, como **Custo padrão**. Marque as caixas de seleção para indicar que o grupo deve permitir estoque financeiro negativo e que deve lançar estoque físico e estoque financeiro. Esse grupo de custo padrão será atribuído aos itens.

**2. Defina contas contábeis relacionadas às variações de custo padrão.** 

Use a página **Plano de contas** para definir contas contábeis relacionadas às variações de custo padrão. Essas contas contábeis devem ser definidas antes que possam ser atribuídas na página **Lançamento**. As contas contábeis podem refletir grupos de itens e de custo.

**3. Atribua contas contábeis aos lançamentos de item relacionados às variações de custo padrão.** 

Use a página **Lançamento** para atribuir as contas contábeis relacionadas às variações de custo padrão. Você pode especificar a conta contábil de uma variação por item (ou grupo de item) e por grupo de custos (ou tipo de grupo de custos) ou especificar que a conta contábil se aplica a todos os itens e grupos de custos. Essas opções correspondem a relações de custo para tabelas, grupos e tudo. 

Antes de definir as regras de lançamento de item, use a página **Combinações de transações** para habilitar relações de custo (para tabelas, grupos e tudo).

**4. Defina parâmetros de estoque relacionados a custos padrão.** 

-  Use a guia **Listas de materiais** na página **Parâmetros de estoque** para definir dois parâmetros de controle de custo relacionados a custos padrão. 

    -  No campo **Divisão de custo**, selecione **Nenhum** ou **Sub-razão**. Se você selecionar **Sub-razão**, a divisão de custo é do tipo *ativa*. Uma divisão de custo ativa é crítica para calcular, reter e exibir segmentações de grupo de custo em uma estrutura de produto de vários níveis para itens de custo padrão. Quando a divisão de custo é ativa, você pode relatar e analisar estoque, trabalho em andamento (WIP) e custo dos produtos vendidos (COGS) por grupo de custos em um formato de nível único, vários níveis ou total. Quando a divisão de custo é ativa, se você ativar o custo de um item fabricado, a segmentação de grupo de custos será armazenada no registro de custo do item. 

    -  Se você selecionar **Nenhum**, a segmentação de grupo de custos não será mantida para itens de custo padrão. Em outras palavras, o custo padrão de um item fabricado será calculado e mantido como um valor único, sem a segmentação de grupo de custos. As contribuições de custo de componentes fabricados serão agregadas ao valor único.

-  No campo **Variações do Padrão**, selecione **Resumido** ou **Por grupo de custos**. Se selecionar **Por grupo de custos**, você poderá identificar variações de preço de compra e variações de produção por grupo de custos. Você também poderá identificar os quatro tipos de variações de produção: o tamanho do lote, a quantidade, o preço e as variações de substituição. Se selecionar **Resumido**, não será possível identificar variações por grupo de custos e você não poderá identificar os quatro tipos de variações de produção. Poderá visualizar somente uma variação de produção resumida.

-  A diretiva sobre variação para padrão funciona independente da diretiva de divisão de custo. Em outras palavras, você pode selecionar uma política de divisão de custo de **Nenhum** e selecionar variações por grupo de custos, de forma que as variações de produção por grupo de custos ainda sejam capturadas.

**5. Crie versões de avaliação de custo para custos padrão.** 

Use a página **Configuração de versão de avaliação de custo** para criar uma ou mais versões de avaliação de custo para custos padrão. Cada versão de avaliação de custo deve ser designada por um tipo de avaliação de custo **Custo padrão** e permitir que o conteúdo inclua dados de custo.

**6. Prepare um cliente existente para usar custos padrão.** 

Os clientes que desejarem alterar os itens existentes para um modelo de estoque de custo padrão devem usar a página **Conversões em custo padrão**.


<a name="related-topics"></a>Tópicos relacionados
--------

[Visão geral de conversão de custo padrão](standard-cost-conversion-overview.md)



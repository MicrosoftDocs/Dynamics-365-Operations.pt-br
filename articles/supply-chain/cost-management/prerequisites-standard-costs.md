---
title: Visão geral de pré-requisitos de custos padrão
description: Esse artigo descreve as etapas básicas para usar custos padrão.
author: JennySong-SH
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventStdCostConv, CostingVersion
audience: Application User
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bf02653b1d1a2cf5ed45f0fc6bd9affe098e7396
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8895776"
---
# <a name="prerequisites-for-standard-costs-overview"></a>Visão geral de pré-requisitos de custos padrão

[!include [banner](../includes/banner.md)]

Esse artigo descreve as etapas básicas para usar custos padrão. As etapas subsequentes dependem das operações da empresa. Por exemplo, as etapas diferem para um ambiente de não fabricação, um ambiente de fabricação que não usa roteiros e um ambiente de fabricação que usa roteiros. 

Para configurar custos padrão, siga estas etapas.

**1. Crie um grupo de modelos de item para custos padrão.**

Use a página **Grupos de modelos de item** para criar um novo grupo para custos padrão e atribuir um modelo de estoque de **Custo padrão**. O identificador para o grupo de modelos de item deve ser significativo, como **Custo padrão**. Marque as caixas de seleção para indicar que o grupo deve permitir estoque financeiro negativo e que deve lançar estoque físico e estoque financeiro. Esse grupo de custo padrão será atribuído aos itens.

**2. Defina contas contábeis relacionadas às variações de custo padrão.** 

Use a página **Plano de contas** para definir contas contábeis relacionadas às variações de custo padrão. Essas contas contábeis devem ser definidas antes que possam ser atribuídas na página **Lançamento**. As contas contábeis podem refletir grupos de itens e de custo.

**3. Atribua contas contábeis aos lançamentos de item relacionados às variações de custo padrão.** 

Use a página **Lançamento** para atribuir as contas contábeis relacionadas às variações de custo padrão. Você pode especificar a conta contábil de uma variação por item (ou grupo de item) e por grupo de custos (ou tipo de grupo de custos) ou especificar que a conta contábil se aplica a todos os itens e grupos de custos. Essas opções correspondem a relações de custo para tabelas, grupos e tudo. 

Antes de definir as regras de lançamento de item, use a página **Combinações de transações** para habilitar relações de custo (para tabelas, grupos e tudo).

**4. Defina parâmetros de estoque relacionados a custos padrão.** 

-  Use a guia **Contabilidade de estoque** na página **Configuração das políticas contábeis de estoque > Parâmetros** para definir dois parâmetros de controle de custo relacionados aos custos padrão.

    -  No campo **Divisão de custo**, selecione **Nenhum** ou **Sub-razão**. Se você selecionar **Sub-razão**, a divisão de custo é do tipo *ativa*. Uma divisão de custo ativa é crítica para calcular, reter e exibir segmentações de grupo de custo em uma estrutura de produto de vários níveis para itens de custo padrão. Quando a divisão de custo é ativa, você pode relatar e analisar estoque, trabalho em andamento (WIP) e custo dos produtos vendidos (COGS) por grupo de custos em um formato de nível único, vários níveis ou total. Quando a divisão de custo é ativa, se você ativar o custo de um item fabricado, a segmentação de grupo de custos será armazenada no registro de custo do item. 

    -  Se você selecionar **Nenhum**, a segmentação de grupo de custos não será mantida para itens de custo padrão. Em outras palavras, o custo padrão de um item fabricado será calculado e mantido como um valor único, sem a segmentação de grupo de custos. As contribuições de custo de componentes fabricados serão agregadas ao valor único.

-  No campo **Variações do Padrão**, selecione **Resumido** ou **Por grupo de custos**. Se selecionar **Por grupo de custos**, você poderá identificar variações de preço de compra e variações de produção por grupo de custos. Você também poderá identificar os quatro tipos de variações de produção: o tamanho do lote, a quantidade, o preço e as variações de substituição. Se selecionar **Resumido**, não será possível identificar variações por grupo de custos e você não poderá identificar os quatro tipos de variações de produção. Poderá visualizar somente uma variação de produção resumida.

-  A diretiva sobre variação para padrão funciona independente da diretiva de divisão de custo. Em outras palavras, você pode selecionar uma política de divisão de custo de **Nenhum** e selecionar variações por grupo de custos, de forma que as variações de produção por grupo de custos ainda sejam capturadas.

**5. Crie versões de avaliação de custo para custos padrão.** 

Use a página **Configuração de versão de avaliação de custo** para criar uma ou mais versões de avaliação de custo para custos padrão. Cada versão de avaliação de custo deve ser designada por um tipo de avaliação de custo **Custo padrão** e permitir que o conteúdo inclua dados de custo.

**6. Prepare um cliente existente para usar custos padrão.** 

Os clientes que desejarem alterar os itens existentes para um modelo de estoque de custo padrão devem usar a página **Conversões em custo padrão**.


## <a name="related-articles"></a>Artigos relacionados

[Visão geral de conversão de custo padrão](standard-cost-conversion-overview.md)

### <a name="blogs"></a>Blogs

#### <a name="community-blogs"></a>Blogs da comunidade

- [Como configurar os custos padrão para materiais diretos no Dynamics 365 for Finance and Operations](https://financefunction.tech/2018/06/07/how-to-set-up-standard-costs-for-direct-materials-in-dynamics-365-for-finance-and-operations)
- [Custos de mão-de-obra diretos padrão no Dynamics 365 for Finance and Operations](https://financefunction.tech/2018/07/16/standard-direct-labor-cost-in-dynamics-365-for-finance-and-operations)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
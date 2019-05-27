---
title: Gerenciar produtos e categorias de produtos de varejo
description: Este tópico descreve como gerentes de mercadoria podem usar categorias de produtos de varejo para gerenciar relacionamentos entre a hierarquia de produtos de varejo e os detalhes de produtos liberados.
author: ashishmsft
manager: AnnBe
ms.date: 10/23/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: ''
ms.assetid: c7ed2ba5-87c6-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-09-01
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 0bcc5989edd9913fce414c0c24068f111d8c1aeb
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1553614"
---
# <a name="manage-retail-product-categories-and-products"></a>Gerenciar produtos e categorias de produtos de varejo

[!include [banner](./includes/banner.md)]

Este tópico descreve um modo avançado de gerenciar categorias de produtos de varejo e produtos no Microsoft Dynamics 365 for Retail. Os aprimoramentos permitem que os gerentes de mercadoria visualizem uma estrutura de propriedades de produtos que é compartilhada entre a hierarquia de produtos de varejo e os detalhes de produtos liberados.

Para saber mais sobre como gerenciar categorias de produtos de varejo, no espaço de trabalho **Gerenciamento de categorias e produtos** , selecione o bloco **Hierarquia de produtos de varejo** .

Observe a estrutura aprimorada da página **Hierarquia de produtos de varejo** que é exibida. Em versões anteriores do Retail, as propriedades de produtos eram divididas em *Propriedades básicas do produto* e *Propriedades de produto de varejo*, com base no escopo de sua aplicabilidade. As propriedades de produto de varejo são *globais* no escopo de aplicabilidade. Em outras palavras, para uma determinada propriedade de produto de varejo, o mesmo valor é compartilhado em todas as entidades legais. Por outro lado, as Propriedades básicas de produto são *específicas da entidade legal*. Em outras palavras, para uma determinada Propriedade básica de produto, o valor pode ser diferente nas entidades legais, dependendo dos requisitos de negócios individuais de cada entidade legal.

Na estrutura avançada de categorias de produto de varejo, as propriedades de produto são separadas de forma lógica com base em sua aplicabilidade em um grupo, para refletir a estrutura do formulário de detalhes do produto liberado.

![Agrupamento de campos baseado no escopo de aplicabilidade das propriedades](media/NoticeGroupingOfFieldsBasedOnTheirScope.PNG)

Você pode alternar entre gerenciar propriedades específicas da entidade legal em todas as entidades legais e gerenciá-las para uma entidade legal específica.

Para gerenciar propriedades em todas as entidades legais, selecione **Exibir todas as entidades legais** (ou **Editar todas as entidades legais**).

![Exibir/Editar todas as entidades legais](media/ToggleBackToEditForSpecificLegalEntity.PNG)

Para gerenciar propriedades de uma entidade legal específica, selecione **Exibir uma entidade legal específica** (ou **Editar uma entidade legal específica**).

![Exibir/Editar uma entidade legal específica](media/ToggleToEditForAllLegalEntities.PNG)

Além disso, na estrutura de categorias de produto de varejo aprimorada, um gerente de mercadorias agora pode definir valores padrão para um conjunto adicional de propriedades de produto no nível da categoria individual. Depois, quando os produtos forem criados, eles herdarão os valores padrão de suas propriedades de produto, com base na associação dessas propriedades a uma categoria individual da hierarquia de produto de varejo. Essas propriedades de produto herdadas também podem ser modificadas para cada produto para atender a requisitos de negócios individuais.

## <a name="selecting-properties-to-update-products-on-the-retail-product-hierarchy-page"></a>Selecionar propriedades para atualizar os produtos na página Hierarquia de produtos de varejo

Você pode usar a nova estrutura aprimorada das propriedades de produtos para selecionar as propriedades de produto que devem ser enviadas aos produtos associados. Na página **Hierarquia de produtos de varejo**, no Painel de Ação, selecione **Categoria** e depois selecione **Atualizar produtos** para abrir a caixa de diálogo **Atualizar produtos** .

![Caixa de diálogo Atualizar produtos](media/NewUpdateProductsEnhancedView.PNG)

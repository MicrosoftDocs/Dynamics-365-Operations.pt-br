---
title: Gerenciamento de categorias de produtos
description: "Este tópico descreve como gerentes de mercadorias podem usar categorias de produtos de varejo para gerenciar relacionamentos entre a hierarquia de produtos de varejo e os detalhes de produtos liberados."
author: ashishmsft
manager: AnnBe
ms.date: 10/23/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 
ms.assetid: c7ed2ba5-87c6-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-09-01
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 25fa39dc81fc721d7593a25a102ce47041ebc5f0
ms.openlocfilehash: 4b7ef962b777a31e1da238a8ec1be9a42ec5bb5f
ms.contentlocale: pt-br
ms.lasthandoff: 03/13/2018

---


# <a name="enhanced-product-and-category-management"></a>Gerenciamento avançado de categorias e produtos

[!include[banner](./includes/banner.md)]

Este tópico descreve um modo avançado de gerenciar categorias de produtos de varejo e produtos no Dynamics 365 for Retail. Esses aprimoramentos permitem que os gerentes de mercadorias visualizem uma estrutura comum de propriedades de produtos entre a hierarquia de produtos de varejo e os detalhes de produtos liberados.

Para saber mais sobre como gerenciar categorias de produtos de varejo, vá para **Hierarquia de produtos de varejo** no espaço de trabalho **Gerenciamento de categorias e produtos** e observe a estrutura avançada da página **Categoria de produto de varejo** .

![Espaço de trabalho de gerenciamento de categorias e produtos](media/LaunchRetailProductHierarchy.png)

Em versões anteriores, as propriedades de produtos eram divididas em **Propriedades básicas do produto** e **Propriedades de produto de varejo**, com base no escopo de sua aplicabilidade. As **Propriedades de produto de varejo** eram *globais* do escopo de aplicabilidade, o que significa que, para uma determinada **Propriedade de produto de varejo**, o mesmo valor é compartilhado em todas as entidades legais. As **Propriedades básicas de produto** são *específicas da entidade legal*. Em outras palavras, para uma determinada **Propriedade básica de produto**, o valor pode ser diferente em entidades legais, com base nos requisitos de negócios individuais.

Na estrutura avançada de categorias de produto de varejo, as propriedades de produto são separadas de forma lógica com base em sua aplicabilidade dentro de um grupo, para refletir a estrutura de formulário de detalhes do produto liberado.

![Agrupamento de campos baseado no escopo de aplicabilidade](media/NoticeGroupingOfFieldsBasedOnTheirScope.PNG)

Você pode alternar entre gerenciar propriedades específicas de entidade legal em todas as entidades legais gerenciá-las para uma entidade legal específica. Para fazer isso, selecione **Exibir/Editar todas as entidades legais** ou **Exibir/Editar uma entidade legal específica**.

![Ativar exibição entre entidades individuais e todas as entidades legais](media/ToggleBackToEditForSpecificLegalEntity.PNG)

![Ativar exibição entre entidades individuais e todas as entidades legais](media/ToggleToEditForAllLegalEntities.PNG)  

Em comparação a versões anteriores, na nova estrutura de categorias de produto de varejo, um gerente de mercadorias também pode definir valores padrão para um conjunto adicional de propriedades de produto a nível de categoria individual. No momento da criação do produto, os valores de propriedades padrão de produto são herdados por um produto, com base em sua associação a uma categoria individual da hierarquia de produto de varejo. Essas propriedades de produto herdadas também podem ser modificadas para cada produto para atender a requisitos de negócios individuais.

## <a name="select-properties-to-update-products-from-the-retail-product-category-form"></a>Selecionar propriedades para atualizar os produtos do formulário Categoria de produto de varejo 
 
Você pode usar essa nova estrutura avançada para que as propriedades de produtos selecionem quais propriedades de produto devem ser enviadas a produtos associados. 

![Nova exibição avançada de produtos para atualização](media/NewUpdateProductsEnhancedView.PNG) 

Os gerentes de mercadoria podem alterar essas propriedades herdadas de produto para cada produto, para atender a requisitos de negócios individuais.



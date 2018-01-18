---
title: "Gerenciamento e criação de categorias de produtos"
description: "Este tópico descreve os aprimoramentos feitos em relação à experiência de gerenciamento para categorias de produtos de varejo. Esses aprimoramentos permitem que os gerentes de mercadoria tenham uma correlação entre a hierarquia de produtos de varejo e os detalhes do produto liberado."
author: ashishmsft
manager: AnnBe
ms.date: 09/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
ms.search.form: RetailCategoryAndProductWorkspace, RetailCategory
audience: Application User
ms.search.scope: Core, Retail
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2017-09-01
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 98250062892e0c5f665616dc3944181a3ff8599a
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="product-category-management-and-creation"></a>Gerenciamento e criação de categorias de produtos

[!include[banner](./includes/banner.md)]

Os aprimoramentos feitos em relação à experiência de gerenciamento para categorias de produto de varejo permitem que os gerentes de mercadoria tenham uma correlação entre a hierarquia de produtos de varejo e os detalhes do produto liberado. Para exibir esses aprimoramentos, no espaço de trabalho **Gerenciamento de categorias e produtos** , selecione **Hierarquia de produtos de varejo** para abrir a página **Nova estrutura de categoria de produtos de varejo** . 

Em versões anteriores, as propriedades de produtos eram divididas em Propriedades básicas do produto e Propriedades de produto de varejo, com base no escopo de sua aplicabilidade. As propriedades de produto de varejo eram *globais*. Em outras palavras, para uma determinada propriedade do produto, o mesmo valor é compartilhado em todas as entidades legais. As propriedades básicas do produto eram *específicas da entidade legal*. Em outras palavras, uma determinada propriedade do produto pode diferir nas entidades legais, com base nos requisitos de negócios individuais.

Com esses aprimoramentos, para propriedades do produto na categoria de varejo do produto, continuamos a separar os campos com base em sua aplicabilidade dentro de um grupo, para refletir a estrutura de formulário de detalhes do produto liberado.

Você pode alternar entre gerenciar propriedades específicas de entidade legal em todas as entidades legais gerenciá-las para uma entidade legal específica. Selecione **Exibir/Editar todas as entidades legais** ou **Exibir/Editar uma entidade legal específica**, conforme necessário.

Os gerentes de mercadoria também podem definir valores padrão para um conjunto de propriedades adicionais de produto em nível de uma categoria individual. Esses valores de propriedade são herdados por um produto, com base em sua associação a uma categoria no momento da criação do produto.

## <a name="select-properties-to-update-products-from-the-retail-product-category-form"></a>Selecionar propriedades para atualizar os produtos do formulário Categoria de produto de varejo

Você pode usar propriedades lógicas de agrupamento para selecionar quais propriedades atualizadas do produto devem ser enviadas por push para os produtos associados.

Os gerentes de mercadoria podem alterar essas propriedades herdadas de produto para cada produto, para atender a requisitos de negócios individuais.


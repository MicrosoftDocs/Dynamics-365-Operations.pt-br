---
title: Hierarquias do Commerce
description: Este artigo descreve as hierarquias no Dynamics 365 Commerce.
author: josaw1
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.custom: 15851
ms.assetid: dfa11d41-2a0c-4cde-99b6-058c49176c94
ms.search.industry: Retail
ms.search.form: OMHierarchyManager, EcoResCategoryHierarchyFactbox
ms.openlocfilehash: ce196acc8c4bced865b983b12d72f8bc6e4d02a0
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9271868"
---
# <a name="commerce-hierarchies"></a>Hierarquias do Commerce

[!include [banner](includes/banner.md)]

Este artigo descreve as hierarquias no Dynamics 365 Commerce.

É possível criar uma hierarquia de categoria para organizar os produtos vendidos por meio dos seus canais. Você pode usar as hierarquias de produtos para categorizar ou agrupar produtos. Esses produtos podem ser usados para criar sortimentos de produtos e programas de fidelidade do cliente. Também é possível designar atributos e propriedades de produtos, atribuir uma estrutura de preços, incluir os produtos em promoções de produtos, e usar os produtos em relatórios. Você pode criar uma hierarquia de categoria para representar todos os produtos e categorias em sua organização, e depois usar essa hierarquia de categoria para várias finalidades. Como alternativa, é possível criar várias hierarquias de categoria para finalidades especiais, como promoções de produtos. Quando você cria uma hierarquia de produtos, é preciso atribuir um tipo de hierarquia de categoria para identificar a finalidade da hierarquia de categoria. Por exemplo, somente as hierarquias do produto que são atribuídas ao tipo **Hierarquia de navegação comercial** são mencionadas quando você procura produtos por categoria online ou no ponto de venda (PDV).

## <a name="hierarchy-types"></a>Tipos de hierarquia

A tabela a seguir lista os tipos de hierarquias de categoria disponíveis e a finalidade geral de cada tipo.

| Tipo de hierarquia de categoria       | Finalidade |
|-------------------------------|---------|
| Hierarquia de produtos      | Use esse tipo da hierarquia para definir a hierarquia de produtos geral da sua organização. Você pode usar esse tipo da hierarquia para comercialização, preços e promoções, relatórios e planejamento de classificação. Apenas uma hierarquia de produtos pode ser atribuída esse tipo de hierarquia. |
| Hierarquia complementar | Use esse tipo de hierarquia para qualquer hierarquia de categoria adicional que você deseja criar. Por exemplo, na primavera, você tem uma promoção para moda praia. Portanto, você inclui os produtos de moda praia em uma hierarquia de categoria separada e aplica o preço promocional a várias categorias de produto. |
| Hierarquia de navegação   | Use este tipo da hierarquia para agrupar e organizar produtos em categorias, de forma que seja possível procurar os produtos online ou no PDV. |

Ao usar uma hierarquia de categoria para estruturar seus produtos, você pode configurar e manter atributos e propriedades de produtos no nível de categoria. Esses atributos e propriedades incluem as configurações para dimensões do produto e do PDV. Todos os produtos que você atribui às categorias herdam automaticamente os atributos e as propriedades que você define. Você também pode copiar as configurações de propriedade de qualquer produto para vários produtos da categoria selecionada ao mesmo tempo.


[!INCLUDE[footer-include](../includes/footer-banner.md)]

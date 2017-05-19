---
title: Hierarquias de varejo
description: Este artigo descreve as hierarquias de varejo no Microsoft Dynamics AX.
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 15851
ms.assetid: dfa11d41-2a0c-4cde-99b6-058c49176c94
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 6b1f91f863c8da35362ebb3036e76aa10d95ba65
ms.openlocfilehash: 4dc4fdfa8abf65ba13f5c94042a8eb28a3d7c046
ms.contentlocale: pt-br
ms.lasthandoff: 04/26/2017


---

# <a name="retail-hierarchies"></a>Hierarquias de varejo

[!include[banner](includes/banner.md)]


Este artigo descreve as hierarquias de varejo no Microsoft Dynamics AX.

Você pode criar uma hierarquia de categoria de varejo para organizar os produtos vendidos por meio dos canais de varejo. As hierarquias de produtos de varejo podem ser usadas para categorizar ou agrupar produtos. Esses produtos podem ser usados para criar sortimentos de produtos e programas de fidelidade do cliente. Também é possível designar atributos e propriedades de produtos, atribuir uma estrutura de preços, incluir os produtos em promoções de produtos, e usar os produtos em relatórios. Você pode criar uma hierarquia de categoria de varejo para representar todos os produtos e categorias em sua organização, e depois usar essa hierarquia de categoria para várias finalidades. Como alternativa, você pode criar várias hierarquias de categoria de varejo para finalidades especiais, como promoções de produtos. Quando você cria uma hierarquia de produtos de varejo, é preciso atribuir um tipo de hierarquia de categoria para identificar a finalidade da hierarquia de categoria. Por exemplo, somente as hierarquias do produto que são atribuídas ao tipo de **Hierarquia de navegação de varejo** são mencionadas quando você procura produtos por categoria on-line ou no ponto de venda (PDV).

## <a name="retail-hierarchy-types"></a>Tipos de hierarquia de varejo
A tabela a seguir lista os tipos de hierarquias de categoria de varejo disponíveis e a finalidade geral de cada tipo.

| Tipo de hierarquia de categoria       | Finalidade                                                                                                                                                                                                                                                                                                            |
|-------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Hierarquia de produtos de varejo      | Use esse tipo da hierarquia para definir a hierarquia de produtos geral da sua organização. Você pode usar esse tipo da hierarquia para comercialização, preços e promoções, relatórios e planejamento de classificação. Apenas uma hierarquia de produtos de varejo pode ser atribuída esse tipo da hierarquia.                                       |
| Hierarquia de varejo complementar | Use esse tipo da hierarquia para qualquer hierarquia de categoria de varejo adicional que você deseja criar. Por exemplo, na primavera, você tem uma promoção para moda praia. Portanto, você inclui os produtos de moda praia em uma hierarquia de categoria separada e aplica o preço promocional a várias categorias de produto. |
| Hierarquia de navegação de varejo   | Use este tipo da hierarquia para agrupar e organizar produtos em categorias, de forma que seja possível procurar os produtos online ou no PDV.                                                                                                                                                                                       |

Usando uma hierarquia de categoria de varejo para estruturar seus produtos, você pode configurar e manter atributos e propriedades de produtos no nível de categoria. Esses atributos e propriedades incluem as configurações para dimensões do produto e do PDV. Todos os produtos que você atribui às categorias herdam automaticamente os atributos e as propriedades que você define. Você também pode copiar as configurações de propriedade de qualquer produto para vários produtos da categoria selecionada ao mesmo tempo.





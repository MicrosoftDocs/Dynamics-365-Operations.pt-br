---
title: Hierarquias de varejo
description: Este artigo descreve as hierarquias de varejo no Microsoft Dynamics 365 para Varejo.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15851
ms.assetid: dfa11d41-2a0c-4cde-99b6-058c49176c94
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 817696566473bc5f31a7ff11c04291351dfd4764
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="retail-hierarchies"></a>Hierarquias de varejo

[!include[banner](includes/banner.md)]


Este artigo descreve as hierarquias de varejo no Microsoft Dynamics 365 para Varejo.

Você pode criar uma hierarquia de categoria de varejo para organizar os produtos vendidos por meio dos canais de varejo. As hierarquias de produtos de varejo podem ser usadas para categorizar ou agrupar produtos. Esses produtos podem ser usados para criar sortimentos de produtos e programas de fidelidade do cliente. Também é possível designar atributos e propriedades de produtos, atribuir uma estrutura de preços, incluir os produtos em promoções de produtos, e usar os produtos em relatórios. Você pode criar uma hierarquia de categoria de varejo para representar todos os produtos e categorias em sua organização, e depois usar essa hierarquia de categoria para várias finalidades. Como alternativa, você pode criar várias hierarquias de categoria de varejo para finalidades especiais, como promoções de produtos. Quando você cria uma hierarquia de produtos de varejo, é preciso atribuir um tipo de hierarquia de categoria para identificar a finalidade da hierarquia de categoria. Por exemplo, somente as hierarquias do produto que são atribuídas ao tipo de **Hierarquia de navegação de varejo** são mencionadas quando você procura produtos por categoria on-line ou no ponto de venda (PDV).

## <a name="retail-hierarchy-types"></a>Tipos de hierarquia de varejo
A tabela a seguir lista os tipos de hierarquias de categoria de varejo disponíveis e a finalidade geral de cada tipo.

| Tipo de hierarquia de categoria       | Finalidade                                                                                                                                                                                                                                                                                                            |
|-------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Hierarquia de produtos de varejo      | Use esse tipo da hierarquia para definir a hierarquia de produtos geral da sua organização. Você pode usar esse tipo da hierarquia para comercialização, preços e promoções, relatórios e planejamento de classificação. Apenas uma hierarquia de produtos de varejo pode ser atribuída esse tipo da hierarquia.                                       |
| Hierarquia de varejo complementar | Use esse tipo da hierarquia para qualquer hierarquia de categoria de varejo adicional que você deseja criar. Por exemplo, na primavera, você tem uma promoção para moda praia. Portanto, você inclui os produtos de moda praia em uma hierarquia de categoria separada e aplica o preço promocional a várias categorias de produto. |
| Hierarquia de navegação de varejo   | Use este tipo da hierarquia para agrupar e organizar produtos em categorias, de forma que seja possível procurar os produtos online ou no PDV.                                                                                                                                                                                       |

Usando uma hierarquia de categoria de varejo para estruturar seus produtos, você pode configurar e manter atributos e propriedades de produtos no nível de categoria. Esses atributos e propriedades incluem as configurações para dimensões do produto e do PDV. Todos os produtos que você atribui às categorias herdam automaticamente os atributos e as propriedades que você define. Você também pode copiar as configurações de propriedade de qualquer produto para vários produtos da categoria selecionada ao mesmo tempo.





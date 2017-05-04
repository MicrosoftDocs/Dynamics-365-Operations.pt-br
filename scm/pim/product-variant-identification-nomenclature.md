---
title: "Nomenclatura de número de produto"
description: "Este tópico descreve como você pode configurar uma nomenclatura de número de produto para substituir o formato fixo, [Número de produto mestre - Configuração - Tamanho - Cor - Estilo], com um formato segmentado que inclui o número de produto mestre, dimensões de produto ativas e delimitadores de texto de sua preferência. Você também pode criar uma nomenclatura para identificar configurações criadas pelo configurador de produto baseado em restrições. Essas nomenclaturas podem conter os atributos de sua preferência."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: EcoResNomenclature, EcoResProductDimensionGroup, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelDetails
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 220104
ms.assetid: 31c9efb4-b5f6-4af3-b884-8f1e128469bd
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 58afcd62e7ef317e624fd26d198c2606bf53e6a5
ms.lasthandoff: 03/31/2017


---

# <a name="product-number-nomenclature"></a>Nomenclatura de número de produto

[!include[banner](../includes/banner.md)]


Este tópico descreve como você pode configurar uma nomenclatura de número de produto para substituir o formato fixo, [Número de produto mestre - Configuração - Tamanho - Cor - Estilo], com um formato segmentado que inclui o número de produto mestre, dimensões de produto ativas e delimitadores de texto de sua preferência. Você também pode criar uma nomenclatura para identificar configurações criadas pelo configurador de produto baseado em restrições. Essas nomenclaturas podem conter os atributos de sua preferência.

A nova nomenclatura de número de grade de produto permite que incluir segmentos em seus identificadores de grade de produto. Esses segmentos podem incluir o número de produto mestre, dimensões de produto, sequências numéricas, constantes de texto e atributos. Tal funcionalidade permite que você encontre rapidamente uma grade de produto específica ao criar uma ordem de venda ou de compra.

## <a name="nomenclature-of-predefined-product-variants"></a>Nomenclatura de grades de produto predefinidas
As grades de produto são geradas para produtos mestres de acordo com uma das três tecnologias de configuração:

-   Grades predefinidas
-   Baseadas em restrições
-   Baseadas em dimensões

Cada grade de produto tem um número, e a nomenclatura de identificação para grade de produto permite que você selecione os segmentos que serão incluídos no número de cada grade de produto. Você pode selecionar os seguintes segmentos na página **Nomenclatura de produto**.

-   Número do produto mestre
-   Valor de sequência numérica
-   Constante de texto
-   Dimensões do produto
    -   Configuração
    -   Cor
    -   Tamanho
    -   Estilo

Após a nomenclatura de identificação para grade de produto ser definida, ela pode ser associada a um grupo de dimensão de produto. Por conseguinte, a todos os produtos mestres referentes a esse grupo de dimensão de produto serão atribuídos números de grade de produto de acordo com a nomenclatura. Também é possível atribuir uma nomenclatura de identificação para grade de produto diretamente a um produto mestre, caso no qual às grades de produto pertencentes a esse mestre serão atribuídos números de produto de acordo com a nomenclatura.

### <a name="example"></a>Exemplo

Uma camiseta (TS1234) é produzida em 3 diferentes tamanhos (P, M, G), 4 cores diferentes (vermelho, verde, azul, amarelo) e 2 estilos (polo, V), resultando em um total de 24 grades de produto possíveis. Uma nomenclatura de identificação para grade de produto é criada com os seguintes segmentos:

1.  Número do produto mestre
2.  Constante de texto: '-'
3.  Cor
4.  Constante de texto: '-'
5.  Tamanho
6.  Constante de texto: '-'
7.  Estilo

O número da grade de produto para vermelho, pequeno, polo será: TS1234-Red-Small-Polo

## <a name="nomenclature-of-constraintbased-configurations"></a>Nomenclatura de configurações baseadas em restrições
Em configurações baseadas em restrições, uma nomenclatura dedicada pode ser criada para a dimensão de configuração de produto. Você pode selecionar os seguintes segmentos na página **Nomenclatura de produto**.

-   Valor de sequência numérica
-   Constante de texto
-   Valor do atributo 

Cada componente em um modelo de configuração de produto pode ter sua própria nomenclatura de configuração. Apenas atributos pertencentes ao componente podem ser usados. Atributos de subcomponentes ou requisitos de usuário não estão disponíveis.

### <a name="example"></a>Exemplo

Um modelo de configuração de produto tem um componente raiz com dois atributos.

-   Material (plástico, madeira, aço)
-   Tamanho (10...100)

Uma nomenclatura de configuração é definida por meio dos seguintes segmentos:

1.  Valor do atributo: material
2.  Constante de texto: 'AAA'
3.  Valor do atributo: tamanho

A ID de configuração para o material de madeira com um tamanho de 78 terá a seguinte ID de configuração: WoodAAA78.

## <a name="nomenclature-of-dimensionbased-configurations"></a>Nomenclatura de configurações baseadas em dimensões
Em configurações baseadas em dimensão, uma nomenclatura dedicada pode ser criada para a dimensão de configuração de produto. Você pode selecionar os seguintes segmentos na página **Nomenclatura de produto**.

-   Valor de sequência numérica
-   Constante de texto
-   Item de grupo de configuração

Uma nomenclatura de configuração pode ser definida para uma lista de materiais (BOM).

### <a name="example"></a>Exemplo

Uma lista de materiais tem 4 linhas de BOM divididas em 2 grupos de configuração.

-   Linha de BOM: M0007, gabinete padrão
    -   Grupo de configuração: gabinete
-   Linha de BOM: M0008, gabinete avançado
    -   Grupo de configuração: gabinete
-   Linha de BOM: M0021, tecido de grade frontal
    -   Grupo de configuração: grade frontal
-   Linha de BOM: M0022, metal de grade frontal
    -   Grupo de configuração: grade frontal

Uma nomenclatura de configuração é definida por meio dos seguintes segmentos:

1.  Grupo de configuração: gabinete
2.  Constante de texto: '&'
3.  Grupo de configuração: grade frontal

A ID de configuração para um gabinete padrão com grade frontal de tecido será: M0007&M0021.

## <a name="nomenclature-of-a-combination-of-product-variants-and-configurations"></a>Nomenclatura de uma combinação de grades de produto e configurações
Quando você usa uma tecnologia baseada em restrições ou dimensão para configurar grades de produto de um produto mestre, as grades de produto podem receber números de grade de produto que incluem a nomenclatura da dimensão de configuração. Siga as seguintes etapas para configurar as grades:

1.  Defina uma nomenclatura de número de grade de produto que inclua a dimensão da configuração na página **Nomenclatura de produto**.
2.  Atribua essa nomenclatura a um grupo de dimensão de produtos com a dimensão de configuração.
3.  Defina uma nomenclatura de configuração para os componentes ou BOMs que serão usados para configurar as grades de produto.

### <a name="example-for-constraint-based-configurations"></a>Exemplo de configurações baseadas em restrições

Neste exemplo, você pode usar uma nomenclatura de número de grade de produto que consiste nos seguintes segmentos:

1.  Número do produto mestre
2.  Constante de texto '\_'
3.  Configuração

A nomenclatura de configuração pode consistir nos seguintes segmentos:

1.  Valor do atributo: material
2.  Constante de texto: 'AAA'
3.  Valor do atributo: tamanho

É possível inserir os seguintes valores para segmentos:

-   Número do produto mestre = M0099
-   Material = plástico
-   Extensão = 12

O número de grade de produto será: M0099\_PlasticAAA12.

### <a name="example-for-dimension-based-configurations"></a>Exemplo de configurações baseadas em dimensões

Neste exemplo, você pode usar uma nomenclatura de número de grade de produto que consiste nos seguintes segmentos:

1.  Número do produto mestre
2.  Constante de texto: '//'
3.  Configuração

A nomenclatura de configuração pode consistir nos seguintes segmentos:

1.  Grupo de configuração: gabinete
2.  Constante de texto: '&'
3.  Grupo de configuração: grade frontal

É possível inserir os seguintes valores para segmentos:

-   Número do produto mestre = D0123
-   Gabinete = M0008
-   Grade frontal = M0022

O número de grade de produto será: D0123//M0008&M0022.

## <a name="numbering-conflicts"></a>Conflitos de numeração
É possível configurar uma nomenclatura de número de grade de produto que não resulta em números de grade de produto exclusivos. Por exemplo, isso poderia ocorrer se uma dimensão de produto ativa não fosse incluída na nomenclatura para um produto mestre que usa a tecnologia de configuração de variante predefinida. Conflitos são tratados de forma diferente pelas diferentes tecnologias de configuração.

### <a name="predefined-variants"></a>Grades predefinidas

Um erro ocorrerá se você tentar gerar manual ou automaticamente grades de produto quando uma ou mais delas acabarem com o mesmo número de grade de produto. Para evitar isso, você deve usar todas as dimensões de produto ativas no grupo de dimensão de produto ou incluir uma sequência numérica para garantir que os números de grade de produto sejam exclusivos.

### <a name="constraint-based-configurations"></a>Configurações baseadas em restrições

Dependendo da nomenclatura, o sistema pode tentar atribuir um número de grade de produto não exclusivo a uma configuração. Nesse caso, o sistema usará, em vez disso, a sequência numérica para a dimensão de configuração como o número de grade de produto. Se isso ocorrer, você receberá um aviso. Para evitar isso, você deve incluir uma quantidade suficiente de atributos na nomenclatura para garantir exclusividade e fazer com a opção **Reutilizar** seja habilitada para o componente.

### <a name="dimension-based-configurations"></a>Configurações baseadas em dimensões

O processo de configuração inclui uma etapa na qual o sistema sugerirá um valor de configuração de acordo com a nomenclatura. Nessa etapa, você alterará manualmente o valor da configuração. Ao salvar a configuração, o sistema verificará se o valor da configuração é exclusivo. Se esse não for o caso, um erro será exibido. Você deve inserir um valor de configuração exclusivo para salvar a configuração.



<a name="see-also"></a>Consulte também
--------

[Criar uma nomenclatura de número de produto para grades de produto predefinidas (guia de tarefas)](http://ax.help.dynamics.com/en/wiki/create-a-product-number-nomenclature-for-predefined-product-variants/)

[Criar uma nomenclatura de número de produto para grades de produto configuradas (guia de tarefas)](http://ax.help.dynamics.com/en/wiki/create-a-product-number-nomenclature-for-configured-product-variants/)





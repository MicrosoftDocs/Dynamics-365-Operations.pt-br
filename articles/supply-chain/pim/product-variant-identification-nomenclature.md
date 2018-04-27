---
title: "Nomenclatura de números e de nomes de grade de produto"
description: "Este tópico descreve como você pode configurar uma nomenclatura de número de produto para substituir o formato fixo [Número do produto mestre - Configuração - Tamanho - Cor - Estilo]."
author: roxanadiaconu
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResNomenclature, EcoResProductDimensionGroup, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 220104
ms.assetid: 3fe69fb7-5c32-423c-98a8-2f53186cda68
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 72d4ff5e1311005d3bf43a13e28208cd9b3d1457
ms.openlocfilehash: 6a620f2a0105d578d419d3aac816c7d78fbf3e46
ms.contentlocale: pt-br
ms.lasthandoff: 03/08/2018

---

# <a name="nomenclature-of-product-variant-numbers-and-names"></a>Nomenclatura de números e de nomes de grade de produto

[!INCLUDE [banner](../includes/banner.md)]

Este tópico descreve como você pode configurar uma nomenclatura de número de produto para substituir o formato fixo [Número do produto mestre - Configuração - Tamanho - Cor - Estilo]. A nova nomenclatura tem um formato de destino que inclui o número do produto mestre, as dimensões ativas do produto e os delimitadores de texto de sua escolha. Você também pode criar uma nomenclatura para os nomes de produto. Por fim, você pode criar uma nomenclatura para identificar configurações criadas pelo configurador de produto baseado em restrições. Essas nomenclaturas podem conter os atributos de sua preferência.

As novas nomenclaturas para números de grade de produto e nomes de grade de produto permitem incluir segmentos nos identificadores de grades de produto. Esses segmentos podem incluir o número e o nome do produto mestre, as IDs os nomes de dimensão de produto, as sequências numéricas, as constantes de texto e os atributos. Tal funcionalidade permite que você encontre rapidamente uma grade de produto específica ao criar uma ordem de venda ou de compra. Você cria nomenclaturas para números e nomes de grade de produto usando a página **Nomenclatura de produtos**. Para abrir essa página, clique em **Gerenciamento de informações do produto** &gt; **Configuração**.

## <a name="nomenclature-of-predefined-product-variants"></a>Nomenclatura de grades de produto predefinidas
As grades de produto são geradas para produtos mestres de acordo com uma das três tecnologias de configuração:

-   Grades predefinidas
-   Baseadas em restrições
-   Baseadas em dimensões

Cada grade de produto tem um número e um nome, e as nomenclaturas de identificação para grade de produto permitem que você selecione os segmentos que serão incluídos no número de cada grade de produto. Você pode selecionar os seguintes segmentos na página **Nomenclatura de produtos**:

-   Número do produto mestre
-   Nome do produto mestre
-   Valor de sequência numérica
-   Constante de texto
-   Dimensões do produto
    -   ID ou nome da configuração
    -   ID ou nome da cor
    -   ID ou nome do tamanho
    -   ID ou nome do estilo

Depois de definir uma nomenclatura de número de identificação de grade de produto, será possível associá-la a um grupo de dimensões do produto. Todos os produtos mestres que fizerem referência a esse grupo de dimensões de produto receberão números de grade de produto de acordo com a nomenclatura. Contudo, as nomenclaturas de nome de grade de produto não podem ser associadas a grupos de dimensões do produto. Você também pode atribuir uma identificação de grade de produto diretamente a um produto mestre. Nesse caso, as grades do produto que pertencem ao produto mestre receberão números e nomes de grade de produto de acordo com as nomenclaturas.

### <a name="example"></a>Exemplo

Uma camiseta (TS1234) é produzida em três tamanhos (P, M, G), quatro cores (Vermelho, Verde, Azul, Amarelo) e dois estilos (Polo, Gola em V). Portanto, 24 grades de produto são possíveis (= 3 × 4 × 2). Você cria uma nomenclatura de número de grade de produto com os seguintes segmentos:

1.  Número do produto mestre
2.  Constante de texto: "-"
3.  Cor
4.  Constante de texto: "-"
5.  Tamanho
6.  Constante de texto: "-"
7.  Estilo

Nesse caso, o número da grade de produto para uma camiseta polo vermelha pequena será TS1234-Vermelho-Pequena-Polo

## <a name="nomenclature-of-constraint-based-configurations"></a>Nomenclatura de configurações baseadas em restrições
Em configurações baseadas em restrições, você pode criar uma nomenclatura dedicada para a dimensão de configuração de produto. Você pode selecionar os seguintes segmentos na página **Nomenclatura de produtos**:

-   Valor de sequência numérica
-   Constante de texto
-   Valor do atributo

Cada componente em um modelo de configuração de produto pode ter sua própria nomenclatura de configuração. Apenas os atributos que pertencem ao componente podem ser usados. Os atributos de subcomponentes ou os requisitos de usuário não podem ser usados.

### <a name="example"></a>Exemplo

Um modelo de configuração de produto tem um componente raiz com dois atributos:

-   Material (plástico, madeira, aço)
-   Tamanho (10...100)

Você cria uma nomenclatura de configuração com os seguintes segmentos:

1.  Valor do atributo: material
2.  Constante de texto: "AAA"
3.  Valor do atributo: tamanho

Nesse caso, a ID de configuração do material de madeira com um comprimento 78 será MadeiraAAA78.

## <a name="nomenclature-of-dimension-based-configurations"></a>Nomenclatura de configurações baseadas em dimensões
Em configurações baseadas em dimensões, você pode criar uma nomenclatura dedicada para a dimensão de configuração de produto. Você pode selecionar os seguintes segmentos na página **Nomenclatura de produtos**:

-   Valor de sequência numérica
-   Constante de texto
-   Item de grupo de configuração

Você pode definir uma nomenclatura de configuração para uma lista de materiais (BOM).

### <a name="example"></a>Exemplo

Uma BOM tem quatro linhas de BOM divididas em dois grupos de configuração:

-   Linha de BOM: M0007, gabinete padrão
    -   Grupo de configuração: gabinete
-   Linha de BOM: M0008, gabinete avançado
    -   Grupo de configuração: gabinete
-   Linha de BOM: M0021, tecido de grade frontal
    -   Grupo de configuração: grade frontal
-   Linha de BOM: M0022, metal de grade frontal
    -   Grupo de configuração: grade frontal

Você cria uma nomenclatura de configuração com os seguintes segmentos:

1.  Grupo de configuração: gabinete
2.  Constante de texto: "&"
3.  Grupo de configuração: grade frontal

Nesse caso, a ID de configuração para um gabinete padrão com grade frontal de tecido será: M0007&M0021.

## <a name="nomenclature-for-a-combination-of-product-variants-and-configurations"></a>Nomenclatura para uma combinação de grades de produto e configurações
Quando você usa a tecnologia de configuração baseada em restrição ou a tecnologia de configuração baseada em dimensão para configurar grades de produto para um produto mestre, os números das grades de produto podem incluir a nomenclatura da dimensão de configuração. Siga estas etapas para configurar as variantes.

1.  Na página **Nomenclatura de produtos**, defina uma nomenclatura de número de grade de produto que inclua a dimensão de configuração.
2.  Atribua a nomenclatura a um grupo de dimensões de produto com a dimensão de configuração.
3.  Defina uma nomenclatura de configuração para os componentes ou BOMs que serão usados para configurar as grades de produto.

Você também pode criar nomenclaturas para os nomes de grade de produto. Os nomes de grade de produto podem ser configurados para incluir a ID ou o nome da configuração.

### <a name="example-for-constraint-based-configurations"></a>Exemplo de configurações baseadas em restrições

Neste exemplo, use uma nomenclatura de número de grade de produto que consista nestes segmentos:

1.  Número do produto mestre
2.  Constante de texto "\_"
3.  Configuração

A nomenclatura de configuração consiste nestes segmentos:

1.  Valor do atributo: material
2.  Constante de texto: "AAA"
3.  Valor do atributo: tamanho

É possível inserir os seguintes valores para segmentos:

-   Número do produto mestre = **M0099**
-   Material = **Plástico**
-   Comprimento = **12**

Nesse caso, o número da grade de produto será M0099\_PlásticoAAA12.

### <a name="example-for-dimension-based-configurations"></a>Exemplo de configurações baseadas em dimensões

Neste exemplo, use uma nomenclatura de número de grade de produto que consista nestes segmentos:

1.  Número do produto mestre
2.  Constante de texto "//"
3.  Configuração

A nomenclatura de configuração consiste nestes segmentos:

1.  Grupo de configuração: gabinete
2.  Constante de texto: "&"
3.  Grupo de configuração: grade frontal

É possível inserir os seguintes valores para segmentos:

-   Número do produto mestre = **D0123**
-   Gabinete = **M0008**
-   Grade frontal = **M0022**

Nesse caso, o número da grade de produto será D0123//M0008&M0022.

## <a name="numbering-conflicts"></a>Conflitos de numeração
Em alguns casos, uma nomenclatura de número de grade de produto configurada pode não produzir números de grade de produto exclusivos. Por exemplo, os número de grade de produto não serão exclusivos se uma dimensão de produto ativa não for incluída na nomenclatura para um produto mestre que use a tecnologia de configuração de grade predefinida. A forma como você lida com os conflitos varia, dependendo da tecnologia de configuração.

### <a name="predefined-variants"></a>Grades predefinidas

Ocorrerá um erro se você tentar criar manualmente ou gerar de forma automática as grades de produto, e mais de uma grade de produto terminará com o mesmo número de grade de produto. Para evitar esse cenário, sempre utilize todas as dimensões de produto ativas no grupo de dimensões de produto. Como alternativa, inclua uma sequência numérica para ajudar a garantir que os números de grade de produto sejam exclusivos.

### <a name="constraint-based-configurations"></a>Configurações baseadas em restrições

Dependendo da nomenclatura, o sistema poderá tentar atribuir um número de grade de produto não exclusivo a uma configuração. Nesse caso, o sistema usa a sequência numérica para a dimensão de configuração como o número de grade de produto e você recebe um aviso. Para evitar esse cenário, inclua atributos suficientes na nomenclatura para ajudar a garantir o uso de números de variante de produto exclusivos. Você também deve garantir que a opção **Reutilizar** esteja ativada para o componente.

### <a name="dimension-based-configurations"></a>Configurações baseadas em dimensões

Durante uma etapa do processo de configuração, o sistema sugere um valor de configuração de acordo com a nomenclatura. Nessa etapa, você alterará manualmente o valor da configuração. Quando você salva a configuração, o sistema verifica se o valor da configuração é exclusivo. Se o valor inserido não for exclusivo, você receberá uma mensagem de erro. Para salvar a configuração, insira um valor de configuração exclusivo.

<a name="see-also"></a>Consulte também
--------

[Criar uma nomenclatura de número de produto para grades de produto predefinidas](tasks/create-product-number-nomenclature-predefined-variants-2016-11.md)

[Criar uma nomenclatura de número de produto para grades de produto configuradas](tasks/create-product-number-nomenclature-product-variants_2016_11.md)



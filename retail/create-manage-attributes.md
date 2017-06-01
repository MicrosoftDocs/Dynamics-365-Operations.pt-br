---
title: Criar e gerenciar atributos.
description: "Este artigo descreve atributos no Microsoft Dynamics 365 for Operations. Os atributos permitem descrever um produto e suas características em campos definidos pelo usuário."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 16461
ms.assetid: 2b85491c-f830-4e79-a2cb-681b7ced6988
ms.search.region: global
ms.search.industry: Retail
ms.author: prabhup
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: eaee0edb4822a386c8781d9929999cea326f0a40
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="create-and-manage-attributes"></a>Criar e gerenciar atributos.

[!include[banner](includes/banner.md)]


Este artigo descreve atributos no Microsoft Dynamics 365 for Operations. Os atributos permitem descrever um produto e suas características em campos definidos pelo usuário.

Os atributos permitem descrever um produto e suas características em campos definidos pelo usuário. Por exemplo, você pode especificar o tamanho de memória do produto e a capacidade de disco rígido, e indicar se o produto é compatível com Energy Star. Os atributos podem ser associados a várias entidades de varejo, como categorias de produto e canais de varejo; os valores padrão podem ser definidos para eles. Os produtos herdam atributos e valores padrão para esses atributos quando eles são associados às categorias de produto ou aos canais de varejo. Os valores padrão podem ser substituídos no nível do produto individual, no nível de canal de varejo ou em um catálogo de varejo.

#### <a name="examples"></a>Exemplos

| Categoria   | Atributo                | Valores permitidos          | Valor padrão |
|------------|--------------------------|-----------------------------|---------------|
| TV e vídeo | Marca                    | Qualquer valor de Marca válido       | Nenhum(a)          |
| TV         | Tamanho de Tela              | 20″–80″                     | Nenhum(a)          |
| TV         | Resolução Vertical      | 480i, 720p, 1080i ou 1080p | 1080p         |
| TV         | Taxa de Atualização da Tela      | 60hz, 120hz ou 240hz       | 60hz          |
| TV         | Entradas HDMI              | 0–10                        | 3             |
| TV         | Entradas DVI               | 0–10                        | 1             |
| TV         | Entradas Compostas         | 0–10                        | 2             |
| TV         | Entradas de Componentes         | 0–10                        | 1             |
| LCD        | Pronto para 3D                 | Sim ou Não                   | Sim           |
| LCD        | Habilitado para 3D               | Sim ou Não                   | Não            |
| Plasma     | Operação Temporária de      | 32–110 graus              | 32            |
| Plasma     | Operação Temporária até        | 32–110 graus              | 100           |
| Projeção | Garantia de Tubo de Projeção | 6, 12 ou 18 meses         | 12            |
| Projeção | Nº de Tubos de Projeção    | 1–5                         | 3             |


## <a name="attribute-type"></a>Tipo de atributo
  [![attributes-fixed-copy](./media/attributes-fixed-copy.png)](./media/attributes-fixed-copy.png) 
  
Os atributos são baseados nos tipos de atributos. Os tipos de atributos identificam o tipo de dados que podem ser inseridos para um atributo específico. Atualmente, o Microsoft Dynamics 365 for Operations dá suporte aos seguintes tipos de atributos:

-   **Moeda** – Este tipo de atributo dá suporte a valores de moeda. Ele pode ser limitado (isto é, ele pode dar suporte a um intervalo de valores), ou pode ser deixado aberto.
-   **Data/Hora** – Este tipo de atributo dá suporte a valores de data e hora. Ele pode ser limitado (isto é, ele pode dar suporte a um intervalo de valores), ou pode ser deixado aberto.
-   **Decimal** – Este tipo de atributo dá suporte a valores numéricos que incluem casas decimais. Ele também dá suporte a unidades de medida. Ele pode ser limitado (isto é, ele pode dar suporte a um intervalo de valores), ou pode ser deixado aberto.
-   **Inteiro** – Este tipo de atributo dá suporte a valores numéricos. Ele também dá suporte a unidades de medida. Ele pode ser limitado (isto é, ele pode dar suporte a um intervalo de valores), ou pode ser deixado aberto.
-   **Texto** – Este tipo de atributo dá suporte a valores de texto. Ele também dá suporte a um conjunto predefinido de valores possíveis (enumeração).
-   **Booliano** – Este tipo de atributo dá suporte a valores binários (**true**/**false**).
-   **Referência**.

## <a name="attribute"></a>Atributo
  [![createandmanageattribute-8](./media/createandmanageattribute-8.png)](./media/createandmanageattribute-8.png) Além de nome, nome amigável, descrição e texto da ajuda, um ou mais dos seguintes tipos de informações podem ser capturados de um atributo:

-   Valor padrão
-   Atribua metadados, como metadados que indicam se o atributo pode ser pesquisado, refinado ou classificado

## <a name="attribute-group"></a>Grupo de atributos
  [![createandmanageattribute-10](./media/createandmanageattribute-10.png)](./media/createandmanageattribute-10.png) Após definidos, os atributos podem ser agrupados em grupos de atributos. Os grupos de atributos fornecem agrupamentos de atributos individuais, e podem ser atribuídos a categorias de varejo ou canais de varejo.

## <a name="assigning-attribute-groups-to-retail-categories"></a>Como atribuir grupos de atributos a categorias de varejo
  [![createandmanageattribute-12](./media/createandmanageattribute-12.png)](./media/createandmanageattribute-12.png) Um ou mais grupos de atributos podem ser associados a nós de categoria na hierarquia de categorias de produto de varejo. Quando produtos são categorizados, eles herdam os atributos que são incluídos nos grupos de atributos.

## <a name="assigning-attribute-groups-to-retail-stores"></a>Como atribuir grupos de atributos a lojas de varejo
  [![createandmanageattribute-13-1024x576](./media/createandmanageattribute-13-1024x576.png)](./media/createandmanageattribute-13-1024x576.png) Um ou mais grupos de atributos podem ser associados a uma ou mais lojas de varejo na hierarquia de lojas de varejo. Quando produtos são enriquecidos para lojas de varejo específicas, eles herdam os atributos que são incluídos nos grupos de atributos.

## <a name="overriding-attribute-values"></a>Substituição de valores de atributo
### <a name="at-the-product-level"></a>Em nível de produto

  [![createandmanageattribute-14-1024x576](./media/createandmanageattribute-14-1024x576.png)](./media/createandmanageattribute-14-1024x576.png) Os valores padrão de atributos podem ser substituídos no nível de produto (isto é, para produtos individuais).

### <a name="in-a-retail-catalog"></a>Em um catálogo de varejo

  [![createandmanageattribute-2](./media/createandmanageattribute-2.png)](./media/createandmanageattribute-2.png) Os valores padrão de atributos podem ser substituídos para produtos individuais em catálogos específicos que são destinados a canais de varejo específicos.

### <a name="at-the-retail-channel-level"></a>Em nível de canal de varejo

  [![createandmanageattribute-1](./media/createandmanageattribute-1.jpg)](./media/createandmanageattribute-1.jpg) Os valores padrão de atributos podem ser substituídos para produtos individuais em catálogos específicos que são destinados a canais de varejo específicos.





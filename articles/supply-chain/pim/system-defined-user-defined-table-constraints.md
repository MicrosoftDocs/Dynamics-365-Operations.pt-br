---
title: "Restrições de tabela definidas pelo sistema e pelo usuário"
description: "Este artigo explica os dois tipos de restrições de tabela definidas pelo usuário e pelo sistema para os componentes de um modelo de configuração de produto: definido pelo usuário e definido pelo sistema. As restrições de tabela representam matrizes das combinações de atributos permitidos, onde cada linha define um conjunto de possíveis valores de atributo."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCTableConstraintAttachAttributeTree, PCTableConstraintColumnSystem, PCTableConstraintContentUserDef, PCTableConstraintDefinition, PCTableConstraintWizard
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19781
ms.assetid: 0a4ea930-b344-43a8-871e-d5cd077892c4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 77333761aee426c6fa2d9261eaa3fda1a76811f0
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="system-defined-and-user-defined-table-constraints"></a>Restrições de tabela definidas pelo sistema e pelo usuário

[!include[banner](../includes/banner.md)]


Este artigo explica os dois tipos de restrições de tabela definidas pelo usuário e pelo sistema para os componentes de um modelo de configuração de produto: definido pelo usuário e definido pelo sistema. As restrições de tabela representam matrizes das combinações de atributos permitidos, onde cada linha define um conjunto de possíveis valores de atributo.

As restrições de tabela representam matrizes de combinações de atributos que são permitidas para componentes de um modelo de configuração do produto. Cada linha na tabela define um conjunto de valores de atributo possíveis. É possível declarar dois tipos de restrições em um modelo de configuração de produto:

-   **Restrição de expressão** – Cria uma expressão que define relações entre os atributos para garantir que somente os valores compatíveis possam ser selecionados durante a configuração do produto.
-   **Restrição de tabela** – Cria uma tabela que define todas as combinações que são permitidas para um conjunto específico de atributos. Dois tipos de restrições de tabela estão disponíveis: restrições de tabela definidas pelo usuário e restrições de tabela definidas pelo sistema.

Este artigo descreve as restrições de tabela definidas pelo usuário e pelo sistema para os componentes de um modelo de configuração de produto.

## <a name="user-defined-table-constraints"></a>Restrições de tabela definidas pelo usuário
Uma restrição de tabela definida pelo usuário é um tipo de matriz que é usada para descrever as combinações de valores de atributo que são definidas pelos tipos de atributos. Por exemplo, se você produz alto-falantes, pode incluir as colunas para o acabamento do gabinete e a grade frontal na restrição de tabela definida pelo usuário. O tipo de atributo para o acabamento do gabinete possui quatro valores, e o tipo de atributo para a grade frontal tem três valores. Consequentemente, se as restrições não são usadas, haverá as combinações possíveis de 4 × 3 = 12. No entanto, neste exemplo, apenas seis combinações são permitidas, como mostra a tabela a seguir. Estas informações são exibidas na guia **Combinações permitidas** na página **Editar restrição de tabela**.

| Acabamento do gabinete | Grade frontal |
|----------------|-------------|
| Preto          | Preto       |
| Preto          | Metal       |
| Carvalho            | Preto       |
| Jacarandá       | Branco       |
| Branco          | Preto       |
| Branco          | Branco       |

As restrições de tabela definidas pelo usuário são definidas pela entrada de tabela estática que funciona da mesma forma que uma restrição de expressão. Ao usar uma restrição de tabela definida pelo usuário, a vantagem é que as tabelas são frequentemente mais fáceis de serem criadas, compreendidas, e mantidas do que as restrições de expressão extensas.

## <a name="system-defined-table-constraints"></a>Restrições de tabela definidas pelo sistema
Uma restrição de tabela definida pelo sistema cria um mapeamento dinâmicos entre um tipo de atributo e um campo em uma tabela. Quando uma restrição de tabela definida pelo sistema for incluída em um modelo de configuração do produto, o mapeamento garante que os dados da tabela serão mostrados em vez dos valores de tipo de atributo. O resultado é uma restrição dinâmica, pois o conteúdo da tabela pode ser alterado (por exemplo, por outros módulos).  

Ao criar uma restrição de tabela definida pelo sistema, selecione uma tabela, se preferir, defina a consulta a ser usada e, em seguida, associe os tipos de atributos aos campos da tabela selecionada. Os tipos dos campos devem corresponder aos tipos dos tipos de atributo.  

Antes que uma restrição de tabela possa ter efeito em um modelo de configuração de produto, a restrição de tabela deve ser incluída em uma restrição em um dos componentes do modelo. O procedimento é criar uma nova restrição, selecionar o tipo de restrição de tabela e, em seguida, selecionar a definição de restrição de tabela a ser usada. Por fim, todos os campos na tabela de restrição devem ser mapeados para atributos no modelo de configuração do produto.

<a name="see-also"></a>Consulte também
--------

[Principais conceitos em modelos de configuração de produtos](product-configuration-models.md)





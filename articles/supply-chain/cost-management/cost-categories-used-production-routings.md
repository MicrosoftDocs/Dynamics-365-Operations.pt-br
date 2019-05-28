---
title: Categorias de custo usadas em roteiros de produção
description: Este artigo oferece informações sobre as categorias de custo que se aplicam aos ambientes de fabricação que usam o roteiro.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjCategory, RouteCostCategoryPrice
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 78153
ms.assetid: a3fdc76c-0a27-4723-b1c7-4322f707d89e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 90177a6b8dd277ba1180073c9cf416f857c5d730
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1569231"
---
# <a name="cost-categories-used-in-production-routing"></a>Categorias de custo usadas em roteiros de produção

[!include [banner](../includes/banner.md)]

Este artigo oferece informações sobre as categorias de custo que se aplicam aos ambientes de fabricação que usam o roteiro.

As categorias de custo se aplicam aos ambientes de fabricação que usam roteiro. Elas são atribuídas aos recursos de operações e às operações de roteiro para definir custos por hora e segmentar as contribuições de custo nos custos calculados de um item fabricado. Os grupos de custos atribuídos a categorias de custo classificam as contribuições de custo de fabricação com base nos recursos de operações e no tipo de atividade, como tempo de preparação e de execução. A especificidade das atribuições de grupo de custos permite que uma sobrecarga de fabricação seja calculada com base nas informações de roteiro. 

**Observação:** em ambientes de fabricação, as categorias de custo são conhecidas por vários outros nomes, como códigos de taxa de mão-de-obra ou códigos de taxa de máquina. 

Cada categoria de custo tem registros de custo associados e um grupo de custos atribuído. Diferentes categorias de custo são necessárias para diferentes finalidades de produção.

-   Atribua custos por hora diferentes, dependendo do recurso de operações. Por exemplo, os custos podem ser diferentes para vários tipos de habilidades de mão-de-obra, de máquinas ou de células de fabricação.
-   Atribua custos por hora diferentes para o tempo de preparação ou de execução associado a uma operação de roteiro.
-   Atribua custos de recursos de operações com base na quantidade de saída em vez de usar custos por hora, como as taxas de peça para pagar a mão de obra.
-   Forneça segmentação de grupo de custos de contribuições de custo para um custo calculado do item manufaturado. Por exemplo, você pode segmentar de custos de mão-de-obra e de máquinas.
-   Forneça a base do grupo de custos para fórmulas de cálculo de custos gerais indiretos, como fórmulas para custos gerais indiretos relacionados à mão-de-obra ou à máquina ou aqueles relacionados ao tempo de preparação ou de execução.

Uma categoria de custo pode ser atribuída ao tempo de preparação, ao tempo de processamento e à quantidade para uma operação de roteiro. Quando, por exemplo, a segmentação dos custos ou do grupo de custos for diferente entre o tempo de preparação e de processamento, as diferentes categorias de custos deverão ser definidas e atribuídas ao tempo de preparação e ao tempo de processo. O uso seletivo de categorias de custo para tempo de preparação, tempo de processamento e quantidade é determinado pelo grupo de roteiros atribuído a uma operação. A atribuição de categorias de custo ao tempo e à quantidade pode ser obrigatória dependendo das políticas da empresa definidas na página **Parâmetros de controle de produção**. 

Cada categoria de custo tem custos associados que dependem da definição de registros de custo em uma versão do custo. Use a página **Preço de categoria de custo** para definir os registros de custo para uma versão de custos e um site especificados. Quando o registro de custo de uma categoria de custo é inserido pela primeira vez, tem um status **Pendente** e uma data de efetivação pretendida. Quando você ativa o registro de custo do item, o status é atualizado para **Atualmente ativo** e a data de efetivação é atualizada para a data de ativação. Os registros de custo diferentes podem refletir sites, datas efetivas ou status diferentes. Os cálculos da BOM (listas de materiais) para uma data futura ou histórica usarão os registros de custo contendo a data efetiva relevante. O registro de custo ativo no momento será usado para estimar os custos de ordem de produção e avaliar o tempo relatado contra uma ordem de produção. 

O registro de custo para uma categoria de custo pode ser específico ao site ou a toda a empresa. Para criar um site de registro de custo específico, atribua um site a ele. Caso contrário, um valor em branco indica que o registro de custo se aplica a todos os sites da empresa. Como os custos podem ser diferentes de um site para outro, por exemplo, os registros de custo devem ser definidos como específicos ao site. 

Uma operação de roteiro geralmente herda as categorias de custo atribuídas ao recurso de operações ou à operação principal. Quando uma ordem de produção é criada, as operações de roteiro no roteiro de produção refletem a versão do roteiro selecionada. Você pode substituir as categorias de custo que são atribuídas às operações no roteiro de produção. 

Alguns tipos de trabalho de produção podem ser aplicados a estimativas de tempo de projeto e a relatórios. Nesse caso, uma categoria de custo é necessária para fins de produção e de projeto. Você deve definir outras informações relacionadas ao projeto quando uma categoria de custo é sinalizada para uso em projetos.




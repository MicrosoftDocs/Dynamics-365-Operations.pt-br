---
title: Restrições em versões de avaliação de custo para custos padrão
description: Este tópico descreve as restrições que se aplicam a uma versão de avaliação de custo para custos padrão.
author: AndersGirke
manager: tfehr
ms.date: 01/17/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostingVersion
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2348d7721cd281bb2a1b5af007c98ce69377a412
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3214426"
---
#  <a name="restrictions-on-costing-versions-for-standard-costs"></a>Restrições em versões de avaliação de custo para custos padrão

[!include [banner](../includes/banner.md)]

Este tópico descreve as restrições que se aplicam a uma versão de avaliação de custo para custos padrão. 

As restrições a seguir ajudam a garantir a aderência aos princípios de avaliação de custo padrão:

-  Os encargos devem ser incluídos no custo de um item. Os encargos para um item fabricado representam os custos constantes amortizados na lista de materiais (BOM) e nas informações de roteiro. Portanto, os encargos devem ser incluídos no custo unitário. Os encargos para um item comprado também estão incluídos no custo unitário do item.

-  O cálculo de custos padrão de itens fabricados deve ser baseado nos registros de custo em uma versão do custo para custos padrão. Fontes alternativas de dados de custo só podem ser usadas com uma versão de avaliação de custo para custos planejados, como contratos comerciais de preço de compra para itens comprados. Fontes alternativas de dados de custo são definidas pelo grupo de cálculo de BOM.

-  Os cálculos de BOM devem ser feitos em um modo de detalhamento de nível único.

Os dados de custo de item para custos padrão podem ser copiados em outra versão do custo que contenha os custos padrão ou planejados. Porém, os dados de custo de item para os custos planejados não podem ser copiados para uma versão de custo que contenha custos padrão porque as restrições listadas anteriormente neste tópico não se aplicam aos custos planejados.

<a name="related-topics"></a>Tópicos relacionados
--------

[Visão geral de versões de avaliação de custo](costing-versions.md)

[Atualizar custos padrão em um ambiente de não fabricação](update-standard-costs-non-manufacturing-environment.md)

[Preparar para manter custos padrão para itens fabricados](update-standard-costs-manufacturing-environment.md)


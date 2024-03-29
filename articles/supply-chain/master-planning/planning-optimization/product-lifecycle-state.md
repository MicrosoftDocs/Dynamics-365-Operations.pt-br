---
title: Excluir produtos que têm estados específicos do ciclo de vida do produto
description: Este artigo explica como excluir produtos com base em seu estado de ciclo de vida.
author: t-benebo
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-11-13
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 647e2cf4f14dbdfc3e7f04f43dcbd7115f19e8dc
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740756"
---
# <a name="exclude-products-that-have-specific-product-lifecycle-states"></a>Excluir produtos que têm estados específicos do ciclo de vida do produto

[!include [banner](../../includes/banner.md)]

Produtos liberados e versões liberadas do produto incluem um campo **Estado do ciclo de vida do produto**. Este campo permite controlar, dentre outras coisas, quais produtos são incluídos durante o planejamento mestre. É possível adicionar, remover e editar estados do ciclo de vida, conforme a necessidade, acessando **Gerenciamento de informações de produto \> Configuração \> Estado do ciclo de vida do produto**. Para cada estado do ciclo de vida do produto, defina a opção **Está ativa para o planejamento** como *Sim* se os produtos que tiverem esse estado tiverem de ser incluídos durante o planejamento mestre. Quando a opção for definida como *Não*, os produtos e as grades associados serão excluídos de todo o planejamento mestre e de todos os cálculos no nível da BOM (lista de materiais).

Os produtos e as grades liberados nos quais o campo **Estado do ciclo de vida do produto** é deixado em branco são tratados como se tivessem um estado de ciclo de vida do produto, em que a opção **Ativo para planejamento** está definida como *Sim*. Em outras palavras, eles serão incluídos durante o planejamento mestre.

> [!NOTE]
> Para ajudar a evitar sugestões de fornecimento desnecessárias, é altamente recomendável que você associe todos os produtos e grades obsoletos com um estado do ciclo de vida do produto em que a opção **Está ativa para o planejamento** está definida como *Não*. Essa abordagem é especialmente importante quando você trabalha com grades de configuração de produtos que não podem ser reutilizadas, pois ela ajudará a evitar desperdício.

## <a name="related-resources"></a>Recursos relacionados

Para obter mais informações sobre estados de ciclo de vida de produtos, consulte a [Visão geral do estado de ciclo de vida de produtos](../../pim/product-lifecycle.md).

Para obter informações detalhadas que incluem etapas para usar estados de ciclo de vida de produto para excluir produtos dos cálculos de planejamento mestre e do nível da BOM, consulte [Criar um estado do ciclo de vida do produto para excluir produtos do planejamento mestre](../../pim/tasks/exclude-products-master-planning.md).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
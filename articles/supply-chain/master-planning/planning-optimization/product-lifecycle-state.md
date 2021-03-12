---
title: Excluir produtos que têm estados específicos do ciclo de vida do produto
description: Este tópico explica como excluir produtos com base no estado do ciclo de vida ao usar a funcionalidade de otimização de planejamento.
author: ChristianRytt
manager: tfehr
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-11-13
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 02c31aa3862df8dabc2b8c065dc3a94877d237f6
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992411"
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

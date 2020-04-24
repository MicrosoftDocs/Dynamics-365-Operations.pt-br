---
title: Atualizar custos padrão em um ambiente de fabricação
description: Este artigo fornece a orientação sobre como atualizar custos padrão em um ambiente de fabricação.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostingVersion, InventStdCostConv
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 79663
ms.assetid: 3a7c3d13-8dbc-442d-a281-ac0ebe99ec83
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ea810daab0ecdee59aba703f38d0001e2965f936
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3214140"
---
# <a name="update-standard-costs-in-a-manufacturing-environment"></a>Atualizar custos padrão em um ambiente de fabricação

[!include [banner](../includes/banner.md)]

Este artigo fornece a orientação sobre como atualizar custos padrão em um ambiente de fabricação. 

As atualização podem refletir novos itens, categorias de custo ou fórmulas de cálculo de custo indireto. Também podem refletir correções e alterações de custo. O tipo de atualização afeta as etapas que você deve completar para atualizar os custos padrão, como ilustrado nos seguintes casos:

-   Insira alterações de custo padrão antecipadas para itens comprados e em seguida altere o status dos registros de custo de item para **Ativo** na data apropriada. No entanto, não calcule novamente os custos dos itens fabricados que usam os itens comprados.
-   Insira custos padrão para um novo item comprado, mas não calcule novamente os custos de itens fabricados que têm uma versão de lista de materiais (BOM) que contém o novo item comprado como um componente.
-   Corrija ou altere o custo do item comprado ou altere o grupo de custo atribuído a um item comprado e calcule o custo para todos os itens fabricados que têm uma versão de BOM que contém o item comprado como um componente.
-   Altere o custo para uma categoria de custo e calcule o custo para todos os itens fabricados que têm uma versão de roteiro que contém operações de roteiro as quais usam a categoria de custo.
-   Altere as categorias de custo atribuídas a operações de roteiro ou o grupo de custos atribuído a categorias de custo. Altere o custo para uma categoria de custo e calcule o custo para todos os itens fabricados que têm uma versão de roteiro que contém operações de roteiro as quais usam a categoria de custo.
-   Altere uma fórmula de cálculo de custo indireto e calcule o custo para todos os itens fabricados afetados pela alteração.
-   Altere ou adicione um site de fabricação para um item fabricado e calcule o custo de fabricação do item para o site.
-   Calcule ou recalcular o custo para um item fabricado e calcule novamente o custo para todos os itens fabricados que têm uma versão de BOM que contém o item fabricado como um componente.
-   Calcule os custos para um novo item fabricado com base na BOM aprovada e ativa, assim como nas informações de roteiro.

Cada caso requer considerações sobre como atualizar custos padrão.




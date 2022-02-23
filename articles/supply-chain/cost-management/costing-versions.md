---
title: Visão geral de versões de avaliação de custo
description: Este artigo fornece informações sobre versões de custos, como mantê-las e os tipos de dados que podem estar incluídos nelas. A finalidade principal de uma versão de custo é conter registros de custo sobre itens, categorias de custo e fórmulas de cálculo para custos indiretos.
author: AndersGirke
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMCalcDialog, BOMCalcTable, CostingVersion
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 54532
ms.assetid: cd239da5-f434-4d1b-8196-5414c888d76d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cefee7d678789f462eedbf9f9a3fbc9b591e25a2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422472"
---
# <a name="costing-versions-overview"></a>Visão geral de versões de avaliação de custo

[!include [banner](../includes/banner.md)]

Este artigo fornece informações sobre versões de custos, como mantê-las e os tipos de dados que podem estar incluídos nelas. A finalidade principal de uma versão de custo é conter registros de custo sobre itens, categorias de custo e fórmulas de cálculo para custos indiretos.

Uma versão de custo pode servir a um ou mais finalidades, dependendo dos dados contidos na versão de custo. A finalidade principal de uma versão de custo é conter registros de custo sobre itens, categorias de custo e fórmulas de cálculo para custos indiretos. Uma versão de custo pode conter um conjunto de registros de custo padrão ou um conjunto de registros de custo planejado com base no tipo de custo atribuído à versão de custo.

## <a name="costing-versions-for-standard-or-planned-costs"></a>Versões de custos para custos padrão ou planejados
### <a name="standard-costs"></a>Custos padrão

Uma versão de custo pode suportar um modelo de estoque de custo padrão para itens, na qual a versão de custo contém um conjunto de registros de custo padrão sobre itens e processos de fabricação. Os dados de custo sobre processos de fabricação é expresso em termos de categorias de custo para operações de roteiro e as fórmulas de cálculo para custos gerais indiretos de fabricação.

### <a name="planned-costs"></a>Custos planejados

Uma versão de custo pode conter um conjunto de registros de custo planejado sobre itens e processos de fabricação. Uma versão de custo que contém custos planejados é usada normalmente para dar suporte a simulações de cálculo de custo, como simulações do efeito de alterações de custo de materiais comprados ou de processos de fabricação nos custos calculados de itens fabricados. Os registros de custo de item para custos planejados também podem ser usados para dar suporte a um modelo de estoque de custo real ao fornecer os valores iniciais para custos de item. Esses valores incluem o cálculo de custos planejados para itens fabricados.

## <a name="entering-costs"></a>Inserção de custos
A manutenção de dados para registros de custo em uma versão de custo envolve inserir custos para itens comprados e para itens que são transferidos entre sites. A manutenção de dados adicional para fabricantes envolve inserir custos para categorias de custo associadas com operações de roteiro, inserir fórmulas de cálculo para os custos indiretos que refletem os custos gerais indiretos de fabricação e custos de cálculo para itens fabricados. 

Os dados de custo de item em uma versão de custo consistem em um ou mais registros de custo para cada item. Quando um registro de custo de item é inserido pela primeira vez, tem um status **Pendente** e uma data de efetivação pretendida. Quando você ativa o registro de custo do item, o status é atualizado para **Ativo** e a data de efetivação é atualizada para a data de ativação. Os registros de custo de item diferentes podem refletir locais, datas de efetivação ou status diferentes. Ao calcular custos para itens fabricados para uma data futura, o cálculo da BOM (lista de materiais) usará registros de custo com a data efetiva relevante, independentemente de o status ser **Pendente** ou **Ativo**. Um registro de custo ativo atual de um item é usado para estimar custos de ordem de produção e para avaliar transações de estoque sob um modelo de estoque de custo padrão. A manutenção dos registros de custo para categorias de custo e fórmulas de cálculo de custo indireto parece com a manutenção de registros de custo de item. 

Duas políticas de bloqueio para uma versão de custo determinam se os custos pendentes podem ser mantidos e se o custo pendente pode ser ativado. Use as políticas de bloqueio para permitir a manutenção de dados e então para impedir a manutenção de dados para registros de custo em uma versão de avaliação de custo. 

Uma versão de custo também pode conter dados sobre preços de venda de item ou preços de compra com a finalidade de calcular a BOM.

## <a name="item-sales-prices-for-bom-calculations"></a>Preços de venda de item para cálculos de BOM
O motivo principal para incluir os dados sobre os preços de vendas é para reter o preço de venda calculado do item manufaturado. O preço de venda calculado pode então ser analisado para determinar como os componentes, operações de roteiro e custos gerais indiretos contribuem para custo e o preço de venda. 

Um motivo secundário para incluir os dados sobre os preços de venda é definir os registros de preço de venda para itens de componente. Esses registros podem ser usados para calcular o preço de venda de itens fabricados. Você primeiro define o módulo de preço de venda inserido em um grupo de cálculo de BOM e atribui o grupo de cálculo de bom a itens comprados. Em seguida, ao executar cálculos de BOM que usem custos planejados, você seleciona o modelo de preço de custo de grupo de cálculo de BOM. 

Caso contrário, os registros de preço de vendas por item são usados somente como informações de referência, independente dos registros que são inseridos manualmente ou calculados. Ao ativar o registro do preço de vendas de um item, você pode atualizar o preço de venda base desse item. No entanto, o preço de venda base não é específico para o lugar e pode ser substituído manualmente. O preço de venda base do item é usado como um preço de venda padrão em ordens de venda e cotações de venda.

## <a name="item-purchase-prices-for-bom-calculations"></a>Preços de compra de item para cálculos de BOM
O principal motivo para habilitar os dados de preço de compra é definir registros de preço de compra para itens do componente, para que esses registros possam ser usados para calcular os custos dos itens fabricados. Os registros de preço de compra de item devem ser inseridos manualmente. 

Para habilitar o conteúdo de preço de compra, você primeiro define um grupo de cálculos de BOM que contenha um modelo de preço de custo para o preço de compra do item e atribui o grupo de cálculos de BOM aos itens comprados. Você deve usar um modelo de preço de custo para o grupo de cálculos de BOM ao executar cálculos de BOM que usem custos planejados para calcular o preço de venda de itens fabricados. 

Os registros de preço de compra de itens também são usados para informações de referência. Alterando o status do registro de preço de compra de um item de **Pendente** para **Ativo**, você pode atualizar o preço de compra base do item. No entanto, o preço de compra base não é específico para o lugar e pode ser substituído manualmente. O preço de compra base do item é usado como o preço de compra padrão nas ordens de compra.




---
title: Dimensões do elemento de custo
description: Como uma colunas principal na contabilização de custo estimado, as dimensões do elemento de custo previsto são usados para categorizar e rastrear o fluxo onde os custos.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 223204
ms.assetid: 1eda0e62-760b-4737-9dfd-3c3c38d80c1a
ms.search.region: global
ms.author: shylaw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: c703d1a9ae36d4342dc652d70dd82379187057c1
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1565732"
---
# <a name="cost-element-dimensions"></a>Dimensões do elemento de custo

[!include [banner](../includes/banner.md)]

Como uma colunas principal na contabilização de custo estimado, as dimensões do elemento de custo previsto são usados para categorizar e rastrear o fluxo onde os custos. 

Um elemento de custo previsto corresponde a um item de custo relevante no plano de contas. Basicamente, pode ser qualquer tipo de elemento no nível mais baixo em uma empresa em que os custos podem fluxo. Elementos de custo previsto como um conceito variam contábeis a todos os recursos para relevantes. Atualmente, a contabilização de custo previsto suporta contas contábeis.

## <a name="two-types-of-cost-elements"></a>Dois tipos de elementos de custo previsto
Há dois tipos de elementos de custo previsto: elementos de custo previsto e principais elementos de custo previsto secundárias. A tabela a seguir descreve a diferença entre os dois tipos.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Elementos de custo primário</strong></td>
<td><strong>Elementos de custo secundários</strong></td>
</tr>
<tr class="even">
<td>Elementos de custo previsto primários representam o fluxo de custo de conta financeira a contabilização de custo previsto. A estrutura de elemento de custo previsto corresponde à estrutura da conta de lucros e perdas na contabilidade, no qual um elemento de custo previsto pode corresponder a uma conta principal. Nem todas as contas podem ser principais necessariamente representadas como os elementos de custo previsto dependendo das necessidades comerciais. Exemplos de elementos de custo previsto primários incluem:
<ul>
<li>Custos dos produtos vendidos (COGs)</li>
<li>Custos indiretos de material</li>
<li>Custo da equipe</li>
<li>Custos de energia</li>
</ul></td>
<td>Elementos de custo previsto secundários representam o fluxo de custo interna pois esses custos são criados e usados somente na contabilização de custo previsto. Seguro são usados para a fonte de custo pode ser rastreado. Esses elementos de custo são usados em alocações de custo e cálculos de despesas gerais. Exemplos de elementos de custo previsto secundários incluem:
<ul>
<li>Custos da produção</li>
<li>Produção, material, e sobrecargas de marketing</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="cost-element-dimensions-and-cost-element-dimension-members"></a>Dimensões de elemento de custo previsto e membros da dimensão do elemento de custo previsto
Elementos de custo previsto são referidos como *dimensões de elemento de custo previsto*. Os valores de dimensão específicos são chamados de *membros da dimensão do elemento de custo previsto*. Por exemplo, você tem um gráfico. de E contracheques. estrutura de contas (COA) que é a base para seu relatório legal. Este COA é usado como a dimensão do elemento de custo previsto. Contas, as quais são elementos de custos principais, previsto são representadas como membros da dimensão do elemento de custo estimado na contabilização de custo previsto. A captura de tela a seguir mostra um exemplo de como contas a dimensão do elemento de custo previsto com as listas principais real como membros da dimensão do elemento de custo previsto. 

[![cost-element-dimensions](./media/cost-element-dimensions.png)](./media/cost-element-dimensions.png)

## <a name="import-cost-element-dimension-members-through-data-connectors"></a>Membros de custo previsto de dimensão de elemento de importação em dos conectores de dados
Para facilitar o de instalação de membros da dimensão do elemento de custo estimado na contabilização de custo previsto, você pode usar os conectores de dados que são ou criados anteriormente a compilação personalizado para recuperar os elementos de custo previsto principais de um ou vários sistemas de origem.

## <a name="implementation-considerations"></a>Considerações de implementação
Porque os elementos de custo previsto representam o nível mais baixo de detalhes de e realizado, você deve garantir que todos os elementos de custo previsto necessário para que o relatório de administração são incluídos quando ao implementar estrutura de elementos de custo previsto. Pode ser um desafio para localizar um número adequado de elementos de custo estimado para o controle de custo. Milhares de usar elementos de custo previsto pode fazê-lo difícil controlar cada elemento de custo previsto. Como alternativa, você pode agrupar os elementos de custo previsto e gerenciar o controle de custo em um nível agregado.




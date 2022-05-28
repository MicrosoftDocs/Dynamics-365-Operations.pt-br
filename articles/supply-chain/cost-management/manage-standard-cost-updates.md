---
title: Gerenciamento de atualizações de custo padrão
description: 'As atualizações de dados de custo padrão podem ser gerenciadas usando duas abordagens diferentes: a abordagem de uma versão ou a abordagem de duas versões.'
author: JennySong-SH
ms.date: 01/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostingVersion, InventItemPrice, InventParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: 69992
ms.assetid: 468de7af-c7b5-4345-bd5a-ba3aa5a900cc
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: a6d693b58e7fbbd8e082d68d124eae52fb840b02
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8674523"
---
# <a name="manage-standard-cost-updates"></a>Gerenciamento de atualizações de custo padrão

[!include [banner](../includes/banner.md)]

As atualizações de dados de custo padrão podem ser gerenciadas usando duas abordagens diferentes: a abordagem de uma versão ou a abordagem de duas versões.

A abordagem de uma versão usa uma única versão de avaliação de custo que contém todos os registros de custo. Esses registros incluem os custos originais e todas as atualizações de custo.

A abordagem de duas versões usa uma versão que contém os registros de custos originais e uma segunda versão que contém os registros de todas as atualizações de custo. Uma vantagem principal da abordagem de duas versões é a delineação clara e o rastreamento de atualizações de custo em uma versão de custo separada sem afetar a versão de custo original. A abordagem de duas versões pode ser usada para identificar várias atualizações incrementais, onde cada atualização incremental possui uma versão de custo separada que contém os registros incrementais de custo.

## <a name="example"></a>Exemplo

O exemplo a seguir ilustra como as abordagens de uma versão e de duas versões podem ser usadas para atualizar os custos padrão em um ambiente de fabricação. Por exemplo, atualizações que refletem itens novos ou correções de erro. Suponha que uma única versão de avaliação de custo representa os custos padrão para o ano atual. O identificador para esta versão é 2020-STD. A versão 2020-STD contém os custos ativos atuais para todos os itens. Além disso, ela contém todas as categorias de custo relacionadas a roteiro e fórmulas de cálculo dos custos gerais indiretos que eram conhecidas no início do ano de 2020. 2020-STD é a versão de custo original.

- **Abordagem de uma versão para atualizações de dados de custo** − na abordagem de uma versão, a versão original de avaliação de custo 2020-STD contém todos os registros de custo. As atualizações de custo são registradas em 2020-STD e são definidas como um status Pendente. O custos pendentes podem ser inseridos manualmente para novos itens comprados, ou podem ser calculados para um item fabricado para refletir correções. Quando a abordagem de uma versão é usada, os cálculos de BOM não precisam de uma fonte de dados de reserva, pois todos os custos ativos estão contidos na versão de avaliação de custo. Após os custos pendentes se tornarem ativos, a versão original de avaliação de custo 2020-STD conterá novamente todos os custos ativos atuais.
- **Abordagem de duas versões para as atualizações de dados de custo** − a abordagem de duas versões requer uma versão adicional de avaliação de custo que contenha somente as atualizações de custo. O identificador para esta versão é 2020-STD-CHANGES. As atualizações de custo são registradas em 2020-STD-CHANGES e definidas para um status de Pendente. Com a abordagem de duas versões, os cálculos de BOM dos custos pendentes para os itens fabricados precisam de uma fonte de dados de reserva. Isso ocorre devido à versão adicional de avaliação de custo 2020-STD-CHANGES conter somente um subconjunto de dados de custo. O fallback pode ser expresso como os custos ativos ou como a versão de avaliação de custo 2020-STD, pois ambos identificam a fonte dos dados de custo quando ela não estiver incluída em 2020-STD-CHANGES. Após os custos pendentes se tornarem ativos, a versão de avaliação de custo 2020-STD-CHANGES conterá os custos ativos atuais que refletem as atualizações, enquanto que a versão original de avaliação de custo 2020-STD não será alterada. Quando a abordagem de duas versões é usada, as políticas de bloqueio para a versão original de avaliação de custo devem ser configuradas para evitar atualizações. As políticas de bloqueio idênticas devem ser configuradas para a versão adicional de avaliação de custo, exceto para a data de início especificada e o uso seletivo das políticas de bloqueio para permitir atualizações. A data De especificada deve ser atualizada com cada lote de alterações para refletir a data de ativação programada.

Este exemplo usou uma versão de avaliação de custo adicional para gerenciar atualizações durante o ano de 2020. Mais de uma versão de custo adicional pode ser usada, como uma versão separada para cada lote de atualizações. Quando mais de uma avaliação de custo adicional forem usadas, o fallback deve ser expresso como os custos ativos, pois os custos ativos são difundidos em diversas versões de avaliação de custos.

## <a name="financial-dimensions-for-the-standard-cost-revaluation"></a>Dimensões financeiras para a reavaliação de custo padrão

A ativação de um novo preço padrão geralmente reavalia o valor de estoque disponível por transações de reavaliação de custo padrão. Normalmente, as dimensões financeiras do item são lançadas nas transações. No entanto, se quiser controlar se e como as dimensões financeiras são lançadas, use o [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para ativar o recurso chamado *Opções de dimensões financeiras de uso padrão para reavaliação de custo padrão de estoque*. Depois de habilitar esse recurso, acesse **Gerenciamento de custos > Configuração das políticas contábeis de estoque > Parâmetros** e defina a nova lista suspensa **Origem de dimensão financeira** com um dos seguintes valores:

- **Nenhum** – nenhuma dimensão financeira é lançada nas transações de reavaliação. Se a estrutura da conta inclui uma dimensão financeira necessária, o processo de reavaliação ainda será executado, mas criará entradas de contabilidade sem dimensões financeiras. Nesse caso, os usuários receberão uma mensagem de aviso antes, para que possam cancelar a reavaliação se necessário.
- **Tabela** – As dimensões financeiras do item são lançadas nas transações de reavaliação. Esta é a configuração padrão e é consistente com o comportamento do sistema original sem ativar o recurso *Opções de dimensões financeiras de uso padrão para reavaliação de custo padrão do estoque*.
- **Lançamento** – as dimensões financeiras da transação que estão sendo reavaliadas são lançadas nas transações de reavaliação. Por padrão, as dimensões financeiras da conta de estoque da transação original serão usadas para as contas de estoque e de reavaliação.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
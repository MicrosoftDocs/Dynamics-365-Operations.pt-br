---
title: Descartar um ativo fixo como sucata
description: O tópico descreve o processo de eliminação de transações de um ativo fixo que foi descartado como sucata.
author: moaamer
ms.date: 08/14/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-14
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 413847d350ca6b2bdd6153a598ea5b3f34a33818
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826266"
---
# <a name="dispose-of-a-fixed-asset-as-scrap"></a>Descartar um ativo fixo como sucata

[!include [banner](../includes/banner.md)]

O tópico descreve o processo de eliminação de transações de um ativo fixo que foi descartado como sucata. Os tipos de transação que podem ser eliminados incluem transações depreciação acumulada e aquisição de um ativo, além de outras transações de ativos fixos. A eliminação dessas transações afeta as contas de balanço, como contas de ajuste de aquisição, ajuste de depreciação, reavaliação, valorização e desvalorização.

| Transação                                         | Débito (Dr.) | Crédito (Cr.) |
|-----------------------------------------------------|-------------|--------------|
| Dr. Depreciação acumulada                        | X           |              |
| Cr. Ganho/perda de ativos fixos                          |             | X            |
| Dr. Ganho/perda de ativos fixos                          | X           |              |
| Cr. Conta de aquisição de ativos fixos                 |             | X            |
| Dr. Ganho/perda de ativos fixos (valor líquido contábil \[NBV\]) | X           |              |
| Cr. Ganho/perda de ativos fixos (NBV)                    |             | X            |

> [!NOTE]
> Recomendamos que você trabalhe de perto com o diretor financeiro (CFO) ou controlador da empresa para identificar as contas corretas que devem ser usadas para cada tipo de transação e também para confirmar que o processo de descarte e as transações que ele gera atualizam essas as contas corretamente.

Antes de descartar um ativo fixo como sucata, é necessário criar as contas contábeis associadas com o valor de aquisição do ativo, a depreciação do ano atual, a depreciação dos anos anteriores e o NBV do ativo. Os tipos de transação de ativo fixo estão listados na página **Perfis de lançamentos de ativo fixo** . Vá para **Ativos fixos \> Configuração \> Perfis de lançamentos de ativo fixo** e, na Guia Rápida **Alienação**, selecione **Sucata** no campo acima da grade. A ilustração a seguir mostra a lista de tipos de transação de ativo fixo na página **Perfis de lançamentos de ativo fixo** .


[![Descarte de um ativo fixo como sucata, Fig. 1.](./media/Fixed_asset_Disposal_scrap_scenario_1.png)](./media/Fixed_asset_Disposal_scrap_scenario_1.png)

Para o exemplo a seguir, um ativo fixo for adquirido em 1º de janeiro de 2018 e será sucateado em 31 de março de 2019.

- **Preço de aquisição:** 24.000,00 dólares americanos (USD)
- **Vida útil:** 2 anos
- **Método de depreciação:** Vida útil linear
- **Valor de depreciação:** 1.000,00 USD por mês

O NBV de um ativo fixo é calculado usando a seguinte fórmula:

Valor líquido contábil = preço de aquisição – depreciação

Neste exemplo, o ativo fixo foi adquirido e depreciado por 15 meses, de janeiro de 2018 até março de 2019. Portanto, o NBV do ativo é 9.000,00 USD (24.000,00 USD – 15.000,00 USD).

[![Exemplo de depreciação de ativos fixos](./media/Fixed_asset_Disposal_scrap_scenario_2.png)](./media/Fixed_asset_Disposal_scrap_scenario_2.png)


Para criar um diário de descarte, vá para **Ativos fixos \> Entradas de diário \> Diário de ativos fixos** e, no Painel de Ação, selecione **Linhas**. Selecione **Alienação – sucata** e selecione a ID de ativo fixo. Para descartar totalmente o ativo, não insira valores nos campos **Débito** ou **Crédito**.

[![Diário de ativos fixos](./media/Fixed_asset_Disposal_scrap_scenario_3.png)](./media/Fixed_asset_Disposal_scrap_scenario_3.png)

A transação de sucata de descarte de ativo fixo altera os valores de campos do registro dos ativos fixos das seguintes maneiras:

- Na seção **Saldo** , o campo **Status** é atualizado para **Sucateado**.
- Na seção **Emissão**, o campo **Data de alienação** é definido com a data em que o ativo foi sucateado.

[![Detalhe do diário de ativos fixos](./media/Fixed_asset_Disposal_scrap_scenario_4.png)](./media/Fixed_asset_Disposal_scrap_scenario_4.png)

A ilustração a seguir mostra o saldo de ativos fixos.

[![Saldo de ativos fixos](./media/Fixed_asset_Disposal_scrap_scenario_5.png)](./media/Fixed_asset_Disposal_scrap_scenario_5.png)

A ilustração a seguir mostra o comprovante que é lançado.

[![Valor líquido contábil](./media/Fixed_asset_Disposal_scrap_scenario_6.png)](./media/Fixed_asset_Disposal_scrap_scenario_6.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
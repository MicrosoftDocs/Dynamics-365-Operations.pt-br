---
title: Descartar um ativo fixo como sucata
description: O tópico descreve o processo de eliminação de transações de um ativo fixo que foi descartado como sucata.
author: moaamer
manager: Ann Beebe
ms.date: 08/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-14
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 371cc2efa64916698da8e4230825c3c949920698
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3975235"
---
# <a name="dispose-of-a-fixed-asset-as-scrap"></a><span data-ttu-id="688b0-103">Descartar um ativo fixo como sucata</span><span class="sxs-lookup"><span data-stu-id="688b0-103">Dispose of a fixed asset as scrap</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="688b0-104">O tópico descreve o processo de eliminação de transações de um ativo fixo que foi descartado como sucata.</span><span class="sxs-lookup"><span data-stu-id="688b0-104">The topic describes the process of eliminating transactions for a fixed asset that was disposed of as scrap.</span></span> <span data-ttu-id="688b0-105">Os tipos de transação que podem ser eliminados incluem transações depreciação acumulada e aquisição de um ativo, além de outras transações de ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="688b0-105">The transaction types that can be eliminated include an asset's acquisition and accumulated depreciation transactions and other fixed asset transactions.</span></span> <span data-ttu-id="688b0-106">A eliminação dessas transações afeta as contas de balanço, como contas de ajuste de aquisição, ajuste de depreciação, reavaliação, valorização e desvalorização.</span><span class="sxs-lookup"><span data-stu-id="688b0-106">Elimination of these transactions affects balance sheet accounts, such as acquisition adjustment, depreciation adjustment, revaluation, write-up, and write-down accounts.</span></span>

| <span data-ttu-id="688b0-107">Transação</span><span class="sxs-lookup"><span data-stu-id="688b0-107">Transaction</span></span>                                         | <span data-ttu-id="688b0-108">Débito (Dr.)</span><span class="sxs-lookup"><span data-stu-id="688b0-108">Debit (Dr.)</span></span> | <span data-ttu-id="688b0-109">Crédito (Cr.)</span><span class="sxs-lookup"><span data-stu-id="688b0-109">Credit (Cr.)</span></span> |
|-----------------------------------------------------|-------------|--------------|
| <span data-ttu-id="688b0-110">Dr. Depreciação acumulada</span><span class="sxs-lookup"><span data-stu-id="688b0-110">Dr. Accumulated depreciation</span></span>                        | <span data-ttu-id="688b0-111">X</span><span class="sxs-lookup"><span data-stu-id="688b0-111">X</span></span>           |              |
| <span data-ttu-id="688b0-112">Cr. Ganho/perda de ativos fixos</span><span class="sxs-lookup"><span data-stu-id="688b0-112">Cr. Fixed assets gain/loss</span></span>                          |             | <span data-ttu-id="688b0-113">X</span><span class="sxs-lookup"><span data-stu-id="688b0-113">X</span></span>            |
| <span data-ttu-id="688b0-114">Dr. Ganho/perda de ativos fixos</span><span class="sxs-lookup"><span data-stu-id="688b0-114">Dr. Fixed assets gain/loss</span></span>                          | <span data-ttu-id="688b0-115">X</span><span class="sxs-lookup"><span data-stu-id="688b0-115">X</span></span>           |              |
| <span data-ttu-id="688b0-116">Cr. Conta de aquisição de ativos fixos</span><span class="sxs-lookup"><span data-stu-id="688b0-116">Cr. Fixed asset acquisition account</span></span>                 |             | <span data-ttu-id="688b0-117">X</span><span class="sxs-lookup"><span data-stu-id="688b0-117">X</span></span>            |
| <span data-ttu-id="688b0-118">Dr. Ganho/perda de ativos fixos (valor líquido contábil \[NBV\])</span><span class="sxs-lookup"><span data-stu-id="688b0-118">Dr. Fixed assets gain/loss (net book value \[NBV\])</span></span> | <span data-ttu-id="688b0-119">X</span><span class="sxs-lookup"><span data-stu-id="688b0-119">X</span></span>           |              |
| <span data-ttu-id="688b0-120">Cr. Ganho/perda de ativos fixos (NBV)</span><span class="sxs-lookup"><span data-stu-id="688b0-120">Cr. Fixed assets gain/loss (NBV)</span></span>                    |             | <span data-ttu-id="688b0-121">X</span><span class="sxs-lookup"><span data-stu-id="688b0-121">X</span></span>            |

> [!NOTE]
> <span data-ttu-id="688b0-122">Recomendamos que você trabalhe de perto com o diretor financeiro (CFO) ou controlador da empresa para identificar as contas corretas que devem ser usadas para cada tipo de transação e também para confirmar que o processo de descarte e as transações que ele gera atualizam essas as contas corretamente.</span><span class="sxs-lookup"><span data-stu-id="688b0-122">We recommend that you work closely with your company's chief financial officer (CFO) or controller to identify the correct accounts that should be used for each transaction type, and also to verify that the disposal process and the transactions that it generates update those accounts correctly.</span></span>

<span data-ttu-id="688b0-123">Antes de descartar um ativo fixo como sucata, é necessário criar as contas contábeis associadas com o valor de aquisição do ativo, a depreciação do ano atual, a depreciação dos anos anteriores e o NBV do ativo.</span><span class="sxs-lookup"><span data-stu-id="688b0-123">Before you dispose of a fixed asset as scrap, you must create ledger accounts that are associated with the asset's acquisition value, depreciation for the current year, depreciation for previous years, and the asset's NBV.</span></span> <span data-ttu-id="688b0-124">Os tipos de transação de ativo fixo estão listados na página **Perfis de lançamentos de ativo fixo** .</span><span class="sxs-lookup"><span data-stu-id="688b0-124">The fixed asset transaction types are listed on the **Fixed assets posting profile** page.</span></span> <span data-ttu-id="688b0-125">Vá para **Ativos fixos \> Configuração \> Perfis de lançamentos de ativo fixo** e, na Guia Rápida **Alienação**, selecione **Sucata** no campo acima da grade.</span><span class="sxs-lookup"><span data-stu-id="688b0-125">Go to **Fixed assets \> Setup \> Fixed asset posting profiles**, and then, on the **Disposal** FastTab, select **Scrap** in the field above the grid.</span></span> <span data-ttu-id="688b0-126">A ilustração a seguir mostra a lista de tipos de transação de ativo fixo na página **Perfis de lançamentos de ativo fixo** .</span><span class="sxs-lookup"><span data-stu-id="688b0-126">The following illustration shows the list of fixed asset transaction types on the **Fixed asset posting profiles** page.</span></span>


<span data-ttu-id="688b0-127">[![Descarte de um ativo fixo como sucata, Fig. 1.](./media/Fixed_asset_Disposal_scrap_scenario_1.png)](./media/Fixed_asset_Disposal_scrap_scenario_1.png)</span><span class="sxs-lookup"><span data-stu-id="688b0-127">[![Disposing of an asset as scap, Fig. 1](./media/Fixed_asset_Disposal_scrap_scenario_1.png)](./media/Fixed_asset_Disposal_scrap_scenario_1.png)</span></span>

<span data-ttu-id="688b0-128">Para o exemplo a seguir, um ativo fixo for adquirido em 1º de janeiro de 2018 e será sucateado em 31 de março de 2019.</span><span class="sxs-lookup"><span data-stu-id="688b0-128">For the following example, a fixed asset was acquired on January 1, 2018, and it will be scrapped on March 31, 2019.</span></span>

- <span data-ttu-id="688b0-129">**Preço de aquisição:** 24.000,00 dólares americanos (USD)</span><span class="sxs-lookup"><span data-stu-id="688b0-129">**Acquisition price:** 24,000.00 US dollars (USD)</span></span>
- <span data-ttu-id="688b0-130">**Vida útil:** 2 anos</span><span class="sxs-lookup"><span data-stu-id="688b0-130">**Service life:** Two years</span></span>
- <span data-ttu-id="688b0-131">**Método de depreciação:** Vida útil linear</span><span class="sxs-lookup"><span data-stu-id="688b0-131">**Depreciation method:** Straight line service life</span></span>
- <span data-ttu-id="688b0-132">**Valor de depreciação:** 1.000,00 USD por mês</span><span class="sxs-lookup"><span data-stu-id="688b0-132">**Depreciation amount:** 1,000.00 USD per month</span></span>

<span data-ttu-id="688b0-133">O NBV de um ativo fixo é calculado usando a seguinte fórmula:</span><span class="sxs-lookup"><span data-stu-id="688b0-133">The NBV of a fixed asset is calculated by using the following formula:</span></span>

<span data-ttu-id="688b0-134">Valor líquido contábil = preço de aquisição – depreciação</span><span class="sxs-lookup"><span data-stu-id="688b0-134">Net book value = Acquisition price – Depreciation</span></span>

<span data-ttu-id="688b0-135">Neste exemplo, o ativo fixo foi adquirido e depreciado por 15 meses, de janeiro de 2018 até março de 2019.</span><span class="sxs-lookup"><span data-stu-id="688b0-135">In this example, the fixed asset was acquired and was depreciated for 15 months, from January 2018 through March 2019.</span></span> <span data-ttu-id="688b0-136">Portanto, o NBV do ativo é 9.000,00 USD (24.000,00 USD – 15.000,00 USD).</span><span class="sxs-lookup"><span data-stu-id="688b0-136">Therefore, the asset's NBV is 9,000.00 USD (24,000.00 USD – 15,000.00 USD).</span></span>

<span data-ttu-id="688b0-137">[![Exemplo de depreciação de ativos fixos](./media/Fixed_asset_Disposal_scrap_scenario_2.png)](./media/Fixed_asset_Disposal_scrap_scenario_2.png)</span><span class="sxs-lookup"><span data-stu-id="688b0-137">[![Fixed asset depreciation example](./media/Fixed_asset_Disposal_scrap_scenario_2.png)](./media/Fixed_asset_Disposal_scrap_scenario_2.png)</span></span>


<span data-ttu-id="688b0-138">Para criar um diário de descarte, vá para **Ativos fixos \> Entradas de diário \> Diário de ativos fixos** e, no Painel de Ação, selecione **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="688b0-138">To create a disposal journal, go to **Fixed assets \> Journal entries \> Fixed assets journal**, and then, on the Action Pane, select **Lines**.</span></span> <span data-ttu-id="688b0-139">Selecione **Alienação – sucata** e selecione a ID de ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="688b0-139">Select **Disposal – scrap**, and then select a fixed asset ID.</span></span> <span data-ttu-id="688b0-140">Para descartar totalmente o ativo, não insira valores nos campos **Débito** ou **Crédito**.</span><span class="sxs-lookup"><span data-stu-id="688b0-140">To fully dispose of the asset, don't enter a value in either the **Debit** field or the **Credit** field.</span></span>

<span data-ttu-id="688b0-141">[![Diário de ativos fixos](./media/Fixed_asset_Disposal_scrap_scenario_3.png)](./media/Fixed_asset_Disposal_scrap_scenario_3.png)</span><span class="sxs-lookup"><span data-stu-id="688b0-141">[![Fixed assets journal](./media/Fixed_asset_Disposal_scrap_scenario_3.png)](./media/Fixed_asset_Disposal_scrap_scenario_3.png)</span></span>

<span data-ttu-id="688b0-142">A transação de sucata de descarte de ativo fixo altera os valores de campos do registro dos ativos fixos das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="688b0-142">The fixed asset disposal scrap transaction changes the field values for the fixed asset book in the following ways:</span></span>

- <span data-ttu-id="688b0-143">Na seção **Saldo** , o campo **Status** é atualizado para **Sucateado**.</span><span class="sxs-lookup"><span data-stu-id="688b0-143">In the **Balance** section, the **Status** field is updated to **Scrapped**.</span></span>
- <span data-ttu-id="688b0-144">Na seção **Emissão**, o campo **Data de alienação** é definido com a data em que o ativo foi sucateado.</span><span class="sxs-lookup"><span data-stu-id="688b0-144">In the **Issue** section, the **Disposal date** field is set to the date when the asset was scrapped.</span></span>

<span data-ttu-id="688b0-145">[![Detalhe do diário de ativos fixos](./media/Fixed_asset_Disposal_scrap_scenario_4.png)](./media/Fixed_asset_Disposal_scrap_scenario_4.png)</span><span class="sxs-lookup"><span data-stu-id="688b0-145">[![Fixed assets journal detail](./media/Fixed_asset_Disposal_scrap_scenario_4.png)](./media/Fixed_asset_Disposal_scrap_scenario_4.png)</span></span>

<span data-ttu-id="688b0-146">A ilustração a seguir mostra o saldo de ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="688b0-146">The following illustration shows the fixed asset balance.</span></span>

<span data-ttu-id="688b0-147">[![Saldo de ativos fixos](./media/Fixed_asset_Disposal_scrap_scenario_5.png)](./media/Fixed_asset_Disposal_scrap_scenario_5.png)</span><span class="sxs-lookup"><span data-stu-id="688b0-147">[![Fixed asset balance](./media/Fixed_asset_Disposal_scrap_scenario_5.png)](./media/Fixed_asset_Disposal_scrap_scenario_5.png)</span></span>

<span data-ttu-id="688b0-148">A ilustração a seguir mostra o comprovante que é lançado.</span><span class="sxs-lookup"><span data-stu-id="688b0-148">The following illustration shows the voucher that is posted.</span></span>

<span data-ttu-id="688b0-149">[![Valor líquido contábil](./media/Fixed_asset_Disposal_scrap_scenario_6.png)](./media/Fixed_asset_Disposal_scrap_scenario_6.png)</span><span class="sxs-lookup"><span data-stu-id="688b0-149">[![Net book value](./media/Fixed_asset_Disposal_scrap_scenario_6.png)](./media/Fixed_asset_Disposal_scrap_scenario_6.png)</span></span>

---
title: "Liberar linhas de BOM e fórmula para o depósito"
description: "Este tópico descreve o processo para liberar matéria-prima para linhas de BOM e linhas de fórmula para o depósito."
author: johanhoffmann
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.search.region: Global
ms.author: johanho
ms.search.validfrom: 2017-12-31
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: ceea24519d641c676521771cee274feb64ca7783
ms.openlocfilehash: 555484e3c54951594f7f8f738bb0e0fd386ee486
ms.contentlocale: pt-br
ms.lasthandoff: 01/19/2018

---

# <a name="release-bom-and-formula-lines-to-the-warehouse"></a><span data-ttu-id="4b2ab-103">Liberar linhas de BOM e fórmula para o depósito</span><span class="sxs-lookup"><span data-stu-id="4b2ab-103">Release BOM and formula lines to the warehouse</span></span>

<span data-ttu-id="4b2ab-104">Este tópico descreve o processo para liberar matéria-prima para linhas de BOM e linhas de fórmula para o depósito.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-104">This topic describes the process for releasing raw material for bill of materials (BOM) lines and formula lines to the warehouse.</span></span> <span data-ttu-id="4b2ab-105">Quando você libera uma linha da BOM e da fórmula para o depósito, o sistema determina primeiro se o material já está disponível no local de entrada de produção no chão de fábrica em que o material será consumido para o processo de produção.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-105">When you release a BOM or formula line to the warehouse, the system first determines whether material is already available at the production input location on the shop floor where the material will be consumed for the production process.</span></span>

- <span data-ttu-id="4b2ab-106">Se o material estiver disponível no local de entrada de produção, é separado desse local imediatamente após o sinal ser fornecido para a liberação do material para o depósito.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-106">If the material is available at the production input location, it's picked from that location immediately after the signal is given for the release of material to the warehouse.</span></span>
- <span data-ttu-id="4b2ab-107">Se o material não estiver disponível no local de entrada de produção, a liberação do material indique que o material deve ser movido de locais do depósito para o local de entrada de produção.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-107">If the material isn't available at the production input location, the material release indicates that material must be moved from locations in the warehouse to the production input location.</span></span> <span data-ttu-id="4b2ab-108">O material é movido através do trabalho de depósito para separação de matérias-primas.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-108">The material is moved via warehouse work for raw material picking.</span></span> <span data-ttu-id="4b2ab-109">Portanto, os processos de depósito para a separação de matérias-primas deverão ser configurados.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-109">Therefore, warehouse processes for raw material picking must be configured.</span></span> <span data-ttu-id="4b2ab-110">Para obter mais informações, consulte [Reabastecimento](../warehousing/replenishment.md) e [Controlar o trabalho do depósito por meio de modelos de trabalho e diretivas de localização](../warehousing/control-warehouse-location-directives.md).</span><span class="sxs-lookup"><span data-stu-id="4b2ab-110">For more information, see [Replenishment](../warehousing/replenishment.md) and [Control warehouse work by using work templates and location directives](../warehousing/control-warehouse-location-directives.md).</span></span>

## <a name="methods-for-releasing-bom-and-formula-lines"></a><span data-ttu-id="4b2ab-111">Métodos para liberar linhas da BOM e da fórmula</span><span class="sxs-lookup"><span data-stu-id="4b2ab-111">Methods for releasing BOM and formula lines</span></span>

<span data-ttu-id="4b2ab-112">Você pode configurar linhas da BOM e da fórmula de forma que isso ocorra como parte da liberação de uma ordem de produção ou de lote.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-112">You can configure the release of BOM and formula lines so that it occurs as part of the release of a production order or batch order.</span></span> <span data-ttu-id="4b2ab-113">Se preferir, a versão pode ser controlada por um trabalho em lotes ou ser feita como uma interação manual.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-113">Alternatively, the release can be controlled by a batch job or done as a manual interaction.</span></span>

<span data-ttu-id="4b2ab-114">O método usado para liberar linhas da BOM e da fórmula é controlado pelo parâmetro **Liberação da linha de produção**.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-114">The method that is used to release BOM and formula lines is controlled by the **Production line release** parameter.</span></span> <span data-ttu-id="4b2ab-115">Você pode localizar este parâmetro em **Controle de produção** \> **Configuração** \> **Parâmetros de produção**.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-115">You can find this parameter at **Production control** \> **Setup** \> **Production parameters**.</span></span>

- <span data-ttu-id="4b2ab-116">**Liberar linhas da BOM e da fórmula como parte da liberação de uma ordem de produção ou de lote** – Neste método, as linhas da BOM e da fórmula de uma ordem de produção ou de lote são liberadas como parte do processo de liberação da ordem.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-116">**Release BOM and formula lines as part of production or batch order release** – In this method, BOM and formula lines for a production or batch order are released as part of the process of releasing the order.</span></span> <span data-ttu-id="4b2ab-117">Geralmente, durante a liberação de uma ordem de produção ou de lote, os trabalhos de produção são liberados a trabalhadores de chão de fábrica e os documentos de produção são impressos.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-117">Usually, during the release of a production or batch order, production jobs are released to the shop floor workers, and production papers are printed.</span></span> <span data-ttu-id="4b2ab-118">Durante esse processo, o status da ordem também muda para **Liberado**.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-118">During this process, the status of the order is also changed to **Released**.</span></span>
- <span data-ttu-id="4b2ab-119">**Liberar linhas da BOM e da fórmula por meio de um trabalho em lotes ou como uma interação manual** – Neste método, as linhas da BOM e da fórmula podem ser liberadas apenas através do trabalho em lotes **Versão automática das linhas da BOM e da fórmula** ou como uma interação manual.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-119">**Release BOM and formula lines via a batch job or as a manual interaction** – In this method, BOM and formula lines can be released only through the **Automatic release of BOM and formula lines** batch job or as a manual interaction.</span></span> <span data-ttu-id="4b2ab-120">Para liberar manualmente as linhas da BOM e da fórmula, a página de listagem da ordem de produção ou de detalhes da ordem de produção, no painel de ações, selecione **Liberar para o depósito**.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-120">To manually release BOM and formula lines, on the production order list page or the production order details page, on the Action Pane, select **Release to warehouse**.</span></span>

## <a name="releasing-the-bom-and-formula-lines-by-using-a-batch-job"></a><span data-ttu-id="4b2ab-121">Liberando as linhas da BOM e da fórmula usando um trabalho em lotes</span><span class="sxs-lookup"><span data-stu-id="4b2ab-121">Releasing the BOM and formula lines by using a batch job</span></span>

<span data-ttu-id="4b2ab-122">Os trabalhos em lotes da **Liberação automática das linhas da BOM e da fórmula** são feitos por meio das linhas da BOM e da fórmula selecionadas que têm uma quantidade restante para liberar.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-122">The **Automatic release of BOM and formula lines** batch job goes through selected BOM and formula lines that have a remaining quantity to release.</span></span> <span data-ttu-id="4b2ab-123">Os trabalhos consideram somente ordens que têm um status **Liberado**, **Iniciado** ou **Informado como concluído**.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-123">The job considers only orders that have a status of **Released**, **Started**, or **Reported as finished**.</span></span> <span data-ttu-id="4b2ab-124">Se uma linha da BOM ou da fórmula tiver uma quantidade restante para liberar, o trabalho libera a quantidade que pode ser coberta pela quantidade que já foi reservada fisicamente e a quantidade que está disponível fisicamente.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-124">If a BOM or formula line has a remaining quantity to release, the job releases up to the quantity that can be covered by the quantity that has already been physically reserved and the quantity that is physically available.</span></span>

### <a name="example-of-a-batch-job-release"></a><span data-ttu-id="4b2ab-125">Exemplo de uma liberação de trabalho em lote</span><span class="sxs-lookup"><span data-stu-id="4b2ab-125">Example of a batch job release</span></span>

| <span data-ttu-id="4b2ab-126">Cenário</span><span class="sxs-lookup"><span data-stu-id="4b2ab-126">Scenario</span></span> | <span data-ttu-id="4b2ab-127">Quantidade restante a ser liberada</span><span class="sxs-lookup"><span data-stu-id="4b2ab-127">Remaining quantity to release</span></span> | <span data-ttu-id="4b2ab-128">Quantidade reservada fisicamente</span><span class="sxs-lookup"><span data-stu-id="4b2ab-128">Physically reserved quantity</span></span> | <span data-ttu-id="4b2ab-129">Quantidade disponível fisicamente</span><span class="sxs-lookup"><span data-stu-id="4b2ab-129">Physically available quantity</span></span> | <span data-ttu-id="4b2ab-130">Quantidade liberada pelo trabalho em lotes</span><span class="sxs-lookup"><span data-stu-id="4b2ab-130">Quantity released by the batch job</span></span> |
|----------|-------------------------------|------------------------------|-------------------------------|------------------------------------|
| <span data-ttu-id="4b2ab-131">1</span><span class="sxs-lookup"><span data-stu-id="4b2ab-131">1</span></span>        | <span data-ttu-id="4b2ab-132">100</span><span class="sxs-lookup"><span data-stu-id="4b2ab-132">100</span></span>                           | <span data-ttu-id="4b2ab-133">20</span><span class="sxs-lookup"><span data-stu-id="4b2ab-133">20</span></span>                           | <span data-ttu-id="4b2ab-134">90</span><span class="sxs-lookup"><span data-stu-id="4b2ab-134">90</span></span>                            | <span data-ttu-id="4b2ab-135">100</span><span class="sxs-lookup"><span data-stu-id="4b2ab-135">100</span></span>                                |
| <span data-ttu-id="4b2ab-136">2</span><span class="sxs-lookup"><span data-stu-id="4b2ab-136">2</span></span>        | <span data-ttu-id="4b2ab-137">100</span><span class="sxs-lookup"><span data-stu-id="4b2ab-137">100</span></span>                           | <span data-ttu-id="4b2ab-138">20</span><span class="sxs-lookup"><span data-stu-id="4b2ab-138">20</span></span>                           | <span data-ttu-id="4b2ab-139">70</span><span class="sxs-lookup"><span data-stu-id="4b2ab-139">70</span></span>                            | <span data-ttu-id="4b2ab-140">90</span><span class="sxs-lookup"><span data-stu-id="4b2ab-140">90</span></span>                                 |
| <span data-ttu-id="4b2ab-141">3</span><span class="sxs-lookup"><span data-stu-id="4b2ab-141">3</span></span>        | <span data-ttu-id="4b2ab-142">100</span><span class="sxs-lookup"><span data-stu-id="4b2ab-142">100</span></span>                           | <span data-ttu-id="4b2ab-143">0</span><span class="sxs-lookup"><span data-stu-id="4b2ab-143">0</span></span>                            | <span data-ttu-id="4b2ab-144">90</span><span class="sxs-lookup"><span data-stu-id="4b2ab-144">90</span></span>                            | <span data-ttu-id="4b2ab-145">90</span><span class="sxs-lookup"><span data-stu-id="4b2ab-145">90</span></span>                                 |
| <span data-ttu-id="4b2ab-146">4</span><span class="sxs-lookup"><span data-stu-id="4b2ab-146">4</span></span>        | <span data-ttu-id="4b2ab-147">100</span><span class="sxs-lookup"><span data-stu-id="4b2ab-147">100</span></span>                           | <span data-ttu-id="4b2ab-148">0</span><span class="sxs-lookup"><span data-stu-id="4b2ab-148">0</span></span>                            | <span data-ttu-id="4b2ab-149">110</span><span class="sxs-lookup"><span data-stu-id="4b2ab-149">110</span></span>                           | <span data-ttu-id="4b2ab-150">100</span><span class="sxs-lookup"><span data-stu-id="4b2ab-150">100</span></span>                                |
| <span data-ttu-id="4b2ab-151">5</span><span class="sxs-lookup"><span data-stu-id="4b2ab-151">5</span></span>        | <span data-ttu-id="4b2ab-152">100</span><span class="sxs-lookup"><span data-stu-id="4b2ab-152">100</span></span>                           | <span data-ttu-id="4b2ab-153">20</span><span class="sxs-lookup"><span data-stu-id="4b2ab-153">20</span></span>                           | <span data-ttu-id="4b2ab-154">0</span><span class="sxs-lookup"><span data-stu-id="4b2ab-154">0</span></span>                             | <span data-ttu-id="4b2ab-155">20</span><span class="sxs-lookup"><span data-stu-id="4b2ab-155">20</span></span>                                 |

### <a name="batch-job-setup"></a><span data-ttu-id="4b2ab-156">Configuração de trabalho em lotes</span><span class="sxs-lookup"><span data-stu-id="4b2ab-156">Batch job setup</span></span>

<span data-ttu-id="4b2ab-157">Na consulta do trabalho em lotes **Liberação automática das linhas da BOM e da fórmula**, você pode configurar um critério de filtragem para especificar quantos dias depois o trabalho deve procurar por linhas que têm quantidades não liberadas.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-157">In the query for the **Automatic release of BOM and formula lines** batch job, you can set up a filter criterion to specify how many days ahead the job should look for lines that have unreleased quantities.</span></span> <span data-ttu-id="4b2ab-158">Na consulta do trabalho, no campo **Data da matéria-prima**, use a função **(LessThanDate())** como um critério de filtragem.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-158">In the query for the job, in the **Raw material date** field, use the **(LessThanDate())** function as a filter criterion.</span></span>

<span data-ttu-id="4b2ab-159">A ilustração a seguir mostra uma ordem de produção que tem dois trabalhos, 10 e 20, que abrange a montagem e embalagem da ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-159">The following illustration shows a production order that has two jobs, 10 and 20, that cover the assembly and packing for the production order.</span></span> <span data-ttu-id="4b2ab-160">Cada trabalho é configurado para consumir uma quantidade de material.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-160">Each job is set up to consume a quantity of material.</span></span> <span data-ttu-id="4b2ab-161">Nesta ilustração, o limite de tempo de liberação que é indicada pela seta verde abaixo da linha do tempo é igual ao número de dias que foi especificado no critério **(LessThanDate())**.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-161">In this illustration, the release time fence that is indicated by the green arrow below the time line equals the number of days that has been specified in the **(LessThanDate())** criterion.</span></span> <span data-ttu-id="4b2ab-162">Por exemplo, **(LessThanDate (2))** indica que o trabalho deverá procurar quantidades não liberadas somente dentro de um limite de tempo de dois dias.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-162">For example, **(LessThanDate(2))** indicates that the job should look for unreleased quantities only within a time fence of two days.</span></span>

![Exemplo de uma ordem de produção que tem dois trabalhos em lote](media/bach-job-setup.PNG)

## <a name="releasing-material-per-operation-number-or-in-proportion-to-the-amount-of-finished-goods"></a><span data-ttu-id="4b2ab-164">Liberando material por número de operação ou em relação ao valor de mercadorias acabadas</span><span class="sxs-lookup"><span data-stu-id="4b2ab-164">Releasing material per operation number or in proportion to the amount of finished goods</span></span>

<span data-ttu-id="4b2ab-165">Se você liberar materiais usando a definição do parâmetro **Na liberação da ordem de produção**, quando você faz a liberação manual, você tem duas opções para controlar a liberação do material:</span><span class="sxs-lookup"><span data-stu-id="4b2ab-165">If you release materials by using the **On production order release** parameter setting, when you do a manual release, you have two options for controlling the material release:</span></span>

- <span data-ttu-id="4b2ab-166">Liberar material por número de operação.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-166">Release material per operation number.</span></span>
- <span data-ttu-id="4b2ab-167">Liberar material em relação ao valor de mercadorias acabadas.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-167">Release material in proportion to the amount of finished goods.</span></span>

### <a name="release-material-per-operation-number"></a><span data-ttu-id="4b2ab-168">Liberar material por número de operação</span><span class="sxs-lookup"><span data-stu-id="4b2ab-168">Release material per operation number</span></span>

<span data-ttu-id="4b2ab-169">Para controlar as operações nas quais o material deve ser liberado, use a página **Liberar para o depósito**.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-169">To control the operations that material should be released to, use the **Release to warehouse** page.</span></span>

- <span data-ttu-id="4b2ab-170">Selecione **Controle de produção** \> **Ordens de produção** \> **Todas as ordens de produção**, selecione uma ordem de produção e na guia **Depósito**, selecione **Liberar para o depósito**.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-170">Select **Production control** \> **Production orders** \> **All production orders**, select a production order, and then, on the **Warehouse** tab, select **Release to warehouse**.</span></span> <span data-ttu-id="4b2ab-171">Depois use os campos **Da Oper. N°**</span><span class="sxs-lookup"><span data-stu-id="4b2ab-171">Then use the **From Oper. No.**</span></span> <span data-ttu-id="4b2ab-172">e **Para Oper. N°** para especificar a faixa de números da operação.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-172">and **To Oper. No** fields to specify the range of operation numbers.</span></span>

<span data-ttu-id="4b2ab-173">A ilustração a seguir mostra uma ordem de produção que tem duas operações, 10 e 20.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-173">The following illustration shows a production order that has two operations, 10 and 20.</span></span> <span data-ttu-id="4b2ab-174">Neste exemplo, se você limitar a liberação para operação 10, somente o material M9203 será liberado.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-174">In this example, if you limit the release to operation 10, only material M9203 will be released.</span></span>

![Exemplo da liberação de material por número da operação](media/two-operations.PNG)

### <a name="release-material-in-proportion-to-the-amount-of-finished-goods"></a><span data-ttu-id="4b2ab-176">Liberar material em relação ao valor de mercadorias acabadas</span><span class="sxs-lookup"><span data-stu-id="4b2ab-176">Release material in proportion to the amount of finished goods</span></span>

<span data-ttu-id="4b2ab-177">Você pode liberar a matéria-prima para uma quantidade parcial de mercadorias concluídas ou em uma unidade específica.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-177">You can release raw material for a partial quantity of finished goods or in a specific unit.</span></span>

- <span data-ttu-id="4b2ab-178">Para liberar a matéria-prima para uma quantidade parcial de mercadorias acabadas, selecione **Controle de produção** \> **Ordens de produção** \> **Todas as ordens de produção**, selecione uma ordem de produção e na guia **Depósito**, selecione **Liberar para depósito**.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-178">To release raw material for a partial quantity of finished goods, select **Production control** \> **Production orders** \> **All production orders**, select a production order, and then, on the **Warehouse** tab, select **Release to warehouse**.</span></span> <span data-ttu-id="4b2ab-179">Insira a quantidade no campo **Quantidade**.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-179">Then enter a quantity in the **Quantity** field.</span></span>

    <span data-ttu-id="4b2ab-180">Por exemplo, uma ordem de produção é criada e planejada para 1,000 peças (pcs.).</span><span class="sxs-lookup"><span data-stu-id="4b2ab-180">For example, a production order is created and scheduled for 1,000 pieces (pcs.).</span></span> <span data-ttu-id="4b2ab-181">O supervisor do chão de fábrica está planejando a produção de 100 peças</span><span class="sxs-lookup"><span data-stu-id="4b2ab-181">The shop floor supervisor is planning the production of 100 pcs.</span></span> <span data-ttu-id="4b2ab-182">para o próximo turno e quer liberar materiais somente para esse turno.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-182">for the next shift and wants to release materials only for that shift.</span></span> <span data-ttu-id="4b2ab-183">Neste caso, o supervisor pode usar o campo **Quantidade** para liberar os materiais de 100 peças</span><span class="sxs-lookup"><span data-stu-id="4b2ab-183">In this case, the supervisor can use the **Quantity** field to release materials for the 100 pcs.</span></span> <span data-ttu-id="4b2ab-184">isso está planejado para próximo turno.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-184">that are planned for the next shift.</span></span>

- <span data-ttu-id="4b2ab-185">Para liberar matéria-prima em uma unidade específica, selecione **Controle de produção** \> **Ordens de produção** \> **Todas as ordens de produção**, selecione uma ordem de produção e na guia **Depósito**, selecione **Liberar para depósito**.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-185">To release raw material in a specific unit, select **Production control** \> **Production orders** \> **All production orders**, select a production order, and then, on the **Warehouse** tab, select **Release to warehouse**.</span></span> <span data-ttu-id="4b2ab-186">Use o campo **Unidade** para selecionar a unidade de mercadoria acabada na qual será liberado o material.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-186">Then use the **Unit** field to select the unit of the finished good to release material in.</span></span>

    <span data-ttu-id="4b2ab-187">As unidades disponíveis estão definidas no ID do grupo de sequências da unidade da mercadoria acabada.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-187">The units that are available are defined in the unit sequence group ID of the finished good.</span></span>

    <span data-ttu-id="4b2ab-188">Por exemplo, uma mercadoria acabada tem a seguinte conversão de unidades entre as libras (lbs.) e o palete (PL): 1 PL = 100 libras.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-188">For example, a finished good has the following unit conversion between pounds (lbs.) and pallet (PL): 1 PL = 100 lbs.</span></span> <span data-ttu-id="4b2ab-189">Para criar uma ordem de produção para 10.000 libras</span><span class="sxs-lookup"><span data-stu-id="4b2ab-189">To create a production order for 10,000 lbs.</span></span> <span data-ttu-id="4b2ab-190">das mercadorias acabadas, você pode liberar matérias-primas para o número de paletes que você pretende produzir.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-190">of the finished good, you can release raw materials for the number of pallets that you plan to produce.</span></span> <span data-ttu-id="4b2ab-191">Selecione **PL** como a unidade e um número correspondente no campo **Quantidade**.</span><span class="sxs-lookup"><span data-stu-id="4b2ab-191">Select **PL** as the unit, and then select a corresponding number in the **Quantity** field.</span></span>

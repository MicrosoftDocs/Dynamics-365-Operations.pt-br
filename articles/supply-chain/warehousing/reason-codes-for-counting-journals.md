---
title: Códigos de motivo de contagem de estoque
description: Este tópico descreve como configurar e aplicar códigos de motivo para tarefas de contagem.
author: Mirzaab
manager: tfehr
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCountingReasonCodePolicy, InventCountingReasonCode
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: d72b171bfe149b25f5055d5bebef85b49e952295
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5228480"
---
# <a name="reason-codes-for-inventory-counting"></a><span data-ttu-id="39ccc-103">Códigos de motivo de contagem de estoque</span><span class="sxs-lookup"><span data-stu-id="39ccc-103">Reason codes for inventory counting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="39ccc-104">Os códigos de motivo permitem analisar os resultados de um processo de contagem e quaisquer discrepâncias que ocorrem durante esse processo.</span><span class="sxs-lookup"><span data-stu-id="39ccc-104">Reason codes let you analyze the results of a counting process and any discrepancies that occur during that process.</span></span> <span data-ttu-id="39ccc-105">Você pode especificar o motivo da contagem como um palete quebrado ou um ajuste de estoque que é baseado nas amostras de estoque.</span><span class="sxs-lookup"><span data-stu-id="39ccc-105">You can specify the reason for doing the count, such as a broken pallet or a stock adjustment that is based on inventory samples.</span></span>

## <a name="recommendation"></a><span data-ttu-id="39ccc-106">Recomendação</span><span class="sxs-lookup"><span data-stu-id="39ccc-106">Recommendation</span></span>

<span data-ttu-id="39ccc-107">Antes de você configurar o sistema, recomendamos que você defina uma estratégia para trabalhar com códigos de motivo.</span><span class="sxs-lookup"><span data-stu-id="39ccc-107">Before you set up the system, we recommend that you define a strategy for working with reason codes.</span></span> <span data-ttu-id="39ccc-108">Por exemplo, tente responder às seguintes questões:</span><span class="sxs-lookup"><span data-stu-id="39ccc-108">For example, try to answer the following questions:</span></span>

- <span data-ttu-id="39ccc-109">Os códigos de motivos devem ser obrigatórios nos depósitos?</span><span class="sxs-lookup"><span data-stu-id="39ccc-109">Should reason codes be mandatory on warehouses?</span></span>
- <span data-ttu-id="39ccc-110">Os códigos de motivo devem ser obrigatórios ou opcionais em alguns itens?</span><span class="sxs-lookup"><span data-stu-id="39ccc-110">Should reason codes be mandatory or optional on some items?</span></span>
- <span data-ttu-id="39ccc-111">Quantos códigos de motivo você precisa?</span><span class="sxs-lookup"><span data-stu-id="39ccc-111">How many reason codes do you require?</span></span>
- <span data-ttu-id="39ccc-112">Como os usuários do scanner de código de barras usam os códigos de motivo?</span><span class="sxs-lookup"><span data-stu-id="39ccc-112">How should users of barcode scanners use reason codes?</span></span> <span data-ttu-id="39ccc-113">Os códigos de motivo devem ser pré-selecionados, obrigatórios ou não editáveis?</span><span class="sxs-lookup"><span data-stu-id="39ccc-113">Should the reason codes be preselected, mandatory, or not editable?</span></span>
- <span data-ttu-id="39ccc-114">Os funcionários do depósito precisam de código de motivo diferente nos scanners móveis?</span><span class="sxs-lookup"><span data-stu-id="39ccc-114">Do warehouse workers require different reason code behavior on mobile scanners?</span></span> <span data-ttu-id="39ccc-115">Se a resposta for sim, você pode criar mais itens de menu e atribuí-los a pessoas diferentes.</span><span class="sxs-lookup"><span data-stu-id="39ccc-115">If the answer is yes, you can create more menu items and assign them to different people.</span></span>

## <a name="where-reason-codes-apply"></a><span data-ttu-id="39ccc-116">Onde os códigos de motivo se aplicam</span><span class="sxs-lookup"><span data-stu-id="39ccc-116">Where reason codes apply</span></span>

<span data-ttu-id="39ccc-117">Você pode criar várias políticas de código de motivo e cada uma pode ter duas políticas de código de montagem de contagem.</span><span class="sxs-lookup"><span data-stu-id="39ccc-117">You can create multiple reason code policies, and each reason code policy can have two counting reason code policies.</span></span> <span data-ttu-id="39ccc-118">As políticas de código de motivo de contagem podem ser usadas para o nível de item ou o nível de depósito.</span><span class="sxs-lookup"><span data-stu-id="39ccc-118">The counting reason code policies can be used at the warehouse level or the item level.</span></span>

## <a name="set-up-reason-code-policies"></a><span data-ttu-id="39ccc-119">Configurar políticas de código de motivo</span><span class="sxs-lookup"><span data-stu-id="39ccc-119">Set up reason code policies</span></span>

1. <span data-ttu-id="39ccc-120">Selecione **Gerenciamento de estoque** \> **Configuração** \> **Estoque** \> **Políticas de código de motivo de contagem** e crie uma nova política de código de motivo.</span><span class="sxs-lookup"><span data-stu-id="39ccc-120">Select **Inventory management** \> **Setup** \> **Inventory** \> **Counting reason code policies**, and create a new reason code policy.</span></span>
2. <span data-ttu-id="39ccc-121">No campo **Tipo de código de motivo de contagem** , selecione **Obrigatório** ou **Opcional** para especificar se a seleção de um código de motivo deve ser uma ação opcional ou obrigatória em um destes diários de contagem:</span><span class="sxs-lookup"><span data-stu-id="39ccc-121">In the **Counting reason code type** field, select either **Mandatory** or **Optional** to specify whether selection of a reason code should be an optional or mandatory action in one of the following counting journals:</span></span>

    - <span data-ttu-id="39ccc-122">Contagem cíclica do (dispositivo móvel)</span><span class="sxs-lookup"><span data-stu-id="39ccc-122">Cycle Count (mobile device)</span></span>
    - <span data-ttu-id="39ccc-123">Contagem pontual (dispositivo móvel)</span><span class="sxs-lookup"><span data-stu-id="39ccc-123">Spot Count (mobile device)</span></span>
    - <span data-ttu-id="39ccc-124">Contagem do limite (dispositivo móvel)</span><span class="sxs-lookup"><span data-stu-id="39ccc-124">Threshold Count (mobile device)</span></span>
    - <span data-ttu-id="39ccc-125">Ajuste de Entrada (dispositivo móvel)</span><span class="sxs-lookup"><span data-stu-id="39ccc-125">Adjustment In (mobile device)</span></span>
    - <span data-ttu-id="39ccc-126">Ajuste de Saída (dispositivo móvel)</span><span class="sxs-lookup"><span data-stu-id="39ccc-126">Adjustment Out (mobile device)</span></span>
    - <span data-ttu-id="39ccc-127">Diário de Contagem (cliente avançado)</span><span class="sxs-lookup"><span data-stu-id="39ccc-127">Counting Journal (rich client)</span></span>

<span data-ttu-id="39ccc-128">Você também pode configurar códigos de motivo para depósitos individuais e para produtos.</span><span class="sxs-lookup"><span data-stu-id="39ccc-128">You can also set up reason codes for individual warehouses and for products.</span></span> <span data-ttu-id="39ccc-129">A configuração de código de motivo para produtos pode desconsiderar a configuração de depósitos.</span><span class="sxs-lookup"><span data-stu-id="39ccc-129">The reason code setup for products can disregard the setup for warehouses.</span></span>

## <a name="mandatory-reason-codes"></a><span data-ttu-id="39ccc-130">Códigos de motivo obrigatórios</span><span class="sxs-lookup"><span data-stu-id="39ccc-130">Mandatory reason codes</span></span>

<span data-ttu-id="39ccc-131">Se o parâmetro **Obrigatório** estiver definido na configuração de códigos de motivo para depósitos ou itens, o diário de contagem não poderá ser concluído e fechado até que um código de motivo seja fornecido.</span><span class="sxs-lookup"><span data-stu-id="39ccc-131">If the **Mandatory** parameter is set in the configuration of reason codes for warehouses or items, the counting journal can't be completed and closed until a reason code is provided.</span></span>

### <a name="set-up-reason-codes-for-warehouses"></a><span data-ttu-id="39ccc-132">Configurar códigos de motivo para depósitos</span><span class="sxs-lookup"><span data-stu-id="39ccc-132">Set up reason codes for warehouses</span></span>

1. <span data-ttu-id="39ccc-133">Selecione **Gerenciamento de Estoque** \> **Configuração** \> **Divisão de estoque** \> **Depósitos**.</span><span class="sxs-lookup"><span data-stu-id="39ccc-133">Select **Inventory Management** \> **Setup** \> **Inventory breakdown** \> **Warehouses**.</span></span>
2. <span data-ttu-id="39ccc-134">Na guia **Depósito**, no campo **Política de código de motivo de contagem**, selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="39ccc-134">On the **Warehouse** tab, in the **Counting reason code policy** field, select one of the following options:</span></span>

    - <span data-ttu-id="39ccc-135">**Em branco** – O parâmetro configurado para o item é usado para determinar se os diários de contagem são obrigatórios para o produto.</span><span class="sxs-lookup"><span data-stu-id="39ccc-135">**Blank** – The parameter that is set up for the item is used to determine whether counting journals are mandatory for the product.</span></span>
    - <span data-ttu-id="39ccc-136">**Obrigatório** – Um código de motivo é sempre necessário em diários de contagem do depósito.</span><span class="sxs-lookup"><span data-stu-id="39ccc-136">**Mandatory** – A reason code is always required on counting journals for the warehouse.</span></span>
    - <span data-ttu-id="39ccc-137">**Opcional** – Um código de motivo não é necessário em diários de contagem do depósito.</span><span class="sxs-lookup"><span data-stu-id="39ccc-137">**Optional** – A reason code isn't required on counting journals for the warehouse.</span></span>

### <a name="set-up-reason-codes-for-products"></a><span data-ttu-id="39ccc-138">Configurar códigos de motivo para produtos</span><span class="sxs-lookup"><span data-stu-id="39ccc-138">Set up reason codes for products</span></span>

1. <span data-ttu-id="39ccc-139">Selecione **Gerenciamento de informações sobre produto** \> **Produtos** \> **Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="39ccc-139">Select **Product information management** \> **Products** \> **Released products**.</span></span>
2. <span data-ttu-id="39ccc-140">Na guia **Produto**, selecione **Política de código de motivo de contagem** e, em seguida, selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="39ccc-140">On the **Product** tab, select **Counting reason code policy**, and then select one of the following options:</span></span>

    - <span data-ttu-id="39ccc-141">**Em branco** – O parâmetro configurado para o depósito é usado para determinar se os diários de contagem são obrigatórios para o produto.</span><span class="sxs-lookup"><span data-stu-id="39ccc-141">**Blank** – The parameter that is set up for the warehouse is used to determine whether counting journals are mandatory for the product.</span></span>
    - <span data-ttu-id="39ccc-142">**Obrigatório** – Um código de motivo é sempre necessário em diários de contagem do produto.</span><span class="sxs-lookup"><span data-stu-id="39ccc-142">**Mandatory** – A reason code is always required on counting journals for the product.</span></span> <span data-ttu-id="39ccc-143">Essa configuração substitui qualquer configuração de código de motivo em nível de depósito.</span><span class="sxs-lookup"><span data-stu-id="39ccc-143">This setting overrides any reason code setting at the warehouse level.</span></span>
    - <span data-ttu-id="39ccc-144">**Opcional** – Um código de motivo não é necessário em diários de contagem do produto.</span><span class="sxs-lookup"><span data-stu-id="39ccc-144">**Optional** – A reason code isn't required on counting journals for the product.</span></span> <span data-ttu-id="39ccc-145">Essa configuração substitui qualquer configuração de código de motivo em nível de depósito.</span><span class="sxs-lookup"><span data-stu-id="39ccc-145">This setting overrides any reason code setting at the warehouse level.</span></span>

### <a name="use-reason-codes-in-counting-journals"></a><span data-ttu-id="39ccc-146">Usar códigos de motivo em diários de contagem</span><span class="sxs-lookup"><span data-stu-id="39ccc-146">Use reason codes in counting journals</span></span>

<span data-ttu-id="39ccc-147">Em um diário de contagem, você pode adicionar códigos de motivo a contagem dos seguintes tipos:</span><span class="sxs-lookup"><span data-stu-id="39ccc-147">In a counting journal, you can add reason codes for counts of the following types:</span></span>

- <span data-ttu-id="39ccc-148">Contagem Cíclica</span><span class="sxs-lookup"><span data-stu-id="39ccc-148">Cycle Count</span></span>
- <span data-ttu-id="39ccc-149">Contagem Pontual</span><span class="sxs-lookup"><span data-stu-id="39ccc-149">Spot Count</span></span>
- <span data-ttu-id="39ccc-150">Contagem do Limite</span><span class="sxs-lookup"><span data-stu-id="39ccc-150">Threshold Count</span></span>
- <span data-ttu-id="39ccc-151">Ajuste de Entrada</span><span class="sxs-lookup"><span data-stu-id="39ccc-151">Adjustment In</span></span>
- <span data-ttu-id="39ccc-152">Ajuste de Saída</span><span class="sxs-lookup"><span data-stu-id="39ccc-152">Adjustment Out</span></span>

<span data-ttu-id="39ccc-153">Os códigos de motivo são adicionados às linhas do diário nos diários de contagem do tipo **Diário de contagem** .</span><span class="sxs-lookup"><span data-stu-id="39ccc-153">Reason codes are added to the journal lines in counting journals of the **Counting journal** type.</span></span>

1. <span data-ttu-id="39ccc-154">Selecione **Gerenciamento de estoque** \> **Entradas de diário** \> **Contagem de itens** \> **Contagem**.</span><span class="sxs-lookup"><span data-stu-id="39ccc-154">Select **Inventory management** \> **Journal entries** \> **Item counting** \> **Counting**.</span></span>
2. <span data-ttu-id="39ccc-155">Nos detalhes da linha do diário de contagem, no campo **Código de motivo de contagem**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="39ccc-155">In the line details of the counting journal, in the **Counting reason code** field, select an option.</span></span>

### <a name="view-the-counting-history-as-its-recorded-by-reason-codes"></a><span data-ttu-id="39ccc-156">Exiba o histórico de contagem como é registrado pelos códigos de motivo</span><span class="sxs-lookup"><span data-stu-id="39ccc-156">View the counting history as it's recorded by reason codes</span></span>

- <span data-ttu-id="39ccc-157">Selecione **Gerenciamento de estoque** \> **Consultas e relatórios** \> **Histórico de contagem** e no campo **Código de motivo de contagem**, exiba o histórico de contagem que foi registrado através de um código de motivo.</span><span class="sxs-lookup"><span data-stu-id="39ccc-157">Select **Inventory management** \> **Inquiries and reports** \> **Counting history**, and then, in the **Counting reason code** field, view the counting history that has been recorded through a reason code.</span></span>

### <a name="use-a-reason-code-for-a-quantity-adjustment"></a><span data-ttu-id="39ccc-158">Use um código de motivo para um ajuste de quantidade</span><span class="sxs-lookup"><span data-stu-id="39ccc-158">Use a reason code for a quantity adjustment</span></span>

1. <span data-ttu-id="39ccc-159">Na página **Estoque disponível**, selecione **Ajustar quantidade**.</span><span class="sxs-lookup"><span data-stu-id="39ccc-159">On the **On-hand inventory** page, select **Adjust quantity**.</span></span> <span data-ttu-id="39ccc-160">Você pode abrir a página **Estoque disponível** de várias formas.</span><span class="sxs-lookup"><span data-stu-id="39ccc-160">You can open the **On-hand inventory** page in several ways.</span></span> <span data-ttu-id="39ccc-161">Por exemplo, selecione **Gerenciamento de estoque** \> **Consultas e relatórios** \> **Estoque disponível**.</span><span class="sxs-lookup"><span data-stu-id="39ccc-161">For example, select **Inventory management** \> **Inquiries and reports** \> **On-hand inventory**.</span></span>
2. <span data-ttu-id="39ccc-162">Selecione **Ajustar quantidade** e no campo **Código de motivo de contagem**, selecione um código de motivo.</span><span class="sxs-lookup"><span data-stu-id="39ccc-162">Select **Adjust quantity**, and then, in the **Counting reason code** field, select a reason code.</span></span>

### <a name="configure-reason-codes-for-mobile-device-menu-items"></a><span data-ttu-id="39ccc-163">Configurar códigos de motivo para itens de menu de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="39ccc-163">Configure reason codes for mobile device menu items</span></span>

<span data-ttu-id="39ccc-164">Você pode configurar códigos de motivo para qualquer tipo de contagem em um item de menu de dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="39ccc-164">You can configure reason codes for any type of count on a mobile device menu item.</span></span> <span data-ttu-id="39ccc-165">A configuração de itens de menu de dispositivo móvel inclui as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="39ccc-165">The configuration of the mobile device menu item includes the following information:</span></span>

- <span data-ttu-id="39ccc-166">Se o código será for mostrado ao trabalhador do dispositivo móvel durante a contagem.</span><span class="sxs-lookup"><span data-stu-id="39ccc-166">Whether the reason code is shown to the mobile device worker during counting.</span></span>
- <span data-ttu-id="39ccc-167">O código de motivo padrão que é mostrado em um item de menu do dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="39ccc-167">The default reason code that is shown on a mobile device menu item.</span></span>
- <span data-ttu-id="39ccc-168">Se o usuário pode editar o código de motivo.</span><span class="sxs-lookup"><span data-stu-id="39ccc-168">Whether the user can edit the reason code.</span></span>

### <a name="set-up-reason-codes-on-a-mobile-device"></a><span data-ttu-id="39ccc-169">Configurar códigos de motivo em um dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="39ccc-169">Set up reason codes on a mobile device</span></span>

1. <span data-ttu-id="39ccc-170">Selecione **Gerenciamento de depósito** \> **Configuração** \> **Dispositivo móvel** \> **Itens de menu do dispositivo móvel**.</span><span class="sxs-lookup"><span data-stu-id="39ccc-170">Select **Warehouse management** \> **Setup** \> **Mobile device** \> **Mobile device menu items**.</span></span>
2. <span data-ttu-id="39ccc-171">Na guia **Contagem cíclica** , selecione **Contagem cíclica**.</span><span class="sxs-lookup"><span data-stu-id="39ccc-171">On the **Cycle count** tab, select **Cycle counting**.</span></span>
3. <span data-ttu-id="39ccc-172">No campo **Código de motivo de contagem padrão** , defina o código de motivo padrão que deve ser registrado quando contagem é feita usando o item de menu de dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="39ccc-172">In the **Default counting reason code** field, set the default reason code that should be recorded when counting is done by using the mobile device menu item.</span></span>
4. <span data-ttu-id="39ccc-173">No campo **Exibir código de motivo de contagem** , selecione **Linha** para mostrar o código de motivo após cada variação ser registrada.</span><span class="sxs-lookup"><span data-stu-id="39ccc-173">In the **Display counting reason code** field, select **Line** to show the reason code after each variance is recorded.</span></span> <span data-ttu-id="39ccc-174">Como alternativa, selecione **Ocultar** se o código de motivo não tiver que ser mostrado.</span><span class="sxs-lookup"><span data-stu-id="39ccc-174">Alternatively, select **Hide** if the reason code shouldn't be shown.</span></span>
5. <span data-ttu-id="39ccc-175">Defina a opção **Editar código de motivo de contagem** como **Sim** ou **Não**.</span><span class="sxs-lookup"><span data-stu-id="39ccc-175">Set the **Edit counting reason code** option to either **Yes** or **No**.</span></span> <span data-ttu-id="39ccc-176">Se você definir esta opção como **Sim**, o trabalhador poderá editar o código de motivo quando ele for mostrado no dispositivo móvel durante a contagem.</span><span class="sxs-lookup"><span data-stu-id="39ccc-176">If you set this option to **Yes**, the worker can edit the reason code when it's shown on the mobile device during counting.</span></span>

> [!NOTE]
> <span data-ttu-id="39ccc-177">O botão **Contagem cíclica** pode ser habilitado em qualquer item de menu de dispositivo móvel onde a contagem pode ser feita.</span><span class="sxs-lookup"><span data-stu-id="39ccc-177">The **Cycle counting** button can be enabled on any mobile device menu item where counting can be done.</span></span> <span data-ttu-id="39ccc-178">O exemplo inclui itens de menu para contagens pontuais, trabalho direcionado ao usuário e trabalho direcionado ao sistema.</span><span class="sxs-lookup"><span data-stu-id="39ccc-178">Example include the menu items for spot counts, user-directed work, and system-directed work.</span></span>

## <a name="cycle-count-approvals"></a><span data-ttu-id="39ccc-179">Aprovações de contagem cíclica</span><span class="sxs-lookup"><span data-stu-id="39ccc-179">Cycle count approvals</span></span>

<span data-ttu-id="39ccc-180">Antes de uma contagem ser aprovada, o usuário pode alterar o código de motivo associado à contagem.</span><span class="sxs-lookup"><span data-stu-id="39ccc-180">Before a count is approved, the user can change the reason code that is associated with the count.</span></span> <span data-ttu-id="39ccc-181">Quando a contagem for aprovada, o código de motivo será inserido nas linhas de diário da contagem.</span><span class="sxs-lookup"><span data-stu-id="39ccc-181">When the count is approved, the reason code is entered on the counting journal lines.</span></span>

### <a name="modify-cycle-count-approvals"></a><span data-ttu-id="39ccc-182">Modificar aprovações de contagem cíclica</span><span class="sxs-lookup"><span data-stu-id="39ccc-182">Modify cycle count approvals</span></span>

1. <span data-ttu-id="39ccc-183">Selecione **Gerenciamento de depósito** \> **Contagem cíclica** \> **Trabalho de contagem cíclica com revisão pendente**.</span><span class="sxs-lookup"><span data-stu-id="39ccc-183">Select **Warehouse management** \> **Cycle counting** \> **Cycle count work pending review**.</span></span>
2. <span data-ttu-id="39ccc-184">Selecione **Contagem cíclica** e, em seguida, no campo **Código de motivo**, selecione um novo código de motivo.</span><span class="sxs-lookup"><span data-stu-id="39ccc-184">Select **Cycle counting**, and then, in the **Reason code** field, select a new reason code.</span></span>

### <a name="modify-the-mobile-device-menu-item-for-adjustment-in-and-adjustment-out"></a><span data-ttu-id="39ccc-185">Modificar o item de menu do dispositivo móvel para Ajuste de entrada e Ajuste de saída</span><span class="sxs-lookup"><span data-stu-id="39ccc-185">Modify the mobile device menu item for Adjustment in and Adjustment out</span></span>

1. <span data-ttu-id="39ccc-186">Selecione **Gerenciamento de depósito** \> **Configuração** \> **Dispositivo móvel** \> **Itens de menu do dispositivo móvel** e depois **Ajuste de entrada e saída**.</span><span class="sxs-lookup"><span data-stu-id="39ccc-186">Select **Warehouse management** \> **Setup** \> **Mobile device** \> **Mobile device menu items**, and then select **Adjustment in and out**.</span></span>
2. <span data-ttu-id="39ccc-187">Defina a opção **Usar trabalho existente** como **Não**.</span><span class="sxs-lookup"><span data-stu-id="39ccc-187">Set the **Use existing work** option to **No**.</span></span>
3. <span data-ttu-id="39ccc-188">No campo **Processo de criação de trabalho**, selecione **Ajuste de entrada**.</span><span class="sxs-lookup"><span data-stu-id="39ccc-188">In the **Work creation process** field, select **Adjustment in**.</span></span>

<span data-ttu-id="39ccc-189">Os campos a seguir serão adicionados ao item de menu do dispositivo móvel quando **Ajuste de entrada** ou **Ajuste de saída** for selecionado durante o processo de criação de trabalho:</span><span class="sxs-lookup"><span data-stu-id="39ccc-189">The following fields will be added to the mobile device menu item when **Adjustment in** or **Adjustment out** is selected during the work creation process:</span></span>

- <span data-ttu-id="39ccc-190">Código de motivo de contagem padrão</span><span class="sxs-lookup"><span data-stu-id="39ccc-190">Default counting reason code</span></span>
- <span data-ttu-id="39ccc-191">Exibir código de motivo de contagem</span><span class="sxs-lookup"><span data-stu-id="39ccc-191">Display counting reason code</span></span>
- <span data-ttu-id="39ccc-192">Editar código de motivo de contagem</span><span class="sxs-lookup"><span data-stu-id="39ccc-192">Edit counting reason code</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
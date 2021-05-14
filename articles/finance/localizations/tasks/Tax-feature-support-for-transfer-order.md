---
title: Suporte ao recurso de imposto para a ordens de transferência
description: Este tópico explica o novo suporte a recursos de imposto para ordens de transferência usando o serviço de cálculo de imposto.
author: kailiang
ms.date: 04/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: d1b99046b0e439c9dadbb240050e270a7b2a6914
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920946"
---
# <a name="tax-feature-support-for-transfer-orders"></a><span data-ttu-id="37d4e-103">Suporte ao recurso de imposto para a ordens de transferência</span><span class="sxs-lookup"><span data-stu-id="37d4e-103">Tax feature support for transfer orders</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="37d4e-104">Este tópico fornece informações sobre cálculo de impostos e integração de lançamento em ordens de transferência.</span><span class="sxs-lookup"><span data-stu-id="37d4e-104">This topic provides information about tax calculation and posting integration in transfer orders.</span></span> <span data-ttu-id="37d4e-105">Essa funcionalidade permite que você defina o cálculo e o lançamento de impostos em ordens de transferência para transferências de estoque.</span><span class="sxs-lookup"><span data-stu-id="37d4e-105">This functionality lets you set up tax calculation and posting in transfer orders for stock transfers.</span></span> <span data-ttu-id="37d4e-106">Sob as regulamentações de imposto sobre valor agregado (IVA) da União Europeia (UE), as transferências de estoque são consideradas de fornecimento e aquisição interna na comunidade.</span><span class="sxs-lookup"><span data-stu-id="37d4e-106">Under European Union (EU) value-added tax (VAT) regulations, stock transfers are considered intra-community supply and intra-community acquisitions.</span></span>

<span data-ttu-id="37d4e-107">Para configurar e usar esse recurso, você deve seguir três etapas principais:</span><span class="sxs-lookup"><span data-stu-id="37d4e-107">To configure and use this functionality, you must complete three main steps:</span></span>

1. <span data-ttu-id="37d4e-108">**Configuração do RCS:** no serviço de configuração regulatória, defina o recurso de imposto, os códigos de imposto e a aplicabilidade dos códigos de imposto para determinar o código de imposto em ordens de transferência.</span><span class="sxs-lookup"><span data-stu-id="37d4e-108">**RCS setup:** In Regulatory Configuration Service, set up the tax feature, tax codes, and tax codes applicability for tax code determination in transfer orders.</span></span>
2. <span data-ttu-id="37d4e-109">**Configuração de finanças:** no Microsoft Dynamics 365 Finance, ative o recurso **Imposto em ordem de transferência**, configure os parâmetros do serviço de imposto do estoque e defina os principais parâmetros de imposto.</span><span class="sxs-lookup"><span data-stu-id="37d4e-109">**Finance setup:** In Microsoft Dynamics 365 Finance, turn on the **Tax in transfer order** feature, set up the tax service parameters for inventory, and set up core tax parameters.</span></span>
3. <span data-ttu-id="37d4e-110">**Configuração de estoque:** defina a configuração de estoque para transações de ordem de transferência.</span><span class="sxs-lookup"><span data-stu-id="37d4e-110">**Inventory setup:** Set up the inventory configuration for transfer order transactions.</span></span>

## <a name="set-up-rcs-for-tax-and-transfer-order-transactions"></a><span data-ttu-id="37d4e-111">Configurar o RCS para transações de ordem de transferência e imposto</span><span class="sxs-lookup"><span data-stu-id="37d4e-111">Set up RCS for tax and transfer order transactions</span></span>

<span data-ttu-id="37d4e-112">Siga estas etapas para configurar o imposto envolvido em uma ordem de transferência.</span><span class="sxs-lookup"><span data-stu-id="37d4e-112">Follow these steps to set up the tax that is involved in a transfer order.</span></span> <span data-ttu-id="37d4e-113">No exemplo mostrado, a ordem de transferência é dos Países Baixos para a Bélgica.</span><span class="sxs-lookup"><span data-stu-id="37d4e-113">In the example that is shown here, the transfer order is from the Netherlands to Belgium.</span></span>

1. <span data-ttu-id="37d4e-114">Na página **Recursos de impostos**, na guia **Versões**, selecione o rascunho da versão do recurso e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-114">On the **Tax features** page, on the **Versions** tab, select the draft feature version, and then select **Edit**.</span></span>

    ![Depois de selecionar Editar](../media/image1.png)

2. <span data-ttu-id="37d4e-116">Na página **Configuração dos recursos de impostos**, na guia **Códigos de impostos**, selecione **Adicionar** para criar códigos de impostos.</span><span class="sxs-lookup"><span data-stu-id="37d4e-116">On the **Tax features setup** page, on the **Tax codes** tab, select **Add** to create new tax codes.</span></span> <span data-ttu-id="37d4e-117">Nesse exemplo, três códigos de imposto são criados: **NL-Exempt**, **BE-RC-21** e **BE-RC+21**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-117">For this example, three tax codes are created: **NL-Exempt**, **BE-RC-21**, and **BE-RC+21**.</span></span>

    - <span data-ttu-id="37d4e-118">Quando uma ordem de transferência é enviada de um depósito nos Países Baixos, o código de imposto isento de IVA dos Países Baixos (**NL-Exempt**) é aplicado.</span><span class="sxs-lookup"><span data-stu-id="37d4e-118">When a transfer order is shipped from a warehouse in the Netherlands, the Netherlands VAT exempted tax code (**NL-Exempt**) is applied.</span></span>
      
        <span data-ttu-id="37d4e-119">Crie o código de imposto **NL-Exempt**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-119">Create the tax code **NL-Exempt**.</span></span>
        1. <span data-ttu-id="37d4e-120">Selecione **Adicionar**, insira o código **NL-Exempt** no campo **Código de imposto**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-120">Select **Add**, enter **NL-Exempt** in the **Tax code** field.</span></span>
        2. <span data-ttu-id="37d4e-121">Selecione **Por valor líquido** no campo **Componente de imposto**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-121">Select **By Net Amount** in the **Tax component** field.</span></span>
        3. <span data-ttu-id="37d4e-122">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-122">Select **Save**.</span></span>
        4. <span data-ttu-id="37d4e-123">Selecione **Adicionar** na tabela **Taxa**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-123">Select **Add** in the **Rate** table.</span></span>
        5. <span data-ttu-id="37d4e-124">Altere o campo **É Isento** para **Sim** na seção **Geral**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-124">Swtich **Is Exempt** to **Yes** in the **General** section.</span></span>

        ![Código de imposto NL-Exempt](../media/image2.png)

    - <span data-ttu-id="37d4e-126">Quando uma ordem de transferência é recebida em um depósito na Bélgica, o mecanismo de cobrança revertido é aplicado usando os códigos de imposto **BE-RC-21** e **BE-RC+21**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-126">When a transfer order is received at a Belgium warehouse, the reverse charge mechanism is applied by using the **BE-RC-21** and **BE-RC+21** tax codes.</span></span>
        
        <span data-ttu-id="37d4e-127">Crie o código de imposto **BE-RC-21**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-127">Create the tax code **BE-RC-21**.</span></span>      
        1. <span data-ttu-id="37d4e-128">Selecione **Adicionar**, insira o código **BE-RC-21** no campo **Código de imposto**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-128">Select **Add**, enter **BE-RC-21** in the **Tax code** field.</span></span>
        2. <span data-ttu-id="37d4e-129">Selecione **Por valor líquido** no campo **Componente de imposto**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-129">Select **By Net Amount** in the **Tax component** field.</span></span>
        3. <span data-ttu-id="37d4e-130">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-130">Select **Save**.</span></span>
        4. <span data-ttu-id="37d4e-131">Selecione **Adicionar** na tabela **Taxa**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-131">Select **Add** in the **Rate** table.</span></span>
        5. <span data-ttu-id="37d4e-132">Insira **-21** no campo **Taxa tributária**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-132">Enter **-21** in the **Tax Rate** field.</span></span>
        6. <span data-ttu-id="37d4e-133">Altere o campo **É Encargo Reverso** para **Sim** na seção **Geral**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-133">Swtich **Is Reverse Charge** to **Yes** in the **General** section.</span></span>
        7. <span data-ttu-id="37d4e-134">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-134">Select **Save**.</span></span>

        ![Código de imposto BE-RC-21 para cobranças revertidas](../media/image3.png)
        
        <span data-ttu-id="37d4e-136">Crie o código de imposto **BE-RC+21**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-136">Create the tax code **BE-RC+21**.</span></span>
        1. <span data-ttu-id="37d4e-137">Selecione **Adicionar**, insira o código **BE-RC-21** no campo **Código de imposto**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-137">Select **Add**, enter **BE-RC-21** in the **Tax code** field.</span></span>
        2. <span data-ttu-id="37d4e-138">Selecione **Por valor líquido** no campo **Componente de imposto**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-138">Select **By Net Amount** in the **Tax component** field.</span></span>
        3. <span data-ttu-id="37d4e-139">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-139">Select **Save**.</span></span>
        4. <span data-ttu-id="37d4e-140">Selecione **Adicionar** na tabela **Taxa**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-140">Select **Add** in the **Rate** table.</span></span>
        5. <span data-ttu-id="37d4e-141">Insira **21** no campo **Taxa tributária**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-141">Enter **21** in the **Tax Rate** field.</span></span>
        6. <span data-ttu-id="37d4e-142">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-142">Select **Save**.</span></span>

        ![Código de imposto BE-RC+21 para cobranças revertidas](../media/image4.png)

3. <span data-ttu-id="37d4e-144">Defina a aplicabilidade dos códigos de imposto.</span><span class="sxs-lookup"><span data-stu-id="37d4e-144">Define the applicability of the tax codes.</span></span>

    1. <span data-ttu-id="37d4e-145">Selecione **Gerenciar colunas** e selecione as colunas que devem ser usadas para criar a tabela de aplicabilidade.</span><span class="sxs-lookup"><span data-stu-id="37d4e-145">Select **Manage columns**, and then select columns that should be used to build the applicability table.</span></span>

        > [!NOTE]
        > <span data-ttu-id="37d4e-146">Adicionar as colunas **Processo comercial** e **Direções de imposto** à tabela.</span><span class="sxs-lookup"><span data-stu-id="37d4e-146">Be sure to add the **Business process** and **Tax directions** columns to the table.</span></span> <span data-ttu-id="37d4e-147">As duas colunas são essenciais para a funcionalidade do imposto em ordens de transferência.</span><span class="sxs-lookup"><span data-stu-id="37d4e-147">Both columns are essential to the functionality for tax in transfer orders.</span></span>

    2. <span data-ttu-id="37d4e-148">Inclua regras de aplicabilidade.</span><span class="sxs-lookup"><span data-stu-id="37d4e-148">Add applicability rules.</span></span> <span data-ttu-id="37d4e-149">Não deixe os campos **Códigos de imposto**, **Grupo de impostos** e **Grupo de impostos sobre o item** em branco.</span><span class="sxs-lookup"><span data-stu-id="37d4e-149">Don't leave the **Tax codes**, **Tax group**, and **Item tax group** fields blank.</span></span>
        
        <span data-ttu-id="37d4e-150">Inclua uma nova regra para a remessa da ordem de transferência.</span><span class="sxs-lookup"><span data-stu-id="37d4e-150">Add a new rule for transfer order shipment.</span></span>
        1. <span data-ttu-id="37d4e-151">Selecione **Adicionar** na tabela **Regras de aplicabilidade**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-151">Select **Add** in the **Applicability rules** table.</span></span>
        2. <span data-ttu-id="37d4e-152">No campo **Processo comercial**, selecione **Estoque** para tornar a regra aplicável para uma ordem de transferência.</span><span class="sxs-lookup"><span data-stu-id="37d4e-152">In the **Business process** field, select **Inventory** to make the rule applicable for a transfer order.</span></span>
        3. <span data-ttu-id="37d4e-153">No campo **Enviar do país/região**, insira **NLD**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-153">In the **Ship From Country/Region** field, enter **NLD**.</span></span>
        4. <span data-ttu-id="37d4e-154">No campo **Enviar para país/região**, insira **BEL**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-154">In the **Ship To Country/Region** field, enter **BEL**.</span></span>
        5. <span data-ttu-id="37d4e-155">No campo **Direção de imposto**, selecione **Saída** para tornar a regra aplicável à remessa da ordem de transferência.</span><span class="sxs-lookup"><span data-stu-id="37d4e-155">In the **Tax direction** field, select **Output** to make the rule applicable to transfer order shipment.</span></span>
        6. <span data-ttu-id="37d4e-156">No campo **Códigos de imposto**, selecione **NL-Exempt**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-156">In the **Tax codes** field, select **NL-Exempt**.</span></span>
        7. <span data-ttu-id="37d4e-157">No campo **Grupo de impostos** e no **Grupo de impostos sobre o item**, insira o grupo de impostos sobre vendas relacionado e o grupo de impostos sobre vendas do item que são definidos no seu sistema financeiro.</span><span class="sxs-lookup"><span data-stu-id="37d4e-157">In the **Tax Group** field and the **Item Tax Group**, enter the related sales tax group and item sales tax group which are defined in your Finance system.</span></span>
        
        <span data-ttu-id="37d4e-158">Inclua outra regra para o recebimento da ordem de transferência.</span><span class="sxs-lookup"><span data-stu-id="37d4e-158">Add another rule for transfer order receipt.</span></span>
        1. <span data-ttu-id="37d4e-159">Selecione **Adicionar** na tabela **Regras de aplicabilidade**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-159">Select **Add** in the **Applicability rules** table.</span></span>
        2. <span data-ttu-id="37d4e-160">No campo **Processo comercial**, selecione **Estoque** para tornar a regra aplicável para uma ordem de transferência.</span><span class="sxs-lookup"><span data-stu-id="37d4e-160">In the **Business process** field, select **Inventory** to make the rule applicable for a transfer order.</span></span>
        3. <span data-ttu-id="37d4e-161">No campo **Enviar do país/região**, insira **NLD**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-161">In the **Ship From Country/Region** field, enter **NLD**.</span></span>
        4. <span data-ttu-id="37d4e-162">No campo **Enviar para país/região**, insira **BEL**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-162">In the **Ship To Country/Region** field, enter **BEL**.</span></span>
        5. <span data-ttu-id="37d4e-163">No campo **Direção de imposto**, selecione **Entrada** para tornar a regra aplicável ao recebimento da ordem de transferência.</span><span class="sxs-lookup"><span data-stu-id="37d4e-163">In the **Tax direction** field, select **Input** to make the rule applicable to transfer order receipt.</span></span>
        6. <span data-ttu-id="37d4e-164">No campo **Códigos de imposto**, selecione **BE-RC+21** e **BE-RC-21**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-164">In the **Tax codes** field, select **BE-RC+21** and **BE-RC-21**.</span></span>
        7. <span data-ttu-id="37d4e-165">No campo **Grupo de impostos** e no **Grupo de impostos sobre o item**, insira o grupo de impostos sobre vendas relacionado e o grupo de impostos sobre vendas do item que são definidos no seu sistema financeiro.</span><span class="sxs-lookup"><span data-stu-id="37d4e-165">In the **Tax Group** field and the **Item Tax Group**, enter the related sales tax group and item sales tax group which are defined in your Finance system.</span></span>

        ![Regras de aplicabilidade](../media/image5.png)

4. <span data-ttu-id="37d4e-167">Conclua e publique a nova versão do recurso de imposto.</span><span class="sxs-lookup"><span data-stu-id="37d4e-167">Complete and publish the new tax feature version.</span></span>

    <span data-ttu-id="37d4e-168">[![Alteração do status da nova versão](../media/image6.png)](../media/image6.png)</span><span class="sxs-lookup"><span data-stu-id="37d4e-168">[![Changing the status of the new version](../media/image6.png)](../media/image6.png)</span></span>

## <a name="set-up-finance-for-transfer-order-transactions"></a><span data-ttu-id="37d4e-169">Configure as Finanças para transações de ordem de transferência e imposto</span><span class="sxs-lookup"><span data-stu-id="37d4e-169">Set up Finance for transfer order transactions</span></span>

<span data-ttu-id="37d4e-170">Siga estas etapas para habilitar e configurar os impostos para ordens de transferência.</span><span class="sxs-lookup"><span data-stu-id="37d4e-170">Follow these steps to enable and set up taxes for transfer orders.</span></span>

1. <span data-ttu-id="37d4e-171">Em Finanças, acesse **Espaços de trabalho** \> **Gerenciamento do recurso**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-171">In Finance, go to **Workspaces** \> **Feature management**.</span></span>
2. <span data-ttu-id="37d4e-172">Na lista, localize e selecione o recurso **Imposto em ordem de transferência** e selecione **Habilitar agora** para ativá-lo.</span><span class="sxs-lookup"><span data-stu-id="37d4e-172">In the list, find and select the **Tax in transfer order** feature, and then select **Enable now** to turn it on.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="37d4e-173">O recurso **Imposto em ordem de transferência** depende totalmente do serviço de imposto.</span><span class="sxs-lookup"><span data-stu-id="37d4e-173">The **Tax in transfer order** feature is fully dependent on the tax service.</span></span> <span data-ttu-id="37d4e-174">Portanto, ele pode ser ativado somente após a instalação do serviço de imposto.</span><span class="sxs-lookup"><span data-stu-id="37d4e-174">Therefore, it can be turned on only after you've installed the tax service.</span></span>

    ![Recurso de impostos em ordem de transferência](../media/image7.png)

3. <span data-ttu-id="37d4e-176">Habilite o serviço de imposto e selecione o processo comercial **Estoque**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-176">Enable the tax service, and select the **Inventory** business process.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="37d4e-177">Você deve concluir esta etapa para cada entidade legal no departamento financeiro em que deseja que o serviço de imposto e a funcionalidade do imposto sobre as ordens de transferência estejam disponíveis.</span><span class="sxs-lookup"><span data-stu-id="37d4e-177">You must complete this step for each legal entity in Finance where you want the tax service and the functionality for tax in transfer orders to be available.</span></span>

    1. <span data-ttu-id="37d4e-178">Acesse **Imposto** \> **Configuração** \> **Configuração do imposto** \> **Configuração do serviço de imposto**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-178">Go to **Tax** \> **Setup** \> **Tax configuration** \> **Tax service setup**.</span></span>
    2. <span data-ttu-id="37d4e-179">No campo **Processo comercial**, selecione **Estoque**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-179">In the **Business process** field, select **Inventory**.</span></span>

    ![Configuração do campo Processo comercial](../media/image8.png)

4. <span data-ttu-id="37d4e-181">Verifique se o mecanismo de reversão da cobrança está configurado.</span><span class="sxs-lookup"><span data-stu-id="37d4e-181">Verify that the reverse charge mechanism is set up.</span></span> <span data-ttu-id="37d4e-182">Acesse **Contabilidade** \> **Configuração** \> **Parâmetros** e, na guia **Reverter cobrança**, verifique se a opção **Habilitar a reversão da cobrança** está definida para **Sim**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-182">Go to **General ledger** \> **Setup** \> **Parameters**, and then, on the **Reverse charge** tab, verify that the **Enable reverse charge** option is set to **Yes**.</span></span>

    ![Habilite a opção de reversão da cobrança](../media/image9.png)

5. <span data-ttu-id="37d4e-184">Verifique se os códigos de imposto relacionados, grupos de impostos, grupos de impostos do item e números de registro do IVA foram configurados em Finanças de acordo com a orientação do serviço de imposto.</span><span class="sxs-lookup"><span data-stu-id="37d4e-184">Verify that the related tax codes, tax groups, item tax groups, and VAT registration numbers have been set up in Finance according to the tax service guidance.</span></span>
6. <span data-ttu-id="37d4e-185">Configure uma conta de trânsito provisória.</span><span class="sxs-lookup"><span data-stu-id="37d4e-185">Set up an interim transit account.</span></span> <span data-ttu-id="37d4e-186">Essa etapa é necessária apenas quando o imposto aplicado a uma ordem de transferência não é aplicável a um mecanismo isento de imposto ou de cobrança revertida.</span><span class="sxs-lookup"><span data-stu-id="37d4e-186">This step is required only when the tax that is applied to a transfer order isn't applicable to a tax exempted or reverse charge mechanism.</span></span>

    1. <span data-ttu-id="37d4e-187">Acesse **Imposto** \> **Configuração** \> **Imposto sobre vendas** \> **Grupos de lançamento da razão**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-187">Go to **Tax** \> **Setup** \> **Sales tax** \> **Ledger posting groups**.</span></span>
    2. <span data-ttu-id="37d4e-188">No campo **Trânsito provisório**, selecione uma conta contábil.</span><span class="sxs-lookup"><span data-stu-id="37d4e-188">In the **Interim transit** field, select a ledger account.</span></span>

    ![Selecionar uma conta de trânsito provisória](../media/image10.png)

## <a name="set-up-basic-inventory-for-transfer-order-transactions"></a><span data-ttu-id="37d4e-190">Configure o estoque básico para transações de ordem de transferência e imposto</span><span class="sxs-lookup"><span data-stu-id="37d4e-190">Set up basic inventory for transfer order transactions</span></span>

<span data-ttu-id="37d4e-191">Siga estas etapas para configurar o inventário básico e habilitar transações de ordem de transferência.</span><span class="sxs-lookup"><span data-stu-id="37d4e-191">Follow these steps to set up basic inventory to enable transfer order transactions.</span></span>

1. <span data-ttu-id="37d4e-192">Crie sites de "enviar de" e "enviar para" seus depósitos em diferentes países ou regiões e adicione o endereço principal para cada site.</span><span class="sxs-lookup"><span data-stu-id="37d4e-192">Create ship-from and ship-to sites for your warehouses in different countries or regions, and add the primary address for each site.</span></span>

    1. <span data-ttu-id="37d4e-193">Acesse **Gerenciamento do depósito** \> **Configuração** \> **Depósito** \> **Locais**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-193">Go to **Warehouse management** \> **Setup** \> **Warehouse** \> **Sites**.</span></span>
    2. <span data-ttu-id="37d4e-194">Selecione **Novo** para criar o local que será atribuído a um depósito posteriormente.</span><span class="sxs-lookup"><span data-stu-id="37d4e-194">Select **New** to create the site that you will assign to a warehouse later.</span></span>
    3. <span data-ttu-id="37d4e-195">Repita a etapa 2 para todos os outros locais que você criar.</span><span class="sxs-lookup"><span data-stu-id="37d4e-195">Repeat step 2 for all the other sites that you must create.</span></span>

    > [!NOTE]
    > <span data-ttu-id="37d4e-196">Um dos locais deve ser nomeado como **Trânsito**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-196">One of the sites that you create should be named **Transit**.</span></span> <span data-ttu-id="37d4e-197">Nas próximas etapas deste procedimento, você atribuirá esse local ao depósito de trânsito para que os comprovantes de estoque relacionados a impostos possam ser lançados em transações de "envio" e "recebimento" para ordens de transferência.</span><span class="sxs-lookup"><span data-stu-id="37d4e-197">In later steps of this procedure, you will assign this site to the transit warehouse, so that tax-related inventory vouchers can be posted in "ship" and "receive" transactions for transfer orders.</span></span> <span data-ttu-id="37d4e-198">O endereço do local de trânsito é irrelevante para o cálculo de imposto.</span><span class="sxs-lookup"><span data-stu-id="37d4e-198">The address of the transit site is irrelevant to tax calculation.</span></span> <span data-ttu-id="37d4e-199">Portanto, você pode deixá-lo em branco.</span><span class="sxs-lookup"><span data-stu-id="37d4e-199">Therefore, you can leave it blank.</span></span>

    ![Definição dos locais](../media/image11.png)

2. <span data-ttu-id="37d4e-201">Crie depósitos de "envio de", trânsito e "envio para".</span><span class="sxs-lookup"><span data-stu-id="37d4e-201">Create ship-from, transit, and ship-to warehouses.</span></span> <span data-ttu-id="37d4e-202">As informações de endereço mantidas em um depósito substituirão o endereço do local durante o cálculo do imposto.</span><span class="sxs-lookup"><span data-stu-id="37d4e-202">Any address information that is maintained in a warehouse will override the site address during tax calculation.</span></span>

    1. <span data-ttu-id="37d4e-203">Acesse **Gerenciamento de depósito** \> **Configuração** \> **Depósito** \> **Depósitos**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-203">Go to **Warehouse management** \> **Setup** \> **Warehouse** \> **Warehouses**.</span></span>
    2. <span data-ttu-id="37d4e-204">Selecione **Novo** para criar um depósito e atribuí-lo ao local correspondente.</span><span class="sxs-lookup"><span data-stu-id="37d4e-204">Select **New** to create a warehouse, and assign it to the corresponding site.</span></span>
    3. <span data-ttu-id="37d4e-205">Repita a etapa 2 para criar um depósito para cada local, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="37d4e-205">Repeat step 2 to create a warehouse for each site as required.</span></span>

    ![Definição dos depósitos](../media/image12.png)

    > [!NOTE]
    > <span data-ttu-id="37d4e-207">No caso de um depósito de "envio para", é necessário selecionar um depósito de trânsito no campo **Depósito de trânsito** para as transações de ordem de transferência.</span><span class="sxs-lookup"><span data-stu-id="37d4e-207">For a ship-from warehouse, a transit warehouse must be selected in the **Transit warehouse** field for transfer order transactions.</span></span>
    >
    > ![Escolha de um depósito de trânsito](../media/image13.png)

3. <span data-ttu-id="37d4e-209">Verifique se a configuração do lançamento do estoque está definida para transações de ordem de transferência.</span><span class="sxs-lookup"><span data-stu-id="37d4e-209">Verify that the inventory posting configuration is set up for transfer order transactions.</span></span>

    1. <span data-ttu-id="37d4e-210">Acesse **Gerenciamento de estoque** \> **Configurar** \> **Lançamento** \> **Lançamento**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-210">Go to **Inventory management** \> **Setup** \> **Posting** \> **Posting**.</span></span>
    2. <span data-ttu-id="37d4e-211">Na guia **Estoque**, verifique se uma conta contábil está configurada para lançamento de **Saída de estoque** e **Recebimento do estoque**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-211">On the **Inventory** tab, verify that a ledger account is set up for both **Inventory issue** and **Inventory receipt** posting.</span></span>

        ![Configuração dos lançamentos Saída de estoque e Recebimento de estoque](../media/image14.png)

    3. <span data-ttu-id="37d4e-213">Verifique se uma conta contábil está configurada para lançamento **A pagar entre unidades**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-213">Verify that a ledger account is set up for **Inter-unit payable** posting.</span></span>

        ![Configuração do lançamento A pagar entre unidades](../media/image15.png)

    4. <span data-ttu-id="37d4e-215">Verifique se uma conta contábil está configurada para lançamento **A receber entre unidades**.</span><span class="sxs-lookup"><span data-stu-id="37d4e-215">Verify that a ledger account is set up for **Inter-unit receivable** posting.</span></span>

        ![Configuração do lançamento A receber entre unidades](../media/image16.png)

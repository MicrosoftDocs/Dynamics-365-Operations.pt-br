---
title: Cobrança por manutenção sobre ativos de propriedade do cliente
description: Este tópico explica como criar, processar e cobrar o trabalho de manutenção que é feito em ativos que seus clientes possuem.
author: johanhoffmann
manager: tfehr
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderProjCostInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 643e59f082949ed51ab61d79648a98b83a7f0b03
ms.sourcegitcommit: 1e615288db245f83c5d5e0cd45315400f8946beb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2021
ms.locfileid: "5131832"
---
# <a name="bill-for-maintenance-on-customer-owned-assets"></a><span data-ttu-id="3b8c0-103">Cobrança por manutenção sobre ativos de propriedade do cliente</span><span class="sxs-lookup"><span data-stu-id="3b8c0-103">Bill for maintenance on customer-owned assets</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3b8c0-104">O recurso *Cobrança de ordem de serviço* permite criar, processar e cobrar o trabalho de manutenção realizado em ativos que seus clientes possuem.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-104">The *Work order billing* feature lets you create, process, and bill maintenance work that is done on assets that your customers own.</span></span> <span data-ttu-id="3b8c0-105">Este recurso permite executar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="3b8c0-105">This feature lets you perform the following tasks:</span></span>

- <span data-ttu-id="3b8c0-106">Conectar os clientes aos ativos que eles possuem.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-106">Connect customers to the assets that they own.</span></span>
- <span data-ttu-id="3b8c0-107">Selecionar um cliente e exiba os ativos que o cliente possui ao criar uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-107">Select a customer and view the assets that customer owns when you create a work order.</span></span>
- <span data-ttu-id="3b8c0-108">Configurar um projeto pai para cada cliente.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-108">Set up a parent project for each customer.</span></span>
- <span data-ttu-id="3b8c0-109">Registrar horas, itens, despesas e taxas em relação à ordem de serviço e criar uma proposta de fatura para o cliente posteriormente.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-109">Register hours, items, expenses, and fees against the work order, and then create an invoice proposal for the customer later.</span></span>

<span data-ttu-id="3b8c0-110">Além disso, o recurso fornece as seguintes funcionalidades:</span><span class="sxs-lookup"><span data-stu-id="3b8c0-110">In addition, the feature provides the following functionality:</span></span>

- <span data-ttu-id="3b8c0-111">O contrato de projeto do projeto pai de um cliente é copiado automaticamente para o projeto de ordem de serviço relevante.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-111">The project contract from a customer's parent project is automatically copied to the relevant work order project.</span></span>
- <span data-ttu-id="3b8c0-112">O gerenciamento de ativos agora pode usar o tipo de transação de projeto *taxa* em previsões de ordem de serviço e diários de ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-112">Asset management can now use the *fee* project transaction type on both work order forecasts and work order journals.</span></span>

## <a name="turn-on-the-customer-billing-feature"></a><span data-ttu-id="3b8c0-113">Ativar o recurso de cobrança de cliente</span><span class="sxs-lookup"><span data-stu-id="3b8c0-113">Turn on the customer billing feature</span></span>

<span data-ttu-id="3b8c0-114">Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-114">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="3b8c0-115">Os administradores podem usar as configurações de [gerenciamento de recursos](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-115">Admins can use the [feature management](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="3b8c0-116">No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="3b8c0-116">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="3b8c0-117">**Módulo:** *gerenciamento e contabilidade do projeto*</span><span class="sxs-lookup"><span data-stu-id="3b8c0-117">**Module:** *Project management and accounting*</span></span>
- <span data-ttu-id="3b8c0-118">**Nome do recurso:** *cobrança da ordem de serviço*</span><span class="sxs-lookup"><span data-stu-id="3b8c0-118">**Feature name:** *Work order billing*</span></span>

## <a name="example-scenario"></a><span data-ttu-id="3b8c0-119">Cenário de exemplo</span><span class="sxs-lookup"><span data-stu-id="3b8c0-119">Example scenario</span></span>

<span data-ttu-id="3b8c0-120">Para saber como esse recurso funciona, veja o cenário de exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-120">To learn how this feature works, work through the following example scenario.</span></span>

<span data-ttu-id="3b8c0-121">Para trabalhar nesse cenário usando os registros e valores de exemplo especificados aqui, você deve usar um sistema em que os [dados de demonstração](../../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) padrão estejam instalados.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-121">To work through this scenario by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="3b8c0-122">Você deve selecionar a entidade legal **USMF** antes de começar.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-122">You must select the **USMF** legal entity before you begin.</span></span>

<span data-ttu-id="3b8c0-123">Você também pode usar este cenário como orientação para usar o recurso ao trabalhar em um sistema de produção.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-123">You can also use this scenario as guidance for using the feature when you work on a production system.</span></span> <span data-ttu-id="3b8c0-124">No entanto, nesse caso, você deve substituir seus próprios valores e talvez não tenha alguns tipos de registros necessários fornecidos pelos dados de demonstração padrão.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-124">However, in that case, you must substitute your own values, and you might be missing some types of required records that the standard demo data provides.</span></span>

### <a name="step-1-create-a-new-project-contract-for-the-customer"></a><span data-ttu-id="3b8c0-125">Etapa 1: criar um novo contrato de projeto para o cliente</span><span class="sxs-lookup"><span data-stu-id="3b8c0-125">Step 1: Create a new project contract for the customer</span></span>

1. <span data-ttu-id="3b8c0-126">Vá para **Gerenciamento e contabilidade de projeto \> Projetos \> Contratos do projeto**.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-126">Go to **Project management and accounting \> Projects \> Project contracts**.</span></span>
1. <span data-ttu-id="3b8c0-127">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-127">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="3b8c0-128">Na caixa de diálogo **Novo contrato de projeto**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="3b8c0-128">In the **New project contract** dialog box, set the following values:</span></span>

    - <span data-ttu-id="3b8c0-129">**Nome:** *atacados Pelican*</span><span class="sxs-lookup"><span data-stu-id="3b8c0-129">**Name:** *Pelican Wholesales*</span></span>
    - <span data-ttu-id="3b8c0-130">**Tipo de financiamento:** *cliente*</span><span class="sxs-lookup"><span data-stu-id="3b8c0-130">**Funding type:** *Customer*</span></span>
    - <span data-ttu-id="3b8c0-131">**Fonte de financiamento:** *EUA-013* (*Atacados Pelican*)</span><span class="sxs-lookup"><span data-stu-id="3b8c0-131">**Funding source:** *US-013* (*Pelican Wholesales*)</span></span>

1. <span data-ttu-id="3b8c0-132">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-132">Select **OK**.</span></span>

### <a name="step-2-create-a-new-parent-project-for-the-customer"></a><span data-ttu-id="3b8c0-133">Etapa 2: criar um novo projeto pai para o cliente</span><span class="sxs-lookup"><span data-stu-id="3b8c0-133">Step 2: Create a new parent project for the customer</span></span>

<span data-ttu-id="3b8c0-134">O projeto pai que você criar aqui será usado quando as ordens de serviços do cliente forem criadas.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-134">The parent project that you create here will be used when work orders for the customer are created.</span></span>

1. <span data-ttu-id="3b8c0-135">Vá para **Gerenciamento e contabilidade de projeto \> Projetos \> Todos os projetos**.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-135">Go to **Project management and accounting \> Projects \> All projects**.</span></span>
1. <span data-ttu-id="3b8c0-136">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-136">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="3b8c0-137">Na caixa de diálogo **Novo projeto**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="3b8c0-137">In the **New project** dialog box, set the following values:</span></span>

    - <span data-ttu-id="3b8c0-138">**Tipo de projeto:** *Tempo e material*</span><span class="sxs-lookup"><span data-stu-id="3b8c0-138">**Project type:** *Time and material*</span></span>
    - <span data-ttu-id="3b8c0-139">**Nome do projeto:** *ordens de serviço da Atacados Pelican*</span><span class="sxs-lookup"><span data-stu-id="3b8c0-139">**Project name:** *Pelican Wholesales work orders*</span></span>
    - <span data-ttu-id="3b8c0-140">**Grupo de projeto:** *TM*</span><span class="sxs-lookup"><span data-stu-id="3b8c0-140">**Project group:** *TM*</span></span>
    - <span data-ttu-id="3b8c0-141">**ID do contrato de projeto:** *Atacados Pelican* (o contrato criado anteriormente)</span><span class="sxs-lookup"><span data-stu-id="3b8c0-141">**Project contract ID:** *Pelican Wholesales* (the contract that you created earlier)</span></span>
    - <span data-ttu-id="3b8c0-142">**Data de início**: selecione a data de hoje.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-142">**Start date:** Select today's date.</span></span>

1. <span data-ttu-id="3b8c0-143">Selecione **Criar projeto**.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-143">Select **Create project**.</span></span>
1. <span data-ttu-id="3b8c0-144">O novo projeto é aberto.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-144">The new project is opened.</span></span> <span data-ttu-id="3b8c0-145">Anote o valor de **ID do projeto**.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-145">Make a note of the **Project ID** value.</span></span> <span data-ttu-id="3b8c0-146">Você terá que digitá-lo posteriormente.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-146">You will have to enter it later.</span></span>

### <a name="step-3-create-a-new-work-order-type-in-asset-management"></a><span data-ttu-id="3b8c0-147">Etapa 3: criar um novo tipo de ordem de serviço no Gerenciamento de ativos</span><span class="sxs-lookup"><span data-stu-id="3b8c0-147">Step 3: Create a new work order type in Asset management</span></span>

1. <span data-ttu-id="3b8c0-148">Vá para **Gerenciamento de Ativos \> Configuração \> Ordens de serviço \> Tipos de ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-148">Go to **Asset management \> Setup \> Work order \> Work order types**.</span></span>
1. <span data-ttu-id="3b8c0-149">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-149">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="3b8c0-150">Um novo registro é adicionada à lista.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-150">A new record is added to the list.</span></span> <span data-ttu-id="3b8c0-151">Defina os seguintes valores para ele:</span><span class="sxs-lookup"><span data-stu-id="3b8c0-151">Set the following values for it:</span></span>

    - <span data-ttu-id="3b8c0-152">**Tipo de ordem de serviço:** *Serviço*</span><span class="sxs-lookup"><span data-stu-id="3b8c0-152">**Work order type:** *Service*</span></span>
    - <span data-ttu-id="3b8c0-153">**Nome:** *ordens de serviço de serviço*</span><span class="sxs-lookup"><span data-stu-id="3b8c0-153">**Name:** *Service work orders*</span></span>
    - <span data-ttu-id="3b8c0-154">**Estado do ciclo de vida da ordem de serviço:** *Padrão*</span><span class="sxs-lookup"><span data-stu-id="3b8c0-154">**Work order lifecycle state:** *Standard*</span></span>

### <a name="step-4-link-the-customer-account-to-the-parent-project"></a><span data-ttu-id="3b8c0-155">Etapa 4: vincular a conta de cliente ao projeto pai</span><span class="sxs-lookup"><span data-stu-id="3b8c0-155">Step 4: Link the customer account to the parent project</span></span>

<span data-ttu-id="3b8c0-156">Agora, você deve vincular a conta de cliente ao projeto pai na configuração do projeto no Gerenciamento de ativos.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-156">You must now link the customer account to the parent project in the project setup in Asset management.</span></span>

1. <span data-ttu-id="3b8c0-157">Vá para **Gerenciamento de ativos \> Configuração \> Ordens de serviço \> Configuração de projeto**.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-157">Go to **Asset management \> Setup \> Work orders \> Project setup**.</span></span>
1. <span data-ttu-id="3b8c0-158">Na guia **Projeto pai**, selecione **Adicionar** para adicionar uma linha.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-158">On the **Parent project** tab, select **Add** to add a line.</span></span>
1. <span data-ttu-id="3b8c0-159">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="3b8c0-159">On the new line, set the following values:</span></span>

    - <span data-ttu-id="3b8c0-160">**Conta de cliente:** *US-013* (*Atacados Pelican*)</span><span class="sxs-lookup"><span data-stu-id="3b8c0-160">**Customer account:** *US-013* (*Pelican Wholesales*)</span></span>
    - <span data-ttu-id="3b8c0-161">**ID do projeto:** insira o ID de projeto que você anotou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-161">**Project ID:** Enter the project ID that you made a note of earlier.</span></span>

### <a name="step-5-link-the-project-group-and-type-to-the-work-order-project"></a><span data-ttu-id="3b8c0-162">Etapa 5: vincular o grupo e o tipo de projeto ao projeto da ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="3b8c0-162">Step 5: Link the project group and type to the work order project</span></span>

<span data-ttu-id="3b8c0-163">Você ainda deve estar na página **Configuração do projeto** (**Gerenciamento de ativos \> Configuração \> Ordens de serviço \> Configuração do projeto**).</span><span class="sxs-lookup"><span data-stu-id="3b8c0-163">You should still be on the **Project setup** page (**Asset management \> Setup \> Work orders \> Project setup**).</span></span>

1. <span data-ttu-id="3b8c0-164">Na guia **Grupo de projeto**, selecione **Adicionar** para adicionar uma linha.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-164">On the **Project group** tab, select **Add** to add a line.</span></span>
1. <span data-ttu-id="3b8c0-165">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="3b8c0-165">On the new line, set the following values:</span></span>

    - <span data-ttu-id="3b8c0-166">**Tipo de ordem de serviço:** *Serviço* (o tipo de ordem de serviço criado anteriormente)</span><span class="sxs-lookup"><span data-stu-id="3b8c0-166">**Work order type:** *Service* (the work order type that you created earlier)</span></span>
    - <span data-ttu-id="3b8c0-167">**Grupo de projeto:** *TM*</span><span class="sxs-lookup"><span data-stu-id="3b8c0-167">**Project group:** *TM*</span></span>

> [!NOTE]
> <span data-ttu-id="3b8c0-168">O contrato de projeto no projeto da ordem de serviço sempre é herdado do projeto pai.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-168">The project contract on the work order project is always inherited from the parent project.</span></span>

### <a name="step-6-link-an-asset-to-the-customer-id"></a><span data-ttu-id="3b8c0-169">Etapa 6: vincular um ativo ao ID do cliente</span><span class="sxs-lookup"><span data-stu-id="3b8c0-169">Step 6: Link an asset to the customer ID</span></span>

1. <span data-ttu-id="3b8c0-170">Vá para **Gerenciamento de ativos \> Ativos \> Ativos ativos**.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-170">Go to **Asset management \> Assets \> Active assets**.</span></span>
1. <span data-ttu-id="3b8c0-171">No campo **Filtro**, digite *VE-102* e selecione para filtrar por **Ativo**.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-171">In the **Filter** field, enter *VE-102*, and select to filter by **Asset**.</span></span>
1. <span data-ttu-id="3b8c0-172">Selecione o ativo para abrir suas configurações.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-172">Select the asset to open its settings.</span></span>
1. <span data-ttu-id="3b8c0-173">Na guia rápida **Cliente**, defina o campo **Conta do cliente** como *US-013* (*Atacados Pelican*).</span><span class="sxs-lookup"><span data-stu-id="3b8c0-173">On the **Customer** FastTab, set the **Customer account** field to *US-013* (*Pelican Wholesales*).</span></span>

    <span data-ttu-id="3b8c0-174">O campo **Nome** é atualizado automaticamente para *Atacados Pelican*.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-174">The **Name** field is automatically updated to *Pelican Wholesales*.</span></span>

### <a name="step-7-create-a-new-work-order-on-the-asset"></a><span data-ttu-id="3b8c0-175">Etapa 7: criar uma nova ordem de serviço no ativo</span><span class="sxs-lookup"><span data-stu-id="3b8c0-175">Step 7: Create a new work order on the asset</span></span>

1. <span data-ttu-id="3b8c0-176">Vá para **Gerenciamento de Ativos \> Ordens de serviço \> Ordens de serviço ativas**.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-176">Go to **Asset management \> Work orders \> Active work orders**.</span></span>
1. <span data-ttu-id="3b8c0-177">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-177">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="3b8c0-178">Na caixa de diálogo **Criar ordem de serviço**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="3b8c0-178">In the **Create work order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="3b8c0-179">**Tipo de ordem de serviço:** *Serviço*</span><span class="sxs-lookup"><span data-stu-id="3b8c0-179">**Work order type:** *Service*</span></span>
    - <span data-ttu-id="3b8c0-180">**Descrição:** *reparar caminhão*</span><span class="sxs-lookup"><span data-stu-id="3b8c0-180">**Description:** *Repair Truck*</span></span>
    - <span data-ttu-id="3b8c0-181">**Conta de cliente:** *US-013* (*Atacados Pelican*)</span><span class="sxs-lookup"><span data-stu-id="3b8c0-181">**Customer account:** *US-013* (*Pelican Wholesales*)</span></span>
    - <span data-ttu-id="3b8c0-182">**Ativo:** *VE-102*</span><span class="sxs-lookup"><span data-stu-id="3b8c0-182">**Asset:** *VE-102*</span></span>

        > [!NOTE]
        > <span data-ttu-id="3b8c0-183">A pesquisa mostra somente os ativos vinculados à conta de cliente selecionada.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-183">The lookup shows only assets that are linked to the selected customer account.</span></span>

    - <span data-ttu-id="3b8c0-184">**Tipo de trabalho de manutenção:** *Reparo*</span><span class="sxs-lookup"><span data-stu-id="3b8c0-184">**Maintenance job type:** *Repair*</span></span>
    - <span data-ttu-id="3b8c0-185">**Comércio:** *Mecânico*</span><span class="sxs-lookup"><span data-stu-id="3b8c0-185">**Trade:** *Mechanic*</span></span>
    - <span data-ttu-id="3b8c0-186">**Nível de serviço:** *4*</span><span class="sxs-lookup"><span data-stu-id="3b8c0-186">**Service level:** *4*</span></span>

1. <span data-ttu-id="3b8c0-187">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-187">Select **OK**.</span></span>

### <a name="step-8-review-the-work-order-and-start-to-work-on-it"></a><span data-ttu-id="3b8c0-188">Etapa 8: revisar a ordem de serviço e comece a trabalhar nela</span><span class="sxs-lookup"><span data-stu-id="3b8c0-188">Step 8: Review the work order and start to work on it</span></span>

<span data-ttu-id="3b8c0-189">Nesta seção, você trabalhará na ordem de serviço criada na seção anterior.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-189">In this section, you will work on the work order that you created in the previous section.</span></span>

1. <span data-ttu-id="3b8c0-190">Siga estas etapas para verificar se o projeto pai é o projeto *Ordem de serviço a Atacados Pelican*:</span><span class="sxs-lookup"><span data-stu-id="3b8c0-190">Follow these steps to verify that the parent project is the *Pelican wholesales Work order* project:</span></span>

    1. <span data-ttu-id="3b8c0-191">Na seção **Trabalhos de manutenção da ordem de serviço**, selecione uma linha.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-191">In the **Work order maintenance jobs** section, select a line.</span></span>
    1. <span data-ttu-id="3b8c0-192">Na guia rápida **Detalhes da linha**, inspecione o valor **ID do projeto**.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-192">On the **Line details** FastTab, inspect the **Project ID** value.</span></span> <span data-ttu-id="3b8c0-193">Ele deve ser um número de hifenização no formulário *\<Parent-Project-ID\>-\<Project-ID\>*.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-193">It should be a hyphenated number in the form *\<Parent-Project-ID\>-\<Project-ID\>*.</span></span> <span data-ttu-id="3b8c0-194">Esse valor é um link.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-194">This value is a link.</span></span>
    1. <span data-ttu-id="3b8c0-195">Selecione o link do ID do projeto para abrir uma página na qual é possível exibir os nomes do projeto e do projeto pai.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-195">Select the project ID link to open a page where you can view the parent project and project names.</span></span>

1. <span data-ttu-id="3b8c0-196">No Painel de Ação, na guia **Ordem de serviço**, no grupo **Estado de ciclo de vida**, selecione **Atualizar estado da ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-196">On the Action Pane, on the **Work order** tab, in the **Lifecycle state** group, select **Update work order state**.</span></span>
1. <span data-ttu-id="3b8c0-197">Na caixa de diálogo **Atualizar estado da ordem de serviço**, na coluna **Selecionar**, marque a caixa de seleção da linha na qual o campo **Estado de ciclo de vida** está definido como *Em andamento*.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-197">In the **Update work order state** dialog box, in the **Select** column, select the check box for the row where the **Lifecycle state** field is set to *In progress*.</span></span>
1. <span data-ttu-id="3b8c0-198">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-198">Select **OK**.</span></span>
1. <span data-ttu-id="3b8c0-199">Na caixa de diálogo **Estado do ciclo de vida: Em andamento**, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-199">In the **Lifecycle state: InProgress** dialog box, select **OK**.</span></span>

### <a name="step-9-post-the-hours-that-were-spent-on-the-work-order-and-create-a-new-invoice-proposal"></a><span data-ttu-id="3b8c0-200">Etapa 9: lançar as horas gastas na ordem de serviço e criar uma nova proposta de fatura</span><span class="sxs-lookup"><span data-stu-id="3b8c0-200">Step 9: Post the hours that were spent on the work order and create a new invoice proposal</span></span>

<span data-ttu-id="3b8c0-201">Nesta seção, você continuará trabalhando na ordem de serviço em que você trabalhou na seção anterior.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-201">In this section, you will continue to work on the work order that you worked on in the previous section.</span></span>

1. <span data-ttu-id="3b8c0-202">No Painel de Ação, na guia **Ordem de serviço**, no grupo **Projeto**, selecione **Diários**.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-202">On the Action Pane, on the **Work order** tab, in the **Project** group, select **Journals**.</span></span>

    <span data-ttu-id="3b8c0-203">A página **Diários de ordem de serviço** será exibida.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-203">The **Work order journals** page appears.</span></span> <span data-ttu-id="3b8c0-204">Aqui, você pode registrar o tempo gasto na ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-204">Here, you can register the time that you spent on the work order.</span></span>

1. <span data-ttu-id="3b8c0-205">Na guia rápida **Horas**, selecione **Adicionar linha**.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-205">On the **Hours** FastTab, select **Add line**.</span></span>
1. <span data-ttu-id="3b8c0-206">Na linha nova, defina o campo **Horas** como *4*.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-206">On the new, line, set the **Hours** field to *4*.</span></span>
1. <span data-ttu-id="3b8c0-207">No Painel de Ação, selecione **Lançar diários**.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-207">On the Action Pane, select **Post journals**.</span></span>
1. <span data-ttu-id="3b8c0-208">Feche a página **Diários de ordem de serviço** para retornar à ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-208">Close the **Work order journals** page to return to the work order.</span></span>
1. <span data-ttu-id="3b8c0-209">No Painel de ações, na guia **Faturamento**, selecione **Nova proposta de fatura**.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-209">On the Action Pane, on the **Invoicing** tab, select **New invoice proposal**.</span></span>
1. <span data-ttu-id="3b8c0-210">Na caixa de diálogo **Criar proposta de fatura**, na seção **Transações do projeto**, marque a caixa de seleção **Selecionar** para cada linha que você deseja faturar.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-210">In the **Create invoice proposal** dialog box, in the **Project transactions** section, select the **Select** check box for every line  that you want to invoice.</span></span>
1. <span data-ttu-id="3b8c0-211">Selecione **OK** para fechar a caixa de diálogo e exibir a nova proposta de fatura.</span><span class="sxs-lookup"><span data-stu-id="3b8c0-211">Select **OK** to close the dialog box and view the new invoice proposal.</span></span>

---
title: ​Configurações de cobertura​
description: Este tópico fornece informações sobre as configurações de cobertura que o agendamento do planejamento mestre usa para calcular os requisitos do item.
author: roxanadiaconu
manager: AnnBe
ms.date: 09/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8b8263afd8469d9bf3f566c4c44a5976d7ff3e86
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2019
ms.locfileid: "2815194"
---
# <a name="coverage-settings"></a><span data-ttu-id="68488-103">​Configurações de cobertura​</span><span class="sxs-lookup"><span data-stu-id="68488-103">Coverage settings</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="68488-104">O planejamento mestre usa configurações de cobertura para calcular requisitos de itens.</span><span class="sxs-lookup"><span data-stu-id="68488-104">Master scheduling uses coverage settings to calculate item requirements.</span></span>

<span data-ttu-id="68488-105">Você pode especificar as configurações de cobertura de várias formas:</span><span class="sxs-lookup"><span data-stu-id="68488-105">You can specify coverage settings in several ways:</span></span>

- <span data-ttu-id="68488-106">Especifique as configurações de cobertura para um grupo de cobertura.</span><span class="sxs-lookup"><span data-stu-id="68488-106">Specify coverage settings for a coverage group.</span></span>

    <span data-ttu-id="68488-107">Você pode criar um grupo de cobertura que contém configurações para todos os produtos vinculados ao grupo de cobertura.</span><span class="sxs-lookup"><span data-stu-id="68488-107">You can create a coverage group that contains settings for all products that are linked to the coverage group.</span></span> <span data-ttu-id="68488-108">Para criar um grupo de cobertura, vá para **Planejamento mestre &gt; Configuração &gt; Cobertura &gt; Grupos de cobertura**.</span><span class="sxs-lookup"><span data-stu-id="68488-108">To create a coverage group, go to **Master planning &gt; Setup &gt; Coverage &gt; Coverage groups**.</span></span> <span data-ttu-id="68488-109">Você pode vincular um grupo de cobertura a um produto.</span><span class="sxs-lookup"><span data-stu-id="68488-109">You can link a coverage group to a product.</span></span> <span data-ttu-id="68488-110">Se o link for específico de um site, um depósito ou uma dimensão de produto, use o campo **Grupo de cobertura** na página **Cobertura de item**.</span><span class="sxs-lookup"><span data-stu-id="68488-110">If the link is specific to a site, warehouse, or product dimension, use the **Coverage group** field on the **Item coverage** page.</span></span> <span data-ttu-id="68488-111">Se o link for genérico, independentemente das dimensões do produto, use o campo **Grupo de cobertura** na Guia Rápida **Plano** da página **Detalhes do produto**</span><span class="sxs-lookup"><span data-stu-id="68488-111">If the link is generic, regardless of the product dimensions, use the **Coverage group** field on the **Plan** FastTab of the **Product details** page.</span></span> <span data-ttu-id="68488-112">Por padrão, se você não vincular um grupo de cobertura a um produto, o planejamento mestre usará o grupo de cobertura geral especificado na página **Parâmetros de planejamento mestre**.</span><span class="sxs-lookup"><span data-stu-id="68488-112">By default, if you don't link a coverage group to a product, master planning uses the general coverage group that is specified on the **Master planning parameters** page.</span></span>

- <span data-ttu-id="68488-113">Especificar configurações de cobertura para um produto.</span><span class="sxs-lookup"><span data-stu-id="68488-113">Specify coverage settings for a product.</span></span>

    <span data-ttu-id="68488-114">Você pode criar configurações de cobertura para um produto específico.</span><span class="sxs-lookup"><span data-stu-id="68488-114">You can create coverage settings for a specific product.</span></span> <span data-ttu-id="68488-115">Vá para **Gerenciamento de informações do produto &gt; Produtos &gt; Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="68488-115">Go to **Product information management &gt; Products &gt; Released products**.</span></span> <span data-ttu-id="68488-116">Selecione o produto e, no Painel de Ação, na guia **Plano**, no grupo **Cobertura**, selecione **Cobertura de item** para abrir a página **Cobertura de item**.</span><span class="sxs-lookup"><span data-stu-id="68488-116">Select the product, and then, on the Action Pane, on the **Plan** tab, in the **Coverage** group, select **Item coverage** to open the **Item coverage** page.</span></span> <span data-ttu-id="68488-117">Se o produto já estiver vinculado a um grupo de cobertura, você poderá substituir as configurações do grupo de cobertura usando o campo **Substituir**.</span><span class="sxs-lookup"><span data-stu-id="68488-117">If the product is already linked to a coverage group, you can override the coverage group settings by using the **Override** field.</span></span> <span data-ttu-id="68488-118">As configurações de cobertura na página**Cobertura de item** têm precedência sobre as configurações da página **Grupo de cobertura**.</span><span class="sxs-lookup"><span data-stu-id="68488-118">The coverage settings on the **Item coverage** page take precedence over the settings on the **Coverage group** page.</span></span>

- <span data-ttu-id="68488-119">Especificar as configurações de cobertura para um produto usando um assistente.</span><span class="sxs-lookup"><span data-stu-id="68488-119">Specify coverage settings for a product by using a wizard.</span></span>

    <span data-ttu-id="68488-120">O assistente guia você passo a passo ao longo do processo de configuração dos principais parâmetros de cobertura do item.</span><span class="sxs-lookup"><span data-stu-id="68488-120">The wizard guides you step by step through the process of setting up the primary item coverage parameters.</span></span> <span data-ttu-id="68488-121">Na página **Cobertura de item**, no Painel de Ação, selecione **Assistente** para abrir o **Assistente de Cobertura de Item**.</span><span class="sxs-lookup"><span data-stu-id="68488-121">On the **Item coverage** page, on the Action Pane, select **Wizard** to open the **Item Coverage Wizard**.</span></span>

- <span data-ttu-id="68488-122">Especifique as configurações de cobertura para um grupo de dimensões.</span><span class="sxs-lookup"><span data-stu-id="68488-122">Specify coverage settings for a dimension group.</span></span>

    <span data-ttu-id="68488-123">Vá para **Gerenciamento de informações do produto &gt; Produtos &gt; Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="68488-123">Go to **Product information management &gt; Products &gt; Released products**.</span></span> <span data-ttu-id="68488-124">Na página **Detalhes do produto liberado**, na Guia Rápida **Geral**, na seção **Administração**, selecione o link no campo **Grupo de dimensões de armazenamento**.</span><span class="sxs-lookup"><span data-stu-id="68488-124">On the **Released product details** page, on the **General** FastTab, in the **Administration** section, select the link in the **Storage dimension group** field.</span></span> <span data-ttu-id="68488-125">Na página **Grupos de dimensões de armazenamento**, marque a caixa de seleção **Plano de cobertura por dimensão** para criar as configurações de cobertura de uma dimensão no grupo de dimensão de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="68488-125">On the **Storage dimension groups** page, select the **Coverage plan by dimension** check box to create the coverage settings for a dimension in the storage dimension group.</span></span> <span data-ttu-id="68488-126">O campo **Plano de cobertura por dimensão** deve ser selecionado para todas as dimensões do produto, como configuração, cor, tamanho e estilo.</span><span class="sxs-lookup"><span data-stu-id="68488-126">The **Coverage plan by dimension** field must be selected for all product dimensions, such as configuration, color, size, and style.</span></span>


## <a name="coverage-codes"></a><span data-ttu-id="68488-127">Códigos de cobertura</span><span class="sxs-lookup"><span data-stu-id="68488-127">Coverage codes</span></span>

<span data-ttu-id="68488-128">O planejamento mestre pode ser configurado para usar diversos métodos de reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="68488-128">Master planning can be configured to use different replenishment methods.</span></span> <span data-ttu-id="68488-129">Os métodos de reabastecimento ou métodos de dimensionamento de lote são as técnicas usadas pelo sistema para determinar o tamanho do lote de itens comprados ou fabricados.</span><span class="sxs-lookup"><span data-stu-id="68488-129">The replenishment methods or lot-sizing methods are the techniques used by the system to determine the batch size for purchased or produced items.</span></span> 

<span data-ttu-id="68488-130">A cada método de reabastecimento é atribuído um dos seguintes códigos de cobertura:</span><span class="sxs-lookup"><span data-stu-id="68488-130">Each replenishment method is assigned one of the following coverage codes:</span></span>

- <span data-ttu-id="68488-131">**Manual** - Método de dimensionamento de lote em que o sistema não sugere ordens de compra, transferência ou produção para o item.</span><span class="sxs-lookup"><span data-stu-id="68488-131">**Manual** - The lot-sizing method where the system does not suggest purchased, transfer, or production orders for the item.</span></span> <span data-ttu-id="68488-132">O planejador do item será responsável pela criação das ordens necessárias para o reabastecimento do item.</span><span class="sxs-lookup"><span data-stu-id="68488-132">The planner for the item will be in charge of creating the required orders for the replenishment of the item.</span></span>
- <span data-ttu-id="68488-133">**Por requisição** - Método de dimensionamento de lote em que o sistema cria uma ordem de compra, transferência ou produção planejada por requisição do item.</span><span class="sxs-lookup"><span data-stu-id="68488-133">**Per requirement** - The lot-sizing method in which the system creates a planned purchase, transfer, or production order per requirement for the item.</span></span> <span data-ttu-id="68488-134">Em geral, é usado para itens caros com demanda intermitente.</span><span class="sxs-lookup"><span data-stu-id="68488-134">This is generally used for expensive items with intermittent demand.</span></span>  
- <span data-ttu-id="68488-135">**Por período** - Método de dimensionamento de lote que combinando toda a demanda de um período em uma ordem do item.</span><span class="sxs-lookup"><span data-stu-id="68488-135">**Per period** - The lot-sizing method that combines all the demand for a period into one order for the item.</span></span> <span data-ttu-id="68488-136">A ordem será planejada para o primeiro dia do período e sua quantidade preencherá as requisições líquidas durante o período estabelecido.</span><span class="sxs-lookup"><span data-stu-id="68488-136">The order will be planned for the first day of the period and its quantity will fulfill the net requirements during the established period.</span></span> <span data-ttu-id="68488-137">O período começa com a primeira a demanda do item e abrange o tempo definido.</span><span class="sxs-lookup"><span data-stu-id="68488-137">The period starts with the first demand of the item and covers the defined length in time.</span></span> <span data-ttu-id="68488-138">O período seguinte começará com as requisições seguintes do item.</span><span class="sxs-lookup"><span data-stu-id="68488-138">The next period will start with the next requirements of the item.</span></span>
- <span data-ttu-id="68488-139">**Mín./máx.** - Método de dimensionamento de lote que contém o reabastecimento do estoque até um determinado nível quando o disponível previsto está abaixo de um limite.</span><span class="sxs-lookup"><span data-stu-id="68488-139">**Min/Max** - The lot-sizing method that contains the replenishment of inventory up to a certain level when the predicted on-hand is below a threshold.</span></span> <span data-ttu-id="68488-140">A quantidade do reabastecimento será a diferença entre o nível máximo e o nível disponível previsto.</span><span class="sxs-lookup"><span data-stu-id="68488-140">The replenishment quantity will be the difference between the maximum level and the predicted on-hand level.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="68488-141">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="68488-141">Additional resources</span></span>

[<span data-ttu-id="68488-142">Visão geral de planos mestres</span><span class="sxs-lookup"><span data-stu-id="68488-142">Master plans overview</span></span>](master-plans.md)

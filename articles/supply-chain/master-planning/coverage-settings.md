---
title: ​Configurações de cobertura​
description: Este tópico fornece informações sobre as configurações de cobertura que o agendamento do planejamento mestre usa para calcular os requisitos do item.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
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
ms.openlocfilehash: 99e094a7131b6d3a299fc72abd0141529908ddd2
ms.sourcegitcommit: 9e50bee6a67f0fe2fa6f86e02c7e8de16d0e2482
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2019
ms.locfileid: "1538885"
---
# <a name="coverage-settings"></a><span data-ttu-id="9e52c-103">​Configurações de cobertura​</span><span class="sxs-lookup"><span data-stu-id="9e52c-103">Coverage settings</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9e52c-104">O planejamento mestre usa configurações de cobertura para calcular requisitos de itens.</span><span class="sxs-lookup"><span data-stu-id="9e52c-104">Master scheduling uses coverage settings to calculate item requirements.</span></span>

<span data-ttu-id="9e52c-105">Você pode especificar as configurações de cobertura de várias formas:</span><span class="sxs-lookup"><span data-stu-id="9e52c-105">You can specify coverage settings in several ways:</span></span>

- <span data-ttu-id="9e52c-106">Especifique as configurações de cobertura para um grupo de cobertura.</span><span class="sxs-lookup"><span data-stu-id="9e52c-106">Specify coverage settings for a coverage group.</span></span>

    <span data-ttu-id="9e52c-107">Você pode criar um grupo de cobertura que contém configurações para todos os produtos vinculados ao grupo de cobertura.</span><span class="sxs-lookup"><span data-stu-id="9e52c-107">You can create a coverage group that contains settings for all products that are linked to the coverage group.</span></span> <span data-ttu-id="9e52c-108">Para criar um grupo de cobertura, vá para **Planejamento mestre &gt; Configuração &gt; Cobertura &gt; Grupos de cobertura**.</span><span class="sxs-lookup"><span data-stu-id="9e52c-108">To create a coverage group, go to **Master planning &gt; Setup &gt; Coverage &gt; Coverage groups**.</span></span> <span data-ttu-id="9e52c-109">Você pode vincular um grupo de cobertura a um produto.</span><span class="sxs-lookup"><span data-stu-id="9e52c-109">You can link a coverage group to a product.</span></span> <span data-ttu-id="9e52c-110">Se o link for específico de um site, um depósito ou uma dimensão de produto, use o campo **Grupo de cobertura** na página **Cobertura de item**.</span><span class="sxs-lookup"><span data-stu-id="9e52c-110">If the link is specific to a site, warehouse, or product dimension, use the **Coverage group** field on the **Item coverage** page.</span></span> <span data-ttu-id="9e52c-111">Se o link for genérico, independentemente das dimensões do produto, use o campo **Grupo de cobertura** na Guia Rápida **Plano** da página **Detalhes do produto**</span><span class="sxs-lookup"><span data-stu-id="9e52c-111">If the link is generic, regardless of the product dimensions, use the **Coverage group** field on the **Plan** FastTab of the **Product details** page.</span></span> <span data-ttu-id="9e52c-112">Por padrão, se você não vincular um grupo de cobertura a um produto, o planejamento mestre usará o grupo de cobertura geral especificado na página **Parâmetros de planejamento mestre**.</span><span class="sxs-lookup"><span data-stu-id="9e52c-112">By default, if you don't link a coverage group to a product, master planning uses the general coverage group that is specified on the **Master planning parameters** page.</span></span>

- <span data-ttu-id="9e52c-113">Especificar configurações de cobertura para um produto.</span><span class="sxs-lookup"><span data-stu-id="9e52c-113">Specify coverage settings for a product.</span></span>

    <span data-ttu-id="9e52c-114">Você pode criar configurações de cobertura para um produto específico.</span><span class="sxs-lookup"><span data-stu-id="9e52c-114">You can create coverage settings for a specific product.</span></span> <span data-ttu-id="9e52c-115">Vá para **Gerenciamento de informações do produto &gt; Produtos &gt; Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="9e52c-115">Go to **Product information management &gt; Products &gt; Released products**.</span></span> <span data-ttu-id="9e52c-116">Selecione o produto e, no Painel de Ação, na guia **Plano**, no grupo **Cobertura**, selecione **Cobertura de item** para abrir a página **Cobertura de item**.</span><span class="sxs-lookup"><span data-stu-id="9e52c-116">Select the product, and then, on the Action Pane, on the **Plan** tab, in the **Coverage** group, select **Item coverage** to open the **Item coverage** page.</span></span> <span data-ttu-id="9e52c-117">Se o produto já estiver vinculado a um grupo de cobertura, você poderá substituir as configurações do grupo de cobertura usando o campo **Substituir**.</span><span class="sxs-lookup"><span data-stu-id="9e52c-117">If the product is already linked to a coverage group, you can override the coverage group settings by using the **Override** field.</span></span> <span data-ttu-id="9e52c-118">As configurações de cobertura na página**Cobertura de item** têm precedência sobre as configurações da página **Grupo de cobertura**.</span><span class="sxs-lookup"><span data-stu-id="9e52c-118">The coverage settings on the **Item coverage** page take precedence over the settings on the **Coverage group** page.</span></span>

- <span data-ttu-id="9e52c-119">Especificar as configurações de cobertura para um produto usando um assistente.</span><span class="sxs-lookup"><span data-stu-id="9e52c-119">Specify coverage settings for a product by using a wizard.</span></span>

    <span data-ttu-id="9e52c-120">O assistente guia você passo a passo ao longo do processo de configuração dos principais parâmetros de cobertura do item.</span><span class="sxs-lookup"><span data-stu-id="9e52c-120">The wizard guides you step by step through the process of setting up the primary item coverage parameters.</span></span> <span data-ttu-id="9e52c-121">Na página **Cobertura de item**, no Painel de Ação, selecione **Assistente** para abrir o **Assistente de Cobertura de Item**.</span><span class="sxs-lookup"><span data-stu-id="9e52c-121">On the **Item coverage** page, on the Action Pane, select **Wizard** to open the **Item Coverage Wizard**.</span></span>

- <span data-ttu-id="9e52c-122">Especifique as configurações de cobertura para um grupo de dimensões.</span><span class="sxs-lookup"><span data-stu-id="9e52c-122">Specify coverage settings for a dimension group.</span></span>

    <span data-ttu-id="9e52c-123">Vá para **Gerenciamento de informações do produto &gt; Produtos &gt; Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="9e52c-123">Go to **Product information management &gt; Products &gt; Released products**.</span></span> <span data-ttu-id="9e52c-124">Na página **Detalhes do produto liberado**, na Guia Rápida **Geral**, na seção **Administração**, selecione o link no campo **Grupo de dimensões de armazenamento**.</span><span class="sxs-lookup"><span data-stu-id="9e52c-124">On the **Released product details** page, on the **General** FastTab, in the **Administration** section, select the link in the **Storage dimension group** field.</span></span> <span data-ttu-id="9e52c-125">Na página **Grupos de dimensões de armazenamento**, marque a caixa de seleção **Plano de cobertura por dimensão** para criar as configurações de cobertura de uma dimensão no grupo de dimensão de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="9e52c-125">On the **Storage dimension groups** page, select the **Coverage plan by dimension** check box to create the coverage settings for a dimension in the storage dimension group.</span></span> <span data-ttu-id="9e52c-126">O campo **Plano de cobertura por dimensão** deve ser selecionado para todas as dimensões do produto, como configuração, cor, tamanho e estilo.</span><span class="sxs-lookup"><span data-stu-id="9e52c-126">The **Coverage plan by dimension** field must be selected for all product dimensions, such as configuration, color, size, and style.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9e52c-127">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="9e52c-127">Additional resources</span></span>

[<span data-ttu-id="9e52c-128">Planos mestres</span><span class="sxs-lookup"><span data-stu-id="9e52c-128">Master plans</span></span>](master-plans.md)

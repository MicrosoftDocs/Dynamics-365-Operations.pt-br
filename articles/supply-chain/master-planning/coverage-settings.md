---
title: "Configurações de cobertura"
description: "O planejamento mestre usa configurações de cobertura para calcular requisitos de itens."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: bd85f89917659ac9c94590bace765b2123d6e556
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="coverage-settings"></a><span data-ttu-id="d44a9-103">Configurações de cobertura</span><span class="sxs-lookup"><span data-stu-id="d44a9-103">Coverage settings</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="d44a9-104">O planejamento mestre usa configurações de cobertura para calcular requisitos de itens.</span><span class="sxs-lookup"><span data-stu-id="d44a9-104">Master scheduling uses coverage settings to calculate item requirements.</span></span> 

<span data-ttu-id="d44a9-105">Você pode especificar as configurações de cobertura de várias formas:</span><span class="sxs-lookup"><span data-stu-id="d44a9-105">You can specify coverage settings in several ways:</span></span>

-   <span data-ttu-id="d44a9-106">Especifique as configurações de cobertura para um grupo de cobertura.</span><span class="sxs-lookup"><span data-stu-id="d44a9-106">Specify coverage settings for a coverage group.</span></span> <span data-ttu-id="d44a9-107">Você pode criar um grupo de cobertura que contém configurações para todos os produtos vinculados ao grupo de cobertura.</span><span class="sxs-lookup"><span data-stu-id="d44a9-107">You can create a coverage group that contains settings for all products that are linked to the coverage group.</span></span> <span data-ttu-id="d44a9-108">Clique em **Planejamento mestre &gt; Configuração &gt; Cobertura &gt; Grupos de cobertura** para criar um grupo de cobertura.</span><span class="sxs-lookup"><span data-stu-id="d44a9-108">Click **Master planning &gt; Setup &gt; Coverage &gt; Coverage groups** to create a coverage group.</span></span> <span data-ttu-id="d44a9-109">Você pode vincular um grupo de cobertura a um produto.</span><span class="sxs-lookup"><span data-stu-id="d44a9-109">You can link a coverage group to a product.</span></span> <span data-ttu-id="d44a9-110">Se o link for específico de um site, um depósito ou uma dimensão de produto, use o campo **Grupo de cobertura** na página **Cobertura de item**.</span><span class="sxs-lookup"><span data-stu-id="d44a9-110">If the link is specific to a site, warehouse, or product dimension, use the **Coverage group** field on the **Item coverage** page.</span></span> <span data-ttu-id="d44a9-111">Se o link for genérico, independentemente das dimensões do produto, use o **Grupo de cobertura** na Guia Rápida **Plano** na página **Detalhes do produto**</span><span class="sxs-lookup"><span data-stu-id="d44a9-111">If the link is generic, regardless of the product dimensions, use the **Coverage group** on the **Plan** FastTab on the **Product details** page.</span></span> <span data-ttu-id="d44a9-112">Se você não vincular um grupo de cobertura a um produto, o planejamento mestre usará como padrão o **Grupo de cobertura geral** especificado nos **Parâmetros de planejamento mestre** como o padrão.</span><span class="sxs-lookup"><span data-stu-id="d44a9-112">If you do not link a coverage group to a product, master planning uses the **General coverage group** that is specified on the **Master planning parameters** page as the default.</span></span>

-   <span data-ttu-id="d44a9-113">Especificar configurações de cobertura para um produto.</span><span class="sxs-lookup"><span data-stu-id="d44a9-113">Specify coverage settings for a product.</span></span> <span data-ttu-id="d44a9-114">Você pode criar configurações de cobertura para um produto específico.</span><span class="sxs-lookup"><span data-stu-id="d44a9-114">You can create coverage settings for a specific product.</span></span> <span data-ttu-id="d44a9-115">Clique em **Gerenciamento de informações do produto &gt; Produtos &gt; Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="d44a9-115">Click **Product information management &gt; Products &gt; Released products**.</span></span> <span data-ttu-id="d44a9-116">Selecione o produto, no **Painel de Ação**, na guia **Plano**, no **Grupo de cobertura**, clique em **Cobertura de item** para abrir a página **Cobertura de item**.</span><span class="sxs-lookup"><span data-stu-id="d44a9-116">Select the product, on the **Action Pane**, on the **Plan** tab, in the **Coverage group**, click **Item coverage** to open the **Item coverage** page.</span></span> <span data-ttu-id="d44a9-117">Se o produto já estiver vinculado a um grupo de cobertura, você poderá substituir as configurações do grupo de cobertura usando o campo **Substituir**.</span><span class="sxs-lookup"><span data-stu-id="d44a9-117">If the product is already linked to a coverage group, you can override the coverage group settings by using the **Override** field.</span></span> <span data-ttu-id="d44a9-118">As configurações de cobertura na página**Cobertura de item** têm precedência sobre as configurações da página **Grupo de cobertura**.</span><span class="sxs-lookup"><span data-stu-id="d44a9-118">The coverage settings on the **Item coverage** page take precedence over the settings on the **Coverage group** page.</span></span>

<!-- -->

-   <span data-ttu-id="d44a9-119">Especificar as configurações de cobertura para um produto usando um assistente.</span><span class="sxs-lookup"><span data-stu-id="d44a9-119">Specify coverage settings for a product by using a wizard.</span></span> <span data-ttu-id="d44a9-120">O assistente é um guia passo a passo que o ajuda a configurar os parâmetros principais de cobertura de item.</span><span class="sxs-lookup"><span data-stu-id="d44a9-120">The wizard is a step-by-step guide to help you set up the primary item coverage parameters.</span></span> <span data-ttu-id="d44a9-121">Na página **Cobertura de item**, clique em **Assistente** para abrir o **Assistente de Cobertura de Item**.</span><span class="sxs-lookup"><span data-stu-id="d44a9-121">On the **Item coverage** page, click **Wizard** to open the **Item Coverage Wizard**.</span></span>

<!-- -->

-   <span data-ttu-id="d44a9-122">Especifique as configurações de cobertura para um grupo de dimensões.</span><span class="sxs-lookup"><span data-stu-id="d44a9-122">Specify coverage settings for a dimension group.</span></span> <span data-ttu-id="d44a9-123">Clique em **Gerenciamento de informações do produto &gt; Comum &gt; Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="d44a9-123">Click **Product information management &gt; Common &gt; Released products**.</span></span> <span data-ttu-id="d44a9-124">Na página **Detalhes do produto liberado**, na guia **Geral**, no grupo **Administração**, clique no link **Grupo de dimensões de armazenamento**.</span><span class="sxs-lookup"><span data-stu-id="d44a9-124">On the **Released product detail **page, on the **General** tab, in the **Administration** group, click the **Storage dimension group** link.</span></span> <span data-ttu-id="d44a9-125">Na página **Grupo de dimensões de armazenamento**, selecione o campo **Plano de cobertura por dimensão** para criar as configurações de cobertura de uma dimensão no grupo de dimensão de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="d44a9-125">On the **Storage dimension group** page, select the **Coverage plan by dimension** field to create the coverage settings for a dimension in the storage dimension group.</span></span> <span data-ttu-id="d44a9-126">Todas as dimensões do produto, como a configuração, a cor, o tamanho, o estilo devem ter o campo **Plano de cobertura por dimensão** selecionado.</span><span class="sxs-lookup"><span data-stu-id="d44a9-126">All product dimensions, such as configuration, color, size, style, must have the **Coverage plan by dimension** field selected.</span></span>



<a name="see-also"></a><span data-ttu-id="d44a9-127">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d44a9-127">See also</span></span>
--------

[<span data-ttu-id="d44a9-128">Planejamentos mestres</span><span class="sxs-lookup"><span data-stu-id="d44a9-128">Master plans</span></span>](master-plans.md)





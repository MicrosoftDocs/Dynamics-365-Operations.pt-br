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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 591b1cd739bb3be61299f33f180ca7c264d21a35
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---

# <a name="coverage-settings"></a><span data-ttu-id="e76a8-103">Configurações de cobertura</span><span class="sxs-lookup"><span data-stu-id="e76a8-103">Coverage settings</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="e76a8-104">O planejamento mestre usa configurações de cobertura para calcular requisitos de itens.</span><span class="sxs-lookup"><span data-stu-id="e76a8-104">Master scheduling uses coverage settings to calculate item requirements.</span></span> 

<span data-ttu-id="e76a8-105">Você pode especificar as configurações de cobertura de várias formas:</span><span class="sxs-lookup"><span data-stu-id="e76a8-105">You can specify coverage settings in several ways:</span></span>

-   <span data-ttu-id="e76a8-106">Especifique as configurações de cobertura para um grupo de cobertura.</span><span class="sxs-lookup"><span data-stu-id="e76a8-106">Specify coverage settings for a coverage group.</span></span> <span data-ttu-id="e76a8-107">Você pode criar um grupo de cobertura que contém configurações para todos os produtos vinculados ao grupo de cobertura.</span><span class="sxs-lookup"><span data-stu-id="e76a8-107">You can create a coverage group that contains settings for all products that are linked to the coverage group.</span></span> <span data-ttu-id="e76a8-108">Clique em **Planejamento mestre &gt; Configuração &gt; Cobertura &gt; Grupos de cobertura** para criar um grupo de cobertura.</span><span class="sxs-lookup"><span data-stu-id="e76a8-108">Click **Master planning &gt; Setup &gt; Coverage &gt; Coverage groups** to create a coverage group.</span></span> <span data-ttu-id="e76a8-109">Você pode vincular um grupo de cobertura a um produto.</span><span class="sxs-lookup"><span data-stu-id="e76a8-109">You can link a coverage group to a product.</span></span> <span data-ttu-id="e76a8-110">Se o link for específico de um site, um depósito ou uma dimensão de produto, use o campo **Grupo de cobertura** na página **Cobertura de item**.</span><span class="sxs-lookup"><span data-stu-id="e76a8-110">If the link is specific to a site, warehouse, or product dimension, use the **Coverage group** field on the **Item coverage** page.</span></span> <span data-ttu-id="e76a8-111">Se o link for genérico, independentemente das dimensões do produto, use o **Grupo de cobertura** na Guia Rápida **Plano** na página **Detalhes do produto**</span><span class="sxs-lookup"><span data-stu-id="e76a8-111">If the link is generic, regardless of the product dimensions, use the **Coverage group** on the **Plan** FastTab on the **Product details** page.</span></span> <span data-ttu-id="e76a8-112">Se você não vincular um grupo de cobertura a um produto, o planejamento mestre usará como padrão o **Grupo de cobertura geral** especificado nos **Parâmetros de planejamento mestre** como o padrão.</span><span class="sxs-lookup"><span data-stu-id="e76a8-112">If you do not link a coverage group to a product, master planning uses the **General coverage group** that is specified on the **Master planning parameters** page as the default.</span></span>

-   <span data-ttu-id="e76a8-113">Especificar configurações de cobertura para um produto.</span><span class="sxs-lookup"><span data-stu-id="e76a8-113">Specify coverage settings for a product.</span></span> <span data-ttu-id="e76a8-114">Você pode criar configurações de cobertura para um produto específico.</span><span class="sxs-lookup"><span data-stu-id="e76a8-114">You can create coverage settings for a specific product.</span></span> <span data-ttu-id="e76a8-115">Clique em **Gerenciamento de informações do produto &gt; Produtos &gt; Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="e76a8-115">Click **Product information management &gt; Products &gt; Released products**.</span></span> <span data-ttu-id="e76a8-116">Selecione o produto, no **Painel de Ação**, na guia **Plano**, no **Grupo de cobertura**, clique em **Cobertura de item** para abrir a página **Cobertura de item**.</span><span class="sxs-lookup"><span data-stu-id="e76a8-116">Select the product, on the **Action Pane**, on the **Plan** tab, in the **Coverage group**, click **Item coverage** to open the **Item coverage** page.</span></span> <span data-ttu-id="e76a8-117">Se o produto já estiver vinculado a um grupo de cobertura, você poderá substituir as configurações do grupo de cobertura usando o campo **Substituir**.</span><span class="sxs-lookup"><span data-stu-id="e76a8-117">If the product is already linked to a coverage group, you can override the coverage group settings by using the **Override** field.</span></span> <span data-ttu-id="e76a8-118">As configurações de cobertura na página**Cobertura de item** têm precedência sobre as configurações da página **Grupo de cobertura**.</span><span class="sxs-lookup"><span data-stu-id="e76a8-118">The coverage settings on the **Item coverage** page take precedence over the settings on the **Coverage group** page.</span></span>

<!-- -->

-   <span data-ttu-id="e76a8-119">Especificar as configurações de cobertura para um produto usando um assistente.</span><span class="sxs-lookup"><span data-stu-id="e76a8-119">Specify coverage settings for a product by using a wizard.</span></span> <span data-ttu-id="e76a8-120">O assistente é um guia passo a passo que o ajuda a configurar os parâmetros principais de cobertura de item.</span><span class="sxs-lookup"><span data-stu-id="e76a8-120">The wizard is a step-by-step guide to help you set up the primary item coverage parameters.</span></span> <span data-ttu-id="e76a8-121">Na página **Cobertura de item**, clique em **Assistente** para abrir o **Assistente de Cobertura de Item**.</span><span class="sxs-lookup"><span data-stu-id="e76a8-121">On the **Item coverage** page, click **Wizard** to open the **Item Coverage Wizard**.</span></span>

<!-- -->

- <span data-ttu-id="e76a8-122">Especifique as configurações de cobertura para um grupo de dimensões.</span><span class="sxs-lookup"><span data-stu-id="e76a8-122">Specify coverage settings for a dimension group.</span></span> <span data-ttu-id="e76a8-123">Clique em <strong>Gerenciamento de informações do produto &gt; Comum &gt; Produtos liberados</strong>.</span><span class="sxs-lookup"><span data-stu-id="e76a8-123">Click <strong>Product information management &gt; Common &gt; Released products</strong>.</span></span> <span data-ttu-id="e76a8-124">Na página <strong>Detalhes do produto liberado **, na guia **Geral</strong>, no grupo <strong>Administração</strong>, clique no link <strong>Grupo de dimensões de armazenamento</strong>.</span><span class="sxs-lookup"><span data-stu-id="e76a8-124">On the <strong>Released product detail **page, on the **General</strong> tab, in the <strong>Administration</strong> group, click the <strong>Storage dimension group</strong> link.</span></span> <span data-ttu-id="e76a8-125">Na página <strong>Grupo de dimensões de armazenamento</strong>, selecione o campo <strong>Plano de cobertura por dimensão</strong> para criar as configurações de cobertura de uma dimensão no grupo de dimensão de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="e76a8-125">On the <strong>Storage dimension group</strong> page, select the <strong>Coverage plan by dimension</strong> field to create the coverage settings for a dimension in the storage dimension group.</span></span> <span data-ttu-id="e76a8-126">Todas as dimensões do produto, como a configuração, a cor, o tamanho, o estilo devem ter o campo <strong>Plano de cobertura por dimensão</strong> selecionado.</span><span class="sxs-lookup"><span data-stu-id="e76a8-126">All product dimensions, such as configuration, color, size, style, must have the <strong>Coverage plan by dimension</strong> field selected.</span></span>



<a name="see-also"></a><span data-ttu-id="e76a8-127">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e76a8-127">See also</span></span>
--------

[<span data-ttu-id="e76a8-128">Planejamentos mestres</span><span class="sxs-lookup"><span data-stu-id="e76a8-128">Master plans</span></span>](master-plans.md)





---
title: Completar instalação básica de um produto mestre lançado
description: Este tópico mostra como concluir a configuração mínima necessária antes de o produto mestre ser usado em versões de BOM.
author: ShylaThompson
manager: AnnBe
ms.date: 07/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventTableInventoryDimensionGroups, InventItemOrderSetup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f93f3db022b7b338bfa18ff6aea79f8086ea997f
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3147919"
---
# <a name="complete-basic-setup-of-a-released-product-master"></a><span data-ttu-id="f3919-103">Completar instalação básica de um produto mestre lançado</span><span class="sxs-lookup"><span data-stu-id="f3919-103">Complete basic setup of a released product master</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f3919-104">Este tópico mostra como concluir a configuração mínima necessária antes de o produto mestre ser usado em versões de BOM.</span><span class="sxs-lookup"><span data-stu-id="f3919-104">This topic shows how to complete the minimum setup that is required before the product master can be used in BOM versions.</span></span>

<span data-ttu-id="f3919-105">Este é o terceiro procedimento dos oito que explicam como criar combinações para configuração baseada em dimensão.</span><span class="sxs-lookup"><span data-stu-id="f3919-105">This is the third procedure out of eight which explains how to build combinations for dimension-based configuration.</span></span> <span data-ttu-id="f3919-106">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="f3919-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="f3919-107">Vá para **Painel de Navegação > Módulos > Gerenciamento de informações do produto > Produtos > Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="f3919-107">Go to **Navigation pane > Modules > Product information management > Products > Released products**.</span></span>
2. <span data-ttu-id="f3919-108">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="f3919-108">In the list, find and select the desired record.</span></span> <span data-ttu-id="f3919-109">Selecione o produto mestre que você liberou no segundo procedimento.</span><span class="sxs-lookup"><span data-stu-id="f3919-109">Select the product master that you have released in the second procedure.</span></span> <span data-ttu-id="f3919-110">Esse produto mestre foi criado com a tecnologia de configuração baseada em dimensão.</span><span class="sxs-lookup"><span data-stu-id="f3919-110">This product master is created with the dimension-based configuration technology.</span></span>  
3. <span data-ttu-id="f3919-111">No Painel de Ação, selecione **Produto**.</span><span class="sxs-lookup"><span data-stu-id="f3919-111">On the Action Pane, select **Product**.</span></span>
4. <span data-ttu-id="f3919-112">Selecione **Grupos de dimensões** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="f3919-112">Select **Dimension groups** to open the drop dialog.</span></span>
5. <span data-ttu-id="f3919-113">No campo **Grupo de dimensões de armazenamento**, selecione o botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f3919-113">In the **Storage dimension group** field, select the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="f3919-114">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="f3919-114">In the list, find and select the desired record.</span></span> <span data-ttu-id="f3919-115">O grupo dimensões de armazenamento determina quais dimensões de armazenamento são usadas na transação do produto.</span><span class="sxs-lookup"><span data-stu-id="f3919-115">The storage dimension group determines which storage dimensions are used for product transaction.</span></span> <span data-ttu-id="f3919-116">Selecione **Site** para esse procedimento.</span><span class="sxs-lookup"><span data-stu-id="f3919-116">Select **Site** for this procedure.</span></span>  
7. <span data-ttu-id="f3919-117">No campo **Grupo de dimensões de rastreamento**, selecione o botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f3919-117">In the **Tracking dimension group** field, select the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="f3919-118">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="f3919-118">In the list, find and select the desired record.</span></span> <span data-ttu-id="f3919-119">O grupo dimensões de rastreamento determina quais dimensões de rastreamento são usadas na transação do produto.</span><span class="sxs-lookup"><span data-stu-id="f3919-119">The tracking dimension group determines which tracking dimensions are used for product transaction.</span></span> <span data-ttu-id="f3919-120">Selecione **Nenhum** para esse procedimento.</span><span class="sxs-lookup"><span data-stu-id="f3919-120">Select **None** for this procedure.</span></span>  
9. <span data-ttu-id="f3919-121">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3919-121">Click **OK**.</span></span>
10. <span data-ttu-id="f3919-122">Clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f3919-122">Click **Edit**.</span></span>
11. <span data-ttu-id="f3919-123">No campo **Grupo de modelos do item**, selecione o botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f3919-123">In the **Item model group** field, select the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="f3919-124">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="f3919-124">In the list, find and select the desired record.</span></span> <span data-ttu-id="f3919-125">Os grupos de modelo de item contêm configurações que determinam como os itens são controlados e processados em recebimentos e saídas.</span><span class="sxs-lookup"><span data-stu-id="f3919-125">Item model groups contain settings that determine how items are controlled and handled on item receipts and issues.</span></span> <span data-ttu-id="f3919-126">Eles também determinam como o consumo de itens é calculado.</span><span class="sxs-lookup"><span data-stu-id="f3919-126">They also determine how item consumption is calculated.</span></span> <span data-ttu-id="f3919-127">Selecione **FIFO** para esse procedimento.</span><span class="sxs-lookup"><span data-stu-id="f3919-127">Select **FIFO** for this procedure.</span></span>  
13. <span data-ttu-id="f3919-128">Expanda a seção **Gerenciar custos**.</span><span class="sxs-lookup"><span data-stu-id="f3919-128">Expand the **Manage costs** section.</span></span>
14. <span data-ttu-id="f3919-129">No campo **Grupo de itens**, selecione o botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f3919-129">In the **Item group** field, select the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="f3919-130">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="f3919-130">In the list, find and select the desired record.</span></span> <span data-ttu-id="f3919-131">Os grupos de itens são usados para gerenciar o estoque, dividindo os itens de estoque em grupos.</span><span class="sxs-lookup"><span data-stu-id="f3919-131">Item groups are used to manage inventory by dividing inventory items into groups.</span></span> <span data-ttu-id="f3919-132">Selecione **CarAudio** para esse procedimento.</span><span class="sxs-lookup"><span data-stu-id="f3919-132">Select **CarAudio** for this procedure.</span></span>  
16. <span data-ttu-id="f3919-133">No Painel de Ações, selecione **Plano**.</span><span class="sxs-lookup"><span data-stu-id="f3919-133">On the Action Pane, select **Plan**.</span></span>
17. <span data-ttu-id="f3919-134">Selecione **Configurações de ordem padrão**.</span><span class="sxs-lookup"><span data-stu-id="f3919-134">Select **Default order settings**.</span></span>
18. <span data-ttu-id="f3919-135">No campo **Tipo de ordem padrão**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="f3919-135">In the **Default order type field**, select an option.</span></span> <span data-ttu-id="f3919-136">Selecione **Produção** para especificar que a opção de fornecimento padrão para esse produto mestre é produzi-lo.</span><span class="sxs-lookup"><span data-stu-id="f3919-136">Select **Production** to specify that the default supply option for this product master is to produce it.</span></span>  
19. <span data-ttu-id="f3919-137">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f3919-137">Select **Save**.</span></span>
20. <span data-ttu-id="f3919-138">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f3919-138">Close the page.</span></span>
21. <span data-ttu-id="f3919-139">Feche o formulário **Detalhes do produto liberado**.</span><span class="sxs-lookup"><span data-stu-id="f3919-139">Close the **Released product details** form.</span></span>


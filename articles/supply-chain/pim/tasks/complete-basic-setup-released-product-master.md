---
title: Completar instalação básica de um produto mestre lançado
description: Este tópico mostra como concluir a configuração mínima necessária antes de o produto mestre ser usado em versões de BOM.
author: ShylaThompson
manager: tfehr
ms.date: 07/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventTableInventoryDimensionGroups, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 668b60efa55fa553cf308d5bfc5da7e23f460366
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4987020"
---
# <a name="complete-basic-setup-of-a-released-product-master"></a><span data-ttu-id="cd364-103">Completar instalação básica de um produto mestre lançado</span><span class="sxs-lookup"><span data-stu-id="cd364-103">Complete basic setup of a released product master</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="cd364-104">Este tópico mostra como concluir a configuração mínima necessária antes de o produto mestre ser usado em versões de BOM.</span><span class="sxs-lookup"><span data-stu-id="cd364-104">This topic shows how to complete the minimum setup that is required before the product master can be used in BOM versions.</span></span>

<span data-ttu-id="cd364-105">Este é o terceiro procedimento dos oito que explicam como criar combinações para configuração baseada em dimensão.</span><span class="sxs-lookup"><span data-stu-id="cd364-105">This is the third procedure out of eight which explains how to build combinations for dimension-based configuration.</span></span> <span data-ttu-id="cd364-106">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="cd364-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="cd364-107">Vá para **Painel de Navegação > Módulos > Gerenciamento de informações do produto > Produtos > Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="cd364-107">Go to **Navigation pane > Modules > Product information management > Products > Released products**.</span></span>
2. <span data-ttu-id="cd364-108">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="cd364-108">In the list, find and select the desired record.</span></span> <span data-ttu-id="cd364-109">Selecione o produto mestre que você liberou no segundo procedimento.</span><span class="sxs-lookup"><span data-stu-id="cd364-109">Select the product master that you have released in the second procedure.</span></span> <span data-ttu-id="cd364-110">Esse produto mestre foi criado com a tecnologia de configuração baseada em dimensão.</span><span class="sxs-lookup"><span data-stu-id="cd364-110">This product master is created with the dimension-based configuration technology.</span></span>  
3. <span data-ttu-id="cd364-111">No Painel de Ação, selecione **Produto**.</span><span class="sxs-lookup"><span data-stu-id="cd364-111">On the Action Pane, select **Product**.</span></span>
4. <span data-ttu-id="cd364-112">Selecione **Grupos de dimensões** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="cd364-112">Select **Dimension groups** to open the drop dialog.</span></span>
5. <span data-ttu-id="cd364-113">No campo **Grupo de dimensões de armazenamento**, selecione o botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="cd364-113">In the **Storage dimension group** field, select the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="cd364-114">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="cd364-114">In the list, find and select the desired record.</span></span> <span data-ttu-id="cd364-115">O grupo dimensões de armazenamento determina quais dimensões de armazenamento são usadas na transação do produto.</span><span class="sxs-lookup"><span data-stu-id="cd364-115">The storage dimension group determines which storage dimensions are used for product transaction.</span></span> <span data-ttu-id="cd364-116">Selecione **Site** para esse procedimento.</span><span class="sxs-lookup"><span data-stu-id="cd364-116">Select **Site** for this procedure.</span></span>  
7. <span data-ttu-id="cd364-117">No campo **Grupo de dimensões de rastreamento**, selecione o botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="cd364-117">In the **Tracking dimension group** field, select the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="cd364-118">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="cd364-118">In the list, find and select the desired record.</span></span> <span data-ttu-id="cd364-119">O grupo dimensões de rastreamento determina quais dimensões de rastreamento são usadas na transação do produto.</span><span class="sxs-lookup"><span data-stu-id="cd364-119">The tracking dimension group determines which tracking dimensions are used for product transaction.</span></span> <span data-ttu-id="cd364-120">Selecione **Nenhum** para esse procedimento.</span><span class="sxs-lookup"><span data-stu-id="cd364-120">Select **None** for this procedure.</span></span>  
9. <span data-ttu-id="cd364-121">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="cd364-121">Click **OK**.</span></span>
10. <span data-ttu-id="cd364-122">Clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="cd364-122">Click **Edit**.</span></span>
11. <span data-ttu-id="cd364-123">No campo **Grupo de modelos do item**, selecione o botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="cd364-123">In the **Item model group** field, select the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="cd364-124">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="cd364-124">In the list, find and select the desired record.</span></span> <span data-ttu-id="cd364-125">Os grupos de modelo de item contêm configurações que determinam como os itens são controlados e processados em recebimentos e saídas.</span><span class="sxs-lookup"><span data-stu-id="cd364-125">Item model groups contain settings that determine how items are controlled and handled on item receipts and issues.</span></span> <span data-ttu-id="cd364-126">Eles também determinam como o consumo de itens é calculado.</span><span class="sxs-lookup"><span data-stu-id="cd364-126">They also determine how item consumption is calculated.</span></span> <span data-ttu-id="cd364-127">Selecione **FIFO** para esse procedimento.</span><span class="sxs-lookup"><span data-stu-id="cd364-127">Select **FIFO** for this procedure.</span></span>  
13. <span data-ttu-id="cd364-128">Expanda a seção **Gerenciar custos**.</span><span class="sxs-lookup"><span data-stu-id="cd364-128">Expand the **Manage costs** section.</span></span>
14. <span data-ttu-id="cd364-129">No campo **Grupo de itens**, selecione o botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="cd364-129">In the **Item group** field, select the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="cd364-130">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="cd364-130">In the list, find and select the desired record.</span></span> <span data-ttu-id="cd364-131">Os grupos de itens são usados para gerenciar o estoque, dividindo os itens de estoque em grupos.</span><span class="sxs-lookup"><span data-stu-id="cd364-131">Item groups are used to manage inventory by dividing inventory items into groups.</span></span> <span data-ttu-id="cd364-132">Selecione **CarAudio** para esse procedimento.</span><span class="sxs-lookup"><span data-stu-id="cd364-132">Select **CarAudio** for this procedure.</span></span>  
16. <span data-ttu-id="cd364-133">No Painel de Ações, selecione **Plano**.</span><span class="sxs-lookup"><span data-stu-id="cd364-133">On the Action Pane, select **Plan**.</span></span>
17. <span data-ttu-id="cd364-134">Selecione **Configurações de ordem padrão**.</span><span class="sxs-lookup"><span data-stu-id="cd364-134">Select **Default order settings**.</span></span>
18. <span data-ttu-id="cd364-135">No campo **Tipo de ordem padrão**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="cd364-135">In the **Default order type field**, select an option.</span></span> <span data-ttu-id="cd364-136">Selecione **Produção** para especificar que a opção de fornecimento padrão para esse produto mestre é produzi-lo.</span><span class="sxs-lookup"><span data-stu-id="cd364-136">Select **Production** to specify that the default supply option for this product master is to produce it.</span></span>  
19. <span data-ttu-id="cd364-137">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="cd364-137">Select **Save**.</span></span>
20. <span data-ttu-id="cd364-138">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="cd364-138">Close the page.</span></span>
21. <span data-ttu-id="cd364-139">Feche o formulário **Detalhes do produto liberado**.</span><span class="sxs-lookup"><span data-stu-id="cd364-139">Close the **Released product details** form.</span></span>


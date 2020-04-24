---
title: Crie ativos com base em ordens de compra
description: Este tópico explica como criar uma lista de itens de ativo que pode ser usada como base para a criação de ativos para trabalhos de manutenção em Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8dd52d877ee7f862577d8bfea113f22eca03c597
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3209872"
---
# <a name="create-assets-based-on-purchase-orders"></a><span data-ttu-id="a1ff3-103">Crie ativos com base em ordens de compra</span><span class="sxs-lookup"><span data-stu-id="a1ff3-103">Create assets based on purchase orders</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="a1ff3-104">Este tópico explica como criar uma lista de itens de ativo que pode ser usada como base para a criação de ativos para trabalhos de manutenção em Gerenciamento de Ativos.</span><span class="sxs-lookup"><span data-stu-id="a1ff3-104">This topic explains how you can create a list of asset items that can be used as a basis for creating assets for maintenance jobs in Asset Management.</span></span> <span data-ttu-id="a1ff3-105">Com base nos itens de ativos, você pode exibir uma lista das linhas de ordem de compra criadas nesses itens.</span><span class="sxs-lookup"><span data-stu-id="a1ff3-105">Based on the asset items, you are able to view a list of the purchase order lines that have been created on those items.</span></span> <span data-ttu-id="a1ff3-106">O objetivo dessa funcionalidade é criar facilmente um ativo em Gerenciamento de Ativos com base em uma ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="a1ff3-106">The purpose of this functionality is to easily create an asset in Asset Management based on a purchase order.</span></span>

<span data-ttu-id="a1ff3-107">Primeiro, você configura os itens a serem usados para a criação de ativos de uma ordem de compra em **Itens de ativo**.</span><span class="sxs-lookup"><span data-stu-id="a1ff3-107">First, you set up the items to be used for creating assets from a purchase order in **Asset items**.</span></span> <span data-ttu-id="a1ff3-108">Após criar uma linha de ordem de compra, você cria os ativos em **Ativos pendentes**.</span><span class="sxs-lookup"><span data-stu-id="a1ff3-108">After creating a purchase order line, you create the assets in **Pending assets**.</span></span> <span data-ttu-id="a1ff3-109">É possível decidir em que estágio da ordem de compra o ativo deve ser criado.</span><span class="sxs-lookup"><span data-stu-id="a1ff3-109">It is possible to decide at which stage of the purchase order the asset should be created.</span></span>


## <a name="select-asset-items"></a><span data-ttu-id="a1ff3-110">Selecione itens do ativo</span><span class="sxs-lookup"><span data-stu-id="a1ff3-110">Select asset items</span></span>

1. <span data-ttu-id="a1ff3-111">Clique em **Gerenciamento de ativos** > **Configuração** > **Ativos** > **Itens**.</span><span class="sxs-lookup"><span data-stu-id="a1ff3-111">Click **Asset management** > **Setup** > **Assets** > **Items**.</span></span>
2. <span data-ttu-id="a1ff3-112">Clique em **Novo** para criar um novo item de ativo.</span><span class="sxs-lookup"><span data-stu-id="a1ff3-112">Click **New** to create a new asset item.</span></span>
3. <span data-ttu-id="a1ff3-113">Selecione o item no campo **Número do item**.</span><span class="sxs-lookup"><span data-stu-id="a1ff3-113">Select the item in the **Item number** field.</span></span> <span data-ttu-id="a1ff3-114">Quando você deixar esse campo, o nome do item será automaticamente inserido no campo **Nome do produto**.</span><span class="sxs-lookup"><span data-stu-id="a1ff3-114">When you leave that field, the item name is automatically inserted in the **Product name** field.</span></span>
4. <span data-ttu-id="a1ff3-115">Na Guia Rápida **Geral**, selecione um tipo de ativo para o item.</span><span class="sxs-lookup"><span data-stu-id="a1ff3-115">On the **General** FastTab, select an asset type for the item.</span></span>
5. <span data-ttu-id="a1ff3-116">Selecione o fabricante do ativo e o modelo do item.</span><span class="sxs-lookup"><span data-stu-id="a1ff3-116">Select asset manufacturer and model for the item.</span></span>
6. <span data-ttu-id="a1ff3-117">Salve o item.</span><span class="sxs-lookup"><span data-stu-id="a1ff3-117">Save the item.</span></span>


## <a name="create-assets-from-pending-assets"></a><span data-ttu-id="a1ff3-118">Crie ativos a partir de ativos pendentes</span><span class="sxs-lookup"><span data-stu-id="a1ff3-118">Create assets from pending assets</span></span>

1. <span data-ttu-id="a1ff3-119">Clique em **Gerenciamento de ativos** > **Comum** > **Ativos** > **Ativos Pendentes**.</span><span class="sxs-lookup"><span data-stu-id="a1ff3-119">Click **Asset management** > **Common** > **Assets** > **Pending Assets**.</span></span>
2. <span data-ttu-id="a1ff3-120">Você verá uma lista atualizada das ordens de compra com base nos itens selecionados em **Itens de ativo**.</span><span class="sxs-lookup"><span data-stu-id="a1ff3-120">You will see an updated list of the purchase orders based on the items selected in **Asset items**.</span></span>
3. <span data-ttu-id="a1ff3-121">Você pode filtrar o status de ordens de compra para selecionar em que estado do ciclo de vida o ativo deve ser criado.</span><span class="sxs-lookup"><span data-stu-id="a1ff3-121">You can filter the status of purchase orders to select at which lifecycle state the asset should be created.</span></span> <span data-ttu-id="a1ff3-122">Por exemplo, talvez você só queira criar ativos quando o recebimento de um produto for lançado em uma ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="a1ff3-122">For example, you may only want to create assets when a product receipt has been posted on a purchase order.</span></span>
4. <span data-ttu-id="a1ff3-123">Selecione o link **Número de referência** em uma linha de ordem de compra para exibir informações detalhadas sobre o item.</span><span class="sxs-lookup"><span data-stu-id="a1ff3-123">Select the **Reference number** link on a purchase order line to view detailed information about the item.</span></span>
5. <span data-ttu-id="a1ff3-124">Se desejar editar as dimensões que serão exibidas na Guia Rápida **Dimensões de estoque**, clique no botão **Exibir Dimensões** e faça seleções.</span><span class="sxs-lookup"><span data-stu-id="a1ff3-124">If you want to edit which dimensions are displayed on the **Inventory dimensions** FastTab, click the **Display Dimensions** button, and make your selections.</span></span>
6. <span data-ttu-id="a1ff3-125">Se desejar criar um ativo com base em uma linha de ordem de compra, marque a caixa de seleção na coluna **Marcar** para essa linha na página de lista e clique em **Criar ativos**.</span><span class="sxs-lookup"><span data-stu-id="a1ff3-125">If you want to create an asset based on a purchase order line, select the check box in the **Mark** column for that line on the list page, and click **Create assets**.</span></span> <span data-ttu-id="a1ff3-126">Uma mensagem será exibida, informando a ID do ativo.</span><span class="sxs-lookup"><span data-stu-id="a1ff3-126">A message will be displayed informing you of the asset ID.</span></span>
7. <span data-ttu-id="a1ff3-127">Selecione o ativo na lista **Todos os ativos** e clique em **Editar** para adicionar mais informações ao ativo.</span><span class="sxs-lookup"><span data-stu-id="a1ff3-127">Select the asset in the **All assets** list and click **Edit** to add more information to the asset.</span></span>
8. <span data-ttu-id="a1ff3-128">Em **Ativos pendentes**, se desejar excluir uma linha porque você não deseja criar um ativo, marque a caixa de seleção na coluna **Marcar** para essa linha e clique em **Descartar ativos pendentes**.</span><span class="sxs-lookup"><span data-stu-id="a1ff3-128">In **Pending assets**, if you want to delete a line because you don't want to create an asset, select the check box in the **Mark** column for that line, and click **Discard pending assets**.</span></span> <span data-ttu-id="a1ff3-129">Uma mensagem será exibida, informando a ID do ativo.</span><span class="sxs-lookup"><span data-stu-id="a1ff3-129">A message will be displayed informing you of the asset ID.</span></span> <span data-ttu-id="a1ff3-130">Você não está excluindo a ordem de compra ou a ordem de venda, mas apenas o registro de onde poderia ter criado um ativo em **Gerenciamento de Ativos**.</span><span class="sxs-lookup"><span data-stu-id="a1ff3-130">You are not deleting the purchase order or sales order, just the record from which you could have created an asset in **Asset Management**.</span></span>

>[!NOTE]
><span data-ttu-id="a1ff3-131">Todas as dimensões do produto (tamanho, cor, configuração etc.) serão automaticamente transferidas para os atributos de ativo.</span><span class="sxs-lookup"><span data-stu-id="a1ff3-131">All product dimensions (size, color, configuration etc.) are automatically transferred to the asset attributes.</span></span> <span data-ttu-id="a1ff3-132">As dimensões de rastreamento (número de série) são armazenadas diretamente no ativo quando o ativo é criado.</span><span class="sxs-lookup"><span data-stu-id="a1ff3-132">Tracking dimensions (serial number) are stored directly on the asset when the asset is created.</span></span>


## <a name="find-pending-assets"></a><span data-ttu-id="a1ff3-133">Localize ativos pendentes</span><span class="sxs-lookup"><span data-stu-id="a1ff3-133">Find pending assets</span></span>

<span data-ttu-id="a1ff3-134">Você pode executar uma **Contagem de ativos pendentes** para verificar os ativos pendentes.</span><span class="sxs-lookup"><span data-stu-id="a1ff3-134">You can run a **Pending asset count** to check for pending assets.</span></span> <span data-ttu-id="a1ff3-135">Por exemplo, essa função pode ser usada para receber uma notificação sempre que um ativo pendente está pronto para ser criado como um ativo.</span><span class="sxs-lookup"><span data-stu-id="a1ff3-135">For example, this function can be used for receiving a notification each time a pending asset is ready to be created as an asset.</span></span>

1. <span data-ttu-id="a1ff3-136">Clique em **Gerenciamento de ativos** > **Periódico** > **Ativos** > **Contagem de ativos pendentes**.</span><span class="sxs-lookup"><span data-stu-id="a1ff3-136">Click **Asset management** > **Periodic** > **Assets** > **Pending asset count**.</span></span>
2. <span data-ttu-id="a1ff3-137">Clique em **OK** para executar o trabalho e atualizar a lista em **Ativos pendentes**.</span><span class="sxs-lookup"><span data-stu-id="a1ff3-137">Click **OK** to run the job and update the list in **Pending assets**.</span></span>
3. <span data-ttu-id="a1ff3-138">Você pode configurar este trabalho para executar como um trabalho em lotes, por exemplo, uma vez a cada dia.</span><span class="sxs-lookup"><span data-stu-id="a1ff3-138">You can set up this job to run as a batch job, for example, once each day.</span></span>

<span data-ttu-id="a1ff3-139">**Cuidado:** se os dados forem alterados em uma ordem de compra *após* você criar um ativo com base no item relativo, as alterações não serão refletidas no ativo.</span><span class="sxs-lookup"><span data-stu-id="a1ff3-139">**Caution:** If data is changed on a purchase order *after* you have created an asset based on the appertaining item, those changes will not be reflected on the asset.</span></span>

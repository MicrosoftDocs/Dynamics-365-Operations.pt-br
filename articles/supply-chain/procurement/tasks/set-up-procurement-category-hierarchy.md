---
title: Configurar uma hierarquia de categorias de compras
description: Este procedimento mostra como criar novos nós em uma hierarquia de categorias de aquisição e como configurar uma categoria de aquisição para ser usada em um processo de aquisição.
author: RichardLuan
manager: tfehr
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 44fd02d37ec4e6431ca25dc980ed1d1785e45fac
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5239341"
---
# <a name="set-up-a-procurement-category-hierarchy"></a><span data-ttu-id="b2abc-103">Configurar uma hierarquia de categorias de compras</span><span class="sxs-lookup"><span data-stu-id="b2abc-103">Set up a procurement category hierarchy</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b2abc-104">Este procedimento mostra como criar novos nós em uma hierarquia de categorias de aquisição e como configurar uma categoria de aquisição para ser usada em um processo de aquisição.</span><span class="sxs-lookup"><span data-stu-id="b2abc-104">This procedure shows you how to create new nodes in a procurement category hierarchy and how to configure a procurement category to be used in a procurement process.</span></span> <span data-ttu-id="b2abc-105">Essas tarefas são normalmente realizadas por um Gerente de compras.</span><span class="sxs-lookup"><span data-stu-id="b2abc-105">These tasks would typically be carried out by a Purchasing manager.</span></span> <span data-ttu-id="b2abc-106">Antes que você possa começar esse procedimento, é necessário que exista uma hierarquia de categoria do tipo Aquisição.</span><span class="sxs-lookup"><span data-stu-id="b2abc-106">Before you can start this procedure, there must be a category hierarchy of type Procurement.</span></span> <span data-ttu-id="b2abc-107">Se você for utilizar uma empresa de dados demonstrativos, é possível executar esse procedimento na empresa USMF.</span><span class="sxs-lookup"><span data-stu-id="b2abc-107">If you're using a demo data company, you can run this procedure in the USMF company.</span></span>


## <a name="add-a-new-procurement-category"></a><span data-ttu-id="b2abc-108">Adicione uma nova categoria de aquisição.</span><span class="sxs-lookup"><span data-stu-id="b2abc-108">Add a new procurement category</span></span>
1. <span data-ttu-id="b2abc-109">Vá para **Painel de navegação > Módulos > Compras e fornecimento > Consignação > Categorias de compras**.</span><span class="sxs-lookup"><span data-stu-id="b2abc-109">Go to **Navigation pane > Modules > Procurement and sourcing > Consignment > Procurement categories**.</span></span>
2. <span data-ttu-id="b2abc-110">No Painel de Ações, selecione **Editar hierarquia de categoria**.</span><span class="sxs-lookup"><span data-stu-id="b2abc-110">On the Action Pane, select **Edit category hierarchy**.</span></span> <span data-ttu-id="b2abc-111">A hierarquia de categorias de aquisição atual é exibida no lado esquerdo da página.</span><span class="sxs-lookup"><span data-stu-id="b2abc-111">The current procurement category hierarchy is displayed in the left side of the page.</span></span> <span data-ttu-id="b2abc-112">Você está prestes a modificar a hierarquia.</span><span class="sxs-lookup"><span data-stu-id="b2abc-112">You  are about to modify the hierarchy.</span></span>  
3. <span data-ttu-id="b2abc-113">No Painel de Ações, selecione **Novo nó de categoria**.</span><span class="sxs-lookup"><span data-stu-id="b2abc-113">On the Action Pane, select **New category node**.</span></span> <span data-ttu-id="b2abc-114">O sistema seleciona o nó superior por padrão.</span><span class="sxs-lookup"><span data-stu-id="b2abc-114">The system selects the top node by default.</span></span> <span data-ttu-id="b2abc-115">Se você estiver executando esse procedimento como um guia de tarefa, é possível clicar no botão Desbloquear e selecionar outro nó superior onde irá inserir o novo nó.</span><span class="sxs-lookup"><span data-stu-id="b2abc-115">If you are running this procedure as a task guide, you can click the Unlock button and select another parent node to insert your new node into.</span></span> <span data-ttu-id="b2abc-116">Assim que isso for feito, bloqueie o guia de tarefa novamente e clique em Novo nó de categoria.</span><span class="sxs-lookup"><span data-stu-id="b2abc-116">Once that is done, lock the task guide again and then click New category node.</span></span>  
4. <span data-ttu-id="b2abc-117">No campo **Nome**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b2abc-117">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="b2abc-118">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b2abc-118">In the **Description** field, type a value.</span></span>
6. <span data-ttu-id="b2abc-119">No campo **Nome amigável**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b2abc-119">In the **Friendly name** field, type a value.</span></span> <span data-ttu-id="b2abc-120">O nome amigável é opcional.</span><span class="sxs-lookup"><span data-stu-id="b2abc-120">The friendly name is optional.</span></span> <span data-ttu-id="b2abc-121">Ele será exibido nas pesquisas de categoria junto com o nome da categoria.</span><span class="sxs-lookup"><span data-stu-id="b2abc-121">It will be displayed in category lookups together with the category name.</span></span>  
7. <span data-ttu-id="b2abc-122">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b2abc-122">Select **Save**.</span></span>

## <a name="add-products-to-your-new-procurement-category"></a><span data-ttu-id="b2abc-123">Adicionar produtos a sua nova categoria de aquisição</span><span class="sxs-lookup"><span data-stu-id="b2abc-123">Add products to your new procurement category</span></span>
1. <span data-ttu-id="b2abc-124">Vá para **Compras e fornecimento > Consignação > Categorias de compras**.</span><span class="sxs-lookup"><span data-stu-id="b2abc-124">Go to **Procurement and sourcing > Consignment > Procurement categories**.</span></span> <span data-ttu-id="b2abc-125">Selecione o nó que você acabou de adicionar.</span><span class="sxs-lookup"><span data-stu-id="b2abc-125">Select the node you just added.</span></span> <span data-ttu-id="b2abc-126">Se você estiver executando este procedimento como um guia de tarefa você talvez precise desbloquear o guia de tarefa para selecionar o nó.</span><span class="sxs-lookup"><span data-stu-id="b2abc-126">If you're running this procedure as a task guide you might need to unlock the task guide to select the node.</span></span>  
2. <span data-ttu-id="b2abc-127">Ative a expansão da seção **Produtos**.</span><span class="sxs-lookup"><span data-stu-id="b2abc-127">Toggle the expansion of the **Products** section.</span></span>
3. <span data-ttu-id="b2abc-128">Selecione **Adicionar** para associar produtos à categoria de compras.</span><span class="sxs-lookup"><span data-stu-id="b2abc-128">Select **Add** to associate products with the procurement category.</span></span>
4. <span data-ttu-id="b2abc-129">Selecione os produtos que você deseja adicionar à categoria de compras.</span><span class="sxs-lookup"><span data-stu-id="b2abc-129">Select the products you want to add to the procurement category.</span></span>
5. <span data-ttu-id="b2abc-130">Selecione a seta para adicionar os produtos à tabela **Selecionados**.</span><span class="sxs-lookup"><span data-stu-id="b2abc-130">Select the arrow to add the products to the **Selected** table.</span></span>
6. <span data-ttu-id="b2abc-131">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="b2abc-131">Select **OK**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
---
title: Proprietários de produto
description: Este tópico fornece informações sobre proprietários de produto. O proprietário de um produto é um grupo de usuários responsáveis por produtos específicos. Somente os membros do grupo podem liberar esses produtos. O proprietário do produto também pode ser usado no fluxo de trabalho de aprovação.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgProductOwner
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 679712b2397f220e263da3df07ecd03c99bebf3f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842017"
---
# <a name="product-owners"></a><span data-ttu-id="2b649-106">Proprietários de produto</span><span class="sxs-lookup"><span data-stu-id="2b649-106">Product owners</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2b649-107">O proprietário de um produto é um grupo de usuários responsáveis por produtos específicos.</span><span class="sxs-lookup"><span data-stu-id="2b649-107">The product owner is a group of users who are responsible for specific products.</span></span> <span data-ttu-id="2b649-108">Quando um grupo de proprietários de produtos é atribuído a um produto, somente os membros desse grupo podem liberar o produto.</span><span class="sxs-lookup"><span data-stu-id="2b649-108">When a product owner group is assigned to a product, only the members of that group can release the product.</span></span> <span data-ttu-id="2b649-109">O proprietário do produto também pode ser usado no fluxo de trabalho de aprovação no gerenciamento de alteração de engenharia.</span><span class="sxs-lookup"><span data-stu-id="2b649-109">The product owner can also be used in the approval workflow in engineering change management.</span></span>

<span data-ttu-id="2b649-110">Os proprietários de produtos são configurações globais.</span><span class="sxs-lookup"><span data-stu-id="2b649-110">Product owners are global settings.</span></span> <span data-ttu-id="2b649-111">Portanto, estão disponíveis para todas as entidades legais.</span><span class="sxs-lookup"><span data-stu-id="2b649-111">Therefore, they are available to all legal entities.</span></span>

## <a name="create-a-product-owner-group"></a><span data-ttu-id="2b649-112">Criar um grupo de proprietários de produtos</span><span class="sxs-lookup"><span data-stu-id="2b649-112">Create a product owner group</span></span>

<span data-ttu-id="2b649-113">Para criar um grupo de proprietários de produtos e adicionar membros a ele, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="2b649-113">To create a product owner group and add members to it, follow these steps.</span></span>

1. <span data-ttu-id="2b649-114">Vá para **Gerenciamento de alteração de engenharia \> Configuração \> Proprietários de produto**.</span><span class="sxs-lookup"><span data-stu-id="2b649-114">Go to **Engineering change management \> Setup \> Product owners**.</span></span>
2. <span data-ttu-id="2b649-115">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="2b649-115">On the Action Pane, select **New**.</span></span>
3. <span data-ttu-id="2b649-116">No campo **Proprietário de produto**, insira um nome para o grupo.</span><span class="sxs-lookup"><span data-stu-id="2b649-116">In the **Product owner** field, enter a name for the group.</span></span>
4. <span data-ttu-id="2b649-117">No campo **Nome**, insira uma descrição do grupo.</span><span class="sxs-lookup"><span data-stu-id="2b649-117">In the **Name** field, enter a description of the group.</span></span>
5. <span data-ttu-id="2b649-118">Na Guia rápida **Membros**, adicione os trabalhadores que devem ser membros do grupo.</span><span class="sxs-lookup"><span data-stu-id="2b649-118">On the **Members** FastTab, add the workers who should be members of the group.</span></span>

## <a name="assign-a-product-owner-to-a-product"></a><span data-ttu-id="2b649-119">Atribuir um proprietário de produto a um produto</span><span class="sxs-lookup"><span data-stu-id="2b649-119">Assign a product owner to a product</span></span>

<span data-ttu-id="2b649-120">Para atribuir uma propriedade de produto a um produto, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="2b649-120">To assign a product owner to a product, follow these steps.</span></span>

1. <span data-ttu-id="2b649-121">Abra a página **Detalhes de produto** para o produto ou produto mestre relevante.</span><span class="sxs-lookup"><span data-stu-id="2b649-121">Open the **Product details** page for the relevant product or product master.</span></span>
1. <span data-ttu-id="2b649-122">Na Guia rápida **Geral**, defina o campo **Proprietário do produto** como o nome do grupo de proprietários de produtos relevante.</span><span class="sxs-lookup"><span data-stu-id="2b649-122">On the **General** FastTab, set the **Product owner** field to the name of the relevant product owner group.</span></span>

<span data-ttu-id="2b649-123">Enquanto um proprietário de produto é atribuído a um produto, somente os membros do grupo de proprietários de produtos podem editar a configuração do **Proprietário do produto**.</span><span class="sxs-lookup"><span data-stu-id="2b649-123">While a product owner is assigned to a product, only the members of the product owner group can edit the **Product owner** setting.</span></span>

<span data-ttu-id="2b649-124">O proprietário do produto também está visível na página **Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="2b649-124">The product owner is also visible on the **Released products** page.</span></span>

## <a name="product-owners-and-product-releases"></a><span data-ttu-id="2b649-125">Proprietários de produtos e liberações de produtos</span><span class="sxs-lookup"><span data-stu-id="2b649-125">Product owners and product releases</span></span>

<span data-ttu-id="2b649-126">Somente os usuários do grupo de proprietários de produtos do produto podem liberar esse produto.</span><span class="sxs-lookup"><span data-stu-id="2b649-126">Only users from a product's product owner group can release that product.</span></span> <span data-ttu-id="2b649-127">No entanto, há uma exceção quando o produto é um item filho, e seu pai é liberado pelo proprietário do pai.</span><span class="sxs-lookup"><span data-stu-id="2b649-127">However, there is an exception when the product is a child item, and its parent is released by the parent's owner.</span></span> <span data-ttu-id="2b649-128">Em outras palavras, se o produto fizer parte da BOM de outro produto, o sistema não verificará o proprietário do produto de cada item na BOM.</span><span class="sxs-lookup"><span data-stu-id="2b649-128">In other words, if the product is part of the BOM of another product, the system doesn't check the product owner of each item in the BOM.</span></span> <span data-ttu-id="2b649-129">Ele verifica somente o proprietário do produto do item pai.</span><span class="sxs-lookup"><span data-stu-id="2b649-129">It checks only the product owner of the parent item.</span></span>

<span data-ttu-id="2b649-130">Por exemplo, o produto X é atribuído ao grupo de proprietários de produtos *Projetar gabinetes*.</span><span class="sxs-lookup"><span data-stu-id="2b649-130">For example, product X is assigned to the *Design cabinets* product owner group.</span></span> <span data-ttu-id="2b649-131">O produto X também faz parte da BOM do produto Y, que é atribuída ao grupo de proprietários de produtos de *Design de alto-falantes*.</span><span class="sxs-lookup"><span data-stu-id="2b649-131">Product X is also part of the BOM of product Y, which is assigned to the *Design Speakers* product owner group.</span></span> <span data-ttu-id="2b649-132">Se um usuário do grupo de proprietários de produtos *Design de alto-falantes* lançar o produto Y e sua BOM, o produto X será liberado junto com o produto Y.</span><span class="sxs-lookup"><span data-stu-id="2b649-132">If a user from the *Design Speakers* product owner group releases product Y and its BOM, product X will be released together with product Y.</span></span>

## <a name="product-owners-and-approvals"></a><span data-ttu-id="2b649-133">Proprietários e aprovações de produtos</span><span class="sxs-lookup"><span data-stu-id="2b649-133">Product owners and approvals</span></span>

<span data-ttu-id="2b649-134">Como os proprietários de produtos sabem se as alterações de engenharia específicas se beneficiarão com seus produtos, geralmente faz sentido incluí-las como parte do processo de aprovação no gerenciamento de alterações de engenharia.</span><span class="sxs-lookup"><span data-stu-id="2b649-134">Because product owners know whether specific engineering changes will benefit their products, it often makes sense to include them as part of the approval process in engineering change management.</span></span> <span data-ttu-id="2b649-135">Você pode implementar essa abordagem configurando os proprietários de produtos como provedores de participantes nos fluxos de trabalho que são usados para o gerenciamento de alterações de engenharia.</span><span class="sxs-lookup"><span data-stu-id="2b649-135">You can implement this approach by setting up the product owners as participant providers in the workflows that are used for engineering change management.</span></span> <span data-ttu-id="2b649-136">O sistema atribuirá tarefas de aprovação nos fluxos de trabalho com base nos produtos que estão nas solicitações de alteração de engenharia e nas ordens de alteração de engenharia.</span><span class="sxs-lookup"><span data-stu-id="2b649-136">The system will then assign approval tasks in the workflows, based on the products that are in engineering change requests and engineering change orders.</span></span> <span data-ttu-id="2b649-137">Para obter mais informações, consulte [Gerenciar alterações de produtos de engenharia](engineering-change-management.md).</span><span class="sxs-lookup"><span data-stu-id="2b649-137">For more information, see [Manage changes to engineering products](engineering-change-management.md).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
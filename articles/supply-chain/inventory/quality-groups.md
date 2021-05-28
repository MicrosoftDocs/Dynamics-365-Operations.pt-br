---
title: Grupos de qualidade de item
description: Este tópico descreve como usar e criar grupos de qualidade de item a fim de agrupar produtos de forma lógica para que eles possam ser atribuídos a associações de qualidade para a geração automática de ordens de qualidade.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestQualityGroup, InventTestItemQualityGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 272cb748e0a2722d9744fe6b357d767a1d6aeb26
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022243"
---
# <a name="item-quality-groups"></a><span data-ttu-id="bfc0f-103">Grupos de qualidade de item</span><span class="sxs-lookup"><span data-stu-id="bfc0f-103">Item quality groups</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bfc0f-104">Um grupo de qualidade representa requisitos de teste comuns para itens.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-104">A quality group represents common testing requirements for items.</span></span> <span data-ttu-id="bfc0f-105">Este tópico descreve como usar e criar grupos de qualidade de item a fim de agrupar produtos de forma lógica para que eles possam ser atribuídos a associações de qualidade para a geração automática de ordens de qualidade.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-105">This topic describes how to use and create item quality groups to logically group products so that they can be assigned to quality associations for the automatic generation of quality orders.</span></span>

<span data-ttu-id="bfc0f-106">Para configurar, editar e exibir os itens atribuídos a um grupo de qualidade, ou os grupos de qualidade atribuídos a um item, vá para **Gerenciamento de estoque \> Configuração \> Grupos de qualidade**.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-106">To set up, edit, and view the items that are assigned to a quality group, or the quality groups that are assigned to an item, go to **Inventory management \> Setup \> Quality groups**.</span></span> <span data-ttu-id="bfc0f-107">Após definir os requisitos de teste da página **Grupos de teste**, você pode definir as regras para gerar automaticamente as ordens de qualidade.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-107">After you define the test requirements on the **Test groups** page, you can define the rules for automatically generating quality orders.</span></span> <span data-ttu-id="bfc0f-108">Para simplificar o processo, você não define regras para itens individuais.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-108">To simplify the process, you don't define rules for individual items.</span></span> <span data-ttu-id="bfc0f-109">Em vez disso, você pode definir as regras para um grupo de qualidade na página **Associações de qualidade**.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-109">Instead, you can define the rules for a quality group on the **Quality associations** page.</span></span>

## <a name="example-of-an-item-quality-group"></a><span data-ttu-id="bfc0f-110">Exemplo de um grupo de qualidade de item</span><span class="sxs-lookup"><span data-stu-id="bfc0f-110">Example of an item quality group</span></span>

<span data-ttu-id="bfc0f-111">Uma fábrica compra diversas matérias-primas que têm os mesmos requisitos de teste para inspeção de entrada.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-111">A manufacturing company purchases various raw materials that have the same testing requirements for incoming inspection.</span></span> <span data-ttu-id="bfc0f-112">Portanto, a empresa define um grupo de qualidade e então atribui os números de item associados às matérias-primas a esse grupo.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-112">Therefore, the company defines a quality group and then assigns the item numbers that are associated with the raw materials to that group.</span></span> <span data-ttu-id="bfc0f-113">Posteriormente, a empresa compra um novo tipo de matéria-prima que têm os mesmos requisitos de teste.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-113">Later, the company purchases a new type of raw material that has the same testing requirements.</span></span> <span data-ttu-id="bfc0f-114">Em vez de configurar novos requisitos de teste para o novo material, a empresa adiciona o número do item para o novo material no grupo de qualidade existente.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-114">Instead of setting up new testing requirements for the new material, the company adds the item number for the new material to the existing quality group.</span></span>

<span data-ttu-id="bfc0f-115">A mesma empresa também produz itens com os mesmos requisitos de teste de produção e remete itens com o mesmo requisito de teste antes da remessa.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-115">The same company also produces items that have the same production testing requirements and ships items that have the same requirement for pre-shipment testing.</span></span> <span data-ttu-id="bfc0f-116">Portanto, a empresa define dois grupos de qualidade adicionais e então atribui os números de item relevantes a cada grupo.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-116">Therefore, the company defines two additional quality groups and then assigns the relevant item numbers to each group.</span></span>

## <a name="create-a-quality-group"></a><span data-ttu-id="bfc0f-117">Criar um grupo de qualidade</span><span class="sxs-lookup"><span data-stu-id="bfc0f-117">Create a quality group</span></span>

<span data-ttu-id="bfc0f-118">Para criar um grupo de qualidade, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-118">To create a quality group, follow these steps.</span></span>

1. <span data-ttu-id="bfc0f-119">Vá para **Gerenciamento de estoque \> Configuração \> Controle de qualidade \> Grupos de qualidade**.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-119">Go to **Inventory management \> Setup \> Quality control \> Quality groups**.</span></span>
1. <span data-ttu-id="bfc0f-120">No Painel de Ação, selecione **Novo** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-120">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="bfc0f-121">Defina os seguintes campos para a nova linha:</span><span class="sxs-lookup"><span data-stu-id="bfc0f-121">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="bfc0f-122">**Grupo de qualidade** – Insira um nome ou uma ID exclusiva para o grupo de qualidade.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-122">**Quality group** – Enter a unique ID or name for the quality group.</span></span>
    - <span data-ttu-id="bfc0f-123">**Descrição** – Insira uma descrição detalhada do grupo de qualidade.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-123">**Description** – Enter a detailed description of the quality group.</span></span>

1. <span data-ttu-id="bfc0f-124">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-124">Close the page.</span></span>

## <a name="manually-add-items-to-a-quality-group"></a><span data-ttu-id="bfc0f-125">Adicionar itens manualmente a um grupo de qualidade</span><span class="sxs-lookup"><span data-stu-id="bfc0f-125">Manually add items to a quality group</span></span>

<span data-ttu-id="bfc0f-126">Para adicionar itens manualmente a um grupo de qualidade, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-126">To manually add items to a quality group, follow these steps.</span></span>

1. <span data-ttu-id="bfc0f-127">Vá para **Gerenciamento de estoque \> Configuração \> Controle de qualidade \> Grupos de qualidade**.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-127">Go to **Inventory management \> Setup \> Quality control \> Quality groups**.</span></span>
1. <span data-ttu-id="bfc0f-128">Selecione o grupo de qualidade ao qual você deseja adicionar itens.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-128">Select the quality group that you want to add items to.</span></span>
1. <span data-ttu-id="bfc0f-129">No Painel de Ações, selecione **Itens**.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-129">On the Action Pane, select **Items**.</span></span>
1. <span data-ttu-id="bfc0f-130">Na página **Itens em grupos de qualidade**, no Painel de Ações, selecione **Novo** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-130">On the **Items in quality groups** page, on the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="bfc0f-131">Em seguida, para a nova linha, defina o campo **Número do item** como o número do item que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-131">Then, for the new row, set the **Item number** field to the item number that you want to add.</span></span>
1. <span data-ttu-id="bfc0f-132">Repita a etapa anterior para cada item adicional que deve ser incluído.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-132">Repeat the previous step for each additional item that must be added.</span></span>
1. <span data-ttu-id="bfc0f-133">Feche as páginas.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-133">Close the pages.</span></span>

## <a name="add-multiple-items-to-a-quality-group"></a><span data-ttu-id="bfc0f-134">Adicionar vários itens a um grupo de qualidade</span><span class="sxs-lookup"><span data-stu-id="bfc0f-134">Add multiple items to a quality group</span></span>

<span data-ttu-id="bfc0f-135">Para adicionar vários itens a um grupo de qualidade, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-135">To add multiple items to a quality group, follow these steps.</span></span>

1. <span data-ttu-id="bfc0f-136">Vá para **Gerenciamento de estoque \> Configuração \> Controle de qualidade \> Grupos de qualidade**.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-136">Go to **Inventory management \> Setup \> Quality control \> Quality groups**.</span></span>
1. <span data-ttu-id="bfc0f-137">Crie ou selecione o grupo de qualidade ao qual você deseja adicionar itens.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-137">Create or select the quality group that you want to add items to.</span></span>
1. <span data-ttu-id="bfc0f-138">No Painel de Ações, selecione **Adicionar itens**.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-138">On the Action Pane, select **Add items**.</span></span>
1. <span data-ttu-id="bfc0f-139">Na caixa de diálogo **Consulta**, insira os critérios de filtragem dos itens que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-139">In the **Inquiry** dialog box, enter the filter criteria for the items that you want to add.</span></span> <span data-ttu-id="bfc0f-140">Por exemplo, você pode filtrar todos os itens em um grupo de itens específico.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-140">For example, you might filter for all items in a specific item group.</span></span>
1. <span data-ttu-id="bfc0f-141">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-141">Select **OK**.</span></span>
1. <span data-ttu-id="bfc0f-142">Na caixa de diálogo **Adicionar itens**, uma grade mostra todos os itens que correspondem à sua consulta.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-142">In the **Add items** dialog box, a grid shows all the items that match your query.</span></span> <span data-ttu-id="bfc0f-143">Revise os resultados.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-143">Review the results.</span></span>

    <span data-ttu-id="bfc0f-144">Se forem necessárias alterações, selecione **Selecionar** para retornar à caixa de diálogo **Consulta** e ajuste a consulta.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-144">If any changes are required, select **Select** to return to the **Inquiry** dialog box, and adjust your query.</span></span>

1. <span data-ttu-id="bfc0f-145">Quando os resultados incluírem todos os itens que você deseja adicionar, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-145">When the results include all the items that you want to add, select **OK**.</span></span>
1. <span data-ttu-id="bfc0f-146">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-146">Close the page.</span></span>

## <a name="manually-associate-an-item-with-a-quality-group"></a><span data-ttu-id="bfc0f-147">Associar manualmente um item a um grupo de qualidade</span><span class="sxs-lookup"><span data-stu-id="bfc0f-147">Manually associate an item with a quality group</span></span>

<span data-ttu-id="bfc0f-148">Para associar manualmente um item a um grupo de qualidade, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-148">To manually associate an item with a quality group, follow these steps.</span></span>

1. <span data-ttu-id="bfc0f-149">Vá para **Gerenciamento de estoque \> Configuração \> Controle de qualidade \> Grupos de qualidade de item**.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-149">Go to **Inventory management \> Setup \> Quality control \> Item quality groups**.</span></span>
1. <span data-ttu-id="bfc0f-150">No Painel de Ação, selecione **Novo** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-150">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="bfc0f-151">Defina os seguintes campos para a nova linha:</span><span class="sxs-lookup"><span data-stu-id="bfc0f-151">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="bfc0f-152">**Número do item** – Selecione o número do item a ser adicionado.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-152">**Item number** – Select the item number to add.</span></span>
    - <span data-ttu-id="bfc0f-153">**Grupo de qualidade** – Selecione o grupo de qualidade a ser atribuído ao item.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-153">**Quality group** – Select the quality group to assign to the item.</span></span>

1. <span data-ttu-id="bfc0f-154">Repita a etapa anterior para cada combinação adicional de um item e um grupo de qualidade que deve ser incluída.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-154">Repeat the previous step for each additional combination of an item and a quality group that must be added.</span></span>
1. <span data-ttu-id="bfc0f-155">Feche as páginas.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-155">Close the pages.</span></span>

## <a name="manually-add-a-quality-group-from-the-released-products-page"></a><span data-ttu-id="bfc0f-156">Adicionar manualmente um grupo de qualidade na página Produtos liberados</span><span class="sxs-lookup"><span data-stu-id="bfc0f-156">Manually add a quality group from the Released products page</span></span>

<span data-ttu-id="bfc0f-157">Para adicionar manualmente um grupo de qualidade na página **Produtos liberados**, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-157">To manually add a quality group from the **Released products** page, follow these steps.</span></span>

1. <span data-ttu-id="bfc0f-158">Vá para **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-158">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="bfc0f-159">Selecione o produto ao qual deseja atribuir um grupo de qualidade.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-159">Select the product that you want to assign a quality group to.</span></span>
1. <span data-ttu-id="bfc0f-160">No Painel de Ações, na guia **Gerenciar estoque**, no grupo **Qualidade**, selecione **Grupos de qualidade de item**.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-160">On the Action Pane, on the **Manage inventory** tab, in the **Quality** group, select **Item quality groups**.</span></span>
1. <span data-ttu-id="bfc0f-161">Na página **Itens em grupos de qualidade**, no Painel de Ações, selecione **Novo** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-161">On the **Items in quality groups** page, on the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="bfc0f-162">Em seguida, para a nova linha, defina o campo **Grupo de qualidade** como o grupo de qualidade que você deseja atribuir ao produto.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-162">Then, for the new row, set the **Quality group** field to the quality group that you want to assign to the product.</span></span>
1. <span data-ttu-id="bfc0f-163">Repita a etapa anterior para cada grupo de qualidade adicional que você deseja atribuir ao produto.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-163">Repeat the previous step for each additional quality group that you want to assign to the product.</span></span>
1. <span data-ttu-id="bfc0f-164">Feche as páginas.</span><span class="sxs-lookup"><span data-stu-id="bfc0f-164">Close the pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bfc0f-165">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="bfc0f-165">Additional resources</span></span>

- [<span data-ttu-id="bfc0f-166">Instrumentos de teste de gerenciamento de qualidade</span><span class="sxs-lookup"><span data-stu-id="bfc0f-166">Quality management test instruments</span></span>](quality-test-instruments.md)
- [<span data-ttu-id="bfc0f-167">Testes de gerenciamento de qualidade</span><span class="sxs-lookup"><span data-stu-id="bfc0f-167">Quality management tests</span></span>](quality-tests.md)
- [<span data-ttu-id="bfc0f-168">Grupos de teste de gerenciamento de qualidade</span><span class="sxs-lookup"><span data-stu-id="bfc0f-168">Quality management test groups</span></span>](quality-test-groups.md)
- [<span data-ttu-id="bfc0f-169">Variáveis de teste de gerenciamento de qualidade</span><span class="sxs-lookup"><span data-stu-id="bfc0f-169">Quality management test variables</span></span>](quality-test-variables.md)
- [<span data-ttu-id="bfc0f-170">Associações de qualidade</span><span class="sxs-lookup"><span data-stu-id="bfc0f-170">Quality associations</span></span>](quality-associations.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

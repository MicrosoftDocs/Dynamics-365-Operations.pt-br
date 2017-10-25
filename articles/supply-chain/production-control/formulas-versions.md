---
title: "Fórmulas e versões de fórmulas"
description: "Este tópico fornece informações sobre fórmulas e versões da fórmula. Uma fórmula define materiais, ingredientes e os resultados de um processo específico na fabricação de processo. As fórmulas são usados para planejar e produzir produtos na manufatura de processos."
author: cvocph
manager: AnnBe
ms.date: 09/12/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: PlanActivity, ReqSupplyDemandSchedule
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 53edebb31b969c13b566d03afe3d58718543bf23
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="formulas-and-formula-versions"></a><span data-ttu-id="9dec4-105">Fórmulas e versões de fórmulas</span><span class="sxs-lookup"><span data-stu-id="9dec4-105">Formulas and formula versions</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="9dec4-106">Uma fórmula define materiais, ingredientes e os resultados de um processo específico na fabricação de processo.</span><span class="sxs-lookup"><span data-stu-id="9dec4-106">A formula defines the materials, ingredients, and outcomes of a specific process in process manufacturing.</span></span> <span data-ttu-id="9dec4-107">Com o roteiro correspondente, a fórmula define todo o processo na manufatura do processo.</span><span class="sxs-lookup"><span data-stu-id="9dec4-107">Together with the corresponding route, the formula defines the whole process in process manufacturing.</span></span> <span data-ttu-id="9dec4-108">As fórmulas são usados para planejar e produzir produtos na manufatura de processos.</span><span class="sxs-lookup"><span data-stu-id="9dec4-108">Formulas are used to plan and produce products in process manufacturing.</span></span>

<span data-ttu-id="9dec4-109">Uma fórmula consiste em ingredientes e quantidades necessários para produzir uma determinada quantidade de um item de fórmula.</span><span class="sxs-lookup"><span data-stu-id="9dec4-109">A formula consists of the ingredients and quantities that are required in order to produce a specific quantity of a formula item.</span></span> <span data-ttu-id="9dec4-110">Dependendo da tarefa que você realizar, é possível acessar a funcionalidade da fórmula do Gerenciamento de estoque e de depósito ou do Gerenciamento de informações do produto.</span><span class="sxs-lookup"><span data-stu-id="9dec4-110">Depending on the task that you perform, you can access formula functionality from Inventory and warehouse management or Product information management.</span></span>

## <a name="formulas-and-formula-lines"></a><span data-ttu-id="9dec4-111">Fórmulas e linhas da fórmula</span><span class="sxs-lookup"><span data-stu-id="9dec4-111">Formulas and formula lines</span></span>
<span data-ttu-id="9dec4-112">Uma fórmula consiste em uma ou mais linhas da fórmula, que identificam os ingredientes ou itens que compõem a fórmula.</span><span class="sxs-lookup"><span data-stu-id="9dec4-112">A formula consists of one or more formula lines that identify the ingredients or items that make up the formula.</span></span> <span data-ttu-id="9dec4-113">Uma linha da fórmula pode conter itens de BOM, itens de fórmula, itens de peso variável, itens comprados, coprodutos ou subprodutos.</span><span class="sxs-lookup"><span data-stu-id="9dec4-113">A formula line can contain Bill of materials (BOM) items, formula items, catch-weight items, purchased items, co-products, or by-products.</span></span> <span data-ttu-id="9dec4-114">Como vários itens são usados em vários produtos, um item pode ser usado em mais de uma fórmula.</span><span class="sxs-lookup"><span data-stu-id="9dec4-114">Because many items are used in multiple products, an item can be used in more than one formula.</span></span>

<span data-ttu-id="9dec4-115">Um exemplo de uma fórmula é uma fórmula de biscoito com gotas de chocolate.</span><span class="sxs-lookup"><span data-stu-id="9dec4-115">An example of a formula is the formula for a chocolate chip cookie.</span></span> <span data-ttu-id="9dec4-116">Os ingredientes para essa fórmula usam várias linhas, como farinha, açúcar, ovos, manteiga e as gotas de chocolate.</span><span class="sxs-lookup"><span data-stu-id="9dec4-116">The ingredients for this formula use multiple lines, such as flour, sugar, eggs, butter, and chocolate chips.</span></span> <span data-ttu-id="9dec4-117">A fórmula de biscoito com gotas de chocolate contém ingredientes que provavelmente são usados em outras fórmulas.</span><span class="sxs-lookup"><span data-stu-id="9dec4-117">The formula for the chocolate chip cookie contains ingredients that are likely used in other formulas.</span></span> <span data-ttu-id="9dec4-118">Quando você faz os biscoitos com gotas de chocolate, é possível que haja sobras, como migalhas, ou alguns biscoitos podem assar demais ou pouco.</span><span class="sxs-lookup"><span data-stu-id="9dec4-118">While you make the chocolate chip cookies, there might be leftovers, such as crumbs, or some of the cookies might be overbaked or underbaked.</span></span> <span data-ttu-id="9dec4-119">Esses itens podem ser configurados como coprodutos ou subprodutos, dependendo das operações de produção.</span><span class="sxs-lookup"><span data-stu-id="9dec4-119">These items can be set up as co-products or by-products, depending on the production operations.</span></span>

<span data-ttu-id="9dec4-120">Quando você cria uma linha da fórmula, você usa o tipo de linha para indicar como o sistema deve tratar a linha ao executar ordens de lote de planejamento e de produção.</span><span class="sxs-lookup"><span data-stu-id="9dec4-120">When you create a formula line, you use the line type to indicate how the system should handle the line when you run master planning and produce batch orders.</span></span> <span data-ttu-id="9dec4-121">Cada tipo de linha gera um resultado diferente.</span><span class="sxs-lookup"><span data-stu-id="9dec4-121">Each line type gives a different result.</span></span> <span data-ttu-id="9dec4-122">A tabela a seguir descreve os diferentes tipos de linhas que você pode selecionar.</span><span class="sxs-lookup"><span data-stu-id="9dec4-122">The following table describes the line types that you can select.</span></span> 

| <span data-ttu-id="9dec4-123">Tipo de linha</span><span class="sxs-lookup"><span data-stu-id="9dec4-123">Line type</span></span>     | <span data-ttu-id="9dec4-124">descrição</span><span class="sxs-lookup"><span data-stu-id="9dec4-124">Description</span></span>  |
|---------------|--------------|
| <span data-ttu-id="9dec4-125">Item</span><span class="sxs-lookup"><span data-stu-id="9dec4-125">Item</span></span>          | <span data-ttu-id="9dec4-126">Selecione **Item** quando o item for uma matéria-prima ou um item semiacabado separado do estoque ou quando o item for um serviço.</span><span class="sxs-lookup"><span data-stu-id="9dec4-126">Select **Item** when the item is a raw material or a semi-finished item that is picked from inventory or when the item is a service.</span></span> |
| <span data-ttu-id="9dec4-127">Fantasma</span><span class="sxs-lookup"><span data-stu-id="9dec4-127">Phantom</span></span>       | <span data-ttu-id="9dec4-128">Selecione **Fantasma** quando quiser detalhar quaisquer itens de fórmula de nível inferior contidos nas linhas de fórmula.</span><span class="sxs-lookup"><span data-stu-id="9dec4-128">Select **Phantom** when you want to explode any lower-level formula items that are contained on formula lines.</span></span> <span data-ttu-id="9dec4-129">Quando você estimar a ordem de lote e os itens de fórmula forem detalhados, os itens de componente serão listados como linhas da fórmula na ordem de lote.</span><span class="sxs-lookup"><span data-stu-id="9dec4-129">When you estimate the batch order, and the formula items are exploded, the component items are listed as formula lines on the batch order.</span></span> <span data-ttu-id="9dec4-130">Além de isso, os roteiros correspondentes serão adicionadas ao roteiro de produção.</span><span class="sxs-lookup"><span data-stu-id="9dec4-130">Additionally, the corresponding routes are added to the production route.</span></span> <span data-ttu-id="9dec4-131">Os itens de fórmula são detalhados usando a configuração atual.</span><span class="sxs-lookup"><span data-stu-id="9dec4-131">Formula items are exploded by using the current configuration.</span></span> <span data-ttu-id="9dec4-132">Ao usar o tipo de linha **Fantasma**, você poderá tratar as configurações de produção e de medição que ocorrem em diferentes níveis da fórmula.</span><span class="sxs-lookup"><span data-stu-id="9dec4-132">When you use the **Phantom** line type, you can handle production and measurement configurations that occur at different formula levels.</span></span> <span data-ttu-id="9dec4-133">Se você selecionar **Fantasma** para um produto na FastTab **Engenharia** da página **Detalhes do produto liberado** e depois usar esse produto em uma fórmula, o tipo de linha da fórmula será alterado para **Fantasma**.</span><span class="sxs-lookup"><span data-stu-id="9dec4-133">If you select **Phantom** for a product on the **Engineer** FastTab of the **Released product details** page and then use this product in a formula, the line type of the formula line is changed to **Phantom**.</span></span> <span data-ttu-id="9dec4-134">Você não pode selecionar **Fantasma** para um item de peso variável ou para itens em que o tipo de produção é **Coproduto**, **Subproduto**, ou **Item de planejamento**.</span><span class="sxs-lookup"><span data-stu-id="9dec4-134">You can't select **Phantom** for a catch-weight item, or for items where the production type is **Co-product**, **By-product**, or **Planning item**.</span></span> |
| <span data-ttu-id="9dec4-135">Fornecimento vinculado</span><span class="sxs-lookup"><span data-stu-id="9dec4-135">Pegged supply</span></span> | <span data-ttu-id="9dec4-136">Selecione **Suprimento vinculado** para criar uma ordem de lotes, ordem de produção, um kanban, uma ordem de transferência, ou uma ordem de compra do ingrediente que estará contido na linha fórmula.</span><span class="sxs-lookup"><span data-stu-id="9dec4-136">Select **Pegged supply** to create a batch order, production order, kanban, transfer order, or purchase order for the ingredient that is contained on the formula line.</span></span> <span data-ttu-id="9dec4-137">A ordem relacionada é determinada com base nas configurações de ordem padrão e no tipo de produção de ingrediente, e será criada quando você estimar a ordem de lote.</span><span class="sxs-lookup"><span data-stu-id="9dec4-137">The related order is determined based on the default order settings and the production type of the ingredient, and is created when you estimate the batch order.</span></span> <span data-ttu-id="9dec4-138">As quantidades necessárias do ingrediente serão reservadas para a ordem de lote.</span><span class="sxs-lookup"><span data-stu-id="9dec4-138">The required ingredient quantities are reserved for the batch order.</span></span> |
| <span data-ttu-id="9dec4-139">Fornecedor</span><span class="sxs-lookup"><span data-stu-id="9dec4-139">Vendor</span></span>        | <span data-ttu-id="9dec4-140">Selecione **Fornecedor** se o processo de produção usar um subcontratado e você desejar criar uma subprodução ou uma ordem de compra para o subcontratado.</span><span class="sxs-lookup"><span data-stu-id="9dec4-140">Select **Vendor** if the production process uses a subcontractor, and you want to create a sub-production or purchase order for the subcontractor.</span></span> <span data-ttu-id="9dec4-141">O serviço ou trabalho realizado pelo subcontratado deve ser criado usando um item de fórmula ou um Item de serviço.</span><span class="sxs-lookup"><span data-stu-id="9dec4-141">The service or work that the subcontractor performs must be created by using a formula item or service item.</span></span> <span data-ttu-id="9dec4-142">Você poderá associar o item ao item principal como uma linha da fórmula.</span><span class="sxs-lookup"><span data-stu-id="9dec4-142">You can attach the item to the parent item as a formula line.</span></span> <span data-ttu-id="9dec4-143">O roteiro deverá conter uma operação atribuída ao recurso de operações do subcontratado.</span><span class="sxs-lookup"><span data-stu-id="9dec4-143">The route must contain an operation that is assigned to the subcontractor's operations resource.</span></span> <span data-ttu-id="9dec4-144">Essa operação é associada à linha da fórmula usando o campo **Nº Oper.**</span><span class="sxs-lookup"><span data-stu-id="9dec4-144">This operation is attached to the formula line by using the **Oper. No.**</span></span> <span data-ttu-id="9dec4-145">.</span><span class="sxs-lookup"><span data-stu-id="9dec4-145">field.</span></span> |

## <a name="formula-versions"></a><span data-ttu-id="9dec4-146">Versões da fórmula</span><span class="sxs-lookup"><span data-stu-id="9dec4-146">Formula versions</span></span>
<span data-ttu-id="9dec4-147">Ao criar uma nova fórmula, você deverá primeiro criar uma versão da fórmula antes de adicionar itens da linha da fórmula e suas características específicas.</span><span class="sxs-lookup"><span data-stu-id="9dec4-147">When you create a new formula, you must first create a formula version before you add the formula line items and their specific characteristics.</span></span> <span data-ttu-id="9dec4-148">Toda fórmula deve ter pelo menos uma versão.</span><span class="sxs-lookup"><span data-stu-id="9dec4-148">Every formula must have at least one version.</span></span> <span data-ttu-id="9dec4-149">O botão **Aprovado** em uma versão da fórmula se torna disponível apenas depois que um registro da versão for salvo com êxito.</span><span class="sxs-lookup"><span data-stu-id="9dec4-149">The **Approved** button on a formula version becomes available only after a version record has been successfully saved.</span></span> <span data-ttu-id="9dec4-150">Cada registro da versão da fórmula é associado a um ou vários coprodutos e subprodutos que podem ser produzidos, conforme você produz o produto acabado.</span><span class="sxs-lookup"><span data-stu-id="9dec4-150">Each formula version record is associated with one or many co-products and by-products that can be produced as you produce the finished product.</span></span> <span data-ttu-id="9dec4-151">Diversos produtos podem ser feitos com os mesmos ingredientes em tamanhos de lote diferentes, múltiplos ou usando quantidades diferentes.</span><span class="sxs-lookup"><span data-stu-id="9dec4-151">Many products can be made from the same ingredients in different batch sizes, in multiples, or by using different yields.</span></span> <span data-ttu-id="9dec4-152">Você pode criar quantas versões da fórmula forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="9dec4-152">You can create as many versions of a formula as you require.</span></span>

<span data-ttu-id="9dec4-153">Para gerenciar várias versões da fórmula ativas, use intervalos de datas efetivas ou dos campos de quantidade.</span><span class="sxs-lookup"><span data-stu-id="9dec4-153">To manage multiple active formula versions, use effective date ranges or "from" quantity fields.</span></span> <span data-ttu-id="9dec4-154">Versões de fórmula ativas múltiplas poderão existir somente se o intervalo de datas e a quantidade "inicial" não se sobrepuserem.</span><span class="sxs-lookup"><span data-stu-id="9dec4-154">Multiple active formula versions can exist only if the date range and "from" quantity don't overlap.</span></span>

<span data-ttu-id="9dec4-155">Diferentemente de BOMs, onde um BOM é frequentemente associado a várias versões de BOM, apenas uma versão de fórmula existe por fórmula.</span><span class="sxs-lookup"><span data-stu-id="9dec4-155">Unlike BOMs, where one BOM is often associated with many BOM versions, only one formula version typically exists per formula.</span></span> <span data-ttu-id="9dec4-156">Lembre-se que somente uma versão de fórmula pode ser ativada para as dimensões e quantidade da cobertura de determinado produto.</span><span class="sxs-lookup"><span data-stu-id="9dec4-156">Remember that only one formula version can be activated for the coverage dimensions and quantity for a given product.</span></span> <span data-ttu-id="9dec4-157">Porém, várias versões de fórmula podem existir por outros motivos, e você pode selecioná-las manualmente quando criar uma ordem de lote.</span><span class="sxs-lookup"><span data-stu-id="9dec4-157">However, many formula versions might exist for other reasons, and you can manually select them when you create a batch order.</span></span>

## <a name="approve-and-activate-formulas-and-formula-versions"></a><span data-ttu-id="9dec4-158">Aprovar e ativar fórmulas e versões da fórmula</span><span class="sxs-lookup"><span data-stu-id="9dec4-158">Approve and activate formulas and formula versions</span></span>
<span data-ttu-id="9dec4-159">Fórmulas e versões da fórmula devem ser aprovadas antes de serem usadas para planejamento e produção.</span><span class="sxs-lookup"><span data-stu-id="9dec4-159">Formulas and formula versions must be approved before they can be used for planning and production.</span></span> <span data-ttu-id="9dec4-160">Geralmente as fórmulas são ativadas antes de serem usadas.</span><span class="sxs-lookup"><span data-stu-id="9dec4-160">Formulas are usually activated before they are used.</span></span> <span data-ttu-id="9dec4-161">Entretanto, durante a produção, é possível selecionar uma versão de fórmula que esteja aprovada, mas não esteja ativada.</span><span class="sxs-lookup"><span data-stu-id="9dec4-161">However, during production, you can select a formula version that is approved, but that isn't activated.</span></span>

<span data-ttu-id="9dec4-162">Para ajudar a proteger uma fórmula ou versão da fórmula, você poderá definir os parâmetros **Bloquear edição** e **Bloquear remoção de aprovação** no formulário **Parâmetros de controle da produção**.</span><span class="sxs-lookup"><span data-stu-id="9dec4-162">To help secure a formula or formula version, you can set the **Block editing** and **Block removal of approval** parameters on the **Production control parameters** page.</span></span>

<span data-ttu-id="9dec4-163">Se você selecionar **Bloquear edição** e a fórmula for aprovada, nenhum campo nas linhas da fórmula poderá ser excluído ou editado.</span><span class="sxs-lookup"><span data-stu-id="9dec4-163">If you select **Block editing**, and the formula is approved, no fields on the formula lines can be deleted or edited.</span></span> <span data-ttu-id="9dec4-164">No entanto, se você remover a aprovação da fórmula, você poderá excluir e modificar as linhas da fórmula.</span><span class="sxs-lookup"><span data-stu-id="9dec4-164">However, if you remove the approval of the formula, you can delete and modify the formula lines.</span></span> <span data-ttu-id="9dec4-165">Você também pode criar novas fórmulas e novas versões da fórmula.</span><span class="sxs-lookup"><span data-stu-id="9dec4-165">You can also create new formulas and new formula versions.</span></span>

<span data-ttu-id="9dec4-166">Se você selecionar **Bloquear remoção da aprovação**, você não poderá remover a aprovação de uma fórmula ou versão da fórmula aprovada.</span><span class="sxs-lookup"><span data-stu-id="9dec4-166">If you select **Block removal of approval**, you can't remove the approval of an approved formula or formula version.</span></span> <span data-ttu-id="9dec4-167">No entanto, você pode criar novas fórmulas e novas versões da fórmula e pode remover a ativação da versão da fórmula.</span><span class="sxs-lookup"><span data-stu-id="9dec4-167">However, you can create new formulas and new formula versions, and you can remove the activation of the formula version.</span></span>

<span data-ttu-id="9dec4-168">Você pode adicionar mais níveis de controle, usando a funcionalidade de assinatura eletrônica.</span><span class="sxs-lookup"><span data-stu-id="9dec4-168">You can add more levels of control by using the electronic signature functionality.</span></span> <span data-ttu-id="9dec4-169">Quando um usuário é configurado de forma que uma assinatura eletrônica seja necessária no momento de aprovação da fórmula, uma página **Assinatura** será exibida quando a fórmula estiver ativada.</span><span class="sxs-lookup"><span data-stu-id="9dec4-169">When a user is set up so that an electronic signature is required at the time of formula approval, a **Signature** page appears when the formula is activated.</span></span> <span data-ttu-id="9dec4-170">O usuário deve estar autorizado para assinar eletronicamente e o certificado deve ser validado com êxito antes que a alteração seja comprometida.</span><span class="sxs-lookup"><span data-stu-id="9dec4-170">The user must be authorized to sign electronically, and the certificate must be successfully validated before the change can be committed.</span></span> <span data-ttu-id="9dec4-171">Se a sua assinatura não puder ser autenticada, a aprovação ou a remoção da aprovação será negada e a alteração que a iniciou a aprovação ou remoção da aprovação voltará para seu estado original.</span><span class="sxs-lookup"><span data-stu-id="9dec4-171">If the signature can't be authenticated, the approval or removal of approval is denied, and the change that initiated the approval or removal of approval is returned to its original state.</span></span>

## <a name="use-the-scalable-feature"></a><span data-ttu-id="9dec4-172">Usar o recurso escalonável</span><span class="sxs-lookup"><span data-stu-id="9dec4-172">Use the Scalable feature</span></span>
<span data-ttu-id="9dec4-173">O recurso Escalonável estará disponível somente se todos os componentes do item da fórmula forem definidos como **Consumo variável**.</span><span class="sxs-lookup"><span data-stu-id="9dec4-173">The Scalable feature is available only if all the item components in the formula are set to **Variable consumption**.</span></span> <span data-ttu-id="9dec4-174">O recurso não está disponível se os componentes de itens forem  **Consumo fixo** ou **Consumo em etapas**.</span><span class="sxs-lookup"><span data-stu-id="9dec4-174">The feature isn't available if item components are set to **Fixed consumption** or **Step consumption**.</span></span> <span data-ttu-id="9dec4-175">Quando o recurso Escalável for usado, se você alterar um ingrediente em uma fórmula, a quantidade dos outros ingredientes que você selecionar será ajustada.</span><span class="sxs-lookup"><span data-stu-id="9dec4-175">When the Scalable feature is used, if you change an ingredient in a formula, the quantity of the other ingredients that you select is adjusted.</span></span> <span data-ttu-id="9dec4-176">O tamanho da fórmula também será ajustado.</span><span class="sxs-lookup"><span data-stu-id="9dec4-176">The size of the formula is also adjusted.</span></span> <span data-ttu-id="9dec4-177">Da mesma forma, se você alterar o tamanho da fórmula, a quantidade de todos os ingredientes escaláveis será alterada.</span><span class="sxs-lookup"><span data-stu-id="9dec4-177">Likewise, if you change the formula size, the quantity of all scalable ingredients is changed.</span></span> <span data-ttu-id="9dec4-178">Este recurso é criado especificamente para criação e manutenção da fórmula.</span><span class="sxs-lookup"><span data-stu-id="9dec4-178">This feature is intended specifically for formula creation and maintenance.</span></span> <span data-ttu-id="9dec4-179">Não indica se a quantidade de um ingrediente estará dimensionada para cima ou para baixo em uma ordem de lote.</span><span class="sxs-lookup"><span data-stu-id="9dec4-179">It doesn't indicate whether the quantity of an ingredient will be scaled up or down on a batch order.</span></span>

## <a name="use-step-consumption"></a><span data-ttu-id="9dec4-180">Usar consumo em etapas</span><span class="sxs-lookup"><span data-stu-id="9dec4-180">Use Step consumption</span></span>
<span data-ttu-id="9dec4-181">O consumo em etapas elimina a necessidade de inserir uma quantidade na guia **Linha da fórmula** de um ingrediente.</span><span class="sxs-lookup"><span data-stu-id="9dec4-181">Step consumption eliminates the requirement that you must enter a quantity on the **Formula line** tab for an ingredient.</span></span> <span data-ttu-id="9dec4-182">Em vez de isso, o consumo da etapa é configurado para ter um valor **Da série** e **Quantidade**.</span><span class="sxs-lookup"><span data-stu-id="9dec4-182">Instead, Step consumption is configured so that it has a **From series** value and a **Quantity** value.</span></span> <span data-ttu-id="9dec4-183">As informações do registro de Consumo da etapa por série que atendem à quantidade na ordem do lote são selecionadas.</span><span class="sxs-lookup"><span data-stu-id="9dec4-183">The information from the Step consumption per series record that satisfies the quantity on the batch order is selected.</span></span> <span data-ttu-id="9dec4-184">O consumo da etapa é útil quando a taxa de consumo não é linear em relação ao tamanho da ordem de lote, e somente aumenta a necessidade quando um determinado limite de quantidade é atingido.</span><span class="sxs-lookup"><span data-stu-id="9dec4-184">Step consumption is useful when the consumption rate isn't linear with respect to the batch order size and only increases the requirement when a specific quantity threshold is met.</span></span> <span data-ttu-id="9dec4-185">Para habilitar esse recurso para uma nova fórmula, no grupo **Cálculo de consumo**, altere a configuração da fórmula para o ingrediente aplicável de  **Padrão** para **Etapa**.</span><span class="sxs-lookup"><span data-stu-id="9dec4-185">To enable this feature for a new formula, under the **Consumption calculation** group, change the formula setting for the applicable ingredient from **Standard** to **Step**.</span></span> <span data-ttu-id="9dec4-186">Você especifica esse método de consumo na guia **Configuração** da página **Linha da fórmula**.</span><span class="sxs-lookup"><span data-stu-id="9dec4-186">You specify this consumption method on the **Setup** tab of the **Formula line** page.</span></span>

---
title: Estado do ciclo de vida de produto
description: O estado de um ciclo de vida do produto documenta o estado do ciclo de vida de um produto ou grade do produto liberado.
author: cvocph
manager: AnnBe
ms.date: 12/08/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductLifecycleState, EcoResReleasedProductLifecycleStateChanges
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: cvocph
ms.dyn365.ops.version: 7.3
ms.search.validFrom: 2017-12-31
ms.translationtype: HT
ms.sourcegitcommit: ceea24519d641c676521771cee274feb64ca7783
ms.openlocfilehash: 8337f1dfb938f9fa69924e77a25a68ee56dbd2ac
ms.contentlocale: pt-br
ms.lasthandoff: 01/19/2018

---

# <a name="product-lifecycle-state"></a><span data-ttu-id="ab98e-103">Estado do ciclo de vida de produto</span><span class="sxs-lookup"><span data-stu-id="ab98e-103">Product lifecycle state</span></span> 

[!include[banner](../includes/banner.md)]


<span data-ttu-id="ab98e-104">O estado de um ciclo de vida do produto documenta o estado do ciclo de vida de um produto ou grade do produto liberado.</span><span class="sxs-lookup"><span data-stu-id="ab98e-104">A product lifecycle state documents the lifecycle state of a released product or product variant.</span></span> <span data-ttu-id="ab98e-105">Os estados do ciclo de vida de produto são definidos pelo usuário, geralmente um gerente de produto ou um gerente de dados mestre de produto.</span><span class="sxs-lookup"><span data-stu-id="ab98e-105">Product lifecycle states are defined by the user, typically a product manager or a product master data manager.</span></span> <span data-ttu-id="ab98e-106">Os processos de negócios específicos, como planejamento mestre podem ser afetados por um estado específico do ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="ab98e-106">Specific business processes, such as master planning, can be affected by a specific lifecycle state.</span></span>   
 
<span data-ttu-id="ab98e-107">Um produto ou grade de produto pode ser associado a um estado do ciclo de vida do produto que documenta em qual estado do ciclo de vida um produto ou grade específica está no momento.</span><span class="sxs-lookup"><span data-stu-id="ab98e-107">A released product or product variant can be associated with a product lifecycle state that documents in which lifecycle state a specific product or variant is currently in.</span></span> <span data-ttu-id="ab98e-108">É possível definir qualquer número de estados do ciclo de vida do produto atribuindo um nome e uma descrição do estado.</span><span class="sxs-lookup"><span data-stu-id="ab98e-108">You can define any number of product lifecycle states by assigning a state name and description.</span></span> <span data-ttu-id="ab98e-109">Você pode selecionar um estado do ciclo de vida como o status padrão de novos produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="ab98e-109">You can select one lifecycle state as the default state for new released products.</span></span> <span data-ttu-id="ab98e-110">As grades de produtos liberados herdam o estado do ciclo de vida do produto de seus produtos mestres liberados na criação.</span><span class="sxs-lookup"><span data-stu-id="ab98e-110">Released product variants inherit their product lifecycle state from their released product master on creation.</span></span> <span data-ttu-id="ab98e-111">Ao alterar o estado do ciclo de vida em um produto mestre liberado, você pode optar por atualizar todas as grades existentes com o mesmo estado original.</span><span class="sxs-lookup"><span data-stu-id="ab98e-111">When changing the lifecycle state on a released product master, you can choose to update all existing variants that have the same original state.</span></span>  

## <a name="create-a-new-product-lifecycle-state"></a><span data-ttu-id="ab98e-112">Criar um novo estado do ciclo de vida do produto</span><span class="sxs-lookup"><span data-stu-id="ab98e-112">Create a new product lifecycle state</span></span> 
 
- <span data-ttu-id="ab98e-113">Para criar um novo estado do ciclo de vida do produto, reproduza ou leia a guia de tarefas **Criar um novo estado do ciclo de vida do produto**.</span><span class="sxs-lookup"><span data-stu-id="ab98e-113">To create a new product lifecycle state, play or read the task guide **Create a new product lifecycle state**.</span></span> 

-  <span data-ttu-id="ab98e-114">Para criar um estado do ciclo de vida do produto padrão, reproduza ou leia a guia de tarefas **Criar um estado do ciclo de vida do produto padrão**.</span><span class="sxs-lookup"><span data-stu-id="ab98e-114">To create a default product lifecycle state, play or read the task guide **Create a default product lifecycle state**.</span></span>   

## <a name="associate-product-lifecycle-states-to-released-products"></a><span data-ttu-id="ab98e-115">Associar estados do ciclo de vida do produto aos produtos liberados</span><span class="sxs-lookup"><span data-stu-id="ab98e-115">Associate product lifecycle states to released products</span></span>  

<span data-ttu-id="ab98e-116">Há várias formas de associar um estado do ciclo de vida do produto aos produtos ou grades de produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="ab98e-116">There are multiple ways to associate a product lifecycle state to released products or product variants.</span></span>

-  <span data-ttu-id="ab98e-117">Na criação de um novo produto liberado, o **Estado do ciclo de vida do produto** padrão é atribuído automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ab98e-117">On creation of a new released product, the default **Product lifecycle state** is automatically assigned.</span></span> 
-  <span data-ttu-id="ab98e-118">Na liberação de um produto para uma entidade legal, o **O estado do ciclo de vida do produto** padrão é atribuído automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ab98e-118">On release of a product to a legal entity, the default **Product lifecycle state** is automatically assigned.</span></span> 
-  <span data-ttu-id="ab98e-119">Na liberação de uma grade de produto a uma entidade legal, o **Estado do ciclo de vida do produto** associado a produtos mestre liberados na entidade legal é atribuído automaticamente à nova grade.</span><span class="sxs-lookup"><span data-stu-id="ab98e-119">On release of a product variant to a legal entity, the **Product lifecycle state** associated to the released product master in this legal entity is automatically assigned to the new variant.</span></span> 

<span data-ttu-id="ab98e-120">Você pode atualizar manualmente o estado do ciclo de vida do produto usando:</span><span class="sxs-lookup"><span data-stu-id="ab98e-120">You can manually update the product lifecycle state by using:</span></span> 

-    <span data-ttu-id="ab98e-121">A página de listagem **Produtos liberados** ou **Exibição de detalhes**.</span><span class="sxs-lookup"><span data-stu-id="ab98e-121">The **Released products** list page or **Details view**.</span></span> 
-  <span data-ttu-id="ab98e-122">A página de listagem **Grades de produtos liberadas** ou **Exibição de detalhes**.</span><span class="sxs-lookup"><span data-stu-id="ab98e-122">The **Released product variants** list page or **Details view**.</span></span> 
-  <span data-ttu-id="ab98e-123">Localize os produtos obsoletos ou grades de produtos com base em demanda e associe um estado do ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="ab98e-123">Find the obsolete products or product variants based on demand and associate a lifecycle state.</span></span>  

<span data-ttu-id="ab98e-124">Para obter informações detalhadas sobre como associar estados do ciclo de vida do produto, reproduza ou leia as duas seguintes guias de tarefas.</span><span class="sxs-lookup"><span data-stu-id="ab98e-124">For detailed information about how to associate product lifecycle states, play or read the following two task guides.</span></span>

-  <span data-ttu-id="ab98e-125">Para associar um estado do ciclo de vida do produto a um produto mestre, reproduza ou leia a guia de tarefas **Atribuir um estado do ciclo de vida do produto a um produto mestre liberado**.</span><span class="sxs-lookup"><span data-stu-id="ab98e-125">To associate a product lifecycle state to a released product master, play or read the task guide **Assign a product lifecycle state to a released product master**.</span></span> 

-  <span data-ttu-id="ab98e-126">Para associar um estado do ciclo de vida do produto a um produto liberado, reproduza ou leia a guia de tarefas **Atribuir um estado do ciclo de vida do produto a um produto liberado**.</span><span class="sxs-lookup"><span data-stu-id="ab98e-126">To associate a product lifecycle state to a release product, play or read the task guide **Assign a product lifecycle state to a released product**.</span></span> 

## <a name="impact-on-master-planning"></a><span data-ttu-id="ab98e-127">Impacto no planejamento mestre</span><span class="sxs-lookup"><span data-stu-id="ab98e-127">Impact on master planning</span></span> 

<span data-ttu-id="ab98e-128">O estado do ciclo de vida de produto só tem um sinalizador de controle: **Está ativo para planejar**.</span><span class="sxs-lookup"><span data-stu-id="ab98e-128">The product lifecycle state has only one control flag: **Is active for planning**.</span></span> <span data-ttu-id="ab98e-129">Por padrão, é definido como **Sim** para todos os estados do ciclo de vida do produto criados, mas pode ser alterado para **Não**.</span><span class="sxs-lookup"><span data-stu-id="ab98e-129">By default, this is set to **Yes** for all created product lifecycle states, but it can be changed to **No**.</span></span> <span data-ttu-id="ab98e-130">Quando definido como **Não**, os produtos liberados ou grades do produto liberados associados são:</span><span class="sxs-lookup"><span data-stu-id="ab98e-130">When set to **No**, the associated released products or released product variants are:</span></span> 

-  <span data-ttu-id="ab98e-131">Excluído do planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="ab98e-131">Excluded from master planning.</span></span> 
-  <span data-ttu-id="ab98e-132">Excluído do cálculo do nível da BOM.</span><span class="sxs-lookup"><span data-stu-id="ab98e-132">Excluded from BOM-level calculation.</span></span> 

<span data-ttu-id="ab98e-133">Para obter informações detalhadas sobre como usar o estado do ciclo de vida do produto para excluir produtos do cálculo de planejamento mestre e do nível da BOM, reproduza ou leia a guia de tarefas **Criar um estado do ciclo de vida do produto para excluir produtos do planejamento mestre**.</span><span class="sxs-lookup"><span data-stu-id="ab98e-133">For detailed information about how to use product lifecycle state to exclude products from master planning and BOM-level calculation, play or read the task guide **Create a product lifecycle state to exclude products from Master planning**.</span></span>

> [!NOTE]
> <span data-ttu-id="ab98e-134">Por motivo de desempenho, é altamente recomendável associar todos os produtos liberados ou grades de produtos obsoletos, especialmente ao trabalhar com grades de configuração de produto não reutilizáveis, com um estado do ciclo de vida do produto que será desativado para o planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="ab98e-134">For performance reasons, it is highly recommended to associate all obsolete released products or product variants, especially when working with non-reusable product configuration variants, with a product lifecycle state that is deactivated for master planning.</span></span>  
 
## <a name="default-migration-import-and-export"></a><span data-ttu-id="ab98e-135">Migração, importação e exportação padrão</span><span class="sxs-lookup"><span data-stu-id="ab98e-135">Default migration, import, and export</span></span> 

<span data-ttu-id="ab98e-136">Os estados do ciclo de vida do produto não são compatíveis com entidades de dados, e o estado do ciclo de vida não pode ser definido para um estado variável pelas entidades de dados de produto liberadas.</span><span class="sxs-lookup"><span data-stu-id="ab98e-136">The product lifecycle states are not supported by data entities, and the lifecycle state cannot be set to a variable state through the released product data entities.</span></span>

-  <span data-ttu-id="ab98e-137">Na migração de versões anteriores, o estado do ciclo de vida de todos os produtos e as grades de produto ficarão em branco.</span><span class="sxs-lookup"><span data-stu-id="ab98e-137">On migration from previous releases, the lifecycle state of all products and product variants will be blank.</span></span>  
-  <span data-ttu-id="ab98e-138">Ao importar produtos liberados por uma entidade de dados, o estado do ciclo de vida padrão será aplicado na criação.</span><span class="sxs-lookup"><span data-stu-id="ab98e-138">When importing released products through a data entity, the default lifecycle state will be applied on creation.</span></span>  
-  <span data-ttu-id="ab98e-139">Ao importar grades de produto liberadas por uma entidade de dados, o estado do ciclo de vida do produto do mestre de produto liberado será importado.</span><span class="sxs-lookup"><span data-stu-id="ab98e-139">When importing released product variants through a data entity, the product lifecycle state of the released product master will be imported.</span></span>   
 
## <a name="find-obsolete-products-and-products-variants"></a><span data-ttu-id="ab98e-140">Localizar produtos e grades de produto obsoletos</span><span class="sxs-lookup"><span data-stu-id="ab98e-140">Find obsolete products and products variants</span></span> 
 
<span data-ttu-id="ab98e-141">Você poderá executar uma análise de simulação para localizar produtos ou grades de produtos liberados obsoletos e atualizar o status do ciclo de vida do produto.</span><span class="sxs-lookup"><span data-stu-id="ab98e-141">You can run a simulation analysis to find the obsolete released products or product variants and then update their product lifecycle status.</span></span> <span data-ttu-id="ab98e-142">Para localizar, produtos obsoletos, reproduza ou leia o guia de tarefas **Localizar grades de produto obsoletos e atribuir um estado do ciclo de vida do produto**.</span><span class="sxs-lookup"><span data-stu-id="ab98e-142">To find obsolete products, play and read the task guide **Find obsolete product variants and assign a product lifecycle state**.</span></span> <span data-ttu-id="ab98e-143">Esta guia de tarefas mostra como localizar produtos ou grades de produto liberados obsoletos e como associar um estado do ciclo de vida do produto a produtos obsoletos.</span><span class="sxs-lookup"><span data-stu-id="ab98e-143">This task guide shows how to find obsolete released products or product variants and how to associate a product lifecycle state to the obsolete products.</span></span> <span data-ttu-id="ab98e-144">Também mostra como exibir os resultados de simulação e avaliar quantos produtos e grades de produto serão associadas a um novo estado do ciclo de vida de produto ao executar a atualização sem simulação.</span><span class="sxs-lookup"><span data-stu-id="ab98e-144">It also shows hot to view the simulation results and assess how many products and product variants will be associated with a new product lifecycle state when running the update without simulation.</span></span>  
 
<span data-ttu-id="ab98e-145">Ao executar a análise em um modo de simulação, os produtos e as grades de produto identificadas como obsoletos são exibidos em um formulário específico, no qual podem ser facilmente revisados.</span><span class="sxs-lookup"><span data-stu-id="ab98e-145">By running the analysis in a simulation mode, the products and product variants identified as obsolete are displayed in a specific form, where they can easily be reviewed.</span></span> <span data-ttu-id="ab98e-146">A análise pesquisa transações e dados mestres específicos para identificar produtos que não têm demanda dentro de um período variável e nenhum dado mestre que pode resultar em demanda.</span><span class="sxs-lookup"><span data-stu-id="ab98e-146">The analysis searches for transactions and specific master data to identify products that have no demand within a variable period and no master data that can result in demand.</span></span> <span data-ttu-id="ab98e-147">Os novos produtos lançados em um período de variáveis podem ser excluídos da análise.</span><span class="sxs-lookup"><span data-stu-id="ab98e-147">New released products within a variable period can be excluded from the analysis.</span></span> <span data-ttu-id="ab98e-148">Quando a simulação de análise retornar o resultado esperado, o usuário pode executar a análise e definir um novo estado do ciclo de vida do produto a todos os produtos identificados como obsoletos pela análise.</span><span class="sxs-lookup"><span data-stu-id="ab98e-148">When the analysis simulation returns the expected result, the user can run the analysis and set a new product lifecycle state to all products identified as obsolete by the analysis.</span></span>  
 
> [!NOTE]
> <span data-ttu-id="ab98e-149">Observe que todas as análises e atualizações devem ser feitas dentro da mesma entidade legal.</span><span class="sxs-lookup"><span data-stu-id="ab98e-149">Note that all analysis and updates must be done within the same legal entity.</span></span>  
 
## <a name="criteria-to-select-and-update-released-products-or-product-variants"></a><span data-ttu-id="ab98e-150">Os critérios para selecionar e atualizar os produtos e grades de produtos liberados</span><span class="sxs-lookup"><span data-stu-id="ab98e-150">Criteria to select and update released products or product variants</span></span> 
 
<span data-ttu-id="ab98e-151">Use os seguintes critérios para selecionar e atualizar os produtos e grades de produtos liberados:</span><span class="sxs-lookup"><span data-stu-id="ab98e-151">Use the following criteria to select and update the released products and product variants:</span></span> 

-    <span data-ttu-id="ab98e-152">O estado do ciclo de vida do produto ou grade do produto devem ser diferentes do novo status desejado.</span><span class="sxs-lookup"><span data-stu-id="ab98e-152">The product lifecycle state of the product or product variant must be different from the new desired state.</span></span> 
-  <span data-ttu-id="ab98e-153">O produtos ou a grade do produto foram criados alguns dias antes com base no número de dias inserido na caixa de diálogo de seleção.</span><span class="sxs-lookup"><span data-stu-id="ab98e-153">The product or product variant was created some days ago based on the number of days that you enter in the selection dialog box.</span></span> 
-  <span data-ttu-id="ab98e-154">Não há nenhuma ordem de produção aberta (= status < concluído) para o produto ou grade de produto.</span><span class="sxs-lookup"><span data-stu-id="ab98e-154">There are no open production orders (= status < ended) for the product or product variant.</span></span> 
-  <span data-ttu-id="ab98e-155">Não há transações de estoque abertas (= status de saída ReservPhysical para QuotationIssue ou status de recebimento Registrered para QuotationReceipt) para o produto ou grade do produto.</span><span class="sxs-lookup"><span data-stu-id="ab98e-155">There are no open inventory transactions (= status issue ReservPhysical to QuotationIssue or status receipt Registrered to QuotationReceipt) for the product or product variant.</span></span> 
-  <span data-ttu-id="ab98e-156">Não há transações de estoque dentro do último número de dias para o produto ou grade de produto.</span><span class="sxs-lookup"><span data-stu-id="ab98e-156">There are no inventory transactions within the last number of days for the product or product variant.</span></span> 
-  <span data-ttu-id="ab98e-157">Não há demanda futura ou previsão de fornecimento para o produto ou grade de produto.</span><span class="sxs-lookup"><span data-stu-id="ab98e-157">There is no future demand or supply forecast for the product or product variant.</span></span>  
-  <span data-ttu-id="ab98e-158">Nenhum nível de estoque mínimo foi definido na cobertura do item para o produto ou grade de produto.</span><span class="sxs-lookup"><span data-stu-id="ab98e-158">No minimum stock level has been set in item coverage for the product or product variant.</span></span> 
-  <span data-ttu-id="ab98e-159">Nenhuma regra kanban de quantidade fixa do produto ou grade de produto.</span><span class="sxs-lookup"><span data-stu-id="ab98e-159">No active fixed quantity kanban rule for the product or product variant.</span></span>  
-  <span data-ttu-id="ab98e-160">Nenhuma linha de ordem de serviço para produto ou grade de produto.</span><span class="sxs-lookup"><span data-stu-id="ab98e-160">No service order line for the product or product variant.</span></span> 
-  <span data-ttu-id="ab98e-161">Nenhuma linha do contrato de compra ou venda ativa ou futura para o produto ou grade do produto.</span><span class="sxs-lookup"><span data-stu-id="ab98e-161">No active or future sales or purchase agreement lines for the product or product variant.</span></span> 
-  <span data-ttu-id="ab98e-162">O produto ou grade do produto não é usada em uma BOM associada a uma versão da BOM não aprovada expirada para um produto ou grade que esteja ativo(a) para planejamento.</span><span class="sxs-lookup"><span data-stu-id="ab98e-162">The product or product variant is not used in a BOM that is associated with a non-expired approved BOM version for a product or variant that is active for planning.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ab98e-163">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="ab98e-163">Related topics</span></span>

-  <span data-ttu-id="ab98e-164">Criar um novo estado do ciclo de vida do produto</span><span class="sxs-lookup"><span data-stu-id="ab98e-164">Create a new product lifecycle state</span></span>
-  <span data-ttu-id="ab98e-165">Criar um novo estado do ciclo de vida do produto padrão</span><span class="sxs-lookup"><span data-stu-id="ab98e-165">Create a default new product lifecycle state</span></span>
-  <span data-ttu-id="ab98e-166">Atribuir um estado do ciclo de vida do produto a um mestre de produto liberado</span><span class="sxs-lookup"><span data-stu-id="ab98e-166">Assign a product lifecycle state to a released product master</span></span>
-  <span data-ttu-id="ab98e-167">Atribuir um estado do ciclo de vida do produto a um produto liberado</span><span class="sxs-lookup"><span data-stu-id="ab98e-167">Assign a product lifecycle state to a released product</span></span>
-  <span data-ttu-id="ab98e-168">Localizar grades de produto obsoletos e atribuir um estado do ciclo de vida do produto</span><span class="sxs-lookup"><span data-stu-id="ab98e-168">Find obsolete product variants and assign a product lifecycle state</span></span>
-  <span data-ttu-id="ab98e-169">Criar um estado do ciclo de vida do produto para excluir produtos do planejamento mestre</span><span class="sxs-lookup"><span data-stu-id="ab98e-169">Create a product lifecycle state to exclude products from Master planning</span></span>

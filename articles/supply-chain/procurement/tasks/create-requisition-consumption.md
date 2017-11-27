--- 
title: "Criar uma requisição para consumo"
description: "Este procedimento apresenta o processo de criação de uma requisição."
author: mkirknel
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 55ef4b1757a6f3c28c8575412d66488fda8608a5
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---
# <a name="create-a-requisition-for-consumption"></a><span data-ttu-id="f7d3c-103">Criar uma requisição para consumo</span><span class="sxs-lookup"><span data-stu-id="f7d3c-103">Create a requisition for consumption</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f7d3c-104">Este procedimento apresenta o processo de criação de uma requisição.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-104">This procedure walks you through the process of creating a requisition.</span></span> <span data-ttu-id="f7d3c-105">Mostra as diferentes formas de pesquisar por produtos no catálogo de aquisições e como adicionar um produto que não está no catálogo.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-105">It shows you different ways to search for products in your procurement catalog and how to add a product that isn’t in your catalog.</span></span> <span data-ttu-id="f7d3c-106">Antes de iniciar esse procedimento, você deve ter uma política de compras configurada com Consumo como o tipo padrão de requisição.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-106">Before you start this procedure, you must have a purchasing policy set up with Consumption as the default type of requisition.</span></span> <span data-ttu-id="f7d3c-107">Você pode ver todo esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-107">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="f7d3c-108">O procedimento só pode ser realizado por um perfil de usuário configurado como funcionário.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-108">The procedure can only be carried out by a user profile that is set up as worker.</span></span>  <span data-ttu-id="f7d3c-109">Essa tarefa é normalmente realizada por um funcionário.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-109">This task would normally be carried out by an employee.</span></span> <span data-ttu-id="f7d3c-110">O Funcionário usa função de segurança irá permitir que você realize as tarefas, ou se você estiver usando USMF, é possível se conectar como Alicia.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-110">The Employee employ security role will allow you to carry out the tasks, or if you’re using USMF, you can log in as Alicia.</span></span>


## <a name="create-a-new-requisition"></a><span data-ttu-id="f7d3c-111">Criar uma nova requisição</span><span class="sxs-lookup"><span data-stu-id="f7d3c-111">Create a new requisition</span></span>
1. <span data-ttu-id="f7d3c-112">Vá para Aquisição e fornecimento > Requisições de compra > Requisições de compra preparadas por mim.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-112">Go to Procurement and sourcing > Purchase requisitions > Purchase requisitions prepared by me.</span></span>
2. <span data-ttu-id="f7d3c-113">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-113">Click New.</span></span>
3. <span data-ttu-id="f7d3c-114">No campo Nome, forneça o nome da requisição.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-114">In the Name field, give the requisition a name.</span></span>
4. <span data-ttu-id="f7d3c-115">No campo Data de solicitação, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-115">In the Requested date field, enter a date.</span></span>
    * <span data-ttu-id="f7d3c-116">Por padrão, a data de solicitação e a data contábil são copiadas para as linhas de requisição de compra.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-116">By default, the requested date and accounting date are copied to the purchase requisition lines.</span></span> <span data-ttu-id="f7d3c-117">Elas podem ser alteradas no nível da linha.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-117">They can be changed at the line level.</span></span> <span data-ttu-id="f7d3c-118">A data de solicitação é a data de entrega da solicitação.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-118">The requested date is the requested delivery date.</span></span>  
5. <span data-ttu-id="f7d3c-119">No campo Data contábil, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-119">In the Accounting date field, enter a date.</span></span>
    * <span data-ttu-id="f7d3c-120">A data contábil é usada para registrar a entrada contábil na contabilidade e para validar se os fundos de orçamento estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-120">The accounting date is used to record the accounting entry in the general ledger, and to validate whether budget funds are available.</span></span>  
6. <span data-ttu-id="f7d3c-121">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-121">Click OK.</span></span>
7. <span data-ttu-id="f7d3c-122">No campo Motivo, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-122">In the Reason field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="f7d3c-123">Por padrão, o motivo de justificativa de negócio selecionado é exibido para as linhas de requisição de compra, mas você pode alterá-lo no nível da linha.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-123">By default, the business justification reason that you select appears for the purchase requisition lines, but you can change it at the line level.</span></span>    
8. <span data-ttu-id="f7d3c-124">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-124">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="f7d3c-125">Selecione o motivo</span><span class="sxs-lookup"><span data-stu-id="f7d3c-125">Select the reason</span></span>
10. <span data-ttu-id="f7d3c-126">No campo detalhes insira uma justificativa mais descritiva para a requisição</span><span class="sxs-lookup"><span data-stu-id="f7d3c-126">In the details field enter a more descriptive justification for the requisition</span></span>

## <a name="add-a-line-to-the-requisition"></a><span data-ttu-id="f7d3c-127">Adicionar uma linha à requisição</span><span class="sxs-lookup"><span data-stu-id="f7d3c-127">Add a line to the requisition</span></span>
1. <span data-ttu-id="f7d3c-128">Clique em Adicionar linha.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-128">Click Add line.</span></span>
    * <span data-ttu-id="f7d3c-129">Existem duas maneiras de adicionar linhas à requisição de compra.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-129">There are two ways of adding lines to the purchase requisition.</span></span> <span data-ttu-id="f7d3c-130">Se você sabe o número do produto ou sabe que está solicitando um produto que não está no catálogo de produtos, então é possível adicionar a linha diretamente através do "Adicionar linha".</span><span class="sxs-lookup"><span data-stu-id="f7d3c-130">If you already know the product number or you already  know that you are requesting a product that is not in the product catalog, then you can add the line directly with "Add line".</span></span> <span data-ttu-id="f7d3c-131">A outra forma é utilizando o "Adicionar produtos" através do qual é possível usar pesquisa e filtragem para localizar os itens no catálogo de produtos.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-131">The other way is to use "Add products" where you can use searching and filtering to find items in the product catalog.</span></span>    
2. <span data-ttu-id="f7d3c-132">Clique na linha que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-132">Click on the row you just created.</span></span>
    * <span data-ttu-id="f7d3c-133">O solicitante é o funcionário que solicitou a requisição.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-133">The requester is the worker that has requested the requisition.</span></span>   
    * <span data-ttu-id="f7d3c-134">Por padrão a pessoa que prepara a requisição é o funcionário que a solicitou.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-134">By default the person preparing the requisition is the worker who has requested it.</span></span> <span data-ttu-id="f7d3c-135">Você precisa receber permissão para preparar uma linha de requisição em nome de outro funcionário.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-135">You have to be given permission to prepare a requisition line on behalf of another worker.</span></span> <span data-ttu-id="f7d3c-136">Se você possuir tais permissões então os outros funcionários aparecerão nessa pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-136">If you have such permissions then the other workers will show up in this lookup.</span></span>  
3. <span data-ttu-id="f7d3c-137">No campo Número de item, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-137">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="f7d3c-138">Os itens disponíveis para escolha são delimitados pela política de acesso a categoria e pelo catálogo de aquisições para a pessoa jurídica compradora.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-138">The items that are available for you to choose are limited by the category access policy and the procurement catalog for the buying legal entity.</span></span>   
4. <span data-ttu-id="f7d3c-139">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-139">In the Quantity field, enter a number.</span></span>

## <a name="add-more-products-to-the-requisition"></a><span data-ttu-id="f7d3c-140">Adicionar mais produtos à requisição</span><span class="sxs-lookup"><span data-stu-id="f7d3c-140">Add more products to the requisition</span></span>
1. <span data-ttu-id="f7d3c-141">Clique em Adicionar produtos.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-141">Click Add products.</span></span>
    * <span data-ttu-id="f7d3c-142">Essa é a opção na qual você pode pesquisar por produtos no catálogo de produtos.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-142">This is the option where you can search for products in the product catalog.</span></span>    
2. <span data-ttu-id="f7d3c-143">No campo Localizar nó da categoria de aquisição, digite a primeira parte do nome da categoria que você está procurando, e então clique em Inserir.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-143">In the Find procurement category node field, type the first part of the name of the category that you are looking for, and then click Enter.</span></span>
    * <span data-ttu-id="f7d3c-144">Por exemplo, digite comput.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-144">For example, type comput.</span></span>  
3. <span data-ttu-id="f7d3c-145">Use o atalho InvokeDefaultButton.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-145">Use the InvokeDefaultButton shortcut.</span></span>
4. <span data-ttu-id="f7d3c-146">Utilize o Filtro para filtrar a lista de produtos na categoria selecionada.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-146">Use the Filter to filter the list of products in the selected category.</span></span>
5. <span data-ttu-id="f7d3c-147">Selecione a carta de produtos que você deseja adicionar à requisição.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-147">Select the product card that you want to add to the requisition.</span></span>
6. <span data-ttu-id="f7d3c-148">Clique em Adicionar às linhas.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-148">Click Add to lines.</span></span>
7. <span data-ttu-id="f7d3c-149">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-149">In the Quantity field, enter a number.</span></span>
8. <span data-ttu-id="f7d3c-150">No campo Localizar nó da categoria de aquisição, digite a primeira parte do nome da categoria que você está procurando, e então clique em Inserir.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-150">In the Find procurement category node field, type the first part of the name of the category that you are looking for, and then click Enter.</span></span>
    * <span data-ttu-id="f7d3c-151">Por exemplo, digite Alto (highlighters).</span><span class="sxs-lookup"><span data-stu-id="f7d3c-151">For example, type High (highlighters).</span></span>  
9. <span data-ttu-id="f7d3c-152">Use o atalho InvokeDefaultButton.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-152">Use the InvokeDefaultButton shortcut.</span></span>
10. <span data-ttu-id="f7d3c-153">Clique em Adicionar produtos não listados às linhas para adicionar um produto que não está listado no catálogo de aquisições.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-153">Click Add unlisted product to lines to add a product that’s not listed in the procurement catalog.</span></span>
11. <span data-ttu-id="f7d3c-154">No campo Nome do produto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-154">In the Product name field, type a value.</span></span>
12. <span data-ttu-id="f7d3c-155">No campo Unidade, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-155">In the Unit field, type a value.</span></span>
13. <span data-ttu-id="f7d3c-156">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-156">Click OK.</span></span>
14. <span data-ttu-id="f7d3c-157">No campo Descrição do item, adicione uma descrição do produto.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-157">In the Item description field, add a description of the product.</span></span>
15. <span data-ttu-id="f7d3c-158">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-158">In the Quantity field, enter a number.</span></span>
16. <span data-ttu-id="f7d3c-159">No campo Preço unitário, insira um número.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-159">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="f7d3c-160">Se você sabe o preço para um fornecedor específico (que você seleciona no campo conta de fornecedor) então esse preço pode ser inserido</span><span class="sxs-lookup"><span data-stu-id="f7d3c-160">If you know the price for a particular vendor (that you select in the vendor account field) then that price can be entered</span></span>   
17. <span data-ttu-id="f7d3c-161">No campo Conta de fornecedor, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-161">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="f7d3c-162">Os fornecedores que estão disponíveis neste campo dependem das políticas de compras e do status que o fornecedor tem para a categoria de aquisição atual.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-162">The vendors that are available in this field depend on the purchasing policies and the status that the vendor has for the current procurement category.</span></span> <span data-ttu-id="f7d3c-163">Como uma alternativa ao selecionar um fornecedor aqui, é possível clicar no botão Sugerir fornecedor.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-163">As an alternative to selecting a vendor here, you can click the Suggest vendor button.</span></span>    
18. <span data-ttu-id="f7d3c-164">Na lista, selecione o fornecedor que deseja utilizar.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-164">In the list, select the vendor you want to use.</span></span>
19. <span data-ttu-id="f7d3c-165">No campo Número externo do item, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-165">In the External item number field, type a value.</span></span>
    * <span data-ttu-id="f7d3c-166">Este é um número de referência para o produto que é conhecido pelo fornecedor.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-166">This is a reference number for the product that is known by the vendor.</span></span> <span data-ttu-id="f7d3c-167">Por exemplo, isso poderia ser o número de item do produto no catálogo do próprio fornecedor.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-167">For example, this could be the item number of the product in the vendor's own catalog.</span></span>  
20. <span data-ttu-id="f7d3c-168">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-168">Click OK.</span></span>

## <a name="distribute-amounts"></a><span data-ttu-id="f7d3c-169">Distribuir valores</span><span class="sxs-lookup"><span data-stu-id="f7d3c-169">Distribute amounts</span></span>
1. <span data-ttu-id="f7d3c-170">Clique em Financeiros.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-170">Click Financials.</span></span>
2. <span data-ttu-id="f7d3c-171">Clique em Distribuir valores.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-171">Click Distribute amounts.</span></span>
    * <span data-ttu-id="f7d3c-172">Este processo mostra como distribuir os custos da primeira linha entre 2 contas.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-172">This process shows you how to distribute the cost for the first line between 2 accounts.</span></span> <span data-ttu-id="f7d3c-173">Isso também pode ser feito mais tarde durante a revisão da requisição.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-173">This can also be done later when the requisition is in review.</span></span>  
3. <span data-ttu-id="f7d3c-174">Clique em Separar para criar uma nova linha de distribuição.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-174">Click Split to create a new distribution line.</span></span>
4. <span data-ttu-id="f7d3c-175">No campo Conta contábil, selecione o primeiro centro de custo que deverá receber parte do custo.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-175">In the Ledger account field select the first cost centre that should take part of the cost.</span></span>
5. <span data-ttu-id="f7d3c-176">Selecione a outra linha de distribuição.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-176">Select the other distribution line.</span></span>
6. <span data-ttu-id="f7d3c-177">No campo Conta contábil, especifique o outro centro de custo.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-177">In the Ledger account field specify the other cost centre.</span></span>
7. <span data-ttu-id="f7d3c-178">Clique em Distribuir igualmente.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-178">Click Distribute equally.</span></span>
8. <span data-ttu-id="f7d3c-179">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-179">Close the page.</span></span>

## <a name="view-line-details"></a><span data-ttu-id="f7d3c-180">Exibir detalhes de linha</span><span class="sxs-lookup"><span data-stu-id="f7d3c-180">View line details</span></span>
1. <span data-ttu-id="f7d3c-181">Ative a expansão da seção Detalhes de linha.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-181">Toggle the expansion of the Line details section.</span></span>

## <a name="submit-the-requisition"></a><span data-ttu-id="f7d3c-182">Enviar a requisição</span><span class="sxs-lookup"><span data-stu-id="f7d3c-182">Submit the requisition</span></span>
1. <span data-ttu-id="f7d3c-183">Clique em Fluxo de trabalho para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-183">Click Workflow to open the drop dialog.</span></span>
2. <span data-ttu-id="f7d3c-184">Clique em Enviar.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-184">Click Submit.</span></span>
3. <span data-ttu-id="f7d3c-185">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-185">Close the page.</span></span>
4. <span data-ttu-id="f7d3c-186">No campo Comentário, digite uma nota para o aprovador da requisição.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-186">In the Comment field, type a note for the approver of the requisition.</span></span>
5. <span data-ttu-id="f7d3c-187">Clique em Enviar.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-187">Click Submit.</span></span>
6. <span data-ttu-id="f7d3c-188">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-188">Close the page.</span></span>
7. <span data-ttu-id="f7d3c-189">Atualize a página.</span><span class="sxs-lookup"><span data-stu-id="f7d3c-189">Refresh the page.</span></span>



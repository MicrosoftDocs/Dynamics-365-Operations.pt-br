--- 
title: "Criar uma requisição que use um RFQ"
description: "Este guia mostra como adicionar o preço e a informação do vendedor a uma requisição da compra de um processo do RFQ."
author: mkirknel
manager: AnnBe
ms.date: 08/25/2016
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: d97ccd15031b2f7398486eee4a716ecef5e9dafd
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-requisition-that-uses-an-rfq"></a><span data-ttu-id="6dd88-103">Criar uma requisição que use um RFQ</span><span class="sxs-lookup"><span data-stu-id="6dd88-103">Create a requisition that uses an RFQ</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6dd88-104">Este guia mostra como adicionar o preço e a informação do vendedor a uma requisição da compra de um processo do RFQ.</span><span class="sxs-lookup"><span data-stu-id="6dd88-104">This guide shows how to add price and vendor information to a purchase requisition from an RFQ process.</span></span> <span data-ttu-id="6dd88-105">O exemplo mostrado neste guia pode ser usado na empresa dos dados do programa demonstrativo de USMF, e você entrar como um Admin para terminar todas as etapas.</span><span class="sxs-lookup"><span data-stu-id="6dd88-105">The example shown in this guide can be used in the USMF demo data company, and you must be logged in as an Admin to complete all the steps.</span></span> <span data-ttu-id="6dd88-106">As tarefas neste guia seriam feitas tipicamente por profissionais da obtenção.</span><span class="sxs-lookup"><span data-stu-id="6dd88-106">The tasks in this guide would typically be done by procurement professionals.</span></span>


## <a name="create-a-requisition"></a><span data-ttu-id="6dd88-107">Criar um requisito</span><span class="sxs-lookup"><span data-stu-id="6dd88-107">Create a requisition</span></span>
1. <span data-ttu-id="6dd88-108">Vá para Aquisição e fornecimento > Requisições de compra > Requisições de compra preparadas por mim.</span><span class="sxs-lookup"><span data-stu-id="6dd88-108">Go to Procurement and sourcing > Purchase requisitions > Purchase requisitions prepared by me.</span></span>
2. <span data-ttu-id="6dd88-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="6dd88-109">Click New.</span></span>
3. <span data-ttu-id="6dd88-110">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="6dd88-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="6dd88-111">No campo Data de solicitação, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="6dd88-111">In the Requested date field, enter a date.</span></span>
5. <span data-ttu-id="6dd88-112">No campo Data contábil, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="6dd88-112">In the Accounting date field, enter a date.</span></span>
6. <span data-ttu-id="6dd88-113">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6dd88-113">Click OK.</span></span>
7. <span data-ttu-id="6dd88-114">No campo Motivo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="6dd88-114">In the Reason field, enter or select a value.</span></span>
8. <span data-ttu-id="6dd88-115">Clique em Adicionar linha.</span><span class="sxs-lookup"><span data-stu-id="6dd88-115">Click Add line.</span></span>
9. <span data-ttu-id="6dd88-116">No campo da categoria da obtenção, selecione uma categoria na árvore, e clique então em OK.</span><span class="sxs-lookup"><span data-stu-id="6dd88-116">In the Procurement category field, select a category in the tree, and then click OK.</span></span>
10. <span data-ttu-id="6dd88-117">No campo Nome do produto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="6dd88-117">In the Product name field, type a value.</span></span>
11. <span data-ttu-id="6dd88-118">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="6dd88-118">In the Quantity field, enter a number.</span></span>
12. <span data-ttu-id="6dd88-119">No campo Unidade, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="6dd88-119">In the Unit field, enter or select a value.</span></span>
13. <span data-ttu-id="6dd88-120">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="6dd88-120">Click Save.</span></span>
14. <span data-ttu-id="6dd88-121">Clique em Fluxo de trabalho para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="6dd88-121">Click Workflow to open the drop dialog.</span></span>
15. <span data-ttu-id="6dd88-122">Clique em Enviar.</span><span class="sxs-lookup"><span data-stu-id="6dd88-122">Click Submit.</span></span>
16. <span data-ttu-id="6dd88-123">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="6dd88-123">Close the page.</span></span>
17. <span data-ttu-id="6dd88-124">Clique em Enviar.</span><span class="sxs-lookup"><span data-stu-id="6dd88-124">Click Submit.</span></span>

## <a name="reassign-a-workflow-task"></a><span data-ttu-id="6dd88-125">Reatribuir uma tarefa de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="6dd88-125">Reassign a workflow task</span></span>
    * <span data-ttu-id="6dd88-126">A tarefa seguinte é criar um RFQ para obter ofertas dos vendedores para o produto.</span><span class="sxs-lookup"><span data-stu-id="6dd88-126">The next task is to create an RFQ to get bids from vendors for the product.</span></span> <span data-ttu-id="6dd88-127">Em dados do programa demonstrativo de USMF, os trabalhos da requisição estabelecem-se com uma regra de modo que se um vendedor não está selecionado, ou o preço unitário é 0 para uma linha, uma tarefa será atribuída a um trabalhador específico para criar um RFQ.</span><span class="sxs-lookup"><span data-stu-id="6dd88-127">In USMF demo data, the requisition workflow is set up with a rule so that if a vendor is not selected, or the unit price is 0 for a line, a task is assigned to a specific worker to create an RFQ.</span></span> <span data-ttu-id="6dd88-128">Para continuar com este guia, você precisa atribuir novamente essa tarefa a um outro usuário (você mesmo).</span><span class="sxs-lookup"><span data-stu-id="6dd88-128">To continue with this guide, you need to re-assign that task to another user (yourself).</span></span> <span data-ttu-id="6dd88-129">Você pode somente fazer isso se você entrou como um Admin.</span><span class="sxs-lookup"><span data-stu-id="6dd88-129">You can only do this if you are logged in as an Admin.</span></span>  
1. <span data-ttu-id="6dd88-130">Clique em Fluxo de trabalho para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="6dd88-130">Click Workflow to open the drop dialog.</span></span>
2. <span data-ttu-id="6dd88-131">Clique em Exibir histórico.</span><span class="sxs-lookup"><span data-stu-id="6dd88-131">Click View history.</span></span>
3. <span data-ttu-id="6dd88-132">Atualize a página.</span><span class="sxs-lookup"><span data-stu-id="6dd88-132">Refresh the page.</span></span>
4. <span data-ttu-id="6dd88-133">Expanda a seção Rastrear detalhes.</span><span class="sxs-lookup"><span data-stu-id="6dd88-133">Expand the Tracking details section.</span></span>
5. <span data-ttu-id="6dd88-134">Na árvore, selecione 'a linha em que começa com "Linha de fluxo de trabalho ativados em"'.</span><span class="sxs-lookup"><span data-stu-id="6dd88-134">In the tree, select 'the line that starts with “Line workflow activated on”'.</span></span>
6. <span data-ttu-id="6dd88-135">Clique em Exibir detalhes do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="6dd88-135">Click View workflow details.</span></span>
7. <span data-ttu-id="6dd88-136">Expanda a seção Itens de trabalho.</span><span class="sxs-lookup"><span data-stu-id="6dd88-136">Expand the Work items section.</span></span>
8. <span data-ttu-id="6dd88-137">Clique em Reatribuir.</span><span class="sxs-lookup"><span data-stu-id="6dd88-137">Click Reassign.</span></span>
9. <span data-ttu-id="6dd88-138">No campo Usuário, selecione Admin.</span><span class="sxs-lookup"><span data-stu-id="6dd88-138">In the User field, select Admin.</span></span>
10. <span data-ttu-id="6dd88-139">Clique em Reatribuir.</span><span class="sxs-lookup"><span data-stu-id="6dd88-139">Click Reassign.</span></span>
11. <span data-ttu-id="6dd88-140">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="6dd88-140">Close the page.</span></span>
12. <span data-ttu-id="6dd88-141">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="6dd88-141">Close the page.</span></span>

## <a name="create-an-rfq"></a><span data-ttu-id="6dd88-142">Criar um RFQ</span><span class="sxs-lookup"><span data-stu-id="6dd88-142">Create an RFQ</span></span>
1. <span data-ttu-id="6dd88-143">Atualize a página.</span><span class="sxs-lookup"><span data-stu-id="6dd88-143">Refresh the page.</span></span>
2. <span data-ttu-id="6dd88-144">Clique em Solicitação de cotação.</span><span class="sxs-lookup"><span data-stu-id="6dd88-144">Click Request for quotation.</span></span>
3. <span data-ttu-id="6dd88-145">No campo Comprar entidade legal, selecione USMF.</span><span class="sxs-lookup"><span data-stu-id="6dd88-145">In the Buying legal entity field, select USMF.</span></span>
    * <span data-ttu-id="6dd88-146">Você deve selecionar a mesma entidade legal que está na linha da requisição.</span><span class="sxs-lookup"><span data-stu-id="6dd88-146">You must select the same legal entity that’s on the requisition line.</span></span>  
4. <span data-ttu-id="6dd88-147">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="6dd88-147">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="6dd88-148">Se você tiver múltiplas linhas em sua requisição de compra, selecione todas as linhas que você quer adicionar ao RFQ.</span><span class="sxs-lookup"><span data-stu-id="6dd88-148">If you had multiple lines on your purchase requisition, select all the lines that you want to add to the RFQ.</span></span>  
5. <span data-ttu-id="6dd88-149">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6dd88-149">Click OK.</span></span>
6. <span data-ttu-id="6dd88-150">Atualize a página.</span><span class="sxs-lookup"><span data-stu-id="6dd88-150">Refresh the page.</span></span>
7. <span data-ttu-id="6dd88-151">Abra o Quadro de Fatos e expanda então a seção Relacionada dos documentos.</span><span class="sxs-lookup"><span data-stu-id="6dd88-151">Open the FactBox and then expand the Related documents section.</span></span>
    * <span data-ttu-id="6dd88-152">Você pode já ter aberto o Quadro de Fatos.</span><span class="sxs-lookup"><span data-stu-id="6dd88-152">You may already have the FactBox open.</span></span> <span data-ttu-id="6dd88-153">Procure o ícone com uma seta nela, à direita dos botões de alavanca das linhas/cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="6dd88-153">Look for the icon with an arrow on it, to the right of the Lines/Header toggle buttons.</span></span> <span data-ttu-id="6dd88-154">Se a seta está apontando à direita, o Quadro de Fatos já está aberto.</span><span class="sxs-lookup"><span data-stu-id="6dd88-154">If the arrow is pointing to the right, the FactBox is already open.</span></span> <span data-ttu-id="6dd88-155">Se a seta aponta à esquerda, clique-a para abrir o Quadro de Fatos.</span><span class="sxs-lookup"><span data-stu-id="6dd88-155">If the arrow points to the left, click it to open the FactBox.</span></span>  
8. <span data-ttu-id="6dd88-156">Clique no link no campo Solicitação de cotação para abrir o RFQ que acabou de ser criado.</span><span class="sxs-lookup"><span data-stu-id="6dd88-156">Click the link in the Request for quotation field to open the RFQ that was just created.</span></span>
9. <span data-ttu-id="6dd88-157">Clique em Cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="6dd88-157">Click Header.</span></span>
10. <span data-ttu-id="6dd88-158">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="6dd88-158">Click Add.</span></span>
11. <span data-ttu-id="6dd88-159">No campo Conta de fornecedor, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="6dd88-159">In the Vendor account field, enter or select a value.</span></span>
12. <span data-ttu-id="6dd88-160">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="6dd88-160">Click Add.</span></span>
13. <span data-ttu-id="6dd88-161">No campo Conta de fornecedor, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="6dd88-161">In the Vendor account field, enter or select a value.</span></span>
14. <span data-ttu-id="6dd88-162">Clique em Enviar.</span><span class="sxs-lookup"><span data-stu-id="6dd88-162">Click Send.</span></span>
15. <span data-ttu-id="6dd88-163">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6dd88-163">Click OK.</span></span>
16. <span data-ttu-id="6dd88-164">Clique em Digitar Resposta.</span><span class="sxs-lookup"><span data-stu-id="6dd88-164">Click Enter reply.</span></span>
17. <span data-ttu-id="6dd88-165">No Painel de Ação, clique em Resposta.</span><span class="sxs-lookup"><span data-stu-id="6dd88-165">On the Action Pane, click Reply.</span></span>
18. <span data-ttu-id="6dd88-166">Clique em Copiar dados para resposta.</span><span class="sxs-lookup"><span data-stu-id="6dd88-166">Click Copy data to reply.</span></span>
    * <span data-ttu-id="6dd88-167">Isto copia dados, tais como a quantidade e as datas, do RFQ à resposta.</span><span class="sxs-lookup"><span data-stu-id="6dd88-167">This copies data, such as the quantity and dates, from the RFQ to the reply .</span></span>  
19. <span data-ttu-id="6dd88-168">No campo Preço unitário, insira um número.</span><span class="sxs-lookup"><span data-stu-id="6dd88-168">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="6dd88-169">Este é o preço que você recebeu do vendedor.</span><span class="sxs-lookup"><span data-stu-id="6dd88-169">This is the price that you’ve received from the vendor.</span></span> <span data-ttu-id="6dd88-170">Você pode querer também inserir informações adicionais do vendedor.</span><span class="sxs-lookup"><span data-stu-id="6dd88-170">You might also want to enter additional information from the vendor.</span></span>  
20. <span data-ttu-id="6dd88-171">Clique em Aceitar.</span><span class="sxs-lookup"><span data-stu-id="6dd88-171">Click Accept.</span></span>
21. <span data-ttu-id="6dd88-172">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6dd88-172">Click OK.</span></span>

## <a name="verify-that-vendor-and-price-have-been-transferred-to-the-requisition"></a><span data-ttu-id="6dd88-173">Verifique se o fornecedor e o preço foram transferidos para a requisição</span><span class="sxs-lookup"><span data-stu-id="6dd88-173">Verify that vendor and price have been transferred to the requisition</span></span>
1. <span data-ttu-id="6dd88-174">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="6dd88-174">Close the page.</span></span>
2. <span data-ttu-id="6dd88-175">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="6dd88-175">Click Lines.</span></span>
3. <span data-ttu-id="6dd88-176">Clique em Informações Relacionadas.</span><span class="sxs-lookup"><span data-stu-id="6dd88-176">Click Related information.</span></span>
4. <span data-ttu-id="6dd88-177">Clique em Linhas de requisição de compra.</span><span class="sxs-lookup"><span data-stu-id="6dd88-177">Click Purchase requisition.</span></span>
5. <span data-ttu-id="6dd88-178">Selecione a linha que foi transferida ao RFQ.</span><span class="sxs-lookup"><span data-stu-id="6dd88-178">Select the line that was transferred to the RFQ.</span></span>
    * <span data-ttu-id="6dd88-179">Verifique se o preço e o vendedor estão copiados à requisição.</span><span class="sxs-lookup"><span data-stu-id="6dd88-179">Verify that the price and vendor have been copied to the requisition.</span></span>  
6. <span data-ttu-id="6dd88-180">Clique em Fluxo de trabalho para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="6dd88-180">Click Workflow to open the drop dialog.</span></span>
7. <span data-ttu-id="6dd88-181">Clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="6dd88-181">Click Complete.</span></span>
8. <span data-ttu-id="6dd88-182">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="6dd88-182">Close the page.</span></span>
9. <span data-ttu-id="6dd88-183">Clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="6dd88-183">Click Complete.</span></span>



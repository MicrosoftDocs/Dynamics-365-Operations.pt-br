---
title: Criar uma requisição que use um RFQ
description: Este guia mostra como adicionar o preço e a informação do vendedor a uma requisição da compra de um processo do RFQ.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchReqTableListPage, PurchReqCreate, PurchReqTable, PurchReqLineRelatedDocuments, EcoResCategorySingleLookup, PurchReqWorkflowDropDialog, WorkflowSubmitDialog, WorkflowStatus, WorkflowWorkItemActionDialog, WorkflowUserListLookup, PurchReqCopyRFQ, SysDataAreaSelectLookup, PurchRFQCaseTable, PurchRFQEditLines, PurchRFQReplyTable, UnitOfMeasureLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8a9418b526f992008086f10ce78e95cb682bc164
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "344975"
---
# <a name="create-a-requisition-that-uses-an-rfq"></a><span data-ttu-id="d2832-103">Criar uma requisição que use um RFQ</span><span class="sxs-lookup"><span data-stu-id="d2832-103">Create a requisition that uses an RFQ</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d2832-104">Este guia mostra como adicionar o preço e a informação do vendedor a uma requisição da compra de um processo do RFQ.</span><span class="sxs-lookup"><span data-stu-id="d2832-104">This guide shows how to add price and vendor information to a purchase requisition from an RFQ process.</span></span> <span data-ttu-id="d2832-105">O exemplo mostrado neste guia pode ser usado na empresa dos dados do programa demonstrativo de USMF, e você entrar como um Admin para terminar todas as etapas.</span><span class="sxs-lookup"><span data-stu-id="d2832-105">The example shown in this guide can be used in the USMF demo data company, and you must be logged in as an Admin to complete all the steps.</span></span> <span data-ttu-id="d2832-106">As tarefas neste guia seriam feitas tipicamente por profissionais da obtenção.</span><span class="sxs-lookup"><span data-stu-id="d2832-106">The tasks in this guide would typically be done by procurement professionals.</span></span>


## <a name="create-a-requisition"></a><span data-ttu-id="d2832-107">Criar um requisito</span><span class="sxs-lookup"><span data-stu-id="d2832-107">Create a requisition</span></span>
1. <span data-ttu-id="d2832-108">Vá para Aquisição e fornecimento > Requisições de compra > Requisições de compra preparadas por mim.</span><span class="sxs-lookup"><span data-stu-id="d2832-108">Go to Procurement and sourcing > Purchase requisitions > Purchase requisitions prepared by me.</span></span>
2. <span data-ttu-id="d2832-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="d2832-109">Click New.</span></span>
3. <span data-ttu-id="d2832-110">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="d2832-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="d2832-111">No campo Data de solicitação, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="d2832-111">In the Requested date field, enter a date.</span></span>
5. <span data-ttu-id="d2832-112">No campo Data contábil, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="d2832-112">In the Accounting date field, enter a date.</span></span>
6. <span data-ttu-id="d2832-113">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="d2832-113">Click OK.</span></span>
7. <span data-ttu-id="d2832-114">No campo Motivo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d2832-114">In the Reason field, enter or select a value.</span></span>
8. <span data-ttu-id="d2832-115">Clique em Adicionar linha.</span><span class="sxs-lookup"><span data-stu-id="d2832-115">Click Add line.</span></span>
9. <span data-ttu-id="d2832-116">No campo da categoria da obtenção, selecione uma categoria na árvore, e clique então em OK.</span><span class="sxs-lookup"><span data-stu-id="d2832-116">In the Procurement category field, select a category in the tree, and then click OK.</span></span>
10. <span data-ttu-id="d2832-117">No campo Nome do produto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="d2832-117">In the Product name field, type a value.</span></span>
11. <span data-ttu-id="d2832-118">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="d2832-118">In the Quantity field, enter a number.</span></span>
12. <span data-ttu-id="d2832-119">No campo Unidade, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d2832-119">In the Unit field, enter or select a value.</span></span>
13. <span data-ttu-id="d2832-120">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="d2832-120">Click Save.</span></span>
14. <span data-ttu-id="d2832-121">Clique em Fluxo de trabalho para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="d2832-121">Click Workflow to open the drop dialog.</span></span>
15. <span data-ttu-id="d2832-122">Clique em Enviar.</span><span class="sxs-lookup"><span data-stu-id="d2832-122">Click Submit.</span></span>
16. <span data-ttu-id="d2832-123">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d2832-123">Close the page.</span></span>
17. <span data-ttu-id="d2832-124">Clique em Enviar.</span><span class="sxs-lookup"><span data-stu-id="d2832-124">Click Submit.</span></span>

## <a name="reassign-a-workflow-task"></a><span data-ttu-id="d2832-125">Reatribuir uma tarefa de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="d2832-125">Reassign a workflow task</span></span>
    * <span data-ttu-id="d2832-126">A tarefa seguinte é criar um RFQ para obter ofertas dos vendedores para o produto.</span><span class="sxs-lookup"><span data-stu-id="d2832-126">The next task is to create an RFQ to get bids from vendors for the product.</span></span> <span data-ttu-id="d2832-127">Em dados do programa demonstrativo de USMF, os trabalhos da requisição estabelecem-se com uma regra de modo que se um vendedor não está selecionado, ou o preço unitário é 0 para uma linha, uma tarefa será atribuída a um trabalhador específico para criar um RFQ.</span><span class="sxs-lookup"><span data-stu-id="d2832-127">In USMF demo data, the requisition workflow is set up with a rule so that if a vendor is not selected, or the unit price is 0 for a line, a task is assigned to a specific worker to create an RFQ.</span></span> <span data-ttu-id="d2832-128">Para continuar com este guia, você precisa atribuir novamente essa tarefa a um outro usuário (você mesmo).</span><span class="sxs-lookup"><span data-stu-id="d2832-128">To continue with this guide, you need to re-assign that task to another user (yourself).</span></span> <span data-ttu-id="d2832-129">Você pode somente fazer isso se você entrou como um Admin.</span><span class="sxs-lookup"><span data-stu-id="d2832-129">You can only do this if you are logged in as an Admin.</span></span>  
1. <span data-ttu-id="d2832-130">Clique em Fluxo de trabalho para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="d2832-130">Click Workflow to open the drop dialog.</span></span>
2. <span data-ttu-id="d2832-131">Clique em Exibir histórico.</span><span class="sxs-lookup"><span data-stu-id="d2832-131">Click View history.</span></span>
3. <span data-ttu-id="d2832-132">Atualize a página.</span><span class="sxs-lookup"><span data-stu-id="d2832-132">Refresh the page.</span></span>
4. <span data-ttu-id="d2832-133">Expanda a seção Rastrear detalhes.</span><span class="sxs-lookup"><span data-stu-id="d2832-133">Expand the Tracking details section.</span></span>
5. <span data-ttu-id="d2832-134">Na árvore, selecione 'a linha em que começa com "Linha de fluxo de trabalho ativados em"'.</span><span class="sxs-lookup"><span data-stu-id="d2832-134">In the tree, select 'the line that starts with “Line workflow activated on”'.</span></span>
6. <span data-ttu-id="d2832-135">Clique em Exibir detalhes do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d2832-135">Click View workflow details.</span></span>
7. <span data-ttu-id="d2832-136">Expanda a seção Itens de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d2832-136">Expand the Work items section.</span></span>
8. <span data-ttu-id="d2832-137">Clique em Reatribuir.</span><span class="sxs-lookup"><span data-stu-id="d2832-137">Click Reassign.</span></span>
9. <span data-ttu-id="d2832-138">No campo Usuário, selecione Admin.</span><span class="sxs-lookup"><span data-stu-id="d2832-138">In the User field, select Admin.</span></span>
10. <span data-ttu-id="d2832-139">Clique em Reatribuir.</span><span class="sxs-lookup"><span data-stu-id="d2832-139">Click Reassign.</span></span>
11. <span data-ttu-id="d2832-140">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d2832-140">Close the page.</span></span>
12. <span data-ttu-id="d2832-141">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d2832-141">Close the page.</span></span>

## <a name="create-an-rfq"></a><span data-ttu-id="d2832-142">Criar um RFQ</span><span class="sxs-lookup"><span data-stu-id="d2832-142">Create an RFQ</span></span>
1. <span data-ttu-id="d2832-143">Atualize a página.</span><span class="sxs-lookup"><span data-stu-id="d2832-143">Refresh the page.</span></span>
2. <span data-ttu-id="d2832-144">Clique em Solicitação de cotação.</span><span class="sxs-lookup"><span data-stu-id="d2832-144">Click Request for quotation.</span></span>
3. <span data-ttu-id="d2832-145">No campo Comprar entidade legal, selecione USMF.</span><span class="sxs-lookup"><span data-stu-id="d2832-145">In the Buying legal entity field, select USMF.</span></span>
    * <span data-ttu-id="d2832-146">Você deve selecionar a mesma entidade legal que está na linha da requisição.</span><span class="sxs-lookup"><span data-stu-id="d2832-146">You must select the same legal entity that’s on the requisition line.</span></span>  
4. <span data-ttu-id="d2832-147">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="d2832-147">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="d2832-148">Se você tiver múltiplas linhas em sua requisição de compra, selecione todas as linhas que você quer adicionar ao RFQ.</span><span class="sxs-lookup"><span data-stu-id="d2832-148">If you had multiple lines on your purchase requisition, select all the lines that you want to add to the RFQ.</span></span>  
5. <span data-ttu-id="d2832-149">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="d2832-149">Click OK.</span></span>
6. <span data-ttu-id="d2832-150">Atualize a página.</span><span class="sxs-lookup"><span data-stu-id="d2832-150">Refresh the page.</span></span>
7. <span data-ttu-id="d2832-151">Abra o Quadro de Fatos e expanda então a seção Relacionada dos documentos.</span><span class="sxs-lookup"><span data-stu-id="d2832-151">Open the FactBox and then expand the Related documents section.</span></span>
    * <span data-ttu-id="d2832-152">Você pode já ter aberto o Quadro de Fatos.</span><span class="sxs-lookup"><span data-stu-id="d2832-152">You may already have the FactBox open.</span></span> <span data-ttu-id="d2832-153">Procure o ícone com uma seta nela, à direita dos botões de alavanca das linhas/cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="d2832-153">Look for the icon with an arrow on it, to the right of the Lines/Header toggle buttons.</span></span> <span data-ttu-id="d2832-154">Se a seta está apontando à direita, o Quadro de Fatos já está aberto.</span><span class="sxs-lookup"><span data-stu-id="d2832-154">If the arrow is pointing to the right, the FactBox is already open.</span></span> <span data-ttu-id="d2832-155">Se a seta aponta à esquerda, clique-a para abrir o Quadro de Fatos.</span><span class="sxs-lookup"><span data-stu-id="d2832-155">If the arrow points to the left, click it to open the FactBox.</span></span>  
8. <span data-ttu-id="d2832-156">Clique no link no campo Solicitação de cotação para abrir o RFQ que acabou de ser criado.</span><span class="sxs-lookup"><span data-stu-id="d2832-156">Click the link in the Request for quotation field to open the RFQ that was just created.</span></span>
9. <span data-ttu-id="d2832-157">Clique em Cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="d2832-157">Click Header.</span></span>
10. <span data-ttu-id="d2832-158">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="d2832-158">Click Add.</span></span>
11. <span data-ttu-id="d2832-159">No campo Conta de fornecedor, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d2832-159">In the Vendor account field, enter or select a value.</span></span>
12. <span data-ttu-id="d2832-160">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="d2832-160">Click Add.</span></span>
13. <span data-ttu-id="d2832-161">No campo Conta de fornecedor, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d2832-161">In the Vendor account field, enter or select a value.</span></span>
14. <span data-ttu-id="d2832-162">Clique em Enviar.</span><span class="sxs-lookup"><span data-stu-id="d2832-162">Click Send.</span></span>
15. <span data-ttu-id="d2832-163">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="d2832-163">Click OK.</span></span>
16. <span data-ttu-id="d2832-164">Clique em Digitar Resposta.</span><span class="sxs-lookup"><span data-stu-id="d2832-164">Click Enter reply.</span></span>
17. <span data-ttu-id="d2832-165">No Painel de Ação, clique em Resposta.</span><span class="sxs-lookup"><span data-stu-id="d2832-165">On the Action Pane, click Reply.</span></span>
18. <span data-ttu-id="d2832-166">Clique em Copiar dados para resposta.</span><span class="sxs-lookup"><span data-stu-id="d2832-166">Click Copy data to reply.</span></span>
    * <span data-ttu-id="d2832-167">Isto copia dados, tais como a quantidade e as datas, do RFQ à resposta.</span><span class="sxs-lookup"><span data-stu-id="d2832-167">This copies data, such as the quantity and dates, from the RFQ to the reply .</span></span>  
19. <span data-ttu-id="d2832-168">No campo Preço unitário, insira um número.</span><span class="sxs-lookup"><span data-stu-id="d2832-168">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="d2832-169">Este é o preço que você recebeu do vendedor.</span><span class="sxs-lookup"><span data-stu-id="d2832-169">This is the price that you’ve received from the vendor.</span></span> <span data-ttu-id="d2832-170">Você pode querer também inserir informações adicionais do vendedor.</span><span class="sxs-lookup"><span data-stu-id="d2832-170">You might also want to enter additional information from the vendor.</span></span>  
20. <span data-ttu-id="d2832-171">Clique em Aceitar.</span><span class="sxs-lookup"><span data-stu-id="d2832-171">Click Accept.</span></span>
21. <span data-ttu-id="d2832-172">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="d2832-172">Click OK.</span></span>

## <a name="verify-that-vendor-and-price-have-been-transferred-to-the-requisition"></a><span data-ttu-id="d2832-173">Verifique se o fornecedor e o preço foram transferidos para a requisição</span><span class="sxs-lookup"><span data-stu-id="d2832-173">Verify that vendor and price have been transferred to the requisition</span></span>
1. <span data-ttu-id="d2832-174">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d2832-174">Close the page.</span></span>
2. <span data-ttu-id="d2832-175">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="d2832-175">Click Lines.</span></span>
3. <span data-ttu-id="d2832-176">Clique em Informações Relacionadas.</span><span class="sxs-lookup"><span data-stu-id="d2832-176">Click Related information.</span></span>
4. <span data-ttu-id="d2832-177">Clique em Linhas de requisição de compra.</span><span class="sxs-lookup"><span data-stu-id="d2832-177">Click Purchase requisition.</span></span>
5. <span data-ttu-id="d2832-178">Selecione a linha que foi transferida ao RFQ.</span><span class="sxs-lookup"><span data-stu-id="d2832-178">Select the line that was transferred to the RFQ.</span></span>
    * <span data-ttu-id="d2832-179">Verifique se o preço e o vendedor estão copiados à requisição.</span><span class="sxs-lookup"><span data-stu-id="d2832-179">Verify that the price and vendor have been copied to the requisition.</span></span>  
6. <span data-ttu-id="d2832-180">Clique em Fluxo de trabalho para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="d2832-180">Click Workflow to open the drop dialog.</span></span>
7. <span data-ttu-id="d2832-181">Clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="d2832-181">Click Complete.</span></span>
8. <span data-ttu-id="d2832-182">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d2832-182">Close the page.</span></span>
9. <span data-ttu-id="d2832-183">Clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="d2832-183">Click Complete.</span></span>


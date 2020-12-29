---
title: Criar uma requisição que use um RFQ
description: Este tópico explica como adicionar o preço e a informação do vendedor a uma requisição da compra de um processo do RFQ.
author: mkirknel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchReqTableListPage, PurchReqCreate, PurchReqTable, PurchReqLineRelatedDocuments, EcoResCategorySingleLookup, PurchReqWorkflowDropDialog, WorkflowSubmitDialog, WorkflowStatus, WorkflowWorkItemActionDialog, WorkflowUserListLookup, PurchReqCopyRFQ, SysDataAreaSelectLookup, PurchRFQCaseTable, PurchRFQEditLines, PurchRFQReplyTable, UnitOfMeasureLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 205cba2325e76dae9572301e44e0e89cbcfd106e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422052"
---
# <a name="create-a-requisition-that-uses-an-rfq"></a><span data-ttu-id="d2439-103">Criar uma requisição que use um RFQ</span><span class="sxs-lookup"><span data-stu-id="d2439-103">Create a requisition that uses an RFQ</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d2439-104">Este tópico explica como adicionar o preço e a informação do vendedor a uma requisição da compra de um processo do RFQ.</span><span class="sxs-lookup"><span data-stu-id="d2439-104">This topic explains how to add price and vendor information to a purchase requisition from an RFQ process.</span></span> <span data-ttu-id="d2439-105">O exemplo mostrado neste guia pode ser usado na empresa dos dados do programa demonstrativo de USMF, e você entrar como um Admin para terminar todas as etapas.</span><span class="sxs-lookup"><span data-stu-id="d2439-105">The example shown in this guide can be used in the USMF demo data company, and you must be logged in as an Admin to complete all the steps.</span></span> <span data-ttu-id="d2439-106">As tarefas neste guia seriam feitas tipicamente por profissionais da obtenção.</span><span class="sxs-lookup"><span data-stu-id="d2439-106">The tasks in this guide would typically be done by procurement professionals.</span></span>


## <a name="create-a-requisition"></a><span data-ttu-id="d2439-107">Criar um requisito</span><span class="sxs-lookup"><span data-stu-id="d2439-107">Create a requisition</span></span>
1. <span data-ttu-id="d2439-108">No Painel de Navegação, vá para **Módulos > Aquisição e fornecimento > Requisições de compra > Requisições de compra preparadas por mim**.</span><span class="sxs-lookup"><span data-stu-id="d2439-108">In the navigation pane, go to **Modules > Procurement and sourcing > Purchase requisitions > Purchase requisitions prepared by me**.</span></span>
2. <span data-ttu-id="d2439-109">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="d2439-109">Select **New**.</span></span>
3. <span data-ttu-id="d2439-110">No campo **Nome**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="d2439-110">In the **Name** field, type a value.</span></span>
4. <span data-ttu-id="d2439-111">No campo **Data solicitada**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="d2439-111">In the **Requested date** field, enter a date.</span></span>
5. <span data-ttu-id="d2439-112">No campo **Data contábil**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="d2439-112">In the **Accounting date** field, enter a date.</span></span>
6. <span data-ttu-id="d2439-113">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="d2439-113">Select **OK**.</span></span>
7. <span data-ttu-id="d2439-114">No campo **Motivo**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d2439-114">In the **Reason** field, enter or select a value.</span></span>
8. <span data-ttu-id="d2439-115">Selecione **Adicionar linha**.</span><span class="sxs-lookup"><span data-stu-id="d2439-115">Select **Add line**.</span></span>
9. <span data-ttu-id="d2439-116">No campo **Categoria de compras**, selecione uma categoria na árvore e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="d2439-116">In the **Procurement category** field, select a category in the tree, and then select **OK**.</span></span>
10. <span data-ttu-id="d2439-117">No campo **Nome do produto**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="d2439-117">In the **Product name** field, type a value.</span></span>
11. <span data-ttu-id="d2439-118">No campo **Quantidade.**, insira um número</span><span class="sxs-lookup"><span data-stu-id="d2439-118">In the **Quantity** field, enter a number.</span></span>
12. <span data-ttu-id="d2439-119">No campo **Unidade**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d2439-119">In the **Unit** field, enter or select a value.</span></span>
13. <span data-ttu-id="d2439-120">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d2439-120">Select **Save**.</span></span>
14. <span data-ttu-id="d2439-121">Selecione **Fluxo de trabalho** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="d2439-121">Select **Workflow** to open the drop dialog.</span></span>
15. <span data-ttu-id="d2439-122">Selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="d2439-122">Select **Submit**.</span></span>
16. <span data-ttu-id="d2439-123">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d2439-123">Close the page.</span></span>
17. <span data-ttu-id="d2439-124">Selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="d2439-124">Select **Submit**.</span></span>

## <a name="reassign-a-workflow-task"></a><span data-ttu-id="d2439-125">Reatribuir uma tarefa de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="d2439-125">Reassign a workflow task</span></span>
<span data-ttu-id="d2439-126">A tarefa seguinte é criar um RFQ para obter ofertas dos vendedores para o produto.</span><span class="sxs-lookup"><span data-stu-id="d2439-126">The next task is to create an RFQ to get bids from vendors for the product.</span></span> <span data-ttu-id="d2439-127">Em dados do programa demonstrativo de USMF, os trabalhos da requisição estabelecem-se com uma regra de modo que se um vendedor não está selecionado, ou o preço unitário é 0 para uma linha, uma tarefa será atribuída a um trabalhador específico para criar um RFQ.</span><span class="sxs-lookup"><span data-stu-id="d2439-127">In USMF demo data, the requisition workflow is set up with a rule so that if a vendor is not selected, or the unit price is 0 for a line, a task is assigned to a specific worker to create an RFQ.</span></span> <span data-ttu-id="d2439-128">Para continuar com este guia, você precisa atribuir novamente essa tarefa a um outro usuário (você mesmo).</span><span class="sxs-lookup"><span data-stu-id="d2439-128">To continue with this guide, you need to re-assign that task to another user (yourself).</span></span> <span data-ttu-id="d2439-129">Você pode somente fazer isso se você entrou como um Admin.</span><span class="sxs-lookup"><span data-stu-id="d2439-129">You can only do this if you are logged in as an Admin.</span></span>  

1. <span data-ttu-id="d2439-130">Selecione **Fluxo de trabalho** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="d2439-130">Select **Workflow** to open the drop dialog.</span></span>
2. <span data-ttu-id="d2439-131">Selecione **Exibir histórico**.</span><span class="sxs-lookup"><span data-stu-id="d2439-131">Select **View history**.</span></span>
3. <span data-ttu-id="d2439-132">Atualize a página.</span><span class="sxs-lookup"><span data-stu-id="d2439-132">Refresh the page.</span></span>
4. <span data-ttu-id="d2439-133">Expanda a seção **Rastrear detalhes**.</span><span class="sxs-lookup"><span data-stu-id="d2439-133">Expand the **Tracking details** section.</span></span>
5. <span data-ttu-id="d2439-134">Na árvore, selecione "a linha em que começa com "Linha de fluxo de trabalho ativados em".</span><span class="sxs-lookup"><span data-stu-id="d2439-134">In the tree, select the line that starts with "Line workflow activated on".</span></span>
6. <span data-ttu-id="d2439-135">Selecione **Exibir detalhes do fluxo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="d2439-135">Select **View workflow details**.</span></span>
7. <span data-ttu-id="d2439-136">Expanda a seção **Itens de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="d2439-136">Expand the **Work items** section.</span></span>
8. <span data-ttu-id="d2439-137">Selecione **Reatribuir**.</span><span class="sxs-lookup"><span data-stu-id="d2439-137">Select **Reassign**.</span></span>
9. <span data-ttu-id="d2439-138">No campo **Usuário**, selecione **Admin**.</span><span class="sxs-lookup"><span data-stu-id="d2439-138">In the **User** field, select **Admin**.</span></span>
10. <span data-ttu-id="d2439-139">Selecione **Reatribuir**.</span><span class="sxs-lookup"><span data-stu-id="d2439-139">Select **Reassign**.</span></span>
11. <span data-ttu-id="d2439-140">Feche as duas páginas.</span><span class="sxs-lookup"><span data-stu-id="d2439-140">Close the two pages.</span></span>

## <a name="create-an-rfq"></a><span data-ttu-id="d2439-141">Criar um RFQ</span><span class="sxs-lookup"><span data-stu-id="d2439-141">Create an RFQ</span></span>

1. <span data-ttu-id="d2439-142">Atualize a página.</span><span class="sxs-lookup"><span data-stu-id="d2439-142">Refresh the page.</span></span>
2. <span data-ttu-id="d2439-143">Selecione **Solicitação de cotação**.</span><span class="sxs-lookup"><span data-stu-id="d2439-143">Select **Request for quotation**.</span></span>
3. <span data-ttu-id="d2439-144">No campo **Comprar entidade legal**, selecione **USMF**.</span><span class="sxs-lookup"><span data-stu-id="d2439-144">In the **Buying legal entity** field, select **USMF**.</span></span> <span data-ttu-id="d2439-145">Você deve selecionar a mesma entidade legal que está na linha da requisição.</span><span class="sxs-lookup"><span data-stu-id="d2439-145">You must select the same legal entity that's on the requisition line.</span></span>  
4. <span data-ttu-id="d2439-146">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="d2439-146">In the list, mark the selected row.</span></span> <span data-ttu-id="d2439-147">Se você tiver múltiplas linhas em sua requisição de compra, selecione todas as linhas que você quer adicionar ao RFQ.</span><span class="sxs-lookup"><span data-stu-id="d2439-147">If you had multiple lines on your purchase requisition, select all the lines that you want to add to the RFQ.</span></span>  
5. <span data-ttu-id="d2439-148">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="d2439-148">Select **OK**.</span></span>
6. <span data-ttu-id="d2439-149">Atualize a página.</span><span class="sxs-lookup"><span data-stu-id="d2439-149">Refresh the page.</span></span>
7. <span data-ttu-id="d2439-150">Verifique se o FactBox está aberto e expanda a seção **Documentos relacionados**.</span><span class="sxs-lookup"><span data-stu-id="d2439-150">Ensure that the FactBox is open, then expand the **Related documents** section.</span></span>
8. <span data-ttu-id="d2439-151">Selecione o link no campo **Solicitação de cotação** para abrir o RFQ que acabou de ser criado.</span><span class="sxs-lookup"><span data-stu-id="d2439-151">Select the link in the **Request for quotation** field to open the RFQ that was just created.</span></span>
9. <span data-ttu-id="d2439-152">Selecione **Cabeçalho**.</span><span class="sxs-lookup"><span data-stu-id="d2439-152">Select **Header**.</span></span>
10. <span data-ttu-id="d2439-153">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="d2439-153">Select **Add**.</span></span>
11. <span data-ttu-id="d2439-154">No campo **Conta de fornecedor**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d2439-154">In the **Vendor account** field, enter or select a value.</span></span>
12. <span data-ttu-id="d2439-155">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="d2439-155">Select **Add**.</span></span>
13. <span data-ttu-id="d2439-156">No campo **Conta de fornecedor**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d2439-156">In the **Vendor account** field, enter or select a value.</span></span>
14. <span data-ttu-id="d2439-157">Selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="d2439-157">Select **Send**.</span></span>
15. <span data-ttu-id="d2439-158">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="d2439-158">Select **OK**.</span></span>
16. <span data-ttu-id="d2439-159">Selecione **Digitar Resposta**.</span><span class="sxs-lookup"><span data-stu-id="d2439-159">Select **Enter reply**.</span></span>
17. <span data-ttu-id="d2439-160">No Painel de Ação, selecione **Responder**.</span><span class="sxs-lookup"><span data-stu-id="d2439-160">On the Action Pane, select **Reply**.</span></span>
18. <span data-ttu-id="d2439-161">Selecione **Copiar Dados para Resposta**.</span><span class="sxs-lookup"><span data-stu-id="d2439-161">Select **Copy data to reply**.</span></span> <span data-ttu-id="d2439-162">Isto copia dados, tais como a quantidade e as datas, do RFQ à resposta.</span><span class="sxs-lookup"><span data-stu-id="d2439-162">This copies data, such as the quantity and dates, from the RFQ to the reply.</span></span>  
19. <span data-ttu-id="d2439-163">No campo **Preço unitário**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="d2439-163">In the **Unit price** field, enter a number.</span></span> <span data-ttu-id="d2439-164">Este é o preço que você recebeu do vendedor.</span><span class="sxs-lookup"><span data-stu-id="d2439-164">This is the price that you've received from the vendor.</span></span> <span data-ttu-id="d2439-165">Você pode querer também inserir informações adicionais do vendedor.</span><span class="sxs-lookup"><span data-stu-id="d2439-165">You might also want to enter additional information from the vendor.</span></span>  
20. <span data-ttu-id="d2439-166">Selecione **Aceitar**.</span><span class="sxs-lookup"><span data-stu-id="d2439-166">Select **Accept**.</span></span>
21. <span data-ttu-id="d2439-167">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="d2439-167">Select **OK**.</span></span>

## <a name="verify-that-vendor-and-price-have-been-transferred-to-the-requisition"></a><span data-ttu-id="d2439-168">Verifique se o fornecedor e o preço foram transferidos para a requisição</span><span class="sxs-lookup"><span data-stu-id="d2439-168">Verify that vendor and price have been transferred to the requisition</span></span>
1. <span data-ttu-id="d2439-169">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d2439-169">Close the page.</span></span>
2. <span data-ttu-id="d2439-170">Selecione **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="d2439-170">Select **Lines**.</span></span>
3. <span data-ttu-id="d2439-171">Selecione **Informações Relacionadas**.</span><span class="sxs-lookup"><span data-stu-id="d2439-171">Select **Related information**.</span></span>
4. <span data-ttu-id="d2439-172">Selecione **Requisição de Compra**.</span><span class="sxs-lookup"><span data-stu-id="d2439-172">Select **Purchase requisition**.</span></span>
5. <span data-ttu-id="d2439-173">Selecione a linha que foi transferida ao RFQ.</span><span class="sxs-lookup"><span data-stu-id="d2439-173">Select the line that was transferred to the RFQ.</span></span> <span data-ttu-id="d2439-174">Verifique se o preço e o vendedor estão copiados à requisição.</span><span class="sxs-lookup"><span data-stu-id="d2439-174">Verify that the price and vendor have been copied to the requisition.</span></span>  
6. <span data-ttu-id="d2439-175">Selecione **Fluxo de trabalho** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="d2439-175">Select **Workflow** to open the drop dialog.</span></span>
7. <span data-ttu-id="d2439-176">Selecione Concluído.</span><span class="sxs-lookup"><span data-stu-id="d2439-176">Select Complete.</span></span>
8. <span data-ttu-id="d2439-177">Selecione a página.</span><span class="sxs-lookup"><span data-stu-id="d2439-177">Select the page.</span></span>
9. <span data-ttu-id="d2439-178">Selecione Concluído.</span><span class="sxs-lookup"><span data-stu-id="d2439-178">Select Complete.</span></span>


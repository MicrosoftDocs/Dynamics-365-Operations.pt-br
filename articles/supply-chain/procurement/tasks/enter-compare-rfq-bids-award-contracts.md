--- 
title: "Inserir e comparar lances RFQ e contratos de prêmio"
description: "Este procedimento mostra como inserir respostas de uma solicitação de cotação, marcar e comparar ofertas, além de conceder a oferta a um dos fornecedores."
author: mkirknel
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: e2b07323fc7c66e2e551f3eabb8e4965b85e92f4
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2018

---
# <a name="enter-and-compare-rfq-bids-and-award-contracts"></a><span data-ttu-id="6bd8e-103">Inserir e comparar lances RFQ e contratos de prêmio</span><span class="sxs-lookup"><span data-stu-id="6bd8e-103">Enter and compare RFQ bids and award contracts</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6bd8e-104">Este procedimento mostra como inserir respostas de uma solicitação de cotação, marcar e comparar ofertas, além de conceder a oferta a um dos fornecedores.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-104">This procedure shows you how to enter replies to an RFQ, score and compare bids, and then award the bid to one of the vendors.</span></span> <span data-ttu-id="6bd8e-105">Você pode usar este procedimento na empresa USMF de dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-105">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="6bd8e-106">Antes de começar, você deve ter uma RFQ com duas linhas que foi enviado para pelo menos dois fornecedores.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-106">Before you start, you must have an RFQ with two lines that has been sent to at least two vendors.</span></span> <span data-ttu-id="6bd8e-107">Você pode executar o procedimento "Criar uma solicitação de cotação" como um pré-requisito para criar isso.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-107">You can run the "Create a request for quotation" procedure as a prerequisite to create this.</span></span> <span data-ttu-id="6bd8e-108">Você precisa ter configurado critérios de pontuação antes de executar este procedimento.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-108">You need to have set up scoring criteria before you can run this procedure.</span></span>


## <a name="enter-a-reply-from-a-vendor"></a><span data-ttu-id="6bd8e-109">Inserir uma resposta de um fornecedor</span><span class="sxs-lookup"><span data-stu-id="6bd8e-109">Enter a reply from a vendor</span></span>
1. <span data-ttu-id="6bd8e-110">Vá para Aquisição e fornecimento > Solicitações de cotações > Todas as solicitações de cotações.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-110">Go to Procurement and sourcing > Requests for quotations > All requests for quotations.</span></span>
2. <span data-ttu-id="6bd8e-111">Selecione uma solicitação de cotação com um status Enviado e clique no link no número do caso da Solicitação de cotação.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-111">Select an RFQ that has a status of Sent and click the link on the Request for quotation case number.</span></span>
    * <span data-ttu-id="6bd8e-112">A RFQ deve ser enviada para, pelo menos, 2 fornecedores.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-112">The RFQ should have been sent to at least 2 vendors.</span></span>  
3. <span data-ttu-id="6bd8e-113">Clique no cabeçalho para ir para a lista de fornecedores.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-113">Click Header to go to the list of vendors.</span></span>
4. <span data-ttu-id="6bd8e-114">Selecione o fornecedor para o qual você deseja inserir uma resposta no RFQ.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-114">Select the vendor for whom you want to enter a response on the RFQ.</span></span>
5. <span data-ttu-id="6bd8e-115">Clique em Digitar Resposta.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-115">Click Enter reply.</span></span>
6. <span data-ttu-id="6bd8e-116">No Painel de Ação, clique em Resposta.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-116">On the Action Pane, click Reply.</span></span>
7. <span data-ttu-id="6bd8e-117">Clique em Copiar dados para resposta.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-117">Click Copy data to reply.</span></span>
    * <span data-ttu-id="6bd8e-118">Esta ação copiará os dados selecionados, por exemplo, a quantidade de exemplos da solicitação de cotação para a resposta à solicitação de cotação.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-118">This action will copy selected data, for example, the quantity from the RFQ case to the RFQ reply.</span></span> <span data-ttu-id="6bd8e-119">Alternativamente você pode ignorar essa ação e preencher toda a resposta do campo manualmente ao editar a resposta.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-119">Alternatively you can skip this action and fill in all the response fields manually when you edit the reply.</span></span>  
8. <span data-ttu-id="6bd8e-120">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-120">Click Edit.</span></span>
9. <span data-ttu-id="6bd8e-121">No campo Preço unitário, insira um número.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-121">In the Unit price field, enter a number.</span></span>
10. <span data-ttu-id="6bd8e-122">Escolher a outra linha de cotação.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-122">Choose the other quotation line.</span></span>
11. <span data-ttu-id="6bd8e-123">No campo Preço unitário, insira um número.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-123">In the Unit price field, enter a number.</span></span>

## <a name="score-the-bid"></a><span data-ttu-id="6bd8e-124">Marcar a oferta</span><span class="sxs-lookup"><span data-stu-id="6bd8e-124">Score the bid</span></span>
1. <span data-ttu-id="6bd8e-125">Clique no cabeçalho para ir para a pontuação do lance.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-125">Click Header to go to the scoring of the bid.</span></span>
2. <span data-ttu-id="6bd8e-126">Expanda a seção de pontuação do lance.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-126">Expand the Bid scoring section.</span></span>
3. <span data-ttu-id="6bd8e-127">No campo Pontuação, insira um número para um dos critérios de marcação.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-127">In the Score field, enter a number for one of the scoring criteria.</span></span>
    * <span data-ttu-id="6bd8e-128">Se você passar o mouse em cima de um critério de pontuação, uma dica de ferramenta exibe a variação da pontuação que você precisa usar.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-128">If you hover over one of the scoring criteria a tooltip shows the range that you have to score within.</span></span> <span data-ttu-id="6bd8e-129">Nesta demonstração você pode adicionar um número entre 1 e 5 para qualquer um dos critérios.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-129">In this demo you can add a number between 1 and 5 to any of the criteria.</span></span>  
4. <span data-ttu-id="6bd8e-130">Selecione outro critério para marcação.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-130">Select another scoring criterion.</span></span>
5. <span data-ttu-id="6bd8e-131">No campo Pontuação, insira um número.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-131">In the Score field, enter a number.</span></span>
6. <span data-ttu-id="6bd8e-132">Expanda a seção de Questionários.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-132">Expand the Questionnaires section.</span></span>
    * <span data-ttu-id="6bd8e-133">Se os exemplos do caso RFQ apresentarem um questionário que foi enviado aos fornecedores, você pode inserir suas respostas na seção de questionário.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-133">If the RFQ case has a questionnaire that was sent to the vendors, you can enter their responses in the questionnaire section.</span></span>  
7. <span data-ttu-id="6bd8e-134">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-134">Close the page.</span></span>

## <a name="enter-a-reply-for-another-vendor"></a><span data-ttu-id="6bd8e-135">Insira uma resposta de outro fornecedor</span><span class="sxs-lookup"><span data-stu-id="6bd8e-135">Enter a reply for another vendor</span></span>
1. <span data-ttu-id="6bd8e-136">Selecione o fornecedor seguinte limpando o fornecedor que você contatou apenas na resposta para selecionar e na linha do fornecedor a seguir.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-136">Select the next vendor by clearing the vendor you have just entered the reply for and then selecting the row for the next vendor.</span></span>
2. <span data-ttu-id="6bd8e-137">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-137">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="6bd8e-138">Clique em Digitar Resposta.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-138">Click Enter reply.</span></span>
4. <span data-ttu-id="6bd8e-139">Clique em Copiar dados para resposta.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-139">Click Copy data to reply.</span></span>
5. <span data-ttu-id="6bd8e-140">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-140">Click Edit.</span></span>
6. <span data-ttu-id="6bd8e-141">No campo Preço unitário, insira um número.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-141">In the Unit price field, enter a number.</span></span>
7. <span data-ttu-id="6bd8e-142">Escolher a outra linha de cotação.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-142">Choose the other quotation line.</span></span>
8. <span data-ttu-id="6bd8e-143">No campo Preço unitário, insira um número.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-143">In the Unit price field, enter a number.</span></span>

## <a name="score-the-second-bid"></a><span data-ttu-id="6bd8e-144">Marcar a segunda oferta</span><span class="sxs-lookup"><span data-stu-id="6bd8e-144">Score the second bid</span></span>
1. <span data-ttu-id="6bd8e-145">Clique no cabeçalho para ir para a pontuação do lance.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-145">Click Header to go to scoring of the bid.</span></span>
2. <span data-ttu-id="6bd8e-146">No campo Pontuação, insira um número.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-146">In the Score field, enter a number.</span></span>
3. <span data-ttu-id="6bd8e-147">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-147">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="6bd8e-148">No campo Pontuação, insira um número.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-148">In the Score field, enter a number.</span></span>

## <a name="compare-the-replies"></a><span data-ttu-id="6bd8e-149">Comparar as respostas</span><span class="sxs-lookup"><span data-stu-id="6bd8e-149">Compare the replies</span></span>
1. <span data-ttu-id="6bd8e-150">No Painel de Ação, clique em Geral.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-150">On the Action Pane, click General.</span></span>
2. <span data-ttu-id="6bd8e-151">Clique em Comparar Respostas.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-151">Click Compare replies.</span></span>
3. <span data-ttu-id="6bd8e-152">No campo Pontuação, insira um número.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-152">In the Rank field, enter a number.</span></span>
    * <span data-ttu-id="6bd8e-153">Esta página mostra as ofertas com o cabeçalho e as linhas, e a pontuação total em nível de cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-153">This page shows the bids with the header and lines, and the total score on the header level.</span></span> <span data-ttu-id="6bd8e-154">Você pode comparar as linhas de classificação na grade de forma que as linhas comparáveis sejam próximas uma da outra.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-154">You can compare the lines by sorting in the grid so that comparable lines are next to each other.</span></span> <span data-ttu-id="6bd8e-155">As informações também incluem: Quantidade: a quantidade cotada pelo fornecedor.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-155">The information also includes:   Quantity: The quantity quoted by the vendor.</span></span> <span data-ttu-id="6bd8e-156">Isso pode não ser igual à quantidade especificada na RFQ.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-156">This might not equal the quantity specified in the RFQ.</span></span>   <span data-ttu-id="6bd8e-157">Valor líquido: o preço cotado por um fornecedor, depois de subtrair descontos, para os itens na linha.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-157">Net amount: The price quoted by a vendor, after subtracting any discounts, for the items on the line.</span></span>   <span data-ttu-id="6bd8e-158">Desvio: o número de dias em que a data de vencimento no cabeçalho ou a linha da oferta desvia da data de entrega solicitada no cabeçalho ou na da RFQ.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-158">Deviation: The number of days that the delivery date in the bid header or line deviates from the requested delivery date in the RFQ header or RFQ line.</span></span>   <span data-ttu-id="6bd8e-159">Você só pode inserir uma classificação para cada lance.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-159">You can enter a rank for each bid.</span></span>  
4. <span data-ttu-id="6bd8e-160">Selecione a linha do cabeçalho do outro lance que deseja pontuar.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-160">Select the header line for the other bid that you want to rank.</span></span>
5. <span data-ttu-id="6bd8e-161">No campo Pontuação, insira um número.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-161">In the Rank field, enter a number.</span></span>
6. <span data-ttu-id="6bd8e-162">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-162">Click Save.</span></span>

## <a name="reject-a-bid"></a><span data-ttu-id="6bd8e-163">Rejeitar uma oferta</span><span class="sxs-lookup"><span data-stu-id="6bd8e-163">Reject a bid</span></span>
1. <span data-ttu-id="6bd8e-164">Selecione a linha do cabeçalho do lance que deseja rejeitar</span><span class="sxs-lookup"><span data-stu-id="6bd8e-164">Select the header line for the bid that you want to reject.</span></span>
    * <span data-ttu-id="6bd8e-165">Você só pode aceitar, rejeitar, ou devolver um lance ou linhas dentro de um lance por vez.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-165">You can only accept, reject, or return one bid or lines within one bid at a time.</span></span>  
2. <span data-ttu-id="6bd8e-166">Marque a caixa de seleção Marcar.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-166">Select the Mark check box.</span></span>
    * <span data-ttu-id="6bd8e-167">Se você marcar a caixa de seleção do cabeçalho da oferta, então todas as linhas serão marcadas também.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-167">If you select the Mark check box on the Header of the bid then all the lines will be marked as well.</span></span> <span data-ttu-id="6bd8e-168">Você também pode optar por marcar um subconjunto de linhas na oferta para aceitar ou rejeitar.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-168">You could also choose to mark a subset of the lines within the bid to reject or accept those.</span></span> <span data-ttu-id="6bd8e-169">É possível aceitar uma oferta de fornecedor para algumas linhas de uma solicitação de cotação, e permissões em outras linhas RFQ de outro fornecedor, eles podem precisar fazer isso em 2 etapas, oferecidas uma por vez.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-169">It’s possible to accept one vendor’s bid for some lines of an RFQ, and then award other RFQ lines to a different vendor, however you need to do this in 2 steps, one bid at a time.</span></span> <span data-ttu-id="6bd8e-170">Se as linhas alternativas estiverem presentes, você só poderá aceitar a linha de oferta original ou sua alternativa, mas não ambas.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-170">If alternate lines are present, you can only accept either the original bid line or its alternate, but not both.</span></span>  
3. <span data-ttu-id="6bd8e-171">Clique em Rejeitar.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-171">Click Reject.</span></span>
4. <span data-ttu-id="6bd8e-172">Clique em Parâmetros para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-172">Click Parameters to open the drop dialog.</span></span>
5. <span data-ttu-id="6bd8e-173">No campo Motivo da rejeição, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-173">In the Reason reject field, enter or select a value.</span></span>
    * <span data-ttu-id="6bd8e-174">O motivo para a rejeição será armazenado na resposta.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-174">The reason for rejection will be stored on the reply.</span></span>  
6. <span data-ttu-id="6bd8e-175">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-175">Click OK.</span></span>
7. <span data-ttu-id="6bd8e-176">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-176">Click OK.</span></span>
8. <span data-ttu-id="6bd8e-177">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-177">Close the page.</span></span>
9. <span data-ttu-id="6bd8e-178">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-178">Close the page.</span></span>
10. <span data-ttu-id="6bd8e-179">Atualize a página.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-179">Refresh the page.</span></span>

## <a name="accept-a-bid"></a><span data-ttu-id="6bd8e-180">Aceitar uma oferta</span><span class="sxs-lookup"><span data-stu-id="6bd8e-180">Accept a bid</span></span>
1. <span data-ttu-id="6bd8e-181">Selecione a oferta que deseja aceitar e clique no link no campo Solicitação de cotação.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-181">Select the bid that you want to accept and then click the link in the Request for quotation field.</span></span>
2. <span data-ttu-id="6bd8e-182">No Painel de Ação, clique em Resposta.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-182">On the Action Pane, click Reply.</span></span>
3. <span data-ttu-id="6bd8e-183">Clique em Aceitar.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-183">Click Accept.</span></span>
    * <span data-ttu-id="6bd8e-184">Se você marcou linhas específicas e não outras, então a ação de aceitação incluirá somente as linhas marcadas.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-184">If you have marked specific lines and not others then the accept action will only include the marked lines.</span></span> <span data-ttu-id="6bd8e-185">Se você deseja aceitar todas as linhas da oferta então você não precisará marcar as linhas.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-185">If you want to accept all lines on the bid then you do not have to mark the lines.</span></span>  
4. <span data-ttu-id="6bd8e-186">Clique em Parâmetros para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-186">Click Parameters to open the drop dialog.</span></span>
    * <span data-ttu-id="6bd8e-187">Isso permite que você registre um motivo para aceitar a oferta.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-187">This allows you to record a reason for accepting the bid.</span></span> <span data-ttu-id="6bd8e-188">O motivo para será armazenado no lance.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-188">The reason will be stored on the bid.</span></span>  
5. <span data-ttu-id="6bd8e-189">No campo Motivo da aceitação, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-189">In the Reason accept field, enter or select a value.</span></span>
6. <span data-ttu-id="6bd8e-190">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-190">Click OK.</span></span>
7. <span data-ttu-id="6bd8e-191">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-191">Click OK.</span></span>
    * <span data-ttu-id="6bd8e-192">Quando você clicar em OK, isso gera uma ordem de compra com base nas linhas que estão incluídas na aceitação da solicitação de cotação.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-192">When you click OK this generates a purchase order based on the lines that are included in the RFQ acceptance.</span></span> <span data-ttu-id="6bd8e-193">Se houver outras ofertas que não foram processadas (aceitas, rejeitadas ou retornadas), então o sistema avisará você para rejeitar ofertas restantes.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-193">If there are other bids that have not been processed (accepted, rejected, or returned) then the system will prompt you to reject the remaining bids.</span></span>  

## <a name="view-the-purchase-order-thats-been-generated"></a><span data-ttu-id="6bd8e-194">Ver a ordem de compra que foi gerada</span><span class="sxs-lookup"><span data-stu-id="6bd8e-194">View the purchase order that's been generated</span></span>
1. <span data-ttu-id="6bd8e-195">No Painel de Ação, clique em Geral.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-195">On the Action Pane, click General.</span></span>
2. <span data-ttu-id="6bd8e-196">Clique em Ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-196">Click Purchase order.</span></span>
    * <span data-ttu-id="6bd8e-197">Aqui você pode ver a ordem de compra que foi gerada quando aceitou a oferta.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-197">Here you can see the purchase order that was generated when you accepted the bid.</span></span>  
3. <span data-ttu-id="6bd8e-198">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-198">Close the page.</span></span>
4. <span data-ttu-id="6bd8e-199">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-199">Close the page.</span></span>
5. <span data-ttu-id="6bd8e-200">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-200">Close the page.</span></span>
6. <span data-ttu-id="6bd8e-201">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="6bd8e-201">Close the page.</span></span>



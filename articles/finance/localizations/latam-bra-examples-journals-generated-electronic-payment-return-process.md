---
title: Diários gerados durante o processo de devolução de pagamento eletrônico do Brasil
description: Esse tópico mostra como os diários de pagamentos são gerados quando você importa e lança o arquivo de retorno para pagamentos eletrônicos. As linhas de pagamento aprovadas no arquivo de retorno podem ser lançadas em um diário ou em vários diários.
author: sndray
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 269174
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: d4e31771806e8a9050085943940fc4c340090ce8
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2175200"
---
# <a name="journals-generated-during-the-electronic-payment-return-process-for-brazil"></a><span data-ttu-id="a217a-104">Diários gerados durante o processo de devolução de pagamento eletrônico do Brasil</span><span class="sxs-lookup"><span data-stu-id="a217a-104">Journals generated during the electronic payment return process for Brazil</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a217a-105">Esse tópico mostra como os diários de pagamentos são gerados quando você importa e lança o arquivo de retorno para pagamentos eletrônicos.</span><span class="sxs-lookup"><span data-stu-id="a217a-105">This topic shows how payment journals are generated when you import and post the return file for electronic payments.</span></span> <span data-ttu-id="a217a-106">As linhas de pagamento aprovadas no arquivo de retorno podem ser lançadas em um diário ou em vários diários.</span><span class="sxs-lookup"><span data-stu-id="a217a-106">The approved payment lines in the return file can be posted either to one journal or multiple journals.</span></span>

<span data-ttu-id="a217a-107">É possível fazer pagamentos eletrônicos pela transferência de arquivos entre uma entidade legal e um banco.</span><span class="sxs-lookup"><span data-stu-id="a217a-107">You can make electronic payments by transferring files between a legal entity and a bank.</span></span> <span data-ttu-id="a217a-108">Primeiro, você gera e envia arquivos de remessa eletrônica para o banco.</span><span class="sxs-lookup"><span data-stu-id="a217a-108">First, you generate and send electronic remittance files to the bank.</span></span> <span data-ttu-id="a217a-109">Depois, após o banco processar os arquivos exportados, é possível importar um arquivo de devolução do banco.</span><span class="sxs-lookup"><span data-stu-id="a217a-109">Then, after the bank processes the exported files, you import a return file from the bank.</span></span> <span data-ttu-id="a217a-110">O arquivo de devolução contém informações sobre a aceitação de uma fatura, junto com o número de pagamento fornecido pelo banco, ou informações sobre os pagamentos recebidos de um cliente ou pagos a um fornecedor.</span><span class="sxs-lookup"><span data-stu-id="a217a-110">The return file contains information about the acceptance of an invoice, together with the payment number that is provided by the bank, or information about the payments that are received from a customer or paid to a vendor.</span></span> <span data-ttu-id="a217a-111">Ao importar um arquivo de devolução, o status dos pagamentos é atualizado no campo **Status de pagamento** na página **Transferências de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="a217a-111">When you import a return file, the status of the payments is updated in the **Payment status** field on the **Payment transfers** page.</span></span> <span data-ttu-id="a217a-112">O novo status depende do relacionamento entre os códigos de ocorrência de devolução bancária no arquivo de devolução e os códigos de ocorrência de devolução no Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="a217a-112">The new status depends on the relationship between the bank return occurrence codes in the return file and the return occurrence codes in Dynamics 365 Finance.</span></span> <span data-ttu-id="a217a-113">Ao lançar os pagamentos para os quais o arquivo de devolução é importado, somente os pagamentos que possuem um status **Aprovado** são lançados.</span><span class="sxs-lookup"><span data-stu-id="a217a-113">When you post the payments that the return file is imported for, only payments that have a status of **Approved** are posted.</span></span> <span data-ttu-id="a217a-114">Esses pagamentos podem ser lançados para o mesmo diário de pagamento ou para vários diários de pagamento.</span><span class="sxs-lookup"><span data-stu-id="a217a-114">These payments can be posted to either the same payment journal or multiple payment journals.</span></span>

## <a name="approved-payment-lines-that-are-posted-to-the-same-payment-journal"></a><span data-ttu-id="a217a-115">Linhas de pagamento aprovadas que são lançadas no mesmo diário de pagamento</span><span class="sxs-lookup"><span data-stu-id="a217a-115">Approved payment lines that are posted to the same payment journal</span></span>
<span data-ttu-id="a217a-116">É possível lançar todas as linhas de pagamento aprovadas que pertencem ao mesmo nome de diário em um diário de pagamento.</span><span class="sxs-lookup"><span data-stu-id="a217a-116">You can post all approved payment lines that belong to the same journal name to a payment journal.</span></span> <span data-ttu-id="a217a-117">Por exemplo, você importa um arquivo de devolução que contém seis linhas de pagamento.</span><span class="sxs-lookup"><span data-stu-id="a217a-117">For example, you import a return file that contains six payment lines.</span></span> <span data-ttu-id="a217a-118">Três linhas de pagamento têm o status **Aprovado** e três têm o status **Rejeitado**.</span><span class="sxs-lookup"><span data-stu-id="a217a-118">Three payment lines have a status of **Approved**, and three payment lines have a status of **Rejected**.</span></span> <span data-ttu-id="a217a-119">Duas das linhas de pagamento aprovadas para os números de diário 001 e 002, pertencem ao mesmo nome de diário, DP.</span><span class="sxs-lookup"><span data-stu-id="a217a-119">Two of the approved payment lines, for journal numbers 001 and 002, belong to the same journal name, DP.</span></span> <span data-ttu-id="a217a-120">A terceira linha de pagamento aprovada para o número de diário 100, pertence ao nome do diário Teste.</span><span class="sxs-lookup"><span data-stu-id="a217a-120">The third approved payment line, for journal number 100, belongs to the Test journal name.</span></span> <span data-ttu-id="a217a-121">A tabela a seguir contém informações sobre as linhas de pagamento no arquivo de devolução.</span><span class="sxs-lookup"><span data-stu-id="a217a-121">The following table contains information about the payment lines in the return file.</span></span>

| <span data-ttu-id="a217a-122">Nome do diário</span><span class="sxs-lookup"><span data-stu-id="a217a-122">Journal name</span></span> | <span data-ttu-id="a217a-123">Número do diário</span><span class="sxs-lookup"><span data-stu-id="a217a-123">Journal number</span></span> | <span data-ttu-id="a217a-124">Linha de pagamento</span><span class="sxs-lookup"><span data-stu-id="a217a-124">Payment line</span></span> | <span data-ttu-id="a217a-125">Status</span><span class="sxs-lookup"><span data-stu-id="a217a-125">Status</span></span>   | <span data-ttu-id="a217a-126">Valor</span><span class="sxs-lookup"><span data-stu-id="a217a-126">Amount</span></span> |
|--------------|----------------|--------------|----------|--------|
| <span data-ttu-id="a217a-127">DP</span><span class="sxs-lookup"><span data-stu-id="a217a-127">DP</span></span>           | <span data-ttu-id="a217a-128">001</span><span class="sxs-lookup"><span data-stu-id="a217a-128">001</span></span>            | <span data-ttu-id="a217a-129">1</span><span class="sxs-lookup"><span data-stu-id="a217a-129">1</span></span>            | <span data-ttu-id="a217a-130">Recebido</span><span class="sxs-lookup"><span data-stu-id="a217a-130">Received</span></span> | <span data-ttu-id="a217a-131">1.000</span><span class="sxs-lookup"><span data-stu-id="a217a-131">1,000</span></span>  |
| <span data-ttu-id="a217a-132">DP</span><span class="sxs-lookup"><span data-stu-id="a217a-132">DP</span></span>           | <span data-ttu-id="a217a-133">001</span><span class="sxs-lookup"><span data-stu-id="a217a-133">001</span></span>            | <span data-ttu-id="a217a-134">2</span><span class="sxs-lookup"><span data-stu-id="a217a-134">2</span></span>            | <span data-ttu-id="a217a-135">Aprovada</span><span class="sxs-lookup"><span data-stu-id="a217a-135">Approved</span></span> | <span data-ttu-id="a217a-136">2.000</span><span class="sxs-lookup"><span data-stu-id="a217a-136">2,000</span></span>  |
| <span data-ttu-id="a217a-137">Testar</span><span class="sxs-lookup"><span data-stu-id="a217a-137">Test</span></span>         | <span data-ttu-id="a217a-138">100</span><span class="sxs-lookup"><span data-stu-id="a217a-138">100</span></span>            | <span data-ttu-id="a217a-139">1</span><span class="sxs-lookup"><span data-stu-id="a217a-139">1</span></span>            | <span data-ttu-id="a217a-140">Aprovada</span><span class="sxs-lookup"><span data-stu-id="a217a-140">Approved</span></span> | <span data-ttu-id="a217a-141">3.000</span><span class="sxs-lookup"><span data-stu-id="a217a-141">3,000</span></span>  |
| <span data-ttu-id="a217a-142">Testar</span><span class="sxs-lookup"><span data-stu-id="a217a-142">Test</span></span>         | <span data-ttu-id="a217a-143">100</span><span class="sxs-lookup"><span data-stu-id="a217a-143">100</span></span>            | <span data-ttu-id="a217a-144">2</span><span class="sxs-lookup"><span data-stu-id="a217a-144">2</span></span>            | <span data-ttu-id="a217a-145">Rejeitada</span><span class="sxs-lookup"><span data-stu-id="a217a-145">Rejected</span></span> | <span data-ttu-id="a217a-146">4.000</span><span class="sxs-lookup"><span data-stu-id="a217a-146">4,000</span></span>  |
| <span data-ttu-id="a217a-147">DP</span><span class="sxs-lookup"><span data-stu-id="a217a-147">DP</span></span>           | <span data-ttu-id="a217a-148">002</span><span class="sxs-lookup"><span data-stu-id="a217a-148">002</span></span>            | <span data-ttu-id="a217a-149">1</span><span class="sxs-lookup"><span data-stu-id="a217a-149">1</span></span>            | <span data-ttu-id="a217a-150">Aprovada</span><span class="sxs-lookup"><span data-stu-id="a217a-150">Approved</span></span> | <span data-ttu-id="a217a-151">5.000</span><span class="sxs-lookup"><span data-stu-id="a217a-151">5,000</span></span>  |
| <span data-ttu-id="a217a-152">DP</span><span class="sxs-lookup"><span data-stu-id="a217a-152">DP</span></span>           | <span data-ttu-id="a217a-153">002</span><span class="sxs-lookup"><span data-stu-id="a217a-153">002</span></span>            | <span data-ttu-id="a217a-154">2</span><span class="sxs-lookup"><span data-stu-id="a217a-154">2</span></span>            | <span data-ttu-id="a217a-155">Enviada</span><span class="sxs-lookup"><span data-stu-id="a217a-155">Sent</span></span>     | <span data-ttu-id="a217a-156">6,000</span><span class="sxs-lookup"><span data-stu-id="a217a-156">6,000</span></span>  |

<span data-ttu-id="a217a-157">Quando você lança as linhas de pagamento, as duas linhas aprovadas do diário números 001 e 002 que pertencem ao nome de diário de DP são lançadas no mesmo diário de liquidação, 003.</span><span class="sxs-lookup"><span data-stu-id="a217a-157">When you post the payment lines, the two approved payment lines for journal numbers 001 and 002 that belong to the DP journal name are posted to the same payment journal, 003.</span></span> <span data-ttu-id="a217a-158">Entretanto, a linha de pagamento aprovada para o número de diário 100 que pertence ao nome de diário Teste é lançada no diário de pagamento 101.</span><span class="sxs-lookup"><span data-stu-id="a217a-158">However, the approved payment line for journal number 100 that belongs to the Test journal name is posted to payment journal 101.</span></span> <span data-ttu-id="a217a-159">A tabela a seguir contém informações sobre os diários de pagamento que são criados quando você lança as linhas de pagamento aprovadas.</span><span class="sxs-lookup"><span data-stu-id="a217a-159">The following table contains information about the payment journals that are created when you post the approved payment lines.</span></span>

| <span data-ttu-id="a217a-160">Novo número do diário</span><span class="sxs-lookup"><span data-stu-id="a217a-160">New journal number</span></span> | <span data-ttu-id="a217a-161">A partir do número do diário</span><span class="sxs-lookup"><span data-stu-id="a217a-161">From journal number</span></span> | <span data-ttu-id="a217a-162">Linha de pagamento</span><span class="sxs-lookup"><span data-stu-id="a217a-162">Payment line</span></span> | <span data-ttu-id="a217a-163">Status</span><span class="sxs-lookup"><span data-stu-id="a217a-163">Status</span></span>   | <span data-ttu-id="a217a-164">Valor</span><span class="sxs-lookup"><span data-stu-id="a217a-164">Amount</span></span> |
|--------------------|---------------------|--------------|----------|--------|
| <span data-ttu-id="a217a-165">003</span><span class="sxs-lookup"><span data-stu-id="a217a-165">003</span></span>                | <span data-ttu-id="a217a-166">001</span><span class="sxs-lookup"><span data-stu-id="a217a-166">001</span></span>                 | <span data-ttu-id="a217a-167">2</span><span class="sxs-lookup"><span data-stu-id="a217a-167">2</span></span>            | <span data-ttu-id="a217a-168">Aprovada</span><span class="sxs-lookup"><span data-stu-id="a217a-168">Approved</span></span> | <span data-ttu-id="a217a-169">2.000</span><span class="sxs-lookup"><span data-stu-id="a217a-169">2,000</span></span>  |
|                    | <span data-ttu-id="a217a-170">002</span><span class="sxs-lookup"><span data-stu-id="a217a-170">002</span></span>                 | <span data-ttu-id="a217a-171">1</span><span class="sxs-lookup"><span data-stu-id="a217a-171">1</span></span>            | <span data-ttu-id="a217a-172">Aprovada</span><span class="sxs-lookup"><span data-stu-id="a217a-172">Approved</span></span> | <span data-ttu-id="a217a-173">5.000</span><span class="sxs-lookup"><span data-stu-id="a217a-173">5,000</span></span>  |
| <span data-ttu-id="a217a-174">101</span><span class="sxs-lookup"><span data-stu-id="a217a-174">101</span></span>                | <span data-ttu-id="a217a-175">100</span><span class="sxs-lookup"><span data-stu-id="a217a-175">100</span></span>                 | <span data-ttu-id="a217a-176">1</span><span class="sxs-lookup"><span data-stu-id="a217a-176">1</span></span>            | <span data-ttu-id="a217a-177">Aprovada</span><span class="sxs-lookup"><span data-stu-id="a217a-177">Approved</span></span> | <span data-ttu-id="a217a-178">3.000</span><span class="sxs-lookup"><span data-stu-id="a217a-178">3,000</span></span>  |

## <a name="approved-payment-lines-that-are-posted-to-multiple-payment-journals"></a><span data-ttu-id="a217a-179">Linhas de pagamento aprovadas que são lançadas em vários diários de pagamento</span><span class="sxs-lookup"><span data-stu-id="a217a-179">Approved payment lines that are posted to multiple payment journals</span></span>
<span data-ttu-id="a217a-180">Se a data da transação que é atualizada para as linhas de pagamento aprovadas for diferente de cada linha de pagamento em um arquivo de devolução, as linhas de pagamento serão lançadas em diários de pagamento diferentes.</span><span class="sxs-lookup"><span data-stu-id="a217a-180">If the transaction date that is updated for the approved payment lines differs for each payment line in a return file, the payment lines are posted to different payment journals.</span></span> <span data-ttu-id="a217a-181">Por exemplo, você importa um arquivo de devolução que contém arquivos de pagamento aprovados que possuem três datas de transação diferentes.</span><span class="sxs-lookup"><span data-stu-id="a217a-181">For example, you import a return file that contains approved payment files that have three different transaction dates.</span></span> <span data-ttu-id="a217a-182">A tabela a seguir contém informações sobre as três linhas de pagamento aprovadas que possuem datas de transação diferentes.</span><span class="sxs-lookup"><span data-stu-id="a217a-182">The following table contains information about the three approved payment lines that have different transaction dates.</span></span>

| <span data-ttu-id="a217a-183">Número do diário</span><span class="sxs-lookup"><span data-stu-id="a217a-183">Journal number</span></span> | <span data-ttu-id="a217a-184">Linha de pagamento</span><span class="sxs-lookup"><span data-stu-id="a217a-184">Payment line</span></span> | <span data-ttu-id="a217a-185">Data da transação</span><span class="sxs-lookup"><span data-stu-id="a217a-185">Transaction date</span></span> | <span data-ttu-id="a217a-186">Status</span><span class="sxs-lookup"><span data-stu-id="a217a-186">Status</span></span>   | <span data-ttu-id="a217a-187">Valor</span><span class="sxs-lookup"><span data-stu-id="a217a-187">Amount</span></span> |
|----------------|--------------|------------------|----------|--------|
| <span data-ttu-id="a217a-188">001</span><span class="sxs-lookup"><span data-stu-id="a217a-188">001</span></span>            | <span data-ttu-id="a217a-189">1</span><span class="sxs-lookup"><span data-stu-id="a217a-189">1</span></span>            | <span data-ttu-id="a217a-190">5 de janeiro, 2013</span><span class="sxs-lookup"><span data-stu-id="a217a-190">January 5, 2013</span></span>  | <span data-ttu-id="a217a-191">Aprovada</span><span class="sxs-lookup"><span data-stu-id="a217a-191">Approved</span></span> | <span data-ttu-id="a217a-192">1.000</span><span class="sxs-lookup"><span data-stu-id="a217a-192">1,000</span></span>  |
|                | <span data-ttu-id="a217a-193">2</span><span class="sxs-lookup"><span data-stu-id="a217a-193">2</span></span>            | <span data-ttu-id="a217a-194">2 de janeiro, 2013</span><span class="sxs-lookup"><span data-stu-id="a217a-194">January 2, 2013</span></span>  | <span data-ttu-id="a217a-195">Recebido</span><span class="sxs-lookup"><span data-stu-id="a217a-195">Received</span></span> | <span data-ttu-id="a217a-196">2.000</span><span class="sxs-lookup"><span data-stu-id="a217a-196">2,000</span></span>  |
|                | <span data-ttu-id="a217a-197">3</span><span class="sxs-lookup"><span data-stu-id="a217a-197">3</span></span>            | <span data-ttu-id="a217a-198">1 de janeiro, 2013</span><span class="sxs-lookup"><span data-stu-id="a217a-198">January 1, 2013</span></span>  | <span data-ttu-id="a217a-199">Aprovada</span><span class="sxs-lookup"><span data-stu-id="a217a-199">Approved</span></span> | <span data-ttu-id="a217a-200">3.000</span><span class="sxs-lookup"><span data-stu-id="a217a-200">3,000</span></span>  |
|                | <span data-ttu-id="a217a-201">4</span><span class="sxs-lookup"><span data-stu-id="a217a-201">4</span></span>            | <span data-ttu-id="a217a-202">3 de janeiro, 2013</span><span class="sxs-lookup"><span data-stu-id="a217a-202">January 3, 2013</span></span>  | <span data-ttu-id="a217a-203">Aprovada</span><span class="sxs-lookup"><span data-stu-id="a217a-203">Approved</span></span> | <span data-ttu-id="a217a-204">4.000</span><span class="sxs-lookup"><span data-stu-id="a217a-204">4,000</span></span>  |

<span data-ttu-id="a217a-205">Ao lançar as linhas de pagamento aprovadas, as três linhas de pagamento são lançadas em três diários diferentes.</span><span class="sxs-lookup"><span data-stu-id="a217a-205">When you post the approved payment lines, the three payment lines are posted to three different journals.</span></span> <span data-ttu-id="a217a-206">A tabela a seguir contém informações sobre os diários de pagamento que são criados quando você lança as linhas de pagamento aprovadas.</span><span class="sxs-lookup"><span data-stu-id="a217a-206">The following table contains information about the payment journals that are created when you post the approved payment lines.</span></span>

| <span data-ttu-id="a217a-207">Número do diário</span><span class="sxs-lookup"><span data-stu-id="a217a-207">Journal number</span></span> | <span data-ttu-id="a217a-208">Linha de pagamento</span><span class="sxs-lookup"><span data-stu-id="a217a-208">Payment line</span></span> | <span data-ttu-id="a217a-209">Data da transação</span><span class="sxs-lookup"><span data-stu-id="a217a-209">Transaction date</span></span> | <span data-ttu-id="a217a-210">Status</span><span class="sxs-lookup"><span data-stu-id="a217a-210">Status</span></span>   | <span data-ttu-id="a217a-211">Valor</span><span class="sxs-lookup"><span data-stu-id="a217a-211">Amount</span></span> |
|----------------|--------------|------------------|----------|--------|
| <span data-ttu-id="a217a-212">002</span><span class="sxs-lookup"><span data-stu-id="a217a-212">002</span></span>            | <span data-ttu-id="a217a-213">1</span><span class="sxs-lookup"><span data-stu-id="a217a-213">1</span></span>            | <span data-ttu-id="a217a-214">5 de janeiro, 2013</span><span class="sxs-lookup"><span data-stu-id="a217a-214">January 5, 2013</span></span>  | <span data-ttu-id="a217a-215">Aprovada</span><span class="sxs-lookup"><span data-stu-id="a217a-215">Approved</span></span> | <span data-ttu-id="a217a-216">1.000</span><span class="sxs-lookup"><span data-stu-id="a217a-216">1,000</span></span>  |
| <span data-ttu-id="a217a-217">003</span><span class="sxs-lookup"><span data-stu-id="a217a-217">003</span></span>            | <span data-ttu-id="a217a-218">1</span><span class="sxs-lookup"><span data-stu-id="a217a-218">1</span></span>            | <span data-ttu-id="a217a-219">1 de janeiro, 2013</span><span class="sxs-lookup"><span data-stu-id="a217a-219">January 1, 2013</span></span>  | <span data-ttu-id="a217a-220">Aprovada</span><span class="sxs-lookup"><span data-stu-id="a217a-220">Approved</span></span> | <span data-ttu-id="a217a-221">3.000</span><span class="sxs-lookup"><span data-stu-id="a217a-221">3,000</span></span>  |
| <span data-ttu-id="a217a-222">004</span><span class="sxs-lookup"><span data-stu-id="a217a-222">004</span></span>            | <span data-ttu-id="a217a-223">1</span><span class="sxs-lookup"><span data-stu-id="a217a-223">1</span></span>            | <span data-ttu-id="a217a-224">3 de janeiro, 2013</span><span class="sxs-lookup"><span data-stu-id="a217a-224">January 3, 2013</span></span>  | <span data-ttu-id="a217a-225">Aprovada</span><span class="sxs-lookup"><span data-stu-id="a217a-225">Approved</span></span> | <span data-ttu-id="a217a-226">4.000</span><span class="sxs-lookup"><span data-stu-id="a217a-226">4,000</span></span>  |





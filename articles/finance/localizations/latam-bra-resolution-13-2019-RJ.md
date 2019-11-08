---
title: Resolução do SPED fiscal 13/2019 RJ
description: Este tópico explica como configurar e gerar arquivos de texto do SPED ECD.
author: v-oloski
manager: AnnBe
ms.date: 10/22/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Brazil
ms.author: shylaw
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7
ms.openlocfilehash: 0692f8489badaa9e23da38eb2c6b6df6f8bc505a
ms.sourcegitcommit: a8696b0542325d467eeb57b12fd643b1d9269f76
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2019
ms.locfileid: "2651792"
---
# <a name="sped-fiscal-resolution-132019-rj"></a><span data-ttu-id="c33eb-103">Resolução do SPED fiscal 13/2019 RJ</span><span class="sxs-lookup"><span data-stu-id="c33eb-103">SPED fiscal resolution 13/2019 RJ</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c33eb-104">O estado do Rio de Janeiro (RJ) publicou a Resolução 13/2019.</span><span class="sxs-lookup"><span data-stu-id="c33eb-104">The state of Rio de Janeiro (RJ) has published Resolution 13/2019.</span></span> <span data-ttu-id="c33eb-105">Esta resolução define como uma nota fiscal eletrônica (NF-e) deve ser emitida e como as informações devem ser registradas no EFD-ICMS/IPI quando as seguintes operações forem executadas (Decreto nº.</span><span class="sxs-lookup"><span data-stu-id="c33eb-105">This resolution defines how a Nota fiscal eletrônica (NF-e) should be issued, and how the information should be recorded in the EFD-ICMS/IPI when the following operations are run (Decree No.</span></span> <span data-ttu-id="c33eb-106">27.815/01):</span><span class="sxs-lookup"><span data-stu-id="c33eb-106">27.815/01):</span></span>

- <span data-ttu-id="c33eb-107">Isenção</span><span class="sxs-lookup"><span data-stu-id="c33eb-107">Exemption</span></span>
- <span data-ttu-id="c33eb-108">Redução da base de cálculo ou redução da taxa</span><span class="sxs-lookup"><span data-stu-id="c33eb-108">Reduction of the basis of calculation or reduction of rate</span></span>
- <span data-ttu-id="c33eb-109">Crédito presumido</span><span class="sxs-lookup"><span data-stu-id="c33eb-109">Presumed credit</span></span>
- <span data-ttu-id="c33eb-110">Tributação na cobrança, tributação no recebimento ou tributação na saída</span><span class="sxs-lookup"><span data-stu-id="c33eb-110">Taxation on billing, taxation on receipt, or taxation on output</span></span>
- <span data-ttu-id="c33eb-111">Diferimento</span><span class="sxs-lookup"><span data-stu-id="c33eb-111">Deferral</span></span>
- <span data-ttu-id="c33eb-112">Inelegibilidade para estorno de crédito</span><span class="sxs-lookup"><span data-stu-id="c33eb-112">Ineligibility for credit reversal</span></span>
- <span data-ttu-id="c33eb-113">Reparo fiscal de crédito ou transferência de saldo acumulado de crédito</span><span class="sxs-lookup"><span data-stu-id="c33eb-113">Fiscal credit repair or accumulated credit balance transfer</span></span>

<span data-ttu-id="c33eb-114">De acordo com a resolução, as exonerações são registradas como ajustes nas notas fiscais e nos livros fiscais e devem ser relatadas nos arquivos do Sistema Público de Escrituração Digital (SPED).</span><span class="sxs-lookup"><span data-stu-id="c33eb-114">According to the resolution, exonerations are registered as adjustments on fiscal documents and in fiscal books, and should be reported in Sistema Público de Escrituração Digital (SPED) files.</span></span>

<span data-ttu-id="c33eb-115">Os requisitos de resolução afetam a saída das linhas E111, E115, C195, C197 e 0460 no SPED Fiscal.</span><span class="sxs-lookup"><span data-stu-id="c33eb-115">The resolution requirements affect the output of lines E111, E115, C195, C197, and 0460 in SPED Fiscal.</span></span>

## <a name="sped-fiscal-records-by-operation"></a><span data-ttu-id="c33eb-116">Registros do SPED Fiscal por operação</span><span class="sxs-lookup"><span data-stu-id="c33eb-116">SPED Fiscal records by operation</span></span>

### <a name="exemption-and-credit-reversal"></a><span data-ttu-id="c33eb-117">Isenção e estorno de crédito</span><span class="sxs-lookup"><span data-stu-id="c33eb-117">Exemption and credit reversal</span></span>

<span data-ttu-id="c33eb-118">Durante o processo de sincronização, dois tipos de transações de ajuste são criados na apuração do Imposto Sobre Operações Relativas à Circulação de Mercadorias e Serviços (ICMS) quando as seguintes condições são atendidas:</span><span class="sxs-lookup"><span data-stu-id="c33eb-118">During the synchronization process, two types of adjustment transactions are created in the Imposto Sobre Operações Relativas à Circulação de Mercadorias e Serviços (ICMS) tax assessment when the following conditions are met:</span></span>

- <span data-ttu-id="c33eb-119">Uma nota fiscal de saída emitida pelo estado do RJ tem um código de tributação de **30** ou **40**.</span><span class="sxs-lookup"><span data-stu-id="c33eb-119">An outgoing fiscal document that is issued from RJ state has a taxation code of **30** or **40**.</span></span>
- <span data-ttu-id="c33eb-120">Os códigos de benefícios da tabela 5.2 e da tabela 5.3, e também códigos de observação, são atribuídos ao item e ao estado relacionados da nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="c33eb-120">The benefit codes from table 5.2 and table 5.3, and also observation codes, are assigned to the related item and state of the fiscal document.</span></span> <span data-ttu-id="c33eb-121">Por exemplo, o código da tabela 5.2 é **RJ801137** e o código da tabela 5.3 é **RJ90980000**.</span><span class="sxs-lookup"><span data-stu-id="c33eb-121">For example, the code from table 5.2 is **RJ801137**, and the code from table 5.3 is **RJ90980000**.</span></span>

<span data-ttu-id="c33eb-122">Veja alguns exemplos de transações de ajuste criadas automaticamente no SPED Fiscal:</span><span class="sxs-lookup"><span data-stu-id="c33eb-122">Here are some examples of adjustment transactions that are automatically created in SPED Fiscal:</span></span>

- <span data-ttu-id="c33eb-123">O código de ajuste da tabela 5.2 gera um registro E115:</span><span class="sxs-lookup"><span data-stu-id="c33eb-123">The adjustment code from table 5.2 generates an E115 record:</span></span>

    <span data-ttu-id="c33eb-124">\|E115\|RJ801137\|0\|\|</span><span class="sxs-lookup"><span data-stu-id="c33eb-124">\|E115\|RJ801137\|0\|\|</span></span>

- <span data-ttu-id="c33eb-125">O código de ajuste da tabela 5.3 gera um registro C197:</span><span class="sxs-lookup"><span data-stu-id="c33eb-125">The adjustment code from table 5.3 generates a C197 record:</span></span>

    <span data-ttu-id="c33eb-126">\|C197\|RJ90980000\|RJ801137\|ItemId\|0,00\|0,00\|0,00\|0,88\|</span><span class="sxs-lookup"><span data-stu-id="c33eb-126">\|C197\|RJ90980000\|RJ801137\|ItemId\|0.00\|0.00\|0.00\|0.88\|</span></span>

    > [!NOTE]
    > <span data-ttu-id="c33eb-127">Neste exemplo, o valor base é 3,5, o percentual de ICMS é 18 e a taxa do Fundo de Combate e Erradicação à Pobreza (FCP) é 0,02.</span><span class="sxs-lookup"><span data-stu-id="c33eb-127">In this example, the base amount is 3.5, the ICMS percentage is 18, and the Fundo de Combate e Erradicação à Pobreza (FCP) rate is 0.02.</span></span> <span data-ttu-id="c33eb-128">Portanto, o valor 0,88 é calculado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="c33eb-128">Therefore, the amount 0.88 is calculated in the following way:</span></span>
    >
    > <span data-ttu-id="c33eb-129">3,5 ÷ (1 – \[0,18 + 0,02\]) × (0,18 + 0,02)</span><span class="sxs-lookup"><span data-stu-id="c33eb-129">3.5 ÷ (1 – \[0.18 + 0.02\]) × (0.18 + 0.02)</span></span>

- <span data-ttu-id="c33eb-130">O código de observação atribuído ao item e estado relacionados da nota fiscal gera registros C195 e 0460:</span><span class="sxs-lookup"><span data-stu-id="c33eb-130">The observation code that is assigned to the related item and state of the fiscal document generates C195 and 0460 records:</span></span>

    <span data-ttu-id="c33eb-131">\|C195\|\<Código de observação\>\|\<Descrição do código de observação\>\|</span><span class="sxs-lookup"><span data-stu-id="c33eb-131">\|C195\|\<Observation code\>\|\<Observation code description\>\|</span></span>

    <span data-ttu-id="c33eb-132">\|0460\|\<Código de observação\>\|\<Descrição do código de observação\>\|</span><span class="sxs-lookup"><span data-stu-id="c33eb-132">\|0460\|\<Observation code\>\|\<Observation code description\>\|</span></span>

<span data-ttu-id="c33eb-133">Para registrar o estorno de crédito, crie um ajuste manual no diário Ajuste geral de imposto/benefício/incentivo e adicione o código da tabela 5.2 ao campo **Descrição**.</span><span class="sxs-lookup"><span data-stu-id="c33eb-133">To register the credit reversal, create a manual adjustment in the General tax adjustment/benefit/incentive journal, and add the code from table 5.2 to the **Description** field.</span></span>

<span data-ttu-id="c33eb-134">Veja um exemplo de uma transação de ajuste criada automaticamente no SPED Fiscal:</span><span class="sxs-lookup"><span data-stu-id="c33eb-134">Here is an example of an adjustment transaction that is automatically created in SPED Fiscal:</span></span>

<span data-ttu-id="c33eb-135">\|E111\|RJ18003\|RJ801137\|\<Valor do ajuste\>\|</span><span class="sxs-lookup"><span data-stu-id="c33eb-135">\|E111\|RJ18003\|RJ801137\|\<Adjustment amount\>\|</span></span>

### <a name="reduction-of-tax-base-or-percentage"></a><span data-ttu-id="c33eb-136">Redução da base tributária ou percentual</span><span class="sxs-lookup"><span data-stu-id="c33eb-136">Reduction of tax base or percentage</span></span>

<span data-ttu-id="c33eb-137">Durante o processo de sincronização, dois tipos de transações de ajuste são criados na apuração do imposto ICMS quando as seguintes condições são atendidas:</span><span class="sxs-lookup"><span data-stu-id="c33eb-137">During the synchronization process, two types of adjustment transactions are created in the ICMS tax assessment when the following conditions are met:</span></span>

- <span data-ttu-id="c33eb-138">Uma nota fiscal de saída emitida pelo estado do RJ tem um código de tributação de **20** ou **70**.</span><span class="sxs-lookup"><span data-stu-id="c33eb-138">An outgoing fiscal document that is issued from RJ state has a taxation code of **20** or **70**.</span></span>
- <span data-ttu-id="c33eb-139">Os códigos de benefícios da tabela 5.2 e da tabela 5.3 são atribuídos ao item e ao estado relacionados da nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="c33eb-139">The benefit codes from table 5.2 and table 5.3 are assigned to the related item and state of the fiscal document.</span></span> <span data-ttu-id="c33eb-140">Por exemplo, o código da tabela 5.2 é **RJ802164** e o código da tabela 5.3 é **RJ90980000**.</span><span class="sxs-lookup"><span data-stu-id="c33eb-140">For example, the code from table 5.2 is **RJ802164**, and the code from table 5.3 is **RJ90980000**.</span></span>

<span data-ttu-id="c33eb-141">Veja alguns exemplos de transações de ajuste criadas automaticamente no SPED Fiscal:</span><span class="sxs-lookup"><span data-stu-id="c33eb-141">Here are some examples of adjustment transactions that are automatically created in SPED Fiscal:</span></span>

- <span data-ttu-id="c33eb-142">O código de ajuste da tabela 5.2 gera um registro E115:</span><span class="sxs-lookup"><span data-stu-id="c33eb-142">The adjustment code from table 5.2 generates an E115 record:</span></span>

    <span data-ttu-id="c33eb-143">\|E115\|RJ802164\|0\|\|</span><span class="sxs-lookup"><span data-stu-id="c33eb-143">\|E115\|RJ802164\|0\|\|</span></span>

- <span data-ttu-id="c33eb-144">O código de ajuste da tabela 5.3 gera um registro C197:</span><span class="sxs-lookup"><span data-stu-id="c33eb-144">The adjustment code from table 5.3 generates a C197 record:</span></span>

    <span data-ttu-id="c33eb-145">\|C197\|RJ90980000\|RJ802164\|ItemId\|0,00\|0,00\|0,00\|0,20\|</span><span class="sxs-lookup"><span data-stu-id="c33eb-145">\|C197\|RJ90980000\|RJ802164\|ItemId\|0.00\|0.00\|0.00\|0,20\|</span></span>

    > [!NOTE]
    > <span data-ttu-id="c33eb-146">Neste exemplo, o valor base é 3,5, o percentual de ICMS é 12 e a redução de percentual é 41,67.</span><span class="sxs-lookup"><span data-stu-id="c33eb-146">In this example, the base amount is 3.5, the ICMS percentage is 12, and the percentage reduction is 41.67.</span></span> <span data-ttu-id="c33eb-147">Portanto, o valor 0,20 é calculado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="c33eb-147">Therefore, the amount 0.20 is calculated in the following way:</span></span>
    >
    > <span data-ttu-id="c33eb-148">3,5 × (1 – \[0,12 × (1 – 0,4167)\]) ÷ (1 – 0,12) – 3,5</span><span class="sxs-lookup"><span data-stu-id="c33eb-148">3.5 × (1 – \[0.12 × (1 – 0.4167)\]) ÷ (1 – 0.12) – 3.5</span></span>

- <span data-ttu-id="c33eb-149">O código de observação atribuído ao item e estado relacionados da nota fiscal gera registros C195 e 0460:</span><span class="sxs-lookup"><span data-stu-id="c33eb-149">The observation code that is assigned to the related item and state of the fiscal document generates C195 and 0460 records:</span></span>

    <span data-ttu-id="c33eb-150">\|C195\|\<Código de observação\>\|\<Descrição do código de observação\>\|</span><span class="sxs-lookup"><span data-stu-id="c33eb-150">\|C195\|\<Observation code\>\|\<Observation code description\>\|</span></span>

    <span data-ttu-id="c33eb-151">\|0460\|\<Código de observação\>\|\<Descrição do código de observação\>\|</span><span class="sxs-lookup"><span data-stu-id="c33eb-151">\|0460\|\<Observation code\>\|\<Observation code description\>\|</span></span>

### <a name="presumed-credit"></a><span data-ttu-id="c33eb-152">Crédito presumido</span><span class="sxs-lookup"><span data-stu-id="c33eb-152">Presumed credit</span></span>

<span data-ttu-id="c33eb-153">**Fora do escopo:** o sistema não pode preparar a porcentagem adicional necessária para os registros C197.</span><span class="sxs-lookup"><span data-stu-id="c33eb-153">**Out of scope:** The system can't prepare the additional percentage that is required for C197 records.</span></span>

<span data-ttu-id="c33eb-154">Para registrar o estorno de créditos, crie um ajuste manual no diário Ajuste geral de imposto/benefício/incentivo e adicione o código da tabela 5.2 ao campo **Descrição**.</span><span class="sxs-lookup"><span data-stu-id="c33eb-154">To register the reversal of credits, create a manual adjustment in the General tax adjustment/benefit/incentive journal, and add the code from table 5.2 to the **Description** field.</span></span>

<span data-ttu-id="c33eb-155">Veja um exemplo de uma transação de ajuste criada automaticamente no SPED Fiscal:</span><span class="sxs-lookup"><span data-stu-id="c33eb-155">Here is an example of an adjustment transaction that is automatically created in SPED Fiscal:</span></span>

<span data-ttu-id="c33eb-156">\|E111\|RJ018003\|RJ805289\|\<Valor do ajuste\>\|</span><span class="sxs-lookup"><span data-stu-id="c33eb-156">\|E111\|RJ018003\|RJ805289\|\<Adjustment amount\>\|</span></span>

### <a name="tax-on-total-sales-output-and-billing"></a><span data-ttu-id="c33eb-157">Imposto sobre vendas totais, produção e cobrança</span><span class="sxs-lookup"><span data-stu-id="c33eb-157">Tax on total sales, output, and billing</span></span>

<span data-ttu-id="c33eb-158">Durante o processo de sincronização, um tipo de transação de ajuste é criado na apuração do imposto ICMS quando as seguintes condições são atendidas:</span><span class="sxs-lookup"><span data-stu-id="c33eb-158">During the synchronization process, one type of adjustment transaction is created in the ICMS tax assessment when the following conditions are met:</span></span>

- <span data-ttu-id="c33eb-159">Os documentos fiscais de saída emitidos pelo estado do RJ têm um código tributário de **00**.</span><span class="sxs-lookup"><span data-stu-id="c33eb-159">Outgoing fiscal documents that are issued from RJ state have a taxation code of **00**.</span></span>
- <span data-ttu-id="c33eb-160">O código de benefício da tabela 5.2 é atribuído ao item e estado relacionados de uma nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="c33eb-160">The benefit code from table 5.2 is assigned to the related item and state of a fiscal document.</span></span> <span data-ttu-id="c33eb-161">O código da tabela 5.3 não está atribuído.</span><span class="sxs-lookup"><span data-stu-id="c33eb-161">The code from the table 5.3 isn't assigned.</span></span> <span data-ttu-id="c33eb-162">Por exemplo, o código da tabela 5.2 é **RJ822371**.</span><span class="sxs-lookup"><span data-stu-id="c33eb-162">For example, the code from table 5.2 is **RJ822371**.</span></span>

<span data-ttu-id="c33eb-163">Veja um exemplo de uma transação de ajuste criada automaticamente no SPED Fiscal:</span><span class="sxs-lookup"><span data-stu-id="c33eb-163">Here is an example of an adjustment transaction that is automatically created in SPED Fiscal:</span></span>

- <span data-ttu-id="c33eb-164">O código de ajuste da tabela 5.2 gera um registro E115:</span><span class="sxs-lookup"><span data-stu-id="c33eb-164">The adjustment code from table 5.2 generates an E115 record:</span></span>

    <span data-ttu-id="c33eb-165">\|E115\|RJ822371\|0\|\|</span><span class="sxs-lookup"><span data-stu-id="c33eb-165">\|E115\|RJ822371\|0\|\|</span></span>

    > [!NOTE]
    > <span data-ttu-id="c33eb-166">Como não há código da tabela 5.3, os registros C195, C197 e 0460 não são criados.</span><span class="sxs-lookup"><span data-stu-id="c33eb-166">Because there is no code from table 5.3, records C195, C197, and 0460 aren't created.</span></span>

<span data-ttu-id="c33eb-167">Para registrar o estorno de créditos e débitos, crie ajustes manuais no diário Ajuste geral de imposto/benefício/incentivo e adicione o código da tabela 5.2 ao campo **Descrição**.</span><span class="sxs-lookup"><span data-stu-id="c33eb-167">To register the reversal of credits and debits, create manual adjustments in the General tax adjustment/benefit/incentive journal, and add the code from table 5.2 to the **Description** field.</span></span>

<span data-ttu-id="c33eb-168">Veja alguns exemplos de transações de ajuste criadas automaticamente no SPED Fiscal:</span><span class="sxs-lookup"><span data-stu-id="c33eb-168">Here are some examples of adjustment transactions that are automatically created in SPED Fiscal:</span></span>

<span data-ttu-id="c33eb-169">\|E111\|RJ18003\|RJ822371\|\<Valor do ajuste\>\|</span><span class="sxs-lookup"><span data-stu-id="c33eb-169">\|E111\|RJ18003\|RJ822371\|\<Adjustment amount\>\|</span></span>

<span data-ttu-id="c33eb-170">\|E111\|RJ38003\|RJ822371\|\<Valor do ajuste\>\|</span><span class="sxs-lookup"><span data-stu-id="c33eb-170">\|E111\|RJ38003\|RJ822371\|\<Adjustment amount\>\|</span></span>

<span data-ttu-id="c33eb-171">\|E111\|RJ08006\|RJ822371\|\<Valor do ajuste\>\|</span><span class="sxs-lookup"><span data-stu-id="c33eb-171">\|E111\|RJ08006\|RJ822371\|\<Adjustment amount\>\|</span></span>

### <a name="deferral"></a><span data-ttu-id="c33eb-172">Diferimento</span><span class="sxs-lookup"><span data-stu-id="c33eb-172">Deferral</span></span>

<span data-ttu-id="c33eb-173">Durante o processo de sincronização, dois tipos de transações de ajuste são criados na apuração do imposto ICMS quando as seguintes condições são atendidas:</span><span class="sxs-lookup"><span data-stu-id="c33eb-173">During the synchronization process, two types of adjustment transactions are created in the ICMS tax assessment when the following conditions are met:</span></span>

- <span data-ttu-id="c33eb-174">Os documentos fiscais de saída emitidos pelo estado do RJ têm um código tributário de **51**.</span><span class="sxs-lookup"><span data-stu-id="c33eb-174">Outgoing fiscal documents that are issued from RJ state have a taxation code of **51**.</span></span>
- <span data-ttu-id="c33eb-175">Os códigos de benefícios da tabela 5.2 e da tabela 5.3 são atribuídos ao item e ao estado relacionados de uma nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="c33eb-175">The benefit codes from table 5.2 and table 5.3 are assigned to the related item and state of a fiscal document.</span></span> <span data-ttu-id="c33eb-176">Por exemplo, o código da tabela 5.2 é **RJ818317** e o código da tabela 5.3 é **RJ90980001**.</span><span class="sxs-lookup"><span data-stu-id="c33eb-176">For example, the code from table 5.2 is **RJ818317**, and the code from table 5.3 is **RJ90980001**.</span></span>

<span data-ttu-id="c33eb-177">Veja alguns exemplos de transações de ajuste criadas automaticamente no SPED Fiscal:</span><span class="sxs-lookup"><span data-stu-id="c33eb-177">Here are some examples of adjustment transactions that are automatically created in SPED Fiscal:</span></span>

- <span data-ttu-id="c33eb-178">O código de ajuste da tabela 5.2 gera um registro E115:</span><span class="sxs-lookup"><span data-stu-id="c33eb-178">The adjustment code from table 5.2 generates an E115 record:</span></span>

    <span data-ttu-id="c33eb-179">\|E115\|RJ818317\|0\|\|</span><span class="sxs-lookup"><span data-stu-id="c33eb-179">\|E115\|RJ818317\|0\|\|</span></span>

- <span data-ttu-id="c33eb-180">O código de ajuste da tabela 5.3 gera um registro C197:</span><span class="sxs-lookup"><span data-stu-id="c33eb-180">The adjustment code from table 5.3 generates a C197 record:</span></span>

    <span data-ttu-id="c33eb-181">\|C197\|RJ90980001\|RJ818317\|ItemId\|0,00\|0,00\|0,00\|6.585,36\|</span><span class="sxs-lookup"><span data-stu-id="c33eb-181">\|C197\|RJ90980001\|RJ818317\|ItemId\|0.00\|0.00\|0.00\|6585.36\|</span></span>

    > [!NOTE]
    > <span data-ttu-id="c33eb-182">Neste exemplo, o valor base é 30.000,00.</span><span class="sxs-lookup"><span data-stu-id="c33eb-182">In this example, the base amount is 30000.00.</span></span> <span data-ttu-id="c33eb-183">Portanto, o valor 6.585,36 é calculado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="c33eb-183">Therefore, the amount 6585.36 is calculated in the following way:</span></span>
    >
    > <span data-ttu-id="c33eb-184">30.000,00 ÷ (1 – 0,18) × 0,18</span><span class="sxs-lookup"><span data-stu-id="c33eb-184">30000.00 ÷ (1 – 0.18) × 0.18</span></span>

- <span data-ttu-id="c33eb-185">O código de observação atribuído ao item e estado relacionados da nota fiscal gera registros C195 e 0460:</span><span class="sxs-lookup"><span data-stu-id="c33eb-185">The observation code that is assigned to the related item and state of the fiscal document generates C195 and 0460 records:</span></span>

    <span data-ttu-id="c33eb-186">\|C195\|\<Código de observação\>\|\<Descrição do código de observação\>\|</span><span class="sxs-lookup"><span data-stu-id="c33eb-186">\|C195\|\<Observation code\>\|\<Observation code description\>\|</span></span>

    <span data-ttu-id="c33eb-187">\|0460\|\<Código de observação\>\|\<Descrição do código de observação\>\|</span><span class="sxs-lookup"><span data-stu-id="c33eb-187">\|0460\|\<Observation code\>\|\<Observation code description\>\|</span></span>

### <a name="enforceability-of-credit-reversal"></a><span data-ttu-id="c33eb-188">Aplicabilidade do estorno de crédito</span><span class="sxs-lookup"><span data-stu-id="c33eb-188">Enforceability of credit reversal</span></span>

<span data-ttu-id="c33eb-189">Durante o processo de sincronização, dois tipos de transações de ajuste são criados na apuração do imposto ICMS quando as seguintes condições são atendidas:</span><span class="sxs-lookup"><span data-stu-id="c33eb-189">During the synchronization process, two types of adjustment transactions are created the in ICMS tax assessment when the following conditions are met:</span></span>

- <span data-ttu-id="c33eb-190">Uma nota fiscal de saída emitida pelo estado do RJ tem um código de tributação de **40**.</span><span class="sxs-lookup"><span data-stu-id="c33eb-190">An outgoing fiscal document that is issued from RJ state has a taxation code of **40**.</span></span>
- <span data-ttu-id="c33eb-191">Os códigos de benefícios da tabela 5.2 e da tabela 5.3 são atribuídos ao item e ao estado relacionados da nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="c33eb-191">The benefit codes from table 5.2 and table 5.3 are assigned to the related item and state of the fiscal document.</span></span> <span data-ttu-id="c33eb-192">Por exemplo, o código da tabela 5.2 é **RJ801163** e o código da tabela 5.3 é **RJ90980000**.</span><span class="sxs-lookup"><span data-stu-id="c33eb-192">For example, the code from table 5.2 is **RJ801163**, and the code from table 5.3 is **RJ90980000**.</span></span>

<span data-ttu-id="c33eb-193">Veja alguns exemplos de transações de ajuste criadas automaticamente no SPED Fiscal:</span><span class="sxs-lookup"><span data-stu-id="c33eb-193">Here are some examples of adjustment transactions that are automatically created in SPED Fiscal:</span></span>

- <span data-ttu-id="c33eb-194">O código de ajuste da tabela 5.2 gera um registro E115:</span><span class="sxs-lookup"><span data-stu-id="c33eb-194">The adjustment code from table 5.2 generates an E115 record:</span></span>

    <span data-ttu-id="c33eb-195">\|E115\|RJ801163\|0\|\|</span><span class="sxs-lookup"><span data-stu-id="c33eb-195">\|E115\|RJ801163\|0\|\|</span></span>

- <span data-ttu-id="c33eb-196">O código de ajuste da tabela 5.3 gera um registro C197:</span><span class="sxs-lookup"><span data-stu-id="c33eb-196">The adjustment code from table 5.3 generates a C197 record:</span></span>

    <span data-ttu-id="c33eb-197">\|C197\|RJ90980000\|RJ801137\|ItemId\|0,00\|0,00\|0,00\|20\|</span><span class="sxs-lookup"><span data-stu-id="c33eb-197">\|C197\|RJ90980000\|RJ801137\|ItemId\|0.00\|0.00\|0.00\|20\|</span></span>

    > [!NOTE]
    > <span data-ttu-id="c33eb-198">Neste exemplo, o valor base é 200, o percentual de ICMS é 18 e a taxa do FCP é 0,02.</span><span class="sxs-lookup"><span data-stu-id="c33eb-198">In this example, the base amount is 200, the ICMS percentage is 18, and the FCP rate is 0.02.</span></span> <span data-ttu-id="c33eb-199">Portanto, o valor 20 é calculado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="c33eb-199">Therefore, the amount 20 is calculated in the following way:</span></span>
    >
    > <span data-ttu-id="c33eb-200">200 ÷ (1 – \[0,18 + 0,02\]) × (0,18 + 0,02)</span><span class="sxs-lookup"><span data-stu-id="c33eb-200">200 ÷ (1 – \[0.18 + 0.02\]) × (0.18 + 0.02)</span></span>

- <span data-ttu-id="c33eb-201">O código de observação atribuído ao item e estado relacionados da nota fiscal gera registros C195 e 0460:</span><span class="sxs-lookup"><span data-stu-id="c33eb-201">The observation code that is assigned to the related item and state of the fiscal document generates C195 and 0460 records:</span></span>

    <span data-ttu-id="c33eb-202">\|C195\|\<Código de observação\>\|\<Descrição do código de observação\>\|</span><span class="sxs-lookup"><span data-stu-id="c33eb-202">\|C195\|\<Observation code\>\|\<Observation code description\>\|</span></span>

    <span data-ttu-id="c33eb-203">\|0460\|\<Código de observação\>\|\<Descrição do código de observação\>\|</span><span class="sxs-lookup"><span data-stu-id="c33eb-203">\|0460\|\<Observation code\>\|\<Observation code description\>\|</span></span>

<span data-ttu-id="c33eb-204">Para registrar o estorno de créditos, crie ajustes manuais no diário Ajuste geral de imposto/benefício/incentivo e adicione o código da tabela 5.2 ao campo **Descrição**.</span><span class="sxs-lookup"><span data-stu-id="c33eb-204">To register the reversal of credits, create manual adjustments in the General tax adjustment/benefit/incentive journal, and add the code from table 5.2 to the **Description** field.</span></span>

<span data-ttu-id="c33eb-205">Veja um exemplo de uma transação de ajuste criada automaticamente no SPED Fiscal:</span><span class="sxs-lookup"><span data-stu-id="c33eb-205">Here is an example of an adjustment transaction that is automatically created in SPED Fiscal:</span></span>

<span data-ttu-id="c33eb-206">\|E111\|RJ18003\|RJ801163\|\<Valor do ajuste\>\|</span><span class="sxs-lookup"><span data-stu-id="c33eb-206">\|E111\|RJ18003\|RJ801163\|\<Adjustment amount\>\|</span></span>

### <a name="pass-on-or-transfer-a-tax-credit"></a><span data-ttu-id="c33eb-207">Transmitir ou transferir um crédito tributário</span><span class="sxs-lookup"><span data-stu-id="c33eb-207">Pass on or transfer a tax credit</span></span>

<span data-ttu-id="c33eb-208">Durante o processo de sincronização, dois tipos de transações de ajuste são criados na apuração do imposto ICMS quando as seguintes condições são atendidas:</span><span class="sxs-lookup"><span data-stu-id="c33eb-208">During the synchronization process, two types of adjustment transactions are created in the ICMS tax assessment when the following conditions are met:</span></span>

- <span data-ttu-id="c33eb-209">Uma nota fiscal de transferência ou apropriação de imposto de saída emitida pelo estado do RJ tem um código de tributação de **90**.</span><span class="sxs-lookup"><span data-stu-id="c33eb-209">An outgoing tax fiscal document that is issued from RJ state has a taxation code of **90**.</span></span>
- <span data-ttu-id="c33eb-210">Os códigos de benefício das tabelas 5.2 e 5.3 são atribuídos ao item/Código Fiscal de Operações e de Prestações (CFOP) e ao estado da nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="c33eb-210">The benefit codes from table 5.2 and table 5.3 are assigned to the related item/Código Fiscal de Operações e de Prestações (CFOP) and state of the fiscal document.</span></span> <span data-ttu-id="c33eb-211">Por exemplo, o código da tabela 5.2 é **RJ801163** e o código da tabela 5.3 é **RJ90980000**.</span><span class="sxs-lookup"><span data-stu-id="c33eb-211">For example, the code from table 5.2 is **RJ801163**, and the code from table 5.3 is **RJ90980000**.</span></span>

<span data-ttu-id="c33eb-212">Para registrar a reversão de créditos, o sistema cria automaticamente ajustes no diário Ajuste geral de imposto/benefício/incentivo e relaciona a linha do diário à nota fiscal de transferência ou apropriação de imposto.</span><span class="sxs-lookup"><span data-stu-id="c33eb-212">To register the reversal of credits, the system automatically creates adjustments in the General tax adjustment/benefit/incentive journal and relates the journal line to the tax fiscal document.</span></span>

<span data-ttu-id="c33eb-213">Veja alguns exemplos de transações de ajuste criadas automaticamente no SPED Fiscal para um remetente:</span><span class="sxs-lookup"><span data-stu-id="c33eb-213">Here are some examples of adjustment transactions that are automatically created in SPED Fiscal for a sender:</span></span>

<span data-ttu-id="c33eb-214">\|E115\|RJ821231\|0\|\|</span><span class="sxs-lookup"><span data-stu-id="c33eb-214">\|E115\|RJ821231\|0\|\|</span></span>

<span data-ttu-id="c33eb-215">\|C197\|RJ40080001\|RJ821231\|codigoitem\|0,00\|0,00\|\<Valor de imposto\>\|0,00\|</span><span class="sxs-lookup"><span data-stu-id="c33eb-215">\|C197\|RJ40080001\|RJ821231\|codigoitem\|0.00\|0.00\|\<Tax amount\>\|0.00\|</span></span>

<span data-ttu-id="c33eb-216">Veja alguns exemplos de transações de ajuste criadas automaticamente no SPED Fiscal para um destinatário:</span><span class="sxs-lookup"><span data-stu-id="c33eb-216">Here are some examples of adjustment transactions that are created automatically in SPED Fiscal for a recipient:</span></span>

<span data-ttu-id="c33eb-217">\|E115\|RJ821231\|0\|\|</span><span class="sxs-lookup"><span data-stu-id="c33eb-217">\|E115\|RJ821231\|0\|\|</span></span>

<span data-ttu-id="c33eb-218">\|C197\|RJ10080002\|RJ821231\|codigoitem\|0,00\|0,00\|\<Valor de imposto\>\|0,00\|</span><span class="sxs-lookup"><span data-stu-id="c33eb-218">\|C197\|RJ10080002\|RJ821231\|codigoitem\|0.00\|0.00\|\<Tax amount\>\|0.00\|</span></span>

## <a name="setup"></a><span data-ttu-id="c33eb-219">Configurar</span><span class="sxs-lookup"><span data-stu-id="c33eb-219">Setup</span></span>

### <a name="fiscal-books-parameters-per-state"></a><span data-ttu-id="c33eb-220">Parâmetros de livros fiscais por estado</span><span class="sxs-lookup"><span data-stu-id="c33eb-220">Fiscal books parameters per state</span></span>

<span data-ttu-id="c33eb-221">Siga estas etapas para configurar os parâmetros dos livros fiscais para cada estado.</span><span class="sxs-lookup"><span data-stu-id="c33eb-221">Follow these steps to set up Fiscal books parameters for each state.</span></span>

1. <span data-ttu-id="c33eb-222">Vá para **Livros fiscais** \> **Configurar** \> **Parâmetros de livros fiscais por estado**.</span><span class="sxs-lookup"><span data-stu-id="c33eb-222">Go to **Fiscal books** \> **Setup** \> **Fiscal books parameters per state**.</span></span>
2. <span data-ttu-id="c33eb-223">Na Guia Rápida **SPED Fiscal**, na seção **Resolução 13/2019**, defina a opção **Ajuste de nota fiscal** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="c33eb-223">On the **SPED Fiscal** FastTab, in the **Resolution 13/2019** section, set the **Document adjustment** option to **Yes**.</span></span> <span data-ttu-id="c33eb-224">O sistema agora processará ajustes de notas de acordo com a Resolução 13/2019.</span><span class="sxs-lookup"><span data-stu-id="c33eb-224">The system will now process document adjustments according to Resolution 13/2019.</span></span> <span data-ttu-id="c33eb-225">Se você não definir esta opção como **Sim**, os requisitos de resolução não serão aplicados.</span><span class="sxs-lookup"><span data-stu-id="c33eb-225">If you don't set this option to **Yes**, the resolution requirements won't be applied.</span></span>
3. <span data-ttu-id="c33eb-226">No campo **Nome**, digite o nome do diário Ajuste geral de imposto/benefício/incentivo.</span><span class="sxs-lookup"><span data-stu-id="c33eb-226">In the **Name** field, enter the name of the General tax adjustment/benefit/incentive journal.</span></span> <span data-ttu-id="c33eb-227">O sistema usa esse nome de diário quando um usuário deve realizar uma operação de transferência de ICMS para outro estabelecimento fiscal.</span><span class="sxs-lookup"><span data-stu-id="c33eb-227">The system uses this journal name when a user must do an ICMS transfer operation to another fiscal establishment.</span></span>

## <a name="benefit-code-per-item-or-state"></a><span data-ttu-id="c33eb-228">Código de benefício por item ou estado</span><span class="sxs-lookup"><span data-stu-id="c33eb-228">Benefit code per item or state</span></span>

1. <span data-ttu-id="c33eb-229">Vá para **Imposto** \> **Configurar** \> **Imposto** \> **Código de benefício por item/estado**.</span><span class="sxs-lookup"><span data-stu-id="c33eb-229">Go to **Tax** \> **Setup** \> **Sales tax** \> **Benefit code per Item/State**.</span></span>
2. <span data-ttu-id="c33eb-230">Configure **Código de ajuste 5.2**, **Código de ajuste 5.3** e **Código de observação**, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="c33eb-230">Set up **Adjustment code 5.2**, **Adjustment code 5.3**, and **Observation code** as required.</span></span>

<span data-ttu-id="c33eb-231">Essas configurações ajudam a garantir que você obtenha um SPED Fiscal correto de acordo com a resolução.</span><span class="sxs-lookup"><span data-stu-id="c33eb-231">These settings help guarantee that you get a correct SPED Fiscal according to the resolution.</span></span>

<span data-ttu-id="c33eb-232">Essas configurações são usadas para gerar automaticamente registros de ajuste de ICMS para uma linha de nota fiscal durante o lançamento e durante a operação de sincronização.</span><span class="sxs-lookup"><span data-stu-id="c33eb-232">These settings are used to automatically generate ICMS adjustment records for a fiscal document line during posting and during the Sync operation.</span></span>

## <a name="tax-fiscal-document"></a><span data-ttu-id="c33eb-233">Nota fiscal de transferência ou apropriação de imposto</span><span class="sxs-lookup"><span data-stu-id="c33eb-233">Tax fiscal document</span></span>

<span data-ttu-id="c33eb-234">Se a opção **Ajuste de nota fiscal** é definida como **Yes** na página **Parâmetros de livros fiscais por estado**, os usuários podem selecionar apenas um código de imposto sobre vendas que tenha um valor fiscal 3 na linha da nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="c33eb-234">If the **Document adjustment** option is set to **Yes** on the **Fiscal books parameters per state** page, users can select only a sales tax code that has a fiscal value of 3  on the tax fiscal document line.</span></span> <span data-ttu-id="c33eb-235">O código de tributação, relacionado ao código do imposto sobre vendas, tem um valor fiscal de 3, sem crédito/débito.</span><span class="sxs-lookup"><span data-stu-id="c33eb-235">The taxation code, as it's related to the sales tax code, has a fiscal value of 3, without credit/debit.</span></span> 

> [!NOTE]
> <span data-ttu-id="c33eb-236">Para o lançamento correto, a nota fiscal e o código de imposto selecionado devem ter as seguintes configurações de cálculo:</span><span class="sxs-lookup"><span data-stu-id="c33eb-236">For correct posting, the tax fiscal document and the selected sales tax code should have the following calculation settings:</span></span>
>
> - <span data-ttu-id="c33eb-237">**Origem:** percentual do valor líquido</span><span class="sxs-lookup"><span data-stu-id="c33eb-237">**Origin:** Percentage of net amount</span></span>
> - <span data-ttu-id="c33eb-238">**Base marginal:** valor líquido por linha</span><span class="sxs-lookup"><span data-stu-id="c33eb-238">**Marginal base:** Net amount per line</span></span>
> - <span data-ttu-id="c33eb-239">**Método de cálculo:** valor total</span><span class="sxs-lookup"><span data-stu-id="c33eb-239">**Calculation method:** Whole amount</span></span>

<span data-ttu-id="c33eb-240">Quando você lança uma nota fiscal tributária na qual um código de imposto está anexado à linha, o sistema não cria uma transação de comprovante.</span><span class="sxs-lookup"><span data-stu-id="c33eb-240">When you post a tax fiscal document where a sales tax code is attached to the line, the system doesn't create a voucher transaction.</span></span> <span data-ttu-id="c33eb-241">Quando você executa a operação de sincronização, o sistema cria e lança um diário Ajuste geral de imposto/benefício/incentivo relacionado à nota fiscal de transferência ou apropriação de imposto lançada para transferência do ICMS para outro estabelecimento fiscal.</span><span class="sxs-lookup"><span data-stu-id="c33eb-241">When you run the Sync operation, the system creates and posts a General tax/adjustment/benefit/incentive journal that is related to the posted tax fiscal document for ICMS transfer to another fiscal establishment.</span></span> <span data-ttu-id="c33eb-242">(Para executar a operação de sincronização, vá para **Livros fiscais** \> **Comum** \> **Período de escrituração** e selecione **Sincronização**.)</span><span class="sxs-lookup"><span data-stu-id="c33eb-242">(To run the Sync operation, go to **Fiscal books** \> **Common** \> **Booking period**, and then select **Sync**.)</span></span>

<span data-ttu-id="c33eb-243">O sistema preenche dados nas linhas do diário no perfil de lançamentos do código de ajuste 5.3.</span><span class="sxs-lookup"><span data-stu-id="c33eb-243">The system fills in data on the journal lines from the posting profile of adjustment code 5.3.</span></span> <span data-ttu-id="c33eb-244">Ele preenche o valor da nota fiscal de transferência ou apropriação de imposto.</span><span class="sxs-lookup"><span data-stu-id="c33eb-244">It fills in the amount from the tax fiscal document.</span></span>

> [!NOTE]
> <span data-ttu-id="c33eb-245">Antes de usar essa funcionalidade, configure o código de benefício por item/estado para transferência do ICMS, acessando **Imposto** \> **Configurar** \> **Imposto** \> **Código de benefício por item/estado**.</span><span class="sxs-lookup"><span data-stu-id="c33eb-245">Before you use this functionality, set up the benefit code per item/state for ICMS transfer by going to **Tax** \> **Setup** \> **Sales tax** \> **Benefit code per Item/ state**.</span></span> <span data-ttu-id="c33eb-246">De acordo com a resolução, os seguintes códigos de ajuste devem ser configurados para a transferência do ICMS:</span><span class="sxs-lookup"><span data-stu-id="c33eb-246">According to the resolution, the following adjustment codes should be set up for ICMS transfer:</span></span>
>
> - <span data-ttu-id="c33eb-247">**Para o remetente:** código de ajuste da tabela 5.2 = RJ821231 e código de ajuste da tabela 5.3 = RJ10080002</span><span class="sxs-lookup"><span data-stu-id="c33eb-247">**For the sender:** Adjustment code from table 5.2 = RJ821231, and adjustment code from table 5.3 = RJ10080002</span></span>
> - <span data-ttu-id="c33eb-248">**Para o destinatário:** código de ajuste da tabela 5.2 = RJ821231 e código de ajuste da tabela 5.3 = RJ10080002</span><span class="sxs-lookup"><span data-stu-id="c33eb-248">**For the recipient:** Adjustment code from table 5.2 = RJ821231, and adjustment code from table 5.3 = RJ10080002</span></span>

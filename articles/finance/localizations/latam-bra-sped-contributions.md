---
title: Definir contribuições SPED EFD
description: Este tópico explica como configurar parâmetros e gerar o SPED EFD — demonstrativo de contribuições para o Brasil.
author: sndray
manager: AnnBe
ms.date: 02/06/2020
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
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 9180356174da156b5f9b520a885c33a5bdcc985a
ms.sourcegitcommit: 9f90b194c0fc751d866d3d24d57ecf1b3c5053a1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/07/2020
ms.locfileid: "3033053"
---
# <a name="set-sped-efd-contributions"></a><span data-ttu-id="b8f9b-103">Definir contribuições SPED EFD</span><span class="sxs-lookup"><span data-stu-id="b8f9b-103">Set SPED EFD contributions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b8f9b-104">O SPED EFD — declaração de contribuições é gerado no módulo **Livros fiscais**.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-104">The SPED EFD - Contributions statement is generated in the **Fiscal books** module.</span></span> <span data-ttu-id="b8f9b-105">Ele reúne informações sobre o imposto de contribuição social sobre a receita bruta do PIS (programa de integração social) e a contribuição para financiamento de seguridade social (COFINS).</span><span class="sxs-lookup"><span data-stu-id="b8f9b-105">It gathers information about social contribution tax on gross revenue for the Social Integration Program (PIS) and the Contribution for Social Security Financing (COFINS).</span></span>

<span data-ttu-id="b8f9b-106">Siga estas etapas para configurar os requisitos para os arquivos de texto do SPED EFD – Contribuições.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-106">Follow these steps to set up the requirements for SPED EFD - Contributions text files.</span></span>

1. <span data-ttu-id="b8f9b-107">Selecione **Livros fiscais** \> **Configuração** \> **Parâmetros das extensões de obrigações fiscais**.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-107">Select **Fiscal books** \> **Setup** \> **Tax statements parameters**.</span></span>
2. <span data-ttu-id="b8f9b-108">Selecione **EFD - Contribuições** e, em seguida, na Guia Rápida **Parâmetros de configuração**, selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-108">Select **EFD - Contributions**, and then, on the **Setup parameters** FastTab, select **Open**.</span></span>

    <span data-ttu-id="b8f9b-109">A página **Parâmetros da EFD - Contribuições** será exibida, na qual você pode inserir as informações necessárias dos arquivos de texto do SPED EFD – Contribuições.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-109">The **EFD – Contributions parameters** page appears, where you can enter the required information for SPED EFD - Contributions text files.</span></span>

3. <span data-ttu-id="b8f9b-110">No campo **Tipo de atividade**, selecione o tipo de atividade:</span><span class="sxs-lookup"><span data-stu-id="b8f9b-110">In the **Type of activity** field, select the activity type:</span></span>

    - <span data-ttu-id="b8f9b-111">Industrial ou equivalente</span><span class="sxs-lookup"><span data-stu-id="b8f9b-111">Industrial or equivalent</span></span>
    - <span data-ttu-id="b8f9b-112">Prestador de serviços</span><span class="sxs-lookup"><span data-stu-id="b8f9b-112">Services</span></span>
    - <span data-ttu-id="b8f9b-113">Retail</span><span class="sxs-lookup"><span data-stu-id="b8f9b-113">Retail</span></span>
    - <span data-ttu-id="b8f9b-114">Atividade financeira</span><span class="sxs-lookup"><span data-stu-id="b8f9b-114">Financial activity</span></span>
    - <span data-ttu-id="b8f9b-115">Atividade imobiliária</span><span class="sxs-lookup"><span data-stu-id="b8f9b-115">Real estate activity</span></span>
    - <span data-ttu-id="b8f9b-116">Outros(as)</span><span class="sxs-lookup"><span data-stu-id="b8f9b-116">Others</span></span>

4. <span data-ttu-id="b8f9b-117">Defina a opção **Empresa grande** como **Sim** para identificar o tamanho da empresa.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-117">Set the **Large company** option to **Yes** to identify the size of company.</span></span> <span data-ttu-id="b8f9b-118">Esta opção é usada nas instruções SPED Reinf.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-118">This option is used in SPED REINF statements.</span></span>
5. <span data-ttu-id="b8f9b-119">No campo **Versão de layout**, selecione a versão do layout SPED EFD.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-119">In the **Layout version** field, select the version of the SPED EFD layout.</span></span> 
6. <span data-ttu-id="b8f9b-120">No campo **Tipo de entidade legal**, selecione o tipo de entidade legal.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-120">In the **Legal entity type** field, select the type of legal entity.</span></span>
7. <span data-ttu-id="b8f9b-121">No campo **Tipo de empresa**, selecione o tipo de empresa:</span><span class="sxs-lookup"><span data-stu-id="b8f9b-121">In the **Company type** field, select the type of company:</span></span>

    - <span data-ttu-id="b8f9b-122">PJ em geral</span><span class="sxs-lookup"><span data-stu-id="b8f9b-122">PJ in general</span></span>
    - <span data-ttu-id="b8f9b-123">PJ componente do sistema financeiro</span><span class="sxs-lookup"><span data-stu-id="b8f9b-123">PJ member of financial system</span></span>
    - <span data-ttu-id="b8f9b-124">Sociedades seguradoras ou de capitalização ou fundos de pensão complementares abertos</span><span class="sxs-lookup"><span data-stu-id="b8f9b-124">Insurance or capitalization societies or open-ended complementary pensions funds</span></span>

8. <span data-ttu-id="b8f9b-125">No campo **Natureza legal** , insira o código da natureza legal, de acordo com a tabela do SPED EFD.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-125">In the **Legal nature** field, enter the code for the legal nature, according to the SPED EFD table.</span></span>
9. <span data-ttu-id="b8f9b-126">Definir a opção **CPRB** como **Sim** para habilitar a apuração do imposto CPRB.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-126">Set the **CPRB** option to **Yes** to enable CPRB tax assessment.</span></span> <span data-ttu-id="b8f9b-127">Esta opção é usada nas instruções SPED Reinf.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-127">This option is used in SPED REINF statements.</span></span>
10. <span data-ttu-id="b8f9b-128">No campo **Código de classificação de imposto** , selecione o código de classificação de imposto.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-128">In the **Tax classification code** field, select the tax classification code.</span></span> <span data-ttu-id="b8f9b-129">Este campo é usado nas instruções SPED Reinf.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-129">This field is used in SPED REINF statements.</span></span>
11. <span data-ttu-id="b8f9b-130">Defina a opção **Acordo internacional para a isenção de multas** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-130">Set the **International agreement for exemption of fines** option to **Yes**.</span></span>
12. <span data-ttu-id="b8f9b-131">No campo **Regime de apuração**, selecione o esquema de apuração usado para SPED EFD – Contribuições:</span><span class="sxs-lookup"><span data-stu-id="b8f9b-131">In the **Assessment regimen** field, select the assessment schema that is used for SPED EFD - Contributions:</span></span>

    - <span data-ttu-id="b8f9b-132">**Não cumulativo** – Calcula as apurações com base em faturamentos ou débitos e compras e deduções e créditos.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-132">**Non cumulative** – Calculate assessments based on billings or debits and purchases and deductions or credits.</span></span>
    - <span data-ttu-id="b8f9b-133">**Cumulativo** – Calcula as apurações com base em faturamentos que não tenham deduções ou créditos.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-133">**Cumulative** – Calculate assessments based on billings that don't have any deductions or credits.</span></span>
    - <span data-ttu-id="b8f9b-134">**Ambos** – Calcula as apurações com base em regimes **Não cumulativo** e **Cumulativo** .</span><span class="sxs-lookup"><span data-stu-id="b8f9b-134">**Both** – Calculate assessments based on both the **Non cumulative** and **Cumulative** regimens.</span></span>

13. <span data-ttu-id="b8f9b-135">No campo , **Critério de escrituração e apuração**, selecione os critérios a serem usados para registrar o crédito fiscal.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-135">In the **Booking and assessment criteria** field, select the criteria to use to book the tax credit.</span></span>
14. <span data-ttu-id="b8f9b-136">No campo **Tipo de contribuição apurada** , selecione o tipo de contribuição apurada.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-136">In the **Type of assessment contribution** field, select the type of assessment contribution.</span></span>
15. <span data-ttu-id="b8f9b-137">No campo **Método de apropriação de créditos**, selecione o método de alocação de crédito:</span><span class="sxs-lookup"><span data-stu-id="b8f9b-137">In the **Credit allocation method** field, select the method of credit allocation:</span></span>

    - <span data-ttu-id="b8f9b-138">Direto</span><span class="sxs-lookup"><span data-stu-id="b8f9b-138">Direct</span></span>
    - <span data-ttu-id="b8f9b-139">Distribuição proporcional</span><span class="sxs-lookup"><span data-stu-id="b8f9b-139">Proportional distribution</span></span>

    <span data-ttu-id="b8f9b-140">Este campo está disponível somente se você selecionou **Não cumulativo** ou **Ambos** no campo **Regime de apuração** .</span><span class="sxs-lookup"><span data-stu-id="b8f9b-140">This field is available only if you selected **Non cumulative** or **Both** in the **Assessment regimen** field.</span></span>

16. <span data-ttu-id="b8f9b-141">No campo **Opções de NFe e ECF**, selecione a opção de relatório para transações de NFe:</span><span class="sxs-lookup"><span data-stu-id="b8f9b-141">In the **NFe and ECF options** field, select the reporting option for NFe transactions:</span></span>

    - <span data-ttu-id="b8f9b-142">**Consolidado** – Consolida todas as transações de NF-e em um registro no relatório fiscal C18X.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-142">**Consolidated** – Consolidate all NFe transactions into one record on the C18X fiscal report.</span></span>
    - <span data-ttu-id="b8f9b-143">**Detalhado** Lista todas as transações individuais no relatório fiscal.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-143">**Detailed** – List all individual transactions on the fiscal report.</span></span>

17. <span data-ttu-id="b8f9b-144">Na Guia Rápida **Estabelecimento fiscal** , insira as informações necessárias de SPED ECD.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-144">On the **Fiscal establishment** FastTab, enter the required SPED ECD information.</span></span>
18. <span data-ttu-id="b8f9b-145">Na guia **Regra para código de tributação**, selecione o código de tributação e o valor fiscal para evitar que os registros C100 e D100 sejam gerados.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-145">On the **Rule for taxation code** FastTab, select the taxation code and fiscal value to prevent records C100 and D100 from being generated.</span></span>

## <a name="special-requirements-for-layout-version-006-and-later"></a><span data-ttu-id="b8f9b-146">Requisitos especiais para a versão de layout 006 e posterior</span><span class="sxs-lookup"><span data-stu-id="b8f9b-146">Special requirements for layout version 006 and later</span></span>

### <a name="record-0900"></a><span data-ttu-id="b8f9b-147">Registro 0900</span><span class="sxs-lookup"><span data-stu-id="b8f9b-147">Record 0900</span></span>

<span data-ttu-id="b8f9b-148">O registro 0900 nos arquivos de texto SPED EFD - contribuições é gerado automaticamente para fornecer detalhes sobre a composição de receita para o período de reserva especificado.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-148">Record 0900 in the SPED EFD - Contributions text files is automatically generated to provide details about the revenue composition for the specified booking period.</span></span> <span data-ttu-id="b8f9b-149">A geração deste registro é obrigatória quando o arquivo do SPED EFD - contribuições original é transmitido após o período de entrega regular (isto é, após o décimo dia útil do segundo mês do período de reserva).</span><span class="sxs-lookup"><span data-stu-id="b8f9b-149">Generation of this record is mandatory when the original SPED EFD - Contributions file is transmitted after the regular delivery time (that is, after the tenth working day of the second month of the booking period).</span></span>

<span data-ttu-id="b8f9b-150">O registro gerado está disponível no layout versão 006 e posterior.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-150">The generated record is available in layout version 006 and later.</span></span> <span data-ttu-id="b8f9b-151">Selecione esta opção quando o arquivo SPED EFD - Contribuições for executado.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-151">Select this option when the SPED EFD - Contributions file is run.</span></span>

### <a name="m410-pis-and-m810-cofins"></a><span data-ttu-id="b8f9b-152">M410 (PIS) e M810 (COFINS)</span><span class="sxs-lookup"><span data-stu-id="b8f9b-152">M410 (PIS) and M810 (COFINS)</span></span>

<span data-ttu-id="b8f9b-153">Os registros M410 e M810 nos arquivos de texto do SPED EFD - contribuições são gerados automaticamente para transações de receita nas quais um valor fiscal é definido como **2:Isento** ou **3:sem débito/crédito**.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-153">Records M410 and M810 in the SPED EFD - Contributions text files are automatically generated for revenue transactions where a fiscal value is set to **2:Exempt** or **3:without debit/credit**.</span></span>

<span data-ttu-id="b8f9b-154">A implementação do layout versão 006 altera a forma como o campo 02 (**NAT\_REC**) é determinado.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-154">The implementation of layout version 006 changes the way that field 02 (**NAT\_REC**) is determined.</span></span> <span data-ttu-id="b8f9b-155">Nessa versão de layout, será usada uma configuração adicional.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-155">In this layout version, an additional configuration is used.</span></span> <span data-ttu-id="b8f9b-156">Nas versões de layout anteriores, foram usados valores fixos específicos.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-156">In previous layout versions, specific fixed values were used.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b8f9b-157">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="b8f9b-157">Prerequisites</span></span>

<span data-ttu-id="b8f9b-158">Antes de gerar as avaliações de imposto PIS e COFINS e habilitar a geração de registros M410 e M810 que têm a determinação da fonte de receita correta, vá para **Livros fiscais** \> **Configuração** \> **Tabelas de PIS e COFINS** \> **Código de fontes de receita** e selecione os seguintes parâmetros.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-158">Before you generate PIS and COFINS tax assessments and enable the generation of records M410 and M810 that have the correct revenue source determination, go to **Fiscal books** \> **Setup** \> **PIS and COFINS tables** \> **Revenue sources code**, and select the following parameters.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="b8f9b-159">Campo</span><span class="sxs-lookup"><span data-stu-id="b8f9b-159">Field</span></span></th>
<th><span data-ttu-id="b8f9b-160">Descrição</span><span class="sxs-lookup"><span data-stu-id="b8f9b-160">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="b8f9b-161">Tipo da fonte de receita</span><span class="sxs-lookup"><span data-stu-id="b8f9b-161">Revenue source type</span></span></td>
<td><span data-ttu-id="b8f9b-162">Selecione o tipo de fonte de receita, de acordo com o relacionamento incluído nas tabelas que fornecem detalhes sobre a natureza da receita por situação fiscal (por exemplo, tabelas 4.3.10 e 4.3.11).</span><span class="sxs-lookup"><span data-stu-id="b8f9b-162">Select the type of revenue source, according to the relationship that is included in the tables that provide details about the nature of revenue by tax situation (for example, tables 4.3.10 and 4.3.11).</span></span> <span data-ttu-id="b8f9b-163">Essas tabelas são publicadas pela autoridade fiscal.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-163">These tables are published by the tax authority.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b8f9b-164">Código da fonte de receita</span><span class="sxs-lookup"><span data-stu-id="b8f9b-164">Revenue source code</span></span></td>
<td><span data-ttu-id="b8f9b-165">Insira o código para a fonte de receita.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-165">Enter the code for the revenue source.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b8f9b-166">Descrição</span><span class="sxs-lookup"><span data-stu-id="b8f9b-166">Description</span></span></td>
<td><span data-ttu-id="b8f9b-167">Inserir uma descrição do código da fonte de receita.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-167">Enter a description of the revenue source code.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b8f9b-168">Data inicial e final de validade</span><span class="sxs-lookup"><span data-stu-id="b8f9b-168">Valid from and to date</span></span></td>
<td><span data-ttu-id="b8f9b-169">Insira as datas em que a fonte de receita é aplicável.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-169">Enter the dates when this revenue source is applicable.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="b8f9b-170">Vá para **Livros fiscais** \> **Configuração** \> **Tabelas de PIS e COFINS** \> **Fonte de receita por item** para configurar a determinação da fonte de receita.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-170">Go to **Fiscal books** \> **Setup** \> **PIS and COFINS tables** \> **Revenue source per item** to set up the revenue source determination.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="b8f9b-171">Campo</span><span class="sxs-lookup"><span data-stu-id="b8f9b-171">Field</span></span></th>
<th><span data-ttu-id="b8f9b-172">Descrição</span><span class="sxs-lookup"><span data-stu-id="b8f9b-172">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="b8f9b-173">Código do item</span><span class="sxs-lookup"><span data-stu-id="b8f9b-173">Item code</span></span></td>
<td><span data-ttu-id="b8f9b-174">Especifique se a determinação da fonte de receita se aplica a um código de item, um grupo de itens ou todos os itens:</span><span class="sxs-lookup"><span data-stu-id="b8f9b-174">Specify whether the revenue source determination applies to an item code, a group of items, or all items:</span></span>
<ul>
<li><span data-ttu-id="b8f9b-175"><strong>Tabela</strong> – a receita de origem se aplica a um único código de item.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-175"><strong>Table</strong> – The source revenue applies to a single item code.</span></span> <span data-ttu-id="b8f9b-176">Se você selecionar esta opção, selecione o código de item, no campo <strong>Relação de item</strong>.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-176">If you select this option, select the item code in the <strong>Item relation</strong> field.</span></span></li>
<li><span data-ttu-id="b8f9b-177"><strong>Grupo</strong> – a receita de origem se aplica a um grupo de itens.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-177"><strong>Group</strong> – The source revenue applies to an item group.</span></span> <span data-ttu-id="b8f9b-178">Se você selecionar esta opção, selecione o grupo de itens, no campo <strong>Relação de item</strong>.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-178">If you select this option, select the item group in the <strong>Item relation</strong> field.</span></span></li>
<li><span data-ttu-id="b8f9b-179"><strong>Tudo</strong> – a receita de origem se aplica a todos os itens.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-179"><strong>All</strong> – The source revenue applies to all items.</span></span> <span data-ttu-id="b8f9b-180">Se você selecionar essa opção, deixe o campo <strong>Relação de item</strong> em branco.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-180">If you select this option, leave the <strong>Item relation</strong> field blank.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="b8f9b-181">Relação de item</span><span class="sxs-lookup"><span data-stu-id="b8f9b-181">Item relation</span></span></td>
<td><span data-ttu-id="b8f9b-182">Se você selecionou <strong>Tabela</strong> no campo <strong>Código de item</strong>, selecione o código de item associado à fonte de receita.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-182">If you selected <strong>Table</strong> in the <strong>Item code</strong> field, select the item code that is associated with the revenue source.</span></span> <span data-ttu-id="b8f9b-183">Se você selecionou <strong>Grupo</strong>, escolha um grupo de itens.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-183">If you selected <strong>Group</strong>, select an item group.</span></span> <span data-ttu-id="b8f9b-184">Se selecionou <strong>Todos</strong>, deixe este campo em branco.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-184">If you selected <strong>All</strong>, leave this field blank.</span></span></td>
</tr>
</tbody>
</table>

## <a name="generate-a-sped-efd---contributions-text-file"></a><span data-ttu-id="b8f9b-185">Gerar um arquivo de texto SPED EFD - Contribuições</span><span class="sxs-lookup"><span data-stu-id="b8f9b-185">Generate a SPED EFD - Contributions text file</span></span>

1. <span data-ttu-id="b8f9b-186">Vá para **Livros fiscais** \> **Comum** \> **Período de reserva**.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-186">Go to **Fiscal books** \> **Common** \> **Booking period**.</span></span>
2. <span data-ttu-id="b8f9b-187">Selecione o período de reserva relacionado e selecione **Obrigações fiscais** \> **Contribuições EFD** \> **Executar**.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-187">Select the related booking period, and then select **Tax statements** \> **EFD Contributions** \> **Execute**.</span></span>
3. <span data-ttu-id="b8f9b-188">No campo **Tipo de situação**, selecione o tipo de situação.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-188">In the **Type of situation** field, select the type of situation.</span></span>
4. <span data-ttu-id="b8f9b-189">No campo **Tipo de arquivo**, selecione **Original** ou **Substituto**.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-189">In the **File type** field, select **Original** or **Substitute**.</span></span>
5. <span data-ttu-id="b8f9b-190">No campo **Versão do layout**, selecione a última versão disponível.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-190">In the **Layout version** field, select the latest version that is available.</span></span>
6. <span data-ttu-id="b8f9b-191">No campo **Motivo da identificação**, selecione a identificação relacionada.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-191">In the **Identification reason** field, select the related identification.</span></span>
7. <span data-ttu-id="b8f9b-192">Defina a opção **Envio atrasado** como **Sim** para gerar o registro 0900.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-192">Set the **Late submission** option to **Yes** to generate record 0900.</span></span>

> [!NOTE]
> <span data-ttu-id="b8f9b-193">Para usar o processamento em lotes, selecione **Lote** e especifique as opções para a execução do processamento em lotes.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-193">To use batch processing, select **Batch**, and then specify the options for batch processing execution.</span></span> <span data-ttu-id="b8f9b-194">Você poderá usar o processamento em lotes se o arquivo precisar ser gerado posteriormente ou se precisar ser gerado em um servidor, e não no computador.</span><span class="sxs-lookup"><span data-stu-id="b8f9b-194">You might use batch processing if the file should be generated later, or if it should be generated on a server instead of on your computer.</span></span>

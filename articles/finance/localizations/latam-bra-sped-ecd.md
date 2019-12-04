---
title: SPED ECD
description: Este tópico explica como configurar e gerar arquivos de texto do SPED ECD.
author: ShylaThompson
manager: AnnBe
ms.date: 08/27/2018
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
ms.openlocfilehash: 59320a415eb2d6e5b04a9c8fac8177a0c618051e
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2175190"
---
# <a name="sped-ecd"></a><span data-ttu-id="3859e-103">SPED ECD</span><span class="sxs-lookup"><span data-stu-id="3859e-103">SPED ECD</span></span>

[!include [banner](../includes/banner.md)]

## <a name="set-up-parameters-for-sped-ecd-text-files"></a><span data-ttu-id="3859e-104">Configurar os parâmetros de arquivos de texto fiscais do SPED ECD</span><span class="sxs-lookup"><span data-stu-id="3859e-104">Set up parameters for SPED ECD text files</span></span>

<span data-ttu-id="3859e-105">Esta seção explica como especificar a forma como os arquivos de texto fiscais do Sistema Publico de Escrituração Digital (SPED) devem ser salvos antes de você enviá-los às autoridades fiscais federais.</span><span class="sxs-lookup"><span data-stu-id="3859e-105">This section explains how to specify how Sistema Publico de Escrituração Digital (SPED) fiscal text files should be saved before you submit them to the federal tax authorities.</span></span>

<span data-ttu-id="3859e-106">Os arquivos fiscais de texto do SPED contêm informações sobre transações de contabilidade, informações de lucros e perdas, e informações de balanço.</span><span class="sxs-lookup"><span data-stu-id="3859e-106">The SPED fiscal text files contain information about general ledger transactions, profit and loss information, and balance sheet information.</span></span> <span data-ttu-id="3859e-107">As autoridades de imposto federal usam o sistema Contábil de Escrituração Digital (ECD) do SPED para verificar os lucros tributáveis da empresa.</span><span class="sxs-lookup"><span data-stu-id="3859e-107">The federal tax authorities use the SPED Escrituração Contábil Digital (ECD) system to verify taxable a company's profits.</span></span> 

### <a name="set-up-requirements-for-the-sped-ecd-tax-statement"></a><span data-ttu-id="3859e-108">Configurar requisitos para a declaração de imposto SPED ECD</span><span class="sxs-lookup"><span data-stu-id="3859e-108">Set up requirements for the SPED ECD tax statement</span></span>

<span data-ttu-id="3859e-109">Para configurar os requisitos para os arquivos de texto fiscais do SPED ECD, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="3859e-109">To set up requirements for SPED ECD fiscal text files, follow these steps.</span></span>

1.  <span data-ttu-id="3859e-110">Selecione **Livros fiscais** \> **Configuração** \> **Parâmetros das extensões de obrigações fiscais**.</span><span class="sxs-lookup"><span data-stu-id="3859e-110">Select **Fiscal books** \> **Setup** \> **Tax statements parameters**.</span></span>
2.  <span data-ttu-id="3859e-111">Selecione **SPED ECD** à esquerda e, em seguida, na Guia Rápida **Parâmetros de configuração**, selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="3859e-111">Select **SPED ECD** on the left, and then, on the **Setup parameters** FastTab, select **Open**.</span></span>
3.  <span data-ttu-id="3859e-112">Selecione a empresa para a qual gerar o arquivo de texto do SPED ECD.</span><span class="sxs-lookup"><span data-stu-id="3859e-112">Select the company to generate the SPED ECD text file for.</span></span>
4.  <span data-ttu-id="3859e-113">Selecione o conjunto de dimensões financeiras na qual o formato de arquivo de texto do SPED ECD deve se basear.</span><span class="sxs-lookup"><span data-stu-id="3859e-113">Select the financial dimension set that the format of the SPED ECD text file should be based on.</span></span> <span data-ttu-id="3859e-114">O conjunto de dimensões financeiras deve incluir a conta principal e as dimensões de centro de custo.</span><span class="sxs-lookup"><span data-stu-id="3859e-114">The financial dimension set should include the main account and the cost center dimensions.</span></span>
5.  <span data-ttu-id="3859e-115">Selecione o local onde o arquivo de texto do SPED ECD deve ser gerado.</span><span class="sxs-lookup"><span data-stu-id="3859e-115">Select the location where the SPED ECD text file should be generated.</span></span>

    <span data-ttu-id="3859e-116">O tipo de registro é atribuído automaticamente com base no tipo da organização fiscal:</span><span class="sxs-lookup"><span data-stu-id="3859e-116">The booking type is assigned automatically, based on the type of fiscal organization:</span></span>

    -  <span data-ttu-id="3859e-117">**G** – O registro é usado para todas as transações do diário do razão.</span><span class="sxs-lookup"><span data-stu-id="3859e-117">**G** – The booking is used for all the ledger journal transactions.</span></span>
    -  <span data-ttu-id="3859e-118">**S** – O registro é usado para a empresa SCP.</span><span class="sxs-lookup"><span data-stu-id="3859e-118">**S** – The booking is used for the SCP company.</span></span>

6.  <span data-ttu-id="3859e-119">Selecione o tipo de situação da empresa.</span><span class="sxs-lookup"><span data-stu-id="3859e-119">Select the type of company situation.</span></span> <span data-ttu-id="3859e-120">As opções a seguir estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="3859e-120">The following options are available.</span></span> <span data-ttu-id="3859e-121">Alternativamente, deixe o campo em branco para representar a situação normal.</span><span class="sxs-lookup"><span data-stu-id="3859e-121">Alternatively, leave the field blank to represent the regular situation.</span></span>

    -  <span data-ttu-id="3859e-122">Divisão</span><span class="sxs-lookup"><span data-stu-id="3859e-122">Division</span></span>
    -  <span data-ttu-id="3859e-123">Fusão</span><span class="sxs-lookup"><span data-stu-id="3859e-123">Merger</span></span>
    -  <span data-ttu-id="3859e-124">Corporação</span><span class="sxs-lookup"><span data-stu-id="3859e-124">Incorporation</span></span>
    -  <span data-ttu-id="3859e-125">Fechamento</span><span class="sxs-lookup"><span data-stu-id="3859e-125">Closing-down</span></span>
    -  <span data-ttu-id="3859e-126">Transformação</span><span class="sxs-lookup"><span data-stu-id="3859e-126">Transformation</span></span>

7.  <span data-ttu-id="3859e-127">No campo **Período fiscal de abertura**, selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="3859e-127">In the **Opening fiscal period** field, select one of the following options:</span></span>

    -  <span data-ttu-id="3859e-128">Normal</span><span class="sxs-lookup"><span data-stu-id="3859e-128">Regular</span></span>
    -  <span data-ttu-id="3859e-129">Abertura</span><span class="sxs-lookup"><span data-stu-id="3859e-129">Opening</span></span>
    -  <span data-ttu-id="3859e-130">Divisão, Fusão ou Aquisição</span><span class="sxs-lookup"><span data-stu-id="3859e-130">Split, Merge or Acquisition</span></span>
    -  <span data-ttu-id="3859e-131">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="3859e-131">Mandatory</span></span>

8.  <span data-ttu-id="3859e-132">Selecione a versão do formato de arquivo de texto fiscal do SPED ECD a ser gerado.</span><span class="sxs-lookup"><span data-stu-id="3859e-132">Select the version of the SPED ECD text file format to generate.</span></span>
9.  <span data-ttu-id="3859e-133">No campo **Número de inscrição do auditor**, insira o número do auditor da empresa.</span><span class="sxs-lookup"><span data-stu-id="3859e-133">In the **Auditor registration number** field, enter the number of the company's auditor.</span></span>
10. <span data-ttu-id="3859e-134">Insira o nome do auditor.</span><span class="sxs-lookup"><span data-stu-id="3859e-134">Enter the auditor's name.</span></span>
11. <span data-ttu-id="3859e-135">Defina a opção **Empresa de grande porte** como **Sim** se a empresa for de grande porte.</span><span class="sxs-lookup"><span data-stu-id="3859e-135">Set the **Large company** option to **Yes** if the company is a large company.</span></span>

## <a name="generate-and-validate-the-sped-ecd-statement"></a><span data-ttu-id="3859e-136">Gere e valide o demonstrativo ECD SPED</span><span class="sxs-lookup"><span data-stu-id="3859e-136">Generate and validate the SPED ECD statement</span></span> 

<span data-ttu-id="3859e-137">Esta seção explica como gerar e validar o arquivo de texto para a contabilidade digital (SPED ECD).</span><span class="sxs-lookup"><span data-stu-id="3859e-137">This section explains how to generate and validate the text file for the digital accounting bookkeeping (SPED ECD) statement.</span></span>

<span data-ttu-id="3859e-138">Para o demonstrativo SPED ECD, as organizações devem calcular e informar os lucros tributáveis com base nos seguintes tipos de registros da contabilidade:</span><span class="sxs-lookup"><span data-stu-id="3859e-138">For the SPED ECD statement, organizations must calculate and report on their taxable profits, based on the following types of accounting records:</span></span>

- <span data-ttu-id="3859e-139">Registros de diário e registros de suporte</span><span class="sxs-lookup"><span data-stu-id="3859e-139">Journal registers and supporting records</span></span>
- <span data-ttu-id="3859e-140">Contabilidade e sub-razões</span><span class="sxs-lookup"><span data-stu-id="3859e-140">General ledger and subledgers</span></span>
- <span data-ttu-id="3859e-141">Balancetes e balanços diários</span><span class="sxs-lookup"><span data-stu-id="3859e-141">Daily trial balances and balance sheets</span></span>

### <a name="generate-and-validate-a-sped-ecd-text-file"></a><span data-ttu-id="3859e-142">Gerenciar e validar um arquivo de texto SPED ECD</span><span class="sxs-lookup"><span data-stu-id="3859e-142">Generate and validate a SPED ECD text file</span></span>

<span data-ttu-id="3859e-143">Para gerar e validar o arquivo de texto para o demonstrativo SPED ECD, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="3859e-143">To generate and validate the text file for the SPED ECD statement, follow these steps.</span></span>

1.  <span data-ttu-id="3859e-144">Selecione **Livros fiscais** \> **Comum** \> **SPED ECD** \> **Gerar o SPED ECD**.</span><span class="sxs-lookup"><span data-stu-id="3859e-144">Select **Fiscal books** \> **Common** \> **SPED ECD** \> **Generate SPED ECD**.</span></span>
2.  <span data-ttu-id="3859e-145">Selecione a organização fiscal para a qual será gerado o arquivo SPED ECD.</span><span class="sxs-lookup"><span data-stu-id="3859e-145">Select the fiscal organization to generate the SPED ECD file for.</span></span>
3.  <span data-ttu-id="3859e-146">Nos campos **Data inicial** e **Data Final** selecione as datas de início e de término das transações do razão incluídas no relatório.</span><span class="sxs-lookup"><span data-stu-id="3859e-146">In the **From date** and **To date** fields, select the start and end dates of the ledger transactions to report on.</span></span>
4.  <span data-ttu-id="3859e-147">Defina a opção **Incluir demonstrativos contábeis** como **Sim** para gerar o arquivo de texto do Bloco J, além do arquivo SPED ECD.</span><span class="sxs-lookup"><span data-stu-id="3859e-147">Set the **Include accounting statements** option to **Yes** to generate the Block J text file in addition to the SPED ECD file.</span></span>
5.  <span data-ttu-id="3859e-148">Selecione o período de cálculo de saldos de demonstrativo financeiro.</span><span class="sxs-lookup"><span data-stu-id="3859e-148">Select the period to calculate financial statement balances for.</span></span>
6.  <span data-ttu-id="3859e-149">Insira o caminho no qual os arquivos devem ser salvos.</span><span class="sxs-lookup"><span data-stu-id="3859e-149">Enter the path where the files should be saved.</span></span>
7.  <span data-ttu-id="3859e-150">No campo **Número do livro**, insira o número do livro contábil.</span><span class="sxs-lookup"><span data-stu-id="3859e-150">In the **Book number** field, enter the accounting book number.</span></span>

    <span data-ttu-id="3859e-151">O campo **Tipo de escrituração** é definido automaticamente como **G** (Livro Diário completo sem escrituração auxiliar).</span><span class="sxs-lookup"><span data-stu-id="3859e-151">The **Booking type** field is automatically set to **G** (Livro Diario completo sem escrituracao auxiliary).</span></span>

8.  <span data-ttu-id="3859e-152">Selecione o tipo de situação da empresa.</span><span class="sxs-lookup"><span data-stu-id="3859e-152">Select the type of company situation.</span></span> <span data-ttu-id="3859e-153">As opções a seguir estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="3859e-153">The following options are available.</span></span> <span data-ttu-id="3859e-154">Alternativamente, deixe o campo em branco para representar a situação normal.</span><span class="sxs-lookup"><span data-stu-id="3859e-154">Alternatively, leave the field blank to represent the regular situation.</span></span>

    -  <span data-ttu-id="3859e-155">Divisão</span><span class="sxs-lookup"><span data-stu-id="3859e-155">Division</span></span>
    -  <span data-ttu-id="3859e-156">Fusão</span><span class="sxs-lookup"><span data-stu-id="3859e-156">Merger</span></span>
    -  <span data-ttu-id="3859e-157">Corporação</span><span class="sxs-lookup"><span data-stu-id="3859e-157">Incorporation</span></span>
    -  <span data-ttu-id="3859e-158">Fechamento</span><span class="sxs-lookup"><span data-stu-id="3859e-158">Closing-down</span></span>
    -  <span data-ttu-id="3859e-159">Transformação</span><span class="sxs-lookup"><span data-stu-id="3859e-159">Transformation</span></span>

9.  <span data-ttu-id="3859e-160">No campo **Período fiscal de abertura**, selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="3859e-160">In the **Opening fiscal period** field, select one of the following options:</span></span>

    -  <span data-ttu-id="3859e-161">Normal</span><span class="sxs-lookup"><span data-stu-id="3859e-161">Regular</span></span>
    -  <span data-ttu-id="3859e-162">Abertura</span><span class="sxs-lookup"><span data-stu-id="3859e-162">Opening</span></span>
    -  <span data-ttu-id="3859e-163">Divisão, Fusão ou Aquisição</span><span class="sxs-lookup"><span data-stu-id="3859e-163">Split, Merge or Acquisition</span></span>
    -  <span data-ttu-id="3859e-164">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="3859e-164">Mandatory</span></span>

10. <span data-ttu-id="3859e-165">No campo **Versão de layout**, selecione o layout do arquivo SPED ECD.</span><span class="sxs-lookup"><span data-stu-id="3859e-165">In the **Layout version** field, select the layout of the SPED ECD file.</span></span>
11. <span data-ttu-id="3859e-166">No campo **Tipo de arquivo**, selecione o tipo de arquivo a ser gerado:</span><span class="sxs-lookup"><span data-stu-id="3859e-166">In the **File type** field, select the type of file to generate:</span></span>

    -  <span data-ttu-id="3859e-167">Original</span><span class="sxs-lookup"><span data-stu-id="3859e-167">Original</span></span>
    -  <span data-ttu-id="3859e-168">Substituto com NIRE</span><span class="sxs-lookup"><span data-stu-id="3859e-168">Substitute with NIRE</span></span>
    -  <span data-ttu-id="3859e-169">Substituto sem NIRE</span><span class="sxs-lookup"><span data-stu-id="3859e-169">Substitute without NIRE</span></span>
    -  <span data-ttu-id="3859e-170">Substituto com alterações de NIRE</span><span class="sxs-lookup"><span data-stu-id="3859e-170">Substitute with NIRE changes</span></span>

    <span data-ttu-id="3859e-171">O Número de Identificação no Registro de Empresas (NIRE) é inserido na página **Estabelecimento fiscal** na guia rápida **Registro de imposto**.</span><span class="sxs-lookup"><span data-stu-id="3859e-171">The Número de Identificação no Registro de Empresas (NIRE) is entered on the **Tax registration** FastTab of the **Fiscal establishment** page.</span></span>

12. <span data-ttu-id="3859e-172">Selecione **OK** para gerar o arquivo SPED ECD.</span><span class="sxs-lookup"><span data-stu-id="3859e-172">Select **OK** to generate the SPED ECD file.</span></span>
13. <span data-ttu-id="3859e-173">Selecione **Livros fiscais** \> **Comum** \> **SPED ECD** \> **Validar o SPED ECD**.</span><span class="sxs-lookup"><span data-stu-id="3859e-173">Select **Fiscal books** \> **Common** \> **SPED ECD** \> **Validate SPED ECD**.</span></span>
14. <span data-ttu-id="3859e-174">Selecione **OK** para validar o arquivo SPED ECD.</span><span class="sxs-lookup"><span data-stu-id="3859e-174">Select **OK** to validate the SPED ECD file.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3859e-175">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="3859e-175">Additional resources</span></span>

[<span data-ttu-id="3859e-176">Gerar a obrigação de imposto Sintegra</span><span class="sxs-lookup"><span data-stu-id="3859e-176">Generate the Sintegra tax statement</span></span>](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/bra-parameters-tax/articles/financials/localizations/latam-bra-set-up-parameters-for-tax-statements.md)
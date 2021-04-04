---
title: Suprimir controles de conteúdo do Word em relatórios gerados
description: Este tópico explica como configurar um formato de Relatório eletrônico (ER) para gerar relatórios como arquivos do Microsoft Word nos quais os controles de conteúdo são suprimidos.
author: NickSelin
manager: AnnBe
ms.date: 02/11/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner,  LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: Version 10.0.6
ms.openlocfilehash: 81ad25514154dd8982aa4f849f0b2bfeb85270f7
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562109"
---
# <a name="suppress-word-content-controls-in-generated-reports"></a><span data-ttu-id="90a2e-103">Suprimir controles de conteúdo do Word em relatórios gerados</span><span class="sxs-lookup"><span data-stu-id="90a2e-103">Suppress Word content controls in generated reports</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="90a2e-104">Para gerar relatórios como documentos do Microsoft Word, você deverá criar um modelo para os relatórios como um documento do Word.</span><span class="sxs-lookup"><span data-stu-id="90a2e-104">To generate reports as Microsoft Word documents, you must design a template for the reports as a Word document.</span></span> <span data-ttu-id="90a2e-105">Esse modelo deve conter controles de conteúdo do Word como espaços reservados para os dados que serão preenchidos no runtime.</span><span class="sxs-lookup"><span data-stu-id="90a2e-105">This template must contain Word content controls as placeholders for data that will be filled in at runtime.</span></span> <span data-ttu-id="90a2e-106">Para usar um documento do Word criado como um modelo para seus relatórios, você poderá [configurar](er-design-configuration-word.md) uma nova [solução](er-quick-start1-new-solution.md) de [Relatório eletrônico (ER)](general-electronic-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="90a2e-106">To use the Word document that is created as a template for your reports, you can [configure](er-design-configuration-word.md) a new [Electronic reporting (ER)](general-electronic-reporting.md) [solution](er-quick-start1-new-solution.md).</span></span> <span data-ttu-id="90a2e-107">A solução deve incluir uma [configuração](general-electronic-reporting.md#Configuration) ER que contenha um componente de [formato](general-electronic-reporting.md#FormatComponentOutbound) ER.</span><span class="sxs-lookup"><span data-stu-id="90a2e-107">The solution must include an ER [configuration](general-electronic-reporting.md#Configuration) that contains an ER [format](general-electronic-reporting.md#FormatComponentOutbound) component.</span></span> <span data-ttu-id="90a2e-108">Esse formato ER deve ser configurado para usar o modelo projetado para a geração de relatórios.</span><span class="sxs-lookup"><span data-stu-id="90a2e-108">This ER format must be configured to use the designed template for report generation.</span></span>

<span data-ttu-id="90a2e-109">Na versão 10.0.6 e posterior do Dynamics 365 Finance, você pode configurar fórmulas no formato ER para suprimir alguns controles de conteúdo do Word em documentos gerados.</span><span class="sxs-lookup"><span data-stu-id="90a2e-109">In version 10.0.6 and later of Dynamics 365 Finance, you can configure formulas in your ER format to suppress some Word content controls in generated documents.</span></span>

<span data-ttu-id="90a2e-110">As etapas a seguir explicam como um usuário atribuído à função Administrador do sistema ou Consultor funcional de Relatório eletrônico pode configurar um formato ER que gera relatórios como arquivos do Word e suprime alguns dos controles de conteúdo nos relatórios gerados que foram configurados usando um modelo do Word.</span><span class="sxs-lookup"><span data-stu-id="90a2e-110">The following steps explain how a user who is assigned to the System administrator or Electronic reporting functional consultant role can configure an ER format that generates reports as Word files and suppresses some of the content controls in the generated reports that have been configured by using a Word template.</span></span>

<span data-ttu-id="90a2e-111">Estas etapas podem ser concluídas na empresa GBSI.</span><span class="sxs-lookup"><span data-stu-id="90a2e-111">These steps can be completed in the GBSI company.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="90a2e-112">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="90a2e-112">Prerequisites</span></span>

<span data-ttu-id="90a2e-113">Para concluir estas etapas, primeiro você deverá concluir as etapas nas seguintes guias de tarefas:</span><span class="sxs-lookup"><span data-stu-id="90a2e-113">To complete these steps, you must first complete the steps in the following task guides:</span></span>

- [<span data-ttu-id="90a2e-114">Criar uma configuração para gerar relatórios no formato OPENXML</span><span class="sxs-lookup"><span data-stu-id="90a2e-114">Design a configuration for generating reports in OPENXML format</span></span>](./tasks/er-design-reports-openxml-2016-11.md)
- [<span data-ttu-id="90a2e-115">Reutilizar configurações de ER com modelos do Excel para gerar relatórios no formato do Word</span><span class="sxs-lookup"><span data-stu-id="90a2e-115">Re-use ER configurations with Excel templates to generate reports in Word format</span></span>](./tasks/er-design-configuration-word-2016-11.md)

<span data-ttu-id="90a2e-116">Quando você concluir as etapas desses guias de tarefas, os seguintes itens serão preparados:</span><span class="sxs-lookup"><span data-stu-id="90a2e-116">When you complete the steps of these task guides, the following items are prepared:</span></span>

- <span data-ttu-id="90a2e-117">Um formato ER de **Relatório de planilha de exemplo** que está configurado para gerar um documento no formato do Word</span><span class="sxs-lookup"><span data-stu-id="90a2e-117">A **Sample worksheet report** ER format that is configured to generate a document in Word format</span></span>
- <span data-ttu-id="90a2e-118">Uma versão de [rascunho](general-electronic-reporting.md#component-versioning) do formato ER de **Relatório de planilha de exemplo** marcado como **Executável**</span><span class="sxs-lookup"><span data-stu-id="90a2e-118">A [draft](general-electronic-reporting.md#component-versioning) version of the **Sample worksheet report** ER format that is marked as **Runnable**</span></span>
- <span data-ttu-id="90a2e-119">Um método de pagamentos **Eletrônico** configurado para usar o formato ER de **Relatório de planilha de exemplo** para processamento de pagamento de fornecedor</span><span class="sxs-lookup"><span data-stu-id="90a2e-119">An **Electronic** method of payments that is configured to use the **Sample worksheet report** ER format for vendor payment processing</span></span>

<span data-ttu-id="90a2e-120">Você também precisa baixar e salvar o seguinte modelo para o relatório de exemplo:</span><span class="sxs-lookup"><span data-stu-id="90a2e-120">You must also download and save the following template for the sample report:</span></span>

- [<span data-ttu-id="90a2e-121">Modelo limitado 2 de relatório de pagamento (SampleVendPaymDocReportBounded2.docx)</span><span class="sxs-lookup"><span data-stu-id="90a2e-121">Bounded Template 2 of Payment Report (SampleVendPaymDocReportBounded2.docx)</span></span>](https://download.microsoft.com/download/a/1/2/a126cb43-6281-4f7b-bde0-25e03ff9bc1e/SampleVendPaymDocReportBounded2.docx)

## <a name="review-the-downloaded-word-template"></a><a id="tag-control"></a><span data-ttu-id="90a2e-122">Analisar o modelo do Word baixado</span><span class="sxs-lookup"><span data-stu-id="90a2e-122">Review the downloaded Word template</span></span>

1. <span data-ttu-id="90a2e-123">No aplicativo da área de trabalho de Word, abra o arquivo de modelo **SampleVendPaymDocReportBounded2.docx** baixado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="90a2e-123">In the Word desktop application, open the **SampleVendPaymDocReportBounded2.docx** template file that you downloaded earlier.</span></span>
2. <span data-ttu-id="90a2e-124">Verifique se o arquivo de modelo contém uma seção de resumo que mostra os valores de pagamento total para todos os códigos de moeda que foram atendidos nos pagamentos processados.</span><span class="sxs-lookup"><span data-stu-id="90a2e-124">Verify that the template file contains a summary section that shows the total payment amounts for every currency code that has been met in the processed payments.</span></span>

    - <span data-ttu-id="90a2e-125">A seção de resumo reside em uma tabela separada do documento do Word.</span><span class="sxs-lookup"><span data-stu-id="90a2e-125">The summary section resides in a separate table of the Word document.</span></span>
    - <span data-ttu-id="90a2e-126">A primeira linha desta tabela mantém os títulos das colunas da tabela como o cabeçalho da seção.</span><span class="sxs-lookup"><span data-stu-id="90a2e-126">The first row of this table holds the table columns headings as the section header.</span></span>
    - <span data-ttu-id="90a2e-127">A segunda linha desta tabela mantém o controle de conteúdo repetitivo como os detalhes da seção.</span><span class="sxs-lookup"><span data-stu-id="90a2e-127">The second row of this table holds the repeating content control as the section details.</span></span>
    - <span data-ttu-id="90a2e-128">Esse controle de conteúdo é mapeado para o campo **SummaryLines** da parte XML personalizada do **Relatório**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-128">This content control is mapped to the **SummaryLines** field of the **Report** custom XML part.</span></span>
    - <span data-ttu-id="90a2e-129">Com base nesse mapeamento, o controle de conteúdo é associado ao elemento **SummaryLines** do formato ER editável.</span><span class="sxs-lookup"><span data-stu-id="90a2e-129">Based on this mapping, the content control is associated with the **SummaryLines** element of the editable ER format.</span></span>

    > [!NOTE]
    > <span data-ttu-id="90a2e-130">O controle de conteúdo repetitivo é marcado pela chave **SummaryLines** que corresponde ao campo da parte XML personalizada para a qual foi mapeado.</span><span class="sxs-lookup"><span data-stu-id="90a2e-130">The repeating content control is tagged by the **SummaryLines** key that matches the field of the custom XML part that it has been mapped to.</span></span>

    ![Layout de modelo do Word](./media/er-design-configuration-word-suppress-controls-image1.gif)

## <a name="select-the-existing-er-report-configuration"></a><span data-ttu-id="90a2e-132">Selecionar a configuração de relatório de ER existente</span><span class="sxs-lookup"><span data-stu-id="90a2e-132">Select the existing ER report configuration</span></span>

<span data-ttu-id="90a2e-133">Para as etapas a seguir, você reusará a configuração de ER existente que você definiu ao concluir as etapas nos guias de tarefas mencionadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="90a2e-133">For the following steps, you will reuse the existing ER configuration that you configured when you completed the steps in the previously mentioned task guides.</span></span>

1. <span data-ttu-id="90a2e-134">Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-134">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="90a2e-135">Selecione **Configurações de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-135">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="90a2e-136">Na página **Configurações**, na árvore de configuração, expanda **Modelo de pagamento** e selecione **Relatório de planilha de exemplo**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-136">On the **Configurations** page, in the configuration tree, expand **Payment model**, and select **Sample worksheet report**.</span></span>
4. <span data-ttu-id="90a2e-137">Selecione **Designer** para editar a versão de rascunho do formato ER selecionado.</span><span class="sxs-lookup"><span data-stu-id="90a2e-137">Select **Designer** to edit the draft version of the selected ER format.</span></span>

## <a name="replace-the-current-template-with-the-new-template"></a><span data-ttu-id="90a2e-138">Substituir o modelo atual pelo novo modelo</span><span class="sxs-lookup"><span data-stu-id="90a2e-138">Replace the current template with the new template</span></span>

<span data-ttu-id="90a2e-139">Atualmente, o arquivo SampleVendPaymDocReportBounded.docx é usado como um modelo para gerar a saída no formato do Word.</span><span class="sxs-lookup"><span data-stu-id="90a2e-139">Currently, the SampleVendPaymDocReportBounded.docx file is used as a template to generate the output in Word format.</span></span> <span data-ttu-id="90a2e-140">Nas etapas a seguir, você substituirá esse modelo do Word pelo novo modelo do Word, SampleVendPaymDocReportBounded2.docx, que você baixou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="90a2e-140">In the following steps, you will replace this Word template with the new Word template, SampleVendPaymDocReportBounded2.docx, that you downloaded earlier.</span></span>

1. <span data-ttu-id="90a2e-141">Na página **Designer de formatos**, selecione **Anexos**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-141">On the **Format designer** page, select **Attachments**.</span></span>
2. <span data-ttu-id="90a2e-142">Na página **Anexos**, selecione **Excluir** para remover o modelo existente.</span><span class="sxs-lookup"><span data-stu-id="90a2e-142">On the **Attachments** page, select **Delete** to remove the existing template.</span></span>
3. <span data-ttu-id="90a2e-143">Selecione **Sim** para confirmar a exclusão.</span><span class="sxs-lookup"><span data-stu-id="90a2e-143">Select **Yes** to confirm the deletion.</span></span>
4. <span data-ttu-id="90a2e-144">Selecione **Novo** \> **Arquivo**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-144">Select **New** \> **File**.</span></span>
5. <span data-ttu-id="90a2e-145">Selecione **Procurar** e procure e selecione o arquivo **SampleVendPaymDocReportBounded2.docx** baixado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="90a2e-145">Select **Browse**, and browse to and select the **SampleVendPaymDocReportBounded2.docx** file that you downloaded earlier.</span></span>
6. <span data-ttu-id="90a2e-146">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-146">Select **OK**.</span></span>
7. <span data-ttu-id="90a2e-147">Feche a página **Anexos**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-147">Close the **Attachments** page.</span></span>
8. <span data-ttu-id="90a2e-148">Na página **Designer de formatos**, no campo **Modelo**, insira ou selecione o arquivo **SampleVendPaymDocReportBounded2.docx**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-148">On the **Format designer** page, in the **Template** field, enter or select the **SampleVendPaymDocReportBounded2.docx** file.</span></span>

## <a name="run-the-format-to-create-word-output"></a><span data-ttu-id="90a2e-149">Executar o formato para criar a saída do Word</span><span class="sxs-lookup"><span data-stu-id="90a2e-149">Run the format to create Word output</span></span>

1. <span data-ttu-id="90a2e-150">Acesse **Contas a pagar** \> **Pagamentos** \> **Diário de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-150">Go to **Accounts payable** \> **Payments** \> **Payment journal**.</span></span>
2. <span data-ttu-id="90a2e-151">Na página **Pagamentos do fornecedor**, na guia **Lista**, selecione todos os pagamentos.</span><span class="sxs-lookup"><span data-stu-id="90a2e-151">On the **Vendor payments** page, on the **List** tab, select all the payments.</span></span>
3. <span data-ttu-id="90a2e-152">Selecione o **Status do pagamento** \> **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-152">Select **Payment status** \> **None**.</span></span>
4. <span data-ttu-id="90a2e-153">Selecione **Gerar pagamentos**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-153">Select **Generate payments**.</span></span>
5. <span data-ttu-id="90a2e-154">No campo **Método de pagamento**, selecione **Eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-154">In the **Method of payment** field, select **Electronic**.</span></span>
6. <span data-ttu-id="90a2e-155">No campo **Conta bancária**, selecione **GBSI OPER**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-155">In the **Bank account** field, select **GBSI OPER**.</span></span>
7. <span data-ttu-id="90a2e-156">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-156">Select **OK**.</span></span>
8. <span data-ttu-id="90a2e-157">Na caixa de diálogo **Parâmetros de relatório eletrônico**, selecione **OK** e analise a saída gerada.</span><span class="sxs-lookup"><span data-stu-id="90a2e-157">In the **Electronic report parameters** dialog box, select **OK**, and analyze the generated output.</span></span>

    ![Pagamentos para processar na página Pagamentos do fornecedor](./media/er-design-configuration-word-suppress-controls-image2.gif)

    <span data-ttu-id="90a2e-159">A saída é apresentada no formato do Word e contém a seção de resumo.</span><span class="sxs-lookup"><span data-stu-id="90a2e-159">The output is presented in Word format and contains the summary section.</span></span>

## <a name="configure-the-editable-format-to-suppress-the-summary-section"></a><a id="configure-to-suppress-control"></a><span data-ttu-id="90a2e-160">Configurar o formato editável para suprimir a seção de resumo</span><span class="sxs-lookup"><span data-stu-id="90a2e-160">Configure the editable format to suppress the summary section</span></span>

<span data-ttu-id="90a2e-161">Se desejar suprimir a seção de resumo em um documento gerado, com base na solicitação de um usuário que executa esse formato ER, você deverá modificar o formato ER editável.</span><span class="sxs-lookup"><span data-stu-id="90a2e-161">If you want to suppress the summary section in a generated document, based on the request of a user who runs this ER format, you must modify the editable ER format.</span></span>

1. <span data-ttu-id="90a2e-162">Acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico** e abra a versão de rascunho do formato ER para edição.</span><span class="sxs-lookup"><span data-stu-id="90a2e-162">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**, and open the draft version of the ER format for editing.</span></span>
2. <span data-ttu-id="90a2e-163">Selecione **Configurações de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-163">Select **Reporting configurations**.</span></span> 
3. <span data-ttu-id="90a2e-164">Na página **Configurações**, na árvore de configuração, expanda **Modelo de pagamento** \> **Relatório de planilha de exemplo**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-164">On the **Configurations** page, in the configuration tree, expand **Payment model** \> **Sample worksheet report**.</span></span>
4. <span data-ttu-id="90a2e-165">Selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-165">Select **Designer**.</span></span>
5. <span data-ttu-id="90a2e-166">Na página **Designer de formatos**, expanda **Word** e selecione **SummaryLines**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-166">On the **Format designer** page, expand **Word**, and select **SummaryLines**.</span></span>
6. <span data-ttu-id="90a2e-167">Na guia **Mapeamento**, adicione uma nova fonte de dados para perguntar ao usuário, no runtime, se a seção de resumo deve ser suprimida:</span><span class="sxs-lookup"><span data-stu-id="90a2e-167">On the **Mapping** tab, add a new data source to ask the user, at runtime, whether the summary section should be suppressed:</span></span>

    1. <span data-ttu-id="90a2e-168">Selecione **Adicionar raiz**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-168">Select **Add root**.</span></span>
    2. <span data-ttu-id="90a2e-169">Na caixa de diálogo **Adicionar fonte de dados**, selecione **Geral\Parâmetro de entrada de usuário** para abrir a caixa de diálogo **Propriedades da fonte de dados "Parâmetro de entrada do usuário"**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-169">In the **Add data source** dialog box, select **General\User input parameter** to open the **'User input parameter' data source properties** dialog box.</span></span>
    3. <span data-ttu-id="90a2e-170">No campo **Nome**, insira **uipSuppress**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-170">In the **Name** field, enter **uipSuppress**.</span></span>
    4. <span data-ttu-id="90a2e-171">No campo **Rótulo**, insira a **seção Resumo de supressão**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-171">In the **Label** field, enter **Suppress summary section**.</span></span>
    5. <span data-ttu-id="90a2e-172">No campo **Nome do tipo de dados de operações**, selecione ou insira **NoYes**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-172">In the **Operations data type name** field, select or enter **NoYes**.</span></span>
    6. <span data-ttu-id="90a2e-173">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-173">Select **OK**.</span></span>

7. <span data-ttu-id="90a2e-174">Adicione uma nova fonte de dados do tipo de enumeração de aplicativo **NoYes**:</span><span class="sxs-lookup"><span data-stu-id="90a2e-174">Add a new data source of the **NoYes** application enumeration type:</span></span>

    1. <span data-ttu-id="90a2e-175">Selecione **Adicionar raiz**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-175">Select **Add root**.</span></span>
    2. <span data-ttu-id="90a2e-176">Na caixa de diálogo **Adicionar fonte de dados**, selecione **Dynamics 365 for Operations\Enumeração** para abrir a caixa de diálogo **Propriedades da fonte de dados "Enumeração"**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-176">In the **Add data source** dialog box, select **Dynamics 365 for Operations\Enumeration** to open the **'Enumeration' data source properties** dialog box.</span></span>
    3. <span data-ttu-id="90a2e-177">No campo **Nome**, insira **enumNoYes**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-177">In the **Name** field, enter **enumNoYes**.</span></span>
    4. <span data-ttu-id="90a2e-178">No campo **Rótulo**, insira **Opções de supressão**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-178">In the **Label** field, enter **Suppress options**.</span></span>
    5. <span data-ttu-id="90a2e-179">No campo **Nome do tipo de dados de operações**, selecione ou insira **NoYes**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-179">In the **Operations data type name** field, select or enter **NoYes**.</span></span>
    6. <span data-ttu-id="90a2e-180">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-180">Select **OK**.</span></span>

8. <span data-ttu-id="90a2e-181">Para o elemento de formato **SummaryLines** selecionado, configure a fórmula para especificar quando o controle de conteúdo do Word associado ao elemento de formato selecionado deve ser suprimido:</span><span class="sxs-lookup"><span data-stu-id="90a2e-181">For the selected **SummaryLines** format element, configure the formula to specify when the Word content control that is associated with the selected format element should be suppressed:</span></span>

    1. <span data-ttu-id="90a2e-182">Na guia **Mapeamento**, na seção **Removido**, selecione **Editar** para abrir a página **[Designer de fórmulas](general-electronic-reporting-formula-designer.md)**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-182">On the **Mapping** tab, in the **Removed** section, select **Edit** to open the **[Formula designer](general-electronic-reporting-formula-designer.md)** page.</span></span>
    2. <span data-ttu-id="90a2e-183">No campo **Fórmula**, insira a fórmula `uipSuppress = enumNoYes.Yes`.</span><span class="sxs-lookup"><span data-stu-id="90a2e-183">In the **Formula** field, enter the formula `uipSuppress = enumNoYes.Yes`.</span></span>
    3. <span data-ttu-id="90a2e-184">Selecione **Salvar** e feche a página **Designer de fórmulas**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-184">Select **Save**, and close the **Formula designer** page.</span></span>

        > [!NOTE]
        > <span data-ttu-id="90a2e-185">Essa fórmula será aplicada a um documento gerado **depois que todos os outros elementos de formato são executados**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-185">This formula will be applied to a generated document **after all other format elements are run**.</span></span> <span data-ttu-id="90a2e-186">Para aplicar essa fórmula, um controle de conteúdo do Word marcado como um elemento de formato para o qual a fórmula está configurada (**SummaryLines**, nesse caso) é encontrado em um documento gerado.</span><span class="sxs-lookup"><span data-stu-id="90a2e-186">To apply this formula, a Word content control that is tagged as a format element that the formula is configured for (**SummaryLines** in this case) is found in a generated document.</span></span> <span data-ttu-id="90a2e-187">Esse controle de conteúdo é, então, completamente removido, juntamente com a linha da tabela do Word que o contém.</span><span class="sxs-lookup"><span data-stu-id="90a2e-187">That content control is then completely removed, together with the row in the Word table that holds it.</span></span> <span data-ttu-id="90a2e-188">A linha de detalhes da seção de resumo é removida do documento gerado.</span><span class="sxs-lookup"><span data-stu-id="90a2e-188">The details row of the summary section is removed from the generated document.</span></span>
        >
        > <span data-ttu-id="90a2e-189">Em tempo de design, você pode configurar a fórmula **Removida** para um elemento de formato, mesmo que nenhum controle de conteúdo no modelo do Word que você está usando tenha uma marca que corresponda ao nome de um elemento de formato para o qual a propriedade **Removida** está configurada.</span><span class="sxs-lookup"><span data-stu-id="90a2e-189">At design time, you might configure the **Removed** formula for a format element, even though no content control in the Word template that you're using has a tag that matches the name of a format element that the **Removed** property is configured for.</span></span> <span data-ttu-id="90a2e-190">Ao validar o formato no tempo de design, você receberá um [aviso](er-components-inspections.md#i14) sobre essa inconsistência.</span><span class="sxs-lookup"><span data-stu-id="90a2e-190">When you validate the format at design time, you receive a [warning](er-components-inspections.md#i14) about this inconsistency.</span></span>
        >
        > <span data-ttu-id="90a2e-191">No runtime, uma exceção será lançada se nenhum controle de conteúdo no modelo do Word que você está usando tiver uma marca que corresponda ao nome de um elemento de formato para o qual a propriedade **Removida** está configurada.</span><span class="sxs-lookup"><span data-stu-id="90a2e-191">At runtime, an exception is thrown if no content control in the Word template that you're using has a tag that matches the name of a format element that the **Removed** property is configured for.</span></span>

    4. <span data-ttu-id="90a2e-192">Na guia **Mapeamento**, na seção **Removido**, defina a opção **Com pai** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-192">On the **Mapping** tab, in the **Removed** section, set the **With parent** option to **Yes**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="90a2e-193">Você deve definir esta opção como **Sim** para remover a tabela inteira do Word como o objeto pai da linha que contém os detalhes da seção de resumo.</span><span class="sxs-lookup"><span data-stu-id="90a2e-193">You must set this option to **Yes** to remove the whole Word table as the parent object of the row that holds the summary section details.</span></span> <span data-ttu-id="90a2e-194">Se você definir essa opção como **Não**, a linha de cabeçalho da seção permanecerá no documento gerado.</span><span class="sxs-lookup"><span data-stu-id="90a2e-194">If you set this option to **No**, the section header row remains in the generated document.</span></span>

9. <span data-ttu-id="90a2e-195">Selecione **Salvar** para salvar as alterações no formato editável.</span><span class="sxs-lookup"><span data-stu-id="90a2e-195">Select **Save** to save your changes to the editable format.</span></span>

    ![A saída gerada no formato do Word](./media/er-design-configuration-word-suppress-controls-image3.gif)

## <a name="run-the-modified-format-to-create-word-output"></a><span data-ttu-id="90a2e-197">Executar o formato modificado para criar a saída do Word</span><span class="sxs-lookup"><span data-stu-id="90a2e-197">Run the modified format to create Word output</span></span>

1. <span data-ttu-id="90a2e-198">Acesse **Contas a pagar** \> **Pagamentos** \> **Diário de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-198">Go to **Accounts payable** \> **Payments** \> **Payment journal**.</span></span>
2. <span data-ttu-id="90a2e-199">Selecione o diário de pagamento que você criou e, em seguida, selecione **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-199">Select the payment journal that you created, and then select **Lines**.</span></span>
3. <span data-ttu-id="90a2e-200">Na página **Pagamentos do fornecedor**, selecione todas as linhas e, em seguida, selecione **Status do pagamento** \> **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-200">On the **Vendor payments** page, select all the rows, and then select **Payment status** \> **None**.</span></span>
4. <span data-ttu-id="90a2e-201">Selecione **Gerar pagamentos**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-201">Select **Generate payments**.</span></span>
5. <span data-ttu-id="90a2e-202">No campo **Método de pagamento**, selecione **Eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-202">In the **Method of payment** field, select **Electronic**.</span></span>
6. <span data-ttu-id="90a2e-203">No campo **Conta bancária**, selecione **GBSI OPER**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-203">In the **Bank account** field, select **GBSI OPER**.</span></span>
7. <span data-ttu-id="90a2e-204">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-204">Select **OK**.</span></span>
8. <span data-ttu-id="90a2e-205">Na caixa de diálogo **Parâmetros do relatório eletrônico** , no campo **Seção Resumo de supressão**, selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="90a2e-205">In the **Electronic report parameters** dialog box, in the **Suppress summary section** field, select **Yes**.</span></span>
9. <span data-ttu-id="90a2e-206">Selecione **OK** e analise a saída gerada.</span><span class="sxs-lookup"><span data-stu-id="90a2e-206">Select **OK**, and analyze the generated output.</span></span>

    ![Saída gerada no formato Word](./media/er-design-configuration-word-suppress-controls-image4.gif)

    <span data-ttu-id="90a2e-208">Observe que a saída não contém a seção de resumo, pois ela foi suprimida.</span><span class="sxs-lookup"><span data-stu-id="90a2e-208">Notice that the output doesn't contain the summary section, because it has been suppressed.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="90a2e-209">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="90a2e-209">Additional resources</span></span>

- [<span data-ttu-id="90a2e-210">Criar uma configuração para gerar relatórios no formato OPENXML</span><span class="sxs-lookup"><span data-stu-id="90a2e-210">Design a configuration for generating reports in OPENXML format</span></span>](./tasks/er-design-reports-openxml-2016-11.md)
- [<span data-ttu-id="90a2e-211">Criar uma configuração ER para gerar relatórios no formato Word</span><span class="sxs-lookup"><span data-stu-id="90a2e-211">Design a new ER configuration to generate reports in Word format</span></span>](er-design-configuration-word.md)
- [<span data-ttu-id="90a2e-212">Reutilizar configurações de ER com modelos do Excel para gerar relatórios no formato do Word</span><span class="sxs-lookup"><span data-stu-id="90a2e-212">Re-use ER configurations with Excel templates to generate reports in Word format</span></span>](./tasks/er-design-configuration-word-2016-11.md)
- [<span data-ttu-id="90a2e-213">Inspecionar o componente de ER configurado para evitar problemas de runtime</span><span class="sxs-lookup"><span data-stu-id="90a2e-213">Inspect the configured ER component to prevent runtime issues</span></span>](er-components-inspections.md#i14)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
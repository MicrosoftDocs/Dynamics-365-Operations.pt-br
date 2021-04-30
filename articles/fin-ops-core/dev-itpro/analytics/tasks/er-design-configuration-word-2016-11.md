---
title: Reutilizar configurações de ER com modelos do Excel para gerar relatórios no formatos Word
description: Este tópico descreve como os formatos de relatório criados para gerar relatórios como pastas de trabalho do Excel podem ser configurados para gerar relatórios como documentos do Word.
author: NickSelin
ms.date: 01/11/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner, LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ab4cd4a390782936a74977ac2aef3790aa8ac1af
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5891686"
---
# <a name="reuse-er-configurations-with-excel-templates-to-generate-reports-in-word-format"></a><span data-ttu-id="eafb3-103">Reutilizar configurações de ER com modelos do Excel para gerar relatórios no formatos Word</span><span class="sxs-lookup"><span data-stu-id="eafb3-103">Reuse ER configurations with Excel templates to generate reports in Word format</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="eafb3-104">Para gerar relatórios como documentos do Microsoft Word, você pode [configurar](../er-design-configuration-word.md) um novo [formato](../general-electronic-reporting.md) de [relatório eletrônico (ER)](../general-electronic-reporting.md#FormatComponentOutbound).</span><span class="sxs-lookup"><span data-stu-id="eafb3-104">To generate reports as Microsoft Word documents, you can [configure](../er-design-configuration-word.md) a new [Electronic reporting (ER)](../general-electronic-reporting.md) [format](../general-electronic-reporting.md#FormatComponentOutbound).</span></span> <span data-ttu-id="eafb3-105">Como alternativa, você pode reutilizar um formato de ER que foi originalmente projetado para gerar relatórios como pastas de trabalho do Excel.</span><span class="sxs-lookup"><span data-stu-id="eafb3-105">Alternatively, you can reuse an ER format that was originally designed to generate reports as Excel workbooks.</span></span> <span data-ttu-id="eafb3-106">Nesse caso, você deve substituir o modelo do Excel por um modelo do Word.</span><span class="sxs-lookup"><span data-stu-id="eafb3-106">In this case, you must replace the Excel template with a Word template.</span></span>

<span data-ttu-id="eafb3-107">Os procedimentos a seguir mostram como um usuário na função Administrador do sistema ou no desenvolvedor de relatório eletrônico pode configurar um formato de ER para gerar relatórios como arquivos do Word reutilizando um formato de ER que foi criado para gerar relatórios como arquivos do Excel.</span><span class="sxs-lookup"><span data-stu-id="eafb3-107">The following procedures show how a user in either the System administrator role or the Electronic reporting developer role can configure an ER format to generate reports as Word files by reusing an ER format that was designed to generate reports as Excel files.</span></span>

<span data-ttu-id="eafb3-108">Esses procedimentos podem ser concluídos na empresa GBSI.</span><span class="sxs-lookup"><span data-stu-id="eafb3-108">These procedures can be completed in the GBSI company.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="eafb3-109">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="eafb3-109">Prerequisites</span></span>

<span data-ttu-id="eafb3-110">Para completar esses procedimentos, primeiro você deve seguir as etapas no guia de tarefa [Criar uma configuração para gerar relatórios no formato OPENXML](er-design-reports-openxml-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="eafb3-110">To complete these procedures, you must first follow the steps in the [Design a configuration for generating reports in OPENXML format](er-design-reports-openxml-2016-11.md) task guide.</span></span>

<span data-ttu-id="eafb3-111">Você também precisa baixar e salvar localmente os seguintes modelos para o modelo de relatório:</span><span class="sxs-lookup"><span data-stu-id="eafb3-111">You must also download and locally save the following templates for the sample report:</span></span>

- [<span data-ttu-id="eafb3-112">Modelo de relatório de pagamento (SampleVendPaymDocReport.docx)</span><span class="sxs-lookup"><span data-stu-id="eafb3-112">Template of Payment Report (SampleVendPaymDocReport.docx)</span></span>](https://go.microsoft.com/fwlink/?linkid=862266)
- [<span data-ttu-id="eafb3-113">Modelo limitado de relatório de pagamento (SampleVendPaymDocReportBounded.docx)</span><span class="sxs-lookup"><span data-stu-id="eafb3-113">Bounded Template of Payment Report (SampleVendPaymDocReportBounded.docx)</span></span>](https://go.microsoft.com/fwlink/?linkid=862266)

<span data-ttu-id="eafb3-114">Esses procedimentos são para um recurso que foi adicionado no Dynamics 365 for Operations versão 1611 (novembro de 2016).</span><span class="sxs-lookup"><span data-stu-id="eafb3-114">These procedures are for a feature that was added in Dynamics 365 for Operations version 1611 (November 2016).</span></span>

## <a name="select-the-existing-er-report-configuration"></a><span data-ttu-id="eafb3-115">Selecionar a configuração de relatório de ER existente</span><span class="sxs-lookup"><span data-stu-id="eafb3-115">Select the existing ER report configuration</span></span>

1. <span data-ttu-id="eafb3-116">No Dynamics 365 Finance, vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="eafb3-116">In Dynamics 365 Finance, go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="eafb3-117">Verifique se o provedor de configuração **Litware, Inc.** está selecionado como **Ativo**.</span><span class="sxs-lookup"><span data-stu-id="eafb3-117">Make sure that the **Litware, Inc.** configuration provider is selected as **Active**.</span></span> <span data-ttu-id="eafb3-118">Se não estiver, siga as etapas no guia de tarefas [Criar provedores de configuração e marcá-los como ativos](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="eafb3-118">If it isn't, follow the steps in the [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md) task guide.</span></span>
3. <span data-ttu-id="eafb3-119">Selecione **Configurações de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="eafb3-119">Select **Reporting configurations**.</span></span> <span data-ttu-id="eafb3-120">Você reutilizará a configuração de ER existente que foi criada para gerar a saída de relatório no formato OPENXML.</span><span class="sxs-lookup"><span data-stu-id="eafb3-120">You will reuse the existing ER configuration that was designed to generate the report output in OPENXML format.</span></span>
4. <span data-ttu-id="eafb3-121">Na página **Configurações**, na árvore de configuração no painel esquerdo, expanda **Modelo de pagamento** e selecione **Exemplo de relatório de planilha**.</span><span class="sxs-lookup"><span data-stu-id="eafb3-121">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**, and select **Sample worksheet report**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="eafb3-122">A versão de rascunho selecionada do formato de ER pode ser editada na guia rápida **Versões**.</span><span class="sxs-lookup"><span data-stu-id="eafb3-122">The draft version of the selected ER format can be edited on the **Versions** FastTab.</span></span>

5. <span data-ttu-id="eafb3-123">Selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="eafb3-123">Select **Designer**.</span></span>
6. <span data-ttu-id="eafb3-124">Na página **Designer de formato**, observe que o título do elemento de formato raiz indica que um modelo do Excel está sendo usado no momento.</span><span class="sxs-lookup"><span data-stu-id="eafb3-124">On the **Format designer** page, notice that the title of the root format element indicates that an Excel template is currently used.</span></span>

![Selecionar a configuração existente](../media/er-design-configuration-word-2016-11-image01.gif)

## <a name="review-the-downloaded-word-template"></a><span data-ttu-id="eafb3-126">Analisar o modelo do Word baixado</span><span class="sxs-lookup"><span data-stu-id="eafb3-126">Review the downloaded Word template</span></span>

1. <span data-ttu-id="eafb3-127">No aplicativo da área de trabalho Word, abra o arquivo de modelo **SampleVendPaymDocReport.docx** baixado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="eafb3-127">In the Word desktop application, open the **SampleVendPaymDocReport.docx** template file that you downloaded earlier.</span></span>
2. <span data-ttu-id="eafb3-128">Observe que esse modelo contém apenas o layout do documento que desejamos gerar como saída de ER.</span><span class="sxs-lookup"><span data-stu-id="eafb3-128">Verify that the template contains only the layout of the document that you want to generate as ER output.</span></span>

![O layout de modelo do Word no aplicativo da área de trabalho](../media/er-design-configuration-word-2016-11-image02.png)

## <a name="replace-the-excel-template-with-the-word-template-and-add-a-custom-xml-part"></a><span data-ttu-id="eafb3-130">Substituir o modelo do Excel pelo modelo do Word e adicionar uma parte XML personalizada</span><span class="sxs-lookup"><span data-stu-id="eafb3-130">Replace the Excel template with the Word template and add a custom XML part</span></span>

<span data-ttu-id="eafb3-131">Atualmente, o documento do Excel é usado como modelo para gerar a saída no formato OPENXML.</span><span class="sxs-lookup"><span data-stu-id="eafb3-131">Currently, the Excel document is used as a template to generate the output in OPENXML format.</span></span> <span data-ttu-id="eafb3-132">Você substituirá este modelo com o arquivo de modelo do Word SampleVendPaymDocReport.docx baixado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="eafb3-132">You will replace this template with the SampleVendPaymDocReport.docx Word template file that you downloaded earlier.</span></span> <span data-ttu-id="eafb3-133">Você também estenderá o modelo do Word adicionando uma parte XML personalizada.</span><span class="sxs-lookup"><span data-stu-id="eafb3-133">You will also extend the Word template by adding a custom XML part.</span></span>

1. <span data-ttu-id="eafb3-134">No Finance, na página **Designer de formato**, na guia **Formatar**, selecione **Anexos**.</span><span class="sxs-lookup"><span data-stu-id="eafb3-134">In Finance, on the **Format designer** page, on the **Format** tab, select **Attachments**.</span></span>
2. <span data-ttu-id="eafb3-135">Na página **Anexos**, selecione **Excluir** para remover o modelo do Excel existente.</span><span class="sxs-lookup"><span data-stu-id="eafb3-135">On the **Attachments** page, select **Delete** to remove the existing Excel template.</span></span> <span data-ttu-id="eafb3-136">Selecione **Sim** para confirmar a alteração.</span><span class="sxs-lookup"><span data-stu-id="eafb3-136">Select **Yes** to confirm the change.</span></span>
3. <span data-ttu-id="eafb3-137">Selecione **Novo** \> **Arquivo**.</span><span class="sxs-lookup"><span data-stu-id="eafb3-137">Select **New** \> **File**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="eafb3-138">É necessário selecionar um tipo de documento [configurado](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) nos parâmetros de ER para armazenar modelos de formato de ER.</span><span class="sxs-lookup"><span data-stu-id="eafb3-138">You must select a document type that has been [configured](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) in the ER parameters to store templates of ER formats.</span></span>

4. <span data-ttu-id="eafb3-139">Selecione **Pesquisar**, pesquise e selecione o arquivo **SampleVendPaymDocReport.docx** baixado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="eafb3-139">Select **Browse**, and then browse to and select the **SampleVendPaymDocReport.docx** file that you downloaded earlier.</span></span>
5. <span data-ttu-id="eafb3-140">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="eafb3-140">Select **OK**.</span></span>
6. <span data-ttu-id="eafb3-141">Feche a página **Anexos**.</span><span class="sxs-lookup"><span data-stu-id="eafb3-141">Close the **Attachments** page.</span></span>
7. <span data-ttu-id="eafb3-142">Na página **Designer de formato**, no campo **Modelo**, insira ou selecione o arquivo **SampleVendPaymDocReport.docx** para usar esse modelo do Word em vez do modelo do Excel que foi usado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="eafb3-142">On the **Format designer** page, in the **Template** field, enter or select the **SampleVendPaymDocReport.docx** file to use that Word template instead of the Excel template that was previously used.</span></span>
8. <span data-ttu-id="eafb3-143">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="eafb3-143">Select **Save**.</span></span>

    <span data-ttu-id="eafb3-144">Além de armazenar alterações de configuração, a ação **Salvar** também atualiza o modelo do Word anexo.</span><span class="sxs-lookup"><span data-stu-id="eafb3-144">In addition to storing configuration changes, the **Save** action updates the attached Word template.</span></span> <span data-ttu-id="eafb3-145">A estrutura hierárquica do formato criado é adicionada ao documento do Word anexo como nova parte XML personalizada chamada **Relatório**.</span><span class="sxs-lookup"><span data-stu-id="eafb3-145">The hierarchical structure of the designed format is added to the attached Word document as a new custom XML part that is named **Report**.</span></span> <span data-ttu-id="eafb3-146">O modelo do Word anexo contém não só o layout do documento que será gerado como saída de ER, mas também a estrutura dos dados que o ER preencherá nesse modelo no runtime.</span><span class="sxs-lookup"><span data-stu-id="eafb3-146">The attached Word template contains the layout of the document that will be generated as ER output and the structure of data that ER will enter in that template at runtime.</span></span>

9. <span data-ttu-id="eafb3-147">Observe que o título do elemento de formato raiz indica que um modelo do Word está sendo usado no momento.</span><span class="sxs-lookup"><span data-stu-id="eafb3-147">Notice that the title of the root format element indicates that a Word template is currently used.</span></span>

    ![Substituir o modelo do Excel pelo modelo do Word e adicionar uma parte XML personalizada](../media/er-design-configuration-word-2016-11-image03.gif)

10. <span data-ttu-id="eafb3-149">Na guia **Formato**, selecione **Anexos**.</span><span class="sxs-lookup"><span data-stu-id="eafb3-149">On the **Format** tab, select **Attachments**.</span></span>

<span data-ttu-id="eafb3-150">Agora você pode mapear os elementos da parte XML personalizada **Relatório** selecionada para os controles de conteúdo do documento do Word.</span><span class="sxs-lookup"><span data-stu-id="eafb3-150">You can now map the elements of the **Report** custom XML part to the content controls of the Word document.</span></span>

<span data-ttu-id="eafb3-151">Se estiver familiarizado com o processo de criar documentos do Word como formulários com [controles de conteúdo](/office/client-developer/word/content-controls-in-word) mapeados a elementos das [partes XML personalizadas](/visualstudio/vsto/custom-xml-parts-overview?view=vs-2019), siga todas as etapas do próximo procedimento para criar o documento.</span><span class="sxs-lookup"><span data-stu-id="eafb3-151">If you're familiar with the process of designing Word documents as forms that contain [content controls](/office/client-developer/word/content-controls-in-word) that are mapped to elements of [custom XML parts](/visualstudio/vsto/custom-xml-parts-overview?view=vs-2019), complete all steps in the next procedure to create the document.</span></span> <span data-ttu-id="eafb3-152">Para obter mais informações, consulte [Criar formulários preenchidos ou impressos pelos usuários no Word](https://support.office.com/article/Create-forms-that-users-complete-or-print-in-Word-040c5cc1-e309-445b-94ac-542f732c8c8b).</span><span class="sxs-lookup"><span data-stu-id="eafb3-152">For more information, see [Create forms that users complete or print in Words](https://support.office.com/article/Create-forms-that-users-complete-or-print-in-Word-040c5cc1-e309-445b-94ac-542f732c8c8b).</span></span> <span data-ttu-id="eafb3-153">Caso contrário, ignore o próximo procedimento.</span><span class="sxs-lookup"><span data-stu-id="eafb3-153">Otherwise, skip the next procedure.</span></span>

## <a name="get-a-word-document-that-has-a-custom-xml-part-and-do-data-mapping"></a><a id='get-word-doc'></a><span data-ttu-id="eafb3-154">Obter um documento do Word que tenha uma parte XML personalizada e fazer mapeamento de dados</span><span class="sxs-lookup"><span data-stu-id="eafb3-154">Get a Word document that has a custom XML part and do data mapping</span></span>

1. <span data-ttu-id="eafb3-155">No Finance, na página **Anexos**, selecione **Abrir** para baixar o modelo selecionado do Finance e armazená-lo localmente como um documento do Word.</span><span class="sxs-lookup"><span data-stu-id="eafb3-155">In Finance, on the **Attachments** page, select **Open** to download the selected template from Finance and store it locally as a Word document.</span></span>
3. <span data-ttu-id="eafb3-156">No aplicativo da área de trabalho Word, abra o documento que você acabou de baixar.</span><span class="sxs-lookup"><span data-stu-id="eafb3-156">In the Word desktop application, open the document that you just downloaded.</span></span>
4. <span data-ttu-id="eafb3-157">Na guia **Desenvolvedor**, selecione **Painel de mapeamento XML**.</span><span class="sxs-lookup"><span data-stu-id="eafb3-157">On the **Developer** tab, select **XML Mapping Pane**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="eafb3-158">Se a guia **Desenvolvedor** não aparecer na faixa de opções, personalize a faixa para adicioná-la.</span><span class="sxs-lookup"><span data-stu-id="eafb3-158">If the **Developer** tab doesn't appear on the ribbon, customize the ribbon to add it.</span></span>

5. <span data-ttu-id="eafb3-159">No painel **Mapeamento XML**, no campo **Parte XML personalizada**, selecione a parte XML personalizada do **Relatório**.</span><span class="sxs-lookup"><span data-stu-id="eafb3-159">In the **XML Mapping** pane, in the **Custom XML Part** field, select the **Report** custom XML part.</span></span>
6. <span data-ttu-id="eafb3-160">Mapeie os elementos da parte XML personalizada **Relatório** selecionada e os controles de conteúdo do documento do Word.</span><span class="sxs-lookup"><span data-stu-id="eafb3-160">Map the elements of the selected **Report** custom XML part and the content controls of the Word document.</span></span>
7. <span data-ttu-id="eafb3-161">Salve o documento atualizado do Word localmente como **SampleVendPaymDocReportBounded.docx**.</span><span class="sxs-lookup"><span data-stu-id="eafb3-161">Save the updated Word document locally as **SampleVendPaymDocReportBounded.docx**.</span></span>

## <a name="review-the-word-template-where-the-custom-xml-part-is-mapped-to-content-controls"></a><span data-ttu-id="eafb3-162">Revisar o modelo do Word em que a parte XML personalizada é mapeada para controles de conteúdo</span><span class="sxs-lookup"><span data-stu-id="eafb3-162">Review the Word template where the custom XML part is mapped to content controls</span></span>

1. <span data-ttu-id="eafb3-163">No aplicativo da área de trabalho Word, abra o arquivo de modelo **SampleVendPaymDocReport.docx** baixado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="eafb3-163">In the Word desktop application, open the **SampleVendPaymDocReportBounded.docx** template file.</span></span>
2. <span data-ttu-id="eafb3-164">Observe que esse modelo contém o layout do documento que desejamos gerar como saída de ER.</span><span class="sxs-lookup"><span data-stu-id="eafb3-164">Verify that the template contains the layout of the document that you want to generate as ER output.</span></span> <span data-ttu-id="eafb3-165">Os controles de conteúdo usados como espaços reservados para dados que o ER insere neste modelo no tempo de execução são baseados nos mapeamentos que são configurados entre os elementos da parte XML personalizada **Relatório** e os controles de conteúdo do documento do Word.</span><span class="sxs-lookup"><span data-stu-id="eafb3-165">The content controls that are used as placeholders for data that ER will enter in this template at runtime are based on the mappings that are configured between elements of the **Report** custom XML part and the content controls of the Word document.</span></span>

![Versão prévia de modelo do Word no aplicativo da área de trabalho](../media/er-design-configuration-word-2016-11-image04.png)

## <a name="upload-the-word-template-where-the-custom-xml-part-is-mapped-to-content-controls"></a><span data-ttu-id="eafb3-167">Carregar o modelo do Word em que a parte XML personalizada é mapeada para controles de conteúdo</span><span class="sxs-lookup"><span data-stu-id="eafb3-167">Upload the Word template where the custom XML part is mapped to content controls</span></span>

1. <span data-ttu-id="eafb3-168">No Finance, na página **Anexos**, selecione **Excluir** para remover o modelo do Word que não tem mapeamentos entre elementos da parte XML personalizada **Relatório** e controles de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="eafb3-168">In Finance, on the **Attachments** page, select **Delete** to remove the Word template that has no mappings between elements of the **Report** custom XML part and content controls.</span></span> <span data-ttu-id="eafb3-169">Selecione **Sim** para confirmar a alteração.</span><span class="sxs-lookup"><span data-stu-id="eafb3-169">Select **Yes** to confirm the change.</span></span>
2. <span data-ttu-id="eafb3-170">Selecione **Novo** \> **Arquivo** para adicionar um novo arquivo de modelo que contém mapeamentos entre elementos da parte XML personalizada **Relatório** e controles de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="eafb3-170">Select **New** \> **File** to add a new template file that contains mappings between elements of the **Report** custom XML part and content controls.</span></span>

    > [!NOTE]
    > <span data-ttu-id="eafb3-171">É necessário selecionar um tipo de documento [configurado](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) nos parâmetros de ER para armazenar modelos de formato de ER.</span><span class="sxs-lookup"><span data-stu-id="eafb3-171">You must select a document type that has been [configured](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) in the ER parameters to store templates of ER formats.</span></span>

3. <span data-ttu-id="eafb3-172">Selecione **Pesquisar**, pesquise e selecione o arquivo **SampleVendPaymDocReportBounded.docx** que você baixou ou preparou concluindo o procedimento na seção [Obter um documento do Word que tenha uma parte XML personalizada para fazer mapeamento de dados](#get-word-doc).</span><span class="sxs-lookup"><span data-stu-id="eafb3-172">Select **Browse**, and then browse to and select the **SampleVendPaymDocReportBounded.docx** file that you downloaded or prepared by completing the procedure in the [Get a Word that has a custom XML part to do data mapping](#get-word-doc) section.</span></span>
4. <span data-ttu-id="eafb3-173">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="eafb3-173">Select **OK**.</span></span>
5. <span data-ttu-id="eafb3-174">Feche a página **Anexos**.</span><span class="sxs-lookup"><span data-stu-id="eafb3-174">Close the **Attachments** page.</span></span>
6. <span data-ttu-id="eafb3-175">Na página **Designer de formato**, no campo **Modelo**, selecione o documento que você acabou de baixar.</span><span class="sxs-lookup"><span data-stu-id="eafb3-175">On the **Format designer** page, in the **Template** field, select the document that you just downloaded.</span></span>
7. <span data-ttu-id="eafb3-176">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="eafb3-176">Select **Save**.</span></span>
8. <span data-ttu-id="eafb3-177">Feche a página **Designer de formato**.</span><span class="sxs-lookup"><span data-stu-id="eafb3-177">Close the **Format designer** page.</span></span>

## <a name="mark-the-configured-format-as-runnable"></a><span data-ttu-id="eafb3-178">Marcar o formato configurado como executável</span><span class="sxs-lookup"><span data-stu-id="eafb3-178">Mark the configured format as runnable</span></span>

<span data-ttu-id="eafb3-179">Para executar a versão de rascunho do formato editável, você deve torná-la [executável](../er-quick-start2-customize-report.md#MarkFormatRunnable).</span><span class="sxs-lookup"><span data-stu-id="eafb3-179">To run the draft version of the editable format, you must make it [runnable](../er-quick-start2-customize-report.md#MarkFormatRunnable).</span></span>

1. <span data-ttu-id="eafb3-180">No Finance, na página **Configurações**, no Painel Ação, na guia **Configurações**, no grupo **Configurações avançadas**, selecione **Parâmetros de usuário**.</span><span class="sxs-lookup"><span data-stu-id="eafb3-180">In Finance, on the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
2. <span data-ttu-id="eafb3-181">Na caixa de diálogo **Parâmetros de usuário**, defina a opção **Executar configurações** como **Sim** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="eafb3-181">In the **User parameters** dialog box, set the **Run settings** option to **Yes**, and then select **OK**.</span></span>
3. <span data-ttu-id="eafb3-182">Selecione **Editar** para tornar a página atual editável, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="eafb3-182">Select **Edit** to make the current page editable, as required.</span></span>
4. <span data-ttu-id="eafb3-183">Para a configuração **Exemplo de relatório de planilha** selecionada no momento, defina a opção **Executar rascunho** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="eafb3-183">For the currently selected **Sample worksheet report** configuration, set the **Run Draft** option to **Yes**.</span></span>
5. <span data-ttu-id="eafb3-184">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="eafb3-184">Select **Save**.</span></span>

## <a name="run-the-format-to-create-output-in-word-format"></a><span data-ttu-id="eafb3-185">Executar o formato para criar saída no formato do Word</span><span class="sxs-lookup"><span data-stu-id="eafb3-185">Run the format to create output in Word format</span></span>

1. <span data-ttu-id="eafb3-186">No Finance, vá para **Contas a pagar** \> **Pagamentos** \> **Diário de pagamentos**.</span><span class="sxs-lookup"><span data-stu-id="eafb3-186">In Finance, go to **Accounts payable** \> **Payments** \> **Payment journal**.</span></span>
2. <span data-ttu-id="eafb3-187">Em um diário de pagamentos inserido anteriormente, selecione **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="eafb3-187">In a payment journal that you entered earlier, select **Lines**.</span></span>
3. <span data-ttu-id="eafb3-188">Na página **Pagamentos do fornecedor**, selecione todas as linhas na grade.</span><span class="sxs-lookup"><span data-stu-id="eafb3-188">On the **Vendor payments** page, select all rows in the grid.</span></span>
4. <span data-ttu-id="eafb3-189">Selecione o **Status do pagamento** \> **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="eafb3-189">Select **Payment status** \> **None**.</span></span>

    ![Pagamentos para processar na página Pagamentos do fornecedor](../media/er-design-configuration-word-2016-11-image05.png)

5. <span data-ttu-id="eafb3-191">No Painel de Ações, selecione **Gerar pagamentos**.</span><span class="sxs-lookup"><span data-stu-id="eafb3-191">On the Action Pane, select **Generate payments**.</span></span>
6. <span data-ttu-id="eafb3-192">Na caixa de diálogo que aparece, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="eafb3-192">In the dialog box that appears, follow these steps:</span></span>

    1. <span data-ttu-id="eafb3-193">No campo **Método de pagamento**, selecione **Eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="eafb3-193">In the **Method of payment** field, select **Electronic**.</span></span>
    2. <span data-ttu-id="eafb3-194">No campo **Conta bancária**, selecione **GBSI OPER**.</span><span class="sxs-lookup"><span data-stu-id="eafb3-194">In the **Bank account** field, select **GBSI OPER**.</span></span>
    3. <span data-ttu-id="eafb3-195">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="eafb3-195">Select **OK**.</span></span>

7. <span data-ttu-id="eafb3-196">Na caixa de diálogo **Parâmetros de relatório eletrônico**, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="eafb3-196">In the **Electronic report parameters** dialog box, select **OK**.</span></span>
8. <span data-ttu-id="eafb3-197">A saída criada é apresentada no formato Word e contém os detalhes dos pagamentos processados.</span><span class="sxs-lookup"><span data-stu-id="eafb3-197">The generated output is presented in Word format and contains the details of the processed payments.</span></span> <span data-ttu-id="eafb3-198">Analise a saída gerada.</span><span class="sxs-lookup"><span data-stu-id="eafb3-198">Analyze the generated output.</span></span>

    ![Saída gerada no formato Word](../media/er-design-configuration-word-2016-11-image06.png)

## <a name="additional-resources"></a><span data-ttu-id="eafb3-200">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="eafb3-200">Additional resources</span></span>

- [<span data-ttu-id="eafb3-201">Criar uma nova configuração de (ER) para gerar relatórios no formato Word</span><span class="sxs-lookup"><span data-stu-id="eafb3-201">Design a new ER configuration to generate reports in Word format</span></span>](../er-design-configuration-word.md)
- [<span data-ttu-id="eafb3-202">Inserir imagens e formas em documentos que você gerar usando ER</span><span class="sxs-lookup"><span data-stu-id="eafb3-202">Embed images and shapes in documents that you generate by using ER</span></span>](../electronic-reporting-embed-images-shapes.md#embed-an-image-in-a-word-document)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
---
title: Criar configurações de ER para gerar relatórios no formato do Word
description: As etapas a seguir explicam como um usuário na função de administrador do sistema ou de desenvolvedor de relatórios eletrônicos pode configurar um formato de relatório eletrônico para gerar relatórios como arquivos do Microsoft Word.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner,  LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fd138fb5fea4098a862fbecba5e8ec226ed6afa9
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/02/2019
ms.locfileid: "1850294"
---
# <a name="design-er-configurations-to-generate-reports-in-word-format"></a><span data-ttu-id="78aa0-103">Criar configurações de ER para gerar relatórios no formato do Word</span><span class="sxs-lookup"><span data-stu-id="78aa0-103">Design ER configurations to generate reports in Word format</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="78aa0-104">As etapas a seguir explicam como um usuário na função de administrador do sistema ou de desenvolvedor de relatórios eletrônicos pode configurar um formato de relatório eletrônico (ER) para gerar relatórios como arquivos do Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="78aa0-104">The following steps explain how a user in either the System administrator or Electronic reporting developer role can configure an Electronic reporting (ER) formats to generate reports as Microsoft Word files.</span></span> <span data-ttu-id="78aa0-105">Essas etapas podem ser executadas na empresa GBSI.</span><span class="sxs-lookup"><span data-stu-id="78aa0-105">These steps can be performed in the GBSI company.</span></span>

<span data-ttu-id="78aa0-106">Para completar essas etapas, você deve primeiro concluí-las na guia de tarefas "Criar uma configuração ER para gerar relatórios no formato OPENXML".</span><span class="sxs-lookup"><span data-stu-id="78aa0-106">To complete these steps, you must first complete the steps in the “Create an ER configuration for generating reports in OPENXML format” task guide.</span></span> <span data-ttu-id="78aa0-107">Com antecedência, você também precisa baixar e salvar os seguintes modelos localmente para o modelo de relatório:</span><span class="sxs-lookup"><span data-stu-id="78aa0-107">In advance, you must also download and save the following templates locally for the sample report:</span></span>

- [<span data-ttu-id="78aa0-108">Modelo de relatório de pagamento</span><span class="sxs-lookup"><span data-stu-id="78aa0-108">Template of Payment Report</span></span>](https://go.microsoft.com/fwlink/?linkid=862266)
- [<span data-ttu-id="78aa0-109">Modelo limitado de relatório de pagamento</span><span class="sxs-lookup"><span data-stu-id="78aa0-109">Bounded Template of Payment Report</span></span>](https://go.microsoft.com/fwlink/?linkid=862266)


<span data-ttu-id="78aa0-110">Este procedimento é para um recurso que foi adicionado na versão 1611 do Microsoft Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="78aa0-110">This procedure is for a feature that was added in Microsoft Dynamics 365 for Operations version 1611.</span></span>


## <a name="select-the-existing-er-report-configuration"></a><span data-ttu-id="78aa0-111">Selecionar a configuração de relatório de ER existente</span><span class="sxs-lookup"><span data-stu-id="78aa0-111">Select the existing ER report configuration</span></span>
1. <span data-ttu-id="78aa0-112">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="78aa0-112">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="78aa0-113">Verifique se o provedor de configuração "Litware, Inc."</span><span class="sxs-lookup"><span data-stu-id="78aa0-113">Make sure that the configuration provider ‘Litware, Inc.’</span></span> <span data-ttu-id="78aa0-114">está selecionado como ativo.</span><span class="sxs-lookup"><span data-stu-id="78aa0-114">is selected as active.</span></span>  
2. <span data-ttu-id="78aa0-115">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="78aa0-115">Click Reporting configurations.</span></span>
    * <span data-ttu-id="78aa0-116">Reutilizaremos a configuração ER existente que foi originalmente criada para gerar a saída de relatório no formato OPENXML.</span><span class="sxs-lookup"><span data-stu-id="78aa0-116">We will re-use the existing ER configuration that has been originally designed to generate the report output in OPENXML format.</span></span>  
3. <span data-ttu-id="78aa0-117">Na árvore, expanda 'Modelo de pagamento'.</span><span class="sxs-lookup"><span data-stu-id="78aa0-117">In the tree, expand 'Payment model'.</span></span>
4. <span data-ttu-id="78aa0-118">Na árvore, selecione "Modelo de pagamento\Relatório de planilha de amostra".</span><span class="sxs-lookup"><span data-stu-id="78aa0-118">In the tree, select 'Payment model\Sample worksheet report'.</span></span>
5. <span data-ttu-id="78aa0-119">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="78aa0-119">Click Designer.</span></span>

## <a name="replace-the-excel-template-with-the-word-template"></a><span data-ttu-id="78aa0-120">Substituir o modelo do Excel pelo modelo do Word</span><span class="sxs-lookup"><span data-stu-id="78aa0-120">Replace the Excel template with the Word template</span></span>
    * <span data-ttu-id="78aa0-121">Atualmente, o documento do Excel é usado como modelo para gerar a saída no formato OPENXML.</span><span class="sxs-lookup"><span data-stu-id="78aa0-121">Currently, the Excel document is used as a template to generate the output in OPENXML format.</span></span> <span data-ttu-id="78aa0-122">Importaremos o modelo do relatório no formato Word.</span><span class="sxs-lookup"><span data-stu-id="78aa0-122">We will import the report’s template in Word format.</span></span>  
1. <span data-ttu-id="78aa0-123">Clique em Anexos.</span><span class="sxs-lookup"><span data-stu-id="78aa0-123">Click Attachments.</span></span>
    * <span data-ttu-id="78aa0-124">Substitua o modelo do Excel existente pelo modelo do Word que você baixou antes: SampleVendPaymDocReport.docx.</span><span class="sxs-lookup"><span data-stu-id="78aa0-124">Replace the existing Excel template with the Word template that you downloaded earlier, SampleVendPaymDocReport.docx.</span></span> <span data-ttu-id="78aa0-125">Observe que esse modelo contém apenas o layout do documento que desejamos gerar como saída de ER.</span><span class="sxs-lookup"><span data-stu-id="78aa0-125">Note, this template only contains the layout of the document we want to generate as ER output.</span></span>  
2. <span data-ttu-id="78aa0-126">Clique em Excluir.</span><span class="sxs-lookup"><span data-stu-id="78aa0-126">Click Delete.</span></span>
3. <span data-ttu-id="78aa0-127">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="78aa0-127">Click Yes.</span></span>
4. <span data-ttu-id="78aa0-128">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="78aa0-128">Click New.</span></span>
5. <span data-ttu-id="78aa0-129">Clique em Arquivo.</span><span class="sxs-lookup"><span data-stu-id="78aa0-129">Click File.</span></span>
6. <span data-ttu-id="78aa0-130">Clique em Procurar.</span><span class="sxs-lookup"><span data-stu-id="78aa0-130">Click Browse.</span></span> <span data-ttu-id="78aa0-131">Procure e selecione o arquivo SampleVendPaymDocReport.docx que você baixou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="78aa0-131">Navigate to and select SampleVendPaymDocReport.docx that you previously downloaded.</span></span> <span data-ttu-id="78aa0-132">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="78aa0-132">Click OK.</span></span>
    * <span data-ttu-id="78aa0-133">Selecione o modelo que você baixou na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="78aa0-133">Select the template that you downloaded in the previous step.</span></span>  
7. <span data-ttu-id="78aa0-134">No campo Modelo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="78aa0-134">In the Template field, enter or select a value.</span></span>

## <a name="extend-the-word-template-by-adding-a-custom-xml-part"></a><span data-ttu-id="78aa0-135">Estender o modelo do Word adicionando uma parte XML personalizada</span><span class="sxs-lookup"><span data-stu-id="78aa0-135">Extend the Word template by adding a custom XML part</span></span>
1. <span data-ttu-id="78aa0-136">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="78aa0-136">Click Save.</span></span>
    * <span data-ttu-id="78aa0-137">Além de armazenar alterações de configuração, a ação Salvar também atualiza o modelo do Word anexo.</span><span class="sxs-lookup"><span data-stu-id="78aa0-137">In addition to storing configuration changes, the Save action also updates the attached Word template.</span></span> <span data-ttu-id="78aa0-138">A estrutura do formato criado é transferida ao documento do Word anexo como nova parte XML personalizada com o nome "Relatório".</span><span class="sxs-lookup"><span data-stu-id="78aa0-138">The structure of the designed format is ported to the attached Word document as a new custom XML part with the name ‘Report’.</span></span> <span data-ttu-id="78aa0-139">Observe que o modelo do Word anexo contém não só o layout do documento que desejamos gerar como saída de ER, como também contém a estrutura dos dados que o ER preencherá nesse modelo no momento da execução.</span><span class="sxs-lookup"><span data-stu-id="78aa0-139">Note that the attached Word template contains not only the layout of the document we want to generate as ER output, it also contains the structure of data that ER will populate into this template at runtime.</span></span>  
2. <span data-ttu-id="78aa0-140">Clique em Anexos.</span><span class="sxs-lookup"><span data-stu-id="78aa0-140">Click Attachments.</span></span>
    * <span data-ttu-id="78aa0-141">Agora você precisa associar os elementos da parte XML personalizada "Relatório" às partes do documento do Word.</span><span class="sxs-lookup"><span data-stu-id="78aa0-141">Now you need to bind the elements of the custom XML part ‘Report’ to the Word document parts.</span></span>  
    * <span data-ttu-id="78aa0-142">Se estiver familiarizado com documentos do Word que podem ser criados como formulários contendo controles associados a elementos das partes XML personalizadas, siga todas as etapas da próxima subtarefa para criar esse documento.</span><span class="sxs-lookup"><span data-stu-id="78aa0-142">If you're familiar with Word documents that can be designed as forms containing content controls that are bounded with elements of custom XML parts – play all steps of the next sub-task to create such a document.</span></span> <span data-ttu-id="78aa0-143">Para obter mais detalhes, consulte este link https://support.office.com/article/Create-forms-that-users-complete-or-print-in-Word-040c5cc1-e309-445b-94ac-542f732c8c8b?ui=en-US&rs=en-US&ad=US.</span><span class="sxs-lookup"><span data-stu-id="78aa0-143">For more details, see this link https://support.office.com/article/Create-forms-that-users-complete-or-print-in-Word-040c5cc1-e309-445b-94ac-542f732c8c8b?ui=en-US&rs=en-US&ad=US.</span></span> <span data-ttu-id="78aa0-144">Caso contrário, ignore todas as etapas na próxima subtarefa.</span><span class="sxs-lookup"><span data-stu-id="78aa0-144">Otherwise, skip all the steps in the next sub-task.</span></span>  

## <a name="get-word-with-custom-xml-part-to-do-data-bindings"></a><span data-ttu-id="78aa0-145">Obter o Word com a parte XML personalizada para realizar associações de dados</span><span class="sxs-lookup"><span data-stu-id="78aa0-145">Get Word with custom XML part to do data bindings</span></span>
    * <span data-ttu-id="78aa0-146">Abra este documento no Word e faça o seguinte: - Abra a guia Desenvolvedor do Word (personalize a faixa de opções se ela ainda não estiver habilitada).</span><span class="sxs-lookup"><span data-stu-id="78aa0-146">Open this document in Word and do the following:  - Open the Word Developer tab (customize the ribbon if it is not enabled yet).</span></span>  <span data-ttu-id="78aa0-147">- Selecione o painel de mapeamento do XML.</span><span class="sxs-lookup"><span data-stu-id="78aa0-147">- Select XML mapping pane.</span></span>  <span data-ttu-id="78aa0-148">- Selecione a parte XML personalizada "Relatório" na pesquisa.</span><span class="sxs-lookup"><span data-stu-id="78aa0-148">- Select the ‘Report’ custom XML part in the lookup.</span></span>  <span data-ttu-id="78aa0-149">- Realize o mapeamento dos elementos da parte personalizada selecionada e os controles de conteúdo do documento do Word.</span><span class="sxs-lookup"><span data-stu-id="78aa0-149">- Do mapping of the elements of the selected custom XML part and content controls of the Word document.</span></span>  <span data-ttu-id="78aa0-150">- Salve o documento do Word atualizado em uma unidade local.</span><span class="sxs-lookup"><span data-stu-id="78aa0-150">- Save the updated Word document on a local drive.</span></span>  

## <a name="upload-the-word-template-with-custom-xml-part-bounded-to-content-controls"></a><span data-ttu-id="78aa0-151">Atualizar o modelo do Word com a parte XML personalizada associada a controles de conteúdo</span><span class="sxs-lookup"><span data-stu-id="78aa0-151">Upload the Word template with custom XML part bounded to content controls</span></span>
1. <span data-ttu-id="78aa0-152">Clique em Excluir.</span><span class="sxs-lookup"><span data-stu-id="78aa0-152">Click Delete.</span></span>
2. <span data-ttu-id="78aa0-153">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="78aa0-153">Click Yes.</span></span>
    * <span data-ttu-id="78aa0-154">Adicione um novo modelo.</span><span class="sxs-lookup"><span data-stu-id="78aa0-154">Add a new template.</span></span> <span data-ttu-id="78aa0-155">Se você completou as etapas da subtarefa anterior, selecione o documento do Word que você preparou e salvou localmente.</span><span class="sxs-lookup"><span data-stu-id="78aa0-155">If you competed the steps in the previous subtask, select the Word document that you prepared and saved locally.</span></span> <span data-ttu-id="78aa0-156">Caso contrário, selecione o modelo do MS Word SampleVendPaymDocReportBounded.docx que você baixou antes.</span><span class="sxs-lookup"><span data-stu-id="78aa0-156">Otherwise, select the SampleVendPaymDocReportBounded.docx MS Word template that you downloaded earlier.</span></span>  
3. <span data-ttu-id="78aa0-157">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="78aa0-157">Click New.</span></span>
4. <span data-ttu-id="78aa0-158">Clique em Arquivo.</span><span class="sxs-lookup"><span data-stu-id="78aa0-158">Click File.</span></span>
5. <span data-ttu-id="78aa0-159">Clique em Procurar.</span><span class="sxs-lookup"><span data-stu-id="78aa0-159">Click Browse.</span></span> <span data-ttu-id="78aa0-160">Procure e selecione o arquivo SampleVendPaymDocReportBounded.docx que você baixou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="78aa0-160">Navigate to and select SampleVendPaymDocReportBounded.docx that you previously downloaded.</span></span> <span data-ttu-id="78aa0-161">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="78aa0-161">Click OK.</span></span>
6. <span data-ttu-id="78aa0-162">No campo Modelo, selecione o documento que você baixou na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="78aa0-162">In the Template field, select the document that you downloaded in the previous step.</span></span>
7. <span data-ttu-id="78aa0-163">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="78aa0-163">Click Save.</span></span>
8. <span data-ttu-id="78aa0-164">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="78aa0-164">Close the page.</span></span>

## <a name="execute-the-format-to-create-word-output"></a><span data-ttu-id="78aa0-165">Executar o formato para criar a saída do Word</span><span class="sxs-lookup"><span data-stu-id="78aa0-165">Execute the format to create Word output</span></span>
1. <span data-ttu-id="78aa0-166">No Painel de Ação, clique em Configurações.</span><span class="sxs-lookup"><span data-stu-id="78aa0-166">On the Action Pane, click Configurations.</span></span>
2. <span data-ttu-id="78aa0-167">Clique em Parâmetros de usuário.</span><span class="sxs-lookup"><span data-stu-id="78aa0-167">Click User parameters.</span></span>
3. <span data-ttu-id="78aa0-168">Selecione Sim no campo Executar configurações.</span><span class="sxs-lookup"><span data-stu-id="78aa0-168">Select Yes in the Run settings field.</span></span>
4. <span data-ttu-id="78aa0-169">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="78aa0-169">Click OK.</span></span>
5. <span data-ttu-id="78aa0-170">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="78aa0-170">Click Edit.</span></span>
6. <span data-ttu-id="78aa0-171">Selecione Sim no campo Executar Rascunho.</span><span class="sxs-lookup"><span data-stu-id="78aa0-171">Select Yes in the Run Draft field.</span></span>
7. <span data-ttu-id="78aa0-172">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="78aa0-172">Click Save.</span></span>
8. <span data-ttu-id="78aa0-173">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="78aa0-173">Close the page.</span></span>
9. <span data-ttu-id="78aa0-174">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="78aa0-174">Close the page.</span></span>
10. <span data-ttu-id="78aa0-175">Vá para Contas a pagar > Pagamentos > Diário de pagamentos.</span><span class="sxs-lookup"><span data-stu-id="78aa0-175">Go to Accounts payable > Payments > Payment journal.</span></span>
11. <span data-ttu-id="78aa0-176">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="78aa0-176">Click Lines.</span></span>
12. <span data-ttu-id="78aa0-177">Na lista, marque ou desmarque todas as linhas.</span><span class="sxs-lookup"><span data-stu-id="78aa0-177">In the list, mark or unmark all rows.</span></span>
13. <span data-ttu-id="78aa0-178">Clique em Status do pagamento.</span><span class="sxs-lookup"><span data-stu-id="78aa0-178">Click Payment status.</span></span>
14. <span data-ttu-id="78aa0-179">Clique em Nenhum.</span><span class="sxs-lookup"><span data-stu-id="78aa0-179">Click None.</span></span>
15. <span data-ttu-id="78aa0-180">Clique em Gerar pagamentos.</span><span class="sxs-lookup"><span data-stu-id="78aa0-180">Click Generate payments.</span></span>
16. <span data-ttu-id="78aa0-181">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="78aa0-181">Click OK.</span></span>
17. <span data-ttu-id="78aa0-182">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="78aa0-182">Click OK.</span></span>
    * <span data-ttu-id="78aa0-183">Analise a saída gerada.</span><span class="sxs-lookup"><span data-stu-id="78aa0-183">Analyze the generated output.</span></span> <span data-ttu-id="78aa0-184">Observe que a saída criada é apresentada no formato Word e contém os detalhes dos pagamentos processados.</span><span class="sxs-lookup"><span data-stu-id="78aa0-184">Note that the created output is presented in Word format and contains the details of the processed payments.</span></span>  


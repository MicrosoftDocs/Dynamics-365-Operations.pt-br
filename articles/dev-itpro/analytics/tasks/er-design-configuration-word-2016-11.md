--- 
title: "Criar uma configuração para gerar relatórios no formato Microsoft Word para relatório eletrônico (ER)"
description: "As seguintes etapas explicam como um usuário na função de administrador do sistema ou desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para criar relatórios como arquivos do Microsoft Word."
author: NickSelin
manager: AnnBe
ms.date: 12/21/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: d602e07548d22bcdee3f375c3c327c0e8963c3b4
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="design-a-configuration-for-generating-reports-in-microsoft-word-format-for-electronic-reporting-er"></a><span data-ttu-id="feb50-103">Criar uma configuração para gerar relatórios no formato Microsoft Word para relatório eletrônico (ER)</span><span class="sxs-lookup"><span data-stu-id="feb50-103">Design a configuration for generating reports in Microsoft Word format for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="feb50-104">As seguintes etapas explicam como um usuário na função de administrador do sistema ou desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para criar relatórios como arquivos do Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="feb50-104">The following steps explain how a user in either the System administrator or Electronic reporting developer role can configure an Electronic reporting (ER) formats to generate reports as Microsoft Word files.</span></span> <span data-ttu-id="feb50-105">Essas etapas podem ser executadas na empresa GBSI.</span><span class="sxs-lookup"><span data-stu-id="feb50-105">These steps can be performed in the GBSI company.</span></span>

<span data-ttu-id="feb50-106">Para completar essas etapas, você deve primeiro concluí-las na guia de tarefas "Criar uma configuração ER para gerar relatórios no formato OPENXML".</span><span class="sxs-lookup"><span data-stu-id="feb50-106">To complete these steps, you must first complete the steps in the “Create an ER configuration for generating reports in OPENXML format” task guide.</span></span> <span data-ttu-id="feb50-107">Com antecedência, você também precisa baixar e salvar os seguintes modelos localmente para o modelo de relatório:</span><span class="sxs-lookup"><span data-stu-id="feb50-107">In advance, you must also download and save the following templates locally for the sample report:</span></span>

<span data-ttu-id="feb50-108">http://msdynamics.blob.core.windows.net/media/2016/10/SampleVendPaymDocReport.docx</span><span class="sxs-lookup"><span data-stu-id="feb50-108">http://msdynamics.blob.core.windows.net/media/2016/10/SampleVendPaymDocReport.docx</span></span>

<span data-ttu-id="feb50-109">http://msdynamics.blob.core.windows.net/media/2016/10/SampleVendPaymDocReportBounded.docx</span><span class="sxs-lookup"><span data-stu-id="feb50-109">http://msdynamics.blob.core.windows.net/media/2016/10/SampleVendPaymDocReportBounded.docx</span></span>

<span data-ttu-id="feb50-110">Este procedimento é para um recurso que foi adicionado à versão 1611 do Microsoft Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="feb50-110">This procedure is for a feature that was added in Microsoft Dynamics 365 for Operations version 1611.</span></span>


## <a name="select-the-existing-er-report-configuration"></a><span data-ttu-id="feb50-111">Selecionar a configuração de relatório de ER existente</span><span class="sxs-lookup"><span data-stu-id="feb50-111">Select the existing ER report configuration</span></span>
1. <span data-ttu-id="feb50-112">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="feb50-112">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="feb50-113">Verifique se o provedor de configuração "Litware, Inc."</span><span class="sxs-lookup"><span data-stu-id="feb50-113">Make sure that the configuration provider ‘Litware, Inc.’</span></span> <span data-ttu-id="feb50-114">está selecionado como ativo.</span><span class="sxs-lookup"><span data-stu-id="feb50-114">is selected as active.</span></span>  
2. <span data-ttu-id="feb50-115">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="feb50-115">Click Reporting configurations.</span></span>
    * <span data-ttu-id="feb50-116">Reutilizaremos a configuração ER existente que foi originalmente criada para gerar a saída de relatório no formato OPENXML.</span><span class="sxs-lookup"><span data-stu-id="feb50-116">We will re-use the existing ER configuration that has been originally designed to generate the report output in OPENXML format.</span></span>  
3. <span data-ttu-id="feb50-117">Na árvore, expanda 'Modelo de pagamento'.</span><span class="sxs-lookup"><span data-stu-id="feb50-117">In the tree, expand 'Payment model'.</span></span>
4. <span data-ttu-id="feb50-118">Na árvore, selecione "Modelo de pagamento\Relatório de planilha de amostra".</span><span class="sxs-lookup"><span data-stu-id="feb50-118">In the tree, select 'Payment model\Sample worksheet report'.</span></span>
5. <span data-ttu-id="feb50-119">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="feb50-119">Click Designer.</span></span>

## <a name="replace-the-excel-template-with-the-word-template"></a><span data-ttu-id="feb50-120">Substituir o modelo do Excel pelo modelo do Word</span><span class="sxs-lookup"><span data-stu-id="feb50-120">Replace the Excel template with the Word template</span></span>
    * <span data-ttu-id="feb50-121">Atualmente, o documento do Excel é usado como modelo para gerar a saída no formato OPENXML.</span><span class="sxs-lookup"><span data-stu-id="feb50-121">Currently, the Excel document is used as a template to generate the output in OPENXML format.</span></span> <span data-ttu-id="feb50-122">Importaremos o modelo do relatório no formato Word.</span><span class="sxs-lookup"><span data-stu-id="feb50-122">We will import the report’s template in Word format.</span></span>  
1. <span data-ttu-id="feb50-123">Clique em Anexos.</span><span class="sxs-lookup"><span data-stu-id="feb50-123">Click Attachments.</span></span>
    * <span data-ttu-id="feb50-124">Substitua o modelo do Excel existente pelo modelo do Word que você baixou antes: SampleVendPaymDocReport.docx.</span><span class="sxs-lookup"><span data-stu-id="feb50-124">Replace the existing Excel template with the Word template that you downloaded earlier, SampleVendPaymDocReport.docx.</span></span> <span data-ttu-id="feb50-125">Observe que esse modelo contém apenas o layout do documento que desejamos gerar como saída de ER.</span><span class="sxs-lookup"><span data-stu-id="feb50-125">Note, this template only contains the layout of the document we want to generate as ER output.</span></span>  
2. <span data-ttu-id="feb50-126">Clique em Excluir.</span><span class="sxs-lookup"><span data-stu-id="feb50-126">Click Delete.</span></span>
3. <span data-ttu-id="feb50-127">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="feb50-127">Click Yes.</span></span>
4. <span data-ttu-id="feb50-128">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="feb50-128">Click New.</span></span>
5. <span data-ttu-id="feb50-129">Clique em Arquivo.</span><span class="sxs-lookup"><span data-stu-id="feb50-129">Click File.</span></span>
6. <span data-ttu-id="feb50-130">Clique em Procurar.</span><span class="sxs-lookup"><span data-stu-id="feb50-130">Click Browse.</span></span> <span data-ttu-id="feb50-131">Procure e selecione o arquivo SampleVendPaymDocReport.docx que você baixou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="feb50-131">Navigate to and select SampleVendPaymDocReport.docx that you previously downloaded.</span></span> <span data-ttu-id="feb50-132">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="feb50-132">Click OK.</span></span>
    * <span data-ttu-id="feb50-133">Selecione o modelo que você baixou na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="feb50-133">Select the template that you downloaded in the previous step.</span></span>  
7. <span data-ttu-id="feb50-134">No campo Modelo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="feb50-134">In the Template field, enter or select a value.</span></span>

## <a name="extend-the-word-template-by-adding-a-custom-xml-part"></a><span data-ttu-id="feb50-135">Estender o modelo do Word adicionando uma parte XML personalizada</span><span class="sxs-lookup"><span data-stu-id="feb50-135">Extend the Word template by adding a custom XML part</span></span>
1. <span data-ttu-id="feb50-136">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="feb50-136">Click Save.</span></span>
    * <span data-ttu-id="feb50-137">Além de armazenar alterações de configuração, a ação Salvar também atualiza o modelo do Word anexo.</span><span class="sxs-lookup"><span data-stu-id="feb50-137">In addition to storing configuration changes, the Save action also updates the attached Word template.</span></span> <span data-ttu-id="feb50-138">A estrutura do formato criado é transferida ao documento do Word anexo como nova parte XML personalizada com o nome "Relatório".</span><span class="sxs-lookup"><span data-stu-id="feb50-138">The structure of the designed format is ported to the attached Word document as a new custom XML part with the name ‘Report’.</span></span> <span data-ttu-id="feb50-139">Observe que o modelo do Word anexo contém não só o layout do documento que desejamos gerar como saída de ER, como também contém a estrutura dos dados que o ER preencherá nesse modelo no momento da execução.</span><span class="sxs-lookup"><span data-stu-id="feb50-139">Note that the attached Word template contains not only the layout of the document we want to generate as ER output, it also contains the structure of data that ER will populate into this template at runtime.</span></span>  
2. <span data-ttu-id="feb50-140">Clique em Anexos.</span><span class="sxs-lookup"><span data-stu-id="feb50-140">Click Attachments.</span></span>
    * <span data-ttu-id="feb50-141">Agora você precisa associar os elementos da parte XML personalizada "Relatório" às partes do documento do Word.</span><span class="sxs-lookup"><span data-stu-id="feb50-141">Now you need to bind the elements of the custom XML part ‘Report’ to the Word document parts.</span></span>  
    * <span data-ttu-id="feb50-142">Se estiver familiarizado com documentos do Word que podem ser criados como formulários contendo controles associados a elementos das partes XML personalizadas, siga todas as etapas da próxima subtarefa para criar esse documento.</span><span class="sxs-lookup"><span data-stu-id="feb50-142">If you're familiar with Word documents that can be designed as forms containing content controls that are bounded with elements of custom XML parts – play all steps of the next sub-task to create such a document.</span></span> <span data-ttu-id="feb50-143">Para obter mais detalhes, consulte este link https://support.office.com/en-us/article/Create-forms-that-users-complete-or-print-in-Word-040c5cc1-e309-445b-94ac-542f732c8c8b?ui=en-US&rs=en-US&ad=US.</span><span class="sxs-lookup"><span data-stu-id="feb50-143">For more details, see this link https://support.office.com/en-us/article/Create-forms-that-users-complete-or-print-in-Word-040c5cc1-e309-445b-94ac-542f732c8c8b?ui=en-US&rs=en-US&ad=US.</span></span> <span data-ttu-id="feb50-144">Caso contrário, ignore todas as etapas na próxima subtarefa.</span><span class="sxs-lookup"><span data-stu-id="feb50-144">Otherwise, skip all the steps in the next sub-task.</span></span>  

## <a name="get-word-with-custom-xml-part-to-do-data-bindings"></a><span data-ttu-id="feb50-145">Obter o Word com a parte XML personalizada para realizar associações de dados</span><span class="sxs-lookup"><span data-stu-id="feb50-145">Get Word with custom XML part to do data bindings</span></span>
    * <span data-ttu-id="feb50-146">Abra este documento no Word e faça o seguinte: - Abra a guia Desenvolvedor do Word (personalize a faixa de opções se ela ainda não estiver habilitada).</span><span class="sxs-lookup"><span data-stu-id="feb50-146">Open this document in Word and do the following:  - Open the Word Developer tab (customize the ribbon if it is not enabled yet).</span></span>  <span data-ttu-id="feb50-147">- Selecione o painel de mapeamento do XML.</span><span class="sxs-lookup"><span data-stu-id="feb50-147">- Select XML mapping pane.</span></span>  <span data-ttu-id="feb50-148">- Selecione a parte XML personalizada "Relatório" na pesquisa.</span><span class="sxs-lookup"><span data-stu-id="feb50-148">- Select the ‘Report’ custom XML part in the lookup.</span></span>  <span data-ttu-id="feb50-149">- Realize o mapeamento dos elementos da parte personalizada selecionada e os controles de conteúdo do documento do Word.</span><span class="sxs-lookup"><span data-stu-id="feb50-149">- Do mapping of the elements of the selected custom XML part and content controls of the Word document.</span></span>  <span data-ttu-id="feb50-150">- Salve o documento do Word atualizado em uma unidade local.</span><span class="sxs-lookup"><span data-stu-id="feb50-150">- Save the updated Word document on a local drive.</span></span>  

## <a name="upload-the-word-template-with-custom-xml-part-bounded-to-content-controls"></a><span data-ttu-id="feb50-151">Atualizar o modelo do Word com a parte XML personalizada associada a controles de conteúdo</span><span class="sxs-lookup"><span data-stu-id="feb50-151">Upload the Word template with custom XML part bounded to content controls</span></span>
1. <span data-ttu-id="feb50-152">Clique em Excluir.</span><span class="sxs-lookup"><span data-stu-id="feb50-152">Click Delete.</span></span>
2. <span data-ttu-id="feb50-153">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="feb50-153">Click Yes.</span></span>
    * <span data-ttu-id="feb50-154">Adicione um novo modelo.</span><span class="sxs-lookup"><span data-stu-id="feb50-154">Add a new template.</span></span> <span data-ttu-id="feb50-155">Se você completou as etapas da subtarefa anterior, selecione o documento do Word que você preparou e salvou localmente.</span><span class="sxs-lookup"><span data-stu-id="feb50-155">If you competed the steps in the previous subtask, select the Word document that you prepared and saved locally.</span></span> <span data-ttu-id="feb50-156">Caso contrário, selecione o modelo do MS Word SampleVendPaymDocReportBounded.docx que você baixou antes.</span><span class="sxs-lookup"><span data-stu-id="feb50-156">Otherwise, select the SampleVendPaymDocReportBounded.docx MS Word template that you downloaded earlier.</span></span>  
3. <span data-ttu-id="feb50-157">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="feb50-157">Click New.</span></span>
4. <span data-ttu-id="feb50-158">Clique em Arquivo.</span><span class="sxs-lookup"><span data-stu-id="feb50-158">Click File.</span></span>
5. <span data-ttu-id="feb50-159">Clique em Procurar.</span><span class="sxs-lookup"><span data-stu-id="feb50-159">Click Browse.</span></span> <span data-ttu-id="feb50-160">Procure e selecione o arquivo SampleVendPaymDocReportBounded.docx que você baixou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="feb50-160">Navigate to and select SampleVendPaymDocReportBounded.docx that you previously downloaded.</span></span> <span data-ttu-id="feb50-161">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="feb50-161">Click OK.</span></span>
6. <span data-ttu-id="feb50-162">No campo Modelo, selecione o documento que você baixou na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="feb50-162">In the Template field, select the document that you downloaded in the previous step.</span></span>
7. <span data-ttu-id="feb50-163">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="feb50-163">Click Save.</span></span>
8. <span data-ttu-id="feb50-164">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="feb50-164">Close the page.</span></span>

## <a name="execute-the-format-to-create-word-output"></a><span data-ttu-id="feb50-165">Executar o formato para criar a saída do Word</span><span class="sxs-lookup"><span data-stu-id="feb50-165">Execute the format to create Word output</span></span>
1. <span data-ttu-id="feb50-166">No Painel de Ação, clique em Configurações.</span><span class="sxs-lookup"><span data-stu-id="feb50-166">On the Action Pane, click Configurations.</span></span>
2. <span data-ttu-id="feb50-167">Clique em Parâmetros de usuário.</span><span class="sxs-lookup"><span data-stu-id="feb50-167">Click User parameters.</span></span>
3. <span data-ttu-id="feb50-168">Selecione Sim no campo Executar configurações.</span><span class="sxs-lookup"><span data-stu-id="feb50-168">Select Yes in the Run settings field.</span></span>
4. <span data-ttu-id="feb50-169">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="feb50-169">Click OK.</span></span>
5. <span data-ttu-id="feb50-170">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="feb50-170">Click Edit.</span></span>
6. <span data-ttu-id="feb50-171">Selecione Sim no campo Executar Rascunho.</span><span class="sxs-lookup"><span data-stu-id="feb50-171">Select Yes in the Run Draft field.</span></span>
7. <span data-ttu-id="feb50-172">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="feb50-172">Click Save.</span></span>
8. <span data-ttu-id="feb50-173">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="feb50-173">Close the page.</span></span>
9. <span data-ttu-id="feb50-174">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="feb50-174">Close the page.</span></span>
10. <span data-ttu-id="feb50-175">Vá para Contas a pagar > Pagamentos > Diário de pagamentos.</span><span class="sxs-lookup"><span data-stu-id="feb50-175">Go to Accounts payable > Payments > Payment journal.</span></span>
11. <span data-ttu-id="feb50-176">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="feb50-176">Click Lines.</span></span>
12. <span data-ttu-id="feb50-177">Na lista, marque ou desmarque todas as linhas.</span><span class="sxs-lookup"><span data-stu-id="feb50-177">In the list, mark or unmark all rows.</span></span>
13. <span data-ttu-id="feb50-178">Clique em Status do pagamento.</span><span class="sxs-lookup"><span data-stu-id="feb50-178">Click Payment status.</span></span>
14. <span data-ttu-id="feb50-179">Clique em Nenhum.</span><span class="sxs-lookup"><span data-stu-id="feb50-179">Click None.</span></span>
15. <span data-ttu-id="feb50-180">Clique em Gerar pagamentos.</span><span class="sxs-lookup"><span data-stu-id="feb50-180">Click Generate payments.</span></span>
16. <span data-ttu-id="feb50-181">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="feb50-181">Click OK.</span></span>
17. <span data-ttu-id="feb50-182">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="feb50-182">Click OK.</span></span>
    * <span data-ttu-id="feb50-183">Analise a saída gerada.</span><span class="sxs-lookup"><span data-stu-id="feb50-183">Analyze the generated output.</span></span> <span data-ttu-id="feb50-184">Observe que a saída criada é apresentada no formato Word e contém os detalhes dos pagamentos processados.</span><span class="sxs-lookup"><span data-stu-id="feb50-184">Note that the created output is presented in Word format and contains the details of the processed payments.</span></span>  



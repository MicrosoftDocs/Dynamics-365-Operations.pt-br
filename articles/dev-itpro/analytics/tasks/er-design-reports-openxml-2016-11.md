--- 
title: "Criar uma configuração para gerar relatórios no formato OpenXML para relatório eletrônico (ER)"
description: "As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma nova configuração de Relatório Eletrônico (RE) que contem um modelo para gerar os documentos eletrônicos no formato OPENXML."
author: NickSelin
manager: AnnBe
ms.date: 01/16/2017
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
ms.openlocfilehash: 04def14ddf9b079005bf11acbcaf64b21aa80fdb
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="design-a-configuration-for-generating-reports-in-openxml-format-for-electronic-reporting-er"></a><span data-ttu-id="59d0b-103">Criar uma configuração para gerar relatórios no formato OpenXML para relatório eletrônico (ER)</span><span class="sxs-lookup"><span data-stu-id="59d0b-103">Design a configuration for generating reports in OpenXML format for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="59d0b-104">As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma nova configuração de Relatório Eletrônico (RE) que contem um modelo para gerar os documentos eletrônicos no formato OPENXML.</span><span class="sxs-lookup"><span data-stu-id="59d0b-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a template for generating electronic documents in OPENXML format.</span></span> <span data-ttu-id="59d0b-105">Essa configuração será usada para processar pagamentos do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="59d0b-105">This configuration will be used for processing vendor payments.</span></span>



<span data-ttu-id="59d0b-106">Neste exemplo, você criará uma configuração para a empresa de exemplo, Litware, Inc. Estas etapas podem ser executadas na empresa GBSI.</span><span class="sxs-lookup"><span data-stu-id="59d0b-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in GBSI company.</span></span>



<span data-ttu-id="59d0b-107">Para completar essas etapas, você deve primeiro completar as etapas do procedimento “Criar um provedor de configuração e marcá-lo como ativo“.</span><span class="sxs-lookup"><span data-stu-id="59d0b-107">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span> <span data-ttu-id="59d0b-108">Você também deve ter um arquivo Excel que é importado ao criar o modelo.</span><span class="sxs-lookup"><span data-stu-id="59d0b-108">You must also have an Excel file which will be imported when creating the template.</span></span> <span data-ttu-id="59d0b-109">Este arquivo pode ser acessado de: https://msdynamics.blob.core.windows.net/media/2016/04/SampleVendPaymWsReport.xlsx</span><span class="sxs-lookup"><span data-stu-id="59d0b-109">This file can be accessed from:  https://msdynamics.blob.core.windows.net/media/2016/04/SampleVendPaymWsReport.xlsx</span></span>


## <a name="upload-the-payments-data-model-configuration"></a><span data-ttu-id="59d0b-110">Carregar a configuração do modelo de dados de pagamentos</span><span class="sxs-lookup"><span data-stu-id="59d0b-110">Upload the Payments data model configuration</span></span>
1. <span data-ttu-id="59d0b-111">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="59d0b-111">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="59d0b-112">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="59d0b-112">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="59d0b-113">Selecione o provedor de configuração para a empresa de exemplo, 'Litware, Inc.' Se você não visualizar o provedor de configuração, você deve primeiro concluir as etapas do procedimento “Criar um provedor de configuração e marcá-lo como ativo“.</span><span class="sxs-lookup"><span data-stu-id="59d0b-113">Select the configuration provider for sample company, Litware, Inc. If you don’t see this configuration provider, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>  
3. <span data-ttu-id="59d0b-114">Clique em Definir como ativo.</span><span class="sxs-lookup"><span data-stu-id="59d0b-114">Click Set active.</span></span>
4. <span data-ttu-id="59d0b-115">Clique em Repositórios.</span><span class="sxs-lookup"><span data-stu-id="59d0b-115">Click Repositories.</span></span>
    * <span data-ttu-id="59d0b-116">Selecione um repositório para o tipo Recursos de operações, se disponível.</span><span class="sxs-lookup"><span data-stu-id="59d0b-116">Select a repository for the Operations Resources type, if available.</span></span> <span data-ttu-id="59d0b-117">Se estiver disponível, pule as etapas a seguir sobre criar um novo repositório.</span><span class="sxs-lookup"><span data-stu-id="59d0b-117">If its available, skip the following steps about creating a new repository.</span></span>  
5. <span data-ttu-id="59d0b-118">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="59d0b-118">Click Add to open the drop dialog.</span></span>
6. <span data-ttu-id="59d0b-119">No campo Tipo de repositório de configuração, insira 'Recursos de operações'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-119">In the Configuration repository type field, enter 'Operations resources'.</span></span>
7. <span data-ttu-id="59d0b-120">Clique em Criar repositório.</span><span class="sxs-lookup"><span data-stu-id="59d0b-120">Click Create repository.</span></span>
8. <span data-ttu-id="59d0b-121">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="59d0b-121">Click OK.</span></span>
9. <span data-ttu-id="59d0b-122">Clique em Abrir.</span><span class="sxs-lookup"><span data-stu-id="59d0b-122">Click Open.</span></span>
10. <span data-ttu-id="59d0b-123">Na árvore, selecione 'Modelo de pagamento'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-123">In the tree, select 'Payment model'.</span></span>
11. <span data-ttu-id="59d0b-124">Clique em Importar.</span><span class="sxs-lookup"><span data-stu-id="59d0b-124">Click Import.</span></span>
    * <span data-ttu-id="59d0b-125">Importar este modelo de dados.</span><span class="sxs-lookup"><span data-stu-id="59d0b-125">Import this data model.</span></span> <span data-ttu-id="59d0b-126">Será usado como a fonte de dados em uma nova configuração de formato.</span><span class="sxs-lookup"><span data-stu-id="59d0b-126">It will be used as a data source in a new format configuration.</span></span> <span data-ttu-id="59d0b-127">Ignorar essa etapa se essa configuração já tiver sido importada.</span><span class="sxs-lookup"><span data-stu-id="59d0b-127">Skip this step if this configuration has been already imported.</span></span>  
12. <span data-ttu-id="59d0b-128">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="59d0b-128">Click Yes.</span></span>
13. <span data-ttu-id="59d0b-129">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="59d0b-129">Close the page.</span></span>
14. <span data-ttu-id="59d0b-130">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="59d0b-130">Close the page.</span></span>

## <a name="create-a-new-format-configuration"></a><span data-ttu-id="59d0b-131">Criar uma nova configuração de formato</span><span class="sxs-lookup"><span data-stu-id="59d0b-131">Create a new format configuration</span></span>
1. <span data-ttu-id="59d0b-132">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="59d0b-132">Click Reporting configurations.</span></span>
2. <span data-ttu-id="59d0b-133">Na árvore, selecione 'Modelo de pagamento'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-133">In the tree, select 'Payment model'.</span></span>
3. <span data-ttu-id="59d0b-134">Clique em Criar configuração para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="59d0b-134">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="59d0b-135">No campo Novo, insira 'Formato baseado no modelo de dados PaymentModel'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-135">In the New field, enter 'Format based on data model PaymentModel'.</span></span>
    * <span data-ttu-id="59d0b-136">Criar um formato com base no modelo de dados do PaymentModel.</span><span class="sxs-lookup"><span data-stu-id="59d0b-136">Create a format that is based on the PaymentModel data model.</span></span>  
5. <span data-ttu-id="59d0b-137">No campo Nome, digite "Relatório de planilha de exemplo".</span><span class="sxs-lookup"><span data-stu-id="59d0b-137">In the Name field, type 'Sample worksheet report'.</span></span>
    * <span data-ttu-id="59d0b-138">Relatório da planilha de exemplo</span><span class="sxs-lookup"><span data-stu-id="59d0b-138">Sample worksheet report</span></span>  
6. <span data-ttu-id="59d0b-139">No campo Tipo de descrição, digite "Relatório de planilha de amostra para pagamentos de fornecedor".</span><span class="sxs-lookup"><span data-stu-id="59d0b-139">In the Description field, type 'Sample worksheet report for vendors’ payments'.</span></span>
    * <span data-ttu-id="59d0b-140">Relatório de planilha de amostra para pagamentos do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="59d0b-140">Sample worksheet report for vendors’ payments.</span></span>  
7. <span data-ttu-id="59d0b-141">No campo Definição do modelo de dados, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="59d0b-141">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="59d0b-142">Selecione a definição "CustomerCreditTransferInitiation".</span><span class="sxs-lookup"><span data-stu-id="59d0b-142">Select the 'CustomerCreditTransferInitiation' definition.</span></span>  
8. <span data-ttu-id="59d0b-143">Clique em Criar configuração.</span><span class="sxs-lookup"><span data-stu-id="59d0b-143">Click Create configuration.</span></span>

## <a name="design-a-new-document-in-openxml-worksheet-format"></a><span data-ttu-id="59d0b-144">Criar um novo documento no formato da folha OPENXML</span><span class="sxs-lookup"><span data-stu-id="59d0b-144">Design a new document in OPENXML worksheet format</span></span>
1. <span data-ttu-id="59d0b-145">Na árvore, selecione "Modelo de pagamento\Relatório de planilha de amostra".</span><span class="sxs-lookup"><span data-stu-id="59d0b-145">In the tree, select 'Payment model\Sample worksheet report'.</span></span>
2. <span data-ttu-id="59d0b-146">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="59d0b-146">Click Designer.</span></span>
3. <span data-ttu-id="59d0b-147">No Painel de Ação, clique em Importar.</span><span class="sxs-lookup"><span data-stu-id="59d0b-147">On the Action Pane, click Import.</span></span>
4. <span data-ttu-id="59d0b-148">Clique em Importar do Excel.</span><span class="sxs-lookup"><span data-stu-id="59d0b-148">Click Import from Excel.</span></span>
5. <span data-ttu-id="59d0b-149">Clique em Anexos.</span><span class="sxs-lookup"><span data-stu-id="59d0b-149">Click Attachments.</span></span>
    * <span data-ttu-id="59d0b-150">Anexar o documento existente do Excel como um modelo.</span><span class="sxs-lookup"><span data-stu-id="59d0b-150">Attach the existing Excel document as a template.</span></span>  
6. <span data-ttu-id="59d0b-151">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="59d0b-151">Click New.</span></span>
7. <span data-ttu-id="59d0b-152">Clique em Arquivo.</span><span class="sxs-lookup"><span data-stu-id="59d0b-152">Click File.</span></span>
    * <span data-ttu-id="59d0b-153">Apontar para o arquivo existente do Excel.</span><span class="sxs-lookup"><span data-stu-id="59d0b-153">Point to the existing Excel file.</span></span>  
8. <span data-ttu-id="59d0b-154">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="59d0b-154">Close the page.</span></span>
9. <span data-ttu-id="59d0b-155">No campo Modelo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="59d0b-155">In the Template field, enter or select a value.</span></span>
    * <span data-ttu-id="59d0b-156">Selecione o arquivo Excel anexado a ser usado como um modelo.</span><span class="sxs-lookup"><span data-stu-id="59d0b-156">Select the attached Excel file to be used as a template.</span></span>  
10. <span data-ttu-id="59d0b-157">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="59d0b-157">Click OK.</span></span>
    * <span data-ttu-id="59d0b-158">Observe que os componentes do formato ER foram criados no formato criador com base na estrutura do documento de referência do MS Excel (intervalos nomeados).</span><span class="sxs-lookup"><span data-stu-id="59d0b-158">Note that ER format components have been created in the designing format based on the structure of the referring MS Excel document (named ranges).</span></span>  

## <a name="create-a-new-data-source-to-calculate-totals-by-currency-codes"></a><span data-ttu-id="59d0b-159">Criar uma nova fonte de dados para calcular totais por código de moeda</span><span class="sxs-lookup"><span data-stu-id="59d0b-159">Create a new data source to calculate totals by currency codes</span></span>
1. <span data-ttu-id="59d0b-160">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="59d0b-160">Click the Mapping tab.</span></span>
2. <span data-ttu-id="59d0b-161">Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="59d0b-161">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="59d0b-162">Na árvore, selecione 'Funções\Agrupar por'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-162">In the tree, select 'Functions\Group by'.</span></span>
4. <span data-ttu-id="59d0b-163">No campo Nome, digite 'PaymentByCurrency'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-163">In the Name field, type 'PaymentByCurrency'.</span></span>
    * <span data-ttu-id="59d0b-164">PaymentByCurrency</span><span class="sxs-lookup"><span data-stu-id="59d0b-164">PaymentByCurrency</span></span>  
5. <span data-ttu-id="59d0b-165">Clique em Editar grupo por.</span><span class="sxs-lookup"><span data-stu-id="59d0b-165">Click Edit group by.</span></span>
6. <span data-ttu-id="59d0b-166">Na árvore, expanda 'modelo'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-166">In the tree, expand 'model'.</span></span>
7. <span data-ttu-id="59d0b-167">Na árvore, selecione 'modelo\Pagamentos'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-167">In the tree, select 'model\Payments'.</span></span>
8. <span data-ttu-id="59d0b-168">Clique em Adicionar campo a.</span><span class="sxs-lookup"><span data-stu-id="59d0b-168">Click Add field to.</span></span>
9. <span data-ttu-id="59d0b-169">Clique em O que agrupar.</span><span class="sxs-lookup"><span data-stu-id="59d0b-169">Click What to group.</span></span>
10. <span data-ttu-id="59d0b-170">Na árvore, expanda 'modelo\Pagamentos'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-170">In the tree, expand 'model\Payments'.</span></span>
11. <span data-ttu-id="59d0b-171">Na árvore, selecione 'modelo\Pagamentos\Moeda'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-171">In the tree, select 'model\Payments\Currency'.</span></span>
12. <span data-ttu-id="59d0b-172">Clique em Adicionar campo a.</span><span class="sxs-lookup"><span data-stu-id="59d0b-172">Click Add field to.</span></span>
13. <span data-ttu-id="59d0b-173">Clique em Campos agrupados.</span><span class="sxs-lookup"><span data-stu-id="59d0b-173">Click Grouped fields.</span></span>
14. <span data-ttu-id="59d0b-174">Na árvore, selecione 'modelo\Pagamentos\Valor instruído(ValorInstruído)'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-174">In the tree, select 'model\Payments\Instructed Amount(InstructedAmount)'.</span></span>
15. <span data-ttu-id="59d0b-175">Clique em Adicionar campo a.</span><span class="sxs-lookup"><span data-stu-id="59d0b-175">Click Add field to.</span></span>
16. <span data-ttu-id="59d0b-176">Clique em Campos de agregação.</span><span class="sxs-lookup"><span data-stu-id="59d0b-176">Click Aggregation fields.</span></span>
17. <span data-ttu-id="59d0b-177">No campo Método, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="59d0b-177">In the Method field, select an option.</span></span>
    * <span data-ttu-id="59d0b-178">Selecione a função agregada de SUM.</span><span class="sxs-lookup"><span data-stu-id="59d0b-178">Select the SUM aggregation function.</span></span>  
18. <span data-ttu-id="59d0b-179">No campo Nome, digite 'TotalInstructuredAmount'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-179">In the Name field, type 'TotalInstructuredAmount'.</span></span>
    * <span data-ttu-id="59d0b-180">TotalInstructuredAmount</span><span class="sxs-lookup"><span data-stu-id="59d0b-180">TotalInstructuredAmount</span></span>  
19. <span data-ttu-id="59d0b-181">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="59d0b-181">Click Save.</span></span>
20. <span data-ttu-id="59d0b-182">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="59d0b-182">Close the page.</span></span>
21. <span data-ttu-id="59d0b-183">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="59d0b-183">Click OK.</span></span>

## <a name="map-format-components-to-data-sources"></a><span data-ttu-id="59d0b-184">Componentes de formato de mapa para fontes de dados</span><span class="sxs-lookup"><span data-stu-id="59d0b-184">Map format components to data sources</span></span>
1. <span data-ttu-id="59d0b-185">Na árvore, expanda 'modelo'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-185">In the tree, expand 'model'.</span></span>
2. <span data-ttu-id="59d0b-186">Na árvore, expanda 'modelo\Pagamentos'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-186">In the tree, expand 'model\Payments'.</span></span>
3. <span data-ttu-id="59d0b-187">Na árvore, expanda "modelo\Pagamentos\Participante Iniciante(InitiatingParty)".</span><span class="sxs-lookup"><span data-stu-id="59d0b-187">In the tree, expand 'model\Payments\Initiating Party(InitiatingParty)'.</span></span>
4. <span data-ttu-id="59d0b-188">Na árvore, selecione "modelo\Pagamentos\Participante Iniciante(InitiatingParty)\Nome".</span><span class="sxs-lookup"><span data-stu-id="59d0b-188">In the tree, select 'model\Payments\Initiating Party(InitiatingParty)\Name'.</span></span>
5. <span data-ttu-id="59d0b-189">Na árvore, expanda "Excel\ReportHeader".</span><span class="sxs-lookup"><span data-stu-id="59d0b-189">In the tree, expand 'Excel\ReportHeader'.</span></span>
6. <span data-ttu-id="59d0b-190">Na árvore, selecione "Excel\ReportHeader\CompanyName".</span><span class="sxs-lookup"><span data-stu-id="59d0b-190">In the tree, select 'Excel\ReportHeader\CompanyName'.</span></span>
7. <span data-ttu-id="59d0b-191">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="59d0b-191">Click Bind.</span></span>
8. <span data-ttu-id="59d0b-192">Na árvore, expanda 'modelo\Pagamentos\Credor'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-192">In the tree, expand 'model\Payments\Creditor'.</span></span>
9. <span data-ttu-id="59d0b-193">Na árvore, expanda 'modelo\Pagamentos\Credor\Identificação'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-193">In the tree, expand 'model\Payments\Creditor\Identification'.</span></span>
10. <span data-ttu-id="59d0b-194">Na árvore, selecione 'modelo\Pagamentos\Credor\Identificação\ID da fonte(SourceID)'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-194">In the tree, select 'model\Payments\Creditor\Identification\Source ID(SourceID)'.</span></span>
11. <span data-ttu-id="59d0b-195">Na árvore, expanda "Excel\PaymLines".</span><span class="sxs-lookup"><span data-stu-id="59d0b-195">In the tree, expand 'Excel\PaymLines'.</span></span>
12. <span data-ttu-id="59d0b-196">Na árvore, selecione "Excel\PaymLines\VendAccountName".</span><span class="sxs-lookup"><span data-stu-id="59d0b-196">In the tree, select 'Excel\PaymLines\VendAccountName'.</span></span>
13. <span data-ttu-id="59d0b-197">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="59d0b-197">Click Bind.</span></span>
14. <span data-ttu-id="59d0b-198">Na árvore, selecione 'modelo\Pagamentos\Credor\Nome'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-198">In the tree, select 'model\Payments\Creditor\Name'.</span></span>
15. <span data-ttu-id="59d0b-199">Na árvore, selecione "Excel\PaymLines\VendName".</span><span class="sxs-lookup"><span data-stu-id="59d0b-199">In the tree, select 'Excel\PaymLines\VendName'.</span></span>
16. <span data-ttu-id="59d0b-200">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="59d0b-200">Click Bind.</span></span>
17. <span data-ttu-id="59d0b-201">Na árvore, expanda 'modelo\Pagamentos\Agente do Credor(CreditorAgent)'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-201">In the tree, expand 'model\Payments\Creditor Agent(CreditorAgent)'.</span></span>
18. <span data-ttu-id="59d0b-202">Na árvore, selecione 'modelo\Pagamentos\Agente do Credor(CreditorAgent)\Nome'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-202">In the tree, select 'model\Payments\Creditor Agent(CreditorAgent)\Name'.</span></span>
19. <span data-ttu-id="59d0b-203">Na árvore, selecione "Excel\PaymLines\Banco".</span><span class="sxs-lookup"><span data-stu-id="59d0b-203">In the tree, select 'Excel\PaymLines\Bank'.</span></span>
20. <span data-ttu-id="59d0b-204">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="59d0b-204">Click Bind.</span></span>
21. <span data-ttu-id="59d0b-205">Na árvore, selecione 'modelo\Pagamentos\Agente credor(CreditorAgent)\Número de roteiro(RoutingNumber)'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-205">In the tree, select 'model\Payments\Creditor Agent(CreditorAgent)\Routing Number(RoutingNumber)'.</span></span>
22. <span data-ttu-id="59d0b-206">Na árvore, selecione "Excel\PaymLines\RoutingNumber".</span><span class="sxs-lookup"><span data-stu-id="59d0b-206">In the tree, select 'Excel\PaymLines\RoutingNumber'.</span></span>
23. <span data-ttu-id="59d0b-207">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="59d0b-207">Click Bind.</span></span>
24. <span data-ttu-id="59d0b-208">Na árvore, expanda 'modelo\Pagamentos\Conta do Credor(CreditorAccount)'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-208">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)'.</span></span>
25. <span data-ttu-id="59d0b-209">Na árvore, expanda 'modelo\Pagamentos\Conta do Credor(CreditorAccount)\Identificação'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-209">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)\Identification'.</span></span>
26. <span data-ttu-id="59d0b-210">Na árvore, selecione 'modelo\Pagamentos\Conta do Credor(CreditorAccount)\Identificação\Número'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-210">In the tree, select 'model\Payments\Creditor Account(CreditorAccount)\Identification\Number'.</span></span>
27. <span data-ttu-id="59d0b-211">Na árvore, selecione "Excel\PaymLines\AccountNumber".</span><span class="sxs-lookup"><span data-stu-id="59d0b-211">In the tree, select 'Excel\PaymLines\AccountNumber'.</span></span>
28. <span data-ttu-id="59d0b-212">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="59d0b-212">Click Bind.</span></span>
29. <span data-ttu-id="59d0b-213">Na árvore, selecione 'modelo\Pagamentos\Valor instruído(ValorInstruído)'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-213">In the tree, select 'model\Payments\Instructed Amount(InstructedAmount)'.</span></span>
30. <span data-ttu-id="59d0b-214">Na árvore, selecione "Excel\PaymLines\Débito".</span><span class="sxs-lookup"><span data-stu-id="59d0b-214">In the tree, select 'Excel\PaymLines\Debit'.</span></span>
31. <span data-ttu-id="59d0b-215">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="59d0b-215">Click Bind.</span></span>
32. <span data-ttu-id="59d0b-216">Na árvore, expanda 'modelo\Pagamentos\Credor'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-216">In the tree, expand 'model\Payments\Creditor'.</span></span>
33. <span data-ttu-id="59d0b-217">Na árvore, expanda 'modelo\Pagamentos\Conta do Credor(CreditorAccount)'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-217">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)'.</span></span>
34. <span data-ttu-id="59d0b-218">Na árvore, expanda 'modelo\Pagamentos\Agente do Credor(CreditorAgent)'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-218">In the tree, expand 'model\Payments\Creditor Agent(CreditorAgent)'.</span></span>
35. <span data-ttu-id="59d0b-219">Na árvore, selecione 'modelo\Pagamentos\Moeda'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-219">In the tree, select 'model\Payments\Currency'.</span></span>
36. <span data-ttu-id="59d0b-220">Na árvore, selecione "Excel\PaymLines\Moeda".</span><span class="sxs-lookup"><span data-stu-id="59d0b-220">In the tree, select 'Excel\PaymLines\Currency'.</span></span>
37. <span data-ttu-id="59d0b-221">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="59d0b-221">Click Bind.</span></span>
38. <span data-ttu-id="59d0b-222">Na árvore, expanda 'PaymentByCurrency'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-222">In the tree, expand 'PaymentByCurrency'.</span></span>
39. <span data-ttu-id="59d0b-223">Na árvore, expanda 'PaymentByCurrency\agrupado'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-223">In the tree, expand 'PaymentByCurrency\grouped'.</span></span>
40. <span data-ttu-id="59d0b-224">Na árvore, selecione 'PaymentByCurrency\agrupado\Moeda'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-224">In the tree, select 'PaymentByCurrency\grouped\Currency'.</span></span>
41. <span data-ttu-id="59d0b-225">Na árvore, expanda "Excel\SummaryLines".</span><span class="sxs-lookup"><span data-stu-id="59d0b-225">In the tree, expand 'Excel\SummaryLines'.</span></span>
42. <span data-ttu-id="59d0b-226">Na árvore, selecione "Excel\SummaryLines\SummaryCurrency".</span><span class="sxs-lookup"><span data-stu-id="59d0b-226">In the tree, select 'Excel\SummaryLines\SummaryCurrency'.</span></span>
43. <span data-ttu-id="59d0b-227">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="59d0b-227">Click Bind.</span></span>
44. <span data-ttu-id="59d0b-228">Na árvore, expanda "PaymentByCurrency\agregado".</span><span class="sxs-lookup"><span data-stu-id="59d0b-228">In the tree, expand 'PaymentByCurrency\aggregated'.</span></span>
45. <span data-ttu-id="59d0b-229">Na árvore, selecione 'PaymentByCurrency\agregado\TotalInstructuredAmount'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-229">In the tree, select 'PaymentByCurrency\aggregated\TotalInstructuredAmount'.</span></span>
46. <span data-ttu-id="59d0b-230">Na árvore, selecione "Excel\SummaryLines\SummaryAmount".</span><span class="sxs-lookup"><span data-stu-id="59d0b-230">In the tree, select 'Excel\SummaryLines\SummaryAmount'.</span></span>
47. <span data-ttu-id="59d0b-231">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="59d0b-231">Click Bind.</span></span>
48. <span data-ttu-id="59d0b-232">Na árvore, selecione 'PaymentByCurrency'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-232">In the tree, select 'PaymentByCurrency'.</span></span>
49. <span data-ttu-id="59d0b-233">Na árvore, selecione "Excel\SummaryLines".</span><span class="sxs-lookup"><span data-stu-id="59d0b-233">In the tree, select 'Excel\SummaryLines'.</span></span>
50. <span data-ttu-id="59d0b-234">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="59d0b-234">Click Bind.</span></span>
51. <span data-ttu-id="59d0b-235">Na árvore, selecione 'modelo\Pagamentos'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-235">In the tree, select 'model\Payments'.</span></span>
52. <span data-ttu-id="59d0b-236">Na árvore, selecione "Excel\PaymLines".</span><span class="sxs-lookup"><span data-stu-id="59d0b-236">In the tree, select 'Excel\PaymLines'.</span></span>
53. <span data-ttu-id="59d0b-237">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="59d0b-237">Click Bind.</span></span>
54. <span data-ttu-id="59d0b-238">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="59d0b-238">Click Save.</span></span>
55. <span data-ttu-id="59d0b-239">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="59d0b-239">Close the page.</span></span>

## <a name="use-the-created-configuration-for-payments-processing"></a><span data-ttu-id="59d0b-240">Usar a configuração criada para processamento de pagamentos</span><span class="sxs-lookup"><span data-stu-id="59d0b-240">Use the created configuration for payments processing</span></span>
1. <span data-ttu-id="59d0b-241">Clique em Alterar status.</span><span class="sxs-lookup"><span data-stu-id="59d0b-241">Click Change status.</span></span>
2. <span data-ttu-id="59d0b-242">Clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="59d0b-242">Click Complete.</span></span>
3. <span data-ttu-id="59d0b-243">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="59d0b-243">Click OK.</span></span>
4. <span data-ttu-id="59d0b-244">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="59d0b-244">Close the page.</span></span>
5. <span data-ttu-id="59d0b-245">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="59d0b-245">Close the page.</span></span>
6. <span data-ttu-id="59d0b-246">Vá para Contas a pagar > Configurar pagamento > Métodos de pagamento.</span><span class="sxs-lookup"><span data-stu-id="59d0b-246">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
7. <span data-ttu-id="59d0b-247">Use o Filtro Rápido para filtrar o campo Method of payment com o valor "Eletrônico".</span><span class="sxs-lookup"><span data-stu-id="59d0b-247">Use the Quick Filter to filter on the Method of payment field with a value of 'Electronic'.</span></span>
    * <span data-ttu-id="59d0b-248">Eletrônico</span><span class="sxs-lookup"><span data-stu-id="59d0b-248">Electronic</span></span>  
8. <span data-ttu-id="59d0b-249">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="59d0b-249">Click Edit.</span></span>
9. <span data-ttu-id="59d0b-250">Expanda a seção Formatos de arquivo.</span><span class="sxs-lookup"><span data-stu-id="59d0b-250">Expand the File formats section.</span></span>
10. <span data-ttu-id="59d0b-251">Selecione Sim no campo eletrônico Genérico do relatório.</span><span class="sxs-lookup"><span data-stu-id="59d0b-251">Select Yes in the Generic electronic reporting field.</span></span>
11. <span data-ttu-id="59d0b-252">No campo Exportar configuração de formato, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="59d0b-252">In the Export format configuration field, enter or select a value.</span></span>
    * <span data-ttu-id="59d0b-253">Selecione a configuração "Relatório de planilha de amostra".</span><span class="sxs-lookup"><span data-stu-id="59d0b-253">Select the ‘Sample worksheet report’ configuration.</span></span>  
12. <span data-ttu-id="59d0b-254">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="59d0b-254">Click Save.</span></span>
13. <span data-ttu-id="59d0b-255">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="59d0b-255">Close the page.</span></span>

## <a name="use-the-created-configuration-for-testing-of-payment-journals-processing"></a><span data-ttu-id="59d0b-256">Use a configuração criada para testar de processar diários de pagamentos</span><span class="sxs-lookup"><span data-stu-id="59d0b-256">Use the created configuration for testing of payment journals processing</span></span>
1. <span data-ttu-id="59d0b-257">Vá para Contas a pagar > Pagamentos > Diário de pagamentos.</span><span class="sxs-lookup"><span data-stu-id="59d0b-257">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="59d0b-258">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="59d0b-258">Click New.</span></span>
    * <span data-ttu-id="59d0b-259">Crie um novo diário de pagamento.</span><span class="sxs-lookup"><span data-stu-id="59d0b-259">Create a new payment journal.</span></span>  
3. <span data-ttu-id="59d0b-260">No campo Nome, digite 'VendPay'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-260">In the Name field, type 'VendPay'.</span></span>
    * <span data-ttu-id="59d0b-261">VendPay</span><span class="sxs-lookup"><span data-stu-id="59d0b-261">VendPay</span></span>  
4. <span data-ttu-id="59d0b-262">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="59d0b-262">Click Lines.</span></span>
5. <span data-ttu-id="59d0b-263">No campo Conta, especifique os valores 'GB_SI_000001'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-263">In the Account field, specify the values 'GB_SI_000001'.</span></span>
    * <span data-ttu-id="59d0b-264">GB_SI_000001</span><span class="sxs-lookup"><span data-stu-id="59d0b-264">GB_SI_000001</span></span>  
6. <span data-ttu-id="59d0b-265">Definir Débito como '1000'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-265">Set Debit to '1000'.</span></span>
7. <span data-ttu-id="59d0b-266">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="59d0b-266">Click New.</span></span>
8. <span data-ttu-id="59d0b-267">No campo Conta, especifique os valores 'GB_SI_000005'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-267">In the Account field, specify the values 'GB_SI_000005'.</span></span>
    * <span data-ttu-id="59d0b-268">GB_SI_000005</span><span class="sxs-lookup"><span data-stu-id="59d0b-268">GB_SI_000005</span></span>  
9. <span data-ttu-id="59d0b-269">Definir Débito como '2000'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-269">Set Debit to '2000'.</span></span>
10. <span data-ttu-id="59d0b-270">No campo Moeda, digite 'EUR'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-270">In the Currency field, type 'EUR'.</span></span>
    * <span data-ttu-id="59d0b-271">EUR</span><span class="sxs-lookup"><span data-stu-id="59d0b-271">EUR</span></span>  
11. <span data-ttu-id="59d0b-272">No campo Contrapartida, especifique os valores 'GBSI OPER'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-272">In the Offset account field, specify the values 'GBSI OPER'.</span></span>
    * <span data-ttu-id="59d0b-273">GBSI OPER</span><span class="sxs-lookup"><span data-stu-id="59d0b-273">GBSI OPER</span></span>  
12. <span data-ttu-id="59d0b-274">No campo Método de pagamento, digite "Eletrônico".</span><span class="sxs-lookup"><span data-stu-id="59d0b-274">In the Method of payment field, type 'Electronic'.</span></span>
    * <span data-ttu-id="59d0b-275">Eletrônico</span><span class="sxs-lookup"><span data-stu-id="59d0b-275">Electronic</span></span>  
13. <span data-ttu-id="59d0b-276">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="59d0b-276">Click Save.</span></span>
14. <span data-ttu-id="59d0b-277">Clique em Gerar pagamentos.</span><span class="sxs-lookup"><span data-stu-id="59d0b-277">Click Generate payments.</span></span>
15. <span data-ttu-id="59d0b-278">No campo Método de pagamento, digite "Eletrônico".</span><span class="sxs-lookup"><span data-stu-id="59d0b-278">In the Method of payment field, type 'Electronic'.</span></span>
    * <span data-ttu-id="59d0b-279">Eletrônico</span><span class="sxs-lookup"><span data-stu-id="59d0b-279">Electronic</span></span>  
16. <span data-ttu-id="59d0b-280">No campo Nome do arquivo, digite "Pagamentos".</span><span class="sxs-lookup"><span data-stu-id="59d0b-280">In the File name field, type 'Payments'.</span></span>
    * <span data-ttu-id="59d0b-281">Por exemplo, digite Pagamentos.</span><span class="sxs-lookup"><span data-stu-id="59d0b-281">For example, type Payments.</span></span>  
17. <span data-ttu-id="59d0b-282">No campo Conta bancária, digite 'GBSI OPER'.</span><span class="sxs-lookup"><span data-stu-id="59d0b-282">In the Bank account field, type 'GBSI OPER'.</span></span>
    * <span data-ttu-id="59d0b-283">GBSI OPER</span><span class="sxs-lookup"><span data-stu-id="59d0b-283">GBSI OPER</span></span>  
18. <span data-ttu-id="59d0b-284">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="59d0b-284">Click OK.</span></span>
19. <span data-ttu-id="59d0b-285">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="59d0b-285">Click OK.</span></span>
    * <span data-ttu-id="59d0b-286">Revise a planilha criada, incluindo detalhes de linhas de pagamento além do total para cada código de moeda usado na mensagem de pagamento.</span><span class="sxs-lookup"><span data-stu-id="59d0b-286">Review the created worksheet, including details of payment lines as well as totals for each currency code used in this payment message.</span></span>  



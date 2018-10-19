--- 
title: "ER Projetar uma configuração para gerar relatórios no formato OPENXML (Novembro de 2016)"
description: "As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma nova configuração de Relatório Eletrônico (RE) que contem um modelo para gerar os documentos eletrônicos no formato OPENXML."
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERDataSourceAddDropDialog, ERModelGroupByFunctionEditor, VendPaymMode, LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 3e6b6b16f202af051ccff02051eb438ea49ff6da
ms.contentlocale: pt-br
ms.lasthandoff: 09/14/2018

---
# <a name="er-design-a-configuration-for-generating-reports-in-openxml-format-november-2016"></a><span data-ttu-id="eea56-103">ER Projetar uma configuração para gerar relatórios no formato OPENXML (Novembro de 2016)</span><span class="sxs-lookup"><span data-stu-id="eea56-103">ER Design a configuration for generating reports in OPENXML format (November 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="eea56-104">As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma nova configuração de Relatório Eletrônico (RE) que contem um modelo para gerar os documentos eletrônicos no formato OPENXML.</span><span class="sxs-lookup"><span data-stu-id="eea56-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a template for generating electronic documents in OPENXML format.</span></span> <span data-ttu-id="eea56-105">Essa configuração será usada para processar pagamentos do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="eea56-105">This configuration will be used for processing vendor payments.</span></span>



<span data-ttu-id="eea56-106">Neste exemplo, você criará uma configuração para a empresa de exemplo, Litware, Inc. Estas etapas podem ser executadas na empresa GBSI.</span><span class="sxs-lookup"><span data-stu-id="eea56-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in GBSI company.</span></span>



<span data-ttu-id="eea56-107">Para completar essas etapas, você deve primeiro completar as etapas do procedimento “Criar um provedor de configuração e marcá-lo como ativo“.</span><span class="sxs-lookup"><span data-stu-id="eea56-107">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span> <span data-ttu-id="eea56-108">Você também deve ter um arquivo Excel que é importado ao criar o modelo.</span><span class="sxs-lookup"><span data-stu-id="eea56-108">You must also have an Excel file which will be imported when creating the template.</span></span> <span data-ttu-id="eea56-109">Esse arquivo pode ser acessado de [Modelo de relatório de pagamento](https://go.microsoft.com/fwlink/?linkid=862266).</span><span class="sxs-lookup"><span data-stu-id="eea56-109">This file can be accessed from the [Template of Payment Report](https://go.microsoft.com/fwlink/?linkid=862266).</span></span>


## <a name="upload-the-payments-data-model-configuration"></a><span data-ttu-id="eea56-110">Carregar a configuração do modelo de dados de pagamentos</span><span class="sxs-lookup"><span data-stu-id="eea56-110">Upload the Payments data model configuration</span></span>
1. <span data-ttu-id="eea56-111">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="eea56-111">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="eea56-112">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="eea56-112">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="eea56-113">Selecione o provedor de configuração para a empresa de exemplo, 'Litware, Inc.' Se você não visualizar o provedor de configuração, você deve primeiro concluir as etapas do procedimento “Criar um provedor de configuração e marcá-lo como ativo“.</span><span class="sxs-lookup"><span data-stu-id="eea56-113">Select the configuration provider for sample company, Litware, Inc. If you don’t see this configuration provider, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>  
3. <span data-ttu-id="eea56-114">Clique em Definir como ativo.</span><span class="sxs-lookup"><span data-stu-id="eea56-114">Click Set active.</span></span>
4. <span data-ttu-id="eea56-115">Clique em Repositórios.</span><span class="sxs-lookup"><span data-stu-id="eea56-115">Click Repositories.</span></span>
    * <span data-ttu-id="eea56-116">Selecione um repositório para o tipo Recursos de operações, se disponível.</span><span class="sxs-lookup"><span data-stu-id="eea56-116">Select a repository for the Operations Resources type, if available.</span></span> <span data-ttu-id="eea56-117">Se estiver disponível, pule as etapas a seguir sobre criar um novo repositório.</span><span class="sxs-lookup"><span data-stu-id="eea56-117">If its available, skip the following steps about creating a new repository.</span></span>  
5. <span data-ttu-id="eea56-118">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="eea56-118">Click Add to open the drop dialog.</span></span>
6. <span data-ttu-id="eea56-119">No campo Tipo de repositório de configuração, insira 'Recursos de operações'.</span><span class="sxs-lookup"><span data-stu-id="eea56-119">In the Configuration repository type field, enter 'Operations resources'.</span></span>
7. <span data-ttu-id="eea56-120">Clique em Criar repositório.</span><span class="sxs-lookup"><span data-stu-id="eea56-120">Click Create repository.</span></span>
8. <span data-ttu-id="eea56-121">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="eea56-121">Click OK.</span></span>
9. <span data-ttu-id="eea56-122">Clique em Abrir.</span><span class="sxs-lookup"><span data-stu-id="eea56-122">Click Open.</span></span>
10. <span data-ttu-id="eea56-123">Na árvore, selecione 'Modelo de pagamento'.</span><span class="sxs-lookup"><span data-stu-id="eea56-123">In the tree, select 'Payment model'.</span></span>
11. <span data-ttu-id="eea56-124">Clique em Importar.</span><span class="sxs-lookup"><span data-stu-id="eea56-124">Click Import.</span></span>
    * <span data-ttu-id="eea56-125">Importar este modelo de dados.</span><span class="sxs-lookup"><span data-stu-id="eea56-125">Import this data model.</span></span> <span data-ttu-id="eea56-126">Será usado como a fonte de dados em uma nova configuração de formato.</span><span class="sxs-lookup"><span data-stu-id="eea56-126">It will be used as a data source in a new format configuration.</span></span> <span data-ttu-id="eea56-127">Ignorar essa etapa se essa configuração já tiver sido importada.</span><span class="sxs-lookup"><span data-stu-id="eea56-127">Skip this step if this configuration has been already imported.</span></span>  
12. <span data-ttu-id="eea56-128">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="eea56-128">Click Yes.</span></span>
13. <span data-ttu-id="eea56-129">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="eea56-129">Close the page.</span></span>
14. <span data-ttu-id="eea56-130">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="eea56-130">Close the page.</span></span>

## <a name="create-a-new-format-configuration"></a><span data-ttu-id="eea56-131">Criar uma nova configuração de formato</span><span class="sxs-lookup"><span data-stu-id="eea56-131">Create a new format configuration</span></span>
1. <span data-ttu-id="eea56-132">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="eea56-132">Click Reporting configurations.</span></span>
2. <span data-ttu-id="eea56-133">Na árvore, selecione 'Modelo de pagamento'.</span><span class="sxs-lookup"><span data-stu-id="eea56-133">In the tree, select 'Payment model'.</span></span>
3. <span data-ttu-id="eea56-134">Clique em Criar configuração para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="eea56-134">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="eea56-135">No campo Novo, insira 'Formato baseado no modelo de dados PaymentModel'.</span><span class="sxs-lookup"><span data-stu-id="eea56-135">In the New field, enter 'Format based on data model PaymentModel'.</span></span>
    * <span data-ttu-id="eea56-136">Criar um formato com base no modelo de dados do PaymentModel.</span><span class="sxs-lookup"><span data-stu-id="eea56-136">Create a format that is based on the PaymentModel data model.</span></span>  
5. <span data-ttu-id="eea56-137">No campo Nome, digite "Relatório de planilha de exemplo".</span><span class="sxs-lookup"><span data-stu-id="eea56-137">In the Name field, type 'Sample worksheet report'.</span></span>
    * <span data-ttu-id="eea56-138">Relatório da planilha de exemplo</span><span class="sxs-lookup"><span data-stu-id="eea56-138">Sample worksheet report</span></span>  
6. <span data-ttu-id="eea56-139">No campo Tipo de descrição, digite "Relatório de planilha de amostra para pagamentos de fornecedor".</span><span class="sxs-lookup"><span data-stu-id="eea56-139">In the Description field, type 'Sample worksheet report for vendors’ payments'.</span></span>
    * <span data-ttu-id="eea56-140">Relatório de planilha de amostra para pagamentos do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="eea56-140">Sample worksheet report for vendors’ payments.</span></span>  
7. <span data-ttu-id="eea56-141">No campo Definição do modelo de dados, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="eea56-141">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="eea56-142">Selecione a definição "CustomerCreditTransferInitiation".</span><span class="sxs-lookup"><span data-stu-id="eea56-142">Select the 'CustomerCreditTransferInitiation' definition.</span></span>  
8. <span data-ttu-id="eea56-143">Clique em Criar configuração.</span><span class="sxs-lookup"><span data-stu-id="eea56-143">Click Create configuration.</span></span>

## <a name="design-a-new-document-in-openxml-worksheet-format"></a><span data-ttu-id="eea56-144">Criar um novo documento no formato da folha OPENXML</span><span class="sxs-lookup"><span data-stu-id="eea56-144">Design a new document in OPENXML worksheet format</span></span>
1. <span data-ttu-id="eea56-145">Na árvore, selecione "Modelo de pagamento\Relatório de planilha de amostra".</span><span class="sxs-lookup"><span data-stu-id="eea56-145">In the tree, select 'Payment model\Sample worksheet report'.</span></span>
2. <span data-ttu-id="eea56-146">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="eea56-146">Click Designer.</span></span>
3. <span data-ttu-id="eea56-147">No Painel de Ação, clique em Importar.</span><span class="sxs-lookup"><span data-stu-id="eea56-147">On the Action Pane, click Import.</span></span>
4. <span data-ttu-id="eea56-148">Clique em Importar do Excel.</span><span class="sxs-lookup"><span data-stu-id="eea56-148">Click Import from Excel.</span></span>
5. <span data-ttu-id="eea56-149">Clique em Anexos.</span><span class="sxs-lookup"><span data-stu-id="eea56-149">Click Attachments.</span></span>
    * <span data-ttu-id="eea56-150">Anexar o documento existente do Excel como um modelo.</span><span class="sxs-lookup"><span data-stu-id="eea56-150">Attach the existing Excel document as a template.</span></span>  
6. <span data-ttu-id="eea56-151">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="eea56-151">Click New.</span></span>
7. <span data-ttu-id="eea56-152">Clique em Arquivo.</span><span class="sxs-lookup"><span data-stu-id="eea56-152">Click File.</span></span>
    * <span data-ttu-id="eea56-153">Apontar para o arquivo existente do Excel.</span><span class="sxs-lookup"><span data-stu-id="eea56-153">Point to the existing Excel file.</span></span>  
8. <span data-ttu-id="eea56-154">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="eea56-154">Close the page.</span></span>
9. <span data-ttu-id="eea56-155">No campo Modelo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="eea56-155">In the Template field, enter or select a value.</span></span>
    * <span data-ttu-id="eea56-156">Selecione o arquivo Excel anexado a ser usado como um modelo.</span><span class="sxs-lookup"><span data-stu-id="eea56-156">Select the attached Excel file to be used as a template.</span></span>  
10. <span data-ttu-id="eea56-157">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="eea56-157">Click OK.</span></span>
    * <span data-ttu-id="eea56-158">Observe que os componentes do formato ER foram criados no formato criador com base na estrutura do documento de referência do MS Excel (intervalos nomeados).</span><span class="sxs-lookup"><span data-stu-id="eea56-158">Note that ER format components have been created in the designing format based on the structure of the referring MS Excel document (named ranges).</span></span>  

## <a name="create-a-new-data-source-to-calculate-totals-by-currency-codes"></a><span data-ttu-id="eea56-159">Criar uma nova fonte de dados para calcular totais por código de moeda</span><span class="sxs-lookup"><span data-stu-id="eea56-159">Create a new data source to calculate totals by currency codes</span></span>
1. <span data-ttu-id="eea56-160">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="eea56-160">Click the Mapping tab.</span></span>
2. <span data-ttu-id="eea56-161">Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="eea56-161">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="eea56-162">Na árvore, selecione 'Funções\Agrupar por'.</span><span class="sxs-lookup"><span data-stu-id="eea56-162">In the tree, select 'Functions\Group by'.</span></span>
4. <span data-ttu-id="eea56-163">No campo Nome, digite 'PaymentByCurrency'.</span><span class="sxs-lookup"><span data-stu-id="eea56-163">In the Name field, type 'PaymentByCurrency'.</span></span>
    * <span data-ttu-id="eea56-164">PaymentByCurrency</span><span class="sxs-lookup"><span data-stu-id="eea56-164">PaymentByCurrency</span></span>  
5. <span data-ttu-id="eea56-165">Clique em Editar grupo por.</span><span class="sxs-lookup"><span data-stu-id="eea56-165">Click Edit group by.</span></span>
6. <span data-ttu-id="eea56-166">Na árvore, expanda 'modelo'.</span><span class="sxs-lookup"><span data-stu-id="eea56-166">In the tree, expand 'model'.</span></span>
7. <span data-ttu-id="eea56-167">Na árvore, selecione 'modelo\Pagamentos'.</span><span class="sxs-lookup"><span data-stu-id="eea56-167">In the tree, select 'model\Payments'.</span></span>
8. <span data-ttu-id="eea56-168">Clique em Adicionar campo a.</span><span class="sxs-lookup"><span data-stu-id="eea56-168">Click Add field to.</span></span>
9. <span data-ttu-id="eea56-169">Clique em O que agrupar.</span><span class="sxs-lookup"><span data-stu-id="eea56-169">Click What to group.</span></span>
10. <span data-ttu-id="eea56-170">Na árvore, expanda 'modelo\Pagamentos'.</span><span class="sxs-lookup"><span data-stu-id="eea56-170">In the tree, expand 'model\Payments'.</span></span>
11. <span data-ttu-id="eea56-171">Na árvore, selecione 'modelo\Pagamentos\Moeda'.</span><span class="sxs-lookup"><span data-stu-id="eea56-171">In the tree, select 'model\Payments\Currency'.</span></span>
12. <span data-ttu-id="eea56-172">Clique em Adicionar campo a.</span><span class="sxs-lookup"><span data-stu-id="eea56-172">Click Add field to.</span></span>
13. <span data-ttu-id="eea56-173">Clique em Campos agrupados.</span><span class="sxs-lookup"><span data-stu-id="eea56-173">Click Grouped fields.</span></span>
14. <span data-ttu-id="eea56-174">Na árvore, selecione 'modelo\Pagamentos\Valor instruído(ValorInstruído)'.</span><span class="sxs-lookup"><span data-stu-id="eea56-174">In the tree, select 'model\Payments\Instructed Amount(InstructedAmount)'.</span></span>
15. <span data-ttu-id="eea56-175">Clique em Adicionar campo a.</span><span class="sxs-lookup"><span data-stu-id="eea56-175">Click Add field to.</span></span>
16. <span data-ttu-id="eea56-176">Clique em Campos de agregação.</span><span class="sxs-lookup"><span data-stu-id="eea56-176">Click Aggregation fields.</span></span>
17. <span data-ttu-id="eea56-177">No campo Método, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="eea56-177">In the Method field, select an option.</span></span>
    * <span data-ttu-id="eea56-178">Selecione a função agregada de SUM.</span><span class="sxs-lookup"><span data-stu-id="eea56-178">Select the SUM aggregation function.</span></span>  
18. <span data-ttu-id="eea56-179">No campo Nome, digite 'TotalInstructuredAmount'.</span><span class="sxs-lookup"><span data-stu-id="eea56-179">In the Name field, type 'TotalInstructuredAmount'.</span></span>
    * <span data-ttu-id="eea56-180">TotalInstructuredAmount</span><span class="sxs-lookup"><span data-stu-id="eea56-180">TotalInstructuredAmount</span></span>  
19. <span data-ttu-id="eea56-181">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="eea56-181">Click Save.</span></span>
20. <span data-ttu-id="eea56-182">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="eea56-182">Close the page.</span></span>
21. <span data-ttu-id="eea56-183">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="eea56-183">Click OK.</span></span>

## <a name="map-format-components-to-data-sources"></a><span data-ttu-id="eea56-184">Componentes de formato de mapa para fontes de dados</span><span class="sxs-lookup"><span data-stu-id="eea56-184">Map format components to data sources</span></span>
1. <span data-ttu-id="eea56-185">Na árvore, expanda 'modelo'.</span><span class="sxs-lookup"><span data-stu-id="eea56-185">In the tree, expand 'model'.</span></span>
2. <span data-ttu-id="eea56-186">Na árvore, expanda 'modelo\Pagamentos'.</span><span class="sxs-lookup"><span data-stu-id="eea56-186">In the tree, expand 'model\Payments'.</span></span>
3. <span data-ttu-id="eea56-187">Na árvore, expanda "modelo\Pagamentos\Participante Iniciante(InitiatingParty)".</span><span class="sxs-lookup"><span data-stu-id="eea56-187">In the tree, expand 'model\Payments\Initiating Party(InitiatingParty)'.</span></span>
4. <span data-ttu-id="eea56-188">Na árvore, selecione "modelo\Pagamentos\Participante Iniciante(InitiatingParty)\Nome".</span><span class="sxs-lookup"><span data-stu-id="eea56-188">In the tree, select 'model\Payments\Initiating Party(InitiatingParty)\Name'.</span></span>
5. <span data-ttu-id="eea56-189">Na árvore, expanda "Excel\ReportHeader".</span><span class="sxs-lookup"><span data-stu-id="eea56-189">In the tree, expand 'Excel\ReportHeader'.</span></span>
6. <span data-ttu-id="eea56-190">Na árvore, selecione "Excel\ReportHeader\CompanyName".</span><span class="sxs-lookup"><span data-stu-id="eea56-190">In the tree, select 'Excel\ReportHeader\CompanyName'.</span></span>
7. <span data-ttu-id="eea56-191">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="eea56-191">Click Bind.</span></span>
8. <span data-ttu-id="eea56-192">Na árvore, expanda 'modelo\Pagamentos\Credor'.</span><span class="sxs-lookup"><span data-stu-id="eea56-192">In the tree, expand 'model\Payments\Creditor'.</span></span>
9. <span data-ttu-id="eea56-193">Na árvore, expanda 'modelo\Pagamentos\Credor\Identificação'.</span><span class="sxs-lookup"><span data-stu-id="eea56-193">In the tree, expand 'model\Payments\Creditor\Identification'.</span></span>
10. <span data-ttu-id="eea56-194">Na árvore, selecione 'modelo\Pagamentos\Credor\Identificação\ID da fonte(SourceID)'.</span><span class="sxs-lookup"><span data-stu-id="eea56-194">In the tree, select 'model\Payments\Creditor\Identification\Source ID(SourceID)'.</span></span>
11. <span data-ttu-id="eea56-195">Na árvore, expanda "Excel\PaymLines".</span><span class="sxs-lookup"><span data-stu-id="eea56-195">In the tree, expand 'Excel\PaymLines'.</span></span>
12. <span data-ttu-id="eea56-196">Na árvore, selecione "Excel\PaymLines\VendAccountName".</span><span class="sxs-lookup"><span data-stu-id="eea56-196">In the tree, select 'Excel\PaymLines\VendAccountName'.</span></span>
13. <span data-ttu-id="eea56-197">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="eea56-197">Click Bind.</span></span>
14. <span data-ttu-id="eea56-198">Na árvore, selecione 'modelo\Pagamentos\Credor\Nome'.</span><span class="sxs-lookup"><span data-stu-id="eea56-198">In the tree, select 'model\Payments\Creditor\Name'.</span></span>
15. <span data-ttu-id="eea56-199">Na árvore, selecione "Excel\PaymLines\VendName".</span><span class="sxs-lookup"><span data-stu-id="eea56-199">In the tree, select 'Excel\PaymLines\VendName'.</span></span>
16. <span data-ttu-id="eea56-200">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="eea56-200">Click Bind.</span></span>
17. <span data-ttu-id="eea56-201">Na árvore, expanda 'modelo\Pagamentos\Agente do Credor(CreditorAgent)'.</span><span class="sxs-lookup"><span data-stu-id="eea56-201">In the tree, expand 'model\Payments\Creditor Agent(CreditorAgent)'.</span></span>
18. <span data-ttu-id="eea56-202">Na árvore, selecione 'modelo\Pagamentos\Agente do Credor(CreditorAgent)\Nome'.</span><span class="sxs-lookup"><span data-stu-id="eea56-202">In the tree, select 'model\Payments\Creditor Agent(CreditorAgent)\Name'.</span></span>
19. <span data-ttu-id="eea56-203">Na árvore, selecione "Excel\PaymLines\Banco".</span><span class="sxs-lookup"><span data-stu-id="eea56-203">In the tree, select 'Excel\PaymLines\Bank'.</span></span>
20. <span data-ttu-id="eea56-204">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="eea56-204">Click Bind.</span></span>
21. <span data-ttu-id="eea56-205">Na árvore, selecione 'modelo\Pagamentos\Agente credor(CreditorAgent)\Número de roteiro(RoutingNumber)'.</span><span class="sxs-lookup"><span data-stu-id="eea56-205">In the tree, select 'model\Payments\Creditor Agent(CreditorAgent)\Routing Number(RoutingNumber)'.</span></span>
22. <span data-ttu-id="eea56-206">Na árvore, selecione "Excel\PaymLines\RoutingNumber".</span><span class="sxs-lookup"><span data-stu-id="eea56-206">In the tree, select 'Excel\PaymLines\RoutingNumber'.</span></span>
23. <span data-ttu-id="eea56-207">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="eea56-207">Click Bind.</span></span>
24. <span data-ttu-id="eea56-208">Na árvore, expanda 'modelo\Pagamentos\Conta do Credor(CreditorAccount)'.</span><span class="sxs-lookup"><span data-stu-id="eea56-208">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)'.</span></span>
25. <span data-ttu-id="eea56-209">Na árvore, expanda 'modelo\Pagamentos\Conta do Credor(CreditorAccount)\Identificação'.</span><span class="sxs-lookup"><span data-stu-id="eea56-209">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)\Identification'.</span></span>
26. <span data-ttu-id="eea56-210">Na árvore, selecione 'modelo\Pagamentos\Conta do Credor(CreditorAccount)\Identificação\Número'.</span><span class="sxs-lookup"><span data-stu-id="eea56-210">In the tree, select 'model\Payments\Creditor Account(CreditorAccount)\Identification\Number'.</span></span>
27. <span data-ttu-id="eea56-211">Na árvore, selecione "Excel\PaymLines\AccountNumber".</span><span class="sxs-lookup"><span data-stu-id="eea56-211">In the tree, select 'Excel\PaymLines\AccountNumber'.</span></span>
28. <span data-ttu-id="eea56-212">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="eea56-212">Click Bind.</span></span>
29. <span data-ttu-id="eea56-213">Na árvore, selecione 'modelo\Pagamentos\Valor instruído(ValorInstruído)'.</span><span class="sxs-lookup"><span data-stu-id="eea56-213">In the tree, select 'model\Payments\Instructed Amount(InstructedAmount)'.</span></span>
30. <span data-ttu-id="eea56-214">Na árvore, selecione "Excel\PaymLines\Débito".</span><span class="sxs-lookup"><span data-stu-id="eea56-214">In the tree, select 'Excel\PaymLines\Debit'.</span></span>
31. <span data-ttu-id="eea56-215">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="eea56-215">Click Bind.</span></span>
32. <span data-ttu-id="eea56-216">Na árvore, expanda 'modelo\Pagamentos\Credor'.</span><span class="sxs-lookup"><span data-stu-id="eea56-216">In the tree, expand 'model\Payments\Creditor'.</span></span>
33. <span data-ttu-id="eea56-217">Na árvore, expanda 'modelo\Pagamentos\Conta do Credor(CreditorAccount)'.</span><span class="sxs-lookup"><span data-stu-id="eea56-217">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)'.</span></span>
34. <span data-ttu-id="eea56-218">Na árvore, expanda 'modelo\Pagamentos\Agente do Credor(CreditorAgent)'.</span><span class="sxs-lookup"><span data-stu-id="eea56-218">In the tree, expand 'model\Payments\Creditor Agent(CreditorAgent)'.</span></span>
35. <span data-ttu-id="eea56-219">Na árvore, selecione 'modelo\Pagamentos\Moeda'.</span><span class="sxs-lookup"><span data-stu-id="eea56-219">In the tree, select 'model\Payments\Currency'.</span></span>
36. <span data-ttu-id="eea56-220">Na árvore, selecione "Excel\PaymLines\Moeda".</span><span class="sxs-lookup"><span data-stu-id="eea56-220">In the tree, select 'Excel\PaymLines\Currency'.</span></span>
37. <span data-ttu-id="eea56-221">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="eea56-221">Click Bind.</span></span>
38. <span data-ttu-id="eea56-222">Na árvore, expanda 'PaymentByCurrency'.</span><span class="sxs-lookup"><span data-stu-id="eea56-222">In the tree, expand 'PaymentByCurrency'.</span></span>
39. <span data-ttu-id="eea56-223">Na árvore, expanda 'PaymentByCurrency\agrupado'.</span><span class="sxs-lookup"><span data-stu-id="eea56-223">In the tree, expand 'PaymentByCurrency\grouped'.</span></span>
40. <span data-ttu-id="eea56-224">Na árvore, selecione 'PaymentByCurrency\agrupado\Moeda'.</span><span class="sxs-lookup"><span data-stu-id="eea56-224">In the tree, select 'PaymentByCurrency\grouped\Currency'.</span></span>
41. <span data-ttu-id="eea56-225">Na árvore, expanda "Excel\SummaryLines".</span><span class="sxs-lookup"><span data-stu-id="eea56-225">In the tree, expand 'Excel\SummaryLines'.</span></span>
42. <span data-ttu-id="eea56-226">Na árvore, selecione "Excel\SummaryLines\SummaryCurrency".</span><span class="sxs-lookup"><span data-stu-id="eea56-226">In the tree, select 'Excel\SummaryLines\SummaryCurrency'.</span></span>
43. <span data-ttu-id="eea56-227">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="eea56-227">Click Bind.</span></span>
44. <span data-ttu-id="eea56-228">Na árvore, expanda "PaymentByCurrency\agregado".</span><span class="sxs-lookup"><span data-stu-id="eea56-228">In the tree, expand 'PaymentByCurrency\aggregated'.</span></span>
45. <span data-ttu-id="eea56-229">Na árvore, selecione 'PaymentByCurrency\agregado\TotalInstructuredAmount'.</span><span class="sxs-lookup"><span data-stu-id="eea56-229">In the tree, select 'PaymentByCurrency\aggregated\TotalInstructuredAmount'.</span></span>
46. <span data-ttu-id="eea56-230">Na árvore, selecione "Excel\SummaryLines\SummaryAmount".</span><span class="sxs-lookup"><span data-stu-id="eea56-230">In the tree, select 'Excel\SummaryLines\SummaryAmount'.</span></span>
47. <span data-ttu-id="eea56-231">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="eea56-231">Click Bind.</span></span>
48. <span data-ttu-id="eea56-232">Na árvore, selecione 'PaymentByCurrency'.</span><span class="sxs-lookup"><span data-stu-id="eea56-232">In the tree, select 'PaymentByCurrency'.</span></span>
49. <span data-ttu-id="eea56-233">Na árvore, selecione "Excel\SummaryLines".</span><span class="sxs-lookup"><span data-stu-id="eea56-233">In the tree, select 'Excel\SummaryLines'.</span></span>
50. <span data-ttu-id="eea56-234">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="eea56-234">Click Bind.</span></span>
51. <span data-ttu-id="eea56-235">Na árvore, selecione 'modelo\Pagamentos'.</span><span class="sxs-lookup"><span data-stu-id="eea56-235">In the tree, select 'model\Payments'.</span></span>
52. <span data-ttu-id="eea56-236">Na árvore, selecione "Excel\PaymLines".</span><span class="sxs-lookup"><span data-stu-id="eea56-236">In the tree, select 'Excel\PaymLines'.</span></span>
53. <span data-ttu-id="eea56-237">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="eea56-237">Click Bind.</span></span>
54. <span data-ttu-id="eea56-238">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="eea56-238">Click Save.</span></span>
55. <span data-ttu-id="eea56-239">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="eea56-239">Close the page.</span></span>

## <a name="use-the-created-configuration-for-payments-processing"></a><span data-ttu-id="eea56-240">Usar a configuração criada para processamento de pagamentos</span><span class="sxs-lookup"><span data-stu-id="eea56-240">Use the created configuration for payments processing</span></span>
1. <span data-ttu-id="eea56-241">Clique em Alterar status.</span><span class="sxs-lookup"><span data-stu-id="eea56-241">Click Change status.</span></span>
2. <span data-ttu-id="eea56-242">Clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="eea56-242">Click Complete.</span></span>
3. <span data-ttu-id="eea56-243">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="eea56-243">Click OK.</span></span>
4. <span data-ttu-id="eea56-244">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="eea56-244">Close the page.</span></span>
5. <span data-ttu-id="eea56-245">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="eea56-245">Close the page.</span></span>
6. <span data-ttu-id="eea56-246">Vá para Contas a pagar > Configurar pagamento > Métodos de pagamento.</span><span class="sxs-lookup"><span data-stu-id="eea56-246">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
7. <span data-ttu-id="eea56-247">Use o Filtro Rápido para filtrar o campo Method of payment com o valor "Eletrônico".</span><span class="sxs-lookup"><span data-stu-id="eea56-247">Use the Quick Filter to filter on the Method of payment field with a value of 'Electronic'.</span></span>
    * <span data-ttu-id="eea56-248">Eletrônico</span><span class="sxs-lookup"><span data-stu-id="eea56-248">Electronic</span></span>  
8. <span data-ttu-id="eea56-249">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="eea56-249">Click Edit.</span></span>
9. <span data-ttu-id="eea56-250">Expanda a seção Formatos de arquivo.</span><span class="sxs-lookup"><span data-stu-id="eea56-250">Expand the File formats section.</span></span>
10. <span data-ttu-id="eea56-251">Selecione Sim no campo eletrônico Genérico do relatório.</span><span class="sxs-lookup"><span data-stu-id="eea56-251">Select Yes in the Generic electronic reporting field.</span></span>
11. <span data-ttu-id="eea56-252">No campo Exportar configuração de formato, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="eea56-252">In the Export format configuration field, enter or select a value.</span></span>
    * <span data-ttu-id="eea56-253">Selecione a configuração "Relatório de planilha de amostra".</span><span class="sxs-lookup"><span data-stu-id="eea56-253">Select the ‘Sample worksheet report’ configuration.</span></span>  
12. <span data-ttu-id="eea56-254">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="eea56-254">Click Save.</span></span>
13. <span data-ttu-id="eea56-255">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="eea56-255">Close the page.</span></span>

## <a name="use-the-created-configuration-for-testing-of-payment-journals-processing"></a><span data-ttu-id="eea56-256">Use a configuração criada para testar de processar diários de pagamentos</span><span class="sxs-lookup"><span data-stu-id="eea56-256">Use the created configuration for testing of payment journals processing</span></span>
1. <span data-ttu-id="eea56-257">Vá para Contas a pagar > Pagamentos > Diário de pagamentos.</span><span class="sxs-lookup"><span data-stu-id="eea56-257">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="eea56-258">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="eea56-258">Click New.</span></span>
    * <span data-ttu-id="eea56-259">Crie um novo diário de pagamento.</span><span class="sxs-lookup"><span data-stu-id="eea56-259">Create a new payment journal.</span></span>  
3. <span data-ttu-id="eea56-260">No campo Nome, digite 'VendPay'.</span><span class="sxs-lookup"><span data-stu-id="eea56-260">In the Name field, type 'VendPay'.</span></span>
    * <span data-ttu-id="eea56-261">VendPay</span><span class="sxs-lookup"><span data-stu-id="eea56-261">VendPay</span></span>  
4. <span data-ttu-id="eea56-262">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="eea56-262">Click Lines.</span></span>
5. <span data-ttu-id="eea56-263">No campo Conta, especifique os valores 'GB_SI_000001'.</span><span class="sxs-lookup"><span data-stu-id="eea56-263">In the Account field, specify the values 'GB_SI_000001'.</span></span>
    * <span data-ttu-id="eea56-264">GB_SI_000001</span><span class="sxs-lookup"><span data-stu-id="eea56-264">GB_SI_000001</span></span>  
6. <span data-ttu-id="eea56-265">Definir Débito como '1000'.</span><span class="sxs-lookup"><span data-stu-id="eea56-265">Set Debit to '1000'.</span></span>
7. <span data-ttu-id="eea56-266">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="eea56-266">Click New.</span></span>
8. <span data-ttu-id="eea56-267">No campo Conta, especifique os valores 'GB_SI_000005'.</span><span class="sxs-lookup"><span data-stu-id="eea56-267">In the Account field, specify the values 'GB_SI_000005'.</span></span>
    * <span data-ttu-id="eea56-268">GB_SI_000005</span><span class="sxs-lookup"><span data-stu-id="eea56-268">GB_SI_000005</span></span>  
9. <span data-ttu-id="eea56-269">Definir Débito como '2000'.</span><span class="sxs-lookup"><span data-stu-id="eea56-269">Set Debit to '2000'.</span></span>
10. <span data-ttu-id="eea56-270">No campo Moeda, digite 'EUR'.</span><span class="sxs-lookup"><span data-stu-id="eea56-270">In the Currency field, type 'EUR'.</span></span>
    * <span data-ttu-id="eea56-271">EUR</span><span class="sxs-lookup"><span data-stu-id="eea56-271">EUR</span></span>  
11. <span data-ttu-id="eea56-272">No campo Contrapartida, especifique os valores 'GBSI OPER'.</span><span class="sxs-lookup"><span data-stu-id="eea56-272">In the Offset account field, specify the values 'GBSI OPER'.</span></span>
    * <span data-ttu-id="eea56-273">GBSI OPER</span><span class="sxs-lookup"><span data-stu-id="eea56-273">GBSI OPER</span></span>  
12. <span data-ttu-id="eea56-274">No campo Método de pagamento, digite "Eletrônico".</span><span class="sxs-lookup"><span data-stu-id="eea56-274">In the Method of payment field, type 'Electronic'.</span></span>
    * <span data-ttu-id="eea56-275">Eletrônico</span><span class="sxs-lookup"><span data-stu-id="eea56-275">Electronic</span></span>  
13. <span data-ttu-id="eea56-276">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="eea56-276">Click Save.</span></span>
14. <span data-ttu-id="eea56-277">Clique em Gerar pagamentos.</span><span class="sxs-lookup"><span data-stu-id="eea56-277">Click Generate payments.</span></span>
15. <span data-ttu-id="eea56-278">No campo Método de pagamento, digite "Eletrônico".</span><span class="sxs-lookup"><span data-stu-id="eea56-278">In the Method of payment field, type 'Electronic'.</span></span>
    * <span data-ttu-id="eea56-279">Eletrônico</span><span class="sxs-lookup"><span data-stu-id="eea56-279">Electronic</span></span>  
16. <span data-ttu-id="eea56-280">No campo Nome do arquivo, digite "Pagamentos".</span><span class="sxs-lookup"><span data-stu-id="eea56-280">In the File name field, type 'Payments'.</span></span>
    * <span data-ttu-id="eea56-281">Por exemplo, digite Pagamentos.</span><span class="sxs-lookup"><span data-stu-id="eea56-281">For example, type Payments.</span></span>  
17. <span data-ttu-id="eea56-282">No campo Conta bancária, digite 'GBSI OPER'.</span><span class="sxs-lookup"><span data-stu-id="eea56-282">In the Bank account field, type 'GBSI OPER'.</span></span>
    * <span data-ttu-id="eea56-283">GBSI OPER</span><span class="sxs-lookup"><span data-stu-id="eea56-283">GBSI OPER</span></span>  
18. <span data-ttu-id="eea56-284">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="eea56-284">Click OK.</span></span>
19. <span data-ttu-id="eea56-285">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="eea56-285">Click OK.</span></span>
    * <span data-ttu-id="eea56-286">Revise a planilha criada, incluindo detalhes de linhas de pagamento além do total para cada código de moeda usado na mensagem de pagamento.</span><span class="sxs-lookup"><span data-stu-id="eea56-286">Review the created worksheet, including details of payment lines as well as totals for each currency code used in this payment message.</span></span>  



--- 
title: "Criar configurações de ER para gerar relatórios no formato do OpenXML"
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
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: b42cfe36c57a9526e585bbad0fcd31ff60b90397
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2018

---
# <a name="design-er-configurations-to-generate-reports-in-openxml-format"></a><span data-ttu-id="8c208-103">Criar configurações de ER para gerar relatórios no formato do OpenXML</span><span class="sxs-lookup"><span data-stu-id="8c208-103">Design ER configurations to generate reports in OpenXML format</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8c208-104">As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma nova configuração de Relatório Eletrônico (RE) que contem um modelo para gerar os documentos eletrônicos no formato OPENXML.</span><span class="sxs-lookup"><span data-stu-id="8c208-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a template for generating electronic documents in OPENXML format.</span></span> <span data-ttu-id="8c208-105">Essa configuração será usada para processar pagamentos do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="8c208-105">This configuration will be used for processing vendor payments.</span></span>



<span data-ttu-id="8c208-106">Neste exemplo, você criará uma configuração para a empresa de exemplo, Litware, Inc. Estas etapas podem ser executadas na empresa GBSI.</span><span class="sxs-lookup"><span data-stu-id="8c208-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in GBSI company.</span></span>



<span data-ttu-id="8c208-107">Para completar essas etapas, você deve primeiro completar as etapas do procedimento “Criar um provedor de configuração e marcá-lo como ativo“.</span><span class="sxs-lookup"><span data-stu-id="8c208-107">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span> <span data-ttu-id="8c208-108">Você também deve baixar e salvar o arquivo do Microsoft Excel, [Modelo de relatório de pagamento](https://go.microsoft.com/fwlink/?linkid=862266).</span><span class="sxs-lookup"><span data-stu-id="8c208-108">You must also download and save the Microsoft Excel file, [Template of Payment Report](https://go.microsoft.com/fwlink/?linkid=862266).</span></span> 

## <a name="upload-the-payments-data-model-configuration"></a><span data-ttu-id="8c208-109">Carregar a configuração do modelo de dados de pagamentos</span><span class="sxs-lookup"><span data-stu-id="8c208-109">Upload the Payments data model configuration</span></span>
1. <span data-ttu-id="8c208-110">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="8c208-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="8c208-111">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="8c208-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="8c208-112">Selecione o provedor de configuração para a empresa de exemplo, 'Litware, Inc.' Se você não visualizar o provedor de configuração, você deve primeiro concluir as etapas do procedimento “Criar um provedor de configuração e marcá-lo como ativo“.</span><span class="sxs-lookup"><span data-stu-id="8c208-112">Select the configuration provider for sample company, Litware, Inc. If you don’t see this configuration provider, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>  
3. <span data-ttu-id="8c208-113">Clique em Definir como ativo.</span><span class="sxs-lookup"><span data-stu-id="8c208-113">Click Set active.</span></span>
4. <span data-ttu-id="8c208-114">Clique em Repositórios.</span><span class="sxs-lookup"><span data-stu-id="8c208-114">Click Repositories.</span></span>
    * <span data-ttu-id="8c208-115">Selecione um repositório para o tipo Recursos de operações, se disponível.</span><span class="sxs-lookup"><span data-stu-id="8c208-115">Select a repository for the Operations Resources type, if available.</span></span> <span data-ttu-id="8c208-116">Se estiver disponível, pule as etapas a seguir sobre criar um novo repositório.</span><span class="sxs-lookup"><span data-stu-id="8c208-116">If its available, skip the following steps about creating a new repository.</span></span>  
5. <span data-ttu-id="8c208-117">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="8c208-117">Click Add to open the drop dialog.</span></span>
6. <span data-ttu-id="8c208-118">No campo Tipo de repositório de configuração, insira 'Recursos de operações'.</span><span class="sxs-lookup"><span data-stu-id="8c208-118">In the Configuration repository type field, enter 'Operations resources'.</span></span>
7. <span data-ttu-id="8c208-119">Clique em Criar repositório.</span><span class="sxs-lookup"><span data-stu-id="8c208-119">Click Create repository.</span></span>
8. <span data-ttu-id="8c208-120">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="8c208-120">Click OK.</span></span>
9. <span data-ttu-id="8c208-121">Clique em Abrir.</span><span class="sxs-lookup"><span data-stu-id="8c208-121">Click Open.</span></span>
10. <span data-ttu-id="8c208-122">Na árvore, selecione 'Modelo de pagamento'.</span><span class="sxs-lookup"><span data-stu-id="8c208-122">In the tree, select 'Payment model'.</span></span>
11. <span data-ttu-id="8c208-123">Clique em Importar.</span><span class="sxs-lookup"><span data-stu-id="8c208-123">Click Import.</span></span>
    * <span data-ttu-id="8c208-124">Importar este modelo de dados.</span><span class="sxs-lookup"><span data-stu-id="8c208-124">Import this data model.</span></span> <span data-ttu-id="8c208-125">Será usado como a fonte de dados em uma nova configuração de formato.</span><span class="sxs-lookup"><span data-stu-id="8c208-125">It will be used as a data source in a new format configuration.</span></span> <span data-ttu-id="8c208-126">Ignorar essa etapa se essa configuração já tiver sido importada.</span><span class="sxs-lookup"><span data-stu-id="8c208-126">Skip this step if this configuration has been already imported.</span></span>  
12. <span data-ttu-id="8c208-127">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="8c208-127">Click Yes.</span></span>
13. <span data-ttu-id="8c208-128">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8c208-128">Close the page.</span></span>
14. <span data-ttu-id="8c208-129">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8c208-129">Close the page.</span></span>

## <a name="create-a-new-format-configuration"></a><span data-ttu-id="8c208-130">Criar uma nova configuração de formato</span><span class="sxs-lookup"><span data-stu-id="8c208-130">Create a new format configuration</span></span>
1. <span data-ttu-id="8c208-131">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="8c208-131">Click Reporting configurations.</span></span>
2. <span data-ttu-id="8c208-132">Na árvore, selecione 'Modelo de pagamento'.</span><span class="sxs-lookup"><span data-stu-id="8c208-132">In the tree, select 'Payment model'.</span></span>
3. <span data-ttu-id="8c208-133">Clique em Criar configuração para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="8c208-133">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="8c208-134">No campo Novo, insira 'Formato baseado no modelo de dados PaymentModel'.</span><span class="sxs-lookup"><span data-stu-id="8c208-134">In the New field, enter 'Format based on data model PaymentModel'.</span></span>
    * <span data-ttu-id="8c208-135">Criar um formato com base no modelo de dados do PaymentModel.</span><span class="sxs-lookup"><span data-stu-id="8c208-135">Create a format that is based on the PaymentModel data model.</span></span>  
5. <span data-ttu-id="8c208-136">No campo Nome, digite "Relatório de planilha de exemplo".</span><span class="sxs-lookup"><span data-stu-id="8c208-136">In the Name field, type 'Sample worksheet report'.</span></span>
    * <span data-ttu-id="8c208-137">Relatório da planilha de exemplo</span><span class="sxs-lookup"><span data-stu-id="8c208-137">Sample worksheet report</span></span>  
6. <span data-ttu-id="8c208-138">No campo Tipo de descrição, digite "Relatório de planilha de amostra para pagamentos de fornecedor".</span><span class="sxs-lookup"><span data-stu-id="8c208-138">In the Description field, type 'Sample worksheet report for vendors’ payments'.</span></span>
    * <span data-ttu-id="8c208-139">Relatório de planilha de amostra para pagamentos do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="8c208-139">Sample worksheet report for vendors’ payments.</span></span>  
7. <span data-ttu-id="8c208-140">No campo Definição do modelo de dados, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="8c208-140">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="8c208-141">Selecione a definição "CustomerCreditTransferInitiation".</span><span class="sxs-lookup"><span data-stu-id="8c208-141">Select the 'CustomerCreditTransferInitiation' definition.</span></span>  
8. <span data-ttu-id="8c208-142">Clique em Criar configuração.</span><span class="sxs-lookup"><span data-stu-id="8c208-142">Click Create configuration.</span></span>

## <a name="design-a-new-document-in-openxml-worksheet-format"></a><span data-ttu-id="8c208-143">Criar um novo documento no formato da folha OPENXML</span><span class="sxs-lookup"><span data-stu-id="8c208-143">Design a new document in OPENXML worksheet format</span></span>
1. <span data-ttu-id="8c208-144">Na árvore, selecione "Modelo de pagamento\Relatório de planilha de amostra".</span><span class="sxs-lookup"><span data-stu-id="8c208-144">In the tree, select 'Payment model\Sample worksheet report'.</span></span>
2. <span data-ttu-id="8c208-145">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="8c208-145">Click Designer.</span></span>
3. <span data-ttu-id="8c208-146">No Painel de Ação, clique em Importar.</span><span class="sxs-lookup"><span data-stu-id="8c208-146">On the Action Pane, click Import.</span></span>
4. <span data-ttu-id="8c208-147">Clique em Importar do Excel.</span><span class="sxs-lookup"><span data-stu-id="8c208-147">Click Import from Excel.</span></span>
5. <span data-ttu-id="8c208-148">Clique em Anexos.</span><span class="sxs-lookup"><span data-stu-id="8c208-148">Click Attachments.</span></span>
    * <span data-ttu-id="8c208-149">Anexar o documento existente do Excel como um modelo.</span><span class="sxs-lookup"><span data-stu-id="8c208-149">Attach the existing Excel document as a template.</span></span>  
6. <span data-ttu-id="8c208-150">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="8c208-150">Click New.</span></span>
7. <span data-ttu-id="8c208-151">Clique em Arquivo.</span><span class="sxs-lookup"><span data-stu-id="8c208-151">Click File.</span></span>
    * <span data-ttu-id="8c208-152">Apontar para o arquivo existente do Excel.</span><span class="sxs-lookup"><span data-stu-id="8c208-152">Point to the existing Excel file.</span></span>  
8. <span data-ttu-id="8c208-153">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8c208-153">Close the page.</span></span>
9. <span data-ttu-id="8c208-154">No campo Modelo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="8c208-154">In the Template field, enter or select a value.</span></span>
    * <span data-ttu-id="8c208-155">Selecione o arquivo Excel anexado a ser usado como um modelo.</span><span class="sxs-lookup"><span data-stu-id="8c208-155">Select the attached Excel file to be used as a template.</span></span>  
10. <span data-ttu-id="8c208-156">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="8c208-156">Click OK.</span></span>
    * <span data-ttu-id="8c208-157">Observe que os componentes do formato ER foram criados no formato criador com base na estrutura do documento de referência do MS Excel (intervalos nomeados).</span><span class="sxs-lookup"><span data-stu-id="8c208-157">Note that ER format components have been created in the designing format based on the structure of the referring MS Excel document (named ranges).</span></span>  

## <a name="create-a-new-data-source-to-calculate-totals-by-currency-codes"></a><span data-ttu-id="8c208-158">Criar uma nova fonte de dados para calcular totais por código de moeda</span><span class="sxs-lookup"><span data-stu-id="8c208-158">Create a new data source to calculate totals by currency codes</span></span>
1. <span data-ttu-id="8c208-159">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="8c208-159">Click the Mapping tab.</span></span>
2. <span data-ttu-id="8c208-160">Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="8c208-160">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="8c208-161">Na árvore, selecione 'Funções\Agrupar por'.</span><span class="sxs-lookup"><span data-stu-id="8c208-161">In the tree, select 'Functions\Group by'.</span></span>
4. <span data-ttu-id="8c208-162">No campo Nome, digite 'PaymentByCurrency'.</span><span class="sxs-lookup"><span data-stu-id="8c208-162">In the Name field, type 'PaymentByCurrency'.</span></span>
    * <span data-ttu-id="8c208-163">PaymentByCurrency</span><span class="sxs-lookup"><span data-stu-id="8c208-163">PaymentByCurrency</span></span>  
5. <span data-ttu-id="8c208-164">Clique em Editar grupo por.</span><span class="sxs-lookup"><span data-stu-id="8c208-164">Click Edit group by.</span></span>
6. <span data-ttu-id="8c208-165">Na árvore, expanda 'modelo'.</span><span class="sxs-lookup"><span data-stu-id="8c208-165">In the tree, expand 'model'.</span></span>
7. <span data-ttu-id="8c208-166">Na árvore, selecione 'modelo\Pagamentos'.</span><span class="sxs-lookup"><span data-stu-id="8c208-166">In the tree, select 'model\Payments'.</span></span>
8. <span data-ttu-id="8c208-167">Clique em Adicionar campo a.</span><span class="sxs-lookup"><span data-stu-id="8c208-167">Click Add field to.</span></span>
9. <span data-ttu-id="8c208-168">Clique em O que agrupar.</span><span class="sxs-lookup"><span data-stu-id="8c208-168">Click What to group.</span></span>
10. <span data-ttu-id="8c208-169">Na árvore, expanda 'modelo\Pagamentos'.</span><span class="sxs-lookup"><span data-stu-id="8c208-169">In the tree, expand 'model\Payments'.</span></span>
11. <span data-ttu-id="8c208-170">Na árvore, selecione 'modelo\Pagamentos\Moeda'.</span><span class="sxs-lookup"><span data-stu-id="8c208-170">In the tree, select 'model\Payments\Currency'.</span></span>
12. <span data-ttu-id="8c208-171">Clique em Adicionar campo a.</span><span class="sxs-lookup"><span data-stu-id="8c208-171">Click Add field to.</span></span>
13. <span data-ttu-id="8c208-172">Clique em Campos agrupados.</span><span class="sxs-lookup"><span data-stu-id="8c208-172">Click Grouped fields.</span></span>
14. <span data-ttu-id="8c208-173">Na árvore, selecione 'modelo\Pagamentos\Valor instruído(ValorInstruído)'.</span><span class="sxs-lookup"><span data-stu-id="8c208-173">In the tree, select 'model\Payments\Instructed Amount(InstructedAmount)'.</span></span>
15. <span data-ttu-id="8c208-174">Clique em Adicionar campo a.</span><span class="sxs-lookup"><span data-stu-id="8c208-174">Click Add field to.</span></span>
16. <span data-ttu-id="8c208-175">Clique em Campos de agregação.</span><span class="sxs-lookup"><span data-stu-id="8c208-175">Click Aggregation fields.</span></span>
17. <span data-ttu-id="8c208-176">No campo Método, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="8c208-176">In the Method field, select an option.</span></span>
    * <span data-ttu-id="8c208-177">Selecione a função agregada de SUM.</span><span class="sxs-lookup"><span data-stu-id="8c208-177">Select the SUM aggregation function.</span></span>  
18. <span data-ttu-id="8c208-178">No campo Nome, digite 'TotalInstructuredAmount'.</span><span class="sxs-lookup"><span data-stu-id="8c208-178">In the Name field, type 'TotalInstructuredAmount'.</span></span>
    * <span data-ttu-id="8c208-179">TotalInstructuredAmount</span><span class="sxs-lookup"><span data-stu-id="8c208-179">TotalInstructuredAmount</span></span>  
19. <span data-ttu-id="8c208-180">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="8c208-180">Click Save.</span></span>
20. <span data-ttu-id="8c208-181">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8c208-181">Close the page.</span></span>
21. <span data-ttu-id="8c208-182">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="8c208-182">Click OK.</span></span>

## <a name="map-format-components-to-data-sources"></a><span data-ttu-id="8c208-183">Componentes de formato de mapa para fontes de dados</span><span class="sxs-lookup"><span data-stu-id="8c208-183">Map format components to data sources</span></span>
1. <span data-ttu-id="8c208-184">Na árvore, expanda 'modelo'.</span><span class="sxs-lookup"><span data-stu-id="8c208-184">In the tree, expand 'model'.</span></span>
2. <span data-ttu-id="8c208-185">Na árvore, expanda 'modelo\Pagamentos'.</span><span class="sxs-lookup"><span data-stu-id="8c208-185">In the tree, expand 'model\Payments'.</span></span>
3. <span data-ttu-id="8c208-186">Na árvore, expanda "modelo\Pagamentos\Participante Iniciante(InitiatingParty)".</span><span class="sxs-lookup"><span data-stu-id="8c208-186">In the tree, expand 'model\Payments\Initiating Party(InitiatingParty)'.</span></span>
4. <span data-ttu-id="8c208-187">Na árvore, selecione "modelo\Pagamentos\Participante Iniciante(InitiatingParty)\Nome".</span><span class="sxs-lookup"><span data-stu-id="8c208-187">In the tree, select 'model\Payments\Initiating Party(InitiatingParty)\Name'.</span></span>
5. <span data-ttu-id="8c208-188">Na árvore, expanda "Excel\ReportHeader".</span><span class="sxs-lookup"><span data-stu-id="8c208-188">In the tree, expand 'Excel\ReportHeader'.</span></span>
6. <span data-ttu-id="8c208-189">Na árvore, selecione "Excel\ReportHeader\CompanyName".</span><span class="sxs-lookup"><span data-stu-id="8c208-189">In the tree, select 'Excel\ReportHeader\CompanyName'.</span></span>
7. <span data-ttu-id="8c208-190">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="8c208-190">Click Bind.</span></span>
8. <span data-ttu-id="8c208-191">Na árvore, expanda 'modelo\Pagamentos\Credor'.</span><span class="sxs-lookup"><span data-stu-id="8c208-191">In the tree, expand 'model\Payments\Creditor'.</span></span>
9. <span data-ttu-id="8c208-192">Na árvore, expanda 'modelo\Pagamentos\Credor\Identificação'.</span><span class="sxs-lookup"><span data-stu-id="8c208-192">In the tree, expand 'model\Payments\Creditor\Identification'.</span></span>
10. <span data-ttu-id="8c208-193">Na árvore, selecione 'modelo\Pagamentos\Credor\Identificação\ID da fonte(SourceID)'.</span><span class="sxs-lookup"><span data-stu-id="8c208-193">In the tree, select 'model\Payments\Creditor\Identification\Source ID(SourceID)'.</span></span>
11. <span data-ttu-id="8c208-194">Na árvore, expanda "Excel\PaymLines".</span><span class="sxs-lookup"><span data-stu-id="8c208-194">In the tree, expand 'Excel\PaymLines'.</span></span>
12. <span data-ttu-id="8c208-195">Na árvore, selecione "Excel\PaymLines\VendAccountName".</span><span class="sxs-lookup"><span data-stu-id="8c208-195">In the tree, select 'Excel\PaymLines\VendAccountName'.</span></span>
13. <span data-ttu-id="8c208-196">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="8c208-196">Click Bind.</span></span>
14. <span data-ttu-id="8c208-197">Na árvore, selecione 'modelo\Pagamentos\Credor\Nome'.</span><span class="sxs-lookup"><span data-stu-id="8c208-197">In the tree, select 'model\Payments\Creditor\Name'.</span></span>
15. <span data-ttu-id="8c208-198">Na árvore, selecione "Excel\PaymLines\VendName".</span><span class="sxs-lookup"><span data-stu-id="8c208-198">In the tree, select 'Excel\PaymLines\VendName'.</span></span>
16. <span data-ttu-id="8c208-199">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="8c208-199">Click Bind.</span></span>
17. <span data-ttu-id="8c208-200">Na árvore, expanda 'modelo\Pagamentos\Agente do Credor(CreditorAgent)'.</span><span class="sxs-lookup"><span data-stu-id="8c208-200">In the tree, expand 'model\Payments\Creditor Agent(CreditorAgent)'.</span></span>
18. <span data-ttu-id="8c208-201">Na árvore, selecione 'modelo\Pagamentos\Agente do Credor(CreditorAgent)\Nome'.</span><span class="sxs-lookup"><span data-stu-id="8c208-201">In the tree, select 'model\Payments\Creditor Agent(CreditorAgent)\Name'.</span></span>
19. <span data-ttu-id="8c208-202">Na árvore, selecione "Excel\PaymLines\Banco".</span><span class="sxs-lookup"><span data-stu-id="8c208-202">In the tree, select 'Excel\PaymLines\Bank'.</span></span>
20. <span data-ttu-id="8c208-203">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="8c208-203">Click Bind.</span></span>
21. <span data-ttu-id="8c208-204">Na árvore, selecione 'modelo\Pagamentos\Agente credor(CreditorAgent)\Número de roteiro(RoutingNumber)'.</span><span class="sxs-lookup"><span data-stu-id="8c208-204">In the tree, select 'model\Payments\Creditor Agent(CreditorAgent)\Routing Number(RoutingNumber)'.</span></span>
22. <span data-ttu-id="8c208-205">Na árvore, selecione "Excel\PaymLines\RoutingNumber".</span><span class="sxs-lookup"><span data-stu-id="8c208-205">In the tree, select 'Excel\PaymLines\RoutingNumber'.</span></span>
23. <span data-ttu-id="8c208-206">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="8c208-206">Click Bind.</span></span>
24. <span data-ttu-id="8c208-207">Na árvore, expanda 'modelo\Pagamentos\Conta do Credor(CreditorAccount)'.</span><span class="sxs-lookup"><span data-stu-id="8c208-207">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)'.</span></span>
25. <span data-ttu-id="8c208-208">Na árvore, expanda 'modelo\Pagamentos\Conta do Credor(CreditorAccount)\Identificação'.</span><span class="sxs-lookup"><span data-stu-id="8c208-208">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)\Identification'.</span></span>
26. <span data-ttu-id="8c208-209">Na árvore, selecione 'modelo\Pagamentos\Conta do Credor(CreditorAccount)\Identificação\Número'.</span><span class="sxs-lookup"><span data-stu-id="8c208-209">In the tree, select 'model\Payments\Creditor Account(CreditorAccount)\Identification\Number'.</span></span>
27. <span data-ttu-id="8c208-210">Na árvore, selecione "Excel\PaymLines\AccountNumber".</span><span class="sxs-lookup"><span data-stu-id="8c208-210">In the tree, select 'Excel\PaymLines\AccountNumber'.</span></span>
28. <span data-ttu-id="8c208-211">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="8c208-211">Click Bind.</span></span>
29. <span data-ttu-id="8c208-212">Na árvore, selecione 'modelo\Pagamentos\Valor instruído(ValorInstruído)'.</span><span class="sxs-lookup"><span data-stu-id="8c208-212">In the tree, select 'model\Payments\Instructed Amount(InstructedAmount)'.</span></span>
30. <span data-ttu-id="8c208-213">Na árvore, selecione "Excel\PaymLines\Débito".</span><span class="sxs-lookup"><span data-stu-id="8c208-213">In the tree, select 'Excel\PaymLines\Debit'.</span></span>
31. <span data-ttu-id="8c208-214">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="8c208-214">Click Bind.</span></span>
32. <span data-ttu-id="8c208-215">Na árvore, expanda 'modelo\Pagamentos\Credor'.</span><span class="sxs-lookup"><span data-stu-id="8c208-215">In the tree, expand 'model\Payments\Creditor'.</span></span>
33. <span data-ttu-id="8c208-216">Na árvore, expanda 'modelo\Pagamentos\Conta do Credor(CreditorAccount)'.</span><span class="sxs-lookup"><span data-stu-id="8c208-216">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)'.</span></span>
34. <span data-ttu-id="8c208-217">Na árvore, expanda 'modelo\Pagamentos\Agente do Credor(CreditorAgent)'.</span><span class="sxs-lookup"><span data-stu-id="8c208-217">In the tree, expand 'model\Payments\Creditor Agent(CreditorAgent)'.</span></span>
35. <span data-ttu-id="8c208-218">Na árvore, selecione 'modelo\Pagamentos\Moeda'.</span><span class="sxs-lookup"><span data-stu-id="8c208-218">In the tree, select 'model\Payments\Currency'.</span></span>
36. <span data-ttu-id="8c208-219">Na árvore, selecione "Excel\PaymLines\Moeda".</span><span class="sxs-lookup"><span data-stu-id="8c208-219">In the tree, select 'Excel\PaymLines\Currency'.</span></span>
37. <span data-ttu-id="8c208-220">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="8c208-220">Click Bind.</span></span>
38. <span data-ttu-id="8c208-221">Na árvore, expanda 'PaymentByCurrency'.</span><span class="sxs-lookup"><span data-stu-id="8c208-221">In the tree, expand 'PaymentByCurrency'.</span></span>
39. <span data-ttu-id="8c208-222">Na árvore, expanda 'PaymentByCurrency\agrupado'.</span><span class="sxs-lookup"><span data-stu-id="8c208-222">In the tree, expand 'PaymentByCurrency\grouped'.</span></span>
40. <span data-ttu-id="8c208-223">Na árvore, selecione 'PaymentByCurrency\agrupado\Moeda'.</span><span class="sxs-lookup"><span data-stu-id="8c208-223">In the tree, select 'PaymentByCurrency\grouped\Currency'.</span></span>
41. <span data-ttu-id="8c208-224">Na árvore, expanda "Excel\SummaryLines".</span><span class="sxs-lookup"><span data-stu-id="8c208-224">In the tree, expand 'Excel\SummaryLines'.</span></span>
42. <span data-ttu-id="8c208-225">Na árvore, selecione "Excel\SummaryLines\SummaryCurrency".</span><span class="sxs-lookup"><span data-stu-id="8c208-225">In the tree, select 'Excel\SummaryLines\SummaryCurrency'.</span></span>
43. <span data-ttu-id="8c208-226">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="8c208-226">Click Bind.</span></span>
44. <span data-ttu-id="8c208-227">Na árvore, expanda "PaymentByCurrency\agregado".</span><span class="sxs-lookup"><span data-stu-id="8c208-227">In the tree, expand 'PaymentByCurrency\aggregated'.</span></span>
45. <span data-ttu-id="8c208-228">Na árvore, selecione 'PaymentByCurrency\agregado\TotalInstructuredAmount'.</span><span class="sxs-lookup"><span data-stu-id="8c208-228">In the tree, select 'PaymentByCurrency\aggregated\TotalInstructuredAmount'.</span></span>
46. <span data-ttu-id="8c208-229">Na árvore, selecione "Excel\SummaryLines\SummaryAmount".</span><span class="sxs-lookup"><span data-stu-id="8c208-229">In the tree, select 'Excel\SummaryLines\SummaryAmount'.</span></span>
47. <span data-ttu-id="8c208-230">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="8c208-230">Click Bind.</span></span>
48. <span data-ttu-id="8c208-231">Na árvore, selecione 'PaymentByCurrency'.</span><span class="sxs-lookup"><span data-stu-id="8c208-231">In the tree, select 'PaymentByCurrency'.</span></span>
49. <span data-ttu-id="8c208-232">Na árvore, selecione "Excel\SummaryLines".</span><span class="sxs-lookup"><span data-stu-id="8c208-232">In the tree, select 'Excel\SummaryLines'.</span></span>
50. <span data-ttu-id="8c208-233">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="8c208-233">Click Bind.</span></span>
51. <span data-ttu-id="8c208-234">Na árvore, selecione 'modelo\Pagamentos'.</span><span class="sxs-lookup"><span data-stu-id="8c208-234">In the tree, select 'model\Payments'.</span></span>
52. <span data-ttu-id="8c208-235">Na árvore, selecione "Excel\PaymLines".</span><span class="sxs-lookup"><span data-stu-id="8c208-235">In the tree, select 'Excel\PaymLines'.</span></span>
53. <span data-ttu-id="8c208-236">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="8c208-236">Click Bind.</span></span>
54. <span data-ttu-id="8c208-237">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="8c208-237">Click Save.</span></span>
55. <span data-ttu-id="8c208-238">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8c208-238">Close the page.</span></span>

## <a name="use-the-created-configuration-for-payments-processing"></a><span data-ttu-id="8c208-239">Usar a configuração criada para processamento de pagamentos</span><span class="sxs-lookup"><span data-stu-id="8c208-239">Use the created configuration for payments processing</span></span>
1. <span data-ttu-id="8c208-240">Clique em Alterar status.</span><span class="sxs-lookup"><span data-stu-id="8c208-240">Click Change status.</span></span>
2. <span data-ttu-id="8c208-241">Clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="8c208-241">Click Complete.</span></span>
3. <span data-ttu-id="8c208-242">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="8c208-242">Click OK.</span></span>
4. <span data-ttu-id="8c208-243">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8c208-243">Close the page.</span></span>
5. <span data-ttu-id="8c208-244">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8c208-244">Close the page.</span></span>
6. <span data-ttu-id="8c208-245">Vá para Contas a pagar > Configurar pagamento > Métodos de pagamento.</span><span class="sxs-lookup"><span data-stu-id="8c208-245">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
7. <span data-ttu-id="8c208-246">Use o Filtro Rápido para filtrar o campo Method of payment com o valor "Eletrônico".</span><span class="sxs-lookup"><span data-stu-id="8c208-246">Use the Quick Filter to filter on the Method of payment field with a value of 'Electronic'.</span></span>
    * <span data-ttu-id="8c208-247">Eletrônico</span><span class="sxs-lookup"><span data-stu-id="8c208-247">Electronic</span></span>  
8. <span data-ttu-id="8c208-248">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="8c208-248">Click Edit.</span></span>
9. <span data-ttu-id="8c208-249">Expanda a seção Formatos de arquivo.</span><span class="sxs-lookup"><span data-stu-id="8c208-249">Expand the File formats section.</span></span>
10. <span data-ttu-id="8c208-250">Selecione Sim no campo eletrônico Genérico do relatório.</span><span class="sxs-lookup"><span data-stu-id="8c208-250">Select Yes in the Generic electronic reporting field.</span></span>
11. <span data-ttu-id="8c208-251">No campo Exportar configuração de formato, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="8c208-251">In the Export format configuration field, enter or select a value.</span></span>
    * <span data-ttu-id="8c208-252">Selecione a configuração "Relatório de planilha de amostra".</span><span class="sxs-lookup"><span data-stu-id="8c208-252">Select the ‘Sample worksheet report’ configuration.</span></span>  
12. <span data-ttu-id="8c208-253">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="8c208-253">Click Save.</span></span>
13. <span data-ttu-id="8c208-254">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8c208-254">Close the page.</span></span>

## <a name="use-the-created-configuration-for-testing-of-payment-journals-processing"></a><span data-ttu-id="8c208-255">Use a configuração criada para testar de processar diários de pagamentos</span><span class="sxs-lookup"><span data-stu-id="8c208-255">Use the created configuration for testing of payment journals processing</span></span>
1. <span data-ttu-id="8c208-256">Vá para Contas a pagar > Pagamentos > Diário de pagamentos.</span><span class="sxs-lookup"><span data-stu-id="8c208-256">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="8c208-257">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="8c208-257">Click New.</span></span>
    * <span data-ttu-id="8c208-258">Crie um novo diário de pagamento.</span><span class="sxs-lookup"><span data-stu-id="8c208-258">Create a new payment journal.</span></span>  
3. <span data-ttu-id="8c208-259">No campo Nome, digite 'VendPay'.</span><span class="sxs-lookup"><span data-stu-id="8c208-259">In the Name field, type 'VendPay'.</span></span>
    * <span data-ttu-id="8c208-260">VendPay</span><span class="sxs-lookup"><span data-stu-id="8c208-260">VendPay</span></span>  
4. <span data-ttu-id="8c208-261">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="8c208-261">Click Lines.</span></span>
5. <span data-ttu-id="8c208-262">No campo Conta, especifique os valores 'GB_SI_000001'.</span><span class="sxs-lookup"><span data-stu-id="8c208-262">In the Account field, specify the values 'GB_SI_000001'.</span></span>
    * <span data-ttu-id="8c208-263">GB_SI_000001</span><span class="sxs-lookup"><span data-stu-id="8c208-263">GB_SI_000001</span></span>  
6. <span data-ttu-id="8c208-264">Definir Débito como '1000'.</span><span class="sxs-lookup"><span data-stu-id="8c208-264">Set Debit to '1000'.</span></span>
7. <span data-ttu-id="8c208-265">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="8c208-265">Click New.</span></span>
8. <span data-ttu-id="8c208-266">No campo Conta, especifique os valores 'GB_SI_000005'.</span><span class="sxs-lookup"><span data-stu-id="8c208-266">In the Account field, specify the values 'GB_SI_000005'.</span></span>
    * <span data-ttu-id="8c208-267">GB_SI_000005</span><span class="sxs-lookup"><span data-stu-id="8c208-267">GB_SI_000005</span></span>  
9. <span data-ttu-id="8c208-268">Definir Débito como '2000'.</span><span class="sxs-lookup"><span data-stu-id="8c208-268">Set Debit to '2000'.</span></span>
10. <span data-ttu-id="8c208-269">No campo Moeda, digite 'EUR'.</span><span class="sxs-lookup"><span data-stu-id="8c208-269">In the Currency field, type 'EUR'.</span></span>
    * <span data-ttu-id="8c208-270">EUR</span><span class="sxs-lookup"><span data-stu-id="8c208-270">EUR</span></span>  
11. <span data-ttu-id="8c208-271">No campo Contrapartida, especifique os valores 'GBSI OPER'.</span><span class="sxs-lookup"><span data-stu-id="8c208-271">In the Offset account field, specify the values 'GBSI OPER'.</span></span>
    * <span data-ttu-id="8c208-272">GBSI OPER</span><span class="sxs-lookup"><span data-stu-id="8c208-272">GBSI OPER</span></span>  
12. <span data-ttu-id="8c208-273">No campo Método de pagamento, digite "Eletrônico".</span><span class="sxs-lookup"><span data-stu-id="8c208-273">In the Method of payment field, type 'Electronic'.</span></span>
    * <span data-ttu-id="8c208-274">Eletrônico</span><span class="sxs-lookup"><span data-stu-id="8c208-274">Electronic</span></span>  
13. <span data-ttu-id="8c208-275">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="8c208-275">Click Save.</span></span>
14. <span data-ttu-id="8c208-276">Clique em Gerar pagamentos.</span><span class="sxs-lookup"><span data-stu-id="8c208-276">Click Generate payments.</span></span>
15. <span data-ttu-id="8c208-277">No campo Método de pagamento, digite "Eletrônico".</span><span class="sxs-lookup"><span data-stu-id="8c208-277">In the Method of payment field, type 'Electronic'.</span></span>
    * <span data-ttu-id="8c208-278">Eletrônico</span><span class="sxs-lookup"><span data-stu-id="8c208-278">Electronic</span></span>  
16. <span data-ttu-id="8c208-279">No campo Nome do arquivo, digite "Pagamentos".</span><span class="sxs-lookup"><span data-stu-id="8c208-279">In the File name field, type 'Payments'.</span></span>
    * <span data-ttu-id="8c208-280">Por exemplo, digite Pagamentos.</span><span class="sxs-lookup"><span data-stu-id="8c208-280">For example, type Payments.</span></span>  
17. <span data-ttu-id="8c208-281">No campo Conta bancária, digite 'GBSI OPER'.</span><span class="sxs-lookup"><span data-stu-id="8c208-281">In the Bank account field, type 'GBSI OPER'.</span></span>
    * <span data-ttu-id="8c208-282">GBSI OPER</span><span class="sxs-lookup"><span data-stu-id="8c208-282">GBSI OPER</span></span>  
18. <span data-ttu-id="8c208-283">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="8c208-283">Click OK.</span></span>
19. <span data-ttu-id="8c208-284">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="8c208-284">Click OK.</span></span>
    * <span data-ttu-id="8c208-285">Revise a planilha criada, incluindo detalhes de linhas de pagamento além do total para cada código de moeda usado na mensagem de pagamento.</span><span class="sxs-lookup"><span data-stu-id="8c208-285">Review the created worksheet, including details of payment lines as well as totals for each currency code used in this payment message.</span></span>  



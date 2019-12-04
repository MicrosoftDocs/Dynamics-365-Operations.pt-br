---
title: ER Usar intervalos expansíveis horizontalmente para adicionar colunas dinamicamente em relatórios do Excel (Parte 1 - Criar formato)
description: As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou de desenvolvedor de relatório eletrônico (ER) pode configurar um formato para gerar relatórios como arquivos OPENXML de planilhas de Excel em que as colunas exigidas possam ser criadas dinamicamente como intervalos expansíveis horizontalmente.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b616998738d6b6986f157d136fc56e061900ef41
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550523"
---
# <a name="er-use-horizontally-expandable-ranges-to-dynamically-add-columns-in-excel-reports-part-1---design-format"></a><span data-ttu-id="448c5-103">ER Usar intervalos expansíveis horizontalmente para adicionar colunas dinamicamente em relatórios do Excel (Parte 1 - Criar formato)</span><span class="sxs-lookup"><span data-stu-id="448c5-103">ER Use horizontally expandable ranges to dynamically add columns in Excel reports (Part 1 - Design format)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="448c5-104">As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou de desenvolvedor de relatório eletrônico (ER) pode configurar um formato para gerar relatórios como arquivos OPENXML de planilhas de Excel em que as colunas exigidas possam ser criadas dinamicamente como intervalos expansíveis horizontalmente.</span><span class="sxs-lookup"><span data-stu-id="448c5-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to generate reports as OPENXML worksheets (Excel) files in which the required columns can be created dynamically as horizontally expandable ranges.</span></span> <span data-ttu-id="448c5-105">Essas etapas podem ser executadas em qualquer empresa.</span><span class="sxs-lookup"><span data-stu-id="448c5-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="448c5-106">Para concluir essas etapas, primeiro você deve concluir essas guias de três tarefas:</span><span class="sxs-lookup"><span data-stu-id="448c5-106">To complete these steps, you must first complete these three task guides:</span></span> 

<span data-ttu-id="448c5-107">"ER Criar um provedor de configuração e marcá-lo como ativo"</span><span class="sxs-lookup"><span data-stu-id="448c5-107">“ER Create a configuration provider and mark it as active”</span></span>

<span data-ttu-id="448c5-108">"ER Usar dimensões financeiras como uma fonte de dados (Parte 1: Modelo de dados de design)"</span><span class="sxs-lookup"><span data-stu-id="448c5-108">“ER Use financial dimensions as a data source (Part 1: Design data model)”</span></span>

<span data-ttu-id="448c5-109">"ER Usar dimensões financeiras como uma fonte de dados (Parte 2: mapeamento de modelo)"</span><span class="sxs-lookup"><span data-stu-id="448c5-109">“ER Use financial dimensions as a data source (Part 2: Model mapping)”</span></span>

<span data-ttu-id="448c5-110">Você também deve baixar e salvar uma cópia local do modelo com um relatório de exemplo encontrado aqui, [Relatório de Serviço Web de Dimensões Financeiras de Exemplo](https://go.microsoft.com/fwlink/?linkid=862266).</span><span class="sxs-lookup"><span data-stu-id="448c5-110">You must also download and save a local copy of the template with a sample report found here, [Sample Financial Dimensions Web Service Report](https://go.microsoft.com/fwlink/?linkid=862266).</span></span>

<span data-ttu-id="448c5-111">Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="448c5-111">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-new-report-configuration"></a><span data-ttu-id="448c5-112">Criar uma nova configuração de relatório</span><span class="sxs-lookup"><span data-stu-id="448c5-112">Create a new report configuration</span></span>
1. <span data-ttu-id="448c5-113">Vá para Administração da organização > Relatório eletrônico > Configurações.</span><span class="sxs-lookup"><span data-stu-id="448c5-113">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="448c5-114">Na árvore, selecione "Modelo de amostra de dimensão financeira".</span><span class="sxs-lookup"><span data-stu-id="448c5-114">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="448c5-115">Clique em Criar configuração para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="448c5-115">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="448c5-116">No campo Novo, insira 'Formato baseado no modelo de dados modelo de amostra de dimensões financeiras'.</span><span class="sxs-lookup"><span data-stu-id="448c5-116">In the New field, enter 'Format based on data model Financial dimensions sample model'.</span></span>
    * <span data-ttu-id="448c5-117">Use o modelo criado antecipadamente como a fonte de dados de seu novo relatório.</span><span class="sxs-lookup"><span data-stu-id="448c5-117">Use the model created in advance as the data source for your new report.</span></span>  
5. <span data-ttu-id="448c5-118">No campo Nome, digite 'Relatório de exemplo com intervalos expansíveis horizontalmente'.</span><span class="sxs-lookup"><span data-stu-id="448c5-118">In the Name field, type 'Sample report with horizontally expandable ranges'.</span></span>
    * <span data-ttu-id="448c5-119">Relatório de exemplo com intervalos expansíveis horizontalmente</span><span class="sxs-lookup"><span data-stu-id="448c5-119">Sample report with horizontally expandable ranges</span></span>  
6. <span data-ttu-id="448c5-120">No campo Descrição, digite 'Para fazer saída do Excel com a adição de colunas dinamicamente'.</span><span class="sxs-lookup"><span data-stu-id="448c5-120">In the Description field, type 'To make Excel output with dynamically adding columns'.</span></span>
    * <span data-ttu-id="448c5-121">Para fazer saída do Excel com a adição de colunas dinamicamente</span><span class="sxs-lookup"><span data-stu-id="448c5-121">To make Excel output with dynamically adding columns</span></span>  
7. <span data-ttu-id="448c5-122">No campo Definição de modelo de dados, selecione Entrada.</span><span class="sxs-lookup"><span data-stu-id="448c5-122">In the Data model definition field, select Entry.</span></span>
8. <span data-ttu-id="448c5-123">Clique em Criar configuração.</span><span class="sxs-lookup"><span data-stu-id="448c5-123">Click Create configuration.</span></span>

## <a name="design-the-report-format"></a><span data-ttu-id="448c5-124">Criar o formato do relatório</span><span class="sxs-lookup"><span data-stu-id="448c5-124">Design the report format</span></span>
1. <span data-ttu-id="448c5-125">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="448c5-125">Click Designer.</span></span>
2. <span data-ttu-id="448c5-126">Ative o botão de alternância 'Mostrar detalhes'.</span><span class="sxs-lookup"><span data-stu-id="448c5-126">Turn on the ‘Show details’ toggle button.</span></span>
3. <span data-ttu-id="448c5-127">No Painel de Ação, clique em Importar.</span><span class="sxs-lookup"><span data-stu-id="448c5-127">On the Action Pane, click Import.</span></span>
4. <span data-ttu-id="448c5-128">Clique em Importar do Excel.</span><span class="sxs-lookup"><span data-stu-id="448c5-128">Click Import from Excel.</span></span>
5. <span data-ttu-id="448c5-129">Clique em Anexos.</span><span class="sxs-lookup"><span data-stu-id="448c5-129">Click Attachments.</span></span>
    * <span data-ttu-id="448c5-130">Importe o modelo do relatório.</span><span class="sxs-lookup"><span data-stu-id="448c5-130">Import the report’s template.</span></span> <span data-ttu-id="448c5-131">Use o arquivo Excel que você baixou para isso.</span><span class="sxs-lookup"><span data-stu-id="448c5-131">Use Excel file that you downloaded for that.</span></span>  
6. <span data-ttu-id="448c5-132">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="448c5-132">Click New.</span></span>
7. <span data-ttu-id="448c5-133">Clique em Arquivo.</span><span class="sxs-lookup"><span data-stu-id="448c5-133">Click File.</span></span>
8. <span data-ttu-id="448c5-134">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="448c5-134">Close the page.</span></span>
9. <span data-ttu-id="448c5-135">No campo Modelo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="448c5-135">In the Template field, enter or select a value.</span></span>
    * <span data-ttu-id="448c5-136">Selecione o modelo baixado.</span><span class="sxs-lookup"><span data-stu-id="448c5-136">Select the downloaded template.</span></span>  
10. <span data-ttu-id="448c5-137">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="448c5-137">Click OK.</span></span>
    * <span data-ttu-id="448c5-138">Adicione um novo intervalo para criar dinamicamente saídas do Excel com quantas colunas você selecionar (no formulário da caixa de diálogo do usuário) para as dimensões financeiras.</span><span class="sxs-lookup"><span data-stu-id="448c5-138">Add a new range to dynamically create Excel output with as many columns as you selected (in the user dialog form) for financial dimensions.</span></span> <span data-ttu-id="448c5-139">Cada célula para cada coluna representará o nome de uma única dimensão financeira.</span><span class="sxs-lookup"><span data-stu-id="448c5-139">Each cell for every column will represent a single financial dimension’s name.</span></span>  
11. <span data-ttu-id="448c5-140">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="448c5-140">Click Add to open the drop dialog.</span></span>
12. <span data-ttu-id="448c5-141">Na árvore, selecione 'Excel\Intervalo'.</span><span class="sxs-lookup"><span data-stu-id="448c5-141">In the tree, select 'Excel\Range'.</span></span>
13. <span data-ttu-id="448c5-142">No campo Intervalo do Excel, digite 'DimNames'.</span><span class="sxs-lookup"><span data-stu-id="448c5-142">In the Excel range field, type 'DimNames'.</span></span>
    * <span data-ttu-id="448c5-143">DimNames</span><span class="sxs-lookup"><span data-stu-id="448c5-143">DimNames</span></span>  
14. <span data-ttu-id="448c5-144">No campo Direção de replicações, selecione 'Horizontal'.</span><span class="sxs-lookup"><span data-stu-id="448c5-144">In the Replication direction field, select 'Horizontal'.</span></span>
15. <span data-ttu-id="448c5-145">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="448c5-145">Click OK.</span></span>
16. <span data-ttu-id="448c5-146">Na árvore, selecione 'Excel = "SampleFinDimWsReport"\Intervalo<DimNames>: Horizontal'.</span><span class="sxs-lookup"><span data-stu-id="448c5-146">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal'.</span></span>
17. <span data-ttu-id="448c5-147">Clique em Mover para cima.</span><span class="sxs-lookup"><span data-stu-id="448c5-147">Click Move up.</span></span>
18. <span data-ttu-id="448c5-148">Na árvore, selecione 'Excel = "SampleFinDimWsReport"\Célula<DimNames>'.</span><span class="sxs-lookup"><span data-stu-id="448c5-148">In the tree, select 'Excel = "SampleFinDimWsReport"\Cell<DimNames>'.</span></span>
19. <span data-ttu-id="448c5-149">Clique em Recortar.</span><span class="sxs-lookup"><span data-stu-id="448c5-149">Click Cut.</span></span>
20. <span data-ttu-id="448c5-150">Na árvore, selecione 'Excel = "SampleFinDimWsReport"\Intervalo<DimNames>: Horizontal'.</span><span class="sxs-lookup"><span data-stu-id="448c5-150">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal'.</span></span>
21. <span data-ttu-id="448c5-151">Clique em Colar.</span><span class="sxs-lookup"><span data-stu-id="448c5-151">Click Paste.</span></span>
22. <span data-ttu-id="448c5-152">Na árvore, expanda 'Excel = "SampleFinDimWsReport"\Intervalo<DimNames>: Horizontal'.</span><span class="sxs-lookup"><span data-stu-id="448c5-152">In the tree, expand 'Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal'.</span></span>
23. <span data-ttu-id="448c5-153">Na árvore, expanda 'Excel = "SampleFinDimWsReport"\Intervalo<JournalLine>: Vertical'.</span><span class="sxs-lookup"><span data-stu-id="448c5-153">In the tree, expand 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical'.</span></span>
24. <span data-ttu-id="448c5-154">Na árvore, expanda 'Excel = "SampleFinDimWsReport"\Intervalo<JournalLine>: Vertical\Intervalo<TransactionLine>: Vertical'.</span><span class="sxs-lookup"><span data-stu-id="448c5-154">In the tree, expand 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical'.</span></span>
25. <span data-ttu-id="448c5-155">Na árvore, selecione 'Excel = "SampleFinDimWsReport"\Intervalo<JournalLine>: Vertical\Intervalo<TransactionLine>: Vertical'.</span><span class="sxs-lookup"><span data-stu-id="448c5-155">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical'.</span></span>
    * <span data-ttu-id="448c5-156">Adicione um novo intervalo para criar dinamicamente saídas do Excel com quantas colunas você selecionar (no formulário da caixa de diálogo do usuário) para as dimensões financeiras.</span><span class="sxs-lookup"><span data-stu-id="448c5-156">Add a new range to dynamically create Excel output with as many columns as you selected (in the user dialog form) for financial dimensions.</span></span> <span data-ttu-id="448c5-157">Cada célula para cada coluna representará o valor de uma única dimensão financeira para cada transação do relatório.</span><span class="sxs-lookup"><span data-stu-id="448c5-157">Each cell for every column will represent a single financial dimension’s value for each reporting transaction.</span></span>  
26. <span data-ttu-id="448c5-158">Clique em Adicionar intervalo.</span><span class="sxs-lookup"><span data-stu-id="448c5-158">Click Add Range.</span></span>
27. <span data-ttu-id="448c5-159">No campo Intervalo do Excel, digite 'DimValues'.</span><span class="sxs-lookup"><span data-stu-id="448c5-159">In the Excel range field, type 'DimValues'.</span></span>
    * <span data-ttu-id="448c5-160">DimValues</span><span class="sxs-lookup"><span data-stu-id="448c5-160">DimValues</span></span>  
28. <span data-ttu-id="448c5-161">No campo Direção de replicações, selecione 'Horizontal'.</span><span class="sxs-lookup"><span data-stu-id="448c5-161">In the Replication direction field, select 'Horizontal'.</span></span>
29. <span data-ttu-id="448c5-162">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="448c5-162">Click OK.</span></span>
30. <span data-ttu-id="448c5-163">Na árvore, selecione 'Excel = "SampleFinDimWsReport"\Intervalo<JournalLine>: Vertical\Intervalo<TransactionLine>: Vertical\Célula<DimValues>'.</span><span class="sxs-lookup"><span data-stu-id="448c5-163">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<DimValues>'.</span></span>
31. <span data-ttu-id="448c5-164">Clique em Recortar.</span><span class="sxs-lookup"><span data-stu-id="448c5-164">Click Cut.</span></span>
32. <span data-ttu-id="448c5-165">Na árvore, selecione 'Excel = "SampleFinDimWsReport"\Intervalo<JournalLine>: Vertical\Intervalo<TransactionLine>: Vertical\Intervalo<DimValues>: Horizontal'.</span><span class="sxs-lookup"><span data-stu-id="448c5-165">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal'.</span></span>
33. <span data-ttu-id="448c5-166">Clique em Colar.</span><span class="sxs-lookup"><span data-stu-id="448c5-166">Click Paste.</span></span>
34. <span data-ttu-id="448c5-167">Na árvore, expanda 'Excel = "SampleFinDimWsReport"\Intervalo<JournalLine>: Vertical\Intervalo<TransactionLine>: Vertical\Intervalo<DimValues>: Horizontal'.</span><span class="sxs-lookup"><span data-stu-id="448c5-167">In the tree, expand 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal'.</span></span>

## <a name="map-format-elements-to-data-sources"></a><span data-ttu-id="448c5-168">Mapear elementos de formato para as fontes de dados</span><span class="sxs-lookup"><span data-stu-id="448c5-168">Map format elements to data sources</span></span>
1. <span data-ttu-id="448c5-169">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="448c5-169">Click the Mapping tab.</span></span>
2. <span data-ttu-id="448c5-170">Na árvore, expanda "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados".</span><span class="sxs-lookup"><span data-stu-id="448c5-170">In the tree, expand 'model: Data model Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="448c5-171">Na árvore, expanda "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="448c5-171">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
4. <span data-ttu-id="448c5-172">Na árvore, expanda "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="448c5-172">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
5. <span data-ttu-id="448c5-173">Na árvore, expanda "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Dados de dimensões: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="448c5-173">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
6. <span data-ttu-id="448c5-174">Na árvore, selecione 'Excel = "SampleFinDimWsReport"\Intervalo<JournalLine>: Vertical\Intervalo<TransactionLine>: Vertical\Intervalo<DimValues>: Horizontal\Célula<DimValues>'.</span><span class="sxs-lookup"><span data-stu-id="448c5-174">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal\Cell<DimValues>'.</span></span>
7. <span data-ttu-id="448c5-175">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Dados de dimensões: Lista de registros\Código: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="448c5-175">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String'.</span></span>
8. <span data-ttu-id="448c5-176">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="448c5-176">Click Bind.</span></span>
9. <span data-ttu-id="448c5-177">Na árvore, selecione 'Excel = "SampleFinDimWsReport"\Intervalo<JournalLine>: Vertical\Intervalo<TransactionLine>: Vertical\Intervalo<DimValues>: Horizontal'.</span><span class="sxs-lookup"><span data-stu-id="448c5-177">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal'.</span></span>
10. <span data-ttu-id="448c5-178">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Dados de dimensões: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="448c5-178">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
11. <span data-ttu-id="448c5-179">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="448c5-179">Click Bind.</span></span>
12. <span data-ttu-id="448c5-180">Na árvore, selecione 'Excel = "SampleFinDimWsReport"\Intervalo<JournalLine>: Vertical\Intervalo<TransactionLine>: Vertical\Célula<Credit>'.</span><span class="sxs-lookup"><span data-stu-id="448c5-180">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<Credit>'.</span></span>
13. <span data-ttu-id="448c5-181">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Crédito: Real".</span><span class="sxs-lookup"><span data-stu-id="448c5-181">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real'.</span></span>
14. <span data-ttu-id="448c5-182">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="448c5-182">Click Bind.</span></span>
15. <span data-ttu-id="448c5-183">Na árvore, selecione 'Excel = "SampleFinDimWsReport"\Intervalo<JournalLine>: Vertical\Intervalo<TransactionLine>: Vertical\Célula<Debit>'.</span><span class="sxs-lookup"><span data-stu-id="448c5-183">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<Debit>'.</span></span>
16. <span data-ttu-id="448c5-184">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Débito: Real".</span><span class="sxs-lookup"><span data-stu-id="448c5-184">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real'.</span></span>
17. <span data-ttu-id="448c5-185">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="448c5-185">Click Bind.</span></span>
18. <span data-ttu-id="448c5-186">Na árvore, selecione 'Excel = "SampleFinDimWsReport"\Intervalo<JournalLine>: Vertical\Intervalo<TransactionLine>: Vertical\Célula<Currency>'.</span><span class="sxs-lookup"><span data-stu-id="448c5-186">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<Currency>'.</span></span>
19. <span data-ttu-id="448c5-187">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Moeda: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="448c5-187">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String'.</span></span>
20. <span data-ttu-id="448c5-188">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="448c5-188">Click Bind.</span></span>
21. <span data-ttu-id="448c5-189">Na árvore, selecione 'Excel = "SampleFinDimWsReport"\Intervalo<JournalLine>: Vertical\Intervalo<TransactionLine>: Vertical\Célula<TransDate>'.</span><span class="sxs-lookup"><span data-stu-id="448c5-189">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<TransDate>'.</span></span>
22. <span data-ttu-id="448c5-190">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Data: Data".</span><span class="sxs-lookup"><span data-stu-id="448c5-190">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date'.</span></span>
23. <span data-ttu-id="448c5-191">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="448c5-191">Click Bind.</span></span>
24. <span data-ttu-id="448c5-192">Na árvore, selecione 'Excel = "SampleFinDimWsReport"\Intervalo<JournalLine>: Vertical\Intervalo<TransactionLine>: Vertical\Célula<TransVoucher>'.</span><span class="sxs-lookup"><span data-stu-id="448c5-192">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<TransVoucher>'.</span></span>
25. <span data-ttu-id="448c5-193">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Comprovante: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="448c5-193">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String'.</span></span>
26. <span data-ttu-id="448c5-194">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="448c5-194">Click Bind.</span></span>
27. <span data-ttu-id="448c5-195">Na árvore, selecione 'Excel = "SampleFinDimWsReport"\Intervalo<JournalLine>: Vertical\Intervalo<TransactionLine>: Vertical\Célula<TransBatch>'.</span><span class="sxs-lookup"><span data-stu-id="448c5-195">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<TransBatch>'.</span></span>
28. <span data-ttu-id="448c5-196">Na árvore, selecione 'modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Lote: Sequência de caracteres'.</span><span class="sxs-lookup"><span data-stu-id="448c5-196">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Batch: String'.</span></span>
29. <span data-ttu-id="448c5-197">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="448c5-197">Click Bind.</span></span>
30. <span data-ttu-id="448c5-198">Na árvore, selecione 'Excel = "SampleFinDimWsReport"\Intervalo<JournalLine>: Vertical\Intervalo<TransactionLine>: Vertical'.</span><span class="sxs-lookup"><span data-stu-id="448c5-198">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical'.</span></span>
31. <span data-ttu-id="448c5-199">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="448c5-199">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
32. <span data-ttu-id="448c5-200">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="448c5-200">Click Bind.</span></span>
33. <span data-ttu-id="448c5-201">Na árvore, selecione 'Excel = "SampleFinDimWsReport"\Intervalo<JournalLine>: Vertical\Célula<Batch>'.</span><span class="sxs-lookup"><span data-stu-id="448c5-201">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Cell<Batch>'.</span></span>
34. <span data-ttu-id="448c5-202">Na árvore, selecione 'modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Lote: Sequência de caracteres'.</span><span class="sxs-lookup"><span data-stu-id="448c5-202">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Batch: String'.</span></span>
35. <span data-ttu-id="448c5-203">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="448c5-203">Click Bind.</span></span>
36. <span data-ttu-id="448c5-204">Na árvore, selecione 'Excel = "SampleFinDimWsReport"\Intervalo<JournalLine>: Vertical'.</span><span class="sxs-lookup"><span data-stu-id="448c5-204">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical'.</span></span>
37. <span data-ttu-id="448c5-205">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="448c5-205">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
38. <span data-ttu-id="448c5-206">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="448c5-206">Click Bind.</span></span>
39. <span data-ttu-id="448c5-207">Na árvore, expanda 'modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Configuração de dimensões: Lista de registros'.</span><span class="sxs-lookup"><span data-stu-id="448c5-207">In the tree, expand 'model: Data model Financial dimensions sample model\Dimensions setting: Record list'.</span></span>
40. <span data-ttu-id="448c5-208">Na árvore, selecione 'modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Configuração de dimensões: Lista de registros\Código: Sequência de caracteres'.</span><span class="sxs-lookup"><span data-stu-id="448c5-208">In the tree, select 'model: Data model Financial dimensions sample model\Dimensions setting: Record list\Code: String'.</span></span>
41. <span data-ttu-id="448c5-209">Na árvore, selecione 'Excel = "SampleFinDimWsReport"\Intervalo<DimNames>: Horizontal\Célula<DimNames>'.</span><span class="sxs-lookup"><span data-stu-id="448c5-209">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal\Cell<DimNames>'.</span></span>
42. <span data-ttu-id="448c5-210">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="448c5-210">Click Bind.</span></span>
43. <span data-ttu-id="448c5-211">Na árvore, selecione 'modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Configuração de dimensões: Lista de registros'.</span><span class="sxs-lookup"><span data-stu-id="448c5-211">In the tree, select 'model: Data model Financial dimensions sample model\Dimensions setting: Record list'.</span></span>
44. <span data-ttu-id="448c5-212">Na árvore, selecione 'Excel = "SampleFinDimWsReport"\Intervalo<DimNames>: Horizontal'.</span><span class="sxs-lookup"><span data-stu-id="448c5-212">In the tree, select 'Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal'.</span></span>
45. <span data-ttu-id="448c5-213">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="448c5-213">Click Bind.</span></span>
46. <span data-ttu-id="448c5-214">Na árvore, selecione 'Excel = "SampleFinDimWsReport"\Célula<CompanyName>'.</span><span class="sxs-lookup"><span data-stu-id="448c5-214">In the tree, select 'Excel = "SampleFinDimWsReport"\Cell<CompanyName>'.</span></span>
47. <span data-ttu-id="448c5-215">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Empresa: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="448c5-215">In the tree, select 'model: Data model Financial dimensions sample model\Company: String'.</span></span>
48. <span data-ttu-id="448c5-216">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="448c5-216">Click Bind.</span></span>
49. <span data-ttu-id="448c5-217">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="448c5-217">Click Save.</span></span>
50. <span data-ttu-id="448c5-218">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="448c5-218">Close the page.</span></span>

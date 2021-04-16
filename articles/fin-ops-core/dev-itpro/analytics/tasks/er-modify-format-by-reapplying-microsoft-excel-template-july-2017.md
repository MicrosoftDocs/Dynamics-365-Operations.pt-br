---
title: Modificar formatos ao reaplicar modelos do Excel
description: Para completar as etapas deste procedimento, primeiro você deve concluir o procedimento ER - Criar uma configuração para gerar relatórios no formato OPENXML.
author: NickSelin
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 24eb64679b458d14e30dc5b4365c7305d71cfc4c
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5754881"
---
# <a name="modify-formats-by-reapplying-excel-templates"></a><span data-ttu-id="27405-103">Modificar formatos ao reaplicar modelos do Excel</span><span class="sxs-lookup"><span data-stu-id="27405-103">Modify formats by reapplying Excel templates</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="27405-104">Para completar as etapas deste procedimento, primeiro você deve concluir o procedimento ER - Criar uma configuração para gerar relatórios no formato OPENXML.</span><span class="sxs-lookup"><span data-stu-id="27405-104">To complete the steps in this procedure, you must first complete the procedure, ER - Design a configuration for generating reports in OPENXML format.</span></span>

<span data-ttu-id="27405-105">Este procedimento explica como modificar uma configuração de formato de relatório eletrônico (ER) reaplicando um modelo modificado do Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="27405-105">This procedure explains how to modify an Electronic reporting (ER) format configuration by reapplying a Microsoft Excel template that has been modified.</span></span> <span data-ttu-id="27405-106">Nesse procedimento, você importará um modelo do Excel modificado para configurações de formato de ER que foi criado para a empresa exemplo, Litware, Inc., e depois gerará documentos eletrônicos.</span><span class="sxs-lookup"><span data-stu-id="27405-106">In this procedure, you will import a modified Excel template into ER format configurations that have been created for the sample company, Litware, Inc., and then generate electronic documents.</span></span> <span data-ttu-id="27405-107">Esse procedimento é destinado a usuários com a função de administrador do sistema ou desenvolvedor de relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="27405-107">This procedure is intended for users who have the system administrator or electronic reporting developer role.</span></span> <span data-ttu-id="27405-108">Estas etapas podem ser concluídas usando o conjunto de dados de GBSI.</span><span class="sxs-lookup"><span data-stu-id="27405-108">These steps can be completed by using the GBSI dataset.</span></span> <span data-ttu-id="27405-109">Antes de começar, faça download e salve o arquivo SampleVendPaymWsReport2.xlsx que é listado no tópico de Ajuda. Modifique o formato de relatório eletrônico reaplicando um modelo do Excel (modify-electronic-reporting-format-reapply-excel-template/).</span><span class="sxs-lookup"><span data-stu-id="27405-109">Before you begin, download and save the file, SampleVendPaymWsReport2.xlsx, which is listed in the Help topic, Modify Electronic reporting format by reapplying an Excel template (modify-electronic-reporting-format-reapply-excel-template/).</span></span>

1. <span data-ttu-id="27405-110">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="27405-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="27405-111">Verifique se o provedor de configuração da empresa exemplo, Litware, Inc., está disponível e marcado como Ativo.</span><span class="sxs-lookup"><span data-stu-id="27405-111">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as Active.</span></span> <span data-ttu-id="27405-112">Se não visualizar este provedor de configuração, conclua as etapas no procedimento Criar um provedor de configuração e marcá-lo como ativo.</span><span class="sxs-lookup"><span data-stu-id="27405-112">If you don't see this configuration provider, complete the steps in the procedure, Create a configuration provider and mark it as active.</span></span>  

## <a name="select-the-er-format"></a><span data-ttu-id="27405-113">Selecione o formato de ER</span><span class="sxs-lookup"><span data-stu-id="27405-113">Select the ER format</span></span>
1. <span data-ttu-id="27405-114">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="27405-114">Click Reporting configurations.</span></span>
2. <span data-ttu-id="27405-115">Na árvore, expanda 'Modelo de pagamento'.</span><span class="sxs-lookup"><span data-stu-id="27405-115">In the tree, expand 'Payment model'.</span></span>
3. <span data-ttu-id="27405-116">Na árvore, selecione "Modelo de pagamento\Relatório de planilha de amostra".</span><span class="sxs-lookup"><span data-stu-id="27405-116">In the tree, select 'Payment model\Sample worksheet report'.</span></span>
4. <span data-ttu-id="27405-117">Clique em Anexos.</span><span class="sxs-lookup"><span data-stu-id="27405-117">Click Attachments.</span></span>
    * <span data-ttu-id="27405-118">Observe que o arquivo de Excel SampleVendPaymWsReport.xlsx atualmente é usado como modelo para o processamento do diário de pagamento.</span><span class="sxs-lookup"><span data-stu-id="27405-118">Note that the SampleVendPaymWsReport.xlsx Excel file is currently used as a template for payment journal processing.</span></span>   
5. <span data-ttu-id="27405-119">Clique em Abrir.</span><span class="sxs-lookup"><span data-stu-id="27405-119">Click Open.</span></span>
    * <span data-ttu-id="27405-120">Clique em Abrir para explorar o layout do modelo do Excel.</span><span class="sxs-lookup"><span data-stu-id="27405-120">Click Open to explore the layout of the Excel template.</span></span>  
    * <span data-ttu-id="27405-121">Revise o modelo.</span><span class="sxs-lookup"><span data-stu-id="27405-121">Review the template.</span></span> <span data-ttu-id="27405-122">Observe que atualmente ele inclui os seguintes detalhes de cada linha de pagamento: número de conta de fornecedor, nome do fornecedor, banco, número de roteiro, número da conta, débito, crédito e moeda.</span><span class="sxs-lookup"><span data-stu-id="27405-122">Note that it currently includes the following details for each payment line: vendor account number, vendor name, bank, routing number, account number, debit, credit, and currency.</span></span> <span data-ttu-id="27405-123">Para este exemplo, queremos estender esta lista, adicionando detalhes sobre a data de pagamento.</span><span class="sxs-lookup"><span data-stu-id="27405-123">For this example, we want to extend this list by adding details about the payment date.</span></span>   
6. <span data-ttu-id="27405-124">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="27405-124">Close the page.</span></span>

## <a name="reapply-a-new-excel-template-to-er-format"></a><span data-ttu-id="27405-125">Reaplique um novo modelo de Excel para o formato de ER</span><span class="sxs-lookup"><span data-stu-id="27405-125">Reapply a new Excel template to ER format</span></span>
1. <span data-ttu-id="27405-126">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="27405-126">Click Designer.</span></span>
    * <span data-ttu-id="27405-127">Abre a versão de rascunho de formato de ER selecionado para edição.</span><span class="sxs-lookup"><span data-stu-id="27405-127">Open the draft version of the selected ER format for editing.</span></span>  
2. <span data-ttu-id="27405-128">No Painel de Ação, clique em Importar.</span><span class="sxs-lookup"><span data-stu-id="27405-128">On the Action Pane, click Import.</span></span>
3. <span data-ttu-id="27405-129">Clique em Atualizar do Excel.</span><span class="sxs-lookup"><span data-stu-id="27405-129">Click Update from Excel.</span></span>
    * <span data-ttu-id="27405-130">Clique em "Atualizar modelo" e, em seguida, selecione o arquivo, SampleVendPaymWsReport2.xlsx.</span><span class="sxs-lookup"><span data-stu-id="27405-130">Click 'Update template', and then select the file, SampleVendPaymWsReport2.xlsx.</span></span>  
    * <span data-ttu-id="27405-131">Clique em Atualizar modelo e procure o arquivo SampleVendPaymWsReport2.xlsx baixado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="27405-131">Click Update template and browse to get the downloaded earlier SampleVendPaymWsReport2.xlsx file.</span></span>  
4. <span data-ttu-id="27405-132">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="27405-132">Click OK.</span></span>
    * <span data-ttu-id="27405-133">O modelo SampleVendPaymWsReport2.xlsx é aplicado.</span><span class="sxs-lookup"><span data-stu-id="27405-133">The SampleVendPaymWsReport2.xlsx template is applied.</span></span> <span data-ttu-id="27405-134">A estrutura de formato de ER é sincronizada com o conteúdo do modelo, cujos elementos são adicionados ao formato de ER.</span><span class="sxs-lookup"><span data-stu-id="27405-134">The structure of the ER format is synchronized with the content of the template, whose elements are added to the ER format.</span></span> <span data-ttu-id="27405-135">Todos os elementos existentes no formato de ER que não estão incluídos no modelo são removidos da definição de formato.</span><span class="sxs-lookup"><span data-stu-id="27405-135">Any existing elements in the ER format that aren't included in the template are removed from the format definition.</span></span>  
5. <span data-ttu-id="27405-136">Na árvore, selecione 'Excel'.</span><span class="sxs-lookup"><span data-stu-id="27405-136">In the tree, select 'Excel'.</span></span>
    * <span data-ttu-id="27405-137">Observe que o campo Modelo agora contém uma referência para o novo modelo.</span><span class="sxs-lookup"><span data-stu-id="27405-137">Note that the Template field now contains a reference to the new template.</span></span>   
6. <span data-ttu-id="27405-138">Clique em Anexos.</span><span class="sxs-lookup"><span data-stu-id="27405-138">Click Attachments.</span></span>
7. <span data-ttu-id="27405-139">Clique em Abrir.</span><span class="sxs-lookup"><span data-stu-id="27405-139">Click Open.</span></span>
    * <span data-ttu-id="27405-140">Clique em Abrir para explorar o layout do modelo do Excel modificado.</span><span class="sxs-lookup"><span data-stu-id="27405-140">Click Open to explore the layout of the modified Excel template.</span></span>  
    * <span data-ttu-id="27405-141">Revise o modelo.</span><span class="sxs-lookup"><span data-stu-id="27405-141">Review the template.</span></span> <span data-ttu-id="27405-142">Observe que agora ele contém uma linha para a data de pagamento.</span><span class="sxs-lookup"><span data-stu-id="27405-142">Note that it now contains a line for the payment date.</span></span>   
8. <span data-ttu-id="27405-143">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="27405-143">Close the page.</span></span>
9. <span data-ttu-id="27405-144">Na árvore, expanda 'Excel'.</span><span class="sxs-lookup"><span data-stu-id="27405-144">In the tree, expand 'Excel'.</span></span>
10. <span data-ttu-id="27405-145">Na árvore, expanda "Excel\PaymLines".</span><span class="sxs-lookup"><span data-stu-id="27405-145">In the tree, expand 'Excel\PaymLines'.</span></span>
11. <span data-ttu-id="27405-146">Na árvore, selecione 'Excel\PaymLines\PaymDate'.</span><span class="sxs-lookup"><span data-stu-id="27405-146">In the tree, select 'Excel\PaymLines\PaymDate'.</span></span>
    * <span data-ttu-id="27405-147">Observe que o formato de ER agora contém mais um item.</span><span class="sxs-lookup"><span data-stu-id="27405-147">Note that the ER format now contains one more item.</span></span> <span data-ttu-id="27405-148">Uma célula, PaymDate, foi adicionada ao modelo do Excel.</span><span class="sxs-lookup"><span data-stu-id="27405-148">A cell, PaymDate, has been added to the Excel template.</span></span>  
12. <span data-ttu-id="27405-149">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="27405-149">Click the Mapping tab.</span></span>
13. <span data-ttu-id="27405-150">Na árvore, expanda 'modelo'.</span><span class="sxs-lookup"><span data-stu-id="27405-150">In the tree, expand 'model'.</span></span>
14. <span data-ttu-id="27405-151">Na árvore, expanda 'modelo\Pagamentos'.</span><span class="sxs-lookup"><span data-stu-id="27405-151">In the tree, expand 'model\Payments'.</span></span>
15. <span data-ttu-id="27405-152">Na árvore, selecione 'modelo\Pagamentos\Data da transação(DataTransação)'.</span><span class="sxs-lookup"><span data-stu-id="27405-152">In the tree, select 'model\Payments\Transaction date(TransactionDate)'.</span></span>
16. <span data-ttu-id="27405-153">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="27405-153">Click Bind.</span></span>
    * <span data-ttu-id="27405-154">Especifique os dados que são adicionados à nova célula no tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="27405-154">Specify what data is added to the new cell at runtime.</span></span>  
17. <span data-ttu-id="27405-155">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="27405-155">Click Save.</span></span>
18. <span data-ttu-id="27405-156">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="27405-156">Close the page.</span></span>

## <a name="enable-the-modified-draft-version-of-the-er-format-for-use-in-payment-journal-processing"></a><span data-ttu-id="27405-157">Habilite a versão de rascunho alterada do formato de ER para usar no processamento do diário de pagamento</span><span class="sxs-lookup"><span data-stu-id="27405-157">Enable the modified draft version of the ER format for use in payment journal processing</span></span>
1. <span data-ttu-id="27405-158">No Painel de Ação, clique em Configurações.</span><span class="sxs-lookup"><span data-stu-id="27405-158">On the Action Pane, click Configurations.</span></span>
2. <span data-ttu-id="27405-159">Clique em Parâmetros de usuário.</span><span class="sxs-lookup"><span data-stu-id="27405-159">Click User parameters.</span></span>
3. <span data-ttu-id="27405-160">Selecione Sim no campo Executar configurações.</span><span class="sxs-lookup"><span data-stu-id="27405-160">Select Yes in the Run settings field.</span></span>
4. <span data-ttu-id="27405-161">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="27405-161">Click OK.</span></span>
5. <span data-ttu-id="27405-162">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="27405-162">Click Edit.</span></span>
6. <span data-ttu-id="27405-163">Selecione Sim no campo Executar Rascunho.</span><span class="sxs-lookup"><span data-stu-id="27405-163">Select Yes in the Run Draft field.</span></span>

## <a name="use-the-modified-draft-version-of-the-er-format-for-payment-journal-processing"></a><span data-ttu-id="27405-164">Use a versão de rascunho alterada do formato de ER para processamento do diário de pagamento</span><span class="sxs-lookup"><span data-stu-id="27405-164">Use the modified draft version of the ER format for payment journal processing</span></span>

<span data-ttu-id="27405-165">Revise a planilha criada, incluindo novos detalhes de linhas de pagamento – data de pagamento.</span><span class="sxs-lookup"><span data-stu-id="27405-165">Review the created worksheet, including new detail of payment lines – payment date.</span></span>  


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
---
title: ER Usar arquivos de gerenciamento de documentos em formato de saída (Parte 5 - Modificar e executar o formato)
description: Este tópico descreve como configurar um formato de relatório eletrônico (ER) para usar arquivos de gerenciamento de documentos (anexos) na saída de ER. (Parte 5)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERComponentTypeDropDialog, ERExpressionDesignerFormula, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f954b76a09bf7c5edd4c608d400318fbd9386778
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5749084"
---
# <a name="er-use-document-management-files-in-format-outputs-part-5---modify-and-run-format"></a><span data-ttu-id="ddbec-104">ER Usar arquivos de gerenciamento de documentos em formato de saída (Parte 5 - Modificar e executar o formato)</span><span class="sxs-lookup"><span data-stu-id="ddbec-104">ER Use Document Management files in format outputs (Part 5 - Modify and run format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ddbec-105">As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para usar arquivos de gerenciamento de documentos (anexos) na saída do ER.</span><span class="sxs-lookup"><span data-stu-id="ddbec-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="ddbec-106">Essas etapas podem ser executadas na empresa DEMF.</span><span class="sxs-lookup"><span data-stu-id="ddbec-106">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="ddbec-107">Para concluir estas etapas, primeiro você deve concluir as etapas no procedimento "ER Usar arquivos de gerenciamento de documentos em saídas de formato (Parte 4: executar formato)".</span><span class="sxs-lookup"><span data-stu-id="ddbec-107">To complete these steps, you must first complete the steps in the "ER Use Document Management files in format outputs (Part 4: Run format)" procedure.</span></span>

<span data-ttu-id="ddbec-108">Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="ddbec-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="modify-the-format-to-populate-attachments-into-generating-messages-in-binary-format"></a><span data-ttu-id="ddbec-109">Modificar o formato para popular anexos para a geração de mensagens no formato binário</span><span class="sxs-lookup"><span data-stu-id="ddbec-109">Modify the format to populate attachments into generating messages in binary format</span></span>
1. <span data-ttu-id="ddbec-110">Vá para Administração da organização > Relatório eletrônico > Configurações.</span><span class="sxs-lookup"><span data-stu-id="ddbec-110">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="ddbec-111">Na árvore, expanda 'Modelo de fatura de cliente'.</span><span class="sxs-lookup"><span data-stu-id="ddbec-111">In the tree, expand 'Customer invoice model'.</span></span>
3. <span data-ttu-id="ddbec-112">Na árvore, expanda 'Modelo de fatura de cliente\Modelo de fatura de cliente (personalizada)'.</span><span class="sxs-lookup"><span data-stu-id="ddbec-112">In the tree, expand 'Customer invoice model\Customer invoice model (custom)'.</span></span>
4. <span data-ttu-id="ddbec-113">Na árvore, selecione 'Modelo de fatura de cliente\Modelo de fatura de cliente (personalizada)\Mensagem de exemplo da fatura eletrônica'.</span><span class="sxs-lookup"><span data-stu-id="ddbec-113">In the tree, select 'Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message'.</span></span>
5. <span data-ttu-id="ddbec-114">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="ddbec-114">Click Designer.</span></span>
    * <span data-ttu-id="ddbec-115">Você preencherá a mensagem da fatura na saída gerada como um arquivo XML usando a codificação UNICODE.</span><span class="sxs-lookup"><span data-stu-id="ddbec-115">You will populate the invoice message in the generating output as an XML file using UNICODE encoding.</span></span>  
6. <span data-ttu-id="ddbec-116">Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="ddbec-116">Click Add root to open the drop dialog.</span></span>
7. <span data-ttu-id="ddbec-117">Na árvore, selecione 'Comum\Arquivo'.</span><span class="sxs-lookup"><span data-stu-id="ddbec-117">In the tree, select 'Common\File'.</span></span>
8. <span data-ttu-id="ddbec-118">No campo Nome, digite 'Mensagem Xml'.</span><span class="sxs-lookup"><span data-stu-id="ddbec-118">In the Name field, type 'Xml message'.</span></span>
    * <span data-ttu-id="ddbec-119">Mensagem Xml</span><span class="sxs-lookup"><span data-stu-id="ddbec-119">Xml message</span></span>  
9. <span data-ttu-id="ddbec-120">No campo Codificação, digite 'UTF-8'.</span><span class="sxs-lookup"><span data-stu-id="ddbec-120">In the Encoding field, type 'UTF-8'.</span></span>
    * <span data-ttu-id="ddbec-121">UTF-8</span><span class="sxs-lookup"><span data-stu-id="ddbec-121">UTF-8</span></span>  
10. <span data-ttu-id="ddbec-122">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="ddbec-122">Click OK.</span></span>
    * <span data-ttu-id="ddbec-123">Configurar as saídas geradas como arquivo compactado.</span><span class="sxs-lookup"><span data-stu-id="ddbec-123">Configure the generating output as a zipped file.</span></span>  
11. <span data-ttu-id="ddbec-124">Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="ddbec-124">Click Add root to open the drop dialog.</span></span>
12. <span data-ttu-id="ddbec-125">Na árvore, selecione 'Comum\Pasta'.</span><span class="sxs-lookup"><span data-stu-id="ddbec-125">In the tree, select 'Common\Folder'.</span></span>
13. <span data-ttu-id="ddbec-126">No campo Nome, digite 'Saída Zip'.</span><span class="sxs-lookup"><span data-stu-id="ddbec-126">In the Name field, type 'Zip output'.</span></span>
    * <span data-ttu-id="ddbec-127">Saída Zip</span><span class="sxs-lookup"><span data-stu-id="ddbec-127">Zip output</span></span>  
14. <span data-ttu-id="ddbec-128">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="ddbec-128">Click OK.</span></span>
15. <span data-ttu-id="ddbec-129">Na árvore, selecione 'Saída Zip'.</span><span class="sxs-lookup"><span data-stu-id="ddbec-129">In the tree, select 'Zip output'.</span></span>
    * <span data-ttu-id="ddbec-130">Adicionar anexos ao arquivo compactado gerado como arquivos com extensões e nomes originais.</span><span class="sxs-lookup"><span data-stu-id="ddbec-130">Add attachments to the generating zipped file as files with original names and extensions.</span></span>  
16. <span data-ttu-id="ddbec-131">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="ddbec-131">Click Add to open the drop dialog.</span></span>
17. <span data-ttu-id="ddbec-132">Na árvore, selecione 'Comum\Arquivo'.</span><span class="sxs-lookup"><span data-stu-id="ddbec-132">In the tree, select 'Common\File'.</span></span>
18. <span data-ttu-id="ddbec-133">No campo Nome, digite 'Arquivo anexo'.</span><span class="sxs-lookup"><span data-stu-id="ddbec-133">In the Name field, type 'Attached file'.</span></span>
    * <span data-ttu-id="ddbec-134">Arquivo anexo</span><span class="sxs-lookup"><span data-stu-id="ddbec-134">Attached file</span></span>  
19. <span data-ttu-id="ddbec-135">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="ddbec-135">Click OK.</span></span>
20. <span data-ttu-id="ddbec-136">Na árvore, selecione 'Saída Zip\Arquivo anexo'.</span><span class="sxs-lookup"><span data-stu-id="ddbec-136">In the tree, select 'Zip output\Attached file'.</span></span>
21. <span data-ttu-id="ddbec-137">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="ddbec-137">Click Add to open the drop dialog.</span></span>
22. <span data-ttu-id="ddbec-138">Na árvore, selecione 'Texto\Base64'.</span><span class="sxs-lookup"><span data-stu-id="ddbec-138">In the tree, select 'Text\Base64'.</span></span>
23. <span data-ttu-id="ddbec-139">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="ddbec-139">Click OK.</span></span>

## <a name="map-new-format-elements-to-data-model"></a><span data-ttu-id="ddbec-140">Mapear novos elementos de formato no modelo de dados</span><span class="sxs-lookup"><span data-stu-id="ddbec-140">Map new format elements to data model</span></span>
1. <span data-ttu-id="ddbec-141">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="ddbec-141">Click the Mapping tab.</span></span>
2. <span data-ttu-id="ddbec-142">Na árvore, expanda 'modelo'.</span><span class="sxs-lookup"><span data-stu-id="ddbec-142">In the tree, expand 'model'.</span></span>
3. <span data-ttu-id="ddbec-143">Na árvore, expanda 'modelo\Anexos da fatura'.</span><span class="sxs-lookup"><span data-stu-id="ddbec-143">In the tree, expand 'model\Invoice attachments'.</span></span>
4. <span data-ttu-id="ddbec-144">Na árvore, selecione 'Saída Zip\Arquivo anexo\Base64'.</span><span class="sxs-lookup"><span data-stu-id="ddbec-144">In the tree, select 'Zip output\Attached file\Base64'.</span></span>
5. <span data-ttu-id="ddbec-145">Na árvore, selecione 'modelo\Anexos da fatura\Conteúdo do arquivo'.</span><span class="sxs-lookup"><span data-stu-id="ddbec-145">In the tree, select 'model\Invoice attachments\File content'.</span></span>
6. <span data-ttu-id="ddbec-146">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="ddbec-146">Click Bind.</span></span>
7. <span data-ttu-id="ddbec-147">Na árvore, selecione 'Saída Zip\Arquivo anexo'.</span><span class="sxs-lookup"><span data-stu-id="ddbec-147">In the tree, select 'Zip output\Attached file'.</span></span>
8. <span data-ttu-id="ddbec-148">Clique em Editar nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="ddbec-148">Click Edit filename.</span></span>
9. <span data-ttu-id="ddbec-149">Na árvore, expanda 'modelo'.</span><span class="sxs-lookup"><span data-stu-id="ddbec-149">In the tree, expand 'model'.</span></span>
10. <span data-ttu-id="ddbec-150">Na árvore, expanda 'modelo\Anexos da fatura'.</span><span class="sxs-lookup"><span data-stu-id="ddbec-150">In the tree, expand 'model\Invoice attachments'.</span></span>
11. <span data-ttu-id="ddbec-151">Na árvore, selecione 'modelo\Anexos da fatura\Nome do arquivo'.</span><span class="sxs-lookup"><span data-stu-id="ddbec-151">In the tree, select 'model\Invoice attachments\File name'.</span></span>
12. <span data-ttu-id="ddbec-152">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="ddbec-152">Click Add data source.</span></span>
13. <span data-ttu-id="ddbec-153">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="ddbec-153">Click Save.</span></span>
14. <span data-ttu-id="ddbec-154">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="ddbec-154">Close the page.</span></span>
15. <span data-ttu-id="ddbec-155">Na árvore, selecione 'modelo\Anexos da fatura'.</span><span class="sxs-lookup"><span data-stu-id="ddbec-155">In the tree, select 'model\Invoice attachments'.</span></span>
16. <span data-ttu-id="ddbec-156">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="ddbec-156">Click Bind.</span></span>
17. <span data-ttu-id="ddbec-157">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="ddbec-157">Click Save.</span></span>
18. <span data-ttu-id="ddbec-158">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="ddbec-158">Close the page.</span></span>

## <a name="run-the-designed-report-for-the-selected-invoice"></a><span data-ttu-id="ddbec-159">Executar relatório criado para a fatura selecionada</span><span class="sxs-lookup"><span data-stu-id="ddbec-159">Run the designed report for the selected invoice</span></span>
1. <span data-ttu-id="ddbec-160">Clique em Executar.</span><span class="sxs-lookup"><span data-stu-id="ddbec-160">Click Run.</span></span>
2. <span data-ttu-id="ddbec-161">Expanda os Registros para incluir a seção ().</span><span class="sxs-lookup"><span data-stu-id="ddbec-161">Expand the Records to include () section.</span></span>
3. <span data-ttu-id="ddbec-162">Clique em Filtro.</span><span class="sxs-lookup"><span data-stu-id="ddbec-162">Click Filter.</span></span>
4. <span data-ttu-id="ddbec-163">Selecione a linha do diário de faturas do cliente e o campo Ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="ddbec-163">Select the row of the Customer invoice journal and the Sales order field.</span></span>
5. <span data-ttu-id="ddbec-164">No campo Critérios, no campo do critério "Ordem de venda" digite o número de ordem 000148.</span><span class="sxs-lookup"><span data-stu-id="ddbec-164">In the Criteria field, In the criteria "Sales order" field, type the order number 000148.</span></span>
    * <span data-ttu-id="ddbec-165">000148</span><span class="sxs-lookup"><span data-stu-id="ddbec-165">000148</span></span>  
6. <span data-ttu-id="ddbec-166">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="ddbec-166">Click OK.</span></span>
7. <span data-ttu-id="ddbec-167">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="ddbec-167">Click OK.</span></span>
    * <span data-ttu-id="ddbec-168">Revise a saída gerada.</span><span class="sxs-lookup"><span data-stu-id="ddbec-168">Review the generated output.</span></span> <span data-ttu-id="ddbec-169">Observe que, além da mensagem da fatura em formato XML, um único arquivo foi criado para cada anexo.</span><span class="sxs-lookup"><span data-stu-id="ddbec-169">Note,that in addition to the invoice message in XML format, a single file has been created for each attachment.</span></span> <span data-ttu-id="ddbec-170">Os arquivos anexos são preenchidos com as saídas compactadas em formato binário.</span><span class="sxs-lookup"><span data-stu-id="ddbec-170">The attachment files are populated with the zipped output in binary format.</span></span>  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
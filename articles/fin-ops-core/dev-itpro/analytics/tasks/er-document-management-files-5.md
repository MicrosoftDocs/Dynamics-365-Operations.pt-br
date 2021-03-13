---
title: ER Usar arquivos de gerenciamento de documentos em formato de saída (Parte 5 - Modificar e executar o formato)
description: Este tópico descreve como configurar um formato de relatório eletrônico (ER) para usar arquivos de gerenciamento de documentos (anexos) na saída de ER. (Parte 5)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERComponentTypeDropDialog, ERExpressionDesignerFormula, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f96189163d5ecac47ade9f713b3fd689e41352d0
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092479"
---
# <a name="er-use-document-management-files-in-format-outputs-part-5---modify-and-run-format"></a><span data-ttu-id="40634-104">ER Usar arquivos de gerenciamento de documentos em formato de saída (Parte 5 - Modificar e executar o formato)</span><span class="sxs-lookup"><span data-stu-id="40634-104">ER Use Document Management files in format outputs (Part 5 - Modify and run format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="40634-105">As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para usar arquivos de gerenciamento de documentos (anexos) na saída do ER.</span><span class="sxs-lookup"><span data-stu-id="40634-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="40634-106">Essas etapas podem ser executadas na empresa DEMF.</span><span class="sxs-lookup"><span data-stu-id="40634-106">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="40634-107">Para concluir estas etapas, primeiro você deve concluir as etapas no procedimento "ER Usar arquivos de gerenciamento de documentos em saídas de formato (Parte 4: executar formato)".</span><span class="sxs-lookup"><span data-stu-id="40634-107">To complete these steps, you must first complete the steps in the "ER Use Document Management files in format outputs (Part 4: Run format)" procedure.</span></span>

<span data-ttu-id="40634-108">Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="40634-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="modify-the-format-to-populate-attachments-into-generating-messages-in-binary-format"></a><span data-ttu-id="40634-109">Modificar o formato para popular anexos para a geração de mensagens no formato binário</span><span class="sxs-lookup"><span data-stu-id="40634-109">Modify the format to populate attachments into generating messages in binary format</span></span>
1. <span data-ttu-id="40634-110">Vá para Administração da organização > Relatório eletrônico > Configurações.</span><span class="sxs-lookup"><span data-stu-id="40634-110">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="40634-111">Na árvore, expanda 'Modelo de fatura de cliente'.</span><span class="sxs-lookup"><span data-stu-id="40634-111">In the tree, expand 'Customer invoice model'.</span></span>
3. <span data-ttu-id="40634-112">Na árvore, expanda 'Modelo de fatura de cliente\Modelo de fatura de cliente (personalizada)'.</span><span class="sxs-lookup"><span data-stu-id="40634-112">In the tree, expand 'Customer invoice model\Customer invoice model (custom)'.</span></span>
4. <span data-ttu-id="40634-113">Na árvore, selecione 'Modelo de fatura de cliente\Modelo de fatura de cliente (personalizada)\Mensagem de exemplo da fatura eletrônica'.</span><span class="sxs-lookup"><span data-stu-id="40634-113">In the tree, select 'Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message'.</span></span>
5. <span data-ttu-id="40634-114">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="40634-114">Click Designer.</span></span>
    * <span data-ttu-id="40634-115">Você preencherá a mensagem da fatura na saída gerada como um arquivo XML usando a codificação UNICODE.</span><span class="sxs-lookup"><span data-stu-id="40634-115">You will populate the invoice message in the generating output as an XML file using UNICODE encoding.</span></span>  
6. <span data-ttu-id="40634-116">Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="40634-116">Click Add root to open the drop dialog.</span></span>
7. <span data-ttu-id="40634-117">Na árvore, selecione 'Comum\Arquivo'.</span><span class="sxs-lookup"><span data-stu-id="40634-117">In the tree, select 'Common\File'.</span></span>
8. <span data-ttu-id="40634-118">No campo Nome, digite 'Mensagem Xml'.</span><span class="sxs-lookup"><span data-stu-id="40634-118">In the Name field, type 'Xml message'.</span></span>
    * <span data-ttu-id="40634-119">Mensagem Xml</span><span class="sxs-lookup"><span data-stu-id="40634-119">Xml message</span></span>  
9. <span data-ttu-id="40634-120">No campo Codificação, digite 'UTF-8'.</span><span class="sxs-lookup"><span data-stu-id="40634-120">In the Encoding field, type 'UTF-8'.</span></span>
    * <span data-ttu-id="40634-121">UTF-8</span><span class="sxs-lookup"><span data-stu-id="40634-121">UTF-8</span></span>  
10. <span data-ttu-id="40634-122">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="40634-122">Click OK.</span></span>
    * <span data-ttu-id="40634-123">Configurar as saídas geradas como arquivo compactado.</span><span class="sxs-lookup"><span data-stu-id="40634-123">Configure the generating output as a zipped file.</span></span>  
11. <span data-ttu-id="40634-124">Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="40634-124">Click Add root to open the drop dialog.</span></span>
12. <span data-ttu-id="40634-125">Na árvore, selecione 'Comum\Pasta'.</span><span class="sxs-lookup"><span data-stu-id="40634-125">In the tree, select 'Common\Folder'.</span></span>
13. <span data-ttu-id="40634-126">No campo Nome, digite 'Saída Zip'.</span><span class="sxs-lookup"><span data-stu-id="40634-126">In the Name field, type 'Zip output'.</span></span>
    * <span data-ttu-id="40634-127">Saída Zip</span><span class="sxs-lookup"><span data-stu-id="40634-127">Zip output</span></span>  
14. <span data-ttu-id="40634-128">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="40634-128">Click OK.</span></span>
15. <span data-ttu-id="40634-129">Na árvore, selecione 'Saída Zip'.</span><span class="sxs-lookup"><span data-stu-id="40634-129">In the tree, select 'Zip output'.</span></span>
    * <span data-ttu-id="40634-130">Adicionar anexos ao arquivo compactado gerado como arquivos com extensões e nomes originais.</span><span class="sxs-lookup"><span data-stu-id="40634-130">Add attachments to the generating zipped file as files with original names and extensions.</span></span>  
16. <span data-ttu-id="40634-131">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="40634-131">Click Add to open the drop dialog.</span></span>
17. <span data-ttu-id="40634-132">Na árvore, selecione 'Comum\Arquivo'.</span><span class="sxs-lookup"><span data-stu-id="40634-132">In the tree, select 'Common\File'.</span></span>
18. <span data-ttu-id="40634-133">No campo Nome, digite 'Arquivo anexo'.</span><span class="sxs-lookup"><span data-stu-id="40634-133">In the Name field, type 'Attached file'.</span></span>
    * <span data-ttu-id="40634-134">Arquivo anexo</span><span class="sxs-lookup"><span data-stu-id="40634-134">Attached file</span></span>  
19. <span data-ttu-id="40634-135">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="40634-135">Click OK.</span></span>
20. <span data-ttu-id="40634-136">Na árvore, selecione 'Saída Zip\Arquivo anexo'.</span><span class="sxs-lookup"><span data-stu-id="40634-136">In the tree, select 'Zip output\Attached file'.</span></span>
21. <span data-ttu-id="40634-137">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="40634-137">Click Add to open the drop dialog.</span></span>
22. <span data-ttu-id="40634-138">Na árvore, selecione 'Texto\Base64'.</span><span class="sxs-lookup"><span data-stu-id="40634-138">In the tree, select 'Text\Base64'.</span></span>
23. <span data-ttu-id="40634-139">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="40634-139">Click OK.</span></span>

## <a name="map-new-format-elements-to-data-model"></a><span data-ttu-id="40634-140">Mapear novos elementos de formato no modelo de dados</span><span class="sxs-lookup"><span data-stu-id="40634-140">Map new format elements to data model</span></span>
1. <span data-ttu-id="40634-141">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="40634-141">Click the Mapping tab.</span></span>
2. <span data-ttu-id="40634-142">Na árvore, expanda 'modelo'.</span><span class="sxs-lookup"><span data-stu-id="40634-142">In the tree, expand 'model'.</span></span>
3. <span data-ttu-id="40634-143">Na árvore, expanda 'modelo\Anexos da fatura'.</span><span class="sxs-lookup"><span data-stu-id="40634-143">In the tree, expand 'model\Invoice attachments'.</span></span>
4. <span data-ttu-id="40634-144">Na árvore, selecione 'Saída Zip\Arquivo anexo\Base64'.</span><span class="sxs-lookup"><span data-stu-id="40634-144">In the tree, select 'Zip output\Attached file\Base64'.</span></span>
5. <span data-ttu-id="40634-145">Na árvore, selecione 'modelo\Anexos da fatura\Conteúdo do arquivo'.</span><span class="sxs-lookup"><span data-stu-id="40634-145">In the tree, select 'model\Invoice attachments\File content'.</span></span>
6. <span data-ttu-id="40634-146">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="40634-146">Click Bind.</span></span>
7. <span data-ttu-id="40634-147">Na árvore, selecione 'Saída Zip\Arquivo anexo'.</span><span class="sxs-lookup"><span data-stu-id="40634-147">In the tree, select 'Zip output\Attached file'.</span></span>
8. <span data-ttu-id="40634-148">Clique em Editar nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="40634-148">Click Edit filename.</span></span>
9. <span data-ttu-id="40634-149">Na árvore, expanda 'modelo'.</span><span class="sxs-lookup"><span data-stu-id="40634-149">In the tree, expand 'model'.</span></span>
10. <span data-ttu-id="40634-150">Na árvore, expanda 'modelo\Anexos da fatura'.</span><span class="sxs-lookup"><span data-stu-id="40634-150">In the tree, expand 'model\Invoice attachments'.</span></span>
11. <span data-ttu-id="40634-151">Na árvore, selecione 'modelo\Anexos da fatura\Nome do arquivo'.</span><span class="sxs-lookup"><span data-stu-id="40634-151">In the tree, select 'model\Invoice attachments\File name'.</span></span>
12. <span data-ttu-id="40634-152">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="40634-152">Click Add data source.</span></span>
13. <span data-ttu-id="40634-153">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="40634-153">Click Save.</span></span>
14. <span data-ttu-id="40634-154">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="40634-154">Close the page.</span></span>
15. <span data-ttu-id="40634-155">Na árvore, selecione 'modelo\Anexos da fatura'.</span><span class="sxs-lookup"><span data-stu-id="40634-155">In the tree, select 'model\Invoice attachments'.</span></span>
16. <span data-ttu-id="40634-156">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="40634-156">Click Bind.</span></span>
17. <span data-ttu-id="40634-157">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="40634-157">Click Save.</span></span>
18. <span data-ttu-id="40634-158">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="40634-158">Close the page.</span></span>

## <a name="run-the-designed-report-for-the-selected-invoice"></a><span data-ttu-id="40634-159">Executar relatório criado para a fatura selecionada</span><span class="sxs-lookup"><span data-stu-id="40634-159">Run the designed report for the selected invoice</span></span>
1. <span data-ttu-id="40634-160">Clique em Executar.</span><span class="sxs-lookup"><span data-stu-id="40634-160">Click Run.</span></span>
2. <span data-ttu-id="40634-161">Expanda os Registros para incluir a seção ().</span><span class="sxs-lookup"><span data-stu-id="40634-161">Expand the Records to include () section.</span></span>
3. <span data-ttu-id="40634-162">Clique em Filtro.</span><span class="sxs-lookup"><span data-stu-id="40634-162">Click Filter.</span></span>
4. <span data-ttu-id="40634-163">Selecione a linha do diário de faturas do cliente e o campo Ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="40634-163">Select the row of the Customer invoice journal and the Sales order field.</span></span>
5. <span data-ttu-id="40634-164">No campo Critérios, no campo do critério "Ordem de venda" digite o número de ordem 000148.</span><span class="sxs-lookup"><span data-stu-id="40634-164">In the Criteria field, In the criteria "Sales order" field, type the order number 000148.</span></span>
    * <span data-ttu-id="40634-165">000148</span><span class="sxs-lookup"><span data-stu-id="40634-165">000148</span></span>  
6. <span data-ttu-id="40634-166">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="40634-166">Click OK.</span></span>
7. <span data-ttu-id="40634-167">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="40634-167">Click OK.</span></span>
    * <span data-ttu-id="40634-168">Revise a saída gerada.</span><span class="sxs-lookup"><span data-stu-id="40634-168">Review the generated output.</span></span> <span data-ttu-id="40634-169">Observe que, além da mensagem da fatura em formato XML, um único arquivo foi criado para cada anexo.</span><span class="sxs-lookup"><span data-stu-id="40634-169">Note,that in addition to the invoice message in XML format, a single file has been created for each attachment.</span></span> <span data-ttu-id="40634-170">Os arquivos anexos são preenchidos com as saídas compactadas em formato binário.</span><span class="sxs-lookup"><span data-stu-id="40634-170">The attachment files are populated with the zipped output in binary format.</span></span>  


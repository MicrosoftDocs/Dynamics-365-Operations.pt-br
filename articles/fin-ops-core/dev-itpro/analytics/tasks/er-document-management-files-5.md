---
title: ER Usar arquivos de gerenciamento de documentos em formato de saída (Parte 5 - Modificar e executar o formato)
description: As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para usar arquivos de gerenciamento de documentos (anexos) na saída do ER.
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
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: de075899547d194fb9eb0e68947efd005c101851
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550685"
---
# <a name="er-use-document-management-files-in-format-outputs-part-5---modify-and-run-format"></a><span data-ttu-id="7de87-103">ER Usar arquivos de gerenciamento de documentos em formato de saída (Parte 5 - Modificar e executar o formato)</span><span class="sxs-lookup"><span data-stu-id="7de87-103">ER Use Document Management files in format outputs (Part 5 - Modify and run format)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7de87-104">As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para usar arquivos de gerenciamento de documentos (anexos) na saída do ER.</span><span class="sxs-lookup"><span data-stu-id="7de87-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="7de87-105">Essas etapas podem ser executadas na empresa DEMF.</span><span class="sxs-lookup"><span data-stu-id="7de87-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="7de87-106">Para concluir estas etapas, primeiro você deve concluir as etapas no procedimento "ER Usar arquivos de gerenciamento de documentos em saídas de formato (Parte 4: executar formato)".</span><span class="sxs-lookup"><span data-stu-id="7de87-106">To complete these steps, you must first complete the steps in the “ER Use Document Management files in format outputs (Part 4: Run format)” procedure.</span></span>

<span data-ttu-id="7de87-107">Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="7de87-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="modify-the-format-to-populate-attachments-into-generating-messages-in-binary-format"></a><span data-ttu-id="7de87-108">Modificar o formato para popular anexos para a geração de mensagens no formato binário</span><span class="sxs-lookup"><span data-stu-id="7de87-108">Modify the format to populate attachments into generating messages in binary format</span></span>
1. <span data-ttu-id="7de87-109">Vá para Administração da organização > Relatório eletrônico > Configurações.</span><span class="sxs-lookup"><span data-stu-id="7de87-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="7de87-110">Na árvore, expanda 'Modelo de fatura de cliente'.</span><span class="sxs-lookup"><span data-stu-id="7de87-110">In the tree, expand 'Customer invoice model'.</span></span>
3. <span data-ttu-id="7de87-111">Na árvore, expanda 'Modelo de fatura de cliente\Modelo de fatura de cliente (personalizada)'.</span><span class="sxs-lookup"><span data-stu-id="7de87-111">In the tree, expand 'Customer invoice model\Customer invoice model (custom)'.</span></span>
4. <span data-ttu-id="7de87-112">Na árvore, selecione 'Modelo de fatura de cliente\Modelo de fatura de cliente (personalizada)\Mensagem de exemplo da fatura eletrônica'.</span><span class="sxs-lookup"><span data-stu-id="7de87-112">In the tree, select 'Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message'.</span></span>
5. <span data-ttu-id="7de87-113">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="7de87-113">Click Designer.</span></span>
    * <span data-ttu-id="7de87-114">Você preencherá a mensagem da fatura na saída gerada como um arquivo XML usando a codificação UNICODE.</span><span class="sxs-lookup"><span data-stu-id="7de87-114">You will populate the invoice message in the generating output as an XML file using UNICODE encoding.</span></span>  
6. <span data-ttu-id="7de87-115">Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="7de87-115">Click Add root to open the drop dialog.</span></span>
7. <span data-ttu-id="7de87-116">Na árvore, selecione 'Comum\Arquivo'.</span><span class="sxs-lookup"><span data-stu-id="7de87-116">In the tree, select 'Common\File'.</span></span>
8. <span data-ttu-id="7de87-117">No campo Nome, digite 'Mensagem Xml'.</span><span class="sxs-lookup"><span data-stu-id="7de87-117">In the Name field, type 'Xml message'.</span></span>
    * <span data-ttu-id="7de87-118">Mensagem Xml</span><span class="sxs-lookup"><span data-stu-id="7de87-118">Xml message</span></span>  
9. <span data-ttu-id="7de87-119">No campo Codificação, digite 'UTF-8'.</span><span class="sxs-lookup"><span data-stu-id="7de87-119">In the Encoding field, type 'UTF-8'.</span></span>
    * <span data-ttu-id="7de87-120">UTF-8</span><span class="sxs-lookup"><span data-stu-id="7de87-120">UTF-8</span></span>  
10. <span data-ttu-id="7de87-121">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="7de87-121">Click OK.</span></span>
    * <span data-ttu-id="7de87-122">Configurar as saídas geradas como arquivo compactado.</span><span class="sxs-lookup"><span data-stu-id="7de87-122">Configure the generating output as a zipped file.</span></span>  
11. <span data-ttu-id="7de87-123">Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="7de87-123">Click Add root to open the drop dialog.</span></span>
12. <span data-ttu-id="7de87-124">Na árvore, selecione 'Comum\Pasta'.</span><span class="sxs-lookup"><span data-stu-id="7de87-124">In the tree, select 'Common\Folder'.</span></span>
13. <span data-ttu-id="7de87-125">No campo Nome, digite 'Saída Zip'.</span><span class="sxs-lookup"><span data-stu-id="7de87-125">In the Name field, type 'Zip output'.</span></span>
    * <span data-ttu-id="7de87-126">Saída Zip</span><span class="sxs-lookup"><span data-stu-id="7de87-126">Zip output</span></span>  
14. <span data-ttu-id="7de87-127">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="7de87-127">Click OK.</span></span>
15. <span data-ttu-id="7de87-128">Na árvore, selecione 'Saída Zip'.</span><span class="sxs-lookup"><span data-stu-id="7de87-128">In the tree, select 'Zip output'.</span></span>
    * <span data-ttu-id="7de87-129">Adicionar anexos ao arquivo compactado gerado como arquivos com extensões e nomes originais.</span><span class="sxs-lookup"><span data-stu-id="7de87-129">Add attachments to the generating zipped file as files with original names and extensions.</span></span>  
16. <span data-ttu-id="7de87-130">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="7de87-130">Click Add to open the drop dialog.</span></span>
17. <span data-ttu-id="7de87-131">Na árvore, selecione 'Comum\Arquivo'.</span><span class="sxs-lookup"><span data-stu-id="7de87-131">In the tree, select 'Common\File'.</span></span>
18. <span data-ttu-id="7de87-132">No campo Nome, digite 'Arquivo anexo'.</span><span class="sxs-lookup"><span data-stu-id="7de87-132">In the Name field, type 'Attached file'.</span></span>
    * <span data-ttu-id="7de87-133">Arquivo anexo</span><span class="sxs-lookup"><span data-stu-id="7de87-133">Attached file</span></span>  
19. <span data-ttu-id="7de87-134">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="7de87-134">Click OK.</span></span>
20. <span data-ttu-id="7de87-135">Na árvore, selecione 'Saída Zip\Arquivo anexo'.</span><span class="sxs-lookup"><span data-stu-id="7de87-135">In the tree, select 'Zip output\Attached file'.</span></span>
21. <span data-ttu-id="7de87-136">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="7de87-136">Click Add to open the drop dialog.</span></span>
22. <span data-ttu-id="7de87-137">Na árvore, selecione 'Texto\Base64'.</span><span class="sxs-lookup"><span data-stu-id="7de87-137">In the tree, select 'Text\Base64'.</span></span>
23. <span data-ttu-id="7de87-138">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="7de87-138">Click OK.</span></span>

## <a name="map-new-format-elements-to-data-model"></a><span data-ttu-id="7de87-139">Mapear novos elementos de formato no modelo de dados</span><span class="sxs-lookup"><span data-stu-id="7de87-139">Map new format elements to data model</span></span>
1. <span data-ttu-id="7de87-140">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="7de87-140">Click the Mapping tab.</span></span>
2. <span data-ttu-id="7de87-141">Na árvore, expanda 'modelo'.</span><span class="sxs-lookup"><span data-stu-id="7de87-141">In the tree, expand 'model'.</span></span>
3. <span data-ttu-id="7de87-142">Na árvore, expanda 'modelo\Anexos da fatura'.</span><span class="sxs-lookup"><span data-stu-id="7de87-142">In the tree, expand 'model\Invoice attachments'.</span></span>
4. <span data-ttu-id="7de87-143">Na árvore, selecione 'Saída Zip\Arquivo anexo\Base64'.</span><span class="sxs-lookup"><span data-stu-id="7de87-143">In the tree, select 'Zip output\Attached file\Base64'.</span></span>
5. <span data-ttu-id="7de87-144">Na árvore, selecione 'modelo\Anexos da fatura\Conteúdo do arquivo'.</span><span class="sxs-lookup"><span data-stu-id="7de87-144">In the tree, select 'model\Invoice attachments\File content'.</span></span>
6. <span data-ttu-id="7de87-145">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="7de87-145">Click Bind.</span></span>
7. <span data-ttu-id="7de87-146">Na árvore, selecione 'Saída Zip\Arquivo anexo'.</span><span class="sxs-lookup"><span data-stu-id="7de87-146">In the tree, select 'Zip output\Attached file'.</span></span>
8. <span data-ttu-id="7de87-147">Clique em Editar nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="7de87-147">Click Edit filename.</span></span>
9. <span data-ttu-id="7de87-148">Na árvore, expanda 'modelo'.</span><span class="sxs-lookup"><span data-stu-id="7de87-148">In the tree, expand 'model'.</span></span>
10. <span data-ttu-id="7de87-149">Na árvore, expanda 'modelo\Anexos da fatura'.</span><span class="sxs-lookup"><span data-stu-id="7de87-149">In the tree, expand 'model\Invoice attachments'.</span></span>
11. <span data-ttu-id="7de87-150">Na árvore, selecione 'modelo\Anexos da fatura\Nome do arquivo'.</span><span class="sxs-lookup"><span data-stu-id="7de87-150">In the tree, select 'model\Invoice attachments\File name'.</span></span>
12. <span data-ttu-id="7de87-151">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="7de87-151">Click Add data source.</span></span>
13. <span data-ttu-id="7de87-152">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="7de87-152">Click Save.</span></span>
14. <span data-ttu-id="7de87-153">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7de87-153">Close the page.</span></span>
15. <span data-ttu-id="7de87-154">Na árvore, selecione 'modelo\Anexos da fatura'.</span><span class="sxs-lookup"><span data-stu-id="7de87-154">In the tree, select 'model\Invoice attachments'.</span></span>
16. <span data-ttu-id="7de87-155">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="7de87-155">Click Bind.</span></span>
17. <span data-ttu-id="7de87-156">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="7de87-156">Click Save.</span></span>
18. <span data-ttu-id="7de87-157">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7de87-157">Close the page.</span></span>

## <a name="run-the-designed-report-for-the-selected-invoice"></a><span data-ttu-id="7de87-158">Executar relatório criado para a fatura selecionada</span><span class="sxs-lookup"><span data-stu-id="7de87-158">Run the designed report for the selected invoice</span></span>
1. <span data-ttu-id="7de87-159">Clique em Executar.</span><span class="sxs-lookup"><span data-stu-id="7de87-159">Click Run.</span></span>
2. <span data-ttu-id="7de87-160">Expanda os Registros para incluir a seção ().</span><span class="sxs-lookup"><span data-stu-id="7de87-160">Expand the Records to include () section.</span></span>
3. <span data-ttu-id="7de87-161">Clique em Filtro.</span><span class="sxs-lookup"><span data-stu-id="7de87-161">Click Filter.</span></span>
4. <span data-ttu-id="7de87-162">Selecione a linha do diário de faturas do cliente e o campo Ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="7de87-162">Select the row of the Customer invoice journal and the Sales order field.</span></span>
5. <span data-ttu-id="7de87-163">No campo Critérios, no campo do critério "Ordem de venda" digite o número de ordem 000148.</span><span class="sxs-lookup"><span data-stu-id="7de87-163">In the Criteria field, In the criteria “Sales order” field, type the order number 000148.</span></span>
    * <span data-ttu-id="7de87-164">000148</span><span class="sxs-lookup"><span data-stu-id="7de87-164">000148</span></span>  
6. <span data-ttu-id="7de87-165">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="7de87-165">Click OK.</span></span>
7. <span data-ttu-id="7de87-166">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="7de87-166">Click OK.</span></span>
    * <span data-ttu-id="7de87-167">Revise a saída gerada.</span><span class="sxs-lookup"><span data-stu-id="7de87-167">Review the generated output.</span></span> <span data-ttu-id="7de87-168">Observe que, além da mensagem da fatura em formato XML, um único arquivo foi criado para cada anexo.</span><span class="sxs-lookup"><span data-stu-id="7de87-168">Note,that in addition to the invoice message in XML format, a single file has been created for each attachment.</span></span> <span data-ttu-id="7de87-169">Os arquivos anexos são preenchidos com as saídas compactadas em formato binário.</span><span class="sxs-lookup"><span data-stu-id="7de87-169">The attachment files are populated with the zipped output in binary format.</span></span>  

---
title: Criar formatos para usar arquivos de gerenciamento de documentos em saídas de ER
description: As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico para usar arquivos de gerenciamento de documentos na saída do ER.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1815a0004eee6734b3c7d2c2f9e75ce5fe16af1c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1544739"
---
# <a name="create-formats-to-use-document-management-files-in-er-output"></a><span data-ttu-id="6e132-103">Criar formatos para usar arquivos de gerenciamento de documentos em saídas de ER</span><span class="sxs-lookup"><span data-stu-id="6e132-103">Create formats to use Document Management files in ER output</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6e132-104">As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para usar arquivos de gerenciamento de documentos (anexos) na saída do ER.</span><span class="sxs-lookup"><span data-stu-id="6e132-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="6e132-105">Essas etapas podem ser executadas em qualquer empresa.</span><span class="sxs-lookup"><span data-stu-id="6e132-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="6e132-106">Para concluir estas etapas, primeiramente você deve concluir as etapas no procedimento "ER Usar arquivos de gerenciamento de documentos em formatos de saída (Parte 2: estender modelo de dados)".</span><span class="sxs-lookup"><span data-stu-id="6e132-106">To complete these steps, you must first complete the steps in the “ER Use Document Management files in format outputs (Part 2: Extend data model” procedure.</span></span>

<span data-ttu-id="6e132-107">Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="6e132-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-format-to-process-invoices"></a><span data-ttu-id="6e132-108">Criar um formato para processar faturas</span><span class="sxs-lookup"><span data-stu-id="6e132-108">Create a format to process invoices</span></span>
1. <span data-ttu-id="6e132-109">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="6e132-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="6e132-110">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="6e132-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="6e132-111">Na árvore, expanda 'Modelo de fatura de cliente'.</span><span class="sxs-lookup"><span data-stu-id="6e132-111">In the tree, expand 'Customer invoice model'.</span></span>
4. <span data-ttu-id="6e132-112">Na árvore, selecione 'Modelo de fatura de cliente\Modelo de fatura de cliente (personalizada)'.</span><span class="sxs-lookup"><span data-stu-id="6e132-112">In the tree, select 'Customer invoice model\Customer invoice model (custom)'.</span></span>
    * <span data-ttu-id="6e132-113">Você criará um formato para gerar mensagens eletrônicas com informações sobre todos os arquivos que foram anexados a uma ordem de venda que esteja relacionada a um processamento eletrônico de fatura.</span><span class="sxs-lookup"><span data-stu-id="6e132-113">You will create a format to generate electronic messages with information about any files that have been attached to a sales order that is related to an electronically processing invoice.</span></span>  
5. <span data-ttu-id="6e132-114">Clique em Criar configuração para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="6e132-114">Click Create configuration to open the drop dialog.</span></span>
6. <span data-ttu-id="6e132-115">No campo Novo, insira 'Formato baseado no modelo de dados Modelo de fatura de cliente (personalizada)'.</span><span class="sxs-lookup"><span data-stu-id="6e132-115">In the New field, enter 'Format based on data model Customer invoice model (custom)'.</span></span>
7. <span data-ttu-id="6e132-116">No campo Nome, digite 'Mensagem de exemplo da fatura eletrônica'.</span><span class="sxs-lookup"><span data-stu-id="6e132-116">In the Name field, type 'Electronic invoice sample message'.</span></span>
    * <span data-ttu-id="6e132-117">Mensagem de exemplo da fatura eletrônica</span><span class="sxs-lookup"><span data-stu-id="6e132-117">Electronic invoice sample message</span></span>  
8. <span data-ttu-id="6e132-118">No campo Definição do modelo de dados, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="6e132-118">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="6e132-119">InvoiceCustomer</span><span class="sxs-lookup"><span data-stu-id="6e132-119">InvoiceCustomer</span></span>  
9. <span data-ttu-id="6e132-120">Clique em Criar configuração.</span><span class="sxs-lookup"><span data-stu-id="6e132-120">Click Create configuration.</span></span>

## <a name="design-a-format-to-populate-attachments-into-generating-a-message-in-mime-format"></a><span data-ttu-id="6e132-121">Criar um formato para popular anexos para a geração de uma mensagem no formato MIME</span><span class="sxs-lookup"><span data-stu-id="6e132-121">Design a format to populate attachments into generating a message in MIME format</span></span>
1. <span data-ttu-id="6e132-122">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="6e132-122">Click Designer.</span></span>
2. <span data-ttu-id="6e132-123">Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="6e132-123">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="6e132-124">Na árvore, selecione 'XML\Elemento'.</span><span class="sxs-lookup"><span data-stu-id="6e132-124">In the tree, select 'XML\Element'.</span></span>
4. <span data-ttu-id="6e132-125">No campo Nome, digite 'Fatura'.</span><span class="sxs-lookup"><span data-stu-id="6e132-125">In the Name field, type 'Invoice'.</span></span>
    * <span data-ttu-id="6e132-126">Fatura</span><span class="sxs-lookup"><span data-stu-id="6e132-126">Invoice</span></span>  
5. <span data-ttu-id="6e132-127">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6e132-127">Click OK.</span></span>
6. <span data-ttu-id="6e132-128">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="6e132-128">Click Add to open the drop dialog.</span></span>
7. <span data-ttu-id="6e132-129">Na árvore, selecione 'XML\Atributo'.</span><span class="sxs-lookup"><span data-stu-id="6e132-129">In the tree, select 'XML\Attribute'.</span></span>
8. <span data-ttu-id="6e132-130">No campo Nome, digite 'SalesOrder'.</span><span class="sxs-lookup"><span data-stu-id="6e132-130">In the Name field, type 'SalesOrder'.</span></span>
    * <span data-ttu-id="6e132-131">SalesOrder</span><span class="sxs-lookup"><span data-stu-id="6e132-131">SalesOrder</span></span>  
9. <span data-ttu-id="6e132-132">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6e132-132">Click OK.</span></span>
10. <span data-ttu-id="6e132-133">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="6e132-133">Click Add Attribute.</span></span>
11. <span data-ttu-id="6e132-134">No campo Nome, digite 'InvoiceNumber'.</span><span class="sxs-lookup"><span data-stu-id="6e132-134">In the Name field, type 'InvoiceNumber'.</span></span>
    * <span data-ttu-id="6e132-135">InvoiceNumber</span><span class="sxs-lookup"><span data-stu-id="6e132-135">InvoiceNumber</span></span>  
12. <span data-ttu-id="6e132-136">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6e132-136">Click OK.</span></span>
13. <span data-ttu-id="6e132-137">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="6e132-137">Click Add Attribute.</span></span>
14. <span data-ttu-id="6e132-138">No campo Nome, digite 'InvoiceAmount'.</span><span class="sxs-lookup"><span data-stu-id="6e132-138">In the Name field, type 'InvoiceAmount'.</span></span>
    * <span data-ttu-id="6e132-139">InvoiceAmount</span><span class="sxs-lookup"><span data-stu-id="6e132-139">InvoiceAmount</span></span>  
15. <span data-ttu-id="6e132-140">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6e132-140">Click OK.</span></span>
16. <span data-ttu-id="6e132-141">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="6e132-141">Click Add to open the drop dialog.</span></span>
17. <span data-ttu-id="6e132-142">Na árvore, selecione 'XML\Elemento'.</span><span class="sxs-lookup"><span data-stu-id="6e132-142">In the tree, select 'XML\Element'.</span></span>
18. <span data-ttu-id="6e132-143">No campo Nome, digite 'EnclosedDocs'.</span><span class="sxs-lookup"><span data-stu-id="6e132-143">In the Name field, type 'EnclosedDocs'.</span></span>
    * <span data-ttu-id="6e132-144">EnclosedDocs</span><span class="sxs-lookup"><span data-stu-id="6e132-144">EnclosedDocs</span></span>  
19. <span data-ttu-id="6e132-145">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6e132-145">Click OK.</span></span>
20. <span data-ttu-id="6e132-146">Na árvore, selecione 'Fatura\EnclosedDocs'.</span><span class="sxs-lookup"><span data-stu-id="6e132-146">In the tree, select 'Invoice\EnclosedDocs'.</span></span>
21. <span data-ttu-id="6e132-147">Clique em Adicionar elemento.</span><span class="sxs-lookup"><span data-stu-id="6e132-147">Click Add Element.</span></span>
22. <span data-ttu-id="6e132-148">No campo Nome, digite 'Documento'.</span><span class="sxs-lookup"><span data-stu-id="6e132-148">In the Name field, type 'Document'.</span></span>
    * <span data-ttu-id="6e132-149">Documento</span><span class="sxs-lookup"><span data-stu-id="6e132-149">Document</span></span>  
23. <span data-ttu-id="6e132-150">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6e132-150">Click OK.</span></span>
24. <span data-ttu-id="6e132-151">Na árvore, selecione 'Fatura\EnclosedDocs\Documento'.</span><span class="sxs-lookup"><span data-stu-id="6e132-151">In the tree, select 'Invoice\EnclosedDocs\Document'.</span></span>
25. <span data-ttu-id="6e132-152">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="6e132-152">Click Add to open the drop dialog.</span></span>
26. <span data-ttu-id="6e132-153">Na árvore, selecione 'XML\Atributo'.</span><span class="sxs-lookup"><span data-stu-id="6e132-153">In the tree, select 'XML\Attribute'.</span></span>
27. <span data-ttu-id="6e132-154">No campo Nome, digite 'FileName'.</span><span class="sxs-lookup"><span data-stu-id="6e132-154">In the Name field, type 'FileName'.</span></span>
    * <span data-ttu-id="6e132-155">FileName</span><span class="sxs-lookup"><span data-stu-id="6e132-155">FileName</span></span>  
28. <span data-ttu-id="6e132-156">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6e132-156">Click OK.</span></span>
29. <span data-ttu-id="6e132-157">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="6e132-157">Click Add to open the drop dialog.</span></span>
30. <span data-ttu-id="6e132-158">Na árvore, selecione 'XML\Elemento'.</span><span class="sxs-lookup"><span data-stu-id="6e132-158">In the tree, select 'XML\Element'.</span></span>
31. <span data-ttu-id="6e132-159">No campo Nome, digite 'FileContent'.</span><span class="sxs-lookup"><span data-stu-id="6e132-159">In the Name field, type 'FileContent'.</span></span>
    * <span data-ttu-id="6e132-160">FileContent</span><span class="sxs-lookup"><span data-stu-id="6e132-160">FileContent</span></span>  
32. <span data-ttu-id="6e132-161">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6e132-161">Click OK.</span></span>
33. <span data-ttu-id="6e132-162">Na árvore, selecione 'Fatura\EnclosedDocs\Documento\FileContent'.</span><span class="sxs-lookup"><span data-stu-id="6e132-162">In the tree, select 'Invoice\EnclosedDocs\Document\FileContent'.</span></span>
34. <span data-ttu-id="6e132-163">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="6e132-163">Click Add to open the drop dialog.</span></span>
35. <span data-ttu-id="6e132-164">Na árvore, selecione 'Texto\Base64'.</span><span class="sxs-lookup"><span data-stu-id="6e132-164">In the tree, select 'Text\Base64'.</span></span>
36. <span data-ttu-id="6e132-165">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6e132-165">Click OK.</span></span>

## <a name="map-format-elements-to-data-model-as-data-source"></a><span data-ttu-id="6e132-166">Mapear elementos de formato para o modelo de dados como fonte de dados</span><span class="sxs-lookup"><span data-stu-id="6e132-166">Map format elements to data model as data source</span></span>
1. <span data-ttu-id="6e132-167">Na árvore, selecione 'Fatura\SalesOrder'.</span><span class="sxs-lookup"><span data-stu-id="6e132-167">In the tree, select 'Invoice\SalesOrder'.</span></span>
2. <span data-ttu-id="6e132-168">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="6e132-168">Click the Mapping tab.</span></span>
3. <span data-ttu-id="6e132-169">Na árvore, expanda 'modelo'.</span><span class="sxs-lookup"><span data-stu-id="6e132-169">In the tree, expand 'model'.</span></span>
4. <span data-ttu-id="6e132-170">Na árvore, selecione 'modelo\número da ordem de venda(SalesId)'.</span><span class="sxs-lookup"><span data-stu-id="6e132-170">In the tree, select 'model\Sales order number(SalesId)'.</span></span>
5. <span data-ttu-id="6e132-171">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="6e132-171">Click Bind.</span></span>
6. <span data-ttu-id="6e132-172">Na árvore, selecione 'Fatura\InvoiceNumber'.</span><span class="sxs-lookup"><span data-stu-id="6e132-172">In the tree, select 'Invoice\InvoiceNumber'.</span></span>
7. <span data-ttu-id="6e132-173">Na árvore, expanda 'modelo\Fatura base(InvoiceBase)'.</span><span class="sxs-lookup"><span data-stu-id="6e132-173">In the tree, expand 'model\Base invoice(InvoiceBase)'.</span></span>
8. <span data-ttu-id="6e132-174">Na árvore, selecione 'modelo\Fatura base(InvoiceBase)\Número da fatura(ID)'.</span><span class="sxs-lookup"><span data-stu-id="6e132-174">In the tree, select 'model\Base invoice(InvoiceBase)\Invoice number(Id)'.</span></span>
9. <span data-ttu-id="6e132-175">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="6e132-175">Click Bind.</span></span>
10. <span data-ttu-id="6e132-176">Na árvore, selecione 'Fatura\InvoiceAmount'.</span><span class="sxs-lookup"><span data-stu-id="6e132-176">In the tree, select 'Invoice\InvoiceAmount'.</span></span>
11. <span data-ttu-id="6e132-177">Na árvore, selecione 'modelo\Fatura base(InvoiceBase)\Valor da fatura(Valor)'.</span><span class="sxs-lookup"><span data-stu-id="6e132-177">In the tree, select 'model\Base invoice(InvoiceBase)\Invoice amount(Amount)'.</span></span>
12. <span data-ttu-id="6e132-178">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="6e132-178">Click Bind.</span></span>
13. <span data-ttu-id="6e132-179">Na árvore, expanda 'modelo\Anexos da fatura'.</span><span class="sxs-lookup"><span data-stu-id="6e132-179">In the tree, expand 'model\Invoice attachments'.</span></span>
14. <span data-ttu-id="6e132-180">Na árvore, selecione 'modelo\Anexos da fatura\Conteúdo do arquivo'.</span><span class="sxs-lookup"><span data-stu-id="6e132-180">In the tree, select 'model\Invoice attachments\File content'.</span></span>
15. <span data-ttu-id="6e132-181">Na árvore, selecione 'Fatura\EnclosedDocs\Documento\FileContent\Base64'.</span><span class="sxs-lookup"><span data-stu-id="6e132-181">In the tree, select 'Invoice\EnclosedDocs\Document\FileContent\Base64'.</span></span>
16. <span data-ttu-id="6e132-182">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="6e132-182">Click Bind.</span></span>
17. <span data-ttu-id="6e132-183">Na árvore, selecione 'modelo\Anexos da fatura\Nome do arquivo'.</span><span class="sxs-lookup"><span data-stu-id="6e132-183">In the tree, select 'model\Invoice attachments\File name'.</span></span>
18. <span data-ttu-id="6e132-184">Na árvore, selecione 'Fatura\EnclosedDocs\Documento\FileName'.</span><span class="sxs-lookup"><span data-stu-id="6e132-184">In the tree, select 'Invoice\EnclosedDocs\Document\FileName'.</span></span>
19. <span data-ttu-id="6e132-185">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="6e132-185">Click Bind.</span></span>
20. <span data-ttu-id="6e132-186">Na árvore, selecione 'modelo\Anexos da fatura'.</span><span class="sxs-lookup"><span data-stu-id="6e132-186">In the tree, select 'model\Invoice attachments'.</span></span>
21. <span data-ttu-id="6e132-187">Na árvore, selecione 'Fatura\EnclosedDocs\Documento'.</span><span class="sxs-lookup"><span data-stu-id="6e132-187">In the tree, select 'Invoice\EnclosedDocs\Document'.</span></span>
22. <span data-ttu-id="6e132-188">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="6e132-188">Click Bind.</span></span>
23. <span data-ttu-id="6e132-189">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="6e132-189">Click Save.</span></span>
24. <span data-ttu-id="6e132-190">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="6e132-190">Close the page.</span></span>


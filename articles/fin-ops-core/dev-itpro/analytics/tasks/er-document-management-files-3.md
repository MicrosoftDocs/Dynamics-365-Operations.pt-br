---
title: O ER usar arquivos de gerenciamento de documentos em formato de saída (parte 3 - criar formato)
description: Este tópico descreve como configurar um formato de relatório eletrônico para usar arquivos de gerenciamento de documentos na saída de ER. (Parte 3)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1ec1ebc15cd980734aebec63d6758404868c1e36
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559740"
---
# <a name="er-use-document-management-files-in-format-outputs-part-3---create-format"></a><span data-ttu-id="1c843-104">O ER usar arquivos de gerenciamento de documentos em formato de saída (parte 3 - criar formato)</span><span class="sxs-lookup"><span data-stu-id="1c843-104">ER Use Document Management files in format outputs (Part 3 - Create format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1c843-105">As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para usar arquivos de gerenciamento de documentos (anexos) na saída do ER.</span><span class="sxs-lookup"><span data-stu-id="1c843-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="1c843-106">Essas etapas podem ser executadas em qualquer empresa.</span><span class="sxs-lookup"><span data-stu-id="1c843-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="1c843-107">Para concluir estas etapas, primeiramente você deve concluir as etapas no procedimento "ER Usar arquivos de gerenciamento de documentos em formatos de saída (Parte 2: estender modelo de dados)".</span><span class="sxs-lookup"><span data-stu-id="1c843-107">To complete these steps, you must first complete the steps in the "ER Use Document Management files in format outputs (Part 2: Extend data model" procedure.</span></span>

<span data-ttu-id="1c843-108">Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="1c843-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-format-to-process-invoices"></a><span data-ttu-id="1c843-109">Criar um formato para processar faturas</span><span class="sxs-lookup"><span data-stu-id="1c843-109">Create a format to process invoices</span></span>
1. <span data-ttu-id="1c843-110">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="1c843-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="1c843-111">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="1c843-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="1c843-112">Na árvore, expanda 'Modelo de fatura de cliente'.</span><span class="sxs-lookup"><span data-stu-id="1c843-112">In the tree, expand 'Customer invoice model'.</span></span>
4. <span data-ttu-id="1c843-113">Na árvore, selecione 'Modelo de fatura de cliente\Modelo de fatura de cliente (personalizada)'.</span><span class="sxs-lookup"><span data-stu-id="1c843-113">In the tree, select 'Customer invoice model\Customer invoice model (custom)'.</span></span>
    * <span data-ttu-id="1c843-114">Você criará um formato para gerar mensagens eletrônicas com informações sobre todos os arquivos que foram anexados a uma ordem de venda que esteja relacionada a um processamento eletrônico de fatura.</span><span class="sxs-lookup"><span data-stu-id="1c843-114">You will create a format to generate electronic messages with information about any files that have been attached to a sales order that is related to an electronically processing invoice.</span></span>  
5. <span data-ttu-id="1c843-115">Clique em Criar configuração para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1c843-115">Click Create configuration to open the drop dialog.</span></span>
6. <span data-ttu-id="1c843-116">No campo Novo, insira 'Formato baseado no modelo de dados Modelo de fatura de cliente (personalizada)'.</span><span class="sxs-lookup"><span data-stu-id="1c843-116">In the New field, enter 'Format based on data model Customer invoice model (custom)'.</span></span>
7. <span data-ttu-id="1c843-117">No campo Nome, digite 'Mensagem de exemplo da fatura eletrônica'.</span><span class="sxs-lookup"><span data-stu-id="1c843-117">In the Name field, type 'Electronic invoice sample message'.</span></span>
    * <span data-ttu-id="1c843-118">Mensagem de exemplo da fatura eletrônica</span><span class="sxs-lookup"><span data-stu-id="1c843-118">Electronic invoice sample message</span></span>  
8. <span data-ttu-id="1c843-119">No campo Definição do modelo de dados, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="1c843-119">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="1c843-120">InvoiceCustomer</span><span class="sxs-lookup"><span data-stu-id="1c843-120">InvoiceCustomer</span></span>  
9. <span data-ttu-id="1c843-121">Clique em Criar configuração.</span><span class="sxs-lookup"><span data-stu-id="1c843-121">Click Create configuration.</span></span>

## <a name="design-a-format-to-populate-attachments-into-generating-a-message-in-mime-format"></a><span data-ttu-id="1c843-122">Criar um formato para popular anexos para a geração de uma mensagem no formato MIME</span><span class="sxs-lookup"><span data-stu-id="1c843-122">Design a format to populate attachments into generating a message in MIME format</span></span>
1. <span data-ttu-id="1c843-123">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="1c843-123">Click Designer.</span></span>
2. <span data-ttu-id="1c843-124">Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1c843-124">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="1c843-125">Na árvore, selecione 'XML\Elemento'.</span><span class="sxs-lookup"><span data-stu-id="1c843-125">In the tree, select 'XML\Element'.</span></span>
4. <span data-ttu-id="1c843-126">No campo Nome, digite 'Fatura'.</span><span class="sxs-lookup"><span data-stu-id="1c843-126">In the Name field, type 'Invoice'.</span></span>
    * <span data-ttu-id="1c843-127">Fatura</span><span class="sxs-lookup"><span data-stu-id="1c843-127">Invoice</span></span>  
5. <span data-ttu-id="1c843-128">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="1c843-128">Click OK.</span></span>
6. <span data-ttu-id="1c843-129">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1c843-129">Click Add to open the drop dialog.</span></span>
7. <span data-ttu-id="1c843-130">Na árvore, selecione 'XML\Atributo'.</span><span class="sxs-lookup"><span data-stu-id="1c843-130">In the tree, select 'XML\Attribute'.</span></span>
8. <span data-ttu-id="1c843-131">No campo Nome, digite 'SalesOrder'.</span><span class="sxs-lookup"><span data-stu-id="1c843-131">In the Name field, type 'SalesOrder'.</span></span>
    * <span data-ttu-id="1c843-132">SalesOrder</span><span class="sxs-lookup"><span data-stu-id="1c843-132">SalesOrder</span></span>  
9. <span data-ttu-id="1c843-133">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="1c843-133">Click OK.</span></span>
10. <span data-ttu-id="1c843-134">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="1c843-134">Click Add Attribute.</span></span>
11. <span data-ttu-id="1c843-135">No campo Nome, digite 'InvoiceNumber'.</span><span class="sxs-lookup"><span data-stu-id="1c843-135">In the Name field, type 'InvoiceNumber'.</span></span>
    * <span data-ttu-id="1c843-136">InvoiceNumber</span><span class="sxs-lookup"><span data-stu-id="1c843-136">InvoiceNumber</span></span>  
12. <span data-ttu-id="1c843-137">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="1c843-137">Click OK.</span></span>
13. <span data-ttu-id="1c843-138">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="1c843-138">Click Add Attribute.</span></span>
14. <span data-ttu-id="1c843-139">No campo Nome, digite 'InvoiceAmount'.</span><span class="sxs-lookup"><span data-stu-id="1c843-139">In the Name field, type 'InvoiceAmount'.</span></span>
    * <span data-ttu-id="1c843-140">InvoiceAmount</span><span class="sxs-lookup"><span data-stu-id="1c843-140">InvoiceAmount</span></span>  
15. <span data-ttu-id="1c843-141">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="1c843-141">Click OK.</span></span>
16. <span data-ttu-id="1c843-142">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1c843-142">Click Add to open the drop dialog.</span></span>
17. <span data-ttu-id="1c843-143">Na árvore, selecione 'XML\Elemento'.</span><span class="sxs-lookup"><span data-stu-id="1c843-143">In the tree, select 'XML\Element'.</span></span>
18. <span data-ttu-id="1c843-144">No campo Nome, digite 'EnclosedDocs'.</span><span class="sxs-lookup"><span data-stu-id="1c843-144">In the Name field, type 'EnclosedDocs'.</span></span>
    * <span data-ttu-id="1c843-145">EnclosedDocs</span><span class="sxs-lookup"><span data-stu-id="1c843-145">EnclosedDocs</span></span>  
19. <span data-ttu-id="1c843-146">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="1c843-146">Click OK.</span></span>
20. <span data-ttu-id="1c843-147">Na árvore, selecione 'Fatura\EnclosedDocs'.</span><span class="sxs-lookup"><span data-stu-id="1c843-147">In the tree, select 'Invoice\EnclosedDocs'.</span></span>
21. <span data-ttu-id="1c843-148">Clique em Adicionar elemento.</span><span class="sxs-lookup"><span data-stu-id="1c843-148">Click Add Element.</span></span>
22. <span data-ttu-id="1c843-149">No campo Nome, digite 'Documento'.</span><span class="sxs-lookup"><span data-stu-id="1c843-149">In the Name field, type 'Document'.</span></span>
    * <span data-ttu-id="1c843-150">Documento</span><span class="sxs-lookup"><span data-stu-id="1c843-150">Document</span></span>  
23. <span data-ttu-id="1c843-151">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="1c843-151">Click OK.</span></span>
24. <span data-ttu-id="1c843-152">Na árvore, selecione 'Fatura\EnclosedDocs\Documento'.</span><span class="sxs-lookup"><span data-stu-id="1c843-152">In the tree, select 'Invoice\EnclosedDocs\Document'.</span></span>
25. <span data-ttu-id="1c843-153">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1c843-153">Click Add to open the drop dialog.</span></span>
26. <span data-ttu-id="1c843-154">Na árvore, selecione 'XML\Atributo'.</span><span class="sxs-lookup"><span data-stu-id="1c843-154">In the tree, select 'XML\Attribute'.</span></span>
27. <span data-ttu-id="1c843-155">No campo Nome, digite 'FileName'.</span><span class="sxs-lookup"><span data-stu-id="1c843-155">In the Name field, type 'FileName'.</span></span>
    * <span data-ttu-id="1c843-156">FileName</span><span class="sxs-lookup"><span data-stu-id="1c843-156">FileName</span></span>  
28. <span data-ttu-id="1c843-157">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="1c843-157">Click OK.</span></span>
29. <span data-ttu-id="1c843-158">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1c843-158">Click Add to open the drop dialog.</span></span>
30. <span data-ttu-id="1c843-159">Na árvore, selecione 'XML\Elemento'.</span><span class="sxs-lookup"><span data-stu-id="1c843-159">In the tree, select 'XML\Element'.</span></span>
31. <span data-ttu-id="1c843-160">No campo Nome, digite 'FileContent'.</span><span class="sxs-lookup"><span data-stu-id="1c843-160">In the Name field, type 'FileContent'.</span></span>
    * <span data-ttu-id="1c843-161">FileContent</span><span class="sxs-lookup"><span data-stu-id="1c843-161">FileContent</span></span>  
32. <span data-ttu-id="1c843-162">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="1c843-162">Click OK.</span></span>
33. <span data-ttu-id="1c843-163">Na árvore, selecione 'Fatura\EnclosedDocs\Documento\FileContent'.</span><span class="sxs-lookup"><span data-stu-id="1c843-163">In the tree, select 'Invoice\EnclosedDocs\Document\FileContent'.</span></span>
34. <span data-ttu-id="1c843-164">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1c843-164">Click Add to open the drop dialog.</span></span>
35. <span data-ttu-id="1c843-165">Na árvore, selecione 'Texto\Base64'.</span><span class="sxs-lookup"><span data-stu-id="1c843-165">In the tree, select 'Text\Base64'.</span></span>
36. <span data-ttu-id="1c843-166">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="1c843-166">Click OK.</span></span>

## <a name="map-format-elements-to-data-model-as-data-source"></a><span data-ttu-id="1c843-167">Mapear elementos de formato para o modelo de dados como fonte de dados</span><span class="sxs-lookup"><span data-stu-id="1c843-167">Map format elements to data model as data source</span></span>
1. <span data-ttu-id="1c843-168">Na árvore, selecione 'Fatura\SalesOrder'.</span><span class="sxs-lookup"><span data-stu-id="1c843-168">In the tree, select 'Invoice\SalesOrder'.</span></span>
2. <span data-ttu-id="1c843-169">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="1c843-169">Click the Mapping tab.</span></span>
3. <span data-ttu-id="1c843-170">Na árvore, expanda 'modelo'.</span><span class="sxs-lookup"><span data-stu-id="1c843-170">In the tree, expand 'model'.</span></span>
4. <span data-ttu-id="1c843-171">Na árvore, selecione 'modelo\número da ordem de venda(SalesId)'.</span><span class="sxs-lookup"><span data-stu-id="1c843-171">In the tree, select 'model\Sales order number(SalesId)'.</span></span>
5. <span data-ttu-id="1c843-172">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="1c843-172">Click Bind.</span></span>
6. <span data-ttu-id="1c843-173">Na árvore, selecione 'Fatura\InvoiceNumber'.</span><span class="sxs-lookup"><span data-stu-id="1c843-173">In the tree, select 'Invoice\InvoiceNumber'.</span></span>
7. <span data-ttu-id="1c843-174">Na árvore, expanda 'modelo\Fatura base(InvoiceBase)'.</span><span class="sxs-lookup"><span data-stu-id="1c843-174">In the tree, expand 'model\Base invoice(InvoiceBase)'.</span></span>
8. <span data-ttu-id="1c843-175">Na árvore, selecione 'modelo\Fatura base(InvoiceBase)\Número da fatura(ID)'.</span><span class="sxs-lookup"><span data-stu-id="1c843-175">In the tree, select 'model\Base invoice(InvoiceBase)\Invoice number(Id)'.</span></span>
9. <span data-ttu-id="1c843-176">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="1c843-176">Click Bind.</span></span>
10. <span data-ttu-id="1c843-177">Na árvore, selecione 'Fatura\InvoiceAmount'.</span><span class="sxs-lookup"><span data-stu-id="1c843-177">In the tree, select 'Invoice\InvoiceAmount'.</span></span>
11. <span data-ttu-id="1c843-178">Na árvore, selecione 'modelo\Fatura base(InvoiceBase)\Valor da fatura(Valor)'.</span><span class="sxs-lookup"><span data-stu-id="1c843-178">In the tree, select 'model\Base invoice(InvoiceBase)\Invoice amount(Amount)'.</span></span>
12. <span data-ttu-id="1c843-179">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="1c843-179">Click Bind.</span></span>
13. <span data-ttu-id="1c843-180">Na árvore, expanda 'modelo\Anexos da fatura'.</span><span class="sxs-lookup"><span data-stu-id="1c843-180">In the tree, expand 'model\Invoice attachments'.</span></span>
14. <span data-ttu-id="1c843-181">Na árvore, selecione 'modelo\Anexos da fatura\Conteúdo do arquivo'.</span><span class="sxs-lookup"><span data-stu-id="1c843-181">In the tree, select 'model\Invoice attachments\File content'.</span></span>
15. <span data-ttu-id="1c843-182">Na árvore, selecione 'Fatura\EnclosedDocs\Documento\FileContent\Base64'.</span><span class="sxs-lookup"><span data-stu-id="1c843-182">In the tree, select 'Invoice\EnclosedDocs\Document\FileContent\Base64'.</span></span>
16. <span data-ttu-id="1c843-183">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="1c843-183">Click Bind.</span></span>
17. <span data-ttu-id="1c843-184">Na árvore, selecione 'modelo\Anexos da fatura\Nome do arquivo'.</span><span class="sxs-lookup"><span data-stu-id="1c843-184">In the tree, select 'model\Invoice attachments\File name'.</span></span>
18. <span data-ttu-id="1c843-185">Na árvore, selecione 'Fatura\EnclosedDocs\Documento\FileName'.</span><span class="sxs-lookup"><span data-stu-id="1c843-185">In the tree, select 'Invoice\EnclosedDocs\Document\FileName'.</span></span>
19. <span data-ttu-id="1c843-186">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="1c843-186">Click Bind.</span></span>
20. <span data-ttu-id="1c843-187">Na árvore, selecione 'modelo\Anexos da fatura'.</span><span class="sxs-lookup"><span data-stu-id="1c843-187">In the tree, select 'model\Invoice attachments'.</span></span>
21. <span data-ttu-id="1c843-188">Na árvore, selecione 'Fatura\EnclosedDocs\Documento'.</span><span class="sxs-lookup"><span data-stu-id="1c843-188">In the tree, select 'Invoice\EnclosedDocs\Document'.</span></span>
22. <span data-ttu-id="1c843-189">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="1c843-189">Click Bind.</span></span>
23. <span data-ttu-id="1c843-190">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="1c843-190">Click Save.</span></span>
24. <span data-ttu-id="1c843-191">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1c843-191">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
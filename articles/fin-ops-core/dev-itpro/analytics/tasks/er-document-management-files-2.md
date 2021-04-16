---
title: ER Usar arquivos de gerenciamento de documentos em formato de saída (Parte 2 - Estender modelo de dados)
description: Este tópico descreve como configurar um formato de relatório eletrônico (ER) para usar arquivos de gerenciamento de documentos (anexos) na saída de ER. (Parte 2)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1e79dd0a6c68aa6ba7b857c31c9159c68543d93b
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5754905"
---
# <a name="er-use-document-management-files-in-format-outputs-part-2---extend-data-model"></a><span data-ttu-id="9b831-104">ER Usar arquivos de gerenciamento de documentos em formato de saída (Parte 2 - Estender modelo de dados)</span><span class="sxs-lookup"><span data-stu-id="9b831-104">ER Use Document Management files in format outputs (Part 2 - Extend data model)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9b831-105">As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para usar arquivos de gerenciamento de documentos (anexos) na saída do ER.</span><span class="sxs-lookup"><span data-stu-id="9b831-105">The following steps explain how a user assigned to the System Administrator or Electronic Reporting Developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="9b831-106">Essas etapas podem ser executadas em qualquer empresa.</span><span class="sxs-lookup"><span data-stu-id="9b831-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="9b831-107">Para concluir estas etapas, primeiramente você deve concluir as etapas no guia de tarefas "ER Usar arquivos de gerenciamento de documentos em formatos de saída (Parte 1: preparar modelo de dados)".</span><span class="sxs-lookup"><span data-stu-id="9b831-107">To complete these steps, you must first complete the steps in the "ER Use Document Management files in format outputs (Part 1: Prepare data model)" task guide.</span></span>

<span data-ttu-id="9b831-108">Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="9b831-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="extend-data-model-to-present-the-document-management-files-in-it"></a><span data-ttu-id="9b831-109">Estender o modelo de dados para apresentar os arquivos de gerenciamento de documentos nele</span><span class="sxs-lookup"><span data-stu-id="9b831-109">Extend data model to present the Document Management files in it</span></span>
1. <span data-ttu-id="9b831-110">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="9b831-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="9b831-111">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="9b831-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="9b831-112">Na árvore, expanda 'Modelo de fatura de cliente'.</span><span class="sxs-lookup"><span data-stu-id="9b831-112">In the tree, expand 'Customer invoice model'.</span></span>
4. <span data-ttu-id="9b831-113">Na árvore, selecione 'Modelo de fatura de cliente\Modelo de fatura de cliente (personalizada)'.</span><span class="sxs-lookup"><span data-stu-id="9b831-113">In the tree, select 'Customer invoice model\Customer invoice model (custom)'.</span></span>
5. <span data-ttu-id="9b831-114">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="9b831-114">Click Designer.</span></span>
6. <span data-ttu-id="9b831-115">Na árvore, selecione 'Fatura de cliente(InvoiceCustomer)'.</span><span class="sxs-lookup"><span data-stu-id="9b831-115">In the tree, select 'Customer invoice(InvoiceCustomer)'.</span></span>
    * <span data-ttu-id="9b831-116">Estenderemos este modelo de dados para expor nele todos os arquivos associados a uma ordem de venda que esteja relacionada a um processamento eletrônico de fatura.</span><span class="sxs-lookup"><span data-stu-id="9b831-116">We will extend this data model to expose in it any files that have been attached to a sales order that is related to an electronically processing invoice.</span></span>  
7. <span data-ttu-id="9b831-117">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="9b831-117">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="9b831-118">No campo Nome, digite 'Anexos da fatura'.</span><span class="sxs-lookup"><span data-stu-id="9b831-118">In the Name field, type 'Invoice attachments'.</span></span>
    * <span data-ttu-id="9b831-119">Anexos da fatura</span><span class="sxs-lookup"><span data-stu-id="9b831-119">Invoice attachments</span></span>  
9. <span data-ttu-id="9b831-120">No campo Tipo de item, selecione 'Lista de Registro'.</span><span class="sxs-lookup"><span data-stu-id="9b831-120">In the Item type field, select 'Record list'.</span></span>
10. <span data-ttu-id="9b831-121">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="9b831-121">Click Add.</span></span>
11. <span data-ttu-id="9b831-122">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="9b831-122">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="9b831-123">No campo Nome, digite 'Conteúdo do arquivo'.</span><span class="sxs-lookup"><span data-stu-id="9b831-123">In the Name field, type 'File content'.</span></span>
    * <span data-ttu-id="9b831-124">Conteúdo do arquivo</span><span class="sxs-lookup"><span data-stu-id="9b831-124">File content</span></span>  
13. <span data-ttu-id="9b831-125">No campo Tipo de item, selecione 'Contêiner'.</span><span class="sxs-lookup"><span data-stu-id="9b831-125">In the Item type field, select 'Container'.</span></span>
14. <span data-ttu-id="9b831-126">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="9b831-126">Click Add.</span></span>
15. <span data-ttu-id="9b831-127">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="9b831-127">Click New to open the drop dialog.</span></span>
16. <span data-ttu-id="9b831-128">No campo Nome, digite 'Nome do arquivo'.</span><span class="sxs-lookup"><span data-stu-id="9b831-128">In the Name field, type 'File name'.</span></span>
    * <span data-ttu-id="9b831-129">Nome do arquivo</span><span class="sxs-lookup"><span data-stu-id="9b831-129">File name</span></span>  
17. <span data-ttu-id="9b831-130">No campo Tipo de item, selecione 'String'.</span><span class="sxs-lookup"><span data-stu-id="9b831-130">In the Item type field, select 'String'.</span></span>
18. <span data-ttu-id="9b831-131">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="9b831-131">Click Add.</span></span>

## <a name="map-new-data-model-elements-to-data-sources"></a><span data-ttu-id="9b831-132">Mapear novos elementos do modelo de dados para fontes de dados</span><span class="sxs-lookup"><span data-stu-id="9b831-132">Map new data model elements to data sources</span></span>
1. <span data-ttu-id="9b831-133">Clique em Mapear modelo para fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="9b831-133">Click Map model to datasource.</span></span>
2. <span data-ttu-id="9b831-134">Use o Filtro Rápido para filtrar no campo Definição com um valor de 'InvoiceCustomer'.</span><span class="sxs-lookup"><span data-stu-id="9b831-134">Use the Quick Filter to filter on the Definition field with a value of 'InvoiceCustomer'.</span></span>
    * <span data-ttu-id="9b831-135">InvoiceCustomer</span><span class="sxs-lookup"><span data-stu-id="9b831-135">InvoiceCustomer</span></span>  
    * <span data-ttu-id="9b831-136">Mapearemos novos elementos do modelo para utilizar fontes de dados apropriadas.</span><span class="sxs-lookup"><span data-stu-id="9b831-136">We will map new model elements to appropriate data sources.</span></span>  
3. <span data-ttu-id="9b831-137">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="9b831-137">Click Designer.</span></span>
4. <span data-ttu-id="9b831-138">Na árvore, selecione 'Anexos da fatura'.</span><span class="sxs-lookup"><span data-stu-id="9b831-138">In the tree, select 'Invoice attachments'.</span></span>
5. <span data-ttu-id="9b831-139">Na árvore, expanda 'Anexos da fatura'.</span><span class="sxs-lookup"><span data-stu-id="9b831-139">In the tree, expand 'Invoice attachments'.</span></span>
6. <span data-ttu-id="9b831-140">Na árvore, selecione 'Anexos da fatura\Nome do arquivo'.</span><span class="sxs-lookup"><span data-stu-id="9b831-140">In the tree, select 'Invoice attachments\File name'.</span></span>
7. <span data-ttu-id="9b831-141">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="9b831-141">Click Edit.</span></span>
8. <span data-ttu-id="9b831-142">No campo Fórmula, insira 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()''.</span><span class="sxs-lookup"><span data-stu-id="9b831-142">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()''.</span></span>
    * <span data-ttu-id="9b831-143">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'</span><span class="sxs-lookup"><span data-stu-id="9b831-143">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'</span></span>  
9. <span data-ttu-id="9b831-144">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="9b831-144">Click Save.</span></span>
10. <span data-ttu-id="9b831-145">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9b831-145">Close the page.</span></span>
11. <span data-ttu-id="9b831-146">Na árvore, selecione 'Anexos da fatura\Conteúdo do arquivo'.</span><span class="sxs-lookup"><span data-stu-id="9b831-146">In the tree, select 'Invoice attachments\File content'.</span></span>
12. <span data-ttu-id="9b831-147">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="9b831-147">Click Edit.</span></span>
13. <span data-ttu-id="9b831-148">No campo Fórmula, insira 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()''.</span><span class="sxs-lookup"><span data-stu-id="9b831-148">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()''.</span></span>
    * <span data-ttu-id="9b831-149">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'</span><span class="sxs-lookup"><span data-stu-id="9b831-149">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'</span></span>  
14. <span data-ttu-id="9b831-150">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="9b831-150">Click Save.</span></span>
15. <span data-ttu-id="9b831-151">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9b831-151">Close the page.</span></span>
16. <span data-ttu-id="9b831-152">Na árvore, selecione 'Anexos da fatura'.</span><span class="sxs-lookup"><span data-stu-id="9b831-152">In the tree, select 'Invoice attachments'.</span></span>
17. <span data-ttu-id="9b831-153">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="9b831-153">Click Edit.</span></span>
18. <span data-ttu-id="9b831-154">No campo Fórmula, insira 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents''.</span><span class="sxs-lookup"><span data-stu-id="9b831-154">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents''.</span></span>
    * <span data-ttu-id="9b831-155">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'</span><span class="sxs-lookup"><span data-stu-id="9b831-155">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'</span></span>  
19. <span data-ttu-id="9b831-156">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="9b831-156">Click Save.</span></span>
20. <span data-ttu-id="9b831-157">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9b831-157">Close the page.</span></span>
21. <span data-ttu-id="9b831-158">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="9b831-158">Click Save.</span></span>
22. <span data-ttu-id="9b831-159">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9b831-159">Close the page.</span></span>
23. <span data-ttu-id="9b831-160">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9b831-160">Close the page.</span></span>
24. <span data-ttu-id="9b831-161">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9b831-161">Close the page.</span></span>
25. <span data-ttu-id="9b831-162">Clique em Alterar status.</span><span class="sxs-lookup"><span data-stu-id="9b831-162">Click Change status.</span></span>
26. <span data-ttu-id="9b831-163">Clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="9b831-163">Click Complete.</span></span>
27. <span data-ttu-id="9b831-164">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="9b831-164">Click OK.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
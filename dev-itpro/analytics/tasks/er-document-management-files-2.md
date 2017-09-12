--- 
title: "Estender o modelo de dados para usar arquivos do Gerenciamento de Documentos em saídas de formato para relatório eletrônico (ER)"
description: "As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para usar arquivos de gerenciamento de documentos (anexos) na saída do ER."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 1a5325dc3a97b9e205b41fe8dae18f43e430daeb
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="extend-data-model-to-use-document-management-files-in-format-outputs-for-electronic-reporting-er"></a><span data-ttu-id="1c206-103">Estender o modelo de dados para usar arquivos do Gerenciamento de Documentos em saídas de formato para relatório eletrônico (ER)</span><span class="sxs-lookup"><span data-stu-id="1c206-103">Extend data model to use Document Management files in format outputs for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1c206-104">As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para usar arquivos de gerenciamento de documentos (anexos) na saída do ER.</span><span class="sxs-lookup"><span data-stu-id="1c206-104">The following steps explain how a user assigned to the System Administrator or Electronic Reporting Developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="1c206-105">Essas etapas podem ser executadas em qualquer empresa.</span><span class="sxs-lookup"><span data-stu-id="1c206-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="1c206-106">Para concluir estas etapas, primeiramente você deve concluir as etapas no guia de tarefas "ER Usar arquivos de gerenciamento de documentos em formatos de saída (Parte 1: preparar modelo de dados)".</span><span class="sxs-lookup"><span data-stu-id="1c206-106">To complete these steps, you must first complete the steps in the “ER Use Document Management files in format outputs (Part 1: Prepare data model)” task guide.</span></span>

<span data-ttu-id="1c206-107">Este procedimento é para um recurso que foi adicionado à versão 1611 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="1c206-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="extend-data-model-to-present-the-document-management-files-in-it"></a><span data-ttu-id="1c206-108">Estender o modelo de dados para apresentar os arquivos de gerenciamento de documentos nele</span><span class="sxs-lookup"><span data-stu-id="1c206-108">Extend data model to present the Document Management files in it</span></span>
1. <span data-ttu-id="1c206-109">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="1c206-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="1c206-110">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="1c206-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="1c206-111">Na árvore, expanda 'Modelo de fatura de cliente'.</span><span class="sxs-lookup"><span data-stu-id="1c206-111">In the tree, expand 'Customer invoice model'.</span></span>
4. <span data-ttu-id="1c206-112">Na árvore, selecione 'Modelo de fatura de cliente\Modelo de fatura de cliente (personalizada)'.</span><span class="sxs-lookup"><span data-stu-id="1c206-112">In the tree, select 'Customer invoice model\Customer invoice model (custom)'.</span></span>
5. <span data-ttu-id="1c206-113">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="1c206-113">Click Designer.</span></span>
6. <span data-ttu-id="1c206-114">Na árvore, selecione 'Fatura de cliente(InvoiceCustomer)'.</span><span class="sxs-lookup"><span data-stu-id="1c206-114">In the tree, select 'Customer invoice(InvoiceCustomer)'.</span></span>
    * <span data-ttu-id="1c206-115">Estenderemos este modelo de dados para expor nele todos os arquivos associados a uma ordem de venda que esteja relacionada a um processamento eletrônico de fatura.</span><span class="sxs-lookup"><span data-stu-id="1c206-115">We will extend this data model to expose in it any files that have been attached to a sales order that is related to an electronically processing invoice.</span></span>  
7. <span data-ttu-id="1c206-116">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1c206-116">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="1c206-117">No campo Nome, digite 'Anexos da fatura'.</span><span class="sxs-lookup"><span data-stu-id="1c206-117">In the Name field, type 'Invoice attachments'.</span></span>
    * <span data-ttu-id="1c206-118">Anexos da fatura</span><span class="sxs-lookup"><span data-stu-id="1c206-118">Invoice attachments</span></span>  
9. <span data-ttu-id="1c206-119">No campo Tipo de item, selecione 'Lista de Registro'.</span><span class="sxs-lookup"><span data-stu-id="1c206-119">In the Item type field, select 'Record list'.</span></span>
10. <span data-ttu-id="1c206-120">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="1c206-120">Click Add.</span></span>
11. <span data-ttu-id="1c206-121">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1c206-121">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="1c206-122">No campo Nome, digite 'Conteúdo do arquivo'.</span><span class="sxs-lookup"><span data-stu-id="1c206-122">In the Name field, type 'File content'.</span></span>
    * <span data-ttu-id="1c206-123">Conteúdo do arquivo</span><span class="sxs-lookup"><span data-stu-id="1c206-123">File content</span></span>  
13. <span data-ttu-id="1c206-124">No campo Tipo de item, selecione 'Contêiner'.</span><span class="sxs-lookup"><span data-stu-id="1c206-124">In the Item type field, select 'Container'.</span></span>
14. <span data-ttu-id="1c206-125">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="1c206-125">Click Add.</span></span>
15. <span data-ttu-id="1c206-126">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1c206-126">Click New to open the drop dialog.</span></span>
16. <span data-ttu-id="1c206-127">No campo Nome, digite 'Nome do arquivo'.</span><span class="sxs-lookup"><span data-stu-id="1c206-127">In the Name field, type 'File name'.</span></span>
    * <span data-ttu-id="1c206-128">Nome do arquivo</span><span class="sxs-lookup"><span data-stu-id="1c206-128">File name</span></span>  
17. <span data-ttu-id="1c206-129">No campo Tipo de item, selecione 'String'.</span><span class="sxs-lookup"><span data-stu-id="1c206-129">In the Item type field, select 'String'.</span></span>
18. <span data-ttu-id="1c206-130">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="1c206-130">Click Add.</span></span>

## <a name="map-new-data-model-elements-to-dynamics-365-for-finance-and-operations-enterprise-edition-data-sources"></a><span data-ttu-id="1c206-131">Mapeie os novos elementos do modelo de dados para as fontes de dados do Dynamics 365 for Finance and Operations, edição Enterprise.</span><span class="sxs-lookup"><span data-stu-id="1c206-131">Map new data model elements to Dynamics 365 for Finance and Operations, Enterprise edition data sources</span></span>
1. <span data-ttu-id="1c206-132">Clique em Mapear modelo para fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="1c206-132">Click Map model to datasource.</span></span>
2. <span data-ttu-id="1c206-133">Use o Filtro Rápido para filtrar no campo Definição com um valor de 'InvoiceCustomer'.</span><span class="sxs-lookup"><span data-stu-id="1c206-133">Use the Quick Filter to filter on the Definition field with a value of 'InvoiceCustomer'.</span></span>
    * <span data-ttu-id="1c206-134">InvoiceCustomer</span><span class="sxs-lookup"><span data-stu-id="1c206-134">InvoiceCustomer</span></span>  
    * <span data-ttu-id="1c206-135">Mapearemos novos elementos do modelo para utilizar fontes de dados apropriadas.</span><span class="sxs-lookup"><span data-stu-id="1c206-135">We will map new model elements to appropriate data sources.</span></span>  
3. <span data-ttu-id="1c206-136">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="1c206-136">Click Designer.</span></span>
4. <span data-ttu-id="1c206-137">Na árvore, selecione 'Anexos da fatura'.</span><span class="sxs-lookup"><span data-stu-id="1c206-137">In the tree, select 'Invoice attachments'.</span></span>
5. <span data-ttu-id="1c206-138">Na árvore, expanda 'Anexos da fatura'.</span><span class="sxs-lookup"><span data-stu-id="1c206-138">In the tree, expand 'Invoice attachments'.</span></span>
6. <span data-ttu-id="1c206-139">Na árvore, selecione 'Anexos da fatura\Nome do arquivo'.</span><span class="sxs-lookup"><span data-stu-id="1c206-139">In the tree, select 'Invoice attachments\File name'.</span></span>
7. <span data-ttu-id="1c206-140">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="1c206-140">Click Edit.</span></span>
8. <span data-ttu-id="1c206-141">No campo Fórmula, insira 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()''.</span><span class="sxs-lookup"><span data-stu-id="1c206-141">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()''.</span></span>
    * <span data-ttu-id="1c206-142">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'</span><span class="sxs-lookup"><span data-stu-id="1c206-142">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'</span></span>  
9. <span data-ttu-id="1c206-143">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="1c206-143">Click Save.</span></span>
10. <span data-ttu-id="1c206-144">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1c206-144">Close the page.</span></span>
11. <span data-ttu-id="1c206-145">Na árvore, selecione 'Anexos da fatura\Conteúdo do arquivo'.</span><span class="sxs-lookup"><span data-stu-id="1c206-145">In the tree, select 'Invoice attachments\File content'.</span></span>
12. <span data-ttu-id="1c206-146">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="1c206-146">Click Edit.</span></span>
13. <span data-ttu-id="1c206-147">No campo Fórmula, insira 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()''.</span><span class="sxs-lookup"><span data-stu-id="1c206-147">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()''.</span></span>
    * <span data-ttu-id="1c206-148">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'</span><span class="sxs-lookup"><span data-stu-id="1c206-148">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'</span></span>  
14. <span data-ttu-id="1c206-149">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="1c206-149">Click Save.</span></span>
15. <span data-ttu-id="1c206-150">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1c206-150">Close the page.</span></span>
16. <span data-ttu-id="1c206-151">Na árvore, selecione 'Anexos da fatura'.</span><span class="sxs-lookup"><span data-stu-id="1c206-151">In the tree, select 'Invoice attachments'.</span></span>
17. <span data-ttu-id="1c206-152">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="1c206-152">Click Edit.</span></span>
18. <span data-ttu-id="1c206-153">No campo Fórmula, insira 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents''.</span><span class="sxs-lookup"><span data-stu-id="1c206-153">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents''.</span></span>
    * <span data-ttu-id="1c206-154">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'</span><span class="sxs-lookup"><span data-stu-id="1c206-154">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'</span></span>  
19. <span data-ttu-id="1c206-155">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="1c206-155">Click Save.</span></span>
20. <span data-ttu-id="1c206-156">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1c206-156">Close the page.</span></span>
21. <span data-ttu-id="1c206-157">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="1c206-157">Click Save.</span></span>
22. <span data-ttu-id="1c206-158">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1c206-158">Close the page.</span></span>
23. <span data-ttu-id="1c206-159">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1c206-159">Close the page.</span></span>
24. <span data-ttu-id="1c206-160">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1c206-160">Close the page.</span></span>
25. <span data-ttu-id="1c206-161">Clique em Alterar status.</span><span class="sxs-lookup"><span data-stu-id="1c206-161">Click Change status.</span></span>
26. <span data-ttu-id="1c206-162">Clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="1c206-162">Click Complete.</span></span>
27. <span data-ttu-id="1c206-163">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="1c206-163">Click OK.</span></span>



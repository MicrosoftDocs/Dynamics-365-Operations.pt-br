---
title: O ER usar arquivos de gerenciamento de documentos em formato de saída (parte 4 - executar formato)
description: As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico para usar arquivos de gerenciamento de documentos na saída do ER.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustOpenInvoicesListPage, CustInvoiceJournal, SalesTable, ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f5639a46c105e735d028e903513b4fcfb1f0d968
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142603"
---
# <a name="er-use-document-management-files-in-format-outputs-part-4---run-format"></a><span data-ttu-id="d0567-103">O ER usar arquivos de gerenciamento de documentos em formato de saída (parte 4 - executar formato)</span><span class="sxs-lookup"><span data-stu-id="d0567-103">ER Use Document Management files in format outputs (Part 4 - Run format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d0567-104">As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para usar arquivos de gerenciamento de documentos (anexos) na saída do ER.</span><span class="sxs-lookup"><span data-stu-id="d0567-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="d0567-105">Essas etapas podem ser executadas na empresa DEMF.</span><span class="sxs-lookup"><span data-stu-id="d0567-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="d0567-106">Para concluir estas etapas, primeiramente você deve concluir as etapas no procedimento "ER Usar arquivos de gerenciamento de documentos em formatos de saída (Parte 3: criar formato)".</span><span class="sxs-lookup"><span data-stu-id="d0567-106">To complete these steps, you must first complete the steps in the "ER Use Document Management files in format outputs (Part 3: Create format)" procedure.</span></span>

<span data-ttu-id="d0567-107">Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="d0567-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="add-necessary-attachments-for-sales-order-of-a-single-invoice"></a><span data-ttu-id="d0567-108">Adicionar os anexos necessários para a ordem de venda de uma única fatura</span><span class="sxs-lookup"><span data-stu-id="d0567-108">Add necessary attachments for sales order of a single invoice</span></span>
1. <span data-ttu-id="d0567-109">Vá para Contas recebíveis > Faturas > Faturas de cliente abertas.</span><span class="sxs-lookup"><span data-stu-id="d0567-109">Go to Accounts receivable > Invoices > Open customer invoices.</span></span>
2. <span data-ttu-id="d0567-110">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="d0567-110">Use the Quick Filter to find records.</span></span> <span data-ttu-id="d0567-111">Por exemplo, filtre o campo Fatura com um valor de 'CIV-000148'.</span><span class="sxs-lookup"><span data-stu-id="d0567-111">For example, filter on the Invoice field with a value of 'CIV-000148'.</span></span>
    * <span data-ttu-id="d0567-112">CIV-000148</span><span class="sxs-lookup"><span data-stu-id="d0567-112">CIV-000148</span></span>  
3. <span data-ttu-id="d0567-113">Clique para seguir o link da fatura selecionada.</span><span class="sxs-lookup"><span data-stu-id="d0567-113">Click to follow the selected invoice's link.</span></span>
    * <span data-ttu-id="d0567-114">CIV-000148</span><span class="sxs-lookup"><span data-stu-id="d0567-114">CIV-000148</span></span>  
4. <span data-ttu-id="d0567-115">Clique para seguir o link no campo Ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="d0567-115">Click to follow the link in the Sales order field.</span></span>
    * <span data-ttu-id="d0567-116">000148</span><span class="sxs-lookup"><span data-stu-id="d0567-116">000148</span></span>  
5. <span data-ttu-id="d0567-117">No campo Linhas ou cabeçalho, selecione a opção de Cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="d0567-117">In the Lines or header field, select the option of Header.</span></span>
    * <span data-ttu-id="d0567-118">Selecione Cabeçalho para indicar que este será o alvo para a adição de anexos.</span><span class="sxs-lookup"><span data-stu-id="d0567-118">Select Header to indicate that this will be the target for adding attachments.</span></span>  
6. <span data-ttu-id="d0567-119">Clique em Anexar.</span><span class="sxs-lookup"><span data-stu-id="d0567-119">Click Attach.</span></span>
    * <span data-ttu-id="d0567-120">Adicione alguns arquivos como anexos a esta ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="d0567-120">Add a few files as attachments for this sales order.</span></span> <span data-ttu-id="d0567-121">Use os arquivos dos tipos de documento que têm suporte do gerenciamento de documentos (com extensões de arquivo DOCX, DPF XML JPG, etc.).</span><span class="sxs-lookup"><span data-stu-id="d0567-121">Use the files of the document types that are supported by the Document Management (with file extensions DOCX, DPF, XML, JPG, etc.).</span></span> <span data-ttu-id="d0567-122">Procure e selecione os arquivos a serem anexados e processados com a fatura relacionada na mensagem eletrônica do ER.</span><span class="sxs-lookup"><span data-stu-id="d0567-122">Browse and select files to be attached and further processed with the related invoice in the ER electronic message.</span></span>  
7. <span data-ttu-id="d0567-123">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="d0567-123">Click New.</span></span>
8. <span data-ttu-id="d0567-124">Clique em Arquivo.</span><span class="sxs-lookup"><span data-stu-id="d0567-124">Click File.</span></span>
9. <span data-ttu-id="d0567-125">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="d0567-125">Click New.</span></span>
10. <span data-ttu-id="d0567-126">Clique em Arquivo.</span><span class="sxs-lookup"><span data-stu-id="d0567-126">Click File.</span></span>
11. <span data-ttu-id="d0567-127">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d0567-127">Close the page.</span></span>
12. <span data-ttu-id="d0567-128">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d0567-128">Close the page.</span></span>
13. <span data-ttu-id="d0567-129">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d0567-129">Close the page.</span></span>
14. <span data-ttu-id="d0567-130">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d0567-130">Close the page.</span></span>

## <a name="run-the-designed-report-for-the-selected-invoice"></a><span data-ttu-id="d0567-131">Executar relatório criado para a fatura selecionada</span><span class="sxs-lookup"><span data-stu-id="d0567-131">Run the designed report for the selected invoice</span></span>
1. <span data-ttu-id="d0567-132">Vá para Administração da organização > Relatório eletrônico > Configurações.</span><span class="sxs-lookup"><span data-stu-id="d0567-132">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="d0567-133">Na árvore, expanda 'Modelo de fatura de cliente'.</span><span class="sxs-lookup"><span data-stu-id="d0567-133">In the tree, expand 'Customer invoice model'.</span></span>
3. <span data-ttu-id="d0567-134">Na árvore, expanda 'Modelo de fatura de cliente\Modelo de fatura de cliente (personalizada)'.</span><span class="sxs-lookup"><span data-stu-id="d0567-134">In the tree, expand 'Customer invoice model\Customer invoice model (custom)'.</span></span>
4. <span data-ttu-id="d0567-135">Na árvore, selecione 'Modelo de fatura de cliente\Modelo de fatura de cliente (personalizada)\Mensagem de exemplo da fatura eletrônica'.</span><span class="sxs-lookup"><span data-stu-id="d0567-135">In the tree, select 'Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message'.</span></span>
5. <span data-ttu-id="d0567-136">Clique em Executar.</span><span class="sxs-lookup"><span data-stu-id="d0567-136">Click Run.</span></span>
6. <span data-ttu-id="d0567-137">Expanda os Registros para incluir a seção ().</span><span class="sxs-lookup"><span data-stu-id="d0567-137">Expand the Records to include () section.</span></span>
7. <span data-ttu-id="d0567-138">Clique em Filtro.</span><span class="sxs-lookup"><span data-stu-id="d0567-138">Click Filter.</span></span>
8. <span data-ttu-id="d0567-139">Selecione a linha do diário de faturas do cliente e o campo Ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="d0567-139">Select the row of the Customer invoice journal and the Sales order field.</span></span>
9. <span data-ttu-id="d0567-140">No campo Critérios, digite '000148'.</span><span class="sxs-lookup"><span data-stu-id="d0567-140">In the Criteria field, type '000148'.</span></span>
    * <span data-ttu-id="d0567-141">No campo do critério "Ordem de venda" digite o número de ordem 000148.</span><span class="sxs-lookup"><span data-stu-id="d0567-141">In the criteria "Sales order" field, type the order number 000148.</span></span>  
10. <span data-ttu-id="d0567-142">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="d0567-142">Click OK.</span></span>
11. <span data-ttu-id="d0567-143">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="d0567-143">Click OK.</span></span>
    * <span data-ttu-id="d0567-144">Revise a saída gerada.</span><span class="sxs-lookup"><span data-stu-id="d0567-144">Review the generated output.</span></span> <span data-ttu-id="d0567-145">Observe que um único nó XML foi criado para cada anexo.</span><span class="sxs-lookup"><span data-stu-id="d0567-145">Note that for each attachment a single XML node has been created.</span></span> <span data-ttu-id="d0567-146">O conteúdo do anexo é preenchido na saída do XML no formato de texto MIME (base64).</span><span class="sxs-lookup"><span data-stu-id="d0567-146">The attachment's content is populated to the XML output in MIME (base64) text format.</span></span>  


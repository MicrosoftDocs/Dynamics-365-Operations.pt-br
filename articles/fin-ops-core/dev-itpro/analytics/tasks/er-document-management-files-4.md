---
title: O ER usar arquivos de gerenciamento de documentos em formato de saída (parte 4 - executar formato)
description: Este tópico descreve como configurar um formato de relatório eletrônico para usar arquivos de gerenciamento de documentos na saída de ER. (Parte 4)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenInvoicesListPage, CustInvoiceJournal, SalesTable, ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ede71118f64eec27b150a4c575aead97d3174509
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559716"
---
# <a name="er-use-document-management-files-in-format-outputs-part-4---run-format"></a><span data-ttu-id="a33db-104">O ER usar arquivos de gerenciamento de documentos em formato de saída (parte 4 - executar formato)</span><span class="sxs-lookup"><span data-stu-id="a33db-104">ER Use Document Management files in format outputs (Part 4 - Run format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a33db-105">As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para usar arquivos de gerenciamento de documentos (anexos) na saída do ER.</span><span class="sxs-lookup"><span data-stu-id="a33db-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="a33db-106">Essas etapas podem ser executadas na empresa DEMF.</span><span class="sxs-lookup"><span data-stu-id="a33db-106">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="a33db-107">Para concluir estas etapas, primeiramente você deve concluir as etapas no procedimento "ER Usar arquivos de gerenciamento de documentos em formatos de saída (Parte 3: criar formato)".</span><span class="sxs-lookup"><span data-stu-id="a33db-107">To complete these steps, you must first complete the steps in the "ER Use Document Management files in format outputs (Part 3: Create format)" procedure.</span></span>

<span data-ttu-id="a33db-108">Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="a33db-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="add-necessary-attachments-for-sales-order-of-a-single-invoice"></a><span data-ttu-id="a33db-109">Adicionar os anexos necessários para a ordem de venda de uma única fatura</span><span class="sxs-lookup"><span data-stu-id="a33db-109">Add necessary attachments for sales order of a single invoice</span></span>
1. <span data-ttu-id="a33db-110">Vá para Contas recebíveis > Faturas > Faturas de cliente abertas.</span><span class="sxs-lookup"><span data-stu-id="a33db-110">Go to Accounts receivable > Invoices > Open customer invoices.</span></span>
2. <span data-ttu-id="a33db-111">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="a33db-111">Use the Quick Filter to find records.</span></span> <span data-ttu-id="a33db-112">Por exemplo, filtre o campo Fatura com um valor de 'CIV-000148'.</span><span class="sxs-lookup"><span data-stu-id="a33db-112">For example, filter on the Invoice field with a value of 'CIV-000148'.</span></span>
    * <span data-ttu-id="a33db-113">CIV-000148</span><span class="sxs-lookup"><span data-stu-id="a33db-113">CIV-000148</span></span>  
3. <span data-ttu-id="a33db-114">Clique para seguir o link da fatura selecionada.</span><span class="sxs-lookup"><span data-stu-id="a33db-114">Click to follow the selected invoice's link.</span></span>
    * <span data-ttu-id="a33db-115">CIV-000148</span><span class="sxs-lookup"><span data-stu-id="a33db-115">CIV-000148</span></span>  
4. <span data-ttu-id="a33db-116">Clique para seguir o link no campo Ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="a33db-116">Click to follow the link in the Sales order field.</span></span>
    * <span data-ttu-id="a33db-117">000148</span><span class="sxs-lookup"><span data-stu-id="a33db-117">000148</span></span>  
5. <span data-ttu-id="a33db-118">No campo Linhas ou cabeçalho, selecione a opção de Cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="a33db-118">In the Lines or header field, select the option of Header.</span></span>
    * <span data-ttu-id="a33db-119">Selecione Cabeçalho para indicar que este será o alvo para a adição de anexos.</span><span class="sxs-lookup"><span data-stu-id="a33db-119">Select Header to indicate that this will be the target for adding attachments.</span></span>  
6. <span data-ttu-id="a33db-120">Clique em Anexar.</span><span class="sxs-lookup"><span data-stu-id="a33db-120">Click Attach.</span></span>
    * <span data-ttu-id="a33db-121">Adicione alguns arquivos como anexos a esta ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="a33db-121">Add a few files as attachments for this sales order.</span></span> <span data-ttu-id="a33db-122">Use os arquivos dos tipos de documento que têm suporte do gerenciamento de documentos (com extensões de arquivo DOCX, DPF XML JPG, etc.).</span><span class="sxs-lookup"><span data-stu-id="a33db-122">Use the files of the document types that are supported by the Document Management (with file extensions DOCX, DPF, XML, JPG, etc.).</span></span> <span data-ttu-id="a33db-123">Procure e selecione os arquivos a serem anexados e processados com a fatura relacionada na mensagem eletrônica do ER.</span><span class="sxs-lookup"><span data-stu-id="a33db-123">Browse and select files to be attached and further processed with the related invoice in the ER electronic message.</span></span>  
7. <span data-ttu-id="a33db-124">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="a33db-124">Click New.</span></span>
8. <span data-ttu-id="a33db-125">Clique em Arquivo.</span><span class="sxs-lookup"><span data-stu-id="a33db-125">Click File.</span></span>
9. <span data-ttu-id="a33db-126">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="a33db-126">Click New.</span></span>
10. <span data-ttu-id="a33db-127">Clique em Arquivo.</span><span class="sxs-lookup"><span data-stu-id="a33db-127">Click File.</span></span>
11. <span data-ttu-id="a33db-128">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a33db-128">Close the page.</span></span>
12. <span data-ttu-id="a33db-129">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a33db-129">Close the page.</span></span>
13. <span data-ttu-id="a33db-130">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a33db-130">Close the page.</span></span>
14. <span data-ttu-id="a33db-131">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a33db-131">Close the page.</span></span>

## <a name="run-the-designed-report-for-the-selected-invoice"></a><span data-ttu-id="a33db-132">Executar relatório criado para a fatura selecionada</span><span class="sxs-lookup"><span data-stu-id="a33db-132">Run the designed report for the selected invoice</span></span>
1. <span data-ttu-id="a33db-133">Vá para Administração da organização > Relatório eletrônico > Configurações.</span><span class="sxs-lookup"><span data-stu-id="a33db-133">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="a33db-134">Na árvore, expanda 'Modelo de fatura de cliente'.</span><span class="sxs-lookup"><span data-stu-id="a33db-134">In the tree, expand 'Customer invoice model'.</span></span>
3. <span data-ttu-id="a33db-135">Na árvore, expanda 'Modelo de fatura de cliente\Modelo de fatura de cliente (personalizada)'.</span><span class="sxs-lookup"><span data-stu-id="a33db-135">In the tree, expand 'Customer invoice model\Customer invoice model (custom)'.</span></span>
4. <span data-ttu-id="a33db-136">Na árvore, selecione 'Modelo de fatura de cliente\Modelo de fatura de cliente (personalizada)\Mensagem de exemplo da fatura eletrônica'.</span><span class="sxs-lookup"><span data-stu-id="a33db-136">In the tree, select 'Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message'.</span></span>
5. <span data-ttu-id="a33db-137">Clique em Executar.</span><span class="sxs-lookup"><span data-stu-id="a33db-137">Click Run.</span></span>
6. <span data-ttu-id="a33db-138">Expanda os Registros para incluir a seção ().</span><span class="sxs-lookup"><span data-stu-id="a33db-138">Expand the Records to include () section.</span></span>
7. <span data-ttu-id="a33db-139">Clique em Filtro.</span><span class="sxs-lookup"><span data-stu-id="a33db-139">Click Filter.</span></span>
8. <span data-ttu-id="a33db-140">Selecione a linha do diário de faturas do cliente e o campo Ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="a33db-140">Select the row of the Customer invoice journal and the Sales order field.</span></span>
9. <span data-ttu-id="a33db-141">No campo Critérios, digite '000148'.</span><span class="sxs-lookup"><span data-stu-id="a33db-141">In the Criteria field, type '000148'.</span></span>
    * <span data-ttu-id="a33db-142">No campo do critério "Ordem de venda" digite o número de ordem 000148.</span><span class="sxs-lookup"><span data-stu-id="a33db-142">In the criteria "Sales order" field, type the order number 000148.</span></span>  
10. <span data-ttu-id="a33db-143">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="a33db-143">Click OK.</span></span>
11. <span data-ttu-id="a33db-144">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="a33db-144">Click OK.</span></span>
    * <span data-ttu-id="a33db-145">Revise a saída gerada.</span><span class="sxs-lookup"><span data-stu-id="a33db-145">Review the generated output.</span></span> <span data-ttu-id="a33db-146">Observe que um único nó XML foi criado para cada anexo.</span><span class="sxs-lookup"><span data-stu-id="a33db-146">Note that for each attachment a single XML node has been created.</span></span> <span data-ttu-id="a33db-147">O conteúdo do anexo é preenchido na saída do XML no formato de texto MIME (base64).</span><span class="sxs-lookup"><span data-stu-id="a33db-147">The attachment's content is populated to the XML output in MIME (base64) text format.</span></span>  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
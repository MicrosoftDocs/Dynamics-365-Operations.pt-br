---
title: Criar e processar uma conformidade
description: Use este procedimento para executar o gerenciamento de não conformidades, com base em uma ordem de qualidade existente.
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 16ed11bce92920fe8240fc85f706a2ac6ab0a04b
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "336281"
---
# <a name="create-and-process-a-conformance"></a><span data-ttu-id="f8643-103">Criar e processar uma conformidade</span><span class="sxs-lookup"><span data-stu-id="f8643-103">Create and process a conformance</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f8643-104">Use este procedimento para executar o gerenciamento de não conformidades, com base em uma ordem de qualidade existente.</span><span class="sxs-lookup"><span data-stu-id="f8643-104">Use this procedure to perform nonconformance management, based on an existing quality order.</span></span> <span data-ttu-id="f8643-105">Você pode executar esse registro na empresa de demonstração USMF e pode usar os valores sugeridos.</span><span class="sxs-lookup"><span data-stu-id="f8643-105">You can run this recording in the USMF demo company and can use the suggested values.</span></span> <span data-ttu-id="f8643-106">Normalmente, esse procedimento é realizado por um encarregado de qualidade.</span><span class="sxs-lookup"><span data-stu-id="f8643-106">Typically, this procedure is performed by a quality clerk.</span></span>  <span data-ttu-id="f8643-107">Como um pré-requisito, execute o registro de tarefa “Inspecionar a qualidade das mercadorias“.</span><span class="sxs-lookup"><span data-stu-id="f8643-107">As a prerequisite, run the “Inspect the quality of goods” task recording.</span></span> <span data-ttu-id="f8643-108">Para processar a aprovação de uma não conformidade, o usuário que executa o registro de tarefa deve ter um valor de “Nome“ atribuído na página Usuários.</span><span class="sxs-lookup"><span data-stu-id="f8643-108">To process the approval of a nonconformance, the user who runs the task recording must have a “Name” value assigned on the Users page.</span></span> <span data-ttu-id="f8643-109">Para usar as notas do documento, o usuário também deve ter o Manuseio de documentos ativado nas opções do usuário.</span><span class="sxs-lookup"><span data-stu-id="f8643-109">To use the document notes, the user must also have Document handling activated in the user options.</span></span>


## <a name="select-a-quality-order"></a><span data-ttu-id="f8643-110">Selecione uma ordem de qualidade</span><span class="sxs-lookup"><span data-stu-id="f8643-110">Select a quality order</span></span>
1. <span data-ttu-id="f8643-111">Vá para Ordens de qualidade.</span><span class="sxs-lookup"><span data-stu-id="f8643-111">Go to Quality orders.</span></span>
2. <span data-ttu-id="f8643-112">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="f8643-112">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="f8643-113">Selecione a ordem de qualidade que foi criada no registro de tarefa "Inspecionar a qualidade das mercadorias".</span><span class="sxs-lookup"><span data-stu-id="f8643-113">Select the quality order that was created from the "Inspect the quality of goods" task recording.</span></span>  

## <a name="create-a-nonconformance"></a><span data-ttu-id="f8643-114">Criar uma não conformidade</span><span class="sxs-lookup"><span data-stu-id="f8643-114">Create a nonconformance</span></span>
1. <span data-ttu-id="f8643-115">Clique em Consultas.</span><span class="sxs-lookup"><span data-stu-id="f8643-115">Click Inquiries.</span></span>
2. <span data-ttu-id="f8643-116">Clique em Não conformidades.</span><span class="sxs-lookup"><span data-stu-id="f8643-116">Click Non conformances.</span></span>
3. <span data-ttu-id="f8643-117">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="f8643-117">Click New.</span></span>
4. <span data-ttu-id="f8643-118">No campo Tipo de problema, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f8643-118">In the Problem type field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="f8643-119">Selecione o problema encontrado durante o processo de inspeção.</span><span class="sxs-lookup"><span data-stu-id="f8643-119">Select the problem that was found during the inspection process.</span></span>  
5. <span data-ttu-id="f8643-120">No campo Tipo de problema, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f8643-120">In the Problem type field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="f8643-121">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="f8643-121">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="f8643-122">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="f8643-122">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="f8643-123">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f8643-123">Click OK.</span></span>

## <a name="approvereject-a-nonconformance"></a><span data-ttu-id="f8643-124">Aprovar/rejeitar uma não conformidade</span><span class="sxs-lookup"><span data-stu-id="f8643-124">Approve/reject a nonconformance</span></span>
1. <span data-ttu-id="f8643-125">Clique em Funções.</span><span class="sxs-lookup"><span data-stu-id="f8643-125">Click Functions.</span></span>
2. <span data-ttu-id="f8643-126">Clique em Aprovar a não conformidade.</span><span class="sxs-lookup"><span data-stu-id="f8643-126">Click Approve non conformance.</span></span>
    * <span data-ttu-id="f8643-127">Para esse exemplo, aprove a não conformidade.</span><span class="sxs-lookup"><span data-stu-id="f8643-127">For this example, approve the nonconformance.</span></span> <span data-ttu-id="f8643-128">Não conformidades aprovadas podem ser associadas às operações relacionadas para registrar o trabalho que é feito como parte do manuseio da não conformidade e, como nesse registro de tarefa, o processamento do manuseio de correção.</span><span class="sxs-lookup"><span data-stu-id="f8643-128">Approved nonconformances can be associated with related operations to record work that is done as part of the nonconformance handling and, as in this task recording, the processing of correction handling.</span></span>  
3. <span data-ttu-id="f8643-129">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="f8643-129">Click Yes.</span></span>

## <a name="create-a-correction-action"></a><span data-ttu-id="f8643-130">Criar uma ação de correção</span><span class="sxs-lookup"><span data-stu-id="f8643-130">Create a correction action</span></span>
1. <span data-ttu-id="f8643-131">Clique em Correções.</span><span class="sxs-lookup"><span data-stu-id="f8643-131">Click Corrections.</span></span>
2. <span data-ttu-id="f8643-132">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="f8643-132">Click New.</span></span>
3. <span data-ttu-id="f8643-133">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="f8643-133">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="f8643-134">No campo Número dos funcionários, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f8643-134">In the Personnel number field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="f8643-135">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="f8643-135">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="f8643-136">Clique em Selecionar.</span><span class="sxs-lookup"><span data-stu-id="f8643-136">Click Select.</span></span>
7. <span data-ttu-id="f8643-137">Clique em Anexar.</span><span class="sxs-lookup"><span data-stu-id="f8643-137">Click Attach.</span></span>
    * <span data-ttu-id="f8643-138">Crie uma nota sobre a correção.</span><span class="sxs-lookup"><span data-stu-id="f8643-138">Create a note about the correction.</span></span> <span data-ttu-id="f8643-139">Neste exemplo, a ação é entrar em contato com o fornecedor para discutir o caso não conformidade.</span><span class="sxs-lookup"><span data-stu-id="f8643-139">For this example, the action is to contact the vendor to discuss the nonconformance case.</span></span>  
8. <span data-ttu-id="f8643-140">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="f8643-140">Click New.</span></span>
9. <span data-ttu-id="f8643-141">Clique em Nota.</span><span class="sxs-lookup"><span data-stu-id="f8643-141">Click Note.</span></span>
    * <span data-ttu-id="f8643-142">Observe que, dependendo da configuração do relatório, diferentes tipos de documentos podem ser impressos em relatórios relacionados ao gerenciamento de não conformidades.</span><span class="sxs-lookup"><span data-stu-id="f8643-142">Note that, depending on the report setup, different document types can be printed on the reports that are related to nonconformance management.</span></span>  
10. <span data-ttu-id="f8643-143">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f8643-143">In the Description field, type a value.</span></span>
11. <span data-ttu-id="f8643-144">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f8643-144">Close the page.</span></span>

## <a name="maintain-a-correction"></a><span data-ttu-id="f8643-145">Manter uma correção</span><span class="sxs-lookup"><span data-stu-id="f8643-145">Maintain a correction</span></span>
1. <span data-ttu-id="f8643-146">Clique em Marcar como completo.</span><span class="sxs-lookup"><span data-stu-id="f8643-146">Click Mark complete.</span></span>
2. <span data-ttu-id="f8643-147">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f8643-147">Click OK.</span></span>
3. <span data-ttu-id="f8643-148">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f8643-148">Close the page.</span></span>

## <a name="close-a-nonconformance"></a><span data-ttu-id="f8643-149">Fechar uma não conformidade</span><span class="sxs-lookup"><span data-stu-id="f8643-149">Close a nonconformance</span></span>
1. <span data-ttu-id="f8643-150">Clique em Funções.</span><span class="sxs-lookup"><span data-stu-id="f8643-150">Click Functions.</span></span>
2. <span data-ttu-id="f8643-151">Clique em Fechar a não conformidade.</span><span class="sxs-lookup"><span data-stu-id="f8643-151">Click Close non conformance.</span></span>
3. <span data-ttu-id="f8643-152">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="f8643-152">Click Yes.</span></span>
4. <span data-ttu-id="f8643-153">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f8643-153">Close the page.</span></span>
5. <span data-ttu-id="f8643-154">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f8643-154">Close the page.</span></span>

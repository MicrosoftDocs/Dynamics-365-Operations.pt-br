---
title: Criar e processar uma conformidade
description: "Use este procedimento para executar o gerenciamento de não conformidades, com base em uma ordem de qualidade existente."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0e7f66cccd76e5326fce75d1a13aff294c16fb9b
ms.openlocfilehash: e5187c44aac881273900b2fc0ca91045a65cd838
ms.contentlocale: pt-br
ms.lasthandoff: 09/12/2017

---
# <a name="create-and-process-a-conformance"></a><span data-ttu-id="9dabb-103">Criar e processar uma conformidade</span><span class="sxs-lookup"><span data-stu-id="9dabb-103">Create and process a conformance</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9dabb-104">Use este procedimento para executar o gerenciamento de não conformidades, com base em uma ordem de qualidade existente.</span><span class="sxs-lookup"><span data-stu-id="9dabb-104">Use this procedure to perform nonconformance management, based on an existing quality order.</span></span> <span data-ttu-id="9dabb-105">Você pode executar esse registro na empresa de demonstração USMF e pode usar os valores sugeridos.</span><span class="sxs-lookup"><span data-stu-id="9dabb-105">You can run this recording in the USMF demo company and can use the suggested values.</span></span> <span data-ttu-id="9dabb-106">Normalmente, esse procedimento é realizado por um encarregado de qualidade.</span><span class="sxs-lookup"><span data-stu-id="9dabb-106">Typically, this procedure is performed by a quality clerk.</span></span>  <span data-ttu-id="9dabb-107">Como um pré-requisito, execute o registro de tarefa “Inspecionar a qualidade das mercadorias“.</span><span class="sxs-lookup"><span data-stu-id="9dabb-107">As a prerequisite, run the “Inspect the quality of goods” task recording.</span></span> <span data-ttu-id="9dabb-108">Para processar a aprovação de uma não conformidade, o usuário que executa o registro de tarefa deve ter um valor de “Nome“ atribuído na página Usuários.</span><span class="sxs-lookup"><span data-stu-id="9dabb-108">To process the approval of a nonconformance, the user who runs the task recording must have a “Name” value assigned on the Users page.</span></span> <span data-ttu-id="9dabb-109">Para usar as notas do documento, o usuário também deve ter o Manuseio de documentos ativado nas opções do usuário.</span><span class="sxs-lookup"><span data-stu-id="9dabb-109">To use the document notes, the user must also have Document handling activated in the user options.</span></span>


## <a name="select-a-quality-order"></a><span data-ttu-id="9dabb-110">Selecione uma ordem de qualidade</span><span class="sxs-lookup"><span data-stu-id="9dabb-110">Select a quality order</span></span>
1. <span data-ttu-id="9dabb-111">Vá para Ordens de qualidade.</span><span class="sxs-lookup"><span data-stu-id="9dabb-111">Go to Quality orders.</span></span>
2. <span data-ttu-id="9dabb-112">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="9dabb-112">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="9dabb-113">Selecione a ordem de qualidade que foi criada no registro de tarefa "Inspecionar a qualidade das mercadorias".</span><span class="sxs-lookup"><span data-stu-id="9dabb-113">Select the quality order that was created from the "Inspect the quality of goods" task recording.</span></span>  

## <a name="create-a-nonconformance"></a><span data-ttu-id="9dabb-114">Criar uma não conformidade</span><span class="sxs-lookup"><span data-stu-id="9dabb-114">Create a nonconformance</span></span>
1. <span data-ttu-id="9dabb-115">Clique em Consultas.</span><span class="sxs-lookup"><span data-stu-id="9dabb-115">Click Inquiries.</span></span>
2. <span data-ttu-id="9dabb-116">Clique em Não conformidades.</span><span class="sxs-lookup"><span data-stu-id="9dabb-116">Click Non conformances.</span></span>
3. <span data-ttu-id="9dabb-117">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="9dabb-117">Click New.</span></span>
4. <span data-ttu-id="9dabb-118">No campo Tipo de problema, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="9dabb-118">In the Problem type field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="9dabb-119">Selecione o problema encontrado durante o processo de inspeção.</span><span class="sxs-lookup"><span data-stu-id="9dabb-119">Select the problem that was found during the inspection process.</span></span>  
5. <span data-ttu-id="9dabb-120">No campo Tipo de problema, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="9dabb-120">In the Problem type field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="9dabb-121">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="9dabb-121">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="9dabb-122">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="9dabb-122">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="9dabb-123">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="9dabb-123">Click OK.</span></span>

## <a name="approvereject-a-nonconformance"></a><span data-ttu-id="9dabb-124">Aprovar/rejeitar uma não conformidade</span><span class="sxs-lookup"><span data-stu-id="9dabb-124">Approve/reject a nonconformance</span></span>
1. <span data-ttu-id="9dabb-125">Clique em Funções.</span><span class="sxs-lookup"><span data-stu-id="9dabb-125">Click Functions.</span></span>
2. <span data-ttu-id="9dabb-126">Clique em Aprovar a não conformidade.</span><span class="sxs-lookup"><span data-stu-id="9dabb-126">Click Approve non conformance.</span></span>
    * <span data-ttu-id="9dabb-127">Para esse exemplo, aprove a não conformidade.</span><span class="sxs-lookup"><span data-stu-id="9dabb-127">For this example, approve the nonconformance.</span></span> <span data-ttu-id="9dabb-128">Não conformidades aprovadas podem ser associadas às operações relacionadas para registrar o trabalho que é feito como parte do manuseio da não conformidade e, como nesse registro de tarefa, o processamento do manuseio de correção.</span><span class="sxs-lookup"><span data-stu-id="9dabb-128">Approved nonconformances can be associated with related operations to record work that is done as part of the nonconformance handling and, as in this task recording, the processing of correction handling.</span></span>  
3. <span data-ttu-id="9dabb-129">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="9dabb-129">Click Yes.</span></span>

## <a name="create-a-correction-action"></a><span data-ttu-id="9dabb-130">Criar uma ação de correção</span><span class="sxs-lookup"><span data-stu-id="9dabb-130">Create a correction action</span></span>
1. <span data-ttu-id="9dabb-131">Clique em Correções.</span><span class="sxs-lookup"><span data-stu-id="9dabb-131">Click Corrections.</span></span>
2. <span data-ttu-id="9dabb-132">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="9dabb-132">Click New.</span></span>
3. <span data-ttu-id="9dabb-133">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="9dabb-133">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="9dabb-134">No campo Número dos funcionários, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="9dabb-134">In the Personnel number field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="9dabb-135">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="9dabb-135">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="9dabb-136">Clique em Selecionar.</span><span class="sxs-lookup"><span data-stu-id="9dabb-136">Click Select.</span></span>
7. <span data-ttu-id="9dabb-137">Clique em Anexar.</span><span class="sxs-lookup"><span data-stu-id="9dabb-137">Click Attach.</span></span>
    * <span data-ttu-id="9dabb-138">Crie uma nota sobre a correção.</span><span class="sxs-lookup"><span data-stu-id="9dabb-138">Create a note about the correction.</span></span> <span data-ttu-id="9dabb-139">Neste exemplo, a ação é entrar em contato com o fornecedor para discutir o caso não conformidade.</span><span class="sxs-lookup"><span data-stu-id="9dabb-139">For this example, the action is to contact the vendor to discuss the nonconformance case.</span></span>  
8. <span data-ttu-id="9dabb-140">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="9dabb-140">Click New.</span></span>
9. <span data-ttu-id="9dabb-141">Clique em Nota.</span><span class="sxs-lookup"><span data-stu-id="9dabb-141">Click Note.</span></span>
    * <span data-ttu-id="9dabb-142">Observe que, dependendo da configuração do relatório, diferentes tipos de documentos podem ser impressos em relatórios relacionados ao gerenciamento de não conformidades.</span><span class="sxs-lookup"><span data-stu-id="9dabb-142">Note that, depending on the report setup, different document types can be printed on the reports that are related to nonconformance management.</span></span>  
10. <span data-ttu-id="9dabb-143">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="9dabb-143">In the Description field, type a value.</span></span>
11. <span data-ttu-id="9dabb-144">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9dabb-144">Close the page.</span></span>

## <a name="maintain-a-correction"></a><span data-ttu-id="9dabb-145">Manter uma correção</span><span class="sxs-lookup"><span data-stu-id="9dabb-145">Maintain a correction</span></span>
1. <span data-ttu-id="9dabb-146">Clique em Marcar como completo.</span><span class="sxs-lookup"><span data-stu-id="9dabb-146">Click Mark complete.</span></span>
2. <span data-ttu-id="9dabb-147">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="9dabb-147">Click OK.</span></span>
3. <span data-ttu-id="9dabb-148">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9dabb-148">Close the page.</span></span>

## <a name="close-a-nonconformance"></a><span data-ttu-id="9dabb-149">Fechar uma não conformidade</span><span class="sxs-lookup"><span data-stu-id="9dabb-149">Close a nonconformance</span></span>
1. <span data-ttu-id="9dabb-150">Clique em Funções.</span><span class="sxs-lookup"><span data-stu-id="9dabb-150">Click Functions.</span></span>
2. <span data-ttu-id="9dabb-151">Clique em Fechar a não conformidade.</span><span class="sxs-lookup"><span data-stu-id="9dabb-151">Click Close non conformance.</span></span>
3. <span data-ttu-id="9dabb-152">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="9dabb-152">Click Yes.</span></span>
4. <span data-ttu-id="9dabb-153">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9dabb-153">Close the page.</span></span>
5. <span data-ttu-id="9dabb-154">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9dabb-154">Close the page.</span></span>


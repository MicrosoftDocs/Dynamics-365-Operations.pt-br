---
title: Criar e processar uma conformidade
description: Este tópico explica como executar o gerenciamento de não conformidades, com base em uma ordem de qualidade existente.
author: perlynne
manager: tfehr
ms.date: 08/07/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8bf20ed737707b7cf99023e3c78489caf4a68eab
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422447"
---
# <a name="create-and-process-a-conformance"></a><span data-ttu-id="fc28c-103">Criar e processar uma conformidade</span><span class="sxs-lookup"><span data-stu-id="fc28c-103">Create and process a conformance</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fc28c-104">Este tópico explica como executar o gerenciamento de não conformidades, com base em uma ordem de qualidade existente.</span><span class="sxs-lookup"><span data-stu-id="fc28c-104">This topic explains how to perform nonconformance management, based on an existing quality order.</span></span> <span data-ttu-id="fc28c-105">Você pode executar esse registro na empresa de demonstração USMF e pode usar os valores sugeridos.</span><span class="sxs-lookup"><span data-stu-id="fc28c-105">You can run this recording in the USMF demo company and can use the suggested values.</span></span> <span data-ttu-id="fc28c-106">Normalmente, esse procedimento é realizado por um encarregado de qualidade.</span><span class="sxs-lookup"><span data-stu-id="fc28c-106">Typically, this procedure is performed by a quality clerk.</span></span>  <span data-ttu-id="fc28c-107">Como um pré-requisito, siga as instruções em [Inspecionar a qualidade das mercadorias](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md).</span><span class="sxs-lookup"><span data-stu-id="fc28c-107">As a prerequisite, complete the instructions in [Inspect the quality of goods](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md).</span></span> <span data-ttu-id="fc28c-108">Para processar a aprovação de uma não conformidade, o usuário que executa o registro de tarefa deve ter um valor de "Nome" atribuído na página Usuários.</span><span class="sxs-lookup"><span data-stu-id="fc28c-108">To process the approval of a nonconformance, the user who runs the task recording must have a "Name" value assigned on the Users page.</span></span> <span data-ttu-id="fc28c-109">Para usar as notas do documento, o usuário também deve ter o Manuseio de documentos ativado nas opções do usuário.</span><span class="sxs-lookup"><span data-stu-id="fc28c-109">To use the document notes, the user must also have Document handling activated in the user options.</span></span>


## <a name="select-a-quality-order"></a><span data-ttu-id="fc28c-110">Selecione uma ordem de qualidade</span><span class="sxs-lookup"><span data-stu-id="fc28c-110">Select a quality order</span></span>
1. <span data-ttu-id="fc28c-111">No painel de navegação, vá para **Módulos > Gerenciamento de estoque > Tarefas periódicas > Gerenciamento de qualidade > Ordens de qualidade**.</span><span class="sxs-lookup"><span data-stu-id="fc28c-111">In the navigation pane, go to **Modules > Inventory management > Periodic tasks > Quality management > Quality orders**.</span></span>
2. <span data-ttu-id="fc28c-112">Na lista, selecione a ordem de qualidade criada em [Inspecionar a qualidade das mercadorias](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md).</span><span class="sxs-lookup"><span data-stu-id="fc28c-112">In the list, select the quality order that was created in [Inspect the quality of goods](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md).</span></span>  

## <a name="create-a-nonconformance"></a><span data-ttu-id="fc28c-113">Criar uma não conformidade</span><span class="sxs-lookup"><span data-stu-id="fc28c-113">Create a nonconformance</span></span>
1. <span data-ttu-id="fc28c-114">No Painel de Ações, selecione **Consultas**.</span><span class="sxs-lookup"><span data-stu-id="fc28c-114">On the Action Pane, select **Inquiries**.</span></span>
2. <span data-ttu-id="fc28c-115">Selecione **Não conformidades**.</span><span class="sxs-lookup"><span data-stu-id="fc28c-115">Select **Non conformances**.</span></span>
3. <span data-ttu-id="fc28c-116">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="fc28c-116">Select **New**.</span></span>
4. <span data-ttu-id="fc28c-117">No menu suspenso do campo **Tipo de problema**, selecione o problema encontrado durante o processo de inspeção.</span><span class="sxs-lookup"><span data-stu-id="fc28c-117">In the drop-down menu of the **Problem type** field, select the problem that was found during the inspection process.</span></span>  
5. <span data-ttu-id="fc28c-118">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="fc28c-118">Select **OK**.</span></span>

## <a name="approvereject-a-nonconformance"></a><span data-ttu-id="fc28c-119">Aprovar/rejeitar uma não conformidade</span><span class="sxs-lookup"><span data-stu-id="fc28c-119">Approve/reject a nonconformance</span></span>
1. <span data-ttu-id="fc28c-120">Selecione **Funções**.</span><span class="sxs-lookup"><span data-stu-id="fc28c-120">Select **Functions**.</span></span>
2. <span data-ttu-id="fc28c-121">Selecione **Aprovar não conformidade**.</span><span class="sxs-lookup"><span data-stu-id="fc28c-121">Select **Approve non conformance**.</span></span> <span data-ttu-id="fc28c-122">Para esse exemplo, aprove a não conformidade.</span><span class="sxs-lookup"><span data-stu-id="fc28c-122">For this example, approve the nonconformance.</span></span> <span data-ttu-id="fc28c-123">Não conformidades aprovadas podem ser associadas às operações relacionadas para registrar o trabalho que é feito como parte do manuseio da não conformidade e, como neste tópico, o processamento do manuseio de correção.</span><span class="sxs-lookup"><span data-stu-id="fc28c-123">Approved nonconformances can be associated with related operations to record work that is done as part of the nonconformance handling and, as in this topic, the processing of correction handling.</span></span>  
3. <span data-ttu-id="fc28c-124">Selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="fc28c-124">Select **Yes**.</span></span>

## <a name="create-a-correction-action"></a><span data-ttu-id="fc28c-125">Criar uma ação de correção</span><span class="sxs-lookup"><span data-stu-id="fc28c-125">Create a correction action</span></span>
1. <span data-ttu-id="fc28c-126">Selecione **Correções**.</span><span class="sxs-lookup"><span data-stu-id="fc28c-126">Select **Corrections**.</span></span>
2. <span data-ttu-id="fc28c-127">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="fc28c-127">Select **New**.</span></span>
3. <span data-ttu-id="fc28c-128">No campo **Número da equipe** da nova linha, selecione o registro desejado no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="fc28c-128">In the **Personnel number** field of the new row, select the desired record from the drop down menu.</span></span>
4. <span data-ttu-id="fc28c-129">Clique em **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="fc28c-129">Click **Select**.</span></span>
5. <span data-ttu-id="fc28c-130">Selecione **Anexar**.</span><span class="sxs-lookup"><span data-stu-id="fc28c-130">Select **Attach**.</span></span> <span data-ttu-id="fc28c-131">Crie uma nota sobre a correção.</span><span class="sxs-lookup"><span data-stu-id="fc28c-131">Create a note about the correction.</span></span> <span data-ttu-id="fc28c-132">Neste exemplo, a ação é entrar em contato com o fornecedor para discutir o caso não conformidade.</span><span class="sxs-lookup"><span data-stu-id="fc28c-132">For this example, the action is to contact the vendor to discuss the nonconformance case.</span></span>  
6. <span data-ttu-id="fc28c-133">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="fc28c-133">Select **New**.</span></span>
7. <span data-ttu-id="fc28c-134">Selecione **Nota**.</span><span class="sxs-lookup"><span data-stu-id="fc28c-134">Select **Note**.</span></span> <span data-ttu-id="fc28c-135">Dependendo da configuração do relatório, diferentes tipos de documentos podem ser impressos em relatórios relacionados ao gerenciamento de não conformidades.</span><span class="sxs-lookup"><span data-stu-id="fc28c-135">Depending on the report setup, different document types can be printed on the reports that are related to nonconformance management.</span></span>  
8. <span data-ttu-id="fc28c-136">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="fc28c-136">In the **Description** field, type a value.</span></span>
9. <span data-ttu-id="fc28c-137">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="fc28c-137">Close the page.</span></span>

## <a name="maintain-a-correction"></a><span data-ttu-id="fc28c-138">Manter uma correção</span><span class="sxs-lookup"><span data-stu-id="fc28c-138">Maintain a correction</span></span>
1. <span data-ttu-id="fc28c-139">Selecione **Marcar como concluída**.</span><span class="sxs-lookup"><span data-stu-id="fc28c-139">Select **Mark complete**.</span></span>
2. <span data-ttu-id="fc28c-140">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="fc28c-140">Select **OK**.</span></span>
3. <span data-ttu-id="fc28c-141">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="fc28c-141">Close the page.</span></span>

## <a name="close-a-nonconformance"></a><span data-ttu-id="fc28c-142">Fechar uma não conformidade</span><span class="sxs-lookup"><span data-stu-id="fc28c-142">Close a nonconformance</span></span>
1. <span data-ttu-id="fc28c-143">Selecione **Funções**.</span><span class="sxs-lookup"><span data-stu-id="fc28c-143">Select **Functions**.</span></span>
2. <span data-ttu-id="fc28c-144">Selecione **Fechar não conformidade**.</span><span class="sxs-lookup"><span data-stu-id="fc28c-144">Select **Close non conformance**.</span></span>
3. <span data-ttu-id="fc28c-145">Selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="fc28c-145">Select **Yes**.</span></span>
4. <span data-ttu-id="fc28c-146">Feche as páginas.</span><span class="sxs-lookup"><span data-stu-id="fc28c-146">Close the pages.</span></span>

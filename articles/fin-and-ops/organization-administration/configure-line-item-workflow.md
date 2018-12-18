---
title: Configurar fluxos de trabalho de item de linha
description: "Este tópico explica como configurar um elemento do fluxo de trabalho de item de linha."
author: sericks007
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 195833
ms.assetid: 3237347e-71d5-4569-bc9a-0d0fc9410b78
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 3ee5334c87b2b0acae2afa6882feca63e3b9cc8e
ms.openlocfilehash: 66e79389bba4566176330914ace462110cd0aa22
ms.contentlocale: pt-br
ms.lasthandoff: 12/18/2018

---

# <a name="configure-line-item-workflows"></a><span data-ttu-id="f55ff-103">Configurar fluxos de trabalho de item de linha</span><span class="sxs-lookup"><span data-stu-id="f55ff-103">Configure line-item workflows</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f55ff-104">Este tópico explica como configurar um elemento do fluxo de trabalho de item de linha.</span><span class="sxs-lookup"><span data-stu-id="f55ff-104">This topic explains how to configure a line-item workflow element.</span></span>

<span data-ttu-id="f55ff-105">Para configurar um elemento do fluxo de trabalho de item de linha, no editor de fluxo de trabalho, clique com o botão direito do mouse no elemento **Propriedades** e clique em **Propriedades** para abrir a página.</span><span class="sxs-lookup"><span data-stu-id="f55ff-105">To configure a line-item workflow element, in the workflow editor, right-click the element, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="f55ff-106">Então use os procedimentos a seguir para configurar as propriedades de elemento do fluxo de trabalho de item de linha.</span><span class="sxs-lookup"><span data-stu-id="f55ff-106">Then use the following procedures to configure the properties of the line-item workflow element.</span></span>

## <a name="name-the-line-item-workflow-element"></a><span data-ttu-id="f55ff-107">Forneça um nome ao elemento do fluxo de trabalho de item de linha.</span><span class="sxs-lookup"><span data-stu-id="f55ff-107">Name the line-item workflow element</span></span>

<span data-ttu-id="f55ff-108">Siga estas etapas para inserir um nome para o elemento do fluxo de trabalho de item de linha.</span><span class="sxs-lookup"><span data-stu-id="f55ff-108">Follow these steps to enter a name for the line-item workflow element.</span></span>

1. <span data-ttu-id="f55ff-109">No painel esquerdo, clique em **Configurações Básicas**.</span><span class="sxs-lookup"><span data-stu-id="f55ff-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="f55ff-110">No campo **Nome**, insira um nome exclusivo para o elemento do fluxo de trabalho de item de linha.</span><span class="sxs-lookup"><span data-stu-id="f55ff-110">In the **Name** field, enter a unique name for the line-item workflow element.</span></span>

## <a name="specify-whether-the-same-workflow-is-used-to-process-all-line-items"></a><span data-ttu-id="f55ff-111">Especifique se o mesmo fluxo de trabalho será usado para processar todos os itens de linha.</span><span class="sxs-lookup"><span data-stu-id="f55ff-111">Specify whether the same workflow is used to process all line items</span></span>

<span data-ttu-id="f55ff-112">Siga estas etapas para especificar se o mesmo fluxo de trabalho será usado para processar todos os itens de linha em um documento.</span><span class="sxs-lookup"><span data-stu-id="f55ff-112">Follow these steps to specify whether the same workflow is used to process all the line items on a document.</span></span>

1. <span data-ttu-id="f55ff-113">No painel esquerdo, clique em **Configurações Básicas**.</span><span class="sxs-lookup"><span data-stu-id="f55ff-113">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="f55ff-114">Se o mesmo fluxo de trabalho processar todas as linhas de item em um documento, clique em **Invocar um único fluxo de trabalho para todos os itens de linha**.</span><span class="sxs-lookup"><span data-stu-id="f55ff-114">If the same workflow should process all the line items on a document, click **Invoke a single workflow for all line-items**.</span></span> <span data-ttu-id="f55ff-115">Em seguida, selecione o fluxo de trabalho a ser usado para processar os itens de linha.</span><span class="sxs-lookup"><span data-stu-id="f55ff-115">Then select the workflow to use to process the line items.</span></span>
3. <span data-ttu-id="f55ff-116">Se um fluxo de trabalho específico processar as linhas de item que atenderem um conjunto específico de condições, clique em **Invocar um fluxo de trabalho para cada item de linha**.</span><span class="sxs-lookup"><span data-stu-id="f55ff-116">If a specific workflow should process line items that meet a specific set of conditions, click **Invoke a workflow for each line-item**.</span></span> <span data-ttu-id="f55ff-117">Para definir o conjunto de condições, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="f55ff-117">Then follow these steps to define the set of conditions:</span></span>

    1. <span data-ttu-id="f55ff-118">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="f55ff-118">Click **Add**.</span></span>
    2. <span data-ttu-id="f55ff-119">Selecione a condição na tabela.</span><span class="sxs-lookup"><span data-stu-id="f55ff-119">Select the condition in the table.</span></span>
    3. <span data-ttu-id="f55ff-120">Na guia **Nome da condição**, insira um nome para o conjunto de condições que você está configurando.</span><span class="sxs-lookup"><span data-stu-id="f55ff-120">On the **Condition name** tab, enter a name for the set of conditions that you're defining.</span></span>
    4. <span data-ttu-id="f55ff-121">Clique em **Adicionar condição** para inserir uma condição.</span><span class="sxs-lookup"><span data-stu-id="f55ff-121">Click **Add condition** to enter a condition.</span></span>
    5. <span data-ttu-id="f55ff-122">Insira quaisquer condições adicionais necessárias.</span><span class="sxs-lookup"><span data-stu-id="f55ff-122">Enter any additional conditions that are required.</span></span>
    6. <span data-ttu-id="f55ff-123">Para verificar se o conjunto de condições que você inseriu está configurado corretamente, clique em **Teste**.</span><span class="sxs-lookup"><span data-stu-id="f55ff-123">To verify that the set of conditions that you entered is configured correctly, click **Test**.</span></span> <span data-ttu-id="f55ff-124">Na página **Testar condição de fluxo de trabalho**, na área **Validar condição**, selecione um registro e clique em **Teste**.</span><span class="sxs-lookup"><span data-stu-id="f55ff-124">On the **Test workflow condition** page, in the **Validate condition** area, select a record, and then click **Test**.</span></span> <span data-ttu-id="f55ff-125">O sistema avaliará o registro para determinar se ele atende às condições definidas.</span><span class="sxs-lookup"><span data-stu-id="f55ff-125">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span> <span data-ttu-id="f55ff-126">Clique em **OK** ou **Cancelar** para retornar à página **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="f55ff-126">Click **OK** or **Cancel** to return to the **Properties** page.</span></span>

    <span data-ttu-id="f55ff-127">Na guia **Fluxo de trabalho**, selecione o fluxo de trabalho no fluxo de trabalho a ser usado para processar as linhas de item que atenderem o conjunto de condições definidas.</span><span class="sxs-lookup"><span data-stu-id="f55ff-127">On the **Workflow** tab, select the workflow select the workflow to use to process line items that meet the set of conditions that you defined.</span></span>


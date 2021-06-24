---
title: Melhorar o modelo de previsão (versão preliminar)
description: Este tópico descreve recursos que podem ser usados para melhorar o desempenho de modelos de previsão.
author: ShivamPandey-msft
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 184a1cb5d3851e26b41340b711c51ef38e06eb53
ms.sourcegitcommit: ebcd9019cbb88a7f2afd9e701812e222566fd43d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "6186633"
---
# <a name="improve-the-prediction-model-preview"></a><span data-ttu-id="2bbd9-103">Melhorar o modelo de previsão (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="2bbd9-103">Improve the prediction model (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="2bbd9-104">Este tópico descreve recursos que podem ser usados para melhorar o desempenho de modelos de previsão.</span><span class="sxs-lookup"><span data-stu-id="2bbd9-104">This topic describes features that you can use to improve the performance of prediction models.</span></span> <span data-ttu-id="2bbd9-105">Comece a melhorar seu modelo no espaço de trabalho **Previsões de pagamento de cliente** no Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="2bbd9-105">You start to improve your model in the **Customer payment predictions** workspace in Microsoft Dynamics 365 Finance.</span></span> <span data-ttu-id="2bbd9-106">As etapas de melhoria são concluídas no AI Builder.</span><span class="sxs-lookup"><span data-stu-id="2bbd9-106">The improvement steps are then completed in AI Builder.</span></span>

## <a name="select-historical-outcomes"></a><span data-ttu-id="2bbd9-107">Selecionar resultados históricos</span><span class="sxs-lookup"><span data-stu-id="2bbd9-107">Select historical outcomes</span></span>

<span data-ttu-id="2bbd9-108">Primeiro, selecione um ou mais dos três resultados possíveis para faturas: **No prazo**, **Atrasado** e **Muito atrasado**.</span><span class="sxs-lookup"><span data-stu-id="2bbd9-108">You first select one or more of the three possible outcomes for invoices: **On time**, **Late**, and **Very late**.</span></span> <span data-ttu-id="2bbd9-109">Todos os três resultados devem ser selecionados.</span><span class="sxs-lookup"><span data-stu-id="2bbd9-109">All three outcomes should be selected.</span></span> <span data-ttu-id="2bbd9-110">Se você desmarcar a seleção de qualquer um dos resultados, as faturas serão filtradas do processo de treinamento e a precisão da previsão será reduzida.</span><span class="sxs-lookup"><span data-stu-id="2bbd9-110">If you clear the selection of any of the outcomes, invoices will be filtered out of the training process and the accuracy of the prediction will be reduced.</span></span>

<span data-ttu-id="2bbd9-111">[![Confirmação de resultados](./media/confirm-3-outcomes.png)](./media/confirm-3-outcomes.png)</span><span class="sxs-lookup"><span data-stu-id="2bbd9-111">[![Confirming outcomes](./media/confirm-3-outcomes.png)](./media/confirm-3-outcomes.png)</span></span>

<span data-ttu-id="2bbd9-112">Se a sua organização exigir apenas dois resultados, altere os limites **Atrasado** e **Muito atrasado** para 0 (zero) dias.</span><span class="sxs-lookup"><span data-stu-id="2bbd9-112">If your organization requires only two outcomes, change the **Late** and **Very late** thresholds to 0 (zero) days.</span></span> <span data-ttu-id="2bbd9-113">Dessa forma, você efetivamente recolhe a predição a um estado binário de **No prazo** ou **Atrasado**.</span><span class="sxs-lookup"><span data-stu-id="2bbd9-113">In this way, you effectively collapse the prediction to a binary state of **On time** or **Late**.</span></span>

## <a name="select-fields"></a><span data-ttu-id="2bbd9-114">Selecionar campos</span><span class="sxs-lookup"><span data-stu-id="2bbd9-114">Select fields</span></span>

<span data-ttu-id="2bbd9-115">Quando estiver selecionando campos a serem incluídos no modelo, lembre-se de que a lista inclui todos os campos disponíveis na tabela do Microsoft Dataverse mapeada para os dados no Azure Data Lake.</span><span class="sxs-lookup"><span data-stu-id="2bbd9-115">When you're selecting fields to include in the model, be aware that the list includes all available fields in the Microsoft Dataverse table that is mapped to the data in the Azure data lake.</span></span> <span data-ttu-id="2bbd9-116">Alguns desses campos **não** devem ser selecionados.</span><span class="sxs-lookup"><span data-stu-id="2bbd9-116">Some of these fields should **not** be selected.</span></span> <span data-ttu-id="2bbd9-117">Os campos que não devem ser selecionados caem em uma das três categorias:</span><span class="sxs-lookup"><span data-stu-id="2bbd9-117">The fields that should not be selected fall into one of three categories:</span></span>

- <span data-ttu-id="2bbd9-118">O campo é necessário para a tabela do Dataverse, mas não há dados de backup para ele no data lake.</span><span class="sxs-lookup"><span data-stu-id="2bbd9-118">The field is required for the Dataverse table, but there is no backing data for it in the data lake.</span></span>
- <span data-ttu-id="2bbd9-119">O campo é uma ID e, portanto, não faz sentido para um recurso de aprendizado de máquina.</span><span class="sxs-lookup"><span data-stu-id="2bbd9-119">The field is an ID and therefore doesn't make sense for a machine learning feature.</span></span>
- <span data-ttu-id="2bbd9-120">O campo representa informações que não estarão disponíveis durante a previsão.</span><span class="sxs-lookup"><span data-stu-id="2bbd9-120">The field represents information that won't be available during prediction.</span></span>

<span data-ttu-id="2bbd9-121">As seções a seguir mostram os campos disponíveis para as entidades de fatura e de cliente e listam os campos que **não** devem ser selecionados para treinamento.</span><span class="sxs-lookup"><span data-stu-id="2bbd9-121">The following sections show the fields that are available for the invoice and customer entities, and list the fields that should **not** be selected for training.</span></span> <span data-ttu-id="2bbd9-122">A categoria especificada para cada um desses campos se refere às categorias na lista anterior.</span><span class="sxs-lookup"><span data-stu-id="2bbd9-122">The category that is specified for each of those fields refers to the categories in the preceding list.</span></span>
 
### <a name="invoice-dataverse-table"></a><span data-ttu-id="2bbd9-123">Tabela de faturas do Dataverse</span><span class="sxs-lookup"><span data-stu-id="2bbd9-123">Invoice Dataverse table</span></span>

<span data-ttu-id="2bbd9-124">A ilustração a seguir mostra os campos disponíveis para a tabela de fatura.</span><span class="sxs-lookup"><span data-stu-id="2bbd9-124">The following illustration shows the fields that are available for the invoice table.</span></span>

<span data-ttu-id="2bbd9-125">[![Campos disponíveis para a tabela de fatura](./media/available-fields.png)](./media/available-fields.png)</span><span class="sxs-lookup"><span data-stu-id="2bbd9-125">[![Available fields for the invoice table](./media/available-fields.png)](./media/available-fields.png)</span></span>

<span data-ttu-id="2bbd9-126">Os campos a seguir não devem ser selecionados para treinamento:</span><span class="sxs-lookup"><span data-stu-id="2bbd9-126">The following fields should not be selected for training:</span></span>

- <span data-ttu-id="2bbd9-127">**Conta de Fatura** (categoria 2)</span><span class="sxs-lookup"><span data-stu-id="2bbd9-127">**Invoice Account** (category 2)</span></span>
- <span data-ttu-id="2bbd9-128">**Está fechada** (categoria 3) – este campo é usado para filtrar faturas para treinamento (fechada) e de previsão (não fechada).</span><span class="sxs-lookup"><span data-stu-id="2bbd9-128">**Is closed** (category 3) – This field is used to filter invoices for training (closed) and prediction (not closed).</span></span>
- <span data-ttu-id="2bbd9-129">**Nome** (categoria 1)</span><span class="sxs-lookup"><span data-stu-id="2bbd9-129">**Name** (category 1)</span></span>
- <span data-ttu-id="2bbd9-130">**Id de Origem** (categoria 2)</span><span class="sxs-lookup"><span data-stu-id="2bbd9-130">**Source Id** (category 2)</span></span>
- <span data-ttu-id="2bbd9-131">**Registro de origem** (categoria 2)</span><span class="sxs-lookup"><span data-stu-id="2bbd9-131">**Source record** (category 2)</span></span>
- <span data-ttu-id="2bbd9-132">**Tabela de origem** (categoria 2)</span><span class="sxs-lookup"><span data-stu-id="2bbd9-132">**Source table** (category 2)</span></span>

### <a name="customer-dataverse-table"></a><span data-ttu-id="2bbd9-133">Tabela de clientes do Dataverse</span><span class="sxs-lookup"><span data-stu-id="2bbd9-133">Customer Dataverse table</span></span>

<span data-ttu-id="2bbd9-134">A ilustração a seguir mostra os campos disponíveis para a tabela de clientes.</span><span class="sxs-lookup"><span data-stu-id="2bbd9-134">The following illustration shows the fields that are available for the customer table.</span></span>

<span data-ttu-id="2bbd9-135">[![Campos disponíveis para a tabela de clientes](./media/related-entities.png)](./media/related-entities.png)</span><span class="sxs-lookup"><span data-stu-id="2bbd9-135">[![Available fields for the customer table](./media/related-entities.png)](./media/related-entities.png)</span></span>

<span data-ttu-id="2bbd9-136">O campo a seguir não deve ser selecionados para treinamento:</span><span class="sxs-lookup"><span data-stu-id="2bbd9-136">The following field should not be selected for training:</span></span>

- <span data-ttu-id="2bbd9-137">**Chave Exclusiva de Linha** (categoria 2)</span><span class="sxs-lookup"><span data-stu-id="2bbd9-137">**Row Unique Key** (category 2)</span></span>

## <a name="filters"></a><span data-ttu-id="2bbd9-138">Filtros</span><span class="sxs-lookup"><span data-stu-id="2bbd9-138">Filters</span></span>

<span data-ttu-id="2bbd9-139">No momento, os filtros não dão suporte ao cenário Previsão de pagamento do cliente.</span><span class="sxs-lookup"><span data-stu-id="2bbd9-139">The filters don't currently support the Customer payment predictor scenario.</span></span> <span data-ttu-id="2bbd9-140">Portanto, selecione **Ignorar esta etapa** e prossiga para a página de resumo.</span><span class="sxs-lookup"><span data-stu-id="2bbd9-140">Therefore, select **Skip this step**, and continue to the summary page.</span></span>

<span data-ttu-id="2bbd9-141">[![Modelo de foco com filtros](./media/focus-model-with-filters.png)](./media/focus-model-with-filters.png)</span><span class="sxs-lookup"><span data-stu-id="2bbd9-141">[![Focus model with filters](./media/focus-model-with-filters.png)](./media/focus-model-with-filters.png)</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

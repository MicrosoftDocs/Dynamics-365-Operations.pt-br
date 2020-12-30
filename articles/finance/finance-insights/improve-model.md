---
title: Melhorar o modelo de previsão (versão preliminar)
description: Este tópico descreve recursos que podem ser usados para melhorar o desempenho de modelos de previsão.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 23c9062dcc13951792306c955b54cae6f656fec5
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646070"
---
# <a name="improve-the-prediction-model-preview"></a><span data-ttu-id="844ba-103">Melhorar o modelo de previsão (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="844ba-103">Improve the prediction model (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="844ba-104">Este tópico descreve recursos que podem ser usados para melhorar o desempenho de modelos de previsão.</span><span class="sxs-lookup"><span data-stu-id="844ba-104">This topic describes features that you can use to improve the performance of prediction models.</span></span> <span data-ttu-id="844ba-105">Comece a melhorar seu modelo no espaço de trabalho **Previsões de pagamento de cliente** no Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="844ba-105">You start to improve your model in the **Customer payment predictions** workspace in Microsoft Dynamics 365 Finance.</span></span> <span data-ttu-id="844ba-106">As etapas de melhoria são concluídas no AI Builder.</span><span class="sxs-lookup"><span data-stu-id="844ba-106">The improvement steps are then completed in AI Builder.</span></span>

## <a name="select-historical-outcomes"></a><span data-ttu-id="844ba-107">Selecionar resultados históricos</span><span class="sxs-lookup"><span data-stu-id="844ba-107">Select historical outcomes</span></span>

<span data-ttu-id="844ba-108">Primeiro, selecione um ou mais dos três resultados possíveis para faturas: **No prazo**, **Atrasado** e **Muito atrasado**.</span><span class="sxs-lookup"><span data-stu-id="844ba-108">You first select one or more of the three possible outcomes for invoices: **On time**, **Late**, and **Very late**.</span></span> <span data-ttu-id="844ba-109">Todos os três resultados devem ser selecionados.</span><span class="sxs-lookup"><span data-stu-id="844ba-109">All three outcomes should be selected.</span></span> <span data-ttu-id="844ba-110">Se você desmarcar a seleção de qualquer um dos resultados, as faturas serão filtradas do processo de treinamento e a precisão da previsão será reduzida.</span><span class="sxs-lookup"><span data-stu-id="844ba-110">If you clear the selection of any of the outcomes, invoices will be filtered out of the training process and the accuracy of the prediction will be reduced.</span></span>

<span data-ttu-id="844ba-111">[![Confirmação de resultados](./media/confirm-3-outcomes.png)](./media/confirm-3-outcomes.png)</span><span class="sxs-lookup"><span data-stu-id="844ba-111">[![Confirming outcomes](./media/confirm-3-outcomes.png)](./media/confirm-3-outcomes.png)</span></span>

<span data-ttu-id="844ba-112">Se a sua organização exigir apenas dois resultados, altere os limites **Atrasado** e **Muito atrasado** para 0 (zero) dias.</span><span class="sxs-lookup"><span data-stu-id="844ba-112">If your organization requires only two outcomes, change the **Late** and **Very late** thresholds to 0 (zero) days.</span></span> <span data-ttu-id="844ba-113">Dessa forma, você efetivamente recolhe a predição a um estado binário de **No prazo** ou **Atrasado**.</span><span class="sxs-lookup"><span data-stu-id="844ba-113">In this way, you effectively collapse the prediction to a binary state of **On time** or **Late**.</span></span>

## <a name="select-fields"></a><span data-ttu-id="844ba-114">Selecionar campos</span><span class="sxs-lookup"><span data-stu-id="844ba-114">Select fields</span></span>

<span data-ttu-id="844ba-115">Quando estiver selecionando os campos a serem incluídos no modelo, lembre-se de que a lista inclui todos os campos disponíveis na entidade do Common Data Service mapeada para os dados no Azure Data Lake.</span><span class="sxs-lookup"><span data-stu-id="844ba-115">When you're selecting fields to include in the model, be aware that the list includes all available fields in the Common Data Service entity that is mapped to the data in the Azure data lake.</span></span> <span data-ttu-id="844ba-116">Alguns desses campos **não** devem ser selecionados.</span><span class="sxs-lookup"><span data-stu-id="844ba-116">Some of these fields should **not** be selected.</span></span> <span data-ttu-id="844ba-117">Os campos que não devem ser selecionados caem em uma das três categorias:</span><span class="sxs-lookup"><span data-stu-id="844ba-117">The fields that should not be selected fall into one of three categories:</span></span>

- <span data-ttu-id="844ba-118">O campo é necessário para a entidade do Common Data Service, mas não há dados de backup para ele no data lake.</span><span class="sxs-lookup"><span data-stu-id="844ba-118">The field is required for the Common Data Service entity, but there is no backing data for it in the data lake.</span></span>
- <span data-ttu-id="844ba-119">O campo é uma ID e, portanto, não faz sentido para um recurso de aprendizado de máquina.</span><span class="sxs-lookup"><span data-stu-id="844ba-119">The field is an ID and therefore doesn't make sense for a machine learning feature.</span></span>
- <span data-ttu-id="844ba-120">O campo representa informações que não estarão disponíveis durante a previsão.</span><span class="sxs-lookup"><span data-stu-id="844ba-120">The field represents information that won't be available during prediction.</span></span>

<span data-ttu-id="844ba-121">As seções a seguir mostram os campos disponíveis para as entidades de fatura e de cliente e listam os campos que **não** devem ser selecionados para treinamento.</span><span class="sxs-lookup"><span data-stu-id="844ba-121">The following sections show the fields that are available for the invoice and customer entities, and list the fields that should **not** be selected for training.</span></span> <span data-ttu-id="844ba-122">A categoria especificada para cada um desses campos se refere às categorias na lista anterior.</span><span class="sxs-lookup"><span data-stu-id="844ba-122">The category that is specified for each of those fields refers to the categories in the preceding list.</span></span>
 
### <a name="invoice-common-data-model-entity"></a><span data-ttu-id="844ba-123">Entidade de fatura do Common Data Model</span><span class="sxs-lookup"><span data-stu-id="844ba-123">Invoice Common Data Model entity</span></span>

<span data-ttu-id="844ba-124">A ilustração a seguir mostra os campos disponíveis para a entidade de fatura.</span><span class="sxs-lookup"><span data-stu-id="844ba-124">The following illustration shows the fields that are available for the invoice entity.</span></span>

<span data-ttu-id="844ba-125">[![Campos disponíveis para a entidade de fatura](./media/available-fields.png)](./media/available-fields.png)</span><span class="sxs-lookup"><span data-stu-id="844ba-125">[![Available fields for the invoice entity](./media/available-fields.png)](./media/available-fields.png)</span></span>

<span data-ttu-id="844ba-126">Os campos a seguir não devem ser selecionados para treinamento:</span><span class="sxs-lookup"><span data-stu-id="844ba-126">The following fields should not be selected for training:</span></span>

- <span data-ttu-id="844ba-127">**Conta de Fatura** (categoria 2)</span><span class="sxs-lookup"><span data-stu-id="844ba-127">**Invoice Account** (category 2)</span></span>
- <span data-ttu-id="844ba-128">**Está fechada** (categoria 3) – este campo é usado para filtrar faturas para treinamento (fechada) e de previsão (não fechada).</span><span class="sxs-lookup"><span data-stu-id="844ba-128">**Is closed** (category 3) – This field is used to filter invoices for training (closed) and prediction (not closed).</span></span>
- <span data-ttu-id="844ba-129">**Nome** (categoria 1)</span><span class="sxs-lookup"><span data-stu-id="844ba-129">**Name** (category 1)</span></span>
- <span data-ttu-id="844ba-130">**Id de Origem** (categoria 2)</span><span class="sxs-lookup"><span data-stu-id="844ba-130">**Source Id** (category 2)</span></span>
- <span data-ttu-id="844ba-131">**Registro de origem** (categoria 2)</span><span class="sxs-lookup"><span data-stu-id="844ba-131">**Source record** (category 2)</span></span>
- <span data-ttu-id="844ba-132">**Tabela de origem** (categoria 2)</span><span class="sxs-lookup"><span data-stu-id="844ba-132">**Source table** (category 2)</span></span>

### <a name="customer-common-data-model-entity"></a><span data-ttu-id="844ba-133">Entidade de cliente do Common Data Model</span><span class="sxs-lookup"><span data-stu-id="844ba-133">Customer Common Data Model entity</span></span>

<span data-ttu-id="844ba-134">A ilustração a seguir mostra os campos disponíveis para a entidade de cliente.</span><span class="sxs-lookup"><span data-stu-id="844ba-134">The following illustration shows the fields that are available for the customer entity.</span></span>

<span data-ttu-id="844ba-135">[![Campos disponíveis para a entidade de cliente](./media/related-entities.png)](./media/related-entities.png)</span><span class="sxs-lookup"><span data-stu-id="844ba-135">[![Available fields for the customer entity](./media/related-entities.png)](./media/related-entities.png)</span></span>

<span data-ttu-id="844ba-136">O campo a seguir não deve ser selecionados para treinamento:</span><span class="sxs-lookup"><span data-stu-id="844ba-136">The following field should not be selected for training:</span></span>

- <span data-ttu-id="844ba-137">**Chave Exclusiva de Linha** (categoria 2)</span><span class="sxs-lookup"><span data-stu-id="844ba-137">**Row Unique Key** (category 2)</span></span>

## <a name="filters"></a><span data-ttu-id="844ba-138">Filtros</span><span class="sxs-lookup"><span data-stu-id="844ba-138">Filters</span></span>

<span data-ttu-id="844ba-139">No momento, os filtros não dão suporte ao cenário Previsão de pagamento do cliente.</span><span class="sxs-lookup"><span data-stu-id="844ba-139">The filters don't currently support the Customer payment predictor scenario.</span></span> <span data-ttu-id="844ba-140">Portanto, selecione **Ignorar esta etapa** e prossiga para a página de resumo.</span><span class="sxs-lookup"><span data-stu-id="844ba-140">Therefore, select **Skip this step**, and continue to the summary page.</span></span>

<span data-ttu-id="844ba-141">[![Modelo de foco com filtros](./media/focus-model-with-filters.png)](./media/focus-model-with-filters.png)</span><span class="sxs-lookup"><span data-stu-id="844ba-141">[![Focus model with filters](./media/focus-model-with-filters.png)](./media/focus-model-with-filters.png)</span></span>

#### <a name="privacy-notice"></a><span data-ttu-id="844ba-142">Aviso de privacidade</span><span class="sxs-lookup"><span data-stu-id="844ba-142">Privacy notice</span></span>
<span data-ttu-id="844ba-143">As versões prévias (1) podem utilizar menos medidas de privacidade e segurança que o serviço do Dynamics 365 Finance and Operations, (2) não estão incluídas no contrato de nível de serviço (SLA) desse serviço, (3) não devem ser usadas para processar dados pessoais ou outros dados sujeitos a requisitos de conformidade legais ou regulatórios e (4) têm suporte limitado.</span><span class="sxs-lookup"><span data-stu-id="844ba-143">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>

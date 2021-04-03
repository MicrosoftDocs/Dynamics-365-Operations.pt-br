---
title: Média móvel, sequência de custos de fallback
description: Este tópico fornece informações sobre sequências de custos de fallback para cálculos de média de movimentos no Microsoft Dynamics 365 Supply Chain Management.
author: AndersGirke
manager: tfehr
ms.date: 03/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-03-25
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 1f5b1307f039bb9e921d50aed411b3dc603ada65
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263605"
---
# <a name="moving-average-fallback-cost-sequence"></a><span data-ttu-id="8e9f2-103">Média móvel, sequência de custos de fallback</span><span class="sxs-lookup"><span data-stu-id="8e9f2-103">Moving average fallback cost sequence</span></span>

<span data-ttu-id="8e9f2-104">Uma maneira de calcular o custo do seu estoque é usando uma _média de movimentos_.</span><span class="sxs-lookup"><span data-stu-id="8e9f2-104">One way that you can calculate the cost of your inventory is by using a _moving average_.</span></span> <span data-ttu-id="8e9f2-105">Até três valores de custo podem ser associados a cada item de estoque:</span><span class="sxs-lookup"><span data-stu-id="8e9f2-105">Up to three cost values can be associated with each inventory item:</span></span>

- <span data-ttu-id="8e9f2-106">**Problema mais recente** – O custo do problema mais recente atribuído antes de o estoque ficar negativo</span><span class="sxs-lookup"><span data-stu-id="8e9f2-106">**Last issue** – The last issue cost that was assigned before inventory went negative</span></span>
- <span data-ttu-id="8e9f2-107">**Custo ativo** – O custo mais recente que foi ativado em uma versão de custo</span><span class="sxs-lookup"><span data-stu-id="8e9f2-107">**Active cost** – The latest cost that was activated in a costing version</span></span>
- <span data-ttu-id="8e9f2-108">**Preço de item** – O custo especificado para o produto lançado</span><span class="sxs-lookup"><span data-stu-id="8e9f2-108">**Item price** – The cost that is specified for the released product</span></span>

<span data-ttu-id="8e9f2-109">Para determinar quais desses valores de custo devem ser usados nos cálculos da média de movimentos, o sistema usa uma _sequência de custos de fallback_ para estabelecer a ordem de preferência dos valores.</span><span class="sxs-lookup"><span data-stu-id="8e9f2-109">To determine which of these cost values should be used in moving average calculations, the system uses a _fallback cost sequence_ to establish the order of preference for the values.</span></span> <span data-ttu-id="8e9f2-110">Se o valor do custo preferido não estiver disponível, o sistema utilizará o próximo valor preferencial e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="8e9f2-110">If the preferred cost value isn't available, the system uses the next-preferred value, and so on.</span></span>

<span data-ttu-id="8e9f2-111">Nas versões anteriores do Microsoft Dynamics 365 Supply Chain Management, o sistema usava uma sequência de custos de fallback fixa (_Problema mais recente – Custo ativo – Preço de item_).</span><span class="sxs-lookup"><span data-stu-id="8e9f2-111">In previous versions of Microsoft Dynamics 365 Supply Chain Management, the system used a fixed fallback cost sequence (_Last issue – Active cost – Item price_).</span></span> <span data-ttu-id="8e9f2-112">Na versão 10.0.11, essa sequência ainda é a sequência padrão.</span><span class="sxs-lookup"><span data-stu-id="8e9f2-112">In version 10.0.11, this sequence is still the default sequence.</span></span> <span data-ttu-id="8e9f2-113">Entretanto, você também poderá ativar um recurso que permite selecionar entre três sequências de custos de fallback disponíveis.</span><span class="sxs-lookup"><span data-stu-id="8e9f2-113">However, you can also turn on a feature that lets you select among three available fallback cost sequences.</span></span> <span data-ttu-id="8e9f2-114">Esse recurso pode ser especialmente útil para organizações que usam regularmente valores negativos de estoque.</span><span class="sxs-lookup"><span data-stu-id="8e9f2-114">This feature can be especially useful for organizations that regularly use negative inventory values.</span></span>

<span data-ttu-id="8e9f2-115">Para disponibilizar o seletor para a sequência de custos de fallback, você (ou um administrador) deve usar [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para ativar o recurso chamado _Média móvel, sequência de custos de fallback_.</span><span class="sxs-lookup"><span data-stu-id="8e9f2-115">To make the selector for the fallback cost sequence available, you (or an admin) must use [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) to turn on the feature that is named _Moving average fallback cost sequence_.</span></span>

<span data-ttu-id="8e9f2-116">Para selecionar a sequência de custos de fallback para os cálculos de média de movimentos, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="8e9f2-116">To select the fallback cost sequence for moving average calculations, follow these steps.</span></span>

1. <span data-ttu-id="8e9f2-117">Abra a página **Parâmetros**.</span><span class="sxs-lookup"><span data-stu-id="8e9f2-117">Open the **Parameters** page.</span></span>
2. <span data-ttu-id="8e9f2-118">Na guia **Contabilidade de estoque**, na seção **Média de movimentos**, defina o campo **Sequência de custos de fallback** como um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="8e9f2-118">On the **Inventory accounting** tab, in the **Moving average** section, set the **Fallback cost sequence** field to one of the following values:</span></span>

    - <span data-ttu-id="8e9f2-119">**Problema mais recente – Custo ativo – Preço de item** – Esta sequência é a sequência padrão.</span><span class="sxs-lookup"><span data-stu-id="8e9f2-119">**Last issue – Active cost – Item price** – This sequence is the default sequence.</span></span> <span data-ttu-id="8e9f2-120">É a mesma sequência usada se o recurso _Média móvel, sequência de custos de fallback_ não estiver ativado.</span><span class="sxs-lookup"><span data-stu-id="8e9f2-120">It's the same sequence that is used if the _Moving average fallback cost sequence_ feature isn't turned on.</span></span>
    - <span data-ttu-id="8e9f2-121">**Custo ativo – Problema mais recente**</span><span class="sxs-lookup"><span data-stu-id="8e9f2-121">**Active cost – Last issue**</span></span>
    - <span data-ttu-id="8e9f2-122">**Custo ativo – Preço de item** – As organizações podem enfrentar problemas de desempenho se usarem processos de negócios em que o estoque fica negativo regularmente e, ao mesmo tempo, o volume de transações é alto.</span><span class="sxs-lookup"><span data-stu-id="8e9f2-122">**Active cost – Item price** – Organizations might experience performance issues if they use business processes where inventory regularly goes negative and, at the same time, the transaction volume is high.</span></span> <span data-ttu-id="8e9f2-123">Essa configuração pode ajudar a mitigar esses problemas de desempenho.</span><span class="sxs-lookup"><span data-stu-id="8e9f2-123">This setting can help mitigate those performance issues.</span></span>

<span data-ttu-id="8e9f2-124">![Parâmetros de contabilidade de estoque](media/inventory-accounting-parameters.png "Parâmetros de contabilidade de estoque")</span><span class="sxs-lookup"><span data-stu-id="8e9f2-124">![Inventory accounting parameters](media/inventory-accounting-parameters.png "Inventory accounting parameters")</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
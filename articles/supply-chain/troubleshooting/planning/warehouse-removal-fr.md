---
title: Não é possível remover a dimensão de previsão de demanda do depósito das linhas de previsão
description: Não é possível remover a dimensão de previsão de demanda do depósito das linhas de previsão.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ForecastSales
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6b643c4fe51ae6ce73b34ab81d4e458dcd5032df
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026272"
---
# <a name="you-cant-remove-the-warehouse-demand-forecast-dimension-from-forecast-lines"></a><span data-ttu-id="03adc-103">Não é possível remover a dimensão de previsão de demanda do depósito das linhas de previsão</span><span class="sxs-lookup"><span data-stu-id="03adc-103">You can't remove the Warehouse demand forecast dimension from forecast lines</span></span>

<span data-ttu-id="03adc-104">Número de KB: 4614408</span><span class="sxs-lookup"><span data-stu-id="03adc-104">KB number: 4614408</span></span>

## <a name="symptoms"></a><span data-ttu-id="03adc-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="03adc-105">Symptoms</span></span>

<span data-ttu-id="03adc-106">Esse problema ocorre quando a dimensão **Depósito** não é atribuída na guia **Dimensões de previsão** da página **Previsão de demanda**.</span><span class="sxs-lookup"><span data-stu-id="03adc-106">This issue occurs when the **Warehouse** dimension isn't assigned on the **Forecast dimensions** tab of the **Demand forecasting parameter** page.</span></span> <span data-ttu-id="03adc-107">No entanto, a coluna **Depósito** é exibida na pagina **Previsão de demanda** (**Planejamento mestre \> Previsão \> Entidade de previsão manual \> Linhas de previsão de demanda**).</span><span class="sxs-lookup"><span data-stu-id="03adc-107">Nevertheless, the **Warehouse** column is shown on the **Demand forecast** page (**Master planning \> Forecasting \> Manual forecast entity \> Demand forecast lines**).</span></span>

## <a name="resolution"></a><span data-ttu-id="03adc-108">Resolução</span><span class="sxs-lookup"><span data-stu-id="03adc-108">Resolution</span></span>

<span data-ttu-id="03adc-109">As configurações na guia **Dimensões de previsão** da página **Parâmetro de previsão de demanda** não afetam a página **Previsão de demanda**.</span><span class="sxs-lookup"><span data-stu-id="03adc-109">The settings on the **Forecast dimensions** tab of the **Demand forecasting parameter** page don't affect the **Demand forecast** page.</span></span> <span data-ttu-id="03adc-110">Elas controlam a previsão básica que é gerada e mostrada na previsão de demanda ajustada.</span><span class="sxs-lookup"><span data-stu-id="03adc-110">They control the baseline forecast that is generated and shown in the adjusted demand forecast.</span></span> <span data-ttu-id="03adc-111">No entanto, elas não controlam as dimensões necessárias para a previsão de demanda "real".</span><span class="sxs-lookup"><span data-stu-id="03adc-111">However, they don't control the dimensions that are required for the "real" demand forecast.</span></span> <span data-ttu-id="03adc-112">Ao autorizar os registros mostrados na página **Previsão de demanda ajustada**, você pode convertê-los em entradas de previsão "reais" para um modelo de previsão.</span><span class="sxs-lookup"><span data-stu-id="03adc-112">By authorizing the records that are shown on the **Adjusted demand forecast** page, you can convert them to "real" forecast entries for a forecast model.</span></span> <span data-ttu-id="03adc-113">Assim, esse modelo poderá ser usado para o planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="03adc-113">That model can then be used for master planning.</span></span>

<span data-ttu-id="03adc-114">Na página **Previsão de demanda**, as dimensões da previsão "real" mostradas nas linhas de previsão de demanda fazem parte das dimensões de estoque.</span><span class="sxs-lookup"><span data-stu-id="03adc-114">On the **Demand forecast** page, the dimensions for the "real" forecast that are shown on the demand forecast lines are part of the inventory dimensions.</span></span> <span data-ttu-id="03adc-115">(Esse comportamento é semelhante ao comportamento de linhas da ordem de venda.) Se o sistema não estiver configurado para usar o **Depósito** como uma dimensão de estoque obrigatória, você poderá personalizar a página para ocultar a coluna.</span><span class="sxs-lookup"><span data-stu-id="03adc-115">(This behavior resembles the behavior for sales order lines.) If your system isn't set up to use **Warehouse** as a mandatory inventory dimension, you can customize the page to hide the column.</span></span>

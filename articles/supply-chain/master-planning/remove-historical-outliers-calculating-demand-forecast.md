---
title: Remover exceções de dados históricos de transação ao calcular uma previsão de demanda
description: Este artigo descreve como excluir exceções dos dados históricos que são usados para calcular uma previsão de demanda. Ao excluir as exceções, você pode aumentar a precisão de previsão.
author: roxanadiaconu
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanForecastParameters, ReqDemPlanOutlierQuerySetup, ReqDemPlanOutlierQueryPreview
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72621
ms.assetid: 88a964af-14eb-4c5c-945b-388e5908362c
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2131ae11e634f9ced0d9696acb61d7b8a94c59cf
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5841806"
---
# <a name="remove-outliers-from-historical-transaction-data-when-calculating-a-demand-forecast"></a><span data-ttu-id="271de-104">Remover exceções de dados históricos de transação ao calcular uma previsão de demanda</span><span class="sxs-lookup"><span data-stu-id="271de-104">Remove outliers from historical transaction data when calculating a demand forecast</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="271de-105">Este artigo descreve como excluir exceções dos dados históricos que são usados para calcular uma previsão de demanda.</span><span class="sxs-lookup"><span data-stu-id="271de-105">This article describes how to exclude outliers from the historical data that is used to calculate a demand forecast.</span></span> <span data-ttu-id="271de-106">Ao excluir as exceções, você pode aumentar a precisão de previsão.</span><span class="sxs-lookup"><span data-stu-id="271de-106">By excluding outliers, you can improve forecast accuracy.</span></span>

<span data-ttu-id="271de-107">Você pode excluir exceções para melhorar a precisão de previsão.</span><span class="sxs-lookup"><span data-stu-id="271de-107">You can exclude outliers to improve forecast accuracy.</span></span> <span data-ttu-id="271de-108">Esta é uma tarefa opcional.</span><span class="sxs-lookup"><span data-stu-id="271de-108">This is an optional task.</span></span> <span data-ttu-id="271de-109">Veja uma visão geral do processo:</span><span class="sxs-lookup"><span data-stu-id="271de-109">Here is an overview of the process:</span></span>

1.  <span data-ttu-id="271de-110">Clique em **Planejamento mestre** &gt; **Configuração** &gt; **Previsão de demanda** &gt; **Remoção de exceção** para abrir a página **Remoção de exceção** na qual você pode usar uma consulta para selecionar as transações a serem excluídas.</span><span class="sxs-lookup"><span data-stu-id="271de-110">Click **Master planning** &gt; **Setup** &gt; **Demand forecasting** &gt; **Outlier removal** to open the **Outlier removal** page, where you can use a query to select the transactions to exclude.</span></span>
2.  <span data-ttu-id="271de-111">Selecione a empresa à qual a consulta se aplica. Insira um nome e uma descrição.</span><span class="sxs-lookup"><span data-stu-id="271de-111">Select the company that the query applies to, and then enter a name and description.</span></span> <span data-ttu-id="271de-112">O campo **Data da consulta** é automaticamente definido como a data atual.</span><span class="sxs-lookup"><span data-stu-id="271de-112">The **Query date** field is automatically set to the current date.</span></span>
3.  <span data-ttu-id="271de-113">Marque a caixa de seleção **Ativa** para excluir as transações que foram localizadas pela consulta nos dados históricos.</span><span class="sxs-lookup"><span data-stu-id="271de-113">Select the **Active** check box to exclude the transactions that the query finds from the historical data.</span></span> <span data-ttu-id="271de-114">Essa configuração entrará em vigor quando você criar uma previsão estatística.</span><span class="sxs-lookup"><span data-stu-id="271de-114">This setting will take effect when you create a baseline forecast.</span></span>
4.  <span data-ttu-id="271de-115">Na página **Consulta de remoção de exceção**, você pode adicionar, remover e selecionar os critérios que definem quais transações serão excluídas quando a previsão estatística for calculada.</span><span class="sxs-lookup"><span data-stu-id="271de-115">On the **Outlier removal query** page, you can add, remove, and select the criteria that define which transactions will be excluded when the baseline forecast is calculated.</span></span> <span data-ttu-id="271de-116">Por exemplo, selecione um item ou uma transação de ordem específica a ser excluída.</span><span class="sxs-lookup"><span data-stu-id="271de-116">For example, select a specific item or order transaction to exclude.</span></span>
5.  <span data-ttu-id="271de-117">Clique em **Exibir transações**.</span><span class="sxs-lookup"><span data-stu-id="271de-117">Click **Display transactions**.</span></span> <span data-ttu-id="271de-118">A página **Transações de exceção** lista as transações que atendem aos critérios definidos na consulta e que serão excluídos dos dados históricos quando a previsão de demanda for calculada.</span><span class="sxs-lookup"><span data-stu-id="271de-118">The **Outlier transactions** page lists the transactions that meet the criteria that you defined in the query, and that will be excluded from the historical data when the demand forecast is calculated.</span></span>

<span data-ttu-id="271de-119">**Observação:** você também pode criar uma consulta com base em uma consulta existente.</span><span class="sxs-lookup"><span data-stu-id="271de-119">**Note:** You can also create a query that is based on an existing query.</span></span> <span data-ttu-id="271de-120">Selecione a consulta a ser copiada e então clique em **Duplicar**.</span><span class="sxs-lookup"><span data-stu-id="271de-120">Select the query to copy, and then click **Duplicate**.</span></span> <span data-ttu-id="271de-121">O campo **Data da consulta** identifica a versão.</span><span class="sxs-lookup"><span data-stu-id="271de-121">The **Query date** field identifies the version.</span></span> <span data-ttu-id="271de-122">Você pode usar a consulta como está ou pode clicar em **Editar consulta** para modificar os critérios.</span><span class="sxs-lookup"><span data-stu-id="271de-122">You can use the query as it is, or you can click **Edit query** to modify the criteria.</span></span> <span data-ttu-id="271de-123">Opcionalmente, você pode modificar o nome e a descrição da nova consulta.</span><span class="sxs-lookup"><span data-stu-id="271de-123">You can optionally modify the name and description of the new query.</span></span>

<a name="additional-resources"></a><span data-ttu-id="271de-124">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="271de-124">Additional resources</span></span>
--------

[<span data-ttu-id="271de-125">Visão geral da previsão de demanda</span><span class="sxs-lookup"><span data-stu-id="271de-125">Demand forecasting overview</span></span>](introduction-demand-forecasting.md)

[<span data-ttu-id="271de-126">​Monitorar precisão da previsão​</span><span class="sxs-lookup"><span data-stu-id="271de-126">Monitor forecast accuracy</span></span>](monitor-forecast-accuracy.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
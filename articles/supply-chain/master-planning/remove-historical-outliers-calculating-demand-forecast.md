---
title: Remover exceções de dados históricos de transação ao calcular uma previsão de demanda
description: Este artigo descreve como excluir exceções dos dados históricos que são usados para calcular uma previsão de demanda. Ao excluir as exceções, você pode aumentar a precisão de previsão.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanForecastParameters, ReqDemPlanOutlierQuerySetup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 72621
ms.assetid: 88a964af-14eb-4c5c-945b-388e5908362c
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7ce8ebaf32b30c57b307f0d8799660ba6b42365a
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "323608"
---
# <a name="remove-outliers-from-historical-transaction-data-when-calculating-a-demand-forecast"></a><span data-ttu-id="5b84c-104">Remover exceções de dados históricos de transação ao calcular uma previsão de demanda</span><span class="sxs-lookup"><span data-stu-id="5b84c-104">Remove outliers from historical transaction data when calculating a demand forecast</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5b84c-105">Este artigo descreve como excluir exceções dos dados históricos que são usados para calcular uma previsão de demanda.</span><span class="sxs-lookup"><span data-stu-id="5b84c-105">This article describes how to exclude outliers from the historical data that is used to calculate a demand forecast.</span></span> <span data-ttu-id="5b84c-106">Ao excluir as exceções, você pode aumentar a precisão de previsão.</span><span class="sxs-lookup"><span data-stu-id="5b84c-106">By excluding outliers, you can improve forecast accuracy.</span></span>

<span data-ttu-id="5b84c-107">Você pode excluir exceções para melhorar a precisão de previsão.</span><span class="sxs-lookup"><span data-stu-id="5b84c-107">You can exclude outliers to improve forecast accuracy.</span></span> <span data-ttu-id="5b84c-108">Esta é uma tarefa opcional.</span><span class="sxs-lookup"><span data-stu-id="5b84c-108">This is an optional task.</span></span> <span data-ttu-id="5b84c-109">Veja uma visão geral do processo:</span><span class="sxs-lookup"><span data-stu-id="5b84c-109">Here is an overview of the process:</span></span>

1.  <span data-ttu-id="5b84c-110">Clique em **Planejamento mestre** &gt; **Configuração** &gt; **Previsão de demanda** &gt; **Remoção de exceção** para abrir a página **Remoção de exceção** na qual você pode usar uma consulta para selecionar as transações a serem excluídas.</span><span class="sxs-lookup"><span data-stu-id="5b84c-110">Click **Master planning** &gt; **Setup** &gt; **Demand forecasting** &gt; **Outlier removal** to open the **Outlier removal** page, where you can use a query to select the transactions to exclude.</span></span>
2.  <span data-ttu-id="5b84c-111">Selecione a empresa à qual a consulta se aplica. Insira um nome e uma descrição.</span><span class="sxs-lookup"><span data-stu-id="5b84c-111">Select the company that the query applies to, and then enter a name and description.</span></span> <span data-ttu-id="5b84c-112">O campo **Data da consulta** é automaticamente definido como a data atual.</span><span class="sxs-lookup"><span data-stu-id="5b84c-112">The **Query date** field is automatically set to the current date.</span></span>
3.  <span data-ttu-id="5b84c-113">Marque a caixa de seleção **Ativa** para excluir as transações que foram localizadas pela consulta nos dados históricos.</span><span class="sxs-lookup"><span data-stu-id="5b84c-113">Select the **Active** check box to exclude the transactions that the query finds from the historical data.</span></span> <span data-ttu-id="5b84c-114">Essa configuração entrará em vigor quando você criar uma previsão estatística.</span><span class="sxs-lookup"><span data-stu-id="5b84c-114">This setting will take effect when you create a baseline forecast.</span></span>
4.  <span data-ttu-id="5b84c-115">Na página **Consulta de remoção de exceção**, você pode adicionar, remover e selecionar os critérios que definem quais transações serão excluídas quando a previsão estatística for calculada.</span><span class="sxs-lookup"><span data-stu-id="5b84c-115">On the **Outlier removal query** page, you can add, remove, and select the criteria that define which transactions will be excluded when the baseline forecast is calculated.</span></span> <span data-ttu-id="5b84c-116">Por exemplo, selecione um item ou uma transação de ordem específica a ser excluída.</span><span class="sxs-lookup"><span data-stu-id="5b84c-116">For example, select a specific item or order transaction to exclude.</span></span>
5.  <span data-ttu-id="5b84c-117">Clique em **Exibir transações**.</span><span class="sxs-lookup"><span data-stu-id="5b84c-117">Click **Display transactions**.</span></span> <span data-ttu-id="5b84c-118">A página **Transações de exceção** lista as transações que atendem aos critérios definidos na consulta e que serão excluídos dos dados históricos quando a previsão de demanda for calculada.</span><span class="sxs-lookup"><span data-stu-id="5b84c-118">The **Outlier transactions** page lists the transactions that meet the criteria that you defined in the query, and that will be excluded from the historical data when the demand forecast is calculated.</span></span>

<span data-ttu-id="5b84c-119">**Observação:** você também pode criar uma consulta com base em uma consulta existente.</span><span class="sxs-lookup"><span data-stu-id="5b84c-119">**Note:** You can also create a query that is based on an existing query.</span></span> <span data-ttu-id="5b84c-120">Selecione a consulta a ser copiada e então clique em **Duplicar**.</span><span class="sxs-lookup"><span data-stu-id="5b84c-120">Select the query to copy, and then click **Duplicate**.</span></span> <span data-ttu-id="5b84c-121">O campo **Data da consulta** identifica a versão.</span><span class="sxs-lookup"><span data-stu-id="5b84c-121">The **Query date** field identifies the version.</span></span> <span data-ttu-id="5b84c-122">Você pode usar a consulta como está ou pode clicar em **Editar consulta** para modificar os critérios.</span><span class="sxs-lookup"><span data-stu-id="5b84c-122">You can use the query as it is, or you can click **Edit query** to modify the criteria.</span></span> <span data-ttu-id="5b84c-123">Opcionalmente, você pode modificar o nome e a descrição da nova consulta.</span><span class="sxs-lookup"><span data-stu-id="5b84c-123">You can optionally modify the name and description of the new query.</span></span>

<a name="additional-resources"></a><span data-ttu-id="5b84c-124">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="5b84c-124">Additional resources</span></span>
--------

[<span data-ttu-id="5b84c-125">Introdução à previsão de demanda</span><span class="sxs-lookup"><span data-stu-id="5b84c-125">Introduction to demand forecasting</span></span>](introduction-demand-forecasting.md)

[<span data-ttu-id="5b84c-126">Monitorando a precisão da previsão</span><span class="sxs-lookup"><span data-stu-id="5b84c-126">Monitoring forecast accuracy</span></span>](monitor-forecast-accuracy.md)




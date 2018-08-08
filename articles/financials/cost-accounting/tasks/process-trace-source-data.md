--- 
title: Processar e rastrear dados de origem
description: "Todo o processamento de dados é executado por trabalhos."
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: e476416420875ba0f2401cf251d34977ae84b8f5
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2018

---
# <a name="process-and-trace-source-data"></a><span data-ttu-id="cd6a5-103">Processar e rastrear dados de origem</span><span class="sxs-lookup"><span data-stu-id="cd6a5-103">Process and trace source data</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cd6a5-104">Todo o processamento de dados é executado por trabalhos.</span><span class="sxs-lookup"><span data-stu-id="cd6a5-104">All data processing is run by jobs.</span></span> <span data-ttu-id="cd6a5-105">Para cada trabalho e provedor de dados, é criado um diário para documentar que o processo foi executado, e que as entradas foram processadas no trabalho atual.</span><span class="sxs-lookup"><span data-stu-id="cd6a5-105">For each job and data provider, a journal is created to document that the process has been run, and that the entries were processed in the current job.</span></span> <span data-ttu-id="cd6a5-106">Use este procedimento para configurar uma fonte de dados e para rastrear a origem de uma entrada de custos específica.</span><span class="sxs-lookup"><span data-stu-id="cd6a5-106">Use this procedure to set up a data source and then  trace the origin of a specific cost entry.</span></span> <span data-ttu-id="cd6a5-107">Esta gravação usa os dados da empresa de demonstração USP2.</span><span class="sxs-lookup"><span data-stu-id="cd6a5-107">This recording uses the USP2 demo data company USP2.</span></span> <span data-ttu-id="cd6a5-108">Antes de concluir esta tarefa, certifique-se de que executou os guias de tarefas "Criar um razão de contabilização de custos" e "Definir unidades de controle de custos".</span><span class="sxs-lookup"><span data-stu-id="cd6a5-108">Before you complete this task, make sure that you play the following task guides: "Create a cost accounting ledger," "Define cost control units," and "Manage data source for the cost accounting ledger."</span></span>

1. <span data-ttu-id="cd6a5-109">Vá para Contabilização de custos > Configuração do razão > Razões de contabilização de custos.</span><span class="sxs-lookup"><span data-stu-id="cd6a5-109">Go to Cost accounting > Ledger setup > Cost accounting ledgers.</span></span>
2. <span data-ttu-id="cd6a5-110">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="cd6a5-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="cd6a5-111">Selecione o razão de contabilização de custo criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="cd6a5-111">Select the cost accounting ledger that you created earlier.</span></span>  
3. <span data-ttu-id="cd6a5-112">Clique em Versões reais.</span><span class="sxs-lookup"><span data-stu-id="cd6a5-112">Click Actual versions.</span></span>
4. <span data-ttu-id="cd6a5-113">No Painel de Ação, clique em Processamento de dados de origem.</span><span class="sxs-lookup"><span data-stu-id="cd6a5-113">On the Action Pane, click Source data processing.</span></span>
5. <span data-ttu-id="cd6a5-114">Clique em Diários de transferência de entradas de contabilidade.</span><span class="sxs-lookup"><span data-stu-id="cd6a5-114">Click General ledger entry transfer journals.</span></span>
6. <span data-ttu-id="cd6a5-115">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="cd6a5-115">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="cd6a5-116">Clique em Entradas de Diário.</span><span class="sxs-lookup"><span data-stu-id="cd6a5-116">Click Journal entries.</span></span>
8. <span data-ttu-id="cd6a5-117">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="cd6a5-117">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="cd6a5-118">Clique em Entradas de custo.</span><span class="sxs-lookup"><span data-stu-id="cd6a5-118">Click Cost entries.</span></span>
10. <span data-ttu-id="cd6a5-119">Clique em Entrada de origem.</span><span class="sxs-lookup"><span data-stu-id="cd6a5-119">Click Source entry.</span></span>
11. <span data-ttu-id="cd6a5-120">No Painel de Ação, clique em Processamento de dados de origem.</span><span class="sxs-lookup"><span data-stu-id="cd6a5-120">On the Action Pane, click Source data processing.</span></span>
12. <span data-ttu-id="cd6a5-121">Clique em Contabilidade.</span><span class="sxs-lookup"><span data-stu-id="cd6a5-121">Click General ledger.</span></span>
13. <span data-ttu-id="cd6a5-122">No campo Período do calendário fiscal, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="cd6a5-122">In the Fiscal calendar period field, enter or select a value.</span></span>
    * <span data-ttu-id="cd6a5-123">Para este exemplo, selecione 9, Período Fiscal 2017.</span><span class="sxs-lookup"><span data-stu-id="cd6a5-123">For this example, select Fiscal 2017 Period 9.</span></span>  
14. <span data-ttu-id="cd6a5-124">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="cd6a5-124">Click OK.</span></span>



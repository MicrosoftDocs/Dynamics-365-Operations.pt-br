---
title: Relatar ordens de produção como concluídas
description: Relatar como concluído é um estágio da produção. Nesta fase, um produto acabado é reportado e movido da ordem de produção para o inventário.
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdJournalTransJob, ProdJournalTransProd, ProdJournalTransRoute, ProdParmReportFinished, ProdRouteOprOverview
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 27061
ms.assetid: 1c2dfc54-a293-49f2-9b96-5a912ac5762c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 61c12ee3a831abcb46af18645eba55fe100c99c9
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1567389"
---
# <a name="report-production-orders-as-finished"></a><span data-ttu-id="5bc3f-104">Relatar ordens de produção como concluídas</span><span class="sxs-lookup"><span data-stu-id="5bc3f-104">Report production orders as finished</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5bc3f-105">Relatar como concluído é um estágio da produção.</span><span class="sxs-lookup"><span data-stu-id="5bc3f-105">Report as finished is a production stage.</span></span> <span data-ttu-id="5bc3f-106">Nesta fase, um produto acabado é reportado e movido da ordem de produção para o inventário.</span><span class="sxs-lookup"><span data-stu-id="5bc3f-106">At this stage, a finished product is reported and moved from the production order to the inventory.</span></span>

<span data-ttu-id="5bc3f-107">Quando uma quantidade das mercadorias acabadas é informada como concluída em uma ordem de produção, ela é atualizada como disponível no estoque.</span><span class="sxs-lookup"><span data-stu-id="5bc3f-107">When a quantity of the finished goods is reported as finished on a production order it is updated as on-hand in the inventory.</span></span> <span data-ttu-id="5bc3f-108">As quantidades parciais da quantidade da ordem originalmente planejada podem ser informadas como concluídas.</span><span class="sxs-lookup"><span data-stu-id="5bc3f-108">Partial quantities of the originally planned order quantity can be reported as finished.</span></span> <span data-ttu-id="5bc3f-109">Também é possível relatar as quantidades de erro com um motivo de erro associado ao relatar quantidades como concluídas.</span><span class="sxs-lookup"><span data-stu-id="5bc3f-109">It is also possible to report error quantities with an associated error reason when reporting quantities as finished.</span></span> <span data-ttu-id="5bc3f-110">Quando a ordem de produção atingir o estágio Informado como concluído, isso indicará que nenhuma outra quantidade será informada na ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="5bc3f-110">When the production order reach the stage Reported as finished it indicates that no more quantity is going to be reported at the production  order.</span></span>
<span data-ttu-id="5bc3f-111">As características a seguir também estão associadas ao processo **Informar como concluído**:</span><span class="sxs-lookup"><span data-stu-id="5bc3f-111">The following characteristics are also associated with the **Report as finished** process:</span></span>
-   <span data-ttu-id="5bc3f-112">É possível configurar o consumo de matéria-prima e de tempo que seja proporcional à quantidade informada (baixa de estoque)</span><span class="sxs-lookup"><span data-stu-id="5bc3f-112">It is possible to set up consumption of raw material and time that are proportional to the reported quantity (back-flushing)</span></span>
-   <span data-ttu-id="5bc3f-113">O trabalho de armazenamento pode ser gerado para itens habilitados para os processos de depósito.</span><span class="sxs-lookup"><span data-stu-id="5bc3f-113">Put-away work can be generated for items that are enabled for warehouse processes.</span></span>
-   <span data-ttu-id="5bc3f-114">O valor do custo planejado ou padrão das mercadorias concluídas pode ser configurado para ser informado para as contas contábeis.</span><span class="sxs-lookup"><span data-stu-id="5bc3f-114">The planned or standard cost value of the finished goods can be set up to be reported to ledger accounts.</span></span>
-   <span data-ttu-id="5bc3f-115">Uma ordem de qualidade pode ser criada para a quantidade informada com base na configuração de uma associação de qualidade.</span><span class="sxs-lookup"><span data-stu-id="5bc3f-115">A quality order can be created for the reported quantity based on the setup of a quality association.</span></span>

<span data-ttu-id="5bc3f-116">A quantidade é informada no local de saída.</span><span class="sxs-lookup"><span data-stu-id="5bc3f-116">The quantity is reported to the output location.</span></span> <span data-ttu-id="5bc3f-117">O trabalho de depósito é então gerado para mover a quantidade do local de saída para seu destino final definido pela diretiva da localização do trabalho de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="5bc3f-117">Warehouse work is then generated to move the quantity from the output location to its final destination defined by the location directive for the put-away work.</span></span>

-   <span data-ttu-id="5bc3f-118">Uma ordem de qualidade pode ser criada quando uma ordem de produção é informada como concluída se uma associação de qualidade tiver sido configurada.</span><span class="sxs-lookup"><span data-stu-id="5bc3f-118">A quality order can be created when a production order is reported as finished if a quality association has been set up.</span></span>

## <a name="set-a-production-order-to-reporting-as-finished"></a><span data-ttu-id="5bc3f-119">Definir uma ordem de produção como Informada como concluída</span><span class="sxs-lookup"><span data-stu-id="5bc3f-119">Set a production order to Reporting as finished</span></span>
<span data-ttu-id="5bc3f-120">Você pode definir uma ordem de produção como **Informar como concluída** por meio da função de atualização da ordem de produção padrão ou por meio dos diários de roteiros e dos diários de ficha de trabalho ou por meio do diário **Informar como concluído**.</span><span class="sxs-lookup"><span data-stu-id="5bc3f-120">You can set a production order to **Report as finished** through the standard production order update function, or through the route and job card journals, or through the journal **Report as finished**.</span></span> <span data-ttu-id="5bc3f-121">Você também pode atualizar o estágio para **Informar como concluído** por meio das páginas de terminal de ficha de trabalho e de dispositivo de ficha de trabalho quando informa no último trabalho da ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="5bc3f-121">You can also update the stage to **Report as finished** through the job card terminal and job card device pages, when you report on the last job of the production order.</span></span> <span data-ttu-id="5bc3f-122">Por fim, você pode habilitar a opção **Informar como concluído** como um processo para a solução de dispositivo portátil para depósito.</span><span class="sxs-lookup"><span data-stu-id="5bc3f-122">Finally, you can enable the **Report as finished** option as a process for the handheld warehouse device solution.</span></span>  




---
title: Atualizar status de kanban
description: Quando um kanban é esvaziado por engano ou um kanban recebido precisa ser esvaziado, você precisa atualizar o status dele.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Kanban, KanbanResetEmpty
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bb8559c0843d7e6e538b5b29dc394a50d05462ee
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3210332"
---
# <a name="update-kanban-status"></a><span data-ttu-id="570ae-103">Atualizar status de kanban</span><span class="sxs-lookup"><span data-stu-id="570ae-103">Update kanban status</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="570ae-104">Quando um kanban é esvaziado por engano ou um kanban recebido precisa ser esvaziado, você precisa atualizar o status dele.</span><span class="sxs-lookup"><span data-stu-id="570ae-104">When a kanban is emptied by mistake or a received kanban needs to be emptied, you need to update kanban status.</span></span> <span data-ttu-id="570ae-105">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="570ae-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="570ae-106">Esse procedimento é criado para o supervisor de loja.</span><span class="sxs-lookup"><span data-stu-id="570ae-106">This procedure is intended for the shop supervisor.</span></span>


## <a name="find-the-kanban"></a><span data-ttu-id="570ae-107">Encontre o kanban.</span><span class="sxs-lookup"><span data-stu-id="570ae-107">Find the kanban.</span></span>
1. <span data-ttu-id="570ae-108">Vá para Controle de produção > Kanban > Kanbans.</span><span class="sxs-lookup"><span data-stu-id="570ae-108">Go to Production control > Kanban > Kanbans.</span></span>
2. <span data-ttu-id="570ae-109">Abra o filtro na coluna do status da unidade de manuseio.</span><span class="sxs-lookup"><span data-stu-id="570ae-109">Open Handling unit status column filter.</span></span>
3. <span data-ttu-id="570ae-110">Clicar em Limpar.</span><span class="sxs-lookup"><span data-stu-id="570ae-110">Click Clear.</span></span>
    * <span data-ttu-id="570ae-111">Isso redefine os filtros.</span><span class="sxs-lookup"><span data-stu-id="570ae-111">This resets the filters.</span></span>  
4. <span data-ttu-id="570ae-112">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="570ae-112">Use the Quick Filter to find records.</span></span> <span data-ttu-id="570ae-113">Por exemplo, filtre no campo Número do cartão com um valor de '000149'.</span><span class="sxs-lookup"><span data-stu-id="570ae-113">For example, filter on the Card number field with a value of '000149'.</span></span>

## <a name="change-emptied-status-to-received-status"></a><span data-ttu-id="570ae-114">Alterar status de esvaziado para recebido</span><span class="sxs-lookup"><span data-stu-id="570ae-114">Change emptied status to received status</span></span>
1. <span data-ttu-id="570ae-115">Clique em Reverter unidade de manuseio de material vazia.</span><span class="sxs-lookup"><span data-stu-id="570ae-115">Click Reverse empty handling unit.</span></span>
2. <span data-ttu-id="570ae-116">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="570ae-116">Click OK.</span></span>
    * <span data-ttu-id="570ae-117">Observe que o status da unidade de manuseio é Recebido.</span><span class="sxs-lookup"><span data-stu-id="570ae-117">Notice that the Handling unit status is Received.</span></span>  

## <a name="change-received-status-to-emptied-status"></a><span data-ttu-id="570ae-118">Alterar status de recebido para esvaziado</span><span class="sxs-lookup"><span data-stu-id="570ae-118">Change received status to emptied status</span></span>
1. <span data-ttu-id="570ae-119">Clique em Kanban vazio.</span><span class="sxs-lookup"><span data-stu-id="570ae-119">Click Empty kanban.</span></span>
2. <span data-ttu-id="570ae-120">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="570ae-120">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="570ae-121">Observe que o status da unidade de manuseio é esvaziado.</span><span class="sxs-lookup"><span data-stu-id="570ae-121">Notice that the Handling unit status is Emptied.</span></span>  


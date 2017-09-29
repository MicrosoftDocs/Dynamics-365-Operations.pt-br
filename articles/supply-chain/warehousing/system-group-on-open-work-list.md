---
title: Agrupamento do sistema em uma lista de trabalho aberta
description: "Este tópico descreve como filtrar a lista aberta de trabalho em um dispositivo móvel."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 0c68d544fec985f325e6472203533f23948cc9b4
ms.contentlocale: pt-br
ms.lasthandoff: 07/18/2017

---

# <a name="system-grouping-on-an-open-work-list"></a><span data-ttu-id="72cf9-103">Agrupamento do sistema em uma lista de trabalho aberta</span><span class="sxs-lookup"><span data-stu-id="72cf9-103">System grouping on an open work list</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="72cf9-104">Ao usar um campo de agrupamento de sistema, você pode filtrar uma lista de trabalho aberta sem ter que editar o item de menu do dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="72cf9-104">By using a system grouping field, you can filter an open work list without having to edit the mobile device menu item.</span></span>
<span data-ttu-id="72cf9-105">Onde aplicável, o agrupamento de sistemas funciona para filtrar uma lista de trabalho em um único campo de cabeçalho de trabalho.</span><span class="sxs-lookup"><span data-stu-id="72cf9-105">Where it applies, system grouping works for filtering a work list on a single work header field.</span></span> <span data-ttu-id="72cf9-106">Você não pode usar o agrupamento de sistema para filtrar em campos de nível de linha.</span><span class="sxs-lookup"><span data-stu-id="72cf9-106">You cannot use system grouping to filter on line level fields.</span></span>

## <a name="set-up-system-grouping-on-an-open-work-list"></a><span data-ttu-id="72cf9-107">Configurar o agrupamento do sistema em uma lista de trabalho aberta</span><span class="sxs-lookup"><span data-stu-id="72cf9-107">Set up system grouping on an open work list</span></span>
<span data-ttu-id="72cf9-108">Use estas etapas para configurar o agrupamento do sistema em uma lista de trabalho aberta.</span><span class="sxs-lookup"><span data-stu-id="72cf9-108">Use these steps to set up system grouping on an open work list.</span></span>

-   <span data-ttu-id="72cf9-109">Em um item de menu de dispositivo móvel, selecione **Modo: Indireto** e **Código de atividade: Exibir lista de trabalho aberta**.</span><span class="sxs-lookup"><span data-stu-id="72cf9-109">From a mobile device menu item, select **Mode: Indirect** and **Activity Code: Display open work list**.</span></span> <span data-ttu-id="72cf9-110">As seguintes opções estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="72cf9-110">The following options become available.</span></span> <span data-ttu-id="72cf9-111">Essas opções são necessárias para o agrupamento de sistema em uma lista de trabalho.</span><span class="sxs-lookup"><span data-stu-id="72cf9-111">These options are required for system grouping on an open work list.</span></span> 

| <span data-ttu-id="72cf9-112">Opção</span><span class="sxs-lookup"><span data-stu-id="72cf9-112">Option</span></span>        | <span data-ttu-id="72cf9-113">descrição</span><span class="sxs-lookup"><span data-stu-id="72cf9-113">Description</span></span>   | 
| ------------- | ------------- |
| <span data-ttu-id="72cf9-114">Permitir o agrupamento do sistema</span><span class="sxs-lookup"><span data-stu-id="72cf9-114">Allow system grouping</span></span>   | <span data-ttu-id="72cf9-115">Permite o agrupamento de sistema para um item de menu selecionado da lista de trabalho.</span><span class="sxs-lookup"><span data-stu-id="72cf9-115">Enables system groping for a selected work list menu item.</span></span>| 
| <span data-ttu-id="72cf9-116">Campo de agrupamento do sistema</span><span class="sxs-lookup"><span data-stu-id="72cf9-116">System grouping field</span></span>   | <span data-ttu-id="72cf9-117">Disponível se **Permitir trabalhos de sistema** estiver definido como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="72cf9-117">Available only if **Allow system work** is set to **Yes**.</span></span> <span data-ttu-id="72cf9-118">Selecione o campo que determina como o trabalho de escolha será agrupado para os trabalhadores.</span><span class="sxs-lookup"><span data-stu-id="72cf9-118">Select the field that determines how picking work will be grouped for workers.</span></span> <span data-ttu-id="72cf9-119">Por exemplo, se você selecionar o campo **ShipmentId**, o trabalhador verificará a ID da remessa para agrupar o trabalho de separação.</span><span class="sxs-lookup"><span data-stu-id="72cf9-119">For example, if you select the **ShipmentId** field, the worker will scan the shipment ID to group the picking work.</span></span> <span data-ttu-id="72cf9-120">Todo o trabalho para a remessa será então atribuído ao trabalhador.</span><span class="sxs-lookup"><span data-stu-id="72cf9-120">All work for the shipment is then assigned to the worker.</span></span> <span data-ttu-id="72cf9-121">Este campo requer que você crie um item de menu para usar o trabalho existente agrupado pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="72cf9-121">This field requires that you create a menu item to use existing work that is grouped by the system.</span></span> <span data-ttu-id="72cf9-122">Use o campo **Rótulo do agrupamento de sistema** para informar ao trabalhador o que verificar.</span><span class="sxs-lookup"><span data-stu-id="72cf9-122">Use the **System grouping label** field to inform the worker what to scan.</span></span> |
| <span data-ttu-id="72cf9-123">Etiqueta de agrupamento do sistema</span><span class="sxs-lookup"><span data-stu-id="72cf9-123">System grouping label</span></span>   | <span data-ttu-id="72cf9-124">Disponível se **Permitir trabalhos de sistema** estiver definido como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="72cf9-124">Available only if **Allow system work** is set to **Yes**.</span></span> <span data-ttu-id="72cf9-125">Insira as informações para o trabalhador sobre o que verificar quando o trabalho de separação for agrupado.</span><span class="sxs-lookup"><span data-stu-id="72cf9-125">Enter information for the worker about what to scan when picking work is grouped.</span></span> <span data-ttu-id="72cf9-126">Por exemplo, se você estiver usando o campo **ShipmentId** para agrupar o trabalho de separação por remessa, poderá inserir ID da Remessa no campo.</span><span class="sxs-lookup"><span data-stu-id="72cf9-126">For example, if you use the **ShipmentId** field to group picking work by shipment, you might enter Shipment ID in the field.</span></span> <span data-ttu-id="72cf9-127">Este campo requer que você crie um item de menu para usar o trabalho existente agrupado pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="72cf9-127">This field requires that you create a menu item to use existing work that is grouped by the system.</span></span> <span data-ttu-id="72cf9-128">Você também deverá selecionar o campo para agrupar no campo **Agrupamento do sistema**.</span><span class="sxs-lookup"><span data-stu-id="72cf9-128">You must also select the field to group by in the **System grouping** field.</span></span>|


---
title: Sincronizar capacidade de recursos
description: Este tópico fornece informações sobre como sincronizar a capacidade de um recurso em calendários e projetos.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 27b6fde91a72e37bb2712daba765032322cbd4e9
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760472"
---
# <a name="synchronize-resource-capacity"></a><span data-ttu-id="0d333-103">Sincronizar capacidade de recursos</span><span class="sxs-lookup"><span data-stu-id="0d333-103">Synchronize resource capacity</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0d333-104">Os processos para ajudar a sincronização de recurso ajudam a garantir que as informações do calendário e do calendário base passem para o agendamento de recurso de projeto.</span><span class="sxs-lookup"><span data-stu-id="0d333-104">The processes for resource synchronization help guarantee that information for the calendar and base calendar trickles down into project resource scheduling.</span></span> <span data-ttu-id="0d333-105">Se o calendário for alterado, os processos farão as atualizações necessárias no agendamento dos recursos de projeto.</span><span class="sxs-lookup"><span data-stu-id="0d333-105">If the calendar is changed, the processes make the required updates to the scheduling of project resources.</span></span> <span data-ttu-id="0d333-106">Os processos também ajudam a melhorar o desempenho, pois as informações de recurso de calendário são previamente sincronizadas.</span><span class="sxs-lookup"><span data-stu-id="0d333-106">The processes also help improve performance, because the calendar's resource information is synchronized in advance.</span></span> <span data-ttu-id="0d333-107">Portanto, as atualizações para informações de recurso ocorrem mais rapidamente.</span><span class="sxs-lookup"><span data-stu-id="0d333-107">Therefore, updates to resource scheduling information occur more quickly.</span></span> <span data-ttu-id="0d333-108">Recomendamos que você agende os processos em lotes em vez de um de cada vez.</span><span class="sxs-lookup"><span data-stu-id="0d333-108">We recommend that you schedule the processes as a batch instead of one at a time.</span></span> <span data-ttu-id="0d333-109">Caso contrário, há o risco de que alguém se esqueça das datas inclusivas quando as informações foram sincronizadas pela última vez.</span><span class="sxs-lookup"><span data-stu-id="0d333-109">Otherwise, there is a risk that someone will forget the inclusive dates when the information was last synchronized.</span></span> <span data-ttu-id="0d333-110">Se as datas inclusivas não forem usadas, poderão ocorrer lacunas durante a sincronização de datas.</span><span class="sxs-lookup"><span data-stu-id="0d333-110">If inclusive dates aren't used, gaps can occur during date synchronization.</span></span>

![Sincronização de calendário](./media/projectresourcing04-1024x471.jpg)

## <a name="synchronize-resource-capacity-roll-ups"></a><span data-ttu-id="0d333-112">Sincronizar acúmulos de capacidade de recurso</span><span class="sxs-lookup"><span data-stu-id="0d333-112">Synchronize resource capacity roll-ups</span></span>

<span data-ttu-id="0d333-113">O processo de sincronização é projetado para sincronizar todas as informações do calendário do recurso.</span><span class="sxs-lookup"><span data-stu-id="0d333-113">The synchronization process is designed to synchronize all resource calendar information.</span></span> <span data-ttu-id="0d333-114">Essas informações incluem informações do calendário base sobre todas as alterações na tabela de capacidade do calendário do recurso do projeto.</span><span class="sxs-lookup"><span data-stu-id="0d333-114">This information includes base calendar information about any changes to the project's Resource calendar capacity table.</span></span> <span data-ttu-id="0d333-115">Se novos recursos forem adicionados ao projeto, a sincronização ajuda a garantir que as informações atualizadas de calendário estejam disponíveis.</span><span class="sxs-lookup"><span data-stu-id="0d333-115">If new resources are added in the project, synchronization helps guarantee that the updated calendar information is available.</span></span> <span data-ttu-id="0d333-116">Essa sincronização pode ser feita a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="0d333-116">This synchronization can be done at any time.</span></span>

<span data-ttu-id="0d333-117">É recomendável usar um lote.</span><span class="sxs-lookup"><span data-stu-id="0d333-117">We recommend that you use a batch.</span></span> <span data-ttu-id="0d333-118">As opções estarão disponíveis durante a sincronização de reservas de capacidade.</span><span class="sxs-lookup"><span data-stu-id="0d333-118">The options are available during synchronization of capacity reservations.</span></span>

1. <span data-ttu-id="0d333-119">Selecione **Gerenciamento e contabilidade de projeto** &gt; **Atividades periódicas** &gt; **Sincronização de capacidade** &gt; **Sincronizar acúmulos de capacidade de recursos**.</span><span class="sxs-lookup"><span data-stu-id="0d333-119">Select **Project management and accounting** &gt; **Periodic** &gt; **Capacity synchronization** &gt; **Synchronize resources capacity roll-ups**.</span></span>
2. <span data-ttu-id="0d333-120">Defina as opções na seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="0d333-120">Set the options in the following table.</span></span>

    | <span data-ttu-id="0d333-121">Opção</span><span class="sxs-lookup"><span data-stu-id="0d333-121">Option</span></span>      | <span data-ttu-id="0d333-122">descrição</span><span class="sxs-lookup"><span data-stu-id="0d333-122">Description</span></span> |
    |-------------|-------------|
    | <span data-ttu-id="0d333-123">Código de período</span><span class="sxs-lookup"><span data-stu-id="0d333-123">Period code</span></span> | <span data-ttu-id="0d333-124">Se preferir, selecione o código de intervalo de datas da contabilidade para definir as datas inicial e final para o processo de sincronização para acúmulos de capacidade de recurso.</span><span class="sxs-lookup"><span data-stu-id="0d333-124">Optionally select the General ledger date interval code to set the start and end dates for the synchronization process for resource capacity roll-ups.</span></span> |
    | <span data-ttu-id="0d333-125">Data de início</span><span class="sxs-lookup"><span data-stu-id="0d333-125">Start date</span></span>  | <span data-ttu-id="0d333-126">Insira a data inicial para o processo de sincronização para acúmulos de capacidade de recurso.</span><span class="sxs-lookup"><span data-stu-id="0d333-126">Enter the start date for the synchronization process for resource capacity roll-ups.</span></span> |
    | <span data-ttu-id="0d333-127">Data de término</span><span class="sxs-lookup"><span data-stu-id="0d333-127">End date</span></span>    | <span data-ttu-id="0d333-128">Insira a data final para o processo de sincronização para acúmulos de capacidade de recurso.</span><span class="sxs-lookup"><span data-stu-id="0d333-128">Enter the end date for the synchronization process for resource capacity roll-ups.</span></span> |

<span data-ttu-id="0d333-129">[![Processo de sincronização](./media/projectresourcing09.jpg)](./media/projectresourcing09.jpg)</span><span class="sxs-lookup"><span data-stu-id="0d333-129">[![Synchronization process](./media/projectresourcing09.jpg)](./media/projectresourcing09.jpg)</span></span>

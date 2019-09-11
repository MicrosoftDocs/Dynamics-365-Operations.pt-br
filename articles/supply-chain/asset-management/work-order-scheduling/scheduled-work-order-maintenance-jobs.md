---
title: Trabalhos de manutenção da ordem de serviço agendados
description: Este tópico explica os trabalhos de manutenção de ordem de serviço agendados no Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4b3cc32d6ff263967c1ee843702c28968219ac33
ms.sourcegitcommit: f93ead945afe5ae18706c66bce6e64a6b57aac50
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/19/2019
ms.locfileid: "1887173"
---
# <a name="scheduled-work-order-maintenance-jobs"></a><span data-ttu-id="9a5e7-103">Trabalhos de manutenção da ordem de serviço agendados</span><span class="sxs-lookup"><span data-stu-id="9a5e7-103">Scheduled work order maintenance jobs</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="9a5e7-104">A página **Trabalhos de manutenção de ordens de serviço agendadas** é usada para obter ma visão geral as ordens de serviço alocadas a um recurso.</span><span class="sxs-lookup"><span data-stu-id="9a5e7-104">The **Scheduled work order maintenance jobs** page is used to get an overview of the work orders allocated to a resource.</span></span> <span data-ttu-id="9a5e7-105">Ordens de trabalho usando tipos de recurso "Recursos humanos", "Ferramenta" e "Máquina" são exibidos na lista.</span><span class="sxs-lookup"><span data-stu-id="9a5e7-105">Work orders using resource types "Human resources", "Tool", and "Machine" are shown in the list.</span></span> <span data-ttu-id="9a5e7-106">A lista pode ser usada para obter uma visão geral das ordens de trabalho alocadas a um recurso específico.</span><span class="sxs-lookup"><span data-stu-id="9a5e7-106">The list can be used to get an overview of work orders allocated to a specific resource.</span></span> <span data-ttu-id="9a5e7-107">Você também pode usá-la para localizar uma ordem de serviço alocada a um funcionário de manutenção que, por exemplo, estava doente essa manhã, e depois rapidamente alocar outro funcionário de manutenção para o trabalho.</span><span class="sxs-lookup"><span data-stu-id="9a5e7-107">You can also use it to quickly find a work order allocated to a maintenance worker who, for example, called in sick this morning, and then quickly allocate another maintenance worker to the job.</span></span>

## <a name="view-scheduled-work-order-maintenance-jobs"></a><span data-ttu-id="9a5e7-108">Exibir trabalhos de manutenção de ordens de serviço agendadas</span><span class="sxs-lookup"><span data-stu-id="9a5e7-108">View scheduled work order maintenance jobs</span></span>

1. <span data-ttu-id="9a5e7-109">Clique em **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Trabalhos de manutenção de ordens de serviço agendadas**.</span><span class="sxs-lookup"><span data-stu-id="9a5e7-109">Click **Asset management** > **Common** > **Work orders** > **Scheduled work order maintenance jobs**.</span></span> <span data-ttu-id="9a5e7-110">Você verá uma lista de todas as ordens de serviço definidas para o estado de ciclo de vida da ordem de serviço "Agendado" ou "Em progresso".</span><span class="sxs-lookup"><span data-stu-id="9a5e7-110">You see a list of all work orders set to work order lifecycle state "Scheduled" or "In progress".</span></span>

2. <span data-ttu-id="9a5e7-111">Você pode classificar a lista, por exemplo, pelo funcionário de manutenção.</span><span class="sxs-lookup"><span data-stu-id="9a5e7-111">You can sort the list, for example, by maintenance worker.</span></span> <span data-ttu-id="9a5e7-112">Você também pode usar o filtro para limitar a lista a exibir ordens de serviço alocadas a um recurso específico ou funcionário de manutenção.</span><span class="sxs-lookup"><span data-stu-id="9a5e7-112">You can also use the filter to limit the list to display work orders allocated to a specific resource or maintenance worker.</span></span>

3. <span data-ttu-id="9a5e7-113">Você pode ver as notas na ordem de serviço e, se necessário, adicionar novas notas selecionando a ordem de serviço na lista e clicando em **Notas**.</span><span class="sxs-lookup"><span data-stu-id="9a5e7-113">You can see notes on the work order and, if required, add new notes by selecting the work order job in the list and clicking **Notes**.</span></span>

4. <span data-ttu-id="9a5e7-114">Se desejar alocar um funcionário de manutenção a uma ordem de serviço, selecione a ordem de serviço na lista e clique em **Ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="9a5e7-114">If you want to allocate one maintenance worker to a work order, select the work order in the list, and click **Work order**.</span></span>

5. <span data-ttu-id="9a5e7-115">A página **Ordem de serviço** é aberta.</span><span class="sxs-lookup"><span data-stu-id="9a5e7-115">The **Work order** page opens.</span></span> <span data-ttu-id="9a5e7-116">Clique em **Expedir** para agendar a ordem de serviço a um funcionário de manutenção específico.</span><span class="sxs-lookup"><span data-stu-id="9a5e7-116">Click **Dispatch** to schedule the work order to a specific maintenance worker.</span></span>

>[!NOTE]
><span data-ttu-id="9a5e7-117">Leia mais sobre como agendar várias ordens de serviço ou uma ordem de serviço em [Agendar ordens de serviço](../work-order-scheduling/schedule-work-orders.md) e [Expedir ordem de serviço](../work-order-scheduling/dispatch-work-order.md).</span><span class="sxs-lookup"><span data-stu-id="9a5e7-117">Read more about scheduling several work orders or one work order in [Schedule work orders](../work-order-scheduling/schedule-work-orders.md) and [Dispatch work order](../work-order-scheduling/dispatch-work-order.md).</span></span>

<span data-ttu-id="9a5e7-118">A figura abaixo mostra um exemplo da página **Trabalhos de manutenção de ordens de serviço agendadas**.</span><span class="sxs-lookup"><span data-stu-id="9a5e7-118">The figure below shows an example of the **Scheduled work order maintenance jobs** page.</span></span>

![Figura 1](media/07-work-order-scheduling.png)


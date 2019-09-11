---
title: Execução agendada
description: Este tópico explica execução agendada no Asset Management.
author: josaw1
manager: AnnBe
ms.date: 08/13/2019
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
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8d9c8afc139c96e32efb3161d35fde685b8abcc5
ms.sourcegitcommit: 802dbf0a744d70f9e546632d419415b0993331ab
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2019
ms.locfileid: "1874661"
---
# <a name="scheduled-execution"></a><span data-ttu-id="5b199-103">Execução agendada</span><span class="sxs-lookup"><span data-stu-id="5b199-103">Scheduled execution</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="5b199-104">Você pode usar níveis de serviço da ordem de serviço para configurar a execução agendada.</span><span class="sxs-lookup"><span data-stu-id="5b199-104">You can use work order service levels to set up scheduled execution.</span></span> <span data-ttu-id="5b199-105">(Para obter mais informações sobre níveis de serviço da ordem de serviço, consulte [Nível de serviço e descrição](service-level-and-description.md).) A execução agendada fornece flexibilidade no planejamento de trabalho para funcionários de manutenção, já você pode configurar requisitos mais ou menos detalhados para um intervalo em que uma ordem de serviço deve ser concluída.</span><span class="sxs-lookup"><span data-stu-id="5b199-105">(For more information about work order service levels, see [Service level and description](service-level-and-description.md).) Scheduled execution provides flexibility in work planning for maintenance workers, because you can set up more detailed or less detailed requirements for the interval that a work order should be completed during.</span></span> <span data-ttu-id="5b199-106">Por exemplo, um funcionário de manutenção que conclui um trabalho mais rápido que o esperado em uma fábrica pode ser capaz de mover para outro trabalho próximo que foi planejado para a semana atual, mas não necessariamente para o dia atual.</span><span class="sxs-lookup"><span data-stu-id="5b199-106">For example, a maintenance worker who completes a job faster than expected in a production facility might be able to move on to another nearby job that was planned for the current week but not necessarily for the current day.</span></span> <span data-ttu-id="5b199-107">Esta abordagem permite a otimização do planejamento do trabalhador e conclusão do trabalho.</span><span class="sxs-lookup"><span data-stu-id="5b199-107">This approach allows for optimization of worker planning and job completion.</span></span>

<span data-ttu-id="5b199-108">Configuração de execução agendada, que é relacionada a ordens de serviço, pode ser genérica ou específica.</span><span class="sxs-lookup"><span data-stu-id="5b199-108">Scheduled execution setup, which is related to work orders, can be generic or specific.</span></span> <span data-ttu-id="5b199-109">Você pode configurar linhas genéricas que não são limitadas a tipos de ordem de serviço específicas, tipos de ativos e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="5b199-109">You can set up generic lines that aren't limited to specific work order types, asset types, and so on.</span></span> <span data-ttu-id="5b199-110">Alternativamente, você pode criar linhas de execução agendadas que se aplicam a um tipo de ordem de serviço específico, tipo de ativo, tipo de trabalho de manutenção, e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="5b199-110">Alternatively, you can create scheduled execution lines that apply to a specific work order type, asset type, maintenance job type, and so on.</span></span>

1. <span data-ttu-id="5b199-111">Selecione **Gerenciamento de Ativos** \> **Configuração** \> **Ordens de serviço** \> **Execução agendada**.</span><span class="sxs-lookup"><span data-stu-id="5b199-111">Select **Asset management** \> **Setup** \> **Work orders** \> **Scheduled execution**.</span></span>
2. <span data-ttu-id="5b199-112">Selecione **Novo** para criar uma linha de execução agendada.</span><span class="sxs-lookup"><span data-stu-id="5b199-112">Select **New** to create a scheduled execution line.</span></span>
3. <span data-ttu-id="5b199-113">Nos campos **Local funcional**, **Tipo de ordem de serviço**, **Tipo de ativo**, **Fabricante**, **Modelo**, **Categoria de tipo de trabalho de manutenção**, **Tipo de trabalho de manutenção**, **Variação do tipo de trabalho de manutenção** e **Comércio**, selecione os valores que deseja.</span><span class="sxs-lookup"><span data-stu-id="5b199-113">In the **Functional location**, **Work order type**, **Asset type**, **Manufacturer**, **Model**, **Maintenance job type category**, **Maintenance job type**, **Maintenance job type variant**, and **Trade** fields, select values as you require.</span></span>
4. <span data-ttu-id="5b199-114">No campo **Nível de serviço**, selecione um nível de serviço de ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="5b199-114">In the **Service level** field, select a work order service level.</span></span> <span data-ttu-id="5b199-115">Se deixar este campo em branco, você cria o tipo mais genérico de linha de execução agendada.</span><span class="sxs-lookup"><span data-stu-id="5b199-115">If you leave this field blank, you make the most generic type of scheduled execution line.</span></span> <span data-ttu-id="5b199-116">Para um exemplo de uma linha genérica, consulte o primeiro registro na ilustração a seguir.</span><span class="sxs-lookup"><span data-stu-id="5b199-116">For an example of a generic line, see the first record in the illustration that follows.</span></span> <span data-ttu-id="5b199-117">Essa linha permite que todos as ordens de serviço que não tem um nível de serviço de ordem de serviço sejam agendadas para uma data e hora específica.</span><span class="sxs-lookup"><span data-stu-id="5b199-117">That line enables all work orders that have no work order service level to be scheduled for a specific date and time.</span></span>
5. <span data-ttu-id="5b199-118">No campo **Execução agendada**, selecione o intervalo de tempo.</span><span class="sxs-lookup"><span data-stu-id="5b199-118">In the **Scheduled execution** field, select the time interval.</span></span>
6. <span data-ttu-id="5b199-119">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5b199-119">Select **Save**.</span></span>

![Figura 1](media/20-setup-for-work-orders.png)

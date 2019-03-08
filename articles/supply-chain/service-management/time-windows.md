---
title: Janelas de horas
description: Você pode usar janelas de tempo para otimizar o agendamento das linhas de ordem de serviço.
author: ShylaThompson
manager: AnnBe
ms.date: 02/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMATimeAgreement
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6f748268f6cb85ff835919485da2828689eee23c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "347206"
---
# <a name="time-windows"></a><span data-ttu-id="8de3a-103">Janelas de horas</span><span class="sxs-lookup"><span data-stu-id="8de3a-103">Time windows</span></span>  

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8de3a-104">Você pode usar janelas de tempo para otimizar o agendamento das linhas de ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="8de3a-104">You can use time windows to optimize the scheduling of service order lines.</span></span> <span data-ttu-id="8de3a-105">Você pode configurar o sistema de forma que criar automaticamente ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="8de3a-105">You can set up the system so that it automatically creates service orders.</span></span> <span data-ttu-id="8de3a-106">Com base nos critérios especificados por uma janela de tempo, você pode associar quantas linhas de ordem de serviço de possíveis à menor quantidade de ordens de serviço possíveis.</span><span class="sxs-lookup"><span data-stu-id="8de3a-106">Based on the criteria specified by a time window, you can connect as many service order lines as possible to as few service orders as possible.</span></span>

<span data-ttu-id="8de3a-107">As janelas de tempo definem até que ponto uma linha de ordem de serviço pode se mover em relação à data de cálculo.</span><span class="sxs-lookup"><span data-stu-id="8de3a-107">Time windows specify how far a service order line can move from its calculated date.</span></span> <span data-ttu-id="8de3a-108">Essa é a data na qual a linha da ordem de serviço foi programada para ocorrer.</span><span class="sxs-lookup"><span data-stu-id="8de3a-108">The calculated date is the date when the service order line was scheduled to occur.</span></span> <span data-ttu-id="8de3a-109">A data é baseada na configuração de intervalo e no período de serviço definidos na página **Criar ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="8de3a-109">The date is based on its interval setting and the service period that you defined in the **Create service orders** page.</span></span> <span data-ttu-id="8de3a-110">Defina uma janela de tempo usando os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="8de3a-110">You define a time window by using the values in the following table.</span></span>

| <span data-ttu-id="8de3a-111">Método</span><span class="sxs-lookup"><span data-stu-id="8de3a-111">Method</span></span> | <span data-ttu-id="8de3a-112">descrição</span><span class="sxs-lookup"><span data-stu-id="8de3a-112">Description</span></span>                                                                                                                                                                                                                                                                                           |
|--------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="8de3a-113">Semana</span><span class="sxs-lookup"><span data-stu-id="8de3a-113">Week</span></span>   | <span data-ttu-id="8de3a-114">A data de execução da linha da ordem de serviço pode ser movida para qualquer dia aberto na mesma semana que a data inicial calculada.</span><span class="sxs-lookup"><span data-stu-id="8de3a-114">The date that the service order line can be moved to any open day in the same week as the initial calculated date.</span></span>                                                                                                                                                                                    |
| <span data-ttu-id="8de3a-115">Mês</span><span class="sxs-lookup"><span data-stu-id="8de3a-115">Month</span></span>  | <span data-ttu-id="8de3a-116">A data de execução da linha da ordem de serviço pode ser movida para qualquer dia aberto no mesmo mês que a data inicial calculada.</span><span class="sxs-lookup"><span data-stu-id="8de3a-116">The date that the service order line can be moved to any open day in the same month as the initial calculated date.</span></span> <span data-ttu-id="8de3a-117">Por exemplo, a data calculada para uma linha de ordem de serviço é 15 de fevereiro de 2017.</span><span class="sxs-lookup"><span data-stu-id="8de3a-117">For example, the calculated date for a service order line is February 15, 2017.</span></span> <span data-ttu-id="8de3a-118">A linha pode ser programada para qualquer dia útil entre 1º de fevereiro e 28 de fevereiro de 2017.</span><span class="sxs-lookup"><span data-stu-id="8de3a-118">The service order line can be scheduled for any weekday between February 1 and February 28, 2017.</span></span> |
| <span data-ttu-id="8de3a-119">Manual</span><span class="sxs-lookup"><span data-stu-id="8de3a-119">Manual</span></span> | <span data-ttu-id="8de3a-120">Defina o número máximo de dias antes ou depois da data inicial calculada em que a linha da ordem de serviço pode ser movida.</span><span class="sxs-lookup"><span data-stu-id="8de3a-120">You define the maximum number of days before or after the initial calculated date that the service order line can be moved.</span></span>                                                                                                                                                                           |

<span data-ttu-id="8de3a-121">Se uma janela de tempo não for especificada para uma linha de contrato de serviço, a linha da ordem de serviço que deriva do contrato deverá ser executada na data exata em que foi programada inicialmente.</span><span class="sxs-lookup"><span data-stu-id="8de3a-121">If you do not specify a time window for a service agreement line, the service order line that is derived from the service agreement must be on the exact date for which it was originally scheduled.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8de3a-122">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="8de3a-122">Related topics</span></span>

[<span data-ttu-id="8de3a-123">Criar janelas de horas</span><span class="sxs-lookup"><span data-stu-id="8de3a-123">Create time windows</span></span>](create-time-windows.md)


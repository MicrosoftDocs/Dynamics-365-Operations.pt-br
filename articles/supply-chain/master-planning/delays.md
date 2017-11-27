---
title: Atrasos
description: "Este artigo fornece informações sobre as datas em atraso no planejamento mestre. Uma data posterior é uma data de vencimento realista que uma transação recebe se a data de preenchimento mais recente que o planejamento mestre calcula é posterior a data solicitada."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqTransFuturesListPage
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: ed0df1abbf4f70ea70046eff7b91a25fdd59016c
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="delays"></a><span data-ttu-id="52079-104">Atrasos</span><span class="sxs-lookup"><span data-stu-id="52079-104">Delays</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="52079-105">Este artigo fornece informações sobre as datas em atraso no planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="52079-105">This article provides information about delayed dates in master planning.</span></span> <span data-ttu-id="52079-106">Uma data posterior é uma data de vencimento realista que uma transação recebe se a data de preenchimento mais recente que o planejamento mestre calcula é posterior a data solicitada.</span><span class="sxs-lookup"><span data-stu-id="52079-106">A delayed date is a realistic due date that a transaction receives if the earliest fulfillment date that master planning calculates is later than the requested date.</span></span>

<span data-ttu-id="52079-107">O planejamento mestre pode calcular a data de término de vigência mais antiga para uma transação com base nos prazos de entrega, na disponibilidade material, na disponibilidade de capacidade e em vários parâmetros de planejamento.</span><span class="sxs-lookup"><span data-stu-id="52079-107">Master planning can calculate the earliest fulfillment date for a transaction, based on lead times, material availability, capacity availability, and various planning parameters.</span></span> 

<span data-ttu-id="52079-108">Se o planejamento mestre calcular a data de uma ordem como anterior à data atual, a ordem não poderá ser atendida a tempo.</span><span class="sxs-lookup"><span data-stu-id="52079-108">If master planning calculates an order date that precedes the current date, the order can't be fulfilled on time.</span></span> <span data-ttu-id="52079-109">Consequentemente, a ordem ficará atrasada.</span><span class="sxs-lookup"><span data-stu-id="52079-109">Therefore, the order is delayed.</span></span> <span data-ttu-id="52079-110">Neste caso, o planejamento mestre antecipado planeja a ordem a partir da data atual e inclui os prazos de entrega.</span><span class="sxs-lookup"><span data-stu-id="52079-110">In this case, master planning forward-plans the order from the current date and includes lead times.</span></span> <span data-ttu-id="52079-111">Esses prazos de entrega começam com qualquer item de componente de nível inferior.</span><span class="sxs-lookup"><span data-stu-id="52079-111">These lead times start with any lower-level component items.</span></span> <span data-ttu-id="52079-112">A ordem então recebe uma data atrasada.</span><span class="sxs-lookup"><span data-stu-id="52079-112">The order then receives a delayed date.</span></span> <span data-ttu-id="52079-113">Uma data atrasada é uma data de vencimento realista baseada na data atual.</span><span class="sxs-lookup"><span data-stu-id="52079-113">A delayed date is a realistic due date, based on the current data.</span></span> <span data-ttu-id="52079-114">O planejamento mestre também calcula o número de dias de atraso.</span><span class="sxs-lookup"><span data-stu-id="52079-114">Master planning also calculates the number of delay days.</span></span> 

<span data-ttu-id="52079-115">Em algumas situações, você poderá optar por não calcular os atrasos, como quando os usuários souberem que podem acelerar os prazos de entrega selecionando modos de entrega alternativos.</span><span class="sxs-lookup"><span data-stu-id="52079-115">In some situations, you might choose not to calculate delays, such as when users know that they can expedite lead times by selecting alternative modes of delivery.</span></span> 

<span data-ttu-id="52079-116">Você pode configurar como os atrasos são calculados para um grupo de cobertura.</span><span class="sxs-lookup"><span data-stu-id="52079-116">You can configure how delays are calculated for a coverage group.</span></span> <span data-ttu-id="52079-117">Você pode então associar o grupo de cobertura a um item posteriormente.</span><span class="sxs-lookup"><span data-stu-id="52079-117">You can then attach the coverage group to an item later.</span></span> 

<span data-ttu-id="52079-118">Na página **Parâmetros de planejamento mestre**, você pode definir a hora de início para o cálculo de atrasos.</span><span class="sxs-lookup"><span data-stu-id="52079-118">On the **Master planning parameters** page, you can set the start time for the calculation of delays.</span></span> <span data-ttu-id="52079-119">Se uma ordem for atendida após esse horário, um atraso de um dia será adicionado à data de atraso da ordem.</span><span class="sxs-lookup"><span data-stu-id="52079-119">If an order is fulfilled after this time, a delay of one day is added to the delay date of the order.</span></span> 

<span data-ttu-id="52079-120">**Observação:** em versões anteriores, os atrasos calculados eram conhecidos como *mensagens futuras*, a data atrasada era conhecida como as *datas futuras* e uma transação atrasada foi mencionada como *uma transação definida no futuro*.</span><span class="sxs-lookup"><span data-stu-id="52079-120">**Note:** In earlier versions, calculated delays were known as *futures messages*, the delayed date was known as the *futures date*, and a delayed transaction was referred to as *a transaction that was future set*.</span></span>

<a name="see-also"></a><span data-ttu-id="52079-121">Consulte também</span><span class="sxs-lookup"><span data-stu-id="52079-121">See also</span></span>
--------

[<span data-ttu-id="52079-122">Configurações de cobertura</span><span class="sxs-lookup"><span data-stu-id="52079-122">Coverage settings</span></span>](coverage-settings.md)





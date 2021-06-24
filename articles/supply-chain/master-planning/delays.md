---
title: Atrasos
description: Este tópico fornece informações sobre as datas em atraso no planejamento mestre. Uma data posterior é uma data de vencimento realista que uma transação recebe se a data de preenchimento mais recente que o planejamento mestre calcula é posterior a data solicitada.
author: roxanadiaconu
ms.date: 03/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqTransFuturesListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a8e863ae63466f68e763b133da9f0e9488c6cfa6
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "6189337"
---
# <a name="delays"></a><span data-ttu-id="0a32b-104">Atrasos</span><span class="sxs-lookup"><span data-stu-id="0a32b-104">Delays</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0a32b-105">Este tópico fornece informações sobre as datas em atraso no planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="0a32b-105">This topic provides information about delayed dates in master planning.</span></span> <span data-ttu-id="0a32b-106">Uma data posterior é uma data de vencimento realista que uma transação recebe se a data de preenchimento mais recente que o planejamento mestre calcula é posterior a data solicitada.</span><span class="sxs-lookup"><span data-stu-id="0a32b-106">A delayed date is a realistic due date that a transaction receives if the earliest fulfillment date that master planning calculates is later than the requested date.</span></span>

<span data-ttu-id="0a32b-107">O planejamento mestre pode calcular a data de término de vigência mais antiga para uma transação com base nos prazos de entrega, na disponibilidade material, na disponibilidade de capacidade e em vários parâmetros de planejamento.</span><span class="sxs-lookup"><span data-stu-id="0a32b-107">Master planning can calculate the earliest fulfillment date for a transaction, based on lead times, material availability, capacity availability, and various planning parameters.</span></span> 

<span data-ttu-id="0a32b-108">Se o planejamento mestre calcular a data de uma ordem como anterior à data atual, a ordem não poderá ser atendida a tempo.</span><span class="sxs-lookup"><span data-stu-id="0a32b-108">If master planning calculates an order date that precedes the current date, the order can't be fulfilled on time.</span></span> <span data-ttu-id="0a32b-109">Consequentemente, a ordem ficará atrasada.</span><span class="sxs-lookup"><span data-stu-id="0a32b-109">Therefore, the order is delayed.</span></span> <span data-ttu-id="0a32b-110">Neste caso, o planejamento mestre antecipado planeja a ordem a partir da data atual e inclui os prazos de entrega.</span><span class="sxs-lookup"><span data-stu-id="0a32b-110">In this case, master planning forward-plans the order from the current date and includes lead times.</span></span> <span data-ttu-id="0a32b-111">Esses prazos de entrega começam com qualquer item de componente de nível inferior.</span><span class="sxs-lookup"><span data-stu-id="0a32b-111">These lead times start with any lower-level component items.</span></span> <span data-ttu-id="0a32b-112">A ordem então recebe uma data atrasada.</span><span class="sxs-lookup"><span data-stu-id="0a32b-112">The order then receives a delayed date.</span></span> <span data-ttu-id="0a32b-113">Uma data atrasada é uma data de vencimento realista baseada na data atual.</span><span class="sxs-lookup"><span data-stu-id="0a32b-113">A delayed date is a realistic due date, based on the current data.</span></span> <span data-ttu-id="0a32b-114">O planejamento mestre também calcula o número de dias de atraso.</span><span class="sxs-lookup"><span data-stu-id="0a32b-114">Master planning also calculates the number of delay days.</span></span> 

<span data-ttu-id="0a32b-115">Em algumas situações, você poderá optar por não calcular os atrasos, como quando os usuários souberem que podem acelerar os prazos de entrega selecionando modos de entrega alternativos.</span><span class="sxs-lookup"><span data-stu-id="0a32b-115">In some situations, you might choose not to calculate delays, such as when users know that they can expedite lead times by selecting alternative modes of delivery.</span></span> 

<span data-ttu-id="0a32b-116">Você pode configurar como os atrasos são calculados para um grupo de cobertura.</span><span class="sxs-lookup"><span data-stu-id="0a32b-116">You can configure how delays are calculated for a coverage group.</span></span> <span data-ttu-id="0a32b-117">Você pode então associar o grupo de cobertura a um item posteriormente.</span><span class="sxs-lookup"><span data-stu-id="0a32b-117">You can then attach the coverage group to an item later.</span></span> 

<span data-ttu-id="0a32b-118">Na página **Parâmetros de planejamento mestre**, você pode definir a hora de início para o cálculo de atrasos.</span><span class="sxs-lookup"><span data-stu-id="0a32b-118">On the **Master planning parameters** page, you can set the start time for the calculation of delays.</span></span> <span data-ttu-id="0a32b-119">Se uma ordem for atendida após esse horário, um atraso de um dia será adicionado à data de atraso da ordem.</span><span class="sxs-lookup"><span data-stu-id="0a32b-119">If an order is fulfilled after this time, a delay of one day is added to the delay date of the order.</span></span> 

> [!NOTE]
> <span data-ttu-id="0a32b-120">Nas versões anteriores, os atrasos calculados eram conhecidos como *mensagens futuras*, a data atrasada era conhecida como *datas futuras* e uma transação atrasada foi mencionada como *uma transação definida no futuro*.</span><span class="sxs-lookup"><span data-stu-id="0a32b-120">In earlier versions, calculated delays were known as *futures messages*, the delayed date was known as the *futures date*, and a delayed transaction was referred to as *a transaction that was future set*.</span></span>

## <a name="limited-delays-in-production-setup-with-multiple-bom-levels"></a><span data-ttu-id="0a32b-121">Atrasos limitados na configuração da produção com vários níveis de BOM</span><span class="sxs-lookup"><span data-stu-id="0a32b-121">Limited delays in production setup with multiple BOM levels</span></span>
<span data-ttu-id="0a32b-122">Ao trabalhar com atrasos em uma configuração de produção que tem vários níveis de BOM, é importante observar que somente os itens diretamente acima do item (na estrutura da BOM) que causam o atraso, serão atualizados com um atraso como parte da execução do planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="0a32b-122">When you work with delays in a production setup that has multiple BOM levels, it is important to note that only the items directly above the item (in the BOM structure) causing the delay, will be updated with a delay as part of the master planning run.</span></span> <span data-ttu-id="0a32b-123">Os outros itens na estrutura da BOM não receberão o atraso aplicado até que o primeiro planejamento mestre seja executado, quando a ordem planejada para o nível superior for aprovada ou confirmada.</span><span class="sxs-lookup"><span data-stu-id="0a32b-123">Other items in the BOM structure will not get the delay applied until the first master planning run, when the planned order for the top level is approved or firmed.</span></span> 

<span data-ttu-id="0a32b-124">Para solucionar essa limitação conhecida, as ordens de produção no topo da estrutura da BOM com atrasos podem ser aprovadas (ou confirmadas) antes da próxima execução do planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="0a32b-124">To work around this known limitation, the production orders on the top of the BOM structure with delays can be approved (or firmed) prior to the next master planning run.</span></span> <span data-ttu-id="0a32b-125">Dessa forma, o atraso da ordem de produção planejada atrasada aprovada será mantido e todos os componentes subjacentes serão atualizados de acordo.</span><span class="sxs-lookup"><span data-stu-id="0a32b-125">This way the delay from the delayed approved planned production order will be kept and all underlying components will be updated accordingly.</span></span>
<span data-ttu-id="0a32b-126">As mensagens de ação também podem ser usadas para identificar ordens planejadas que podem ser movidas para uma data posterior, devido a outros atrasos na estrutura da BOM.</span><span class="sxs-lookup"><span data-stu-id="0a32b-126">Action messages can also be used to identify planned orders that can be moved to a later date, due to other delays in the BOM structure.</span></span>

## <a name="desired-date"></a><span data-ttu-id="0a32b-127">Data desejada</span><span class="sxs-lookup"><span data-stu-id="0a32b-127">Desired date</span></span>

<span data-ttu-id="0a32b-128">Na página **Ordem planejada**, a guia **Atrasos** mostra a **Data desejada** da ordem planejada.</span><span class="sxs-lookup"><span data-stu-id="0a32b-128">On the **Planned order** page, under the **Delays** tab is the **Desired date** for the planned order.</span></span> <span data-ttu-id="0a32b-129">A data desejada de uma ordem planejada é a data base para atrasos, que é uma data calculada equivalente à **Data da solicitação** calculada com base na **Necessidade Líquida**.</span><span class="sxs-lookup"><span data-stu-id="0a32b-129">The desired date of a planned order is the base date for delays, which is a computed date that equals the **Requested date** calculated from the **Net Requirement**.</span></span> <span data-ttu-id="0a32b-130">Se a ordem planejada for uma linha de BOM, linha de produção ou linha kanban, a data desejada será baseada na **Data da necessidade** e a data desejada não será exibida na página **Ordem planejada**.</span><span class="sxs-lookup"><span data-stu-id="0a32b-130">If the planned order is a BOM line, production line or kanban line, the desired date is based on the **Requirement date** and the desired date will not be shown on the **Planned order** page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0a32b-131">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="0a32b-131">Additional resources</span></span>

[<span data-ttu-id="0a32b-132">​Configurações de cobertura​</span><span class="sxs-lookup"><span data-stu-id="0a32b-132">Coverage settings</span></span>](coverage-settings.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
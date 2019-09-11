---
title: Calcular a capacidade máxima em ordens de serviço agendadas
description: Este tópico explica como calcular a capacidade máxima em ordens de serviço agendadas no Gerenciamento de Ativos.
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
ms.openlocfilehash: 0c0dd1e306c54d3f99b86ad6f1816d5acabe6c18
ms.sourcegitcommit: f93ead945afe5ae18706c66bce6e64a6b57aac50
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/19/2019
ms.locfileid: "1887150"
---
# <a name="calculate-capacity-load-on-scheduled-work-orders"></a><span data-ttu-id="d091b-103">Calcular a capacidade máxima em ordens de serviço agendadas</span><span class="sxs-lookup"><span data-stu-id="d091b-103">Calculate capacity load on scheduled work orders</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="d091b-104">Você pode calcular a capacidade máxima em ordens de serviço agendadas para obter uma visão geral da carga de trabalho nos recursos por um período específico.</span><span class="sxs-lookup"><span data-stu-id="d091b-104">You can calculate capacity load on scheduled work orders to get an overview of the work load on resources for a specific period.</span></span> <span data-ttu-id="d091b-105">Os cálculos podem ser feitos para os seguintes recursos: trabalhadores de manutenção, grupos de trabalhadores, ferramentas e ativos.</span><span class="sxs-lookup"><span data-stu-id="d091b-105">Calculations can be made for the following resources: Maintenance workers, worker groups, tools, and assets.</span></span>

1. <span data-ttu-id="d091b-106">Clique em **Gerenciamento de ativos** > **Consultas** > **Agendar** > **Capacidade máxima**.</span><span class="sxs-lookup"><span data-stu-id="d091b-106">Click **Asset management** > **Inquiries** > **Schedule** > **Capacity load**.</span></span>

2. <span data-ttu-id="d091b-107">Na caixa de diálogo **Calcular a capacidade máxima** > campo **Mostrar**, selecione o tipo de carga que deseja calcular: "Capacidade", "Reservado" ou "Pendência".</span><span class="sxs-lookup"><span data-stu-id="d091b-107">In the **Calculate capacity load** dialog > **Show** field, select which load type you want to calculate: "Capacity", "Reserved", or "Remainder".</span></span>

3. <span data-ttu-id="d091b-108">Selecione "Sim" no botão de alternância **Ignorar zero** se não desejar exibir resultados contendo zero.</span><span class="sxs-lookup"><span data-stu-id="d091b-108">Select "Yes" on the **Skip zero** toggle button if you do not want to show results containing zero.</span></span>

4. <span data-ttu-id="d091b-109">Selecione os tipos de recursos para os quais deseja calcular a capacidade máxima, selecionando "Sim" nos botões de alternância relevantes: **Trabalhador**, **Grupo de funcionários de manutenção**, **Ferramenta** e **Ativo**.</span><span class="sxs-lookup"><span data-stu-id="d091b-109">Select the resource types for which you want to calculate capacity load by selecting "Yes" on the relevant toggle buttons: **Worker**, **Maintenance worker group**, **Tool**, and **Asset**.</span></span>

5. <span data-ttu-id="d091b-110">Selecione a data de início para o cálculo no campo **Data inicial**.</span><span class="sxs-lookup"><span data-stu-id="d091b-110">Select the start date for the calculation in the **From date** field.</span></span>

6. <span data-ttu-id="d091b-111">No campo **Tipo de intervalo**, selecione o intervalo para o cálculo: "Dia", "Semana", "Mês" ou "Trimestre".</span><span class="sxs-lookup"><span data-stu-id="d091b-111">In the **Interval type** field, select the interval for the calculation: "Day", "Week", "Month", or "Quarter".</span></span>

7. <span data-ttu-id="d091b-112">No campo **Frequência do período**, insira o número de intervalos que deseja calcular.</span><span class="sxs-lookup"><span data-stu-id="d091b-112">In the **Period frequency** field, insert the number of intervals you want to calculate.</span></span> <span data-ttu-id="d091b-113">Por exemplo, se você selecionou "Dia" como o tipo de intervalo e inseriu o número "5" nesse campo, será feito um cálculo de cinco dias a partir da data inicial.</span><span class="sxs-lookup"><span data-stu-id="d091b-113">For example, if you have selected "Day" as the interval type, and you insert the number "5" in this field, a calculation of five days from the start date will be made.</span></span>

8. <span data-ttu-id="d091b-114">Clique em **OK**para iniciar o cálculo.</span><span class="sxs-lookup"><span data-stu-id="d091b-114">Click **OK** to start the calculation.</span></span>

<span data-ttu-id="d091b-115">A figura abaixo mostra o resultado de um cálculo que abrange três semanas para o tipo de carga "Reservado".</span><span class="sxs-lookup"><span data-stu-id="d091b-115">The figure below shows the result of a calculation covering three weeks for the load type "Reserved".</span></span>

![Figura 1](media/08-work-order-scheduling.png)

>[!NOTE]
><span data-ttu-id="d091b-117">Se você selecionar os tipos de carga "Capacidade" ou "Restante" para o cálculo, o mesmo resultado será exibido se nenhuma reserva tiver sido feita para os recursos no período selecionado.</span><span class="sxs-lookup"><span data-stu-id="d091b-117">If you select the load types "Capacity" or "Remainder" for your calculation, the same result will be displayed if no reservations have been made for the resources in the selected period.</span></span>

<span data-ttu-id="d091b-118">Consulte [Calcular a capacidade máxima](../capacity-planning/calculate-capacity-load.md) para obter informações sobre como calcular a capacidade máxima nas linhas de programação de manutenção e ordens de serviço não agendadas.</span><span class="sxs-lookup"><span data-stu-id="d091b-118">Refer to [Calculate capacity load](../capacity-planning/calculate-capacity-load.md) for information on how to calculate capacity load on maintenance schedule lines and not scheduled work orders.</span></span>


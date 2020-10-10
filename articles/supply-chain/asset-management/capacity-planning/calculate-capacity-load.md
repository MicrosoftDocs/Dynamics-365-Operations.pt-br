---
title: Calcular a capacidade máxima
description: Este tópico explica como calcular a capacidade máxima no Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetCapacityLoad, EntAssetWorkOrderCapacityLoadCalculate, EntAssetWorkOrderCapacityLoad
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5015955338a4cbc2b51585d6297756f20dccee8b
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2020
ms.locfileid: "3888729"
---
# <a name="calculate-capacity-load"></a><span data-ttu-id="90e35-103">Calcular a capacidade máxima</span><span class="sxs-lookup"><span data-stu-id="90e35-103">Calculate capacity load</span></span>

[!include [banner](../../includes/banner.md)]


<span data-ttu-id="90e35-104">No Gerenciamento de Ativos, você pode calcular a capacidade máxima em:</span><span class="sxs-lookup"><span data-stu-id="90e35-104">In Asset Management, you can calculate capacity load on:</span></span>

- <span data-ttu-id="90e35-105">linhas do agendamento de manutenção</span><span class="sxs-lookup"><span data-stu-id="90e35-105">maintenance schedule lines</span></span>  
- <span data-ttu-id="90e35-106">ordens de serviço que ainda não foram agendadas</span><span class="sxs-lookup"><span data-stu-id="90e35-106">work orders that have not yet been scheduled</span></span>  
- <span data-ttu-id="90e35-107">ordens de serviço agendadas</span><span class="sxs-lookup"><span data-stu-id="90e35-107">scheduled work orders</span></span>

<span data-ttu-id="90e35-108">Isso é útil para obter uma visão geral da capacidade máxima esperada por um período específico.</span><span class="sxs-lookup"><span data-stu-id="90e35-108">This is useful if you want to get an overview of expected capacity load for a specific period.</span></span> <span data-ttu-id="90e35-109">O cálculo da capacidade máxima pode ser feito em todos os ativos ou ativos selecionados.</span><span class="sxs-lookup"><span data-stu-id="90e35-109">Calculation of capacity load can be done on all assets or selected assets.</span></span> <span data-ttu-id="90e35-110">Você também pode fazer um cálculo sobre atividades de tempo de inatividade de manutenção ou conjuntos de ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="90e35-110">You can also make a calculation on maintenance downtime activities or work order pools.</span></span>

1. <span data-ttu-id="90e35-111">Clique em **Gerenciamento de ativos** > **Consultas** > **Capacidade máxima** ou **Gerenciamento de ativos** > **Comum** > **Grupos de ordens de serviço** > **Todos os grupos de ordens de serviço** / **Grupos de ordens de serviço ativos** > selecione o grupo de ordens de serviço na lista > botão **Capacidade máxima** ou **Gerenciamento de ativos** > **Comum** > **Atividades de tempo de inatividade de manutenção** > **Todas as atividades de inatividade de manutenção** / **Grupos de ordens de serviço ativos** > selecione a atividade de manutenção na lista > botão **Capacidade máxima**.</span><span class="sxs-lookup"><span data-stu-id="90e35-111">Click **Asset management** > **Inquiries** > **Capacity load**, or **Asset management** > **Common** > **Work order pools** > **All work order pools** / **Active work order pools** > select work order pool in the list > **Capacity load** button, or **Asset management** > **Common** > **Maintenance downtime activities** > **All maintenance downtime activities** / **Active maintenance downtime activities** > select maintenance activity in the list > **Capacity load** button.</span></span>

2. <span data-ttu-id="90e35-112">Na caixa de diálogo **Calcular capacidade máxima**, selecione um período para o cálculo nos campos **Data/hora inicial** e **Data/hora final**.</span><span class="sxs-lookup"><span data-stu-id="90e35-112">In the **Calculate capacity load** dialog, select a period for the calculation in the **Start date/time** and **End date/time** fields.</span></span>

3. <span data-ttu-id="90e35-113">Selecione "Sim" no botão **Incluir agendamento de manutenção** para incluir as linhas do agendamento de manutenção no cálculo.</span><span class="sxs-lookup"><span data-stu-id="90e35-113">Select "Yes" on the **Include maintenance schedule** toggle button if you want to include maintenance schedule lines in the calculation.</span></span>

4. <span data-ttu-id="90e35-114">Selecione "Sim" no botão **Incluir ordem de serviço** para alternar entre os trabalhos de ordem de serviço no cálculo.</span><span class="sxs-lookup"><span data-stu-id="90e35-114">Select "Yes" on the **Include work order** toggle button if you want to include work order jobs in the calculation.</span></span>

5. <span data-ttu-id="90e35-115">Você pode usar o campo **Nível** para indicar o nível de detalhamento desejado das linhas de capacidade máxima em relação aos locais funcionais.</span><span class="sxs-lookup"><span data-stu-id="90e35-115">You can use the **Level** field to indicate how detailed you want the capacity load lines to be regarding functional locations.</span></span> 

    <span data-ttu-id="90e35-116">Por exemplo, se você inserir o número "1" no campo e tiver uma estrutura de local funcional de vários níveis, todas as linhas de agendamento de manutenção e ordens de serviço de um local funcional serão mostradas no nível superior e, portanto, as horas de uma linha podem ser adicionadas dos locais funcionais localizados em nível inferior.</span><span class="sxs-lookup"><span data-stu-id="90e35-116">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all maintenance schedule lines and work orders for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> 
    
    <span data-ttu-id="90e35-117">Se você inserir o número "0" no campo **Nível**, verá um resultado detalhado mostrando todas as linhas do agendamento de manutenção e todas as ordens de serviço em todos os níveis do local funcional ao qual elas estão relacionadas.</span><span class="sxs-lookup"><span data-stu-id="90e35-117">If you insert the number "0" in the **Level** field, you will see a detailed result showing all maintenance schedule lines and all work orders on all the functional location levels to which they are related.</span></span>

6. <span data-ttu-id="90e35-118">Clique em **OK**para iniciar o cálculo.</span><span class="sxs-lookup"><span data-stu-id="90e35-118">Click **OK** to start the calculation.</span></span>

7. <span data-ttu-id="90e35-119">Nos grupos **Agrupar por...**, clique nos botões relevantes para mostrar o nível de detalhe necessário do cálculo.</span><span class="sxs-lookup"><span data-stu-id="90e35-119">In the **Group by...** groups, click the relevant buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="90e35-120">Na captura de tela abaixo, os botões **Agrupar por** são realçados em azul.</span><span class="sxs-lookup"><span data-stu-id="90e35-120">In the screenshot below, the selected **Group by** buttons are highlighted in blue color.</span></span> <span data-ttu-id="90e35-121">Clique em um botão para ativá-los ou desativá-los.</span><span class="sxs-lookup"><span data-stu-id="90e35-121">Click on a button to activate or deactivate it.</span></span>

    ![Figura 1](media/01-capacity-planning.png)

>[!NOTE]
><span data-ttu-id="90e35-123">Se você deseja se concentrar apenas no planejamento de capacidade em relação às ordens de serviço agendadas, consulte [Calcular a capacidade máxima em ordens de serviço agendadas](../work-order-scheduling/calculate-capacity-load-on-scheduled-work-orders.md).</span><span class="sxs-lookup"><span data-stu-id="90e35-123">If you want to focus only on capacity planning regarding scheduled work orders, see [Calculate capacity load on scheduled work orders](../work-order-scheduling/calculate-capacity-load-on-scheduled-work-orders.md).</span></span>


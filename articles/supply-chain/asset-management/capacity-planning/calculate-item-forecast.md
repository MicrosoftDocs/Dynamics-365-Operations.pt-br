---
title: Calcular previsão de itens
description: Este tópico explica como calcular a previsão de itens no Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetItemForecast
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f8f38ac7bfb270f648cd561da50ee5477721ab47
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2020
ms.locfileid: "3888704"
---
# <a name="calculate-item-forecast"></a><span data-ttu-id="e3994-103">Calcular previsão de itens</span><span class="sxs-lookup"><span data-stu-id="e3994-103">Calculate item forecast</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="e3994-104">Da mesma forma que você pode fazer cálculos de capacidade máxima, descritos na seção anterior, também é possível fazer cálculos de previsão de itens em:</span><span class="sxs-lookup"><span data-stu-id="e3994-104">Just as you can make capacity load calculations, which are described in the previous section, you can also make item forecast calculations on:</span></span>

- <span data-ttu-id="e3994-105">linhas do agendamento de manutenção</span><span class="sxs-lookup"><span data-stu-id="e3994-105">maintenance schedule lines</span></span>  
- <span data-ttu-id="e3994-106">ordens de serviço que ainda não foram agendadas</span><span class="sxs-lookup"><span data-stu-id="e3994-106">work orders that have not yet been scheduled</span></span>  
- <span data-ttu-id="e3994-107">ordens de serviço agendadas</span><span class="sxs-lookup"><span data-stu-id="e3994-107">scheduled work orders</span></span>

<span data-ttu-id="e3994-108">Isso é útil se você deseja obter uma visão geral do consumo esperado de itens (peças sobressalentes e outros itens necessários para concluir as ordens de serviço) por um período específico.</span><span class="sxs-lookup"><span data-stu-id="e3994-108">This is useful if you want to get an overview of expected item consumption (spare parts as well as other items required for completing work orders) for a specific period.</span></span> <span data-ttu-id="e3994-109">O cálculo da previsão do item pode ser feito em todos os ativos ou ativos selecionados.</span><span class="sxs-lookup"><span data-stu-id="e3994-109">Calculation of item forecast can be done on all assets or selected assets.</span></span> <span data-ttu-id="e3994-110">Também é possível fazer um cálculo em uma atividade de tempo de inatividade de manutenção (**Todas as atividades de inatividade de manutenção** ou **Atividades de inatividade de manutenção ativa**) ou em um conjunto de ordens de serviço (**Todos os grupos de ordens de serviço** ou **Grupos de ordens de serviço ativos**).</span><span class="sxs-lookup"><span data-stu-id="e3994-110">You can also make a calculation on a maintenance downtime activity (**All maintenance downtime activities** or **Active maintenance downtime activities**), or on a work order pool (**All work order pools** or **Active work order pools**).</span></span>

1. <span data-ttu-id="e3994-111">Clique em **Gerenciamento de ativos** > **Consultas** > **Previsão de item** ou **Gerenciamento de ativos** > **Comum** > **Grupos de ordens de serviço** > **Todos os grupos de ordens de serviço** / **Grupos de ordens de serviço ativos** > selecione o grupo de ordens de serviço na lista > botão **Previsão de Item** ou **Gerenciamento de ativos** > **Comum** > **Atividades de tempo de inatividade de manutenção** > **Todas as atividades de inatividade de manutenção** / **Grupos de ordens de serviço ativos** > selecione a atividade de tempo de inatividade de manutenção na lista > botão **Previsão de item**.</span><span class="sxs-lookup"><span data-stu-id="e3994-111">Click **Asset management** > **Inquiries** > **Item forecast**, or **Asset management** > **Common** > **Work order pools** > **All work order pools** / **Active work order pools** > select work order pool in the list > **Item forecast** button, or **Asset management** > **Common** > **Maintenance downtime activities** > **All maintenance downtime activities** / **Active maintenance downtime activities** > select maintenance downtime activity in the list > **Item forecast** button.</span></span>

2. <span data-ttu-id="e3994-112">Na caixa de diálogo **Calcular previsão de itens**, selecione um período para o cálculo nos campos **Data/hora inicial** e **Data/hora final**.</span><span class="sxs-lookup"><span data-stu-id="e3994-112">In the **Calculate item forecast** dialog, select a period for the calculation in the **Start date/time** and **End date/time** fields.</span></span>

3. <span data-ttu-id="e3994-113">Selecione "Sim" no botão **Incluir agendamento de manutenção** para incluir as linhas do agendamento de manutenção no cálculo da previsão.</span><span class="sxs-lookup"><span data-stu-id="e3994-113">Select "Yes" on the **Include maintenance schedule** toggle button if you want to include maintenance schedule lines in the forecast calculation.</span></span>

4. <span data-ttu-id="e3994-114">Selecione "Sim" no botão **Incluir ordem de serviço** para alternar entre os trabalhos de ordem de serviço no cálculo da previsão.</span><span class="sxs-lookup"><span data-stu-id="e3994-114">Select "Yes" on the **Include work order** toggle button if you want to include work order jobs in the forecast calculation.</span></span>

5. <span data-ttu-id="e3994-115">Você pode usar o campo **Nível** para indicar o nível de detalhamento desejado das linhas de previsão de item em relação aos locais funcionais.</span><span class="sxs-lookup"><span data-stu-id="e3994-115">You can use the **Level** field to indicate how detailed you want the item forecast lines to be regarding functional locations.</span></span> 

      <span data-ttu-id="e3994-116">Por exemplo, se você inserir o número "1" no campo e tiver uma estrutura de local funcional de vários níveis, todas as linhas de agendamento de manutenção e ordens de serviço de um local funcional serão mostradas no nível superior e, portanto, as horas de uma linha podem ser adicionadas dos locais funcionais localizados em nível inferior.</span><span class="sxs-lookup"><span data-stu-id="e3994-116">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all maintenance schedule lines and work orders for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> 
  
      <span data-ttu-id="e3994-117">Se você inserir o número "0" no campo **Nível**, verá um resultado detalhado mostrando todas as linhas do agendamento de manutenção e todas as ordens de serviço em todos os níveis do local funcional ao qual elas estão relacionadas.</span><span class="sxs-lookup"><span data-stu-id="e3994-117">If you insert the number "0" in the **Level** field, you will see a detailed result showing all maintenance schedule lines and all work orders on all the functional location level to which they are related.</span></span>

6. <span data-ttu-id="e3994-118">Clique em **OK**para iniciar o cálculo.</span><span class="sxs-lookup"><span data-stu-id="e3994-118">Click **OK** to start the calculation.</span></span>

7. <span data-ttu-id="e3994-119">Nos grupos **Agrupar por...**, clique nos botões relevantes para mostrar o nível de detalhe necessário do cálculo.</span><span class="sxs-lookup"><span data-stu-id="e3994-119">In the **Group by...** groups, click the relevant buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="e3994-120">Na captura de tela abaixo, os botões **Agrupar por** são realçados em azul.</span><span class="sxs-lookup"><span data-stu-id="e3994-120">In the screenshot below, the selected **Group by** buttons are highlighted in blue color.</span></span> <span data-ttu-id="e3994-121">Clique em um botão para ativá-los ou desativá-los.</span><span class="sxs-lookup"><span data-stu-id="e3994-121">Click on a button to activate or deactivate it.</span></span>

8. <span data-ttu-id="e3994-122">Clique no botão **Exibir dimensões** se desejar ver as dimensões do produto, armazenamento ou rastreamento relacionadas aos itens.</span><span class="sxs-lookup"><span data-stu-id="e3994-122">Click the **Display dimensions** button if you want to see the product, storage, or tracking dimensions related to the items.</span></span> <span data-ttu-id="e3994-123">Marque as caixas de seleção relevantes e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3994-123">Select the relevant check boxes, and click **OK**.</span></span>

![Figura 1](media/02-capacity-planning.png)

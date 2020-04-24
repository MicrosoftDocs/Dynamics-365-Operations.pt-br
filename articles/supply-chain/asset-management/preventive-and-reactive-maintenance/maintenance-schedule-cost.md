---
title: Custo do agendamento de manutenção
description: Este tópico explica o custo de agendamento de manutenção no Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8feea75bb223bdbd013b11cdf3a63d504afb04f5
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3208193"
---
# <a name="maintenance-schedule-cost"></a><span data-ttu-id="0653b-103">Custo do agendamento de manutenção</span><span class="sxs-lookup"><span data-stu-id="0653b-103">Maintenance schedule cost</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="0653b-104">No Gerenciamento de Ativos você pode calcular os custos de orçamento nas linhas de agendamento de manutenção.</span><span class="sxs-lookup"><span data-stu-id="0653b-104">In Asset Management, you can calculate budget costs on maintenance schedule lines.</span></span> <span data-ttu-id="0653b-105">Isso é útil se você quiser obter uma visão geral dos custos esperados, por exemplo, os custos relacionados aos trabalhos de manutenção preventiva planejados para o próximo ano.</span><span class="sxs-lookup"><span data-stu-id="0653b-105">This is useful if you want to get an overview of expected costs, for example, costs relating to planned preventive maintenance jobs for the next year.</span></span> <span data-ttu-id="0653b-106">Os cálculos são baseados nas linhas de agendamento de manutenção existente do tipo "Planos de manutenção" e "Rounds de manutenção" e "Solicitações de manutenção".</span><span class="sxs-lookup"><span data-stu-id="0653b-106">The calculations are based on existing maintenance schedule lines of type "Maintenance plans" and "Maintenance rounds" and "Maintenance requests".</span></span>

1. <span data-ttu-id="0653b-107">Clique em **Gerenciamento de ativos** > **Consultas** > **Ativos** > **Custo de agendamento de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="0653b-107">Click **Asset management** > **Inquiries** > **Assets** > **Maintenance schedule cost**.</span></span>

2. <span data-ttu-id="0653b-108">Na caixa de diálogo **Custo de agendamento de manutenção**, é possível selecionar um **Conjunto de dimensões financeiras** se você quiser ver os custos agrupados nas dimensões financeiras.</span><span class="sxs-lookup"><span data-stu-id="0653b-108">In the **Maintenance schedule cost** dialog, you can select a **Financial dimension set** if you want to see costs grouped in financial dimensions.</span></span>

>[!NOTE]
><span data-ttu-id="0653b-109">Os conjuntos da dimensão financeira são configurados na **Contabilidade** > **Planos de contas** > **Dimensões** > **Conjuntos de dimensões financeiras**.</span><span class="sxs-lookup"><span data-stu-id="0653b-109">Financial dimension sets are set up in **General ledger** > **Chart of accounts** > **Dimensions** > **Financial dimension sets**.</span></span>

3. <span data-ttu-id="0653b-110">Você pode usar o campo **Nível** para indicar o quão detalhado você deseja que as linhas de agendamento de manutenção sejam relativas aos locais funcionais.</span><span class="sxs-lookup"><span data-stu-id="0653b-110">You can use the **Level** field to indicate how detailed you want the maintenance schedule lines to be regarding functional locations.</span></span> <span data-ttu-id="0653b-111">Por exemplo, se você inserir o número "1" no campo e tiver uma estrutura de local funcional de vários níveis, todas as linhas de agendamento de manutenção de um local funcional serão mostradas no nível superior e, portanto, as horas de uma linha podem ser adicionadas dos locais funcionais localizados em nível inferior.</span><span class="sxs-lookup"><span data-stu-id="0653b-111">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all maintenance schedule lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> <span data-ttu-id="0653b-112">Se você inserir o número "0" no campo **Nível**, verá um resultado detalhado mostrando todas as linhas de agendamento de manutenção em todos os níveis do local funcional ao qual elas estão relacionadas.</span><span class="sxs-lookup"><span data-stu-id="0653b-112">If you insert the number "0" in the **Level** field, you will see a detailed result showing all maintenance schedule lines on all the functional location levels to which they are related.</span></span>

4. <span data-ttu-id="0653b-113">Se quiser fazer um cálculo para ativos específicos, clique em **Filtro** na Guia Rápida **Registros a serem incluídos** e selecione os ativos relevantes.</span><span class="sxs-lookup"><span data-stu-id="0653b-113">If you want to make a calculation for specific assets, click **Filter** on the **Records to include** FastTab, and select the relevant assets.</span></span> <span data-ttu-id="0653b-114">Se necessário, você também pode especificar uma data de **Início esperado** para o cálculo de custo ou selecionar um **Status** diferente para o cálculo de custo.</span><span class="sxs-lookup"><span data-stu-id="0653b-114">If required, you can also specify an **Expected start** date for the cost calculation or select a different **Status** for the cost calculation</span></span>

5. <span data-ttu-id="0653b-115">Clique em **OK**para iniciar o cálculo de custo.</span><span class="sxs-lookup"><span data-stu-id="0653b-115">Click **OK** to start the cost calculation.</span></span>

6. <span data-ttu-id="0653b-116">Na guia **Custo de agendamento de manutenção** > nos grupos do painel de ação **Agrupar por...**, clique nos botões relevantes para mostrar o nível de detalhe necessário do cálculo de custo.</span><span class="sxs-lookup"><span data-stu-id="0653b-116">On the **Maintenance schedule cost** tab > in the **Group by...** action pane groups, click the relevant buttons to show the required detail level of the cost calculation.</span></span> <span data-ttu-id="0653b-117">Os botões do grupo do painel de ação selecionado estão destacados.</span><span class="sxs-lookup"><span data-stu-id="0653b-117">The selected action pane group buttons are highlighted.</span></span> <span data-ttu-id="0653b-118">Clique em um botão para ativá-los ou desativá-los.</span><span class="sxs-lookup"><span data-stu-id="0653b-118">Click on a button to activate or deactivate it.</span></span>

7. <span data-ttu-id="0653b-119">Clique no botão **Calcular custo** se quiser fazer um novo cálculo de custo.</span><span class="sxs-lookup"><span data-stu-id="0653b-119">Click the **Calculate cost** button if you want to make a new cost calculation.</span></span>

<span data-ttu-id="0653b-120">A ilustração a seguir mostra os resultados do cálculo de custo de um agendamento de manutenção.</span><span class="sxs-lookup"><span data-stu-id="0653b-120">The illustration below shows the results of a maintenance schedule cost calculation.</span></span>

![Figura 1](media/17-preventive-maintenance.png)


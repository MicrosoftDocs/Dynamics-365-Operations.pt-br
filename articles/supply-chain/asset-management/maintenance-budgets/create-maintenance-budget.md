---
title: Criar orçamentos de manutenção
description: Este tópico explica como criar um orçamento de manutenção em Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetBudgetLineAdjust, EntAssetBudget, EntAssetBudgetRecalc, EntAssetBudgetCopy, EntAssetBudgetLine, EntAssetBudgetCreate, EntAssetBudgetApprove, EntAssetBudgetCalculateActualCost
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 593a03e3317de5759427dfc61093530c4b7ef7e9
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5253485"
---
# <a name="create-maintenance-budgets"></a><span data-ttu-id="e9c66-103">Criar orçamentos de manutenção</span><span class="sxs-lookup"><span data-stu-id="e9c66-103">Create maintenance budgets</span></span>

[!include [banner](../../includes/banner.md)]

 



<span data-ttu-id="e9c66-104">Os orçamentos de manutenção são usados para fornecer uma visão geral dos custos esperados para manutenção preventiva.</span><span class="sxs-lookup"><span data-stu-id="e9c66-104">Maintenance budgets are used to provide an overview of expected costs for preventive maintenance.</span></span> <span data-ttu-id="e9c66-105">As linhas de orçamento são calculadas com base nas linhas de agendamento de manutenção que têm uma data de início prevista durante o período do orçamento.</span><span class="sxs-lookup"><span data-stu-id="e9c66-105">Budget lines are calculated based on maintenance schedule lines that have an expected start date during the budget period.</span></span>

<span data-ttu-id="e9c66-106">Os orçamentos de manutenção são baseados nos tipos de custo usados no Gerenciamento de Ativos: **Preventivo**, **Corretivo** e **Investimento**.</span><span class="sxs-lookup"><span data-stu-id="e9c66-106">Maintenance budgets are based on the cost types that are used in Asset Management: **Preventive**, **Corrective**, and **Investment**.</span></span> <span data-ttu-id="e9c66-107">Os custos do orçamento para manutenção do investimento são incluídos para ativos que têm uma data de substituição durante o período do orçamento e um valor de substituição relacionado.</span><span class="sxs-lookup"><span data-stu-id="e9c66-107">Budget costs for investment maintenance are included for active assets that have a replacement date during the budget period and a related replacement value.</span></span> <span data-ttu-id="e9c66-108">Os custos do orçamento para manutenção corretiva serão incluídos se uma data corretiva anterior for incluída no cálculo do orçamento.</span><span class="sxs-lookup"><span data-stu-id="e9c66-108">Budget costs for corrective maintenance are included if a past corrective date is included in the budget calculation.</span></span> <span data-ttu-id="e9c66-109">Nesse caso, os custos corretivos de um período anterior são calculados para o mesmo período futuro para o qual você calcula o orçamento de manutenção.</span><span class="sxs-lookup"><span data-stu-id="e9c66-109">In that case, corrective costs from an earlier period are calculated for the same future period that you calculate the maintenance budget for.</span></span>

## <a name="create-a-maintenance-budget"></a><span data-ttu-id="e9c66-110">Criar um orçamento de manutenção</span><span class="sxs-lookup"><span data-stu-id="e9c66-110">Create a maintenance budget</span></span>

1. <span data-ttu-id="e9c66-111">Selecione **Gerenciamento de ativos** \> **Consultas** \> **Orçamentos de manutenção** \> **Orçamento**.</span><span class="sxs-lookup"><span data-stu-id="e9c66-111">Select **Asset management** \> **Inquiries** \> **Maintenance budget** \> **Budget**.</span></span>
2. <span data-ttu-id="e9c66-112">Selecione **Criar orçamento**.</span><span class="sxs-lookup"><span data-stu-id="e9c66-112">Select **Create budget**.</span></span>
3. <span data-ttu-id="e9c66-113">No campo **Orçamento de manutenção**, insira uma ID de orçamento.</span><span class="sxs-lookup"><span data-stu-id="e9c66-113">In the **Maintenance budget** field, enter a budget ID.</span></span>
4. <span data-ttu-id="e9c66-114">No campo **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="e9c66-114">In the **Description** field, enter a description.</span></span>
4. <span data-ttu-id="e9c66-115">Na Guia Rápida **Período**, nos campos **Data inicial** e **Data final**, insira as datas de início e término do período do orçamento.</span><span class="sxs-lookup"><span data-stu-id="e9c66-115">On the **Period** FastTab, in the **From date** and **To date** fields, enter the start and end dates of the budget period.</span></span>
5. <span data-ttu-id="e9c66-116">Para incluir custos orçamentários corretivos que são calculados com base nos custos reais de um período anterior, no campo **Data inicial corretiva**, insira a data de início do período em que esses custos devem ser incluídos.</span><span class="sxs-lookup"><span data-stu-id="e9c66-116">To include corrective budget costs that are calculated on the basis of actual costs from a previous period, in the **Corrective from date** field, enter the start date of the period that those costs should be included from.</span></span>
6. <span data-ttu-id="e9c66-117">Dependendo do nível de detalhes necessário no orçamento, defina as opções relevantes nas cinco Guias Rápidas **Agrupar por**.</span><span class="sxs-lookup"><span data-stu-id="e9c66-117">Depending on the level of detail that is required in the budget, set the relevant options on the five **Group by** FastTabs.</span></span>
7. <span data-ttu-id="e9c66-118">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9c66-118">Select **OK**.</span></span>
8. <span data-ttu-id="e9c66-119">Selecione **Linhas de orçamento** para abrir a página **Linhas de orçamento de manutenção**, onde você pode exibir todas as linhas de orçamento que foram criadas para o período.</span><span class="sxs-lookup"><span data-stu-id="e9c66-119">Select **Budget lines** to open **Maintenance budget lines** page, where you can view all the budget lines that have been created for the period.</span></span>
9. <span data-ttu-id="e9c66-120">Para aprovar o orçamento, selecione-o na página **Orçamentos de manutenção** e selecione **Aprovar**.</span><span class="sxs-lookup"><span data-stu-id="e9c66-120">To approve the budget, select it on the **Maintenance budgets** page, and then select **Approve**.</span></span> <span data-ttu-id="e9c66-121">Em seguida, na caixa de diálogo **Aprovar orçamento**, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9c66-121">Then, in the **Approve budget** dialog box, select **OK**.</span></span> <span data-ttu-id="e9c66-122">Seu nome é inserido no campo **Aprovado por** na página **Orçamentos de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="e9c66-122">Your name is entered in the **Approved by** field on the **Maintenance budgets** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e9c66-123">Depois de aprovar um orçamento de manutenção, você não poderá recalcular ou ajustar as linhas relacionadas na página **Linhas de orçamento de manutenção**, a menos que primeiro remova a aprovação.</span><span class="sxs-lookup"><span data-stu-id="e9c66-123">After you've approved a maintenance budget, you can't recalculate or adjust the related lines on the **Maintenance budget lines** page unless you first remove the approval.</span></span> <span data-ttu-id="e9c66-124">Para remover a aprovação de um orçamento de manutenção, selecione-o na página **Orçamentos de manutenção** e selecione **Aprovar**.</span><span class="sxs-lookup"><span data-stu-id="e9c66-124">To remove the approval of a maintenance budget, select it on the **Maintenance budgets** page, and then select **Approve**.</span></span> <span data-ttu-id="e9c66-125">Em seguida, na caixa de diálogo **Aprovar orçamento**, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9c66-125">Then, in the **Approve budget** dialog box, select **OK**.</span></span>

![Orçamentos de Manutenção](media/01-maintenance-budgets.png)

<span data-ttu-id="e9c66-127">Também é possível criar um orçamento de manutenção, copiando um orçamento existente.</span><span class="sxs-lookup"><span data-stu-id="e9c66-127">You can also create a new maintenance budget by copying an existing budget.</span></span> <span data-ttu-id="e9c66-128">Na página **Orçamentos de manutenção**, selecione o orçamento a ser copiado e selecione **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="e9c66-128">On the **Maintenance budgets** page, select the budget to copy, and then select **Copy**.</span></span> <span data-ttu-id="e9c66-129">Essa abordagem é útil se, por exemplo, você criou um orçamento para um mês e deseja copiá-lo para outros meses.</span><span class="sxs-lookup"><span data-stu-id="e9c66-129">This approach is useful if, for example, you've created a budget for one month and want to copy it to other months.</span></span>

> [!NOTE]
> <span data-ttu-id="e9c66-130">O orçamento de manutenção calcula apenas os custos com base nas linhas de agendamento de manutenção.</span><span class="sxs-lookup"><span data-stu-id="e9c66-130">The maintenance budget calculates only budget costs based on maintenance schedule lines.</span></span> <span data-ttu-id="e9c66-131">Para calcular custos reais para o mesmo período, você pode fazer esse cálculo na página **Controle de custos de ativos**.</span><span class="sxs-lookup"><span data-stu-id="e9c66-131">To calculate actual costs for the same period, you can do that calculation on the **Asset cost control** page.</span></span> 


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
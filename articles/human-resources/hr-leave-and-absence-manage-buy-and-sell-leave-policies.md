---
title: Gerenciar políticas de licença de compra e venda
description: Você pode habilitar funcionários a comprar e vender licenças no Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeaveBuySellPolicy, LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 55d29c42cc1b2d69517e2fcd458ee6a1bdf5277f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4417337"
---
# <a name="manage-buy-and-sell-leave-policies"></a><span data-ttu-id="a384b-103">Gerenciar políticas de compra e venda de licenças</span><span class="sxs-lookup"><span data-stu-id="a384b-103">Manage buy and sell leave policies</span></span>

<span data-ttu-id="a384b-104">Você pode permitir que os funcionários comprem e vendam licenças criando uma política de licença de compra e venda.</span><span class="sxs-lookup"><span data-stu-id="a384b-104">You can enable employees to buy and sell leave by creating a buy and sell leave policy.</span></span> <span data-ttu-id="a384b-105">Você pode configurar essas políticas para usar o fluxo de trabalho para aprovações, definir valores e taxas máximos e definir taxas para compras e vendas.</span><span class="sxs-lookup"><span data-stu-id="a384b-105">You can configure these policies to use workflow for approvals, set maximum amounts and rates, and set rates for buying and selling.</span></span> 

## <a name="enable-employees-to-buy-and-sell-leave"></a><span data-ttu-id="a384b-106">Habilitar funcionários a comprar e vender licenças</span><span class="sxs-lookup"><span data-stu-id="a384b-106">Enable employees to buy and sell leave</span></span>

1. <span data-ttu-id="a384b-107">Na página **Parâmetros de licença e ausência**, selecione **Sim** para **Permitir que os funcionários comprem licenças** e **Permitir que os funcionários vendam licenças**.</span><span class="sxs-lookup"><span data-stu-id="a384b-107">On the **Leave and absence parameters** page, select **Yes** for **Allow employees to buy leave** and **Allow employees to sell leave**.</span></span>

## <a name="create-a-buy-and-sell-leave-policy"></a><span data-ttu-id="a384b-108">Criar uma política de compra e venda de licenças</span><span class="sxs-lookup"><span data-stu-id="a384b-108">Create a buy and sell leave policy</span></span>

1. <span data-ttu-id="a384b-109">Na página **Licença e ausência**, selecione a guia **Links**.</span><span class="sxs-lookup"><span data-stu-id="a384b-109">On the **Leave and absence** page, select the **Links** tab.</span></span> 

2. <span data-ttu-id="a384b-110">Selecione a **Política de licença de compra e venda**.</span><span class="sxs-lookup"><span data-stu-id="a384b-110">Select **Buy and sell leave policy**.</span></span>

3. <span data-ttu-id="a384b-111">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="a384b-111">Select **New**.</span></span>

4. <span data-ttu-id="a384b-112">Insira um **Nome** e uma **Descrição** para a política em **Política de licença de compra e venda**.</span><span class="sxs-lookup"><span data-stu-id="a384b-112">Enter a **Name** and **Description** for the policy under **Buy and sell leave policy**.</span></span> 

5. <span data-ttu-id="a384b-113">Selecione um **Tipo de política**.</span><span class="sxs-lookup"><span data-stu-id="a384b-113">Select a **Policy type**.</span></span> 

   <span data-ttu-id="a384b-114">Os tipos de política disponíveis são **Valor** e **Horas por semana**.</span><span class="sxs-lookup"><span data-stu-id="a384b-114">The available policy types are **Amount** and **Hours per week**.</span></span> <span data-ttu-id="a384b-115">Selecione **Valor** para inserir um **Valor fixo** para os valores máximos que os funcionários podem comprar e vender.</span><span class="sxs-lookup"><span data-stu-id="a384b-115">Select **Amount** to enter a **Fixed amount** for the maximum amounts employees can buy and sell.</span></span> <span data-ttu-id="a384b-116">Se você selecionar **Horas por semana**, o período de trabalho definido no calendário de horário de trabalho atribuído do funcionário será usado para determinar o valor máximo da política.</span><span class="sxs-lookup"><span data-stu-id="a384b-116">If you select **Hours per week**, the working time defined in the employee's assigned working time calendar is used to determine the maximum amount of the policy.</span></span> 

6. <span data-ttu-id="a384b-117">Selecione uma **Data inicial** e uma **Data final** para a política.</span><span class="sxs-lookup"><span data-stu-id="a384b-117">Select a **Start date** and **End date** for the policy.</span></span> <span data-ttu-id="a384b-118">As solicitações para comprar ou vender licenças só estarão disponíveis para envio durante esse período.</span><span class="sxs-lookup"><span data-stu-id="a384b-118">Requests to buy or sell leave will only be available for submission during this time frame.</span></span> 

7. <span data-ttu-id="a384b-119">Selecione uma **ID de fluxo de trabalho** para a política.</span><span class="sxs-lookup"><span data-stu-id="a384b-119">Select a **Workflow ID** for the policy.</span></span> <span data-ttu-id="a384b-120">As solicitações de compra e venda usarão este fluxo de trabalho para revisão e aprovação.</span><span class="sxs-lookup"><span data-stu-id="a384b-120">Any buy and sell requests will use this workflow for review and approval.</span></span> 

8. <span data-ttu-id="a384b-121">Em **Política de compra**, selecione **Equivalência de tempo integral** (FTE) para rateio do valor máximo com base no FTE definido na posição do funcionário.</span><span class="sxs-lookup"><span data-stu-id="a384b-121">Under **Buy policy**, select **Full time equivalency** (FTE) to prorate the maximum amount based on the FTE defined on the employee's position.</span></span> <span data-ttu-id="a384b-122">Se o tipo de política for **Valor**, insira um **Valor fixo máximo**.</span><span class="sxs-lookup"><span data-stu-id="a384b-122">If the policy type is **Amount**, enter a **Maximum fixed amount**.</span></span> 

9. <span data-ttu-id="a384b-123">Selecione **Adicionar** para adicionar os tipos de licença para funcionários comprarem licenças.</span><span class="sxs-lookup"><span data-stu-id="a384b-123">Select **Add** to add the leave types for employees to buy leave.</span></span> <span data-ttu-id="a384b-124">Você pode adicionar vários tipos de licença à política.</span><span class="sxs-lookup"><span data-stu-id="a384b-124">You can add multiple leave types to the policy.</span></span> 

10. <span data-ttu-id="a384b-125">Insira os **Meses de serviço** do tipo de licença para habilitar diferentes meses de serviço para determinar o valor máximo que um funcionário pode comprar.</span><span class="sxs-lookup"><span data-stu-id="a384b-125">Enter the **Months of service** for the leave type to enable different months of service to determine the maximum amount an employee can buy.</span></span> 

11. <span data-ttu-id="a384b-126">Insira o **Valor máximo** para o tipo de licença.</span><span class="sxs-lookup"><span data-stu-id="a384b-126">Enter the **Maximum amount** for the leave type.</span></span> 

12. <span data-ttu-id="a384b-127">Insira a **Taxa** na qual o funcionário comprará a licença.</span><span class="sxs-lookup"><span data-stu-id="a384b-127">Enter the **Rate** at which the employee will buy the leave.</span></span> 

13. <span data-ttu-id="a384b-128">Opcionalmente, insira o **Código de ganhos** a ser usado para comprar a licença.</span><span class="sxs-lookup"><span data-stu-id="a384b-128">Optionally enter the **Earning code** to be used for buying leave.</span></span> 

14. <span data-ttu-id="a384b-129">Opcionalmente, defina se o FTE deve ser usado para determinar o valor máximo para o tipo de licença.</span><span class="sxs-lookup"><span data-stu-id="a384b-129">Optionally set whether to use FTE to determine the maximum amount for the leave type.</span></span> 

15. <span data-ttu-id="a384b-130">Para criar uma política de venda, siga as etapas 8 a 14 na **Política de venda**.</span><span class="sxs-lookup"><span data-stu-id="a384b-130">To create a sell policy, follow steps 8 through 14 under **Sell policy**.</span></span> 

## <a name="add-the-buy-and-sell-leave-policy-to-a-leave-and-absence-plan"></a><span data-ttu-id="a384b-131">Adicionar a política de licença de compra e venda a um plano de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="a384b-131">Add the buy and sell leave policy to a leave and absence plan</span></span>

1. <span data-ttu-id="a384b-132">Na página **Licença e ausência**, selecione um plano de licença e ausência.</span><span class="sxs-lookup"><span data-stu-id="a384b-132">On the **Leave and absence** page, select a leave and absence plan.</span></span>

2. <span data-ttu-id="a384b-133">Em **Regras**, selecione a **Política de licença de compra e venda**.</span><span class="sxs-lookup"><span data-stu-id="a384b-133">Under **Rules**, select **Buy and sell leave policy**.</span></span>

## <a name="see-also"></a><span data-ttu-id="a384b-134">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a384b-134">See also</span></span>

[<span data-ttu-id="a384b-135">Visão geral de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="a384b-135">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)</br>
[<span data-ttu-id="a384b-136">Configurar tipos de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="a384b-136">Configure leave and absence types</span></span>](hr-leave-and-absence-types.md)</br>
[<span data-ttu-id="a384b-137">Acumular planos de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="a384b-137">Accrue leave and absence plans</span></span>](hr-leave-and-absence-accrue.md)</br>
[<span data-ttu-id="a384b-138">Comprar e vender licenças</span><span class="sxs-lookup"><span data-stu-id="a384b-138">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)


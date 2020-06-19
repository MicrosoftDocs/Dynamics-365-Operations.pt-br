---
title: Gerenciar políticas de licença de compra e venda
description: Você pode habilitar funcionários a comprar e vender licenças no Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 06/01/2020
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
ms.openlocfilehash: 859445f2b6e980b5960e512e69129f6a8fc6df2b
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2020
ms.locfileid: "3429004"
---
# <a name="manage-buy-and-sell-leave-policies"></a><span data-ttu-id="8bfb9-103">Gerenciar políticas de licença de compra e venda</span><span class="sxs-lookup"><span data-stu-id="8bfb9-103">Manage buy and sell leave policies</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="8bfb9-104">Você pode permitir que os funcionários comprem licenças criando uma política de licença de compra.</span><span class="sxs-lookup"><span data-stu-id="8bfb9-104">You can enable employees to buy leave by creating a buy leave policy.</span></span>  

## <a name="enable-employees-to-buy-and-sell-leave"></a><span data-ttu-id="8bfb9-105">Habilitar funcionários a comprar e vender licenças</span><span class="sxs-lookup"><span data-stu-id="8bfb9-105">Enable employees to buy and sell leave</span></span>

1. <span data-ttu-id="8bfb9-106">Na página **Parâmetros de licença e ausência**, selecione **Sim** para **Permitir que os funcionários comprem licenças**.</span><span class="sxs-lookup"><span data-stu-id="8bfb9-106">On the **Leave and absence parameters** page, select **Yes** for **Allow employees to buy leave**.</span></span> 

## <a name="create-a-buy-leave-policy"></a><span data-ttu-id="8bfb9-107">Criar uma política de licença de compra</span><span class="sxs-lookup"><span data-stu-id="8bfb9-107">Create a buy leave policy</span></span>

1. <span data-ttu-id="8bfb9-108">Na página **Licença e ausência**, selecione a guia **Links**.</span><span class="sxs-lookup"><span data-stu-id="8bfb9-108">On the **Leave and absence** page, select the **Links** tab.</span></span> 

2. <span data-ttu-id="8bfb9-109">Selecione a **Política de licença de compra e venda**.</span><span class="sxs-lookup"><span data-stu-id="8bfb9-109">Select **Buy and sell leave policy**.</span></span>

3. <span data-ttu-id="8bfb9-110">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="8bfb9-110">Select **New**.</span></span>

4. <span data-ttu-id="8bfb9-111">Insira um **Nome** e uma **Descrição** para a política em **Política de licença de compra e venda**.</span><span class="sxs-lookup"><span data-stu-id="8bfb9-111">Enter a **Name** and **Description** for the policy under **Buy and sell leave policy**.</span></span> 

5. <span data-ttu-id="8bfb9-112">Selecione um **Tipo de política**.</span><span class="sxs-lookup"><span data-stu-id="8bfb9-112">Select a **Policy type**.</span></span> 

   <span data-ttu-id="8bfb9-113">Os tipos de política disponíveis são **Valor** e **Horas por semana**.</span><span class="sxs-lookup"><span data-stu-id="8bfb9-113">The available policy types are **Amount** and **Hours per week**.</span></span> <span data-ttu-id="8bfb9-114">Selecione **Valor** para inserir um **Valor fixo** para os valores máximos que os funcionários podem comprar e vender.</span><span class="sxs-lookup"><span data-stu-id="8bfb9-114">Select **Amount** to enter a **Fixed amount** for the maximum amounts employees can buy and sell.</span></span> <span data-ttu-id="8bfb9-115">Se você selecionar **Horas por semana**, o período de trabalho definido no calendário de horário de trabalho atribuído do funcionário será usado para determinar o valor máximo da política.</span><span class="sxs-lookup"><span data-stu-id="8bfb9-115">If you select **Hours per week**, the working time defined in the employee's assigned working time calendar is used to determine the maximum amount of the policy.</span></span> 

6. <span data-ttu-id="8bfb9-116">Selecione uma **Data inicial** e uma **Data final** para a política.</span><span class="sxs-lookup"><span data-stu-id="8bfb9-116">Select a **Start date** and **End date** for the policy.</span></span> <span data-ttu-id="8bfb9-117">As solicitações para comprar ou vender licenças só estarão disponíveis para envio durante esse período.</span><span class="sxs-lookup"><span data-stu-id="8bfb9-117">Requests to buy or sell leave will only be available for submission during this time frame.</span></span> 

7. <span data-ttu-id="8bfb9-118">Em **Política de compra**, selecione **Equivalência de tempo integral** (FTE) para rateio do valor máximo com base no FTE definido na posição do funcionário.</span><span class="sxs-lookup"><span data-stu-id="8bfb9-118">Under **Buy policy**, select **Full time equivalency** (FTE) to prorate the maximum amount based on the FTE defined on the employee's position.</span></span> <span data-ttu-id="8bfb9-119">Se o tipo de política for **Valor**, insira um **Valor fixo máximo**.</span><span class="sxs-lookup"><span data-stu-id="8bfb9-119">If the policy type is **Amount**, enter a **Maximum fixed amount**.</span></span> 

8. <span data-ttu-id="8bfb9-120">Selecione **Adicionar** para adicionar os tipos de licença para funcionários comprarem licenças.</span><span class="sxs-lookup"><span data-stu-id="8bfb9-120">Select **Add** to add the leave types for employees to buy leave.</span></span> <span data-ttu-id="8bfb9-121">Você pode adicionar vários tipos de licença à política.</span><span class="sxs-lookup"><span data-stu-id="8bfb9-121">You can add multiple leave types to the policy.</span></span> 

9. <span data-ttu-id="8bfb9-122">Insira os **Meses de serviço** do tipo de licença para habilitar diferentes meses de serviço para determinar o valor máximo que um funcionário pode comprar.</span><span class="sxs-lookup"><span data-stu-id="8bfb9-122">Enter the **Months of service** for the leave type to enable different months of service to determine the maximum amount an employee can buy.</span></span> 

10. <span data-ttu-id="8bfb9-123">Insira o **Valor máximo** para o tipo de licença.</span><span class="sxs-lookup"><span data-stu-id="8bfb9-123">Enter the **Maximum amount** for the leave type.</span></span> 

11. <span data-ttu-id="8bfb9-124">Insira a **Taxa** na qual o funcionário comprará a licença.</span><span class="sxs-lookup"><span data-stu-id="8bfb9-124">Enter the **Rate** at which the employee will buy the leave.</span></span> 

12. <span data-ttu-id="8bfb9-125">Opcionalmente, insira o **Código de ganhos** a ser usado para comprar a licença.</span><span class="sxs-lookup"><span data-stu-id="8bfb9-125">Optionally enter the **Earning code** to be used for buying leave.</span></span> 

13. <span data-ttu-id="8bfb9-126">Opcionalmente, defina se o FTE deve ser usado para determinar o valor máximo para o tipo de licença.</span><span class="sxs-lookup"><span data-stu-id="8bfb9-126">Optionally set whether to use FTE to determine the maximum amount for the leave type.</span></span> 

## <a name="add-the-buy-and-sell-leave-policy-to-a-leave-and-absence-plan"></a><span data-ttu-id="8bfb9-127">Adicionar a política de licença de compra e venda a um plano de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="8bfb9-127">Add the buy and sell leave policy to a leave and absence plan</span></span>

1. <span data-ttu-id="8bfb9-128">Na página **Licença e ausência**, selecione um plano de licença e ausência.</span><span class="sxs-lookup"><span data-stu-id="8bfb9-128">On the **Leave and absence** page, select a leave and absence plan.</span></span>

2. <span data-ttu-id="8bfb9-129">Em **Regras**, selecione a **Política de licença de compra e venda**.</span><span class="sxs-lookup"><span data-stu-id="8bfb9-129">Under **Rules**, select **Buy and sell leave policy**.</span></span>

## <a name="see-also"></a><span data-ttu-id="8bfb9-130">Consulte também</span><span class="sxs-lookup"><span data-stu-id="8bfb9-130">See also</span></span>

[<span data-ttu-id="8bfb9-131">Visão geral de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="8bfb9-131">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)</br>
[<span data-ttu-id="8bfb9-132">Configurar tipos de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="8bfb9-132">Configure leave and absence types</span></span>](hr-leave-and-absence-types.md)</br>
[<span data-ttu-id="8bfb9-133">Acumular planos de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="8bfb9-133">Accrue leave and absence plans</span></span>](hr-leave-and-absence-accrue.md)</br>
[<span data-ttu-id="8bfb9-134">Comprar e vender licenças</span><span class="sxs-lookup"><span data-stu-id="8bfb9-134">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)


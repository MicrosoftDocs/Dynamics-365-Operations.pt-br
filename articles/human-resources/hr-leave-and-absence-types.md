---
title: Configurar tipos de licença e ausência
description: Configurar tipos de licença que os funcionários podem executar no Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6b21d4d631bcdf603b38212f5f76bb78937d3d3c
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2021
ms.locfileid: "5115067"
---
# <a name="configure-leave-and-absence-types"></a><span data-ttu-id="ad08b-103">Configurar tipos de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="ad08b-103">Configure leave and absence types</span></span>

<span data-ttu-id="ad08b-104">Os tipos de licenças no Dynamics 365 Human Resources definem os tipos de ausências que os funcionários podem relatar.</span><span class="sxs-lookup"><span data-stu-id="ad08b-104">Leave types in Dynamics 365 Human Resources define the types of absences that employees can report.</span></span> <span data-ttu-id="ad08b-105">Você pode personalizar os tipos de licença de acordo com as necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="ad08b-105">You can tailor leave types according to the needs of your organization.</span></span> <span data-ttu-id="ad08b-106">Exemplos de tipos de licença incluem:</span><span class="sxs-lookup"><span data-stu-id="ad08b-106">Examples of leave types include:</span></span>

- <span data-ttu-id="ad08b-107">Folga remunerada (PTO)</span><span class="sxs-lookup"><span data-stu-id="ad08b-107">Paid time off (PTO)</span></span>
- <span data-ttu-id="ad08b-108">Licença não remunerada</span><span class="sxs-lookup"><span data-stu-id="ad08b-108">Unpaid leave</span></span>
- <span data-ttu-id="ad08b-109">Férias remuneradas</span><span class="sxs-lookup"><span data-stu-id="ad08b-109">Paid vacation</span></span>
- <span data-ttu-id="ad08b-110">Ausência por motivo de doença</span><span class="sxs-lookup"><span data-stu-id="ad08b-110">Sick leave</span></span>
- <span data-ttu-id="ad08b-111">Licença médica</span><span class="sxs-lookup"><span data-stu-id="ad08b-111">Medical leave</span></span>
- <span data-ttu-id="ad08b-112">Licença de família</span><span class="sxs-lookup"><span data-stu-id="ad08b-112">Family leave</span></span>
- <span data-ttu-id="ad08b-113">Incapacidade temporária</span><span class="sxs-lookup"><span data-stu-id="ad08b-113">Short-term disability</span></span>
- <span data-ttu-id="ad08b-114">Licença óbito</span><span class="sxs-lookup"><span data-stu-id="ad08b-114">Bereavement leave</span></span>

## <a name="add-a-leave-type"></a><span data-ttu-id="ad08b-115">Adicionar um tipo de licença</span><span class="sxs-lookup"><span data-stu-id="ad08b-115">Add a leave type</span></span>

1. <span data-ttu-id="ad08b-116">Na página **Licença e ausência**, selecione a guia **Links**.</span><span class="sxs-lookup"><span data-stu-id="ad08b-116">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="ad08b-117">Em **Configuração**, selecione **Tipos de licença e ausência**.</span><span class="sxs-lookup"><span data-stu-id="ad08b-117">Under **Setup**, select **Leave and absence types**.</span></span>

3. <span data-ttu-id="ad08b-118">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="ad08b-118">Select **New**.</span></span>

4. <span data-ttu-id="ad08b-119">Digite um nome para o tipo de licença em **Tipo**, selecione um fluxo de trabalho em **ID do fluxo de trabalho** e digite uma descrição em **Descrição**.</span><span class="sxs-lookup"><span data-stu-id="ad08b-119">Enter a name for the leave type under **Type**, select a workflow from **Workflow ID**, and enter a description under **Description**.</span></span>

5. <span data-ttu-id="ad08b-120">Em **Geral**, selecione **Nenhum**, **Agendado** ou **Não agendado** no menu suspenso **Categoria**.</span><span class="sxs-lookup"><span data-stu-id="ad08b-120">In **General**, select **None**, **Scheduled**, or **Unscheduled** from the **Category** dropdown.</span></span>

6. <span data-ttu-id="ad08b-121">Selecione um código de ganhos no menu suspenso **Código de ganhos**.</span><span class="sxs-lookup"><span data-stu-id="ad08b-121">Select an earning code from the **Earning code** dropdown.</span></span>

7. <span data-ttu-id="ad08b-122">Em **Código de motivo obrigatório**, escolha se deseja exigir um código de motivo.</span><span class="sxs-lookup"><span data-stu-id="ad08b-122">Under **Reason code required**, choose whether you want to require a reason code.</span></span> <span data-ttu-id="ad08b-123">Se desejar exigir códigos de motivo, talvez seja necessário adicioná-los.</span><span class="sxs-lookup"><span data-stu-id="ad08b-123">If you want to require reason codes, you might need to add them.</span></span> <span data-ttu-id="ad08b-124">Em **Códigos de motivo**, selecione **Adicionar**, selecione um código de motivo e marque a caixa de seleção **Habilitado** ao lado dele.</span><span class="sxs-lookup"><span data-stu-id="ad08b-124">Under **Reason codes**, select **Add**, select a reason code, and then select the **Enabled** checkbox next to it.</span></span>

8. <span data-ttu-id="ad08b-125">Em **Restringir acesso a funções selecionadas**, escolha se deseja restringir o acesso.</span><span class="sxs-lookup"><span data-stu-id="ad08b-125">Under **Restrict access to selected roles**, choose whether you want to restrict access.</span></span> <span data-ttu-id="ad08b-126">Em seguida, selecione as funções de segurança em **Funções de segurança para este tipo de licença**.</span><span class="sxs-lookup"><span data-stu-id="ad08b-126">Then select the security roles under **Security roles for this leave type**.</span></span> <span data-ttu-id="ad08b-127">As funções de segurança são definidas no fluxo de trabalho selecionado em **ID do fluxo de trabalho**, que vimos antes neste procedimento.</span><span class="sxs-lookup"><span data-stu-id="ad08b-127">The security roles are defined in the workflow you selected under **Workflow ID** earlier in this procedure.</span></span>

9. <span data-ttu-id="ad08b-128">Em **Cor do calendário**, escolha a cor a ser exibida nos calendários de licença e ausência desse tipo de licença.</span><span class="sxs-lookup"><span data-stu-id="ad08b-128">Under **Calendar color**, choose what color to display on leave and absence calendars for this leave type.</span></span> 

10. <span data-ttu-id="ad08b-129">Em **Relações de suspensão**, escolha se você deseja que esse tipo de licença suspenda outro tipo de licença ou seja suspenso por outro tipo de licença.</span><span class="sxs-lookup"><span data-stu-id="ad08b-129">Under **Suspension relations**, choose if you want to have this leave type either suspend another leave type or be suspended by another leave type.</span></span> <span data-ttu-id="ad08b-130">Quando uma solicitação de licença for enviada para o tipo de licença de suspensão, uma suspensão de licença será automaticamente criada para o tipo de licença suspensa.</span><span class="sxs-lookup"><span data-stu-id="ad08b-130">When a leave of absence request is submitted for the suspending leave type, a leave suspension will automatically be created for the suspended leave type.</span></span> 

10. <span data-ttu-id="ad08b-131">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ad08b-131">Select **Save**.</span></span>

## <a name="configure-leave-type-rules"></a><span data-ttu-id="ad08b-132">Configurar regras de tipo de licença</span><span class="sxs-lookup"><span data-stu-id="ad08b-132">Configure leave type rules</span></span>

1. <span data-ttu-id="ad08b-133">Defina as opções de arredondamento para o tipo de licença.</span><span class="sxs-lookup"><span data-stu-id="ad08b-133">Set rounding options for the leave type.</span></span> <span data-ttu-id="ad08b-134">As opções incluem **Nenhum**, **Para cima**, **Para baixo** e **Mais próximo**.</span><span class="sxs-lookup"><span data-stu-id="ad08b-134">Options include **None**, **Up**, **Down**, and **Nearest**.</span></span> <span data-ttu-id="ad08b-135">Você também pode definir a precisão de arredondamento para o tipo de licença.</span><span class="sxs-lookup"><span data-stu-id="ad08b-135">You can also set rounding precision for the leave type.</span></span>

2. <span data-ttu-id="ad08b-136">Defina a **Correção de feriado** para o tipo de licença.</span><span class="sxs-lookup"><span data-stu-id="ad08b-136">Set **Holiday correction** for the leave type.</span></span> <span data-ttu-id="ad08b-137">Quando você seleciona esta opção, o Human Resources usa o número de feriados que caem em um dia útil para determinar como acumular folgas para o tipo de licença.</span><span class="sxs-lookup"><span data-stu-id="ad08b-137">When you select this option, Human Resources uses the number of holidays that fall on a work day to determine how to accrue time off for the leave type.</span></span> <span data-ttu-id="ad08b-138">Por exemplo, se o dia de Natal cair na segunda-feira, o Human Resources subtrairá um dia do tipo de licença ao processar competências.</span><span class="sxs-lookup"><span data-stu-id="ad08b-138">For example, if Christmas Day falls on a Monday, Human Resources will subtract one day from the leave type when processing accruals.</span></span>

   <span data-ttu-id="ad08b-139">Você pode definir feriados no calendário de horário de trabalho.</span><span class="sxs-lookup"><span data-stu-id="ad08b-139">You set holidays in the working time calendar.</span></span> <span data-ttu-id="ad08b-140">Para obter mais informações, consulte [Criar um calendário de horário de trabalho](hr-leave-and-absence-working-time-calendar.md)</span><span class="sxs-lookup"><span data-stu-id="ad08b-140">For more information, see [Create a working time calendar](hr-leave-and-absence-working-time-calendar.md)</span></span>
   
 3. <span data-ttu-id="ad08b-141">Defina **Postergar tipo de licença** para o tipo de licença.</span><span class="sxs-lookup"><span data-stu-id="ad08b-141">Set **Carry-forward leave type** for the leave type.</span></span> <span data-ttu-id="ad08b-142">Quando você selecionar esta opção, qualquer saldo de postergação será transferido para o tipo de licença especificado.</span><span class="sxs-lookup"><span data-stu-id="ad08b-142">When you select this option, any carry-forward balances will be transferred to the specified leave type.</span></span> <span data-ttu-id="ad08b-143">O tipo de licença de postergação também precisa ser incluído no plano de licença e ausência.</span><span class="sxs-lookup"><span data-stu-id="ad08b-143">The carry-forward leave type also needs to be included in the leave and absence plan.</span></span> 
 
 4. <span data-ttu-id="ad08b-144">Defina **Regras de expiração** para o tipo de licença.</span><span class="sxs-lookup"><span data-stu-id="ad08b-144">Define **Expiration rules** for the leave type.</span></span> <span data-ttu-id="ad08b-145">Ao configurar esta opção, você pode escolher a unidade de dias ou meses e definir a duração da expiração.</span><span class="sxs-lookup"><span data-stu-id="ad08b-145">When you configure this option, you can choose the unit of days or months and set the duration for the expiry.</span></span> <span data-ttu-id="ad08b-146">Você também pode definir a data de efetivação da regra de vencimento.</span><span class="sxs-lookup"><span data-stu-id="ad08b-146">You can also set the effective date of the expiration rule.</span></span> <span data-ttu-id="ad08b-147">Os saldos de licença existentes no momento da expiração serão subtraídos do tipo de licença e serão refletidos no saldo de licença.</span><span class="sxs-lookup"><span data-stu-id="ad08b-147">Any leave balances that exist at the time of expiry will be subtracted from the leave type and will be reflected in the leave balance.</span></span> 
 
 
## <a name="see-also"></a><span data-ttu-id="ad08b-148">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ad08b-148">See also</span></span>

- [<span data-ttu-id="ad08b-149">Visão geral de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="ad08b-149">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
- [<span data-ttu-id="ad08b-150">Criar um plano de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="ad08b-150">Create a leave and absence plan</span></span>](hr-leave-and-absence-plans.md)
- [<span data-ttu-id="ad08b-151">Criar um calendário de horas úteis</span><span class="sxs-lookup"><span data-stu-id="ad08b-151">Create a working time calendar</span></span>](hr-leave-and-absence-working-time-calendar.md)
- [<span data-ttu-id="ad08b-152">Suspender licença</span><span class="sxs-lookup"><span data-stu-id="ad08b-152">Suspend leave</span></span>](hr-leave-and-absence-suspend-leave.md)


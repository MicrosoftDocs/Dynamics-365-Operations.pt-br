---
title: Configurar tipos de licença e ausência
description: Configurar tipos de licença que os funcionários podem executar no Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
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
ms.openlocfilehash: 1802938f54a1d78e6ea60572a76177a037192ae0
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2020
ms.locfileid: "3428584"
---
# <a name="configure-leave-and-absence-types"></a><span data-ttu-id="86be8-103">Configurar tipos de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="86be8-103">Configure leave and absence types</span></span>

<span data-ttu-id="86be8-104">Os tipos de licenças no Dynamics 365 Human Resources definem os tipos de ausências que os funcionários podem relatar.</span><span class="sxs-lookup"><span data-stu-id="86be8-104">Leave types in Dynamics 365 Human Resources define the types of absences that employees can report.</span></span> <span data-ttu-id="86be8-105">Você pode personalizar os tipos de licença de acordo com as necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="86be8-105">You can tailor leave types according to the needs of your organization.</span></span> <span data-ttu-id="86be8-106">Exemplos de tipos de licença incluem:</span><span class="sxs-lookup"><span data-stu-id="86be8-106">Examples of leave types include:</span></span>

- <span data-ttu-id="86be8-107">Folga remunerada (PTO)</span><span class="sxs-lookup"><span data-stu-id="86be8-107">Paid time off (PTO)</span></span>
- <span data-ttu-id="86be8-108">Licença não remunerada</span><span class="sxs-lookup"><span data-stu-id="86be8-108">Unpaid leave</span></span>
- <span data-ttu-id="86be8-109">Férias remuneradas</span><span class="sxs-lookup"><span data-stu-id="86be8-109">Paid vacation</span></span>
- <span data-ttu-id="86be8-110">Ausência por motivo de doença</span><span class="sxs-lookup"><span data-stu-id="86be8-110">Sick leave</span></span>
- <span data-ttu-id="86be8-111">Licença médica</span><span class="sxs-lookup"><span data-stu-id="86be8-111">Medical leave</span></span>
- <span data-ttu-id="86be8-112">Licença de família</span><span class="sxs-lookup"><span data-stu-id="86be8-112">Family leave</span></span>
- <span data-ttu-id="86be8-113">Incapacidade temporária</span><span class="sxs-lookup"><span data-stu-id="86be8-113">Short-term disability</span></span>
- <span data-ttu-id="86be8-114">Licença óbito</span><span class="sxs-lookup"><span data-stu-id="86be8-114">Bereavement leave</span></span>

## <a name="add-a-leave-type"></a><span data-ttu-id="86be8-115">Adicionar um tipo de licença</span><span class="sxs-lookup"><span data-stu-id="86be8-115">Add a leave type</span></span>

1. <span data-ttu-id="86be8-116">Na página **Licença e ausência**, selecione a guia **Links**.</span><span class="sxs-lookup"><span data-stu-id="86be8-116">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="86be8-117">Em **Configuração**, selecione **Tipos de licença e ausência**.</span><span class="sxs-lookup"><span data-stu-id="86be8-117">Under **Setup**, select **Leave and absence types**.</span></span>

3. <span data-ttu-id="86be8-118">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="86be8-118">Select **New**.</span></span>

4. <span data-ttu-id="86be8-119">Digite um nome para o tipo de licença em **Tipo**, selecione um fluxo de trabalho em **ID do fluxo de trabalho** e digite uma descrição em **Descrição**.</span><span class="sxs-lookup"><span data-stu-id="86be8-119">Enter a name for the leave type under **Type**, select a workflow from **Workflow ID**, and enter a description under **Description**.</span></span>

5. <span data-ttu-id="86be8-120">Em **Geral**, selecione **Nenhum**, **Agendado** ou **Não agendado** no menu suspenso **Categoria**.</span><span class="sxs-lookup"><span data-stu-id="86be8-120">In **General**, select **None**, **Scheduled**, or **Unscheduled** from the **Category** dropdown.</span></span>

6. <span data-ttu-id="86be8-121">Selecione um código de ganhos no menu suspenso **Código de ganhos**.</span><span class="sxs-lookup"><span data-stu-id="86be8-121">Select an earning code from the **Earning code** dropdown.</span></span>

7. <span data-ttu-id="86be8-122">Em **Código de motivo obrigatório**, escolha se deseja exigir um código de motivo.</span><span class="sxs-lookup"><span data-stu-id="86be8-122">Under **Reason code required**, choose whether you want to require a reason code.</span></span> <span data-ttu-id="86be8-123">Se desejar exigir códigos de motivo, talvez seja necessário adicioná-los.</span><span class="sxs-lookup"><span data-stu-id="86be8-123">If you want to require reason codes, you might need to add them.</span></span> <span data-ttu-id="86be8-124">Em **Códigos de motivo**, selecione **Adicionar**, selecione um código de motivo e marque a caixa de seleção **Habilitado** ao lado dele.</span><span class="sxs-lookup"><span data-stu-id="86be8-124">Under **Reason codes**, select **Add**, select a reason code, and then select the **Enabled** checkbox next to it.</span></span>

8. <span data-ttu-id="86be8-125">Em **Restringir acesso a funções selecionadas**, escolha se deseja restringir o acesso.</span><span class="sxs-lookup"><span data-stu-id="86be8-125">Under **Restrict access to selected roles**, choose whether you want to restrict access.</span></span> <span data-ttu-id="86be8-126">Em seguida, selecione as funções de segurança em **Funções de segurança para este tipo de licença**.</span><span class="sxs-lookup"><span data-stu-id="86be8-126">Then select the security roles under **Security roles for this leave type**.</span></span> <span data-ttu-id="86be8-127">As funções de segurança são definidas no fluxo de trabalho selecionado em **ID do fluxo de trabalho**, que vimos antes neste procedimento.</span><span class="sxs-lookup"><span data-stu-id="86be8-127">The security roles are defined in the workflow you selected under **Workflow ID** earlier in this procedure.</span></span>

9. <span data-ttu-id="86be8-128">Em **Relações de suspensão**, escolha se você deseja que esse tipo de licença suspenda outro tipo de licença ou seja suspenso por outro tipo de licença.</span><span class="sxs-lookup"><span data-stu-id="86be8-128">Under **Suspension relations**, choose if you want to have this leave type either suspend another leave type or be suspended by another leave type.</span></span> <span data-ttu-id="86be8-129">Quando uma solicitação de licença for enviada para o tipo de licença de suspensão, uma suspensão de licença será automaticamente criada para o tipo de licença suspensa.</span><span class="sxs-lookup"><span data-stu-id="86be8-129">When a leave of absence request is submitted for the suspending leave type, a leave suspension will automatically be created for the suspended leave type.</span></span> 

10. <span data-ttu-id="86be8-130">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="86be8-130">Select **Save**.</span></span>

## <a name="configure-leave-type-rules"></a><span data-ttu-id="86be8-131">Configurar regras de tipo de licença</span><span class="sxs-lookup"><span data-stu-id="86be8-131">Configure leave type rules</span></span>

1. <span data-ttu-id="86be8-132">Defina as opções de arredondamento para o tipo de licença.</span><span class="sxs-lookup"><span data-stu-id="86be8-132">Set rounding options for the leave type.</span></span> <span data-ttu-id="86be8-133">As opções incluem **Nenhum**, **Para cima**, **Para baixo** e **Mais próximo**.</span><span class="sxs-lookup"><span data-stu-id="86be8-133">Options include **None**, **Up**, **Down**, and **Nearest**.</span></span> <span data-ttu-id="86be8-134">Você também pode definir a precisão de arredondamento para o tipo de licença.</span><span class="sxs-lookup"><span data-stu-id="86be8-134">You can also set rounding precision for the leave type.</span></span>

2. <span data-ttu-id="86be8-135">Defina a **Correção de feriado** para o tipo de licença.</span><span class="sxs-lookup"><span data-stu-id="86be8-135">Set **Holiday correction** for the leave type.</span></span> <span data-ttu-id="86be8-136">Quando você seleciona esta opção, o Human Resources usa o número de feriados que caem em um dia útil para determinar como acumular folgas para o tipo de licença.</span><span class="sxs-lookup"><span data-stu-id="86be8-136">When you select this option, Human Resources uses the number of holidays that fall on a work day to determine how to accrue time off for the leave type.</span></span> <span data-ttu-id="86be8-137">Por exemplo, se o dia de Natal cair na segunda-feira, o Human Resources subtrairá um dia do tipo de licença ao processar competências.</span><span class="sxs-lookup"><span data-stu-id="86be8-137">For example, if Christmas Day falls on a Monday, Human Resources will subtract one day from the leave type when processing accruals.</span></span>

   <span data-ttu-id="86be8-138">Você pode definir feriados no calendário de horário de trabalho.</span><span class="sxs-lookup"><span data-stu-id="86be8-138">You set holidays in the working time calendar.</span></span> <span data-ttu-id="86be8-139">Para obter mais informações, consulte [Criar um calendário de horário de trabalho](hr-leave-and-absence-working-time-calendar.md)</span><span class="sxs-lookup"><span data-stu-id="86be8-139">For more information, see [Create a working time calendar](hr-leave-and-absence-working-time-calendar.md)</span></span>
   
 3. <span data-ttu-id="86be8-140">Defina **Postergar tipo de licença** para o tipo de licença.</span><span class="sxs-lookup"><span data-stu-id="86be8-140">Set **Carry-forward leave type** for the leave type.</span></span> <span data-ttu-id="86be8-141">Quando você selecionar esta opção, qualquer saldo de postergação será transferido para o tipo de licença especificado.</span><span class="sxs-lookup"><span data-stu-id="86be8-141">When you select this option, any carry-forward balances will be transferred to the specified leave type.</span></span> <span data-ttu-id="86be8-142">O tipo de licença de postergação também precisa ser incluído no plano de licença e ausência.</span><span class="sxs-lookup"><span data-stu-id="86be8-142">The carry-forward leave type also needs to be included in the leave and absence plan.</span></span> 
 
 4. <span data-ttu-id="86be8-143">Defina **Regras de expiração** para o tipo de licença.</span><span class="sxs-lookup"><span data-stu-id="86be8-143">Define **Expiration rules** for the leave type.</span></span> <span data-ttu-id="86be8-144">Ao configurar esta opção, você pode escolher a unidade de dias ou meses e definir a duração da expiração.</span><span class="sxs-lookup"><span data-stu-id="86be8-144">When you configure this option, you can choose the unit of days or months and set the duration for the expiry.</span></span> <span data-ttu-id="86be8-145">Você também pode definir a data de efetivação da regra de vencimento.</span><span class="sxs-lookup"><span data-stu-id="86be8-145">You can also set the effective date of the expiration rule.</span></span> <span data-ttu-id="86be8-146">Os saldos de licença existentes no momento da expiração serão subtraídos do tipo de licença e serão refletidos no saldo de licença.</span><span class="sxs-lookup"><span data-stu-id="86be8-146">Any leave balances that exist at the time of expiry will be subtracted from the leave type and will be reflected in the leave balance.</span></span> 
 
 
## <a name="see-also"></a><span data-ttu-id="86be8-147">Consulte também</span><span class="sxs-lookup"><span data-stu-id="86be8-147">See also</span></span>

- [<span data-ttu-id="86be8-148">Visão geral de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="86be8-148">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
- [<span data-ttu-id="86be8-149">Criar um plano de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="86be8-149">Create a leave and absence plan</span></span>](hr-leave-and-absence-plans.md)
- [<span data-ttu-id="86be8-150">Criar um calendário de horas úteis</span><span class="sxs-lookup"><span data-stu-id="86be8-150">Create a working time calendar</span></span>](hr-leave-and-absence-working-time-calendar.md)
- [<span data-ttu-id="86be8-151">Suspender licença</span><span class="sxs-lookup"><span data-stu-id="86be8-151">Suspend leave</span></span>](hr-leave-and-absence-suspend-leave.md)


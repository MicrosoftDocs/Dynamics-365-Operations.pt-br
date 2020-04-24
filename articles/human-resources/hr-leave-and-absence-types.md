---
title: Configurar tipos de licença e ausência
description: Configurar tipos de licença que os funcionários podem executar no Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: df6e34fe6a23e6f0a8307a035752a35a15a3431c
ms.sourcegitcommit: 79f8aa2c0b166a423db9b8503da53e96e3fc43dc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2020
ms.locfileid: "3198041"
---
# <a name="configure-leave-and-absence-types"></a><span data-ttu-id="89a87-103">Configurar tipos de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="89a87-103">Configure leave and absence types</span></span>

<span data-ttu-id="89a87-104">Os tipos de licenças no Dynamics 365 Human Resources definem os tipos de ausências que os funcionários podem relatar.</span><span class="sxs-lookup"><span data-stu-id="89a87-104">Leave types in Dynamics 365 Human Resources define the types of absences that employees can report.</span></span> <span data-ttu-id="89a87-105">Você pode personalizar os tipos de licença de acordo com as necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="89a87-105">You can tailor leave types according to the needs of your organization.</span></span> <span data-ttu-id="89a87-106">Exemplos de tipos de licença incluem:</span><span class="sxs-lookup"><span data-stu-id="89a87-106">Examples of leave types include:</span></span>

- <span data-ttu-id="89a87-107">Folga remunerada (PTO)</span><span class="sxs-lookup"><span data-stu-id="89a87-107">Paid time off (PTO)</span></span>
- <span data-ttu-id="89a87-108">Licença não remunerada</span><span class="sxs-lookup"><span data-stu-id="89a87-108">Unpaid leave</span></span>
- <span data-ttu-id="89a87-109">Férias remuneradas</span><span class="sxs-lookup"><span data-stu-id="89a87-109">Paid vacation</span></span>
- <span data-ttu-id="89a87-110">Ausência por motivo de doença</span><span class="sxs-lookup"><span data-stu-id="89a87-110">Sick leave</span></span>
- <span data-ttu-id="89a87-111">Licença médica</span><span class="sxs-lookup"><span data-stu-id="89a87-111">Medical leave</span></span>
- <span data-ttu-id="89a87-112">Licença de família</span><span class="sxs-lookup"><span data-stu-id="89a87-112">Family leave</span></span>
- <span data-ttu-id="89a87-113">Incapacidade temporária</span><span class="sxs-lookup"><span data-stu-id="89a87-113">Short-term disability</span></span>
- <span data-ttu-id="89a87-114">Licença óbito</span><span class="sxs-lookup"><span data-stu-id="89a87-114">Bereavement leave</span></span>

## <a name="add-a-leave-type"></a><span data-ttu-id="89a87-115">Adicionar um tipo de licença</span><span class="sxs-lookup"><span data-stu-id="89a87-115">Add a leave type</span></span>

1. <span data-ttu-id="89a87-116">Na página **Licença e ausência**, selecione a guia **Links**.</span><span class="sxs-lookup"><span data-stu-id="89a87-116">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="89a87-117">Em **Configuração**, selecione **Tipos de licença e ausência**.</span><span class="sxs-lookup"><span data-stu-id="89a87-117">Under **Setup**, select **Leave and absence types**.</span></span>

3. <span data-ttu-id="89a87-118">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="89a87-118">Select **New**.</span></span>

4. <span data-ttu-id="89a87-119">Digite um nome para o tipo de licença em **Tipo**, selecione um fluxo de trabalho em **ID do fluxo de trabalho** e digite uma descrição em **Descrição**.</span><span class="sxs-lookup"><span data-stu-id="89a87-119">Enter a name for the leave type under **Type**, select a workflow from **Workflow ID**, and enter a description under **Description**.</span></span>

5. <span data-ttu-id="89a87-120">Em **Geral**, selecione **Nenhum**, **Agendado** ou **Não agendado** no menu suspenso **Categoria**.</span><span class="sxs-lookup"><span data-stu-id="89a87-120">In **General**, select **None**, **Scheduled**, or **Unscheduled** from the **Category** dropdown.</span></span>

6. <span data-ttu-id="89a87-121">Selecione um código de ganhos no menu suspenso **Código de ganhos**.</span><span class="sxs-lookup"><span data-stu-id="89a87-121">Select an earning code from the **Earning code** dropdown.</span></span>

7. <span data-ttu-id="89a87-122">Em **Código de motivo obrigatório**, escolha se deseja exigir um código de motivo.</span><span class="sxs-lookup"><span data-stu-id="89a87-122">Under **Reason code required**, choose whether you want to require a reason code.</span></span> <span data-ttu-id="89a87-123">Se desejar exigir códigos de motivo, talvez seja necessário adicioná-los.</span><span class="sxs-lookup"><span data-stu-id="89a87-123">If you want to require reason codes, you might need to add them.</span></span> <span data-ttu-id="89a87-124">Em **Códigos de motivo**, selecione **Adicionar**, selecione um código de motivo e marque a caixa de seleção **Habilitado** ao lado dele.</span><span class="sxs-lookup"><span data-stu-id="89a87-124">Under **Reason codes**, select **Add**, select a reason code, and then select the **Enabled** checkbox next to it.</span></span>

8. <span data-ttu-id="89a87-125">Em **Restringir acesso a funções selecionadas**, escolha se deseja restringir o acesso.</span><span class="sxs-lookup"><span data-stu-id="89a87-125">Under **Restrict access to selected roles**, choose whether you want to restrict access.</span></span> <span data-ttu-id="89a87-126">Em seguida, selecione as funções de segurança em **Funções de segurança para este tipo de licença**.</span><span class="sxs-lookup"><span data-stu-id="89a87-126">Then select the security roles under **Security roles for this leave type**.</span></span> <span data-ttu-id="89a87-127">As funções de segurança são definidas no fluxo de trabalho selecionado em **ID do fluxo de trabalho**, que vimos antes neste procedimento.</span><span class="sxs-lookup"><span data-stu-id="89a87-127">The security roles are defined in the workflow you selected under **Workflow ID** earlier in this procedure.</span></span>

9. <span data-ttu-id="89a87-128">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="89a87-128">Select **Save**.</span></span>

## <a name="configure-leave-type-rules"></a><span data-ttu-id="89a87-129">Configurar regras de tipo de licença</span><span class="sxs-lookup"><span data-stu-id="89a87-129">Configure leave type rules</span></span>

1. <span data-ttu-id="89a87-130">Defina as opções de arredondamento para o tipo de licença.</span><span class="sxs-lookup"><span data-stu-id="89a87-130">Set rounding options for the leave type.</span></span> <span data-ttu-id="89a87-131">As opções incluem **Nenhum**, **Para cima**, **Para baixo** e **Mais próximo**.</span><span class="sxs-lookup"><span data-stu-id="89a87-131">Options include **None**, **Up**, **Down**, and **Nearest**.</span></span> <span data-ttu-id="89a87-132">Você também pode definir a precisão de arredondamento para o tipo de licença.</span><span class="sxs-lookup"><span data-stu-id="89a87-132">You can also set rounding precision for the leave type.</span></span>

2. <span data-ttu-id="89a87-133">Defina a **Correção de feriado** para o tipo de licença.</span><span class="sxs-lookup"><span data-stu-id="89a87-133">Set **Holiday correction** for the leave type.</span></span> <span data-ttu-id="89a87-134">Quando você seleciona esta opção, o Human Resources usa o número de feriados que caem em um dia útil para determinar como acumular folgas para o tipo de licença.</span><span class="sxs-lookup"><span data-stu-id="89a87-134">When you select this option, Human Resources uses the number of holidays that fall on a work day to determine how to accrue time off for the leave type.</span></span> <span data-ttu-id="89a87-135">Por exemplo, se o dia de Natal cair na segunda-feira, o Human Resources subtrairá um dia do tipo de licença ao processar competências.</span><span class="sxs-lookup"><span data-stu-id="89a87-135">For example, if Christmas Day falls on a Monday, Human Resources will subtract one day from the leave type when processing accruals.</span></span>

   <span data-ttu-id="89a87-136">Você pode definir feriados no calendário de horário de trabalho.</span><span class="sxs-lookup"><span data-stu-id="89a87-136">You set holidays in the working time calendar.</span></span> <span data-ttu-id="89a87-137">Para obter mais informações, consulte [Criar um calendário de horário de trabalho](hr-leave-and-absence-working-time-calendar.md)</span><span class="sxs-lookup"><span data-stu-id="89a87-137">For more information, see [Create a working time calendar](hr-leave-and-absence-working-time-calendar.md)</span></span>
   
## <a name="configure-preview-features"></a><span data-ttu-id="89a87-138">Configure recursos de visualização</span><span class="sxs-lookup"><span data-stu-id="89a87-138">Configure preview features</span></span>

<span data-ttu-id="89a87-139">Se tiver habilitado recursos de visualização para licença e ausência, você também precisará definir configurações para eles.</span><span class="sxs-lookup"><span data-stu-id="89a87-139">If you've enabled preview features for Leave and absence, you need to configure settings for them, too.</span></span>

[!include [banner](includes/preview-feature-leave-absence.md)]

1. <span data-ttu-id="89a87-140">Escolha o tipo de licença para os saldos postergados a serem transferidos.</span><span class="sxs-lookup"><span data-stu-id="89a87-140">Choose the leave type for carry forward balances to be transferred to.</span></span> <span data-ttu-id="89a87-141">Você também pode criar um novo tipo de licença para postergar.</span><span class="sxs-lookup"><span data-stu-id="89a87-141">You can also create a new leave type for carry forward.</span></span> 

## <a name="see-also"></a><span data-ttu-id="89a87-142">Consulte também</span><span class="sxs-lookup"><span data-stu-id="89a87-142">See also</span></span>

- [<span data-ttu-id="89a87-143">Visão geral de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="89a87-143">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
- [<span data-ttu-id="89a87-144">Criar um plano de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="89a87-144">Create a leave and absence plan</span></span>](hr-leave-and-absence-plans.md)
- [<span data-ttu-id="89a87-145">Criar um calendário de horas úteis</span><span class="sxs-lookup"><span data-stu-id="89a87-145">Create a working time calendar</span></span>](hr-leave-and-absence-working-time-calendar.md)

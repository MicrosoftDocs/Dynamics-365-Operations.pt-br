---
title: Configurar tipos de licença e ausência
description: Configurar tipos de licença que os funcionários podem executar no Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
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
ms.openlocfilehash: 1748ec2a888a50af9b9260720dfd439adc4686f9
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008130"
---
# <a name="configure-leave-and-absence-types"></a><span data-ttu-id="80c4a-103">Configurar tipos de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="80c4a-103">Configure leave and absence types</span></span>

<span data-ttu-id="80c4a-104">Os tipos de licenças no Dynamics 365 Human Resources definem os tipos de ausências que os funcionários podem relatar.</span><span class="sxs-lookup"><span data-stu-id="80c4a-104">Leave types in Dynamics 365 Human Resources define the types of absences that employees can report.</span></span> <span data-ttu-id="80c4a-105">Você pode personalizar os tipos de licença de acordo com as necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="80c4a-105">You can tailor leave types according to the needs of your organization.</span></span> <span data-ttu-id="80c4a-106">Exemplos de tipos de licença incluem:</span><span class="sxs-lookup"><span data-stu-id="80c4a-106">Examples of leave types include:</span></span>

- <span data-ttu-id="80c4a-107">Folga remunerada (PTO)</span><span class="sxs-lookup"><span data-stu-id="80c4a-107">Paid time off (PTO)</span></span>
- <span data-ttu-id="80c4a-108">Licença não remunerada</span><span class="sxs-lookup"><span data-stu-id="80c4a-108">Unpaid leave</span></span>
- <span data-ttu-id="80c4a-109">Férias remuneradas</span><span class="sxs-lookup"><span data-stu-id="80c4a-109">Paid vacation</span></span>
- <span data-ttu-id="80c4a-110">Ausência por motivo de doença</span><span class="sxs-lookup"><span data-stu-id="80c4a-110">Sick leave</span></span>
- <span data-ttu-id="80c4a-111">Licença médica</span><span class="sxs-lookup"><span data-stu-id="80c4a-111">Medical leave</span></span>
- <span data-ttu-id="80c4a-112">Licença de família</span><span class="sxs-lookup"><span data-stu-id="80c4a-112">Family leave</span></span>
- <span data-ttu-id="80c4a-113">Incapacidade temporária</span><span class="sxs-lookup"><span data-stu-id="80c4a-113">Short-term disability</span></span>
- <span data-ttu-id="80c4a-114">Licença óbito</span><span class="sxs-lookup"><span data-stu-id="80c4a-114">Bereavement leave</span></span>

## <a name="add-a-leave-type"></a><span data-ttu-id="80c4a-115">Adicionar um tipo de licença</span><span class="sxs-lookup"><span data-stu-id="80c4a-115">Add a leave type</span></span>

1. <span data-ttu-id="80c4a-116">Na página **Licença e ausência**, selecione a guia **Links**.</span><span class="sxs-lookup"><span data-stu-id="80c4a-116">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="80c4a-117">Em **Configuração**, selecione **Tipos de licença e ausência**.</span><span class="sxs-lookup"><span data-stu-id="80c4a-117">Under **Setup**, select **Leave and absence types**.</span></span>

3. <span data-ttu-id="80c4a-118">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="80c4a-118">Select **New**.</span></span>

4. <span data-ttu-id="80c4a-119">Digite um nome para o tipo de licença em **Tipo**, selecione um fluxo de trabalho em **ID do fluxo de trabalho** e digite uma descrição em **Descrição**.</span><span class="sxs-lookup"><span data-stu-id="80c4a-119">Enter a name for the leave type under **Type**, select a workflow from **Workflow ID**, and enter a description under **Description**.</span></span>

5. <span data-ttu-id="80c4a-120">Em **Geral**, selecione **Nenhum**, **Agendado** ou **Não agendado** no menu suspenso **Categoria**.</span><span class="sxs-lookup"><span data-stu-id="80c4a-120">In **General**, select **None**, **Scheduled**, or **Unscheduled** from the **Category** dropdown.</span></span>

6. <span data-ttu-id="80c4a-121">Selecione um código de ganhos no menu suspenso **Código de ganhos**.</span><span class="sxs-lookup"><span data-stu-id="80c4a-121">Select an earning code from the **Earning code** dropdown.</span></span>

7. <span data-ttu-id="80c4a-122">Em **Código de motivo obrigatório**, escolha se deseja exigir um código de motivo.</span><span class="sxs-lookup"><span data-stu-id="80c4a-122">Under **Reason code required**, choose whether you want to require a reason code.</span></span> <span data-ttu-id="80c4a-123">Se desejar exigir códigos de motivo, talvez seja necessário adicioná-los.</span><span class="sxs-lookup"><span data-stu-id="80c4a-123">If you want to require reason codes, you might need to add them.</span></span> <span data-ttu-id="80c4a-124">Em **Códigos de motivo**, selecione **Adicionar**, selecione um código de motivo e marque a caixa de seleção **Habilitado** ao lado dele.</span><span class="sxs-lookup"><span data-stu-id="80c4a-124">Under **Reason codes**, select **Add**, select a reason code, and then select the **Enabled** checkbox next to it.</span></span>

8. <span data-ttu-id="80c4a-125">Em **Restringir acesso a funções selecionadas**, escolha se deseja restringir o acesso.</span><span class="sxs-lookup"><span data-stu-id="80c4a-125">Under **Restrict access to selected roles**, choose whether you want to restrict access.</span></span> <span data-ttu-id="80c4a-126">Em seguida, selecione as funções de segurança em **Funções de segurança para este tipo de licença**.</span><span class="sxs-lookup"><span data-stu-id="80c4a-126">Then select the security roles under **Security roles for this leave type**.</span></span> <span data-ttu-id="80c4a-127">As funções de segurança são definidas no fluxo de trabalho selecionado em **ID do fluxo de trabalho**, que vimos antes neste procedimento.</span><span class="sxs-lookup"><span data-stu-id="80c4a-127">The security roles are defined in the workflow you selected under **Workflow ID** earlier in this procedure.</span></span>

9. <span data-ttu-id="80c4a-128">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="80c4a-128">Select **Save**.</span></span>

## <a name="configure-preview-features"></a><span data-ttu-id="80c4a-129">Configure recursos de visualização</span><span class="sxs-lookup"><span data-stu-id="80c4a-129">Configure preview features</span></span>

<span data-ttu-id="80c4a-130">Se tiver habilitado recursos de visualização para licença e ausência, você também precisará definir configurações para eles.</span><span class="sxs-lookup"><span data-stu-id="80c4a-130">If you've enabled preview features for Leave and absence, you need to configure settings for them, too.</span></span>

[!include [banner](includes/preview-feature-leave-absence.md)]

1. <span data-ttu-id="80c4a-131">Defina as opções de arredondamento para o tipo de licença.</span><span class="sxs-lookup"><span data-stu-id="80c4a-131">Set rounding options for the leave type.</span></span> <span data-ttu-id="80c4a-132">As opções incluem **Nenhum**, **Para cima**, **Para baixo** e **Mais próximo**.</span><span class="sxs-lookup"><span data-stu-id="80c4a-132">Options include **None**, **Up**, **Down**, and **Nearest**.</span></span> <span data-ttu-id="80c4a-133">Você também pode definir a precisão de arredondamento para o tipo de licença.</span><span class="sxs-lookup"><span data-stu-id="80c4a-133">You can also set rounding precision for the leave type.</span></span>

2. <span data-ttu-id="80c4a-134">Defina a **Correção de feriado** para o tipo de licença.</span><span class="sxs-lookup"><span data-stu-id="80c4a-134">Set **Holiday correction** for the leave type.</span></span> <span data-ttu-id="80c4a-135">Quando você seleciona esta opção, o Human Resources usa o número de feriados que caem em um dia útil para determinar como acumular folgas para o tipo de licença.</span><span class="sxs-lookup"><span data-stu-id="80c4a-135">When you select this option, Human Resources uses the number of holidays that fall on a work day to determine how to accrue time off for the leave type.</span></span> <span data-ttu-id="80c4a-136">Por exemplo, se o dia de Natal cair na segunda-feira, o Human Resources subtrairá um dia do tipo de licença ao processar competências.</span><span class="sxs-lookup"><span data-stu-id="80c4a-136">For example, if Christmas Day falls on a Monday, Human Resources will subtract one day from the leave type when processing accruals.</span></span>

   <span data-ttu-id="80c4a-137">Você pode definir feriados no calendário de horário de trabalho.</span><span class="sxs-lookup"><span data-stu-id="80c4a-137">You set holidays in the working time calendar.</span></span> <span data-ttu-id="80c4a-138">Para obter mais informações, consulte [Criar um calendário de horário de trabalho](hr-leave-and-absence-working-time-calendar.md)</span><span class="sxs-lookup"><span data-stu-id="80c4a-138">For more information, see [Create a working time calendar](hr-leave-and-absence-working-time-calendar.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="80c4a-139">Consulte também</span><span class="sxs-lookup"><span data-stu-id="80c4a-139">See also</span></span>

- [<span data-ttu-id="80c4a-140">Visão geral de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="80c4a-140">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
- [<span data-ttu-id="80c4a-141">Criar um plano de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="80c4a-141">Create a leave and absence plan</span></span>](hr-leave-and-absence-plans.md)
- [<span data-ttu-id="80c4a-142">Criar um calendário de horas úteis</span><span class="sxs-lookup"><span data-stu-id="80c4a-142">Create a working time calendar</span></span>](hr-leave-and-absence-working-time-calendar.md)
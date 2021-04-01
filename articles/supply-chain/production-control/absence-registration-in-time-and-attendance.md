---
title: Registro de ausência em Horário e presença
description: Este tópico explica como tratar registros de ausência em Horário e presença.
author: johanhoffmann
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JMGParameters, JmgAbsenceCalendar
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 961b87fb066018f9f6ecc3dcc3cc88e64574bb64
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5246540"
---
# <a name="absence-registration-in-time-and-attendance"></a><span data-ttu-id="3eefb-103">Registro de ausência em Horário e presença</span><span class="sxs-lookup"><span data-stu-id="3eefb-103">Absence registration in Time and attendance</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3eefb-104">Este tópico descreve os conceitos de ausência e explica como tratar ausências em Horário e presença.</span><span class="sxs-lookup"><span data-stu-id="3eefb-104">This topic describes the concepts for absence and explains how to handle absence in Time and attendance.</span></span>

## <a name="absence-that-is-based-on-regular-work-hours"></a><span data-ttu-id="3eefb-105">Ausência que é baseada em horas normais de trabalho</span><span class="sxs-lookup"><span data-stu-id="3eefb-105">Absence that is based on regular work hours</span></span>

<span data-ttu-id="3eefb-106">Os funcionários são considerados ausentes pelas horas que não trabalharem durante as horas normais de trabalho.</span><span class="sxs-lookup"><span data-stu-id="3eefb-106">Workers are considered absent for any hours that they don't work during their regular work hours.</span></span> <span data-ttu-id="3eefb-107">As horas normais de trabalho são definidas no perfil de horário padrão de um trabalhador.</span><span class="sxs-lookup"><span data-stu-id="3eefb-107">Regular work hours are defined in a worker's standard time profile.</span></span>

<span data-ttu-id="3eefb-108">Por exemplo, um trabalhador está trabalhando em um perfil diurno com entrada às 7:00 e saída às 15:00.</span><span class="sxs-lookup"><span data-stu-id="3eefb-108">For example, a worker is working on a day profile that has clock-in at 7:00 AM and clock-out at 3:00 PM.</span></span> <span data-ttu-id="3eefb-109">Se o trabalhador entrar às 9:00, considera-se que ele esteve ausente das 7:00 às 9:00 nesse dia.</span><span class="sxs-lookup"><span data-stu-id="3eefb-109">If the worker clocks in at 9:00 AM, he is considered absent from 7:00 AM to 9:00 AM on that day.</span></span>

<span data-ttu-id="3eefb-110">Neste caso, é solicitado que os trabalhadores insiram um motivo para a ausência.</span><span class="sxs-lookup"><span data-stu-id="3eefb-110">In this case, workers are prompted to enter a reason for their absence.</span></span> <span data-ttu-id="3eefb-111">É possível especificar um motivo selecionando um código de ausência.</span><span class="sxs-lookup"><span data-stu-id="3eefb-111">They can specify a reason by selecting an absence code.</span></span>

## <a name="absence-codes"></a><span data-ttu-id="3eefb-112">Códigos de ausência</span><span class="sxs-lookup"><span data-stu-id="3eefb-112">Absence codes</span></span>

<span data-ttu-id="3eefb-113">Os códigos de ausência definem vários tipos de ausência.</span><span class="sxs-lookup"><span data-stu-id="3eefb-113">Absence codes define the various types of absence.</span></span> <span data-ttu-id="3eefb-114">Os códigos de ausência são definidos pela empresa.</span><span class="sxs-lookup"><span data-stu-id="3eefb-114">Absence codes are defined by the company.</span></span>

<span data-ttu-id="3eefb-115">Várias regras podem ser aplicadas aos códigos de ausência.</span><span class="sxs-lookup"><span data-stu-id="3eefb-115">Various rules can be applied to absence codes.</span></span> <span data-ttu-id="3eefb-116">Por exemplo, um código de ausência pode ser configurado para conceder ou deduzir o pagamento.</span><span class="sxs-lookup"><span data-stu-id="3eefb-116">For example, an absence code can be configured to deduct or grant pay.</span></span>

<span data-ttu-id="3eefb-117">Por exemplo, a empresa define um código de ausência **Atraso** que os trabalhadores usarão se chegarem atrasados e não tiverem um bom motivo.</span><span class="sxs-lookup"><span data-stu-id="3eefb-117">For example, a company defines a **Late** absence code that workers use if they come in late and don't have a good reason.</span></span> <span data-ttu-id="3eefb-118">A empresa também define um código de ausência **Curso interno** que os funcionários usam para horas usadas para a participação em cursos internos.</span><span class="sxs-lookup"><span data-stu-id="3eefb-118">The company also defines an **Internal course** absence code that workers use for time that they spend attending internal courses.</span></span> <span data-ttu-id="3eefb-119">Esses códigos de ausência podem ser configurados de forma que **Atraso** seja deduzido do pagamento de um trabalhador mas **Curso interno** não seja deduzido.</span><span class="sxs-lookup"><span data-stu-id="3eefb-119">These absence codes can be set up so that **Late** deducts from a worker's pay but **Internal course** doesn't deduct from a worker's pay.</span></span>

<span data-ttu-id="3eefb-120">Você pode configurar códigos de ausência automáticos.</span><span class="sxs-lookup"><span data-stu-id="3eefb-120">You can set up automatic absence codes.</span></span> <span data-ttu-id="3eefb-121">Esses códigos de ausência podem ser usados para calcular o horário de um trabalhador quando não houver ausências registradas.</span><span class="sxs-lookup"><span data-stu-id="3eefb-121">These absence codes can be used to calculate a worker's time when no absence is registered.</span></span> <span data-ttu-id="3eefb-122">O perfil de horário do trabalhador determina se o código de ausência para horário padrão ou horário flexível será usado.</span><span class="sxs-lookup"><span data-stu-id="3eefb-122">The worker's time profile determines whether the absence code for standard time or flex time is used.</span></span>

### <a name="set-up-standard-time-and-flex-time"></a><span data-ttu-id="3eefb-123">Configurar horário padrão e horário flexível</span><span class="sxs-lookup"><span data-stu-id="3eefb-123">Set up standard time and flex time</span></span>

- <span data-ttu-id="3eefb-124">Configure os parâmetros para horário padrão e horário flexível usando as opções **Inserção automática de ausência** e **Inserção automática de flex-** na página **Parâmetros de horário e presença**.</span><span class="sxs-lookup"><span data-stu-id="3eefb-124">Configure the parameters for standard time and flex time by using the **Auto insert absence** and **Auto insert Flex-** options on the **Time and attendance parameters** page.</span></span>

## <a name="absence-groups"></a><span data-ttu-id="3eefb-125">Grupos de ausências</span><span class="sxs-lookup"><span data-stu-id="3eefb-125">Absence groups</span></span>

<span data-ttu-id="3eefb-126">Os códigos de ausência são colocados em grupos de ausência.</span><span class="sxs-lookup"><span data-stu-id="3eefb-126">Absence codes are grouped into absence groups.</span></span> <span data-ttu-id="3eefb-127">Você usa grupos de ausência para agrupar códigos de ausência com características em comum.</span><span class="sxs-lookup"><span data-stu-id="3eefb-127">You use absence groups to group absence codes that have common characteristics.</span></span> <span data-ttu-id="3eefb-128">Exemplos incluem códigos de ausência para uma ausência legal ou uma ausência por causa de uma consulta médica, convocação para ser membro de júri ou um filho doente.</span><span class="sxs-lookup"><span data-stu-id="3eefb-128">Examples include absence codes for a legal absence, or absence because of a doctor's appointment, jury duty, or a sick child.</span></span>

## <a name="planned-absence"></a><span data-ttu-id="3eefb-129">Ausência planejada</span><span class="sxs-lookup"><span data-stu-id="3eefb-129">Planned absence</span></span>

<span data-ttu-id="3eefb-130">Se souber que um trabalhador estará ausente por um período, como futuras férias, você poderá usar a ausência planejada.</span><span class="sxs-lookup"><span data-stu-id="3eefb-130">If you know that a worker will be absent for a period, such as an upcoming vacation, you can use planned absence.</span></span> <span data-ttu-id="3eefb-131">Você configura a ausência planejada definindo o código de ausência para que ele considere a ausência planejada.</span><span class="sxs-lookup"><span data-stu-id="3eefb-131">You set up planned absence by configuring the absence code so that it considers the planned absence.</span></span> <span data-ttu-id="3eefb-132">Ao configurar uma ausência planejada, não será solicitado que você insira um código de ausência durante o período de ausência em que os registros de horas do usuário serão calculados.</span><span class="sxs-lookup"><span data-stu-id="3eefb-132">When you set up a planned absence, you aren't prompted for an absence code during the absence period when user time registrations are calculated.</span></span> <span data-ttu-id="3eefb-133">A ausência planejada pode ser definida para um único trabalhador, ou você pode definir um trabalho em lotes para atualizar em massa as ausências planejadas de trabalhadores.</span><span class="sxs-lookup"><span data-stu-id="3eefb-133">Planned absence can be defined for a single worker, or you can define a batch job to bulk update the planned absence for workers.</span></span>

### <a name="set-up-planned-absence"></a><span data-ttu-id="3eefb-134">Configurar ausência planejada</span><span class="sxs-lookup"><span data-stu-id="3eefb-134">Set up planned absence</span></span>

1. <span data-ttu-id="3eefb-135">Selecione **Recursos Humanos** &gt; **Trabalhadores** &gt; **Funcionários** e selecione um funcionário.</span><span class="sxs-lookup"><span data-stu-id="3eefb-135">Select **Human resources** &gt; **Workers** &gt; **Employees**, and select an employee.</span></span>
2. <span data-ttu-id="3eefb-136">Selecione **Tempo** &gt; **Atribuição de Tempo** &gt; **Registro de tempo de ausência** e configure a ausência planejada.</span><span class="sxs-lookup"><span data-stu-id="3eefb-136">Select **Time** &gt; **Time assignments** &gt; **Time Absence registration**, and set up the planned absence.</span></span>

## <a name="interrupted-planned-absence"></a><span data-ttu-id="3eefb-137">Ausência planejada interrompida</span><span class="sxs-lookup"><span data-stu-id="3eefb-137">Interrupted planned absence</span></span>

<span data-ttu-id="3eefb-138">Se você aplicar a opção **Interromper** quando tiver configurado uma ausência planejada, ela será interrompida se o trabalhador se conectar durante o período de ausência planejada.</span><span class="sxs-lookup"><span data-stu-id="3eefb-138">If you apply the **Interrupt** option when you set up a planned absence, the planned absence will be interrupted if the worker signs in during the planned absence period.</span></span> <span data-ttu-id="3eefb-139">A ausência planejada será marcada como **Interrompida** e não terá nenhum efeito sobre os cálculos futuros.</span><span class="sxs-lookup"><span data-stu-id="3eefb-139">The planned absence will be marked as **Interrupted** and won't have any effect on future calculations.</span></span>

### <a name="set-up-a-planned-absence-for-interruption"></a><span data-ttu-id="3eefb-140">Configurar uma ausência planejada para interrupção</span><span class="sxs-lookup"><span data-stu-id="3eefb-140">Set up a planned absence for interruption</span></span>

1. <span data-ttu-id="3eefb-141">Abra a página **Registro de tempo de ausência** conforme descrito no procedimento para configurar a ausência planejada.</span><span class="sxs-lookup"><span data-stu-id="3eefb-141">Open the **Time Absence registration** page as described in the procedure for setting up planned absence.</span></span>
2. <span data-ttu-id="3eefb-142">Selecione **Interromper**.</span><span class="sxs-lookup"><span data-stu-id="3eefb-142">Select **Interrupt**.</span></span>

<span data-ttu-id="3eefb-143">A opção **Interromper** é aplicada quando as horas são registrados pelo terminal ou pelo dispositivo da loja.</span><span class="sxs-lookup"><span data-stu-id="3eefb-143">The **Interrupt** option applies when time is registered through the shop floor terminal or the shop floor device.</span></span> <span data-ttu-id="3eefb-144">A opção não se aplica se os registros forem inseridos nas páginas de aprovação e cálculo, ou na página **Cartão de ponto eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="3eefb-144">The option doesn't apply if the registrations are entered on the calculation and approval pages, or on the **Electronic timecard** page.</span></span>

## <a name="examples-of-the-use-of-absence-in-a-flex-profile"></a><span data-ttu-id="3eefb-145">Exemplo de uso de ausências em um perfil flexível</span><span class="sxs-lookup"><span data-stu-id="3eefb-145">Examples of the use of absence in a flex profile</span></span>

<span data-ttu-id="3eefb-146">Os três exemplos a seguir mostram como a ausência é calculada em um perfil com períodos flexíveis.</span><span class="sxs-lookup"><span data-stu-id="3eefb-146">The following three examples show how absence is calculated in a profile that has flex periods.</span></span>

<span data-ttu-id="3eefb-147">Os exemplos usam o perfil a seguir.</span><span class="sxs-lookup"><span data-stu-id="3eefb-147">The examples use the following profile.</span></span>

| <span data-ttu-id="3eefb-148">Registro de entrada</span><span class="sxs-lookup"><span data-stu-id="3eefb-148">Clock-in</span></span> | <span data-ttu-id="3eefb-149">Período padrão</span><span class="sxs-lookup"><span data-stu-id="3eefb-149">Standard time</span></span>    | <span data-ttu-id="3eefb-150">Interrupção</span><span class="sxs-lookup"><span data-stu-id="3eefb-150">Break</span></span>             | <span data-ttu-id="3eefb-151">Período padrão</span><span class="sxs-lookup"><span data-stu-id="3eefb-151">Standard time</span></span> | <span data-ttu-id="3eefb-152">Menos flexível</span><span class="sxs-lookup"><span data-stu-id="3eefb-152">Flex-</span></span>        | <span data-ttu-id="3eefb-153">Registro de saída</span><span class="sxs-lookup"><span data-stu-id="3eefb-153">Clock-out</span></span> | <span data-ttu-id="3eefb-154">Mais flexível</span><span class="sxs-lookup"><span data-stu-id="3eefb-154">Flex+</span></span>        |
|----------|------------------|-------------------|---------------|--------------|-----------|--------------|
| <span data-ttu-id="3eefb-155">8:00</span><span class="sxs-lookup"><span data-stu-id="3eefb-155">8 AM</span></span>     | <span data-ttu-id="3eefb-156">9:00 às 11:30</span><span class="sxs-lookup"><span data-stu-id="3eefb-156">9 AM to 11:30 AM</span></span> | <span data-ttu-id="3eefb-157">11:30 às 12:00</span><span class="sxs-lookup"><span data-stu-id="3eefb-157">11:30 AM to 12 PM</span></span> | <span data-ttu-id="3eefb-158">12:00 às 15:00</span><span class="sxs-lookup"><span data-stu-id="3eefb-158">12 PM to 3 PM</span></span> | <span data-ttu-id="3eefb-159">15:00 às 16:00</span><span class="sxs-lookup"><span data-stu-id="3eefb-159">3 PM to 4 PM</span></span> | <span data-ttu-id="3eefb-160">16:00</span><span class="sxs-lookup"><span data-stu-id="3eefb-160">4 PM</span></span>      | <span data-ttu-id="3eefb-161">16:00 às 18:00</span><span class="sxs-lookup"><span data-stu-id="3eefb-161">4 PM to 6 PM</span></span> |

### <a name="example-1-signing-out-during-a-flex--period"></a><span data-ttu-id="3eefb-162">Exemplo 1: Desconectar-se durante um período Flex-</span><span class="sxs-lookup"><span data-stu-id="3eefb-162">Example 1: Signing out during a Flex- period</span></span>

<span data-ttu-id="3eefb-163">O trabalhador entra às 8:00 e sai às 15:30.</span><span class="sxs-lookup"><span data-stu-id="3eefb-163">The worker clocks in at 8:00 AM and clocks out at 3:30 PM.</span></span> <span data-ttu-id="3eefb-164">Nesse caso, como o trabalhador registra a saída durante um período Flex-, nenhuma ausência é calculada, e meia hora é deduzida do saldo flexível do trabalhador.</span><span class="sxs-lookup"><span data-stu-id="3eefb-164">In this case, because the worker clocks out during a Flex- period, no absence is calculated, and half an hour is deducted from the worker's flex balance.</span></span>

### <a name="example-2-signing-out-in-during-standard-time-period"></a><span data-ttu-id="3eefb-165">Exemplo 2: Desconectar-se durante o período de tempo padrão</span><span class="sxs-lookup"><span data-stu-id="3eefb-165">Example 2: Signing out in during Standard time period</span></span>

<span data-ttu-id="3eefb-166">O trabalhador entra às 8:00 e sai às 14:30.</span><span class="sxs-lookup"><span data-stu-id="3eefb-166">The worker clocks in at 8:00 AM and clocks out at 2:30 PM.</span></span> <span data-ttu-id="3eefb-167">Nesse caso, como o trabalhador registra a saída durante o período de tempo padrão, a ausência é calculada das 14:30 às 16:00, e um período de ausência de 1,5 hora é registrado.</span><span class="sxs-lookup"><span data-stu-id="3eefb-167">In this case, because the worker clocks out during the Standard time period, absence is calculated from 2:30 PM to 4 PM, and an absence period of 1.5 hours is registered.</span></span> <span data-ttu-id="3eefb-168">Um código de ausência para esse período é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="3eefb-168">An absence code for that period is required.</span></span>

### <a name="example-3-signing-out-during-a-flex-period"></a><span data-ttu-id="3eefb-169">Exemplo 3: Desconectar-se durante um período Flex+</span><span class="sxs-lookup"><span data-stu-id="3eefb-169">Example 3: Signing out during a Flex+ period</span></span>

<span data-ttu-id="3eefb-170">O trabalhador entra às 8:00 e sai às 16:30.</span><span class="sxs-lookup"><span data-stu-id="3eefb-170">The worker clocks in at 8:00 AM and clocks out at 4:30 PM.</span></span> <span data-ttu-id="3eefb-171">Nesse caso, como o trabalhador registra a saída durante um período Flex+, nenhuma ausência é calculada, e meia hora é adicionada do saldo flexível do trabalhador.</span><span class="sxs-lookup"><span data-stu-id="3eefb-171">In this case, because the worker clocks out during a Flex+ period, no absence is calculated, and half an hour is added to the worker's flex balance.</span></span>

## <a name="absence-in-the-calculation-and-approval-process"></a><span data-ttu-id="3eefb-172">Ausência no processo de cálculo e de aprovação</span><span class="sxs-lookup"><span data-stu-id="3eefb-172">Absence in the calculation and approval process</span></span>

<span data-ttu-id="3eefb-173">Os registros de horas do trabalhador devem ser calculados e aprovados antes de serem transferidos para um sistema de folha de pagamento como itens de pagamento.</span><span class="sxs-lookup"><span data-stu-id="3eefb-173">Worker time registrations must be calculated and approved before they can be transferred to a payroll system as pay items.</span></span>

<span data-ttu-id="3eefb-174">Um aprovador pode modificar os registros de horas do trabalhador.</span><span class="sxs-lookup"><span data-stu-id="3eefb-174">An approver can change a worker's time registrations.</span></span> <span data-ttu-id="3eefb-175">Ele poderá alterar até mesmo as ausências que o trabalhador registrou.</span><span class="sxs-lookup"><span data-stu-id="3eefb-175">The approver can even change any absence that the worker has registered.</span></span> <span data-ttu-id="3eefb-176">Se ele inserir manualmente um período de tempo que tenha um código de ausência, o código de ausência para o período não será substituído pelo código padrão de ausência dos parâmetros de Horário e presença.</span><span class="sxs-lookup"><span data-stu-id="3eefb-176">If the approver manually enters a time period that has an absence code, the absence code for that period isn't overridden by the default absence code from the Time and attendance parameters.</span></span>

<span data-ttu-id="3eefb-177">Por exemplo, um trabalhador entra às 10:00 e seleciona um código de ausência que indica que ele está atrasado.</span><span class="sxs-lookup"><span data-stu-id="3eefb-177">For example, a worker clocks in at 10 AM and selects an absence code that indicates that she is late.</span></span> <span data-ttu-id="3eefb-178">Depois, o trabalhador informa seu supervisor que esteve em consulta médica das 8:00 às 10:00.</span><span class="sxs-lookup"><span data-stu-id="3eefb-178">Later, the worker informs her supervisor that she had a doctor's appointment from 8 AM to 10 AM.</span></span> <span data-ttu-id="3eefb-179">Uma consulta médica não deve causar dedução no pagamento do trabalhador.</span><span class="sxs-lookup"><span data-stu-id="3eefb-179">A doctor's appointment should not cause a deduction in the worker's pay.</span></span> <span data-ttu-id="3eefb-180">Portanto, nesse caso, o supervisor poderá ajustar as duas horas de ausência de 8:00 às 10:00 inserindo manualmente um código de ausência que indique doença por essas duas horas.</span><span class="sxs-lookup"><span data-stu-id="3eefb-180">Therefore, in this case, the supervisor can adjust the two hours of absence from 8 AM to 10 AM by manually entering an absence code that indicates illness for those two hours.</span></span>

### <a name="calculate-and-approve-absence"></a><span data-ttu-id="3eefb-181">Calcular e aprovar a ausência</span><span class="sxs-lookup"><span data-stu-id="3eefb-181">Calculate and approve absence</span></span>

- <span data-ttu-id="3eefb-182">Selecione **Horário e presença** &gt; **Revisar e aprovar** &gt; **Aprovar ou Calcular**.</span><span class="sxs-lookup"><span data-stu-id="3eefb-182">Select **Time attendance** &gt; **Review and approve** &gt; **Approve or Calculate**.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
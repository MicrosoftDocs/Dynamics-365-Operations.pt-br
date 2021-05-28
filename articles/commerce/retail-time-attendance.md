---
title: Gerenciamento de horário e de presença no Retail
description: Este tópico descreve os cenários com suporte para o Gerenciamento de horário e presença no in Dynamics 365 Commerce.
author: aamirallaqaband
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JMGParameters
audience: Application User
ms.reviewer: josaw
ms.custom: 62813
ms.assetid: 821994a6-cd29-45a3-a526-ce204064f080
ms.search.region: global
ms.search.industry: Retail
ms.author: aamiral
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 7ac7eec69bda7ad2fa41a7311a71a969eddeafb6
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021479"
---
# <a name="time-and-attendance-management-in-retail"></a><span data-ttu-id="d3274-103">Gerenciamento de horário e de presença no Retail</span><span class="sxs-lookup"><span data-stu-id="d3274-103">Time and attendance management in Retail</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d3274-104">Este tópico descreve os cenários com suporte para o Gerenciamento de horário e presença no in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d3274-104">This topic describes the scenarios that are supported for time and attendance management in Dynamics 365 Commerce.</span></span>

## <a name="manage-worker-setup-and-scheduling"></a><span data-ttu-id="d3274-105">Gerenciar configuração e planejamento do trabalhador</span><span class="sxs-lookup"><span data-stu-id="d3274-105">Manage worker setup and scheduling</span></span>

### <a name="initial-configuration"></a><span data-ttu-id="d3274-106">Configuração inicial de </span><span class="sxs-lookup"><span data-stu-id="d3274-106">Initial configuration</span></span>

- <span data-ttu-id="d3274-107">Execute o assistente de configuração.</span><span class="sxs-lookup"><span data-stu-id="d3274-107">Run the configuration wizard.</span></span>
- <span data-ttu-id="d3274-108">Registre os trabalhadores como trabalhadores com registro de horas.</span><span class="sxs-lookup"><span data-stu-id="d3274-108">Register workers as time registration workers.</span></span>

### <a name="plan-worker-schedules"></a><span data-ttu-id="d3274-109">Planejar agendas do trabalhador</span><span class="sxs-lookup"><span data-stu-id="d3274-109">Plan worker schedules</span></span>

- <span data-ttu-id="d3274-110">Aplique perfis usando o planejador de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d3274-110">Apply profiles by using the work planner.</span></span> <span data-ttu-id="d3274-111">Para obter mais informações, consulte [Aplicar perfis usando o planejador de trabalho](/dynamicsax-2012/appuser-itpro/apply-profiles-using-work-planner).</span><span class="sxs-lookup"><span data-stu-id="d3274-111">For more information, see [Apply profiles using work planner](/dynamicsax-2012/appuser-itpro/apply-profiles-using-work-planner).</span></span>

<span data-ttu-id="d3274-112">Para obter informações sobre as etapas de configuração, consulte [Configurando tempo e presença](/dynamicsax-2012/appuser-itpro/setting-up-time-and-attendance).</span><span class="sxs-lookup"><span data-stu-id="d3274-112">For information about the configuration steps, see [Setting up time and attendance](/dynamicsax-2012/appuser-itpro/setting-up-time-and-attendance).</span></span>

### <a name="commerce-specific-configuration"></a><span data-ttu-id="d3274-113">Configuração específica do Commerce</span><span class="sxs-lookup"><span data-stu-id="d3274-113">Commerce-specific configuration</span></span>

- <span data-ttu-id="d3274-114">Habilite um perfil de funcionalidade do relógio de ponto, para os funcionários para os quais você deseja habilitar registros de horas.</span><span class="sxs-lookup"><span data-stu-id="d3274-114">Enable a functionality profile for Time Clock, for workers that you want to enable time registrations for.</span></span> <span data-ttu-id="d3274-115">Clique em **Perfis de funcionalidade de PDV** &gt; **Funções** &gt; **Registros de horas do PDV** &gt; **Habilitar registros de horário**.</span><span class="sxs-lookup"><span data-stu-id="d3274-115">Click **POS functionality profiles** &gt; **Functions** &gt; **POS time registrations** &gt; **Enable time registrations**.</span></span>
- <span data-ttu-id="d3274-116">Configure grupos permissões de PDV (ponto de venda) para habilitar a permissão Exibir entradas do relógio de ponto.</span><span class="sxs-lookup"><span data-stu-id="d3274-116">Configure point of sale (POS) permissions groups to enable the View timeclock entries permission.</span></span> <span data-ttu-id="d3274-117">Essa permissão permite que um usuário exiba os registros do relógio de ponto de outros trabalhadores na loja (e em qualquer outra loja à qual o usuário esteja associado via catálogo de endereços).</span><span class="sxs-lookup"><span data-stu-id="d3274-117">This permission lets a user view the time clock registrations of other workers in the store (and from any other store that the user is associated with, via the address book).</span></span> <span data-ttu-id="d3274-118">Convém habilitar essa permissão para uma função gerente, mas não para uma função caixa.</span><span class="sxs-lookup"><span data-stu-id="d3274-118">You might want to enable this permission for a manager role but not for a cashier role.</span></span> <span data-ttu-id="d3274-119">Clique em **Grupos de permissões de PDV** &gt; **Exibir entradas do relógio de ponto**.</span><span class="sxs-lookup"><span data-stu-id="d3274-119">Click **POS permission groups** &gt; **View time clock entries**.</span></span>

## <a name="register-time"></a><span data-ttu-id="d3274-120">Hora de registro</span><span class="sxs-lookup"><span data-stu-id="d3274-120">Register time</span></span>

### <a name="cashier-and-non-cashier-time-registrations"></a><span data-ttu-id="d3274-121">Registros de horas para caixa e não caixa</span><span class="sxs-lookup"><span data-stu-id="d3274-121">Cashier and non-cashier time registrations</span></span>

- <span data-ttu-id="d3274-122">No PDV:</span><span class="sxs-lookup"><span data-stu-id="d3274-122">On POS:</span></span>

    - <span data-ttu-id="d3274-123">Operações de registro de entrada.</span><span class="sxs-lookup"><span data-stu-id="d3274-123">Clock-in operations:</span></span>

        - <span data-ttu-id="d3274-124">Faça logon com uma operação não sacadora ou novo turno.</span><span class="sxs-lookup"><span data-stu-id="d3274-124">Log on with a non-drawer operation or New shift.</span></span>
        - <span data-ttu-id="d3274-125">Selecione uma operação de relógio de ponto.</span><span class="sxs-lookup"><span data-stu-id="d3274-125">Select a Time Clock operation.</span></span>
        - <span data-ttu-id="d3274-126">Selecione uma operação desejada:</span><span class="sxs-lookup"><span data-stu-id="d3274-126">Select a desired operation:</span></span>

            - <span data-ttu-id="d3274-127">Registro de entrada</span><span class="sxs-lookup"><span data-stu-id="d3274-127">Clock-in</span></span>
            - <span data-ttu-id="d3274-128">Intervalo de trabalho</span><span class="sxs-lookup"><span data-stu-id="d3274-128">Break for Work</span></span>
            - <span data-ttu-id="d3274-129">Intervalo para o Almoço</span><span class="sxs-lookup"><span data-stu-id="d3274-129">Break for Lunch</span></span>
            - <span data-ttu-id="d3274-130">Registro de saída</span><span class="sxs-lookup"><span data-stu-id="d3274-130">Clock-out</span></span>

        <table>
        <thead>
        <tr>
        <th><span data-ttu-id="d3274-131">Status atual</span><span class="sxs-lookup"><span data-stu-id="d3274-131">Current state</span></span></th>
        <th><span data-ttu-id="d3274-132">Operações disponíveis</span><span class="sxs-lookup"><span data-stu-id="d3274-132">Available operations</span></span></th>
        </tr>
        </thead>
        <tbody>
        <tr>
        <td><span data-ttu-id="d3274-133">Registro de entrada</span><span class="sxs-lookup"><span data-stu-id="d3274-133">Clock-in</span></span></td>
        <td>
        <ul>
        <li><span data-ttu-id="d3274-134">Intervalo de trabalho</span><span class="sxs-lookup"><span data-stu-id="d3274-134">Break for Work</span></span></li>
        <li><span data-ttu-id="d3274-135">Intervalo para o Almoço</span><span class="sxs-lookup"><span data-stu-id="d3274-135">Break for Lunch</span></span></li>
        <li><span data-ttu-id="d3274-136">Registro de saída</span><span class="sxs-lookup"><span data-stu-id="d3274-136">Clock-out</span></span></li>
        </ul>
        </td>
        </tr>
        <tr>
        <td><span data-ttu-id="d3274-137">Intervalo de trabalho</span><span class="sxs-lookup"><span data-stu-id="d3274-137">Break for Work</span></span></td>
        <td><span data-ttu-id="d3274-138">Registro de entrada</span><span class="sxs-lookup"><span data-stu-id="d3274-138">Clock-in</span></span></td>
        </tr>
        <tr>
        <td><span data-ttu-id="d3274-139">Intervalo para o Almoço</span><span class="sxs-lookup"><span data-stu-id="d3274-139">Break for Lunch</span></span></td>
        <td><span data-ttu-id="d3274-140">Registro de entrada</span><span class="sxs-lookup"><span data-stu-id="d3274-140">Clock-in</span></span></td>
        </tr>
        <tr>
        <td><span data-ttu-id="d3274-141">Registro de saída</span><span class="sxs-lookup"><span data-stu-id="d3274-141">Clock-out</span></span></td>
        <td><span data-ttu-id="d3274-142">Registro de entrada</span><span class="sxs-lookup"><span data-stu-id="d3274-142">Clock-in</span></span></td>
        </tr>
        </tbody>
        </table>

        <span data-ttu-id="d3274-143">[![Estados do relógio de ponto](./media/timeclockstates.png)](./media/timeclockstates.png)</span><span class="sxs-lookup"><span data-stu-id="d3274-143">[![Time Clock States](./media/timeclockstates.png)](./media/timeclockstates.png)</span></span>

- <span data-ttu-id="d3274-144">Exiba a mensagem de confirmação e valide que o tempo da atividade atual está correto.</span><span class="sxs-lookup"><span data-stu-id="d3274-144">View the confirmation message, and validate that the current activity time is correct.</span></span>
- <span data-ttu-id="d3274-145">Livro de registros:</span><span class="sxs-lookup"><span data-stu-id="d3274-145">Logbook:</span></span>

    - <span data-ttu-id="d3274-146">Clique em **Livro de registros** para exibir a atividade do relógio de ponto.</span><span class="sxs-lookup"><span data-stu-id="d3274-146">Click **Logbook** to view time clock activity.</span></span>
    - <span data-ttu-id="d3274-147">Use os filtros de tempo para selecionar períodos diferentes.</span><span class="sxs-lookup"><span data-stu-id="d3274-147">Use time filters to select different time windows.</span></span>
    - <span data-ttu-id="d3274-148">Se você trabalhar em vários locais de loja, verá os registros de horas de todas as lojas em que você registrou ponto.</span><span class="sxs-lookup"><span data-stu-id="d3274-148">If you work at multiple store locations, you see your time registrations from all the stores where you recorded time.</span></span> <span data-ttu-id="d3274-149">Você pode usar o filtro de loja para exibir os registros de horas de uma loja selecionada.</span><span class="sxs-lookup"><span data-stu-id="d3274-149">You can use the store filter to view time registrations from a selected store.</span></span>

- <span data-ttu-id="d3274-150">Fusos horários diferentes:</span><span class="sxs-lookup"><span data-stu-id="d3274-150">Different time zones:</span></span>

    - <span data-ttu-id="d3274-151">Se você exibir as horas de um local diferente (para o livro de registros do caixa ou usando **Exibir entradas do relógio de ponto** em um cenário do gerente) e esse local estiver em um fuso horário diferente, os registros de horas exibidos serão convertidos em seu fuso horário local.</span><span class="sxs-lookup"><span data-stu-id="d3274-151">If you view time from a different location (for the cashier logbook, or by using **View timeclock entries** for a manager scenario), and that location is in a different time zone, the time records that you see are converted to your local time zone.</span></span> <span data-ttu-id="d3274-152">Por exemplo, você é gerente de duas lojas, uma no Arizona e outra em Nevada.</span><span class="sxs-lookup"><span data-stu-id="d3274-152">For example, you are a manager for two stores, one in Arizona and the other in Nevada.</span></span> <span data-ttu-id="d3274-153">Um caixa registra a entrada às 9:00 A.M.</span><span class="sxs-lookup"><span data-stu-id="d3274-153">A cashier registers a clock-in at 9:00 A.M.</span></span> <span data-ttu-id="d3274-154">no Arizona.</span><span class="sxs-lookup"><span data-stu-id="d3274-154">in Arizona.</span></span> <span data-ttu-id="d3274-155">Nesse momento, são 8h em Nevada.</span><span class="sxs-lookup"><span data-stu-id="d3274-155">At that moment, the time in Nevada is 8:00 A.M.</span></span> <span data-ttu-id="d3274-156">Portanto, se você estiver na loja de Nevada e observar os registros de horas, verá o registro marcando 8h.</span><span class="sxs-lookup"><span data-stu-id="d3274-156">Therefore, if you are in the Nevada store and look at time registration records, the time registration is marked as 8 A.M.</span></span>

## <a name="view-worker-time-registrations"></a><span data-ttu-id="d3274-157">Exibir registros de tempo de funcionário</span><span class="sxs-lookup"><span data-stu-id="d3274-157">View worker time registrations</span></span>

### <a name="view-worker-time-registrations-and-filter-by-store-or-activity-type"></a><span data-ttu-id="d3274-158">Exibir registros de horas do trabalhador e filtrar por tipo de loja ou atividade</span><span class="sxs-lookup"><span data-stu-id="d3274-158">View worker time registrations, and filter by store or activity type</span></span>

<span data-ttu-id="d3274-159">No PDV:</span><span class="sxs-lookup"><span data-stu-id="d3274-159">On POS:</span></span>

- <span data-ttu-id="d3274-160">Selecione **Exibir entradas do relógio de ponto**.</span><span class="sxs-lookup"><span data-stu-id="d3274-160">Select **View timeclock entries**.</span></span>
- <span data-ttu-id="d3274-161">Você verá atividades de registro do relógio de ponto de todos os trabalhadores atribuídos às mesmas lojas às quais você está atribuído.</span><span class="sxs-lookup"><span data-stu-id="d3274-161">You see time clock registration activities from all workers that are assigned to the same stores that you're assigned to.</span></span>
- <span data-ttu-id="d3274-162">Você pode usar os filtros de loja e tipo de atividade para filtrar os registros de horas.</span><span class="sxs-lookup"><span data-stu-id="d3274-162">You can use the activity type and store filters to filter on time registrations.</span></span>

## <a name="process-and-manage-time-registrations"></a><span data-ttu-id="d3274-163">Processar e gerenciar registros de tempos</span><span class="sxs-lookup"><span data-stu-id="d3274-163">Process and manage time registrations</span></span>

<span data-ttu-id="d3274-164">Um usuário do Commerce segue o fluxo de trabalho para calcular, aprovar e transferir registros de horas para a folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="d3274-164">A Commerce user follows the workflow to calculate, approve, and transfer time registrations to payroll.</span></span>

### <a name="primary-operations"></a><span data-ttu-id="d3274-165">Operações principais</span><span class="sxs-lookup"><span data-stu-id="d3274-165">Primary operations</span></span>

- <span data-ttu-id="d3274-166">Calcular</span><span class="sxs-lookup"><span data-stu-id="d3274-166">Calculate</span></span>
- <span data-ttu-id="d3274-167">Aprovar</span><span class="sxs-lookup"><span data-stu-id="d3274-167">Approve</span></span>
- <span data-ttu-id="d3274-168">Enviar para folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="d3274-168">Submit to payroll</span></span>

### <a name="other-common-operations"></a><span data-ttu-id="d3274-169">Outras operações comuns</span><span class="sxs-lookup"><span data-stu-id="d3274-169">Other common operations</span></span>

- <span data-ttu-id="d3274-170">Saída em massa</span><span class="sxs-lookup"><span data-stu-id="d3274-170">Bulk Clock-out</span></span>
- <span data-ttu-id="d3274-171">Registrar ausência</span><span class="sxs-lookup"><span data-stu-id="d3274-171">Register Absence</span></span>

<span data-ttu-id="d3274-172">Para obter mais informações sobre como processar registros de tempo e presença, consulte [Processar os registros de tempo e presença](/dynamicsax-2012/appuser-itpro/process-time-and-attendance-registrations).</span><span class="sxs-lookup"><span data-stu-id="d3274-172">For more information about how to process time and attendance registrations, see [Process time and attendance registrations](/dynamicsax-2012/appuser-itpro/process-time-and-attendance-registrations).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
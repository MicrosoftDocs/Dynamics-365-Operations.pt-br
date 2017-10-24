---
title: "Hora e presença no Retail"
description: "Este tópico descreve os cenários com suporte para o Gerenciamento de horário e presença no in Microsoft Dynamics 365 para Varejo."
author: aamirallaqaband
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 62813
ms.assetid: 821994a6-cd29-45a3-a526-ce204064f080
ms.search.region: global
ms.search.industry: Retail
ms.author: aamiral
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: ebbf3c72b4c34cba95ecd2fb3ce506af393acc34
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="retail-time-and-attendance"></a><span data-ttu-id="c454f-103">Horário e presença do Retail</span><span class="sxs-lookup"><span data-stu-id="c454f-103">Retail time and attendance</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="c454f-104">Este tópico descreve os cenários com suporte para o Gerenciamento de horário e presença no in Microsoft Dynamics 365 para Varejo.</span><span class="sxs-lookup"><span data-stu-id="c454f-104">This topic describes the scenarios that are supported for time and attendance management in Microsoft Dynamics 365 for Retail.</span></span> 

<a name="manage-worker-setup-and-scheduling"></a><span data-ttu-id="c454f-105">Gerenciar configuração e planejamento do trabalhador</span><span class="sxs-lookup"><span data-stu-id="c454f-105">Manage worker setup and scheduling</span></span>
----------------------------------

### <a name="initial-configuration"></a><span data-ttu-id="c454f-106">Configuração inicial de </span><span class="sxs-lookup"><span data-stu-id="c454f-106">Initial configuration</span></span>

-   <span data-ttu-id="c454f-107">Execute o assistente de configuração.</span><span class="sxs-lookup"><span data-stu-id="c454f-107">Run the configuration wizard.</span></span>
-   <span data-ttu-id="c454f-108">Registre os trabalhadores como trabalhadores com registro de horas.</span><span class="sxs-lookup"><span data-stu-id="c454f-108">Register workers as time registration workers.</span></span>

### <a name="plan-worker-schedules"></a><span data-ttu-id="c454f-109">Planejar agendas do trabalhador</span><span class="sxs-lookup"><span data-stu-id="c454f-109">Plan worker schedules</span></span>

-   <span data-ttu-id="c454f-110">Aplique perfis usando o planejador de trabalho.</span><span class="sxs-lookup"><span data-stu-id="c454f-110">Apply profiles by using the work planner.</span></span> <span data-ttu-id="c454f-111">Para obter mais informações, consulte <https://technet.microsoft.com/en-us/library/aa551234.aspx>.</span><span class="sxs-lookup"><span data-stu-id="c454f-111">For more information, see <https://technet.microsoft.com/en-us/library/aa551234.aspx>.</span></span>

<span data-ttu-id="c454f-112">Para obter informações sobre as etapas de configuração, consulte <https://technet.microsoft.com/en-us/library/aa496971.aspx>.</span><span class="sxs-lookup"><span data-stu-id="c454f-112">For information about the configuration steps, see <https://technet.microsoft.com/en-us/library/aa496971.aspx>.</span></span>

### <a name="retail-specific-configuration"></a><span data-ttu-id="c454f-113">Configuração do Retail</span><span class="sxs-lookup"><span data-stu-id="c454f-113">Retail-specific configuration</span></span>

-   <span data-ttu-id="c454f-114">Habilite um perfil de funcionalidade do relógio de ponto, para os funcionários para os quais você deseja habilitar registros de horas.</span><span class="sxs-lookup"><span data-stu-id="c454f-114">Enable a functionality profile for Time Clock, for workers that you want to enable time registrations for.</span></span> <span data-ttu-id="c454f-115">Clique em **Perfis de funcionalidade de PDV** &gt; **Funções** &gt; **Registros de horas do PDV** &gt; **Habilitar registros de horário**.</span><span class="sxs-lookup"><span data-stu-id="c454f-115">Click **POS functionality profiles** &gt; **Functions** &gt; **POS time registrations** &gt; **Enable time registrations**.</span></span>
-   <span data-ttu-id="c454f-116">Configure grupos permissões de PDV (ponto de venda) para habilitar a permissão Exibir entradas do relógio de ponto.</span><span class="sxs-lookup"><span data-stu-id="c454f-116">Configure point of sale (POS) permissions groups to enable the View timeclock entries permission.</span></span> <span data-ttu-id="c454f-117">Essa permissão permite que um usuário exiba os registros do relógio de ponto de outros trabalhadores na loja (e em qualquer outra loja à qual o usuário esteja associado via catálogo de endereços).</span><span class="sxs-lookup"><span data-stu-id="c454f-117">This permission lets a user view the time clock registrations of other workers in the store (and from any other store that the user is associated with, via the address book).</span></span> <span data-ttu-id="c454f-118">Convém habilitar essa permissão para uma função gerente, mas não para uma função caixa.</span><span class="sxs-lookup"><span data-stu-id="c454f-118">You might want to enable this permission for a manager role but not for a cashier role.</span></span> <span data-ttu-id="c454f-119">Clique em **Grupos de permissões de PDV** &gt; **Exibir entradas do relógio de ponto**.</span><span class="sxs-lookup"><span data-stu-id="c454f-119">Click **POS permission groups** &gt; **View time clock entries**.</span></span>

## <a name="register-time"></a><span data-ttu-id="c454f-120">Hora de registro</span><span class="sxs-lookup"><span data-stu-id="c454f-120">Register time</span></span>
### <a name="cashier-and-non-cashier-time-registrations"></a><span data-ttu-id="c454f-121">Registros de horas para caixa e não caixa</span><span class="sxs-lookup"><span data-stu-id="c454f-121">Cashier and non-cashier time registrations</span></span>

-   <span data-ttu-id="c454f-122">No PDV:</span><span class="sxs-lookup"><span data-stu-id="c454f-122">On POS:</span></span>
    -   <span data-ttu-id="c454f-123">Operações de registro de entrada.</span><span class="sxs-lookup"><span data-stu-id="c454f-123">Clock-in operations:</span></span>
        -   <span data-ttu-id="c454f-124">Faça logon com uma operação não sacadora ou novo turno.</span><span class="sxs-lookup"><span data-stu-id="c454f-124">Log on with a non-drawer operation or New shift.</span></span>
        -   <span data-ttu-id="c454f-125">Selecione uma operação de relógio de ponto.</span><span class="sxs-lookup"><span data-stu-id="c454f-125">Select a Time Clock operation.</span></span>
        -   <span data-ttu-id="c454f-126">Selecione uma operação desejada:</span><span class="sxs-lookup"><span data-stu-id="c454f-126">Select a desired operation:</span></span>
            -   <span data-ttu-id="c454f-127">Registro de entrada</span><span class="sxs-lookup"><span data-stu-id="c454f-127">Clock-in</span></span>
            -   <span data-ttu-id="c454f-128">Intervalo de trabalho</span><span class="sxs-lookup"><span data-stu-id="c454f-128">Break for Work</span></span>
            -   <span data-ttu-id="c454f-129">Intervalo para o Almoço</span><span class="sxs-lookup"><span data-stu-id="c454f-129">Break for Lunch</span></span>
            -   <span data-ttu-id="c454f-130">Registro de saída</span><span class="sxs-lookup"><span data-stu-id="c454f-130">Clock-out</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="c454f-131">Status atual</span><span class="sxs-lookup"><span data-stu-id="c454f-131">Current state</span></span></th>
    <th><span data-ttu-id="c454f-132">Operações disponíveis</span><span class="sxs-lookup"><span data-stu-id="c454f-132">Available operations</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="c454f-133">Registro de entrada</span><span class="sxs-lookup"><span data-stu-id="c454f-133">Clock-in</span></span></td>
    <td><ul>
    <li><span data-ttu-id="c454f-134">Intervalo de trabalho</span><span class="sxs-lookup"><span data-stu-id="c454f-134">Break for Work</span></span></li>
    <li><span data-ttu-id="c454f-135">Intervalo para o Almoço</span><span class="sxs-lookup"><span data-stu-id="c454f-135">Break for Lunch</span></span></li>
    <li><span data-ttu-id="c454f-136">Registro de saída</span><span class="sxs-lookup"><span data-stu-id="c454f-136">Clock-out</span></span></li>
    </ul></td>
    </tr>
    <tr class="even">
    <td><span data-ttu-id="c454f-137">Intervalo de trabalho</span><span class="sxs-lookup"><span data-stu-id="c454f-137">Break for Work</span></span></td>
    <td><span data-ttu-id="c454f-138">Registro de entrada</span><span class="sxs-lookup"><span data-stu-id="c454f-138">Clock-in</span></span></td>
    </tr>
    <tr class="odd">
    <td><span data-ttu-id="c454f-139">Intervalo para o Almoço</span><span class="sxs-lookup"><span data-stu-id="c454f-139">Break for Lunch</span></span></td>
    <td><span data-ttu-id="c454f-140">Registro de entrada</span><span class="sxs-lookup"><span data-stu-id="c454f-140">Clock-in</span></span></td>
    </tr>
    <tr class="even">
    <td><span data-ttu-id="c454f-141">Registro de saída</span><span class="sxs-lookup"><span data-stu-id="c454f-141">Clock-out</span></span></td>
    <td><span data-ttu-id="c454f-142">Registro de entrada</span><span class="sxs-lookup"><span data-stu-id="c454f-142">Clock-in</span></span></td>
    </tr>
    </tbody>
    </table>

    <span data-ttu-id="c454f-143">[![TimeClockStates](./media/timeclockstates.png)](./media/timeclockstates.png)</span><span class="sxs-lookup"><span data-stu-id="c454f-143">[![TimeClockStates](./media/timeclockstates.png)](./media/timeclockstates.png)</span></span>
-   <span data-ttu-id="c454f-144">Exiba a mensagem de confirmação e valide que o tempo da atividade atual está correto.</span><span class="sxs-lookup"><span data-stu-id="c454f-144">View the confirmation message, and validate that the current activity time is correct.</span></span>
-   <span data-ttu-id="c454f-145">Livro de registros:</span><span class="sxs-lookup"><span data-stu-id="c454f-145">Logbook:</span></span>
    -   <span data-ttu-id="c454f-146">Clique em **Livro de registros** para exibir a atividade do relógio de ponto.</span><span class="sxs-lookup"><span data-stu-id="c454f-146">Click **Logbook** to view time clock activity.</span></span>
    -   <span data-ttu-id="c454f-147">Use os filtros de tempo para selecionar períodos diferentes.</span><span class="sxs-lookup"><span data-stu-id="c454f-147">Use time filters to select different time windows.</span></span>
    -   <span data-ttu-id="c454f-148">Se você trabalhar em vários locais de loja, verá os registros de horas de todas as lojas em que você registrou ponto.</span><span class="sxs-lookup"><span data-stu-id="c454f-148">If you work at multiple store locations, you see your time registrations from all the stores where you recorded time.</span></span> <span data-ttu-id="c454f-149">Você pode usar o filtro de loja para exibir os registros de horas de uma loja selecionada.</span><span class="sxs-lookup"><span data-stu-id="c454f-149">You can use the store filter to view time registrations from a selected store.</span></span>

<!-- -->

-   <span data-ttu-id="c454f-150">Fusos horários diferentes:</span><span class="sxs-lookup"><span data-stu-id="c454f-150">Different time zones:</span></span>
    -   <span data-ttu-id="c454f-151">Se você exibir as horas de um local diferente (para o livro de registros do caixa ou usando **Exibir entradas do relógio de ponto** em um cenário do gerente) e esse local estiver em um fuso horário diferente, os registros de horas exibidos serão convertidos em seu fuso horário local.</span><span class="sxs-lookup"><span data-stu-id="c454f-151">If you view time from a different location (for the cashier logbook, or by using **View timeclock entries** for a manager scenario), and that location is in a different time zone, the time records that you see are converted to your local time zone.</span></span> <span data-ttu-id="c454f-152">Por exemplo, você é gerente de duas lojas, uma no Arizona e outra em Nevada.</span><span class="sxs-lookup"><span data-stu-id="c454f-152">For example, you are a manager for two stores, one in Arizona and the other in Nevada.</span></span> <span data-ttu-id="c454f-153">Um caixa registra a entrada às 9:00 A.M.</span><span class="sxs-lookup"><span data-stu-id="c454f-153">A cashier registers a clock-in at 9:00 A.M.</span></span> <span data-ttu-id="c454f-154">no Arizona.</span><span class="sxs-lookup"><span data-stu-id="c454f-154">in Arizona.</span></span> <span data-ttu-id="c454f-155">Nesse momento, são 8h em Nevada.</span><span class="sxs-lookup"><span data-stu-id="c454f-155">At that moment, the time in Nevada is 8:00 A.M.</span></span> <span data-ttu-id="c454f-156">Portanto, se você estiver na loja de Nevada e observar os registros de horas, verá o registro marcando 8h.</span><span class="sxs-lookup"><span data-stu-id="c454f-156">Therefore, if you are in the Nevada store and look at time registration records, the time registration is marked as 8 A.M.</span></span>

## <a name="view-worker-time-registrations"></a><span data-ttu-id="c454f-157">Exibir registros de tempo de funcionário</span><span class="sxs-lookup"><span data-stu-id="c454f-157">View worker time registrations</span></span>
### <a name="view-worker-time-registrations-and-filter-by-store-or-activity-type"></a><span data-ttu-id="c454f-158">Exibir registros de horas do trabalhador e filtrar por tipo de loja ou atividade</span><span class="sxs-lookup"><span data-stu-id="c454f-158">View worker time registrations, and filter by store or activity type</span></span>

<span data-ttu-id="c454f-159">No PDV:</span><span class="sxs-lookup"><span data-stu-id="c454f-159">On POS:</span></span>

-   <span data-ttu-id="c454f-160">Selecione **Exibir entradas do relógio de ponto**.</span><span class="sxs-lookup"><span data-stu-id="c454f-160">Select **View timeclock entries**.</span></span>
-   <span data-ttu-id="c454f-161">Você verá atividades de registro do relógio de ponto de todos os trabalhadores atribuídos às mesmas lojas às quais você está atribuído.</span><span class="sxs-lookup"><span data-stu-id="c454f-161">You see time clock registration activities from all workers that are assigned to the same stores that you're assigned to.</span></span>
-   <span data-ttu-id="c454f-162">Você pode usar os filtros de loja e tipo de atividade para filtrar os registros de horas.</span><span class="sxs-lookup"><span data-stu-id="c454f-162">You can use the activity type and store filters to filter on time registrations.</span></span>

## <a name="process-and-manage-time-registrations"></a><span data-ttu-id="c454f-163">Processar e gerenciar registros de tempos</span><span class="sxs-lookup"><span data-stu-id="c454f-163">Process and manage time registrations</span></span>
<span data-ttu-id="c454f-164">Um usuário do Dynamics 365 para Varejo segue o fluxo de trabalho para calcular, aprovar e transferir registros de horas para a folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="c454f-164">A Dynamics 365 for Retail user follows the workflow to calculate, approve, and transfer time registrations to payroll.</span></span>

### <a name="primary-operations"></a><span data-ttu-id="c454f-165">Operações principais</span><span class="sxs-lookup"><span data-stu-id="c454f-165">Primary operations</span></span>

-   <span data-ttu-id="c454f-166">Calcular</span><span class="sxs-lookup"><span data-stu-id="c454f-166">Calculate</span></span>
-   <span data-ttu-id="c454f-167">Aprovar</span><span class="sxs-lookup"><span data-stu-id="c454f-167">Approve</span></span>
-   <span data-ttu-id="c454f-168">Enviar para folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="c454f-168">Submit to payroll</span></span>

### <a name="other-common-operations"></a><span data-ttu-id="c454f-169">Outras operações comuns</span><span class="sxs-lookup"><span data-stu-id="c454f-169">Other common operations</span></span>

-   <span data-ttu-id="c454f-170">Saída em massa</span><span class="sxs-lookup"><span data-stu-id="c454f-170">Bulk Clock-out</span></span>
-   <span data-ttu-id="c454f-171">Registrar ausência</span><span class="sxs-lookup"><span data-stu-id="c454f-171">Register Absence</span></span>

<span data-ttu-id="c454f-172">Para obter mais informações sobre como processar registros de horas e presença, consulte <https://technet.microsoft.com/en-us/library/aa573180.aspx>.</span><span class="sxs-lookup"><span data-stu-id="c454f-172">For more information about how to process time and attendance registrations, see <https://technet.microsoft.com/en-us/library/aa573180.aspx>.</span></span>





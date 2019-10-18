---
title: Gerenciamento de horário e de presença no Retail
description: Este tópico descreve os cenários com suporte para o Gerenciamento de horário e presença no in Dynamics 365 Retail.
author: aamirallaqaband
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: JMGParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 62813
ms.assetid: 821994a6-cd29-45a3-a526-ce204064f080
ms.search.region: global
ms.search.industry: Retail
ms.author: aamiral
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: d541de550df41b7d4616492960bd4f2aae46d45e
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/24/2019
ms.locfileid: "2024974"
---
# <a name="time-and-attendance-management-in-retail"></a><span data-ttu-id="61b86-103">Gerenciamento de horário e de presença no Retail</span><span class="sxs-lookup"><span data-stu-id="61b86-103">Time and attendance management in Retail</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="61b86-104">Este tópico descreve os cenários com suporte para o Gerenciamento de horário e presença no in Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="61b86-104">This topic describes the scenarios that are supported for time and attendance management in Dynamics 365 Retail.</span></span>

## <a name="manage-worker-setup-and-scheduling"></a><span data-ttu-id="61b86-105">Gerenciar configuração e planejamento do trabalhador</span><span class="sxs-lookup"><span data-stu-id="61b86-105">Manage worker setup and scheduling</span></span>

### <a name="initial-configuration"></a><span data-ttu-id="61b86-106">Configuração inicial de </span><span class="sxs-lookup"><span data-stu-id="61b86-106">Initial configuration</span></span>

- <span data-ttu-id="61b86-107">Execute o assistente de configuração.</span><span class="sxs-lookup"><span data-stu-id="61b86-107">Run the configuration wizard.</span></span>
- <span data-ttu-id="61b86-108">Registre os trabalhadores como trabalhadores com registro de horas.</span><span class="sxs-lookup"><span data-stu-id="61b86-108">Register workers as time registration workers.</span></span>

### <a name="plan-worker-schedules"></a><span data-ttu-id="61b86-109">Planejar agendas do trabalhador</span><span class="sxs-lookup"><span data-stu-id="61b86-109">Plan worker schedules</span></span>

- <span data-ttu-id="61b86-110">Aplique perfis usando o planejador de trabalho.</span><span class="sxs-lookup"><span data-stu-id="61b86-110">Apply profiles by using the work planner.</span></span> <span data-ttu-id="61b86-111">Para obter mais informações, consulte [Aplicar perfis usando o planejador de trabalho](https://technet.microsoft.com/library/aa551234.aspx).</span><span class="sxs-lookup"><span data-stu-id="61b86-111">For more information, see [Apply profiles using work planner](https://technet.microsoft.com/library/aa551234.aspx).</span></span>

<span data-ttu-id="61b86-112">Para obter informações sobre as etapas de configuração, consulte [Configurando tempo e presença](https://technet.microsoft.com/library/aa496971.aspx).</span><span class="sxs-lookup"><span data-stu-id="61b86-112">For information about the configuration steps, see [Setting up time and attendance](https://technet.microsoft.com/library/aa496971.aspx).</span></span>

### <a name="retail-specific-configuration"></a><span data-ttu-id="61b86-113">Configuração do Retail</span><span class="sxs-lookup"><span data-stu-id="61b86-113">Retail-specific configuration</span></span>

- <span data-ttu-id="61b86-114">Habilite um perfil de funcionalidade do relógio de ponto, para os funcionários para os quais você deseja habilitar registros de horas.</span><span class="sxs-lookup"><span data-stu-id="61b86-114">Enable a functionality profile for Time Clock, for workers that you want to enable time registrations for.</span></span> <span data-ttu-id="61b86-115">Clique em **Perfis de funcionalidade de PDV** &gt; **Funções** &gt; **Registros de horas do PDV** &gt; **Habilitar registros de horário**.</span><span class="sxs-lookup"><span data-stu-id="61b86-115">Click **POS functionality profiles** &gt; **Functions** &gt; **POS time registrations** &gt; **Enable time registrations**.</span></span>
- <span data-ttu-id="61b86-116">Configure grupos permissões de PDV (ponto de venda) para habilitar a permissão Exibir entradas do relógio de ponto.</span><span class="sxs-lookup"><span data-stu-id="61b86-116">Configure point of sale (POS) permissions groups to enable the View timeclock entries permission.</span></span> <span data-ttu-id="61b86-117">Essa permissão permite que um usuário exiba os registros do relógio de ponto de outros trabalhadores na loja (e em qualquer outra loja à qual o usuário esteja associado via catálogo de endereços).</span><span class="sxs-lookup"><span data-stu-id="61b86-117">This permission lets a user view the time clock registrations of other workers in the store (and from any other store that the user is associated with, via the address book).</span></span> <span data-ttu-id="61b86-118">Convém habilitar essa permissão para uma função gerente, mas não para uma função caixa.</span><span class="sxs-lookup"><span data-stu-id="61b86-118">You might want to enable this permission for a manager role but not for a cashier role.</span></span> <span data-ttu-id="61b86-119">Clique em **Grupos de permissões de PDV** &gt; **Exibir entradas do relógio de ponto**.</span><span class="sxs-lookup"><span data-stu-id="61b86-119">Click **POS permission groups** &gt; **View time clock entries**.</span></span>

## <a name="register-time"></a><span data-ttu-id="61b86-120">Hora de registro</span><span class="sxs-lookup"><span data-stu-id="61b86-120">Register time</span></span>

### <a name="cashier-and-non-cashier-time-registrations"></a><span data-ttu-id="61b86-121">Registros de horas para caixa e não caixa</span><span class="sxs-lookup"><span data-stu-id="61b86-121">Cashier and non-cashier time registrations</span></span>

- <span data-ttu-id="61b86-122">No PDV:</span><span class="sxs-lookup"><span data-stu-id="61b86-122">On POS:</span></span>

    - <span data-ttu-id="61b86-123">Operações de registro de entrada.</span><span class="sxs-lookup"><span data-stu-id="61b86-123">Clock-in operations:</span></span>

        - <span data-ttu-id="61b86-124">Faça logon com uma operação não sacadora ou novo turno.</span><span class="sxs-lookup"><span data-stu-id="61b86-124">Log on with a non-drawer operation or New shift.</span></span>
        - <span data-ttu-id="61b86-125">Selecione uma operação de relógio de ponto.</span><span class="sxs-lookup"><span data-stu-id="61b86-125">Select a Time Clock operation.</span></span>
        - <span data-ttu-id="61b86-126">Selecione uma operação desejada:</span><span class="sxs-lookup"><span data-stu-id="61b86-126">Select a desired operation:</span></span>

            - <span data-ttu-id="61b86-127">Registro de entrada</span><span class="sxs-lookup"><span data-stu-id="61b86-127">Clock-in</span></span>
            - <span data-ttu-id="61b86-128">Intervalo de trabalho</span><span class="sxs-lookup"><span data-stu-id="61b86-128">Break for Work</span></span>
            - <span data-ttu-id="61b86-129">Intervalo para o Almoço</span><span class="sxs-lookup"><span data-stu-id="61b86-129">Break for Lunch</span></span>
            - <span data-ttu-id="61b86-130">Registro de saída</span><span class="sxs-lookup"><span data-stu-id="61b86-130">Clock-out</span></span>

        <table>
        <thead>
        <tr>
        <th><span data-ttu-id="61b86-131">Status atual</span><span class="sxs-lookup"><span data-stu-id="61b86-131">Current state</span></span></th>
        <th><span data-ttu-id="61b86-132">Operações disponíveis</span><span class="sxs-lookup"><span data-stu-id="61b86-132">Available operations</span></span></th>
        </tr>
        </thead>
        <tbody>
        <tr>
        <td><span data-ttu-id="61b86-133">Registro de entrada</span><span class="sxs-lookup"><span data-stu-id="61b86-133">Clock-in</span></span></td>
        <td>
        <ul>
        <li><span data-ttu-id="61b86-134">Intervalo de trabalho</span><span class="sxs-lookup"><span data-stu-id="61b86-134">Break for Work</span></span></li>
        <li><span data-ttu-id="61b86-135">Intervalo para o Almoço</span><span class="sxs-lookup"><span data-stu-id="61b86-135">Break for Lunch</span></span></li>
        <li><span data-ttu-id="61b86-136">Registro de saída</span><span class="sxs-lookup"><span data-stu-id="61b86-136">Clock-out</span></span></li>
        </ul>
        </td>
        </tr>
        <tr>
        <td><span data-ttu-id="61b86-137">Intervalo de trabalho</span><span class="sxs-lookup"><span data-stu-id="61b86-137">Break for Work</span></span></td>
        <td><span data-ttu-id="61b86-138">Registro de entrada</span><span class="sxs-lookup"><span data-stu-id="61b86-138">Clock-in</span></span></td>
        </tr>
        <tr>
        <td><span data-ttu-id="61b86-139">Intervalo para o Almoço</span><span class="sxs-lookup"><span data-stu-id="61b86-139">Break for Lunch</span></span></td>
        <td><span data-ttu-id="61b86-140">Registro de entrada</span><span class="sxs-lookup"><span data-stu-id="61b86-140">Clock-in</span></span></td>
        </tr>
        <tr>
        <td><span data-ttu-id="61b86-141">Registro de saída</span><span class="sxs-lookup"><span data-stu-id="61b86-141">Clock-out</span></span></td>
        <td><span data-ttu-id="61b86-142">Registro de entrada</span><span class="sxs-lookup"><span data-stu-id="61b86-142">Clock-in</span></span></td>
        </tr>
        </tbody>
        </table>

        <span data-ttu-id="61b86-143">[![TimeClockStates](./media/timeclockstates.png)](./media/timeclockstates.png)</span><span class="sxs-lookup"><span data-stu-id="61b86-143">[![TimeClockStates](./media/timeclockstates.png)](./media/timeclockstates.png)</span></span>

- <span data-ttu-id="61b86-144">Exiba a mensagem de confirmação e valide que o tempo da atividade atual está correto.</span><span class="sxs-lookup"><span data-stu-id="61b86-144">View the confirmation message, and validate that the current activity time is correct.</span></span>
- <span data-ttu-id="61b86-145">Livro de registros:</span><span class="sxs-lookup"><span data-stu-id="61b86-145">Logbook:</span></span>

    - <span data-ttu-id="61b86-146">Clique em **Livro de registros** para exibir a atividade do relógio de ponto.</span><span class="sxs-lookup"><span data-stu-id="61b86-146">Click **Logbook** to view time clock activity.</span></span>
    - <span data-ttu-id="61b86-147">Use os filtros de tempo para selecionar períodos diferentes.</span><span class="sxs-lookup"><span data-stu-id="61b86-147">Use time filters to select different time windows.</span></span>
    - <span data-ttu-id="61b86-148">Se você trabalhar em vários locais de loja, verá os registros de horas de todas as lojas em que você registrou ponto.</span><span class="sxs-lookup"><span data-stu-id="61b86-148">If you work at multiple store locations, you see your time registrations from all the stores where you recorded time.</span></span> <span data-ttu-id="61b86-149">Você pode usar o filtro de loja para exibir os registros de horas de uma loja selecionada.</span><span class="sxs-lookup"><span data-stu-id="61b86-149">You can use the store filter to view time registrations from a selected store.</span></span>

- <span data-ttu-id="61b86-150">Fusos horários diferentes:</span><span class="sxs-lookup"><span data-stu-id="61b86-150">Different time zones:</span></span>

    - <span data-ttu-id="61b86-151">Se você exibir as horas de um local diferente (para o livro de registros do caixa ou usando **Exibir entradas do relógio de ponto** em um cenário do gerente) e esse local estiver em um fuso horário diferente, os registros de horas exibidos serão convertidos em seu fuso horário local.</span><span class="sxs-lookup"><span data-stu-id="61b86-151">If you view time from a different location (for the cashier logbook, or by using **View timeclock entries** for a manager scenario), and that location is in a different time zone, the time records that you see are converted to your local time zone.</span></span> <span data-ttu-id="61b86-152">Por exemplo, você é gerente de duas lojas, uma no Arizona e outra em Nevada.</span><span class="sxs-lookup"><span data-stu-id="61b86-152">For example, you are a manager for two stores, one in Arizona and the other in Nevada.</span></span> <span data-ttu-id="61b86-153">Um caixa registra a entrada às 9:00 A.M.</span><span class="sxs-lookup"><span data-stu-id="61b86-153">A cashier registers a clock-in at 9:00 A.M.</span></span> <span data-ttu-id="61b86-154">no Arizona.</span><span class="sxs-lookup"><span data-stu-id="61b86-154">in Arizona.</span></span> <span data-ttu-id="61b86-155">Nesse momento, são 8h em Nevada.</span><span class="sxs-lookup"><span data-stu-id="61b86-155">At that moment, the time in Nevada is 8:00 A.M.</span></span> <span data-ttu-id="61b86-156">Portanto, se você estiver na loja de Nevada e observar os registros de horas, verá o registro marcando 8h.</span><span class="sxs-lookup"><span data-stu-id="61b86-156">Therefore, if you are in the Nevada store and look at time registration records, the time registration is marked as 8 A.M.</span></span>

## <a name="view-worker-time-registrations"></a><span data-ttu-id="61b86-157">Exibir registros de tempo de funcionário</span><span class="sxs-lookup"><span data-stu-id="61b86-157">View worker time registrations</span></span>

### <a name="view-worker-time-registrations-and-filter-by-store-or-activity-type"></a><span data-ttu-id="61b86-158">Exibir registros de horas do trabalhador e filtrar por tipo de loja ou atividade</span><span class="sxs-lookup"><span data-stu-id="61b86-158">View worker time registrations, and filter by store or activity type</span></span>

<span data-ttu-id="61b86-159">No PDV:</span><span class="sxs-lookup"><span data-stu-id="61b86-159">On POS:</span></span>

- <span data-ttu-id="61b86-160">Selecione **Exibir entradas do relógio de ponto**.</span><span class="sxs-lookup"><span data-stu-id="61b86-160">Select **View timeclock entries**.</span></span>
- <span data-ttu-id="61b86-161">Você verá atividades de registro do relógio de ponto de todos os trabalhadores atribuídos às mesmas lojas às quais você está atribuído.</span><span class="sxs-lookup"><span data-stu-id="61b86-161">You see time clock registration activities from all workers that are assigned to the same stores that you're assigned to.</span></span>
- <span data-ttu-id="61b86-162">Você pode usar os filtros de loja e tipo de atividade para filtrar os registros de horas.</span><span class="sxs-lookup"><span data-stu-id="61b86-162">You can use the activity type and store filters to filter on time registrations.</span></span>

## <a name="process-and-manage-time-registrations"></a><span data-ttu-id="61b86-163">Processar e gerenciar registros de tempos</span><span class="sxs-lookup"><span data-stu-id="61b86-163">Process and manage time registrations</span></span>

<span data-ttu-id="61b86-164">Um usuário do Retail segue o fluxo de trabalho para calcular, aprovar e transferir registros de horas para a folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="61b86-164">A Retail user follows the workflow to calculate, approve, and transfer time registrations to payroll.</span></span>

### <a name="primary-operations"></a><span data-ttu-id="61b86-165">Operações principais</span><span class="sxs-lookup"><span data-stu-id="61b86-165">Primary operations</span></span>

- <span data-ttu-id="61b86-166">Calcular</span><span class="sxs-lookup"><span data-stu-id="61b86-166">Calculate</span></span>
- <span data-ttu-id="61b86-167">Aprovar</span><span class="sxs-lookup"><span data-stu-id="61b86-167">Approve</span></span>
- <span data-ttu-id="61b86-168">Enviar para folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="61b86-168">Submit to payroll</span></span>

### <a name="other-common-operations"></a><span data-ttu-id="61b86-169">Outras operações comuns</span><span class="sxs-lookup"><span data-stu-id="61b86-169">Other common operations</span></span>

- <span data-ttu-id="61b86-170">Saída em massa</span><span class="sxs-lookup"><span data-stu-id="61b86-170">Bulk Clock-out</span></span>
- <span data-ttu-id="61b86-171">Registrar ausência</span><span class="sxs-lookup"><span data-stu-id="61b86-171">Register Absence</span></span>

<span data-ttu-id="61b86-172">Para obter mais informações sobre como processar registros de tempo e presença, consulte [Processar os registros de tempo e presença](https://technet.microsoft.com/library/aa573180.aspx).</span><span class="sxs-lookup"><span data-stu-id="61b86-172">For more information about how to process time and attendance registrations, see [Process time and attendance registrations](https://technet.microsoft.com/library/aa573180.aspx).</span></span>

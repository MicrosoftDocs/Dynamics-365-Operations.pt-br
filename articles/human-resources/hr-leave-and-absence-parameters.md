---
title: Configurar parâmetros de licença e ausência
description: Definir parâmetros de recursos humanos para licença e ausência no Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 08/20/2020
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
ms.openlocfilehash: 196c3901b5bc19f73b882bac7d3361e5bcc37e07
ms.sourcegitcommit: 2bcacef1e010c312f019dbf9740ce87d627848a7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/20/2020
ms.locfileid: "3712367"
---
# <a name="configure-leave-and-absence-parameters"></a><span data-ttu-id="f33b3-103">Configurar parâmetros de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="f33b3-103">Configure leave and absence parameters</span></span>

<span data-ttu-id="f33b3-104">Antes de configurar os planos de licença e ausência no Dynamics 365 Human Resources, convém verificar as configurações de todos os parâmetros de recursos humanos relacionados, incluindo:</span><span class="sxs-lookup"><span data-stu-id="f33b3-104">Before you set up leave and absence plans in Dynamics 365 Human Resources, it's a good idea to verify the settings for all related human resources parameters, including:</span></span>

- <span data-ttu-id="f33b3-105">Sequência numérica para solicitações de licença</span><span class="sxs-lookup"><span data-stu-id="f33b3-105">Number sequence for leave requests</span></span>
- <span data-ttu-id="f33b3-106">Lei de família de licença e médica (FMLA)</span><span class="sxs-lookup"><span data-stu-id="f33b3-106">Family Medical and Leave Act (FMLA) settings</span></span>
- <span data-ttu-id="f33b3-107">Configurações de auto-atendimento para funcionário para solicitações de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="f33b3-107">Employee self service settings for leave and absence requests</span></span>
- <span data-ttu-id="f33b3-108">Parâmetros de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="f33b3-108">Leave and absence parameters</span></span>

## <a name="view-and-change-human-resources-parameters"></a><span data-ttu-id="f33b3-109">Exibir e alterar parâmetros de recursos humanos</span><span class="sxs-lookup"><span data-stu-id="f33b3-109">View and change human resources parameters</span></span>

1. <span data-ttu-id="f33b3-110">Na página **Licença e ausência**, selecione a guia **Links**.</span><span class="sxs-lookup"><span data-stu-id="f33b3-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="f33b3-111">Em **Configuração**, selecione **Parâmetros de recursos humanos**.</span><span class="sxs-lookup"><span data-stu-id="f33b3-111">Under **Setup**, select **Human resources parameters**.</span></span>

3. <span data-ttu-id="f33b3-112">Na guia **Sequências numéricas**, verifique o **Código de sequência numérica** para **ID de solicitação de licença** e faça as alterações necessárias.</span><span class="sxs-lookup"><span data-stu-id="f33b3-112">On the **Number sequences** tab, verify the **Number sequence code** for **Leave request ID** and change as necessary.</span></span> <span data-ttu-id="f33b3-113">Esta configuração determina a sequência usada para atribuir automaticamente IDs a solicitações de licença.</span><span class="sxs-lookup"><span data-stu-id="f33b3-113">This setting determines the sequence used for automatically assigning IDs to leave requests.</span></span>

4. <span data-ttu-id="f33b3-114">Na guia **FMLA**, verifique as configurações de FMLA e altere conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="f33b3-114">On the **FMLA** tab, verify the FMLA settings and change as necessary.</span></span>

5. <span data-ttu-id="f33b3-115">Na guia **Autoatendimento para funcionários**, indique se os gerentes podem inserir solicitações de licença e ausência em nome de seus funcionários.</span><span class="sxs-lookup"><span data-stu-id="f33b3-115">On the **Employee self service** tab, indicate whether managers can enter leave and absence requests on behalf of their employees.</span></span>

7. <span data-ttu-id="f33b3-116">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f33b3-116">Select **Save**.</span></span>

## <a name="view-and-change-leave-and-absence-parameters"></a><span data-ttu-id="f33b3-117">Exibir e alterar parâmetros de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="f33b3-117">View and change leave and absence parameters</span></span>

1. <span data-ttu-id="f33b3-118">Na página **Licença e ausência**, selecione a guia **Links**.</span><span class="sxs-lookup"><span data-stu-id="f33b3-118">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="f33b3-119">Em **Configuração**, selecione **Parâmetros de licença e ausência**.</span><span class="sxs-lookup"><span data-stu-id="f33b3-119">Under **Setup**, select **Leave and absence parameters**.</span></span>

3. <span data-ttu-id="f33b3-120">Na guia **Geral**, defina os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="f33b3-120">On the **General** tab, set the following parameters:</span></span>
 
    - <span data-ttu-id="f33b3-121">Defina a **Unidade para licença e ausência** em horas ou dias.</span><span class="sxs-lookup"><span data-stu-id="f33b3-121">Set **Unit for leave and absence** to either hours or days.</span></span> <span data-ttu-id="f33b3-122">Em caso de dias, você pode selecionar **Habilitar definição de meio dia** para permitir que os funcionários escolham a primeira ou a segunda metade do dia em suas solicitações de tempo limite.</span><span class="sxs-lookup"><span data-stu-id="f33b3-122">If days, you can select **Enable half day definition** to allow employees to choose either first or second half of day in their time-off requests.</span></span> 

    - <span data-ttu-id="f33b3-123">Selecione **Meses de data de efetivação do serviço** para definir quando as taxas de acumulação entram em vigor para os planos de licença usando meses de serviço.</span><span class="sxs-lookup"><span data-stu-id="f33b3-123">Select **Months of service effective date** to set when the accrual rates take effect for leave plans using months of service.</span></span>

    - <span data-ttu-id="f33b3-124">Selecione **Cálculo de saldo** para exibir saldos a partir de hoje ou a partir do período de competência.</span><span class="sxs-lookup"><span data-stu-id="f33b3-124">Select **Balance calculation** to display balances as of today or as of the accrual period.</span></span> <span data-ttu-id="f33b3-125">Se você selecionar **Saldo a partir de hoje**, o saldo exibirá o total de todas as competências, ajustes e solicitações a partir de hoje.</span><span class="sxs-lookup"><span data-stu-id="f33b3-125">If you select **Balance as of today**, the balance displays the total of all accruals, adjustments, and requests as of today.</span></span> <span data-ttu-id="f33b3-126">Se você selecionar **Saldo como período de acumulação**, o saldo exibirá o total de todas as competências, ajustes e solicitações, a partir do período de acumulação definido pela frequência no plano de licença.</span><span class="sxs-lookup"><span data-stu-id="f33b3-126">If you select **Balance as of accrual period**, the balance displays the total of all accruals, adjustments, and requests as of the accrual period defined by the frequency in the leave plan.</span></span> 

    - <span data-ttu-id="f33b3-127">Defina a hora inicial do trabalho em lotes de expiração postergada.</span><span class="sxs-lookup"><span data-stu-id="f33b3-127">Set the start time for the carry forward expiration batch job.</span></span>  
    
    - <span data-ttu-id="f33b3-128">Selecione **Sim** para **Permitir que os funcionários comprem licenças** e **Permitir que os funcionários vendam licença**.</span><span class="sxs-lookup"><span data-stu-id="f33b3-128">Select **Yes** for **Allow employees to buy leave** and **Allow employees to sell leave**.</span></span> <span data-ttu-id="f33b3-129">Se você selecionar **Sim** para essas opções, poderá criar políticas de licença de compra e venda e permitir que os funcionários enviem solicitações de compra e venda de licenças.</span><span class="sxs-lookup"><span data-stu-id="f33b3-129">If you select **Yes** for these options, you can create buy and sell leave policies and enable employees to submit buy and sell leave requests.</span></span>

## <a name="configure-calendar-parameters"></a><span data-ttu-id="f33b3-130">Configure parâmetros de calendário.</span><span class="sxs-lookup"><span data-stu-id="f33b3-130">Configure calendar parameters</span></span>

1. <span data-ttu-id="f33b3-131">Na página **Licença e ausência**, selecione a guia **Links**.</span><span class="sxs-lookup"><span data-stu-id="f33b3-131">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="f33b3-132">Em **Configuração**, selecione **Parâmetros de licença e ausência**.</span><span class="sxs-lookup"><span data-stu-id="f33b3-132">Under **Setup**, select **Leave and absence parameters**.</span></span>

3. <span data-ttu-id="f33b3-133">Na guia **Calendário**, altere as configurações de calendário, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="f33b3-133">On the **Calendar** tab, change calendar settings as necessary.</span></span>

4. <span data-ttu-id="f33b3-134">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f33b3-134">Select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="f33b3-135">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f33b3-135">See also</span></span>

- [<span data-ttu-id="f33b3-136">Visão geral de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="f33b3-136">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)

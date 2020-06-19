---
title: Configurar parâmetros de licença e ausência
description: Definir parâmetros de recursos humanos para licença e ausência no Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 04/01/2020
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
ms.openlocfilehash: 5e4d3b3e4b373631bed5e2d7e3c3a4e14f0c5c98
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2020
ms.locfileid: "3428935"
---
# <a name="configure-leave-and-absence-parameters"></a><span data-ttu-id="64734-103">Configurar parâmetros de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="64734-103">Configure leave and absence parameters</span></span>

<span data-ttu-id="64734-104">Antes de configurar os planos de licença e ausência no Dynamics 365 Human Resources, convém verificar as configurações de todos os parâmetros de recursos humanos relacionados, incluindo:</span><span class="sxs-lookup"><span data-stu-id="64734-104">Before you set up leave and absence plans in Dynamics 365 Human Resources, it's a good idea to verify the settings for all related human resources parameters, including:</span></span>

- <span data-ttu-id="64734-105">Sequência numérica para solicitações de licença</span><span class="sxs-lookup"><span data-stu-id="64734-105">Number sequence for leave requests</span></span>
- <span data-ttu-id="64734-106">Lei de família de licença e médica (FMLA)</span><span class="sxs-lookup"><span data-stu-id="64734-106">Family Medical and Leave Act (FMLA) settings</span></span>
- <span data-ttu-id="64734-107">Configurações de auto-atendimento para funcionário para solicitações de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="64734-107">Employee self service settings for leave and absence requests</span></span>
- <span data-ttu-id="64734-108">Parâmetros de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="64734-108">Leave and absence parameters</span></span>

## <a name="view-and-change-human-resources-parameters"></a><span data-ttu-id="64734-109">Exibir e alterar parâmetros de recursos humanos</span><span class="sxs-lookup"><span data-stu-id="64734-109">View and change human resources parameters</span></span>

1. <span data-ttu-id="64734-110">Na página **Licença e ausência**, selecione a guia **Links**.</span><span class="sxs-lookup"><span data-stu-id="64734-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="64734-111">Em **Configuração**, selecione **Parâmetros de recursos humanos**.</span><span class="sxs-lookup"><span data-stu-id="64734-111">Under **Setup**, select **Human resources parameters**.</span></span>

3. <span data-ttu-id="64734-112">Na guia **Sequências numéricas**, verifique o **Código de sequência numérica** para **ID de solicitação de licença** e faça as alterações necessárias.</span><span class="sxs-lookup"><span data-stu-id="64734-112">On the **Number sequences** tab, verify the **Number sequence code** for **Leave request ID** and change as necessary.</span></span> <span data-ttu-id="64734-113">Esta configuração determina a sequência usada para atribuir automaticamente IDs a solicitações de licença.</span><span class="sxs-lookup"><span data-stu-id="64734-113">This setting determines the sequence used for automatically assigning IDs to leave requests.</span></span>

4. <span data-ttu-id="64734-114">Na guia **FMLA**, verifique as configurações de FMLA e altere conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="64734-114">On the **FMLA** tab, verify the FMLA settings and change as necessary.</span></span>

5. <span data-ttu-id="64734-115">Na guia **Autoatendimento para funcionários**, indique se os gerentes podem inserir solicitações de licença e ausência em nome de seus funcionários.</span><span class="sxs-lookup"><span data-stu-id="64734-115">On the **Employee self service** tab, indicate whether managers can enter leave and absence requests on behalf of their employees.</span></span>

6. <span data-ttu-id="64734-116">Na guia **Licença e ausência**, verifique as configurações e altere conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="64734-116">On the **Leave and absence** tab, verify the settings and change as necessary.</span></span>

7. <span data-ttu-id="64734-117">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="64734-117">Select **Save**.</span></span>

## <a name="view-and-change-leave-and-absence-parameters"></a><span data-ttu-id="64734-118">Exibir e alterar parâmetros de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="64734-118">View and change leave and absence parameters</span></span>

1. <span data-ttu-id="64734-119">Na página **Licença e ausência**, selecione a guia **Links**.</span><span class="sxs-lookup"><span data-stu-id="64734-119">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="64734-120">Em **Configuração**, selecione **Parâmetros de licença e ausência**.</span><span class="sxs-lookup"><span data-stu-id="64734-120">Under **Setup**, select **Leave and absence parameters**.</span></span>

3. <span data-ttu-id="64734-121">Na guia **Geral**, defina os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="64734-121">On the **General** tab, set the following parameters:</span></span>
 
    - <span data-ttu-id="64734-122">Defina a **Unidade para licença e ausência** em horas ou dias.</span><span class="sxs-lookup"><span data-stu-id="64734-122">Set **Unit for leave and absence** to either hours or days.</span></span> <span data-ttu-id="64734-123">Em caso de dias, você pode selecionar **Habilitar definição de meio dia** para permitir que os funcionários escolham a primeira ou a segunda metade do dia em suas solicitações de tempo limite.</span><span class="sxs-lookup"><span data-stu-id="64734-123">If days, you can select **Enable half day definition** to allow employees to choose either first or second half of day in their time-off requests.</span></span> 

    - <span data-ttu-id="64734-124">Selecione **Meses de data de efetivação do serviço** para definir quando as taxas de acumulação entram em vigor para os planos de licença usando meses de serviço.</span><span class="sxs-lookup"><span data-stu-id="64734-124">Select **Months of service effective date** to set when the accrual rates take effect for leave plans using months of service.</span></span>

    - <span data-ttu-id="64734-125">Selecione **Cálculo de saldo** para exibir saldos a serem exibidos a partir de hoje ou a partir do período de acumulação.</span><span class="sxs-lookup"><span data-stu-id="64734-125">Select **Balance calculation** to display balances display as of today or as of the accrual period.</span></span> <span data-ttu-id="64734-126">Se você selecionar **Saldo a partir de hoje**, o saldo exibirá o total de todas as competências, ajustes e solicitações a partir de hoje.</span><span class="sxs-lookup"><span data-stu-id="64734-126">If you select **Balance as of today**, the balance displays the total of all accruals, adjustments, and requests as of today.</span></span> <span data-ttu-id="64734-127">Se você selecionar **Saldo como período de acumulação**, o saldo exibirá o total de todas as competências, ajustes e solicitações, a partir do período de acumulação definido pela frequência no plano de licença.</span><span class="sxs-lookup"><span data-stu-id="64734-127">If you select **Balance as of accrual period**, the balance displays the total of all accruals, adjustments, and requests as of the accrual period defined by the frequency in the leave plan.</span></span> 

## <a name="configure-calendar-parameters"></a><span data-ttu-id="64734-128">Configure parâmetros de calendário.</span><span class="sxs-lookup"><span data-stu-id="64734-128">Configure calendar parameters</span></span>

1. <span data-ttu-id="64734-129">Na página **Licença e ausência**, selecione a guia **Links**.</span><span class="sxs-lookup"><span data-stu-id="64734-129">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="64734-130">Em **Configuração**, selecione **Parâmetros de licença e ausência**.</span><span class="sxs-lookup"><span data-stu-id="64734-130">Under **Setup**, select **Leave and absence parameters**.</span></span>

3. <span data-ttu-id="64734-131">Na guia **Calendário**, altere as configurações de calendário, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="64734-131">On the **Calendar** tab, change calendar settings as necessary.</span></span>

4. <span data-ttu-id="64734-132">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="64734-132">Select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="64734-133">Consulte também</span><span class="sxs-lookup"><span data-stu-id="64734-133">See also</span></span>

- [<span data-ttu-id="64734-134">Visão geral de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="64734-134">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)

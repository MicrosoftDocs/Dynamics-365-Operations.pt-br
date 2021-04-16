---
title: Configurar parâmetros de licença e ausência
description: Definir parâmetros de recursos humanos para licença e ausência no Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 11/02/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 45f5ebfe7bd11a529e871f5fd3244577954534f5
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794628"
---
# <a name="configure-leave-and-absence-parameters"></a><span data-ttu-id="99cb5-103">Configurar parâmetros de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="99cb5-103">Configure leave and absence parameters</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="99cb5-104">Antes de configurar os planos de licença e ausência no Dynamics 365 Human Resources, convém verificar as configurações de todos os parâmetros de recursos humanos relacionados, incluindo:</span><span class="sxs-lookup"><span data-stu-id="99cb5-104">Before you set up leave and absence plans in Dynamics 365 Human Resources, it's a good idea to verify the settings for all related human resources parameters, including:</span></span>

- <span data-ttu-id="99cb5-105">Sequência numérica para solicitações de licença</span><span class="sxs-lookup"><span data-stu-id="99cb5-105">Number sequence for leave requests</span></span>
- <span data-ttu-id="99cb5-106">Lei de família de licença e médica (FMLA)</span><span class="sxs-lookup"><span data-stu-id="99cb5-106">Family Medical and Leave Act (FMLA) settings</span></span>
- <span data-ttu-id="99cb5-107">Configurações de auto-atendimento para funcionário para solicitações de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="99cb5-107">Employee self service settings for leave and absence requests</span></span>
- <span data-ttu-id="99cb5-108">Parâmetros de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="99cb5-108">Leave and absence parameters</span></span>

## <a name="view-and-change-human-resources-parameters"></a><span data-ttu-id="99cb5-109">Exibir e alterar parâmetros de recursos humanos</span><span class="sxs-lookup"><span data-stu-id="99cb5-109">View and change human resources parameters</span></span>

1. <span data-ttu-id="99cb5-110">Na página **Licença e ausência**, selecione a guia **Links**.</span><span class="sxs-lookup"><span data-stu-id="99cb5-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="99cb5-111">Em **Configuração**, selecione **Parâmetros de recursos humanos**.</span><span class="sxs-lookup"><span data-stu-id="99cb5-111">Under **Setup**, select **Human resources parameters**.</span></span>

3. <span data-ttu-id="99cb5-112">Na guia **Sequências numéricas**, verifique o **Código de sequência numérica** para **ID de solicitação de licença** e faça as alterações necessárias.</span><span class="sxs-lookup"><span data-stu-id="99cb5-112">On the **Number sequences** tab, verify the **Number sequence code** for **Leave request ID** and change as necessary.</span></span> <span data-ttu-id="99cb5-113">Esta configuração determina a sequência usada para atribuir automaticamente IDs a solicitações de licença.</span><span class="sxs-lookup"><span data-stu-id="99cb5-113">This setting determines the sequence used for automatically assigning IDs to leave requests.</span></span>

4. <span data-ttu-id="99cb5-114">Na guia **FMLA**, verifique as configurações de FMLA e altere conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="99cb5-114">On the **FMLA** tab, verify the FMLA settings and change as necessary.</span></span>

5. <span data-ttu-id="99cb5-115">Na guia **Autoatendimento para funcionários**, indique se os gerentes podem inserir solicitações de licença e ausência em nome de seus funcionários.</span><span class="sxs-lookup"><span data-stu-id="99cb5-115">On the **Employee self service** tab, indicate whether managers can enter leave and absence requests on behalf of their employees.</span></span>

7. <span data-ttu-id="99cb5-116">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="99cb5-116">Select **Save**.</span></span>

>[!IMPORTANT]
><span data-ttu-id="99cb5-117">A exibição de licenças e ausências em empresas está no momento em versão prévia.</span><span class="sxs-lookup"><span data-stu-id="99cb5-117">Viewing leave and absence across companies is currently in preview.</span></span> <span data-ttu-id="99cb5-118">Você precisará habilitá-la no ambiente **Área restrita** para exibir a opção de licença e ausência.</span><span class="sxs-lookup"><span data-stu-id="99cb5-118">You'll need to enable it in your **Sandbox** environment to display the option for leave and absence.</span></span> <span data-ttu-id="99cb5-119">Para obter mais informações sobre as versões prévias do recurso, consulte [Gerenciar recursos](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="99cb5-119">For more information about enabling preview features, see [Manage features](hr-admin-manage-features.md).</span></span>

## <a name="view-and-change-human-resources-shared-parameters"></a><span data-ttu-id="99cb5-120">Exibir e alterar parâmetros compartilhados de recursos humanos</span><span class="sxs-lookup"><span data-stu-id="99cb5-120">View and change Human resources shared parameters</span></span>

1. <span data-ttu-id="99cb5-121">Na página **Gerenciamento de pessoal**, selecione a guia **Links**.</span><span class="sxs-lookup"><span data-stu-id="99cb5-121">On the **Personnel management** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="99cb5-122">Em **Configuração**, selecione **Parâmetros compartilhados de recursos humanos**.</span><span class="sxs-lookup"><span data-stu-id="99cb5-122">Under **Setup**, select **Human resources shared parameters**.</span></span>

3. <span data-ttu-id="99cb5-123">Na guia **Acesso avançado**, selecione **Sim** para **Habilitar a exibição de licença entre empresas** para permitir que a licença seja exibida entre empresas.</span><span class="sxs-lookup"><span data-stu-id="99cb5-123">On the **Advance access** tab, select **Yes** for **Enable cross company leave view** to allow leave to be viewed across company.</span></span>

4. <span data-ttu-id="99cb5-124">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="99cb5-124">Select **Save**.</span></span>

## <a name="view-and-change-leave-and-absence-parameters"></a><span data-ttu-id="99cb5-125">Exibir e alterar parâmetros de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="99cb5-125">View and change leave and absence parameters</span></span>

1. <span data-ttu-id="99cb5-126">Na página **Licença e ausência**, selecione a guia **Links**.</span><span class="sxs-lookup"><span data-stu-id="99cb5-126">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="99cb5-127">Em **Configuração**, selecione **Parâmetros de licença e ausência**.</span><span class="sxs-lookup"><span data-stu-id="99cb5-127">Under **Setup**, select **Leave and absence parameters**.</span></span>

3. <span data-ttu-id="99cb5-128">Na guia **Geral**, defina os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="99cb5-128">On the **General** tab, set the following parameters:</span></span>
 
    - <span data-ttu-id="99cb5-129">Defina a **Unidade para licença e ausência** em horas ou dias.</span><span class="sxs-lookup"><span data-stu-id="99cb5-129">Set **Unit for leave and absence** to either hours or days.</span></span> <span data-ttu-id="99cb5-130">Em caso de dias, você pode selecionar **Habilitar definição de meio dia** para permitir que os funcionários escolham a primeira ou a segunda metade do dia em suas solicitações de tempo limite.</span><span class="sxs-lookup"><span data-stu-id="99cb5-130">If days, you can select **Enable half day definition** to allow employees to choose either first or second half of day in their time-off requests.</span></span> 

    - <span data-ttu-id="99cb5-131">Selecione **Meses de data de efetivação do serviço** para definir quando as taxas de acumulação entram em vigor para os planos de licença usando meses de serviço.</span><span class="sxs-lookup"><span data-stu-id="99cb5-131">Select **Months of service effective date** to set when the accrual rates take effect for leave plans using months of service.</span></span>

    - <span data-ttu-id="99cb5-132">Selecione **Cálculo de saldo** para exibir saldos a partir de hoje ou a partir do período de competência.</span><span class="sxs-lookup"><span data-stu-id="99cb5-132">Select **Balance calculation** to display balances as of today or as of the accrual period.</span></span> <span data-ttu-id="99cb5-133">Se você selecionar **Saldo a partir de hoje**, o saldo exibirá o total de todas as competências, ajustes e solicitações a partir de hoje.</span><span class="sxs-lookup"><span data-stu-id="99cb5-133">If you select **Balance as of today**, the balance displays the total of all accruals, adjustments, and requests as of today.</span></span> <span data-ttu-id="99cb5-134">Se você selecionar **Saldo como período de acumulação**, o saldo exibirá o total de todas as competências, ajustes e solicitações, a partir do período de acumulação definido pela frequência no plano de licença.</span><span class="sxs-lookup"><span data-stu-id="99cb5-134">If you select **Balance as of accrual period**, the balance displays the total of all accruals, adjustments, and requests as of the accrual period defined by the frequency in the leave plan.</span></span> 

    - <span data-ttu-id="99cb5-135">Defina a hora inicial do trabalho em lotes de expiração postergada.</span><span class="sxs-lookup"><span data-stu-id="99cb5-135">Set the start time for the carry forward expiration batch job.</span></span>  
    
    - <span data-ttu-id="99cb5-136">Selecione **Sim** para **Permitir que os funcionários comprem licenças** e **Permitir que os funcionários vendam licença**.</span><span class="sxs-lookup"><span data-stu-id="99cb5-136">Select **Yes** for **Allow employees to buy leave** and **Allow employees to sell leave**.</span></span> <span data-ttu-id="99cb5-137">Se você selecionar **Sim** para essas opções, poderá criar políticas de licença de compra e venda e permitir que os funcionários enviem solicitações de compra e venda de licenças.</span><span class="sxs-lookup"><span data-stu-id="99cb5-137">If you select **Yes** for these options, you can create buy and sell leave policies and enable employees to submit buy and sell leave requests.</span></span>

## <a name="configure-calendar-parameters"></a><span data-ttu-id="99cb5-138">Configure parâmetros de calendário.</span><span class="sxs-lookup"><span data-stu-id="99cb5-138">Configure calendar parameters</span></span>

1. <span data-ttu-id="99cb5-139">Na página **Licença e ausência**, selecione a guia **Links**.</span><span class="sxs-lookup"><span data-stu-id="99cb5-139">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="99cb5-140">Em **Configuração**, selecione **Parâmetros de licença e ausência**.</span><span class="sxs-lookup"><span data-stu-id="99cb5-140">Under **Setup**, select **Leave and absence parameters**.</span></span>

3. <span data-ttu-id="99cb5-141">Na guia **Calendário**, altere as configurações de calendário, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="99cb5-141">On the **Calendar** tab, change calendar settings as necessary.</span></span>

4. <span data-ttu-id="99cb5-142">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="99cb5-142">Select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="99cb5-143">Consulte também</span><span class="sxs-lookup"><span data-stu-id="99cb5-143">See also</span></span>

- [<span data-ttu-id="99cb5-144">Visão geral de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="99cb5-144">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
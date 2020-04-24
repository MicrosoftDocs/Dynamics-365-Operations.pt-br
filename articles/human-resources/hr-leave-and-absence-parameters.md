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
ms.openlocfilehash: eb992cbfbed33f88e125d3a8b721f8815414599a
ms.sourcegitcommit: 79f8aa2c0b166a423db9b8503da53e96e3fc43dc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2020
ms.locfileid: "3197972"
---
# <a name="configure-leave-and-absence-parameters"></a><span data-ttu-id="ab53c-103">Configurar parâmetros de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="ab53c-103">Configure leave and absence parameters</span></span>

<span data-ttu-id="ab53c-104">Antes de configurar os planos de licença e ausência no Dynamics 365 Human Resources, convém verificar as configurações de todos os parâmetros de recursos humanos relacionados, incluindo:</span><span class="sxs-lookup"><span data-stu-id="ab53c-104">Before you set up leave and absence plans in Dynamics 365 Human Resources, it's a good idea to verify the settings for all related human resources parameters, including:</span></span>

- <span data-ttu-id="ab53c-105">Sequência numérica para solicitações de licença</span><span class="sxs-lookup"><span data-stu-id="ab53c-105">Number sequence for leave requests</span></span>
- <span data-ttu-id="ab53c-106">Lei de família de licença e médica (FMLA)</span><span class="sxs-lookup"><span data-stu-id="ab53c-106">Family Medical and Leave Act (FMLA) settings</span></span>
- <span data-ttu-id="ab53c-107">Configurações de auto-atendimento para funcionário para solicitações de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="ab53c-107">Employee self service settings for leave and absence requests</span></span>
- <span data-ttu-id="ab53c-108">Parâmetros de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="ab53c-108">Leave and absence parameters</span></span>

## <a name="view-and-change-human-resources-parameters"></a><span data-ttu-id="ab53c-109">Exibir e alterar parâmetros de recursos humanos</span><span class="sxs-lookup"><span data-stu-id="ab53c-109">View and change human resources parameters</span></span>

1. <span data-ttu-id="ab53c-110">Na página **Licença e ausência**, selecione a guia **Links**.</span><span class="sxs-lookup"><span data-stu-id="ab53c-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="ab53c-111">Em **Configuração**, selecione **Parâmetros de recursos humanos**.</span><span class="sxs-lookup"><span data-stu-id="ab53c-111">Under **Setup**, select **Human resources parameters**.</span></span>

3. <span data-ttu-id="ab53c-112">Na guia **Sequências numéricas**, verifique o **Código de sequência numérica** para **ID de solicitação de licença** e faça as alterações necessárias.</span><span class="sxs-lookup"><span data-stu-id="ab53c-112">On the **Number sequences** tab, verify the **Number sequence code** for **Leave request ID** and change as necessary.</span></span> <span data-ttu-id="ab53c-113">Esta configuração determina a sequência usada para atribuir automaticamente IDs a solicitações de licença.</span><span class="sxs-lookup"><span data-stu-id="ab53c-113">This setting determines the sequence used for automatically assigning IDs to leave requests.</span></span>

4. <span data-ttu-id="ab53c-114">Na guia **FMLA**, verifique as configurações de FMLA e altere conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="ab53c-114">On the **FMLA** tab, verify the FMLA settings and change as necessary.</span></span>

5. <span data-ttu-id="ab53c-115">Na guia **Autoatendimento para funcionários**, indique se os gerentes podem inserir solicitações de licença e ausência em nome de seus funcionários.</span><span class="sxs-lookup"><span data-stu-id="ab53c-115">On the **Employee self service** tab, indicate whether managers can enter leave and absence requests on behalf of their employees.</span></span>

6. <span data-ttu-id="ab53c-116">Na guia **Licença e ausência**, verifique as configurações e altere conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="ab53c-116">On the **Leave and absence** tab, verify the settings and change as necessary.</span></span>

7. <span data-ttu-id="ab53c-117">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ab53c-117">Select **Save**.</span></span>

## <a name="view-and-change-leave-and-absence-parameters"></a><span data-ttu-id="ab53c-118">Exibir e alterar parâmetros de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="ab53c-118">View and change leave and absence parameters</span></span>

1. <span data-ttu-id="ab53c-119">Na página **Licença e ausência**, selecione a guia **Links**.</span><span class="sxs-lookup"><span data-stu-id="ab53c-119">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="ab53c-120">Em **Configuração**, selecione **Parâmetros de licença e ausência**.</span><span class="sxs-lookup"><span data-stu-id="ab53c-120">Under **Setup**, select **Leave and absence parameters**.</span></span>

3. <span data-ttu-id="ab53c-121">Na guia **Geral**, defina os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="ab53c-121">On the **General** tab, set the following parameters:</span></span>
 
    - <span data-ttu-id="ab53c-122">Defina a **Unidade para licença e ausência** em horas ou dias.</span><span class="sxs-lookup"><span data-stu-id="ab53c-122">Set **Unit for leave and absence** to either hours or days.</span></span> <span data-ttu-id="ab53c-123">Em caso de dias, você pode selecionar **Habilitar definição de meio dia** para permitir que os funcionários escolham a primeira ou a segunda metade do dia em suas solicitações de tempo limite.</span><span class="sxs-lookup"><span data-stu-id="ab53c-123">If days, you can select **Enable half day definition** to allow employees to choose either first or second half of day in their time-off requests.</span></span> 

    - <span data-ttu-id="ab53c-124">Selecione **Meses de data de efetivação do serviço** para definir quando as taxas de acumulação entram em vigor para os planos de licença usando meses de serviço.</span><span class="sxs-lookup"><span data-stu-id="ab53c-124">Select **Months of service effective date** to set when the accrual rates take effect for leave plans using months of service.</span></span>

    - <span data-ttu-id="ab53c-125">Selecione **Cálculo de saldo** para exibir saldos a serem exibidos a partir de hoje ou a partir do período de acumulação.</span><span class="sxs-lookup"><span data-stu-id="ab53c-125">Select **Balance calculation** to display balances display as of today or as of the accrual period.</span></span> <span data-ttu-id="ab53c-126">Se você selecionar **Saldo a partir de hoje**, o saldo exibirá o total de todas as competências, ajustes e solicitações a partir de hoje.</span><span class="sxs-lookup"><span data-stu-id="ab53c-126">If you select **Balance as of today**, the balance displays the total of all accruals, adjustments, and requests as of today.</span></span> <span data-ttu-id="ab53c-127">Se você selecionar **Saldo como período de acumulação**, o saldo exibirá o total de todas as competências, ajustes e solicitações, a partir do período de acumulação definido pela frequência no plano de licença.</span><span class="sxs-lookup"><span data-stu-id="ab53c-127">If you select **Balance as of accrual period**, the balance displays the total of all accruals, adjustments, and requests as of the accrual period defined by the frequency in the leave plan.</span></span> 

## <a name="configure-calendar-parameters"></a><span data-ttu-id="ab53c-128">Configure parâmetros de calendário.</span><span class="sxs-lookup"><span data-stu-id="ab53c-128">Configure calendar parameters</span></span>

1. <span data-ttu-id="ab53c-129">Na página **Licença e ausência**, selecione a guia **Links**.</span><span class="sxs-lookup"><span data-stu-id="ab53c-129">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="ab53c-130">Em **Configuração**, selecione **Parâmetros de licença e ausência**.</span><span class="sxs-lookup"><span data-stu-id="ab53c-130">Under **Setup**, select **Leave and absence parameters**.</span></span>

3. <span data-ttu-id="ab53c-131">Na guia **Calendário**, altere as configurações de calendário, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="ab53c-131">On the **Calendar** tab, change calendar settings as necessary.</span></span>

4. <span data-ttu-id="ab53c-132">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ab53c-132">Select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="ab53c-133">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ab53c-133">See also</span></span>

- [<span data-ttu-id="ab53c-134">Visão geral de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="ab53c-134">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)

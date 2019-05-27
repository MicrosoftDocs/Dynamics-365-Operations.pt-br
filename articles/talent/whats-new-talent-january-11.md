---
title: Novidades ou alterações no Dynamics 365 for Talent Core HR (11 de janeiro de 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 01/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-01-11
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e6a89ba455acbed9724da6826ac4d41c6a481490
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1517304"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-january-11-2019"></a><span data-ttu-id="68e30-103">Novidades ou alterações no Dynamics 365 for Talent Core HR (11 de janeiro de 2019)</span><span class="sxs-lookup"><span data-stu-id="68e30-103">What's new or changed in Dynamics 365 for Talent Core HR (January 11, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="68e30-104">**Compilação 8.1.2100**</span><span class="sxs-lookup"><span data-stu-id="68e30-104">**Build 8.1.2100**</span></span>

<span data-ttu-id="68e30-105">Este tópico descreve os recursos novos ou alterados no Core HR.</span><span class="sxs-lookup"><span data-stu-id="68e30-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="changes"></a><span data-ttu-id="68e30-106">Alterações</span><span class="sxs-lookup"><span data-stu-id="68e30-106">Changes</span></span>

### <a name="validate-leave-requests-by-forecasting-available-balance"></a><span data-ttu-id="68e30-107">Valide solicitações de licença prevendo o saldo disponível</span><span class="sxs-lookup"><span data-stu-id="68e30-107">Validate leave requests by forecasting available balance</span></span>
<span data-ttu-id="68e30-108">As alterações feitas nesta versão permitem que o funcionário solicite licenças futuras sem subtrair de seu respectivo saldo atual.</span><span class="sxs-lookup"><span data-stu-id="68e30-108">Changes made in this release allow employees to request future leave time without subtracting from their current balance.</span></span> <span data-ttu-id="68e30-109">Os fluxos de trabalho padrão serão usados para todas as solicitações futuras.</span><span class="sxs-lookup"><span data-stu-id="68e30-109">Standard workflows will be used for any future requests made.</span></span> <span data-ttu-id="68e30-110">Para obter mais informações, leia [Acumular folga com base nas horas trabalhadas](leave-accrue-hours-worked.md).</span><span class="sxs-lookup"><span data-stu-id="68e30-110">For more information, read [Accrue time off based on hours worked](leave-accrue-hours-worked.md).</span></span>

### <a name="view-forecasted-leave-balance-in-ess-and-people"></a><span data-ttu-id="68e30-111">Exibir o saldo de licença previsto em ESS e Pessoas</span><span class="sxs-lookup"><span data-stu-id="68e30-111">View forecasted leave balance in ESS and People</span></span>
<span data-ttu-id="68e30-112">Este recurso habilita a exibição dos saldos para períodos futuros de licença pelo RH, gerentes e funcionários.</span><span class="sxs-lookup"><span data-stu-id="68e30-112">This feature enables viewing of balances for future leave periods by HR, managers, and employees.</span></span> <span data-ttu-id="68e30-113">Os funcionários podem exibir os saldos futuros no espaço de trabalho **Autoatendimento para funcionários** e o RH tem acesso às mesmas informações usando o espaço trabalho **Pessoas** .</span><span class="sxs-lookup"><span data-stu-id="68e30-113">Employees can view future balances in the **Employee Self-Service** workspace and HR has access to the same information using the **People** workspace.</span></span>

### <a name="notifications-for-changing-leave-balances"></a><span data-ttu-id="68e30-114">Notificações para alterar saldos da licença</span><span class="sxs-lookup"><span data-stu-id="68e30-114">Notifications for changing leave balances</span></span>
<span data-ttu-id="68e30-115">Os saldos de licença exibirão o saldo atual dos funcionários.</span><span class="sxs-lookup"><span data-stu-id="68e30-115">Leave balances will display the employees current balance.</span></span> <span data-ttu-id="68e30-116">Os saldos futuros estão disponíveis nos espaços de trabalho **Autoatendimento para funcionários** e **Pessoas** inserindo uma "data de início" para calcular o saldo previsto.</span><span class="sxs-lookup"><span data-stu-id="68e30-116">Future balances are available on the **Employee Self-Service** and **People** workspaces by entering an “as of date” to calculate the forecasted balance.</span></span>

<span data-ttu-id="68e30-117">Foi adicionada navegação para exibir os saldos previstos nas seguintes áreas:</span><span class="sxs-lookup"><span data-stu-id="68e30-117">Navigation has been added to view forecasted balances in the following areas:</span></span>
  - <span data-ttu-id="68e30-118">Cartão **Folga** no espaço de trabalho **Autoatendimento para funcionários** .</span><span class="sxs-lookup"><span data-stu-id="68e30-118">**Time off** card on the **Employee Self-Service** workspace.</span></span>
  - <span data-ttu-id="68e30-119">Cartão **Licença e ausência** no espaço de trabalho **Autoatendimento para gerentes** .</span><span class="sxs-lookup"><span data-stu-id="68e30-119">**Leave and absence** card on the **Manager Self-Service** workspace.</span></span>
  - <span data-ttu-id="68e30-120">Página**Licença e ausência** no espaço de trabalho **Pessoas** .</span><span class="sxs-lookup"><span data-stu-id="68e30-120">**Leave and absence** page on the **People** workspace.</span></span>

### <a name="allow-decimals-for-variable-compensation-plans-cash-plans"></a><span data-ttu-id="68e30-121">Permita decimais nos Planos de remuneração variável (planos de caixa)</span><span class="sxs-lookup"><span data-stu-id="68e30-121">Allow decimals for Variable compensation plans (Cash plans)</span></span>
<span data-ttu-id="68e30-122">Os prêmios e planos variáveis em dinheiro têm agora flexibilidade adicional para montantes e substituições de montantes com valores decimais.</span><span class="sxs-lookup"><span data-stu-id="68e30-122">Variable cash awards and plans now have the additional flexibility for amounts and overrides for values with decimal amounts.</span></span>

### <a name="unable-to-change-the-dates-on-variable-comp-enrollments-after-the-plan-is-saved"></a><span data-ttu-id="68e30-123">Não é possível alterar as datas nas inscrições para remuneração variável depois que o plano é salvo</span><span class="sxs-lookup"><span data-stu-id="68e30-123">Unable to change the dates on Variable comp enrollments after the plan is saved</span></span>
<span data-ttu-id="68e30-124">Esta alteração permite que a data final do plano seja atualizada (ampliada ou expirada) depois que o plano é salvo.</span><span class="sxs-lookup"><span data-stu-id="68e30-124">This change allows for the plan end date to be updated (extended or expired) after the plan has been saved.</span></span> <span data-ttu-id="68e30-125">Você ainda pode ativar ou desativar planos independentemente das datas de início e fim.</span><span class="sxs-lookup"><span data-stu-id="68e30-125">You can still activate or de-activate plans independent of start and end dates.</span></span>

### <a name="payroll-information-available-when-assigned-the-payroll-admin-security-role"></a><span data-ttu-id="68e30-126">Informações disponíveis de folha de pagamento quando atribuídas à função de segurança Administrador de folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="68e30-126">Payroll information available when assigned the Payroll admin security role</span></span>
<span data-ttu-id="68e30-127">A função de Administrador de folha de pagamento foi atualizada para ter acesso a informações de folha de pagamento durante o processo de solicitação.</span><span class="sxs-lookup"><span data-stu-id="68e30-127">The Payroll Administrator role has been updated to have access to the payroll information during the request process.</span></span>

### <a name="employee-self-service--position-hierarchy-drill-down-from-tile-fails-to-get-parent-node"></a><span data-ttu-id="68e30-128">Autoatendimento para funcionários | Falha na obtenção do nó pai na busca detalhada de hierarquia de posições a partir do bloco</span><span class="sxs-lookup"><span data-stu-id="68e30-128">Employee self-service | Position hierarchy drill-down from tile fails to get parent node</span></span>
<span data-ttu-id="68e30-129">As alterações foram feitas para eliminar um erro que ocorreu na adição da hierarquia de posições a novos espaços de trabalho e na navegação na estrutura da organização.</span><span class="sxs-lookup"><span data-stu-id="68e30-129">Changes have been made to eliminate an error that occurred when adding the position hierarchy to new workspaces and navigating within the organizational structure.</span></span>

### <a name="new-validation-message-when-personnel-number-sequence-is-in-use"></a><span data-ttu-id="68e30-130">Nova mensagem de validação quando a sequência numérica de pessoal está em uso</span><span class="sxs-lookup"><span data-stu-id="68e30-130">New validation message when personnel number sequence is in use</span></span>
<span data-ttu-id="68e30-131">Uma alteração foi feita para explicar qual o problema quando você contrata um funcionário e o número de pessoal está em uso.</span><span class="sxs-lookup"><span data-stu-id="68e30-131">A change has been made to clarify what the issue is when you hire an employee and the next personnel number is in use.</span></span>

### <a name="employee-self-service-workspace-selected-as-the-initial-startup-page"></a><span data-ttu-id="68e30-132">Espaço de trabalho de autoatendimento para funcionários selecionado como a página inicial</span><span class="sxs-lookup"><span data-stu-id="68e30-132">Employee self-service workspace selected as the initial startup page</span></span>
<span data-ttu-id="68e30-133">Quando o espaço de trabalho **Autoatendimento para funcionários** é selecionado como a página inicial de um usuário que não está atribuído à função funcionário, o sistema redireciona para o painel padrão.</span><span class="sxs-lookup"><span data-stu-id="68e30-133">When the **Employee self-service** workspace is selected as the initial startup page for a user and that user is not assigned the employee role, the system will redirect to the default dashboard.</span></span>

### <a name="termination-reason-code-updates-position-assignment-record"></a><span data-ttu-id="68e30-134">O código de motivo da demissão atualiza o registro de atribuição de posição</span><span class="sxs-lookup"><span data-stu-id="68e30-134">Termination reason code updates position assignment record</span></span>
<span data-ttu-id="68e30-135">O código de motivo da demissão atualizará agora a atribuição de posição ao demitir um funcionário e ao encerrar a posição.</span><span class="sxs-lookup"><span data-stu-id="68e30-135">The termination reason code will now update the position assignment when terminating an employee and ending the position.</span></span> 

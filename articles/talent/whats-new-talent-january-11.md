---
title: Novidades ou alterações no Dynamics 365 Talent - Core HR (11 de janeiro de 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent - Core HR.
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
ms.openlocfilehash: 4bf106507800f53be80af1733667bfec3023b56f
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/03/2019
ms.locfileid: "2551826"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-january-11-2019"></a><span data-ttu-id="bb262-103">Novidades ou alterações no Dynamics 365 Talent - Core HR (11 de janeiro de 2019)</span><span class="sxs-lookup"><span data-stu-id="bb262-103">What's new or changed in Dynamics 365 Talent - Core HR (January 11, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="bb262-104">**Compilação 8.1.2100**</span><span class="sxs-lookup"><span data-stu-id="bb262-104">**Build 8.1.2100**</span></span>

<span data-ttu-id="bb262-105">Este tópico descreve os recursos novos ou alterados no Core HR.</span><span class="sxs-lookup"><span data-stu-id="bb262-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="changes"></a><span data-ttu-id="bb262-106">Alterações</span><span class="sxs-lookup"><span data-stu-id="bb262-106">Changes</span></span>

### <a name="validate-leave-requests-by-forecasting-available-balance"></a><span data-ttu-id="bb262-107">Valide solicitações de licença prevendo o saldo disponível</span><span class="sxs-lookup"><span data-stu-id="bb262-107">Validate leave requests by forecasting available balance</span></span>
<span data-ttu-id="bb262-108">As alterações feitas nesta versão permitem que o funcionário solicite licenças futuras sem subtrair de seu respectivo saldo atual.</span><span class="sxs-lookup"><span data-stu-id="bb262-108">Changes made in this release allow employees to request future leave time without subtracting from their current balance.</span></span> <span data-ttu-id="bb262-109">Os fluxos de trabalho padrão serão usados para todas as solicitações futuras.</span><span class="sxs-lookup"><span data-stu-id="bb262-109">Standard workflows will be used for any future requests made.</span></span> <span data-ttu-id="bb262-110">Para obter mais informações, leia [Acumular folga com base nas horas trabalhadas](leave-accrue-hours-worked.md).</span><span class="sxs-lookup"><span data-stu-id="bb262-110">For more information, read [Accrue time off based on hours worked](leave-accrue-hours-worked.md).</span></span>

### <a name="view-forecasted-leave-balance-in-ess-and-people"></a><span data-ttu-id="bb262-111">Exibir o saldo de licença previsto em ESS e Pessoas</span><span class="sxs-lookup"><span data-stu-id="bb262-111">View forecasted leave balance in ESS and People</span></span>
<span data-ttu-id="bb262-112">Este recurso habilita a exibição dos saldos para períodos futuros de licença pelo RH, gerentes e funcionários.</span><span class="sxs-lookup"><span data-stu-id="bb262-112">This feature enables viewing of balances for future leave periods by HR, managers, and employees.</span></span> <span data-ttu-id="bb262-113">Os funcionários podem exibir os saldos futuros no espaço de trabalho **Autoatendimento para funcionários** e o RH tem acesso às mesmas informações usando o espaço trabalho **Pessoas** .</span><span class="sxs-lookup"><span data-stu-id="bb262-113">Employees can view future balances in the **Employee Self-Service** workspace and HR has access to the same information using the **People** workspace.</span></span>

### <a name="notifications-for-changing-leave-balances"></a><span data-ttu-id="bb262-114">Notificações para alterar saldos da licença</span><span class="sxs-lookup"><span data-stu-id="bb262-114">Notifications for changing leave balances</span></span>
<span data-ttu-id="bb262-115">Os saldos de licença exibirão o saldo atual dos funcionários.</span><span class="sxs-lookup"><span data-stu-id="bb262-115">Leave balances will display the employees current balance.</span></span> <span data-ttu-id="bb262-116">Os saldos futuros estão disponíveis nos espaços de trabalho **Autoatendimento para funcionários** e **Pessoas** inserindo uma "data de início" para calcular o saldo previsto.</span><span class="sxs-lookup"><span data-stu-id="bb262-116">Future balances are available on the **Employee Self-Service** and **People** workspaces by entering an “as of date” to calculate the forecasted balance.</span></span>

<span data-ttu-id="bb262-117">Foi adicionada navegação para exibir os saldos previstos nas seguintes áreas:</span><span class="sxs-lookup"><span data-stu-id="bb262-117">Navigation has been added to view forecasted balances in the following areas:</span></span>
  - <span data-ttu-id="bb262-118">Cartão **Folga** no espaço de trabalho **Autoatendimento para funcionários** .</span><span class="sxs-lookup"><span data-stu-id="bb262-118">**Time off** card on the **Employee Self-Service** workspace.</span></span>
  - <span data-ttu-id="bb262-119">Cartão **Licença e ausência** no espaço de trabalho **Autoatendimento para gerentes** .</span><span class="sxs-lookup"><span data-stu-id="bb262-119">**Leave and absence** card on the **Manager Self-Service** workspace.</span></span>
  - <span data-ttu-id="bb262-120">Página**Licença e ausência** no espaço de trabalho **Pessoas** .</span><span class="sxs-lookup"><span data-stu-id="bb262-120">**Leave and absence** page on the **People** workspace.</span></span>

### <a name="allow-decimals-for-variable-compensation-plans-cash-plans"></a><span data-ttu-id="bb262-121">Permita decimais nos Planos de remuneração variável (planos de caixa)</span><span class="sxs-lookup"><span data-stu-id="bb262-121">Allow decimals for Variable compensation plans (Cash plans)</span></span>
<span data-ttu-id="bb262-122">Os prêmios e planos variáveis em dinheiro têm agora flexibilidade adicional para montantes e substituições de montantes com valores decimais.</span><span class="sxs-lookup"><span data-stu-id="bb262-122">Variable cash awards and plans now have the additional flexibility for amounts and overrides for values with decimal amounts.</span></span>

### <a name="unable-to-change-the-dates-on-variable-comp-enrollments-after-the-plan-is-saved"></a><span data-ttu-id="bb262-123">Não é possível alterar as datas nas inscrições para remuneração variável depois que o plano é salvo</span><span class="sxs-lookup"><span data-stu-id="bb262-123">Unable to change the dates on Variable comp enrollments after the plan is saved</span></span>
<span data-ttu-id="bb262-124">Esta alteração permite que a data final do plano seja atualizada (ampliada ou expirada) depois que o plano é salvo.</span><span class="sxs-lookup"><span data-stu-id="bb262-124">This change allows for the plan end date to be updated (extended or expired) after the plan has been saved.</span></span> <span data-ttu-id="bb262-125">Você ainda pode ativar ou desativar planos independentemente das datas de início e fim.</span><span class="sxs-lookup"><span data-stu-id="bb262-125">You can still activate or de-activate plans independent of start and end dates.</span></span>

### <a name="payroll-information-available-when-assigned-the-payroll-admin-security-role"></a><span data-ttu-id="bb262-126">Informações disponíveis de folha de pagamento quando atribuídas à função de segurança Administrador de folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="bb262-126">Payroll information available when assigned the Payroll admin security role</span></span>
<span data-ttu-id="bb262-127">A função de Administrador de folha de pagamento foi atualizada para ter acesso a informações de folha de pagamento durante o processo de solicitação.</span><span class="sxs-lookup"><span data-stu-id="bb262-127">The Payroll Administrator role has been updated to have access to the payroll information during the request process.</span></span>

### <a name="employee-self-service--position-hierarchy-drill-down-from-tile-fails-to-get-parent-node"></a><span data-ttu-id="bb262-128">Autoatendimento para funcionários | Falha na obtenção do nó pai na busca detalhada de hierarquia de posições a partir do bloco</span><span class="sxs-lookup"><span data-stu-id="bb262-128">Employee self-service | Position hierarchy drill-down from tile fails to get parent node</span></span>
<span data-ttu-id="bb262-129">As alterações foram feitas para eliminar um erro que ocorreu na adição da hierarquia de posições a novos espaços de trabalho e na navegação na estrutura da organização.</span><span class="sxs-lookup"><span data-stu-id="bb262-129">Changes have been made to eliminate an error that occurred when adding the position hierarchy to new workspaces and navigating within the organizational structure.</span></span>

### <a name="new-validation-message-when-personnel-number-sequence-is-in-use"></a><span data-ttu-id="bb262-130">Nova mensagem de validação quando a sequência numérica de pessoal está em uso</span><span class="sxs-lookup"><span data-stu-id="bb262-130">New validation message when personnel number sequence is in use</span></span>
<span data-ttu-id="bb262-131">Uma alteração foi feita para explicar qual o problema quando você contrata um funcionário e o número de pessoal está em uso.</span><span class="sxs-lookup"><span data-stu-id="bb262-131">A change has been made to clarify what the issue is when you hire an employee and the next personnel number is in use.</span></span>

### <a name="employee-self-service-workspace-selected-as-the-initial-startup-page"></a><span data-ttu-id="bb262-132">Espaço de trabalho de autoatendimento para funcionários selecionado como a página inicial</span><span class="sxs-lookup"><span data-stu-id="bb262-132">Employee self-service workspace selected as the initial startup page</span></span>
<span data-ttu-id="bb262-133">Quando o espaço de trabalho **Autoatendimento para funcionários** é selecionado como a página inicial de um usuário que não está atribuído à função funcionário, o sistema redireciona para o painel padrão.</span><span class="sxs-lookup"><span data-stu-id="bb262-133">When the **Employee self-service** workspace is selected as the initial startup page for a user and that user is not assigned the employee role, the system will redirect to the default dashboard.</span></span>

### <a name="termination-reason-code-updates-position-assignment-record"></a><span data-ttu-id="bb262-134">O código de motivo da demissão atualiza o registro de atribuição de posição</span><span class="sxs-lookup"><span data-stu-id="bb262-134">Termination reason code updates position assignment record</span></span>
<span data-ttu-id="bb262-135">O código de motivo da demissão atualizará agora a atribuição de posição ao demitir um funcionário e ao encerrar a posição.</span><span class="sxs-lookup"><span data-stu-id="bb262-135">The termination reason code will now update the position assignment when terminating an employee and ending the position.</span></span> 

---
title: Novidades ou alterações no Dynamics 365 Talent (31 de janeiro de 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent.
author: andreabichsel
manager: AnnBe
ms.date: 01/31/2019
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
ms.author: anbichse
ms.search.validFrom: 2019-01-29
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 8e8c11e460a4678efea81f8d3d1eec96b673d329
ms.sourcegitcommit: 53174ed4e7cc4e1ba07cdfc39207e7296ef87c1f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/07/2020
ms.locfileid: "4690043"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-january-31-2019"></a><span data-ttu-id="90287-103">Novidades ou alterações no Dynamics 365 Talent (31 de janeiro de 2019)</span><span class="sxs-lookup"><span data-stu-id="90287-103">What's new or changed in Dynamics 365 Talent (January 31, 2019)</span></span>

<span data-ttu-id="90287-104">Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="90287-104">This topic describes features that are either new or changed in Dynamics 365 Talent.</span></span>

<span data-ttu-id="90287-105">**Compilação 8.1.2128**</span><span class="sxs-lookup"><span data-stu-id="90287-105">**Build 8.1.2128**</span></span>

## <a name="core-hr-changes"></a><span data-ttu-id="90287-106">Alterações no Core HR</span><span class="sxs-lookup"><span data-stu-id="90287-106">Core HR Changes</span></span>

### <a name="time-off-taken-on-leave-people-card-doesnt-consider-leave-plan-dates"></a><span data-ttu-id="90287-107">A folga tirada no cartão pessoal de licença não considera as datas do plano de licença</span><span class="sxs-lookup"><span data-stu-id="90287-107">Time off taken on leave people card doesn't consider leave plan dates</span></span>
<span data-ttu-id="90287-108">Para os planos de licença que não são executados em um ano civil, o cartão **Tirado** agora exibe as folgas que foram tiradas no ano de licença defino no plano.</span><span class="sxs-lookup"><span data-stu-id="90287-108">For leave plans that don’t run on a calendar year, the **Taken** card now displays time off that’s been taken in the plan-defined leave year.</span></span> <span data-ttu-id="90287-109">Por exemplo, se o ano de licença de uma organização vai de 1º de junho a 30 de maio e um funcionário tirou três dias de folga em dezembro, o cartão **Tirado** em 15 de janeiro exibirá 3 dias.</span><span class="sxs-lookup"><span data-stu-id="90287-109">For example, if an organization’s leave year is June 1 through May 30 and an employee has taken three days off in December, the **Taken** card on January 15, will display 3 days.</span></span> 

### <a name="accrual-amounts-not-matching-tier-date-basis"></a><span data-ttu-id="90287-110">Os valores acumulados não está correspondendo à base de datas da camada</span><span class="sxs-lookup"><span data-stu-id="90287-110">Accrual amounts not matching tier date basis</span></span>
<span data-ttu-id="90287-111">Novas opções foram adicionadas à licença e ausência (parâmetros **Recursos Humanos**) para permitir que clientes determinem quais meses da data de serviço dos funcionários são efetivos.</span><span class="sxs-lookup"><span data-stu-id="90287-111">New options have been added to leave and absence (**Human resources** parameters) to enable customers to determine when employees’ months of service date are effective.</span></span> <span data-ttu-id="90287-112">Para algumas organizações, a data é o final do mês, mas para outras ela pode ser o início do próximo mês.</span><span class="sxs-lookup"><span data-stu-id="90287-112">For some organizations, the date is the end of the month, but for others it may be the start of the next month.</span></span> <span data-ttu-id="90287-113">Por exemplo, uma organização pode conceder folga em 31 de dezembro, enquanto outra pode conceder folga em 1º de janeiro.</span><span class="sxs-lookup"><span data-stu-id="90287-113">For example, one organization may award time off on December 31, while another may award time off on January 1.</span></span> <span data-ttu-id="90287-114">Essa opção permitirá que você escolha quando a folga deve ser concedida.</span><span class="sxs-lookup"><span data-stu-id="90287-114">This option will allow you to choose when the award should occur.</span></span> 

### <a name="worker-hire-actions-are-stuck-in-workflow-complete-state"></a><span data-ttu-id="90287-115">As ações de contratação de trabalhadores estão com status "Fluxo de trabalho concluído"</span><span class="sxs-lookup"><span data-stu-id="90287-115">Worker hire actions are stuck in "Workflow complete" state</span></span>
<span data-ttu-id="90287-116">As alterações foram feitas para corrigir um problema em que um pequeno número de fluxos de trabalho foram concluídos com um status "Fluxo de trabalho concluído".</span><span class="sxs-lookup"><span data-stu-id="90287-116">Changes have been made to correct an issue where a small number of workflows finished with a "Workflow complete" status.</span></span> <span data-ttu-id="90287-117">Novos fluxos de trabalho deverão agora mudar para um status "Concluído" quando o fluxo de trabalho for concluído.</span><span class="sxs-lookup"><span data-stu-id="90287-117">New workflows should now move to a "Completed" state when the workflow finishes.</span></span> <span data-ttu-id="90287-118">Os fluxos de trabalho com um status concluído serão modificados para um status de erro para permitir a atualização ou remoção se necessário.</span><span class="sxs-lookup"><span data-stu-id="90287-118">Any workflows in a workflow completed status will be transitioned to an error status to allow for updating or removal if required.</span></span> 

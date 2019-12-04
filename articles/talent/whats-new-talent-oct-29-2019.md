---
title: Novidades ou alterações no Dynamics 365 Talent (29 de outubro de 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 10/29/2019
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
ms.search.validFrom: 2019-10-29
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 83b4734190163ebd2dc29096632642bd45c61e8f
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773868"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-october-29-2019"></a><span data-ttu-id="6ccfb-103">Novidades ou alterações no Dynamics 365 Talent (29 de outubro de 2019)</span><span class="sxs-lookup"><span data-stu-id="6ccfb-103">What's new or changed in Dynamics 365 Talent (October 29, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="6ccfb-104">Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="6ccfb-104">This topic describes features that are either new or changed in Dynamics 365 Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="6ccfb-105">Alterações no Attract</span><span class="sxs-lookup"><span data-stu-id="6ccfb-105">Changes in Attract</span></span>

<span data-ttu-id="6ccfb-106">Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="6ccfb-106">This release includes minor bug fixes for Dynamics 365 Talent: Attract.</span></span>

## <a name="changes-in-onboard"></a><span data-ttu-id="6ccfb-107">Alterações de Integração</span><span class="sxs-lookup"><span data-stu-id="6ccfb-107">Changes in Onboard</span></span>

<span data-ttu-id="6ccfb-108">Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="6ccfb-108">This release includes minor bug fixes for Dynamics 365 Talent: Onboard.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="6ccfb-109">Alterações no Core HR</span><span class="sxs-lookup"><span data-stu-id="6ccfb-109">Changes in Core HR</span></span>

<span data-ttu-id="6ccfb-110">As alterações descritas nesta seção aplicam-se ao número da compilação 8.1.2586.</span><span class="sxs-lookup"><span data-stu-id="6ccfb-110">Changes described in this section apply to build number 8.1.2586.</span></span> <span data-ttu-id="6ccfb-111">Os números em parênteses em alguns cabeçalhos referem-se aos números de suporte no Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="6ccfb-111">The numbers in parentheses in some headings refer to support numbers in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

### <a name="delete-parties-with-no-roles-should-be-on-by-default-371233"></a><span data-ttu-id="6ccfb-112">Excluir participantes sem funções deve estar ativado por padrão (371233)</span><span class="sxs-lookup"><span data-stu-id="6ccfb-112">Delete parties with no roles should be on by default (371233)</span></span>

<span data-ttu-id="6ccfb-113">Quando você provisiona um novo ambiente no Talent, **Excluir participantes se não houver funções** é ativado por padrão.</span><span class="sxs-lookup"><span data-stu-id="6ccfb-113">When you provision a new environment in Talent, **Delete parties if no roles exist** is turned on by default.</span></span> <span data-ttu-id="6ccfb-114">Quando você exclui um trabalhador, o participante associado ao trabalhador não é removido, a menos que essa configuração esteja ativada.</span><span class="sxs-lookup"><span data-stu-id="6ccfb-114">When you delete a worker, the party associated with the worker is not removed unless this setting is on.</span></span> <span data-ttu-id="6ccfb-115">Essa alteração limitará os registros duplicados no catálogo de endereços global quando você precisar importar, alterar ou reimportar trabalhadores.</span><span class="sxs-lookup"><span data-stu-id="6ccfb-115">This change limits duplicate records in the global address book when you need to import, change, or reimport workers.</span></span>

### <a name="draft-and-cancelled-leave-requests-should-be-allowed-to-be-deleted-in-common-data-service-376999"></a><span data-ttu-id="6ccfb-116">As solicitações de licença em rascunho ou canceladas devem poder ser excluídas no Common Data Service (376999)</span><span class="sxs-lookup"><span data-stu-id="6ccfb-116">Draft and cancelled leave requests should be allowed to be deleted in Common Data Service (376999)</span></span>

<span data-ttu-id="6ccfb-117">Com essa alteração, agora você pode excluir solicitações de licença com um status **Rascunho** ou **Cancelada** no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="6ccfb-117">With this change, you can now delete leave requests with a status of **Draft** or **Cancelled** in Common Data Service.</span></span>

### <a name="additional-list-values-in-custom-fields-arent-reflected-in-common-data-service-after-clicking-apply-on-the-custom-fields-form-379599"></a><span data-ttu-id="6ccfb-118">Os valores de lista adicionais em campos personalizados não são refletidos no Common Data Service após clicar em Aplicar ao formulário Campos personalizados (379599)</span><span class="sxs-lookup"><span data-stu-id="6ccfb-118">Additional list values in custom fields aren't reflected in Common Data Service after clicking Apply on the Custom fields form (379599)</span></span>

<span data-ttu-id="6ccfb-119">Quando você adicionar novos valores de lista a um campo personalizado existente que já foi sincronizado com o Common Data Service, agora eles estão disponíveis no Common Data Service depois que você aplicar as alterações ao formulário **Campos personalizados**.</span><span class="sxs-lookup"><span data-stu-id="6ccfb-119">When you add new list values to an existing custom field that has already synchronized with Common Data Service, they're now available in Common Data Serivce after you apply your changes in the **Custom fields** form.</span></span>

### <a name="apply-onboarding-checklists-across-legal-entities-when-more-than-one-employment-exists-371270"></a><span data-ttu-id="6ccfb-120">Aplicar listas de verificação de integração em entidades legais quando houver mais de um emprego (371270)</span><span class="sxs-lookup"><span data-stu-id="6ccfb-120">Apply onboarding checklists across legal entities when more than one employment exists (371270)</span></span>

<span data-ttu-id="6ccfb-121">Na versão desta semana, é possível aplicar listas de verificação a funcionários com mais de um emprego em **formulário Trabalhador > Listas de verificação**.</span><span class="sxs-lookup"><span data-stu-id="6ccfb-121">In this week's release, you can apply checklists to employees with more than one employment in **Worker form > Checklists**.</span></span>

### <a name="benefits-open-enrollment-preview-feature-has-been-removed"></a><span data-ttu-id="6ccfb-122">A versão prévia do recurso de inscrição aberta de benefícios foi removida</span><span class="sxs-lookup"><span data-stu-id="6ccfb-122">Benefits open enrollment preview feature has been removed</span></span>

<span data-ttu-id="6ccfb-123">Junto com o comunicado na postagem do blog [Investimentos estratégicos em Core HR levam à excelência operacional](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/10/02/strategic-investments-in-core-hr-drive-operational-excellence), a Microsoft removeu o recurso de inscrição aberta de benefícios da versão prévia pública.</span><span class="sxs-lookup"><span data-stu-id="6ccfb-123">In conjunction with our announcement in the [Strategic investments in core HR drive operational excellence](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/10/02/strategic-investments-in-core-hr-drive-operational-excellence) blog post, Microsoft has removed the benefits open enrollment feature from public preview.</span></span> <span data-ttu-id="6ccfb-124">Uma nova funcionalidade será lançada no futuro.</span><span class="sxs-lookup"><span data-stu-id="6ccfb-124">New functionality will be released in the future.</span></span> <span data-ttu-id="6ccfb-125">O uso em produção do recurso de inscrição aberta de benefícios não tem suporte.</span><span class="sxs-lookup"><span data-stu-id="6ccfb-125">Production use of the benefits open enrollment feature isn't be supported.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="6ccfb-126">Em breve</span><span class="sxs-lookup"><span data-stu-id="6ccfb-126">Coming soon</span></span>

### <a name="print-performance-reviews"></a><span data-ttu-id="6ccfb-127">Imprima avaliações de desempenho</span><span class="sxs-lookup"><span data-stu-id="6ccfb-127">Print performance reviews</span></span>

<span data-ttu-id="6ccfb-128">Consulte [Revisões de desempenho de impressão](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) no plano da onda 2 da versão 2019 do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="6ccfb-128">See [Print performance reviews](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) in the Dynamics 365: 2019 release wave 2 plan.</span></span>

### <a name="feature-management-workspace"></a><span data-ttu-id="6ccfb-129">Espaço de trabalho do gerenciamento de recursos</span><span class="sxs-lookup"><span data-stu-id="6ccfb-129">Feature management workspace</span></span>

<span data-ttu-id="6ccfb-130">Os recursos são adicionados e atualizados em cada versão.</span><span class="sxs-lookup"><span data-stu-id="6ccfb-130">Features are added and updated in every release.</span></span> <span data-ttu-id="6ccfb-131">A experiência de gerenciamento de recursos fornece um espaço de trabalho no qual você pode exibir uma lista dos recursos que foram entregues em cada versão.</span><span class="sxs-lookup"><span data-stu-id="6ccfb-131">The feature management experience provides a workspace where you can view a list of features that have been delivered in each release.</span></span> <span data-ttu-id="6ccfb-132">Por padrão, os novos recurso estão desativados.</span><span class="sxs-lookup"><span data-stu-id="6ccfb-132">By default, new features are turned off.</span></span> <span data-ttu-id="6ccfb-133">Você pode usar o espaço de trabalho para ativá-los e exibir a documentação deles.</span><span class="sxs-lookup"><span data-stu-id="6ccfb-133">You can use the workspace to turn them on and view the documentation for them.</span></span>

<span data-ttu-id="6ccfb-134">Para saber mais sobre as mudanças que acompanham o gerenciamento de recursos, consulte [Visão geral do gerenciamento de recursos](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview)</span><span class="sxs-lookup"><span data-stu-id="6ccfb-134">To learn more about the changes coming with feature management, see [Feature management overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).</span></span>

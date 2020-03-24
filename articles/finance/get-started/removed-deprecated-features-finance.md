---
title: Recursos removidos ou obsoletos do Dynamics 365 Finance
description: Este tópico descreve os recursos que já foram removidos ou foram planejados para remoção de Dynamics 365 Finance.
author: roschlom
manager: AnnBe
ms.date: 03/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2020-03-02
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: ec13076e6a05c3402af566487f7921f6971da215
ms.sourcegitcommit: 1e7e7c4bc197b0a42e4d53d2a54600a2fb125b69
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/13/2020
ms.locfileid: "3127968"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-finance"></a><span data-ttu-id="aa7cc-103">Recursos removidos ou obsoletos do Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="aa7cc-103">Removed or deprecated features in Dynamics 365 Finance</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="aa7cc-104">Este tópico descreve os recursos que já foram removidos ou foram planejados para remoção de Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="aa7cc-104">This topic describes features that have been removed, or that are planned for removal from Dynamics 365 Finance.</span></span>

- <span data-ttu-id="aa7cc-105">Um recurso *removido* não estará mais disponível no produto.</span><span class="sxs-lookup"><span data-stu-id="aa7cc-105">A *removed* feature is no longer available in the product.</span></span>
- <span data-ttu-id="aa7cc-106">Um recurso *preterido* não está no desenvolvimento ativo e poderá ser removido em uma atualização futura.</span><span class="sxs-lookup"><span data-stu-id="aa7cc-106">A *deprecated* feature is not in active development and may be removed in a future update.</span></span>

<span data-ttu-id="aa7cc-107">Esta lista é destinada a ajudá-lo a considerar essas remoções e reprovações para seu próprio planejamento.</span><span class="sxs-lookup"><span data-stu-id="aa7cc-107">This list is intended to help you consider these removals and deprecations for your own planning.</span></span> 

> [!NOTE]
> <span data-ttu-id="aa7cc-108">Informações detalhadas sobre objetos no Finance and Operations apps podem ser encontradas nos [Relatórios de referência técnica](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span><span class="sxs-lookup"><span data-stu-id="aa7cc-108">Detailed information about objects in Finance and Operations apps can be found in the [Technical reference reports](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span></span> <span data-ttu-id="aa7cc-109">Você pode comparar as diferentes versões desses relatórios para aprender sobre objetos que foram alterados ou removidos em cada versão do Finance and Operations apps.</span><span class="sxs-lookup"><span data-stu-id="aa7cc-109">You can compare the different versions of these reports to learn about objects that have changed or been removed in each version of Finance and Operations apps.</span></span>

## <a name="features-removed-or-deprecated-in-the-finance-10012-release"></a><span data-ttu-id="aa7cc-110">Recursos removidos ou substituídos na versão 10.0.12 do Finance</span><span class="sxs-lookup"><span data-stu-id="aa7cc-110">Features removed or deprecated in the Finance 10.0.12 release</span></span>

### <a name="polish-ssrs-reports-sales-vat-register-purchase-vat-register-eu-summary-vat-register--feature-reference-pl-00014"></a><span data-ttu-id="aa7cc-111">Relatórios SSRS poloneses: registro de IVA de saída, registro de IVA de entrada, registro de IVA de resumo da UE – Referência de recurso PL-00014</span><span class="sxs-lookup"><span data-stu-id="aa7cc-111">Polish SSRS reports: Sales VAT register, Purchase VAT register, EU summary VAT register – Feature reference PL-00014</span></span>

|   |  |
|------------|--------------------|
| <span data-ttu-id="aa7cc-112">**Motivo para a reprovação/remoção**</span><span class="sxs-lookup"><span data-stu-id="aa7cc-112">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="aa7cc-113">Não é legalmente obrigatório.</span><span class="sxs-lookup"><span data-stu-id="aa7cc-113">Not legally required.</span></span>  |
| <span data-ttu-id="aa7cc-114">**Substituída por outro recurso?**</span><span class="sxs-lookup"><span data-stu-id="aa7cc-114">**Replaced by another feature?**</span></span>   | <span data-ttu-id="aa7cc-115">Sim (formato do Excel para arquivo de auditoria padrão com declaração de IVA - JPK_VDEK)</span><span class="sxs-lookup"><span data-stu-id="aa7cc-115">Yes (Excel format for Standard Audit File with VAT declaration - JPK_VDEK)</span></span> |
| <span data-ttu-id="aa7cc-116">**Áreas afetadas do produto**</span><span class="sxs-lookup"><span data-stu-id="aa7cc-116">**Product areas affected**</span></span>         | <span data-ttu-id="aa7cc-117">Requerimento</span><span class="sxs-lookup"><span data-stu-id="aa7cc-117">Application</span></span> |
| <span data-ttu-id="aa7cc-118">**Opção de implantação**</span><span class="sxs-lookup"><span data-stu-id="aa7cc-118">**Deployment option**</span></span>              | <span data-ttu-id="aa7cc-119">Todas</span><span class="sxs-lookup"><span data-stu-id="aa7cc-119">All</span></span> |
| <span data-ttu-id="aa7cc-120">**Status**</span><span class="sxs-lookup"><span data-stu-id="aa7cc-120">**Status**</span></span>                         | <span data-ttu-id="aa7cc-121">Preterido: até 1º de julho de 2021, planejamos não oferecer mais suporte aos relatórios SSRS: **registro de IVA de saída, registro de IVA de entrada, registro de IVA de resumo da UE – referência de recurso PL-00014**.</span><span class="sxs-lookup"><span data-stu-id="aa7cc-121">Deprecated: By July 1, 2021, we plan to no longer support the SSRS reports: **Sales VAT register, Purchase VAT register, EU summary VAT register – Feature reference PL-00014**.</span></span> <span data-ttu-id="aa7cc-122">Em vez disso, o exemplo de formato do Excel para arquivo de auditoria padrão com declaração de IVA (JPK_VDEK) será introduzido.</span><span class="sxs-lookup"><span data-stu-id="aa7cc-122">Excel format example for Standard Audit File with VAT declaration (JPK_VDEK) will be introduced instead.</span></span> |

## <a name="features-removed-or-deprecated-in-the-finance-1007-release"></a><span data-ttu-id="aa7cc-123">Recursos removidos ou substituídos na versão 10.0.7 do Finance</span><span class="sxs-lookup"><span data-stu-id="aa7cc-123">Features removed or deprecated in the Finance 10.0.7 release</span></span>

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a><span data-ttu-id="aa7cc-124">Caixa de diálogo Alterar solicitação de fluxo de trabalho não inclui mais a seleção do usuário de lista suspensa</span><span class="sxs-lookup"><span data-stu-id="aa7cc-124">Workflow request change dialog box no longer includes user selection drop-down list</span></span>
|   |  |
|------------|--------------------|
| <span data-ttu-id="aa7cc-125">**Motivo para a reprovação/remoção**</span><span class="sxs-lookup"><span data-stu-id="aa7cc-125">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="aa7cc-126">Recurso alterado para a seleção de grupos de contas.</span><span class="sxs-lookup"><span data-stu-id="aa7cc-126">Changed to the feature with account groups selection.</span></span>  |
| <span data-ttu-id="aa7cc-127">**Substituída por outro recurso?**</span><span class="sxs-lookup"><span data-stu-id="aa7cc-127">**Replaced by another feature?**</span></span>   | <span data-ttu-id="aa7cc-128">Sim</span><span class="sxs-lookup"><span data-stu-id="aa7cc-128">Yes</span></span> |
| <span data-ttu-id="aa7cc-129">**Áreas afetadas do produto**</span><span class="sxs-lookup"><span data-stu-id="aa7cc-129">**Product areas affected**</span></span>         | <span data-ttu-id="aa7cc-130">Fluxo de Trabalho</span><span class="sxs-lookup"><span data-stu-id="aa7cc-130">Workflow</span></span> |
| <span data-ttu-id="aa7cc-131">**Opção de implantação**</span><span class="sxs-lookup"><span data-stu-id="aa7cc-131">**Deployment option**</span></span>              | <span data-ttu-id="aa7cc-132">Todas</span><span class="sxs-lookup"><span data-stu-id="aa7cc-132">All</span></span> |
| <span data-ttu-id="aa7cc-133">**Status**</span><span class="sxs-lookup"><span data-stu-id="aa7cc-133">**Status**</span></span>                         | <span data-ttu-id="aa7cc-134">Substituído: até 1º de dezembro de 2020, não planejamos mais oferecer suporte à configuração de tipos de comprovantes chineses sem a seleção de Grupos de contas.</span><span class="sxs-lookup"><span data-stu-id="aa7cc-134">Deprecated: By December 1, 2020, we plan to no longer support Chinese voucher types setup without Account groups selection.</span></span> <span data-ttu-id="aa7cc-135">Obtenha mais detalhes sobre o novo design em [Novidades no 10.0.7](whats-new-changed-10-0-7.md).</span><span class="sxs-lookup"><span data-stu-id="aa7cc-135">Find more details about the new design in [What's new in 10.0.7](whats-new-changed-10-0-7.md).</span></span> |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a><span data-ttu-id="aa7cc-136">Comunicados anteriores sobre recursos removidos ou obsoletos</span><span class="sxs-lookup"><span data-stu-id="aa7cc-136">Previous announcements about removed or deprecated features</span></span>
<span data-ttu-id="aa7cc-137">Para saber mais sobre os recursos que foram removidos ou preteridos em versões anteriores, consulte [Recursos removidos ou obsoletos em versões anteriores](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).</span><span class="sxs-lookup"><span data-stu-id="aa7cc-137">To learn more about features that have been removed or deprecated in previous releases, see [Removed or deprecated features in previous releases](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).</span></span>

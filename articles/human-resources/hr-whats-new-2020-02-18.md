---
title: Novidades ou alterações no Dynamics 365 Human Resources (18 de fevereiro de 2020)
description: Este artigo descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 18 de fevereiro de 2020.
author: andreabichsel
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-02-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 62b5890f02b6b9598ba5a87e25745fa7633df769
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6051200"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-18-2020"></a><span data-ttu-id="f80b9-103">Novidades ou alterações no Dynamics 365 Human Resources (18 de fevereiro de 2020)</span><span class="sxs-lookup"><span data-stu-id="f80b9-103">What's new or changed in Dynamics 365 Human Resources (February 18, 2020)</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="f80b9-104">Este artigo descreve os recursos novos ou alterados no Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f80b9-104">This article describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="f80b9-105">As alterações se aplicam ao número da compilação 8.1.2903.</span><span class="sxs-lookup"><span data-stu-id="f80b9-105">Changes apply to build number 8.1.2903.</span></span> <span data-ttu-id="f80b9-106">Os números entre parênteses em alguns títulos referem-se aos números de suporte do LCS para referência.</span><span class="sxs-lookup"><span data-stu-id="f80b9-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="platform-update-32"></a><span data-ttu-id="f80b9-107">Update 32 para plataforma</span><span class="sxs-lookup"><span data-stu-id="f80b9-107">Platform update 32</span></span> 

<span data-ttu-id="f80b9-108">A atualização de plataforma 32 já está disponível.</span><span class="sxs-lookup"><span data-stu-id="f80b9-108">Platform update 32 is now available.</span></span> <span data-ttu-id="f80b9-109">Para obter mais informações, consulte [Novidades ou alterações na Atualização de plataforma 32 para o Finance and Operations (fevereiro de 2020)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-update-32.md).</span><span class="sxs-lookup"><span data-stu-id="f80b9-109">For more information, see [What's new or changed in Platform update 32 for Finance and Operations (February 2020)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-update-32.md).</span></span>

## <a name="search-values-are-remembered-when-changing-view-options-in-streamlined-employee-form-383833"></a><span data-ttu-id="f80b9-110">Os valores de pesquisa são lembrados no momento da alteração das opções de exibição no formulário simplificado de funcionário (383833)</span><span class="sxs-lookup"><span data-stu-id="f80b9-110">Search values are remembered when changing view options in streamlined employee form (383833)</span></span>

<span data-ttu-id="f80b9-111">O novo formulário **Trabalhador** agora lembra os valores de pesquisa quando você altera as opções de exibição e aplica as alterações.</span><span class="sxs-lookup"><span data-stu-id="f80b9-111">The new **Worker** form now remembers  search values when you change the view options and apply changes.</span></span>

## <a name="compensation-management-summary-tiles-in-preview-feature-redirect-to-wrong-form-401861"></a><span data-ttu-id="f80b9-112">Os blocos de resumo do gerenciamento de remuneração no recurso de visualização são redirecionados para a forma incorreta (401861)</span><span class="sxs-lookup"><span data-stu-id="f80b9-112">Compensation management summary tiles in preview feature redirect to wrong form (401861)</span></span>

<span data-ttu-id="f80b9-113">Os blocos de gerenciamento de remuneração fixa e variável agora exibem os registros corretos no novo formulário **Trabalhador**.</span><span class="sxs-lookup"><span data-stu-id="f80b9-113">Fixed and variable compensation management tiles now display the correct records in the new **Worker** form.</span></span> <span data-ttu-id="f80b9-114">Aplica-se somente ao recurso de visualização do formulário simplificado de funcionário.</span><span class="sxs-lookup"><span data-stu-id="f80b9-114">Applies only to the streamlined employee form preview feature.</span></span> <span data-ttu-id="f80b9-115">É possível habilitar esse recurso de visualização em **Gerenciamento de recursos**.</span><span class="sxs-lookup"><span data-stu-id="f80b9-115">You can enable this preview feature in **Feature management**.</span></span> <span data-ttu-id="f80b9-116">Para obter mais informações, consulte [Gerenciar recursos](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="f80b9-116">For more information, see [Manage features](hr-admin-manage-features.md).</span></span>

## <a name="empty-status-field-for-some-leave-request-records-in-dataverse-414915"></a><span data-ttu-id="f80b9-117">Campo Status vazio para alguns registros de solicitação de licença no Dataverse (414915)</span><span class="sxs-lookup"><span data-stu-id="f80b9-117">Empty Status field for some leave request records in Dataverse (414915)</span></span>

<span data-ttu-id="f80b9-118">Essa alteração corrige um problema no Dataverse quando o campo **Status** em uma solicitação de licença é definido como **Revisão**.</span><span class="sxs-lookup"><span data-stu-id="f80b9-118">This change corrects an issue in Dataverse when the **Status** field in a leave request is set to **Review**.</span></span> <span data-ttu-id="f80b9-119">O Dataverse agora reflete o status.</span><span class="sxs-lookup"><span data-stu-id="f80b9-119">Dataverse now reflects the status.</span></span>

## <a name="skill-gap-analysis-only-possible-for-assigned-job-411390"></a><span data-ttu-id="f80b9-120">Análise de lacuna de habilidade só é possível para o trabalho atribuído (411390)</span><span class="sxs-lookup"><span data-stu-id="f80b9-120">Skill gap analysis only possible for assigned job (411390)</span></span>

<span data-ttu-id="f80b9-121">Agora você pode fazer uma análise de lacuna de habilidade em qualquer trabalho definido no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f80b9-121">You can now do a skill gap analysis on any job defined in Human Resources.</span></span>

## <a name="system-currency-doesnt-sync-from-dataverse-to-human-resources-in-new-environments-418011"></a><span data-ttu-id="f80b9-122">A moeda do sistema não é sincronizada do Dataverse para o Human Resources em novos ambientes (418011)</span><span class="sxs-lookup"><span data-stu-id="f80b9-122">System currency doesn't sync from Dataverse to Human Resources in new environments (418011)</span></span>

<span data-ttu-id="f80b9-123">A moeda do sistema no Dataverse agora pode ser sincronizada com o Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f80b9-123">The system currency in Dataverse can now sync to Human Resources.</span></span>

## <a name="in-preview"></a><span data-ttu-id="f80b9-124">Em visualização</span><span class="sxs-lookup"><span data-stu-id="f80b9-124">In preview</span></span>

- [<span data-ttu-id="f80b9-125">Recursos de visualização de licenças e ausências</span><span class="sxs-lookup"><span data-stu-id="f80b9-125">Leave and absence preview features</span></span>](hr-leave-and-absence-overview.md?leave-and-absence-preview-features)

- [<span data-ttu-id="f80b9-126">Recursos de visualização do gerenciamento de benefícios</span><span class="sxs-lookup"><span data-stu-id="f80b9-126">Benefits management preview features</span></span>](hr-benefits-management-overview.md)

## <a name="coming-soon"></a><span data-ttu-id="f80b9-127">Em breve</span><span class="sxs-lookup"><span data-stu-id="f80b9-127">Coming soon</span></span>

### <a name="updated-dataverse-solution"></a><span data-ttu-id="f80b9-128">Solução Dataverse atualizada</span><span class="sxs-lookup"><span data-stu-id="f80b9-128">Updated Dataverse solution</span></span>

<span data-ttu-id="f80b9-129">Uma nova solução de Dataverse estará disponível em breve com as seguintes alterações:</span><span class="sxs-lookup"><span data-stu-id="f80b9-129">A new Dataverse solution will be available soon with the following changes:</span></span>

| <span data-ttu-id="f80b9-130">Descrição</span><span class="sxs-lookup"><span data-stu-id="f80b9-130">Description</span></span> | <span data-ttu-id="f80b9-131">Troco</span><span class="sxs-lookup"><span data-stu-id="f80b9-131">Change</span></span> |
| ----------------------------------------- | --- |
| <span data-ttu-id="f80b9-132">Alterações de entidade do **Trabalho/Posição**</span><span class="sxs-lookup"><span data-stu-id="f80b9-132">**Job/Position** entity changes</span></span> | <span data-ttu-id="f80b9-133">**Região de remuneração** adicionado</span><span class="sxs-lookup"><span data-stu-id="f80b9-133">**Compensation region** added</span></span></br><span data-ttu-id="f80b9-134">**Dimensões financeiras** adicionado</span><span class="sxs-lookup"><span data-stu-id="f80b9-134">**Financial dimensions** added</span></span> |
| <span data-ttu-id="f80b9-135">Alterações de entidade do **Trabalhador**</span><span class="sxs-lookup"><span data-stu-id="f80b9-135">**Worker** entity changes</span></span> | <span data-ttu-id="f80b9-136">**Sequência do nome** adicionado</span><span class="sxs-lookup"><span data-stu-id="f80b9-136">**Name sequence** added</span></span></br><span data-ttu-id="f80b9-137">**Trabalha de casa** adicionado</span><span class="sxs-lookup"><span data-stu-id="f80b9-137">**Works from home** added</span></span></br><span data-ttu-id="f80b9-138">**Idioma** adicionado</span><span class="sxs-lookup"><span data-stu-id="f80b9-138">**Language** added</span></span></br><span data-ttu-id="f80b9-139">**Aniversário de tempo de serviço** adicionado</span><span class="sxs-lookup"><span data-stu-id="f80b9-139">**Seniority date** added</span></span></br><span data-ttu-id="f80b9-140">**Data de aniversário** adicionado</span><span class="sxs-lookup"><span data-stu-id="f80b9-140">**Anniversary date** added</span></span></br><span data-ttu-id="f80b9-141">**Data original de contratação** adicionado</span><span class="sxs-lookup"><span data-stu-id="f80b9-141">**Original hire date** added</span></span> |
| <span data-ttu-id="f80b9-142">Alterações de entidade do **Emprego**</span><span class="sxs-lookup"><span data-stu-id="f80b9-142">**Employment** entity changes</span></span> | <span data-ttu-id="f80b9-143">**Dimensões financeiras** adicionado</span><span class="sxs-lookup"><span data-stu-id="f80b9-143">**Financial dimensions** added</span></span></br><span data-ttu-id="f80b9-144">**Motivo da demissão** adicionado</span><span class="sxs-lookup"><span data-stu-id="f80b9-144">**Termination reason** added</span></span></br><span data-ttu-id="f80b9-145">**Data da demissão** renomeada de **Data de transição**</span><span class="sxs-lookup"><span data-stu-id="f80b9-145">**Termination date** renamed from **Transition date**</span></span></br><span data-ttu-id="f80b9-146">**Data de experiência** adicionado</span><span class="sxs-lookup"><span data-stu-id="f80b9-146">**Probation date** added</span></span> |
| <span data-ttu-id="f80b9-147">Alterações de entidade do **Endereço do trabalhador**</span><span class="sxs-lookup"><span data-stu-id="f80b9-147">**Worker address** entity changes</span></span> | <span data-ttu-id="f80b9-148">**Endereço** adicionado</span><span class="sxs-lookup"><span data-stu-id="f80b9-148">**Street address** added</span></span></br><span data-ttu-id="f80b9-149">**Linha de endereço 1**, **Linha de endereço 2** e **Linha de endereço 3** marcadas para depreciação</span><span class="sxs-lookup"><span data-stu-id="f80b9-149">**Address line 1**, **Address line 2**, and **Address line 3** marked for deprecation</span></span> |
| <span data-ttu-id="f80b9-150">Novas entidades de configuração de remuneração variável</span><span class="sxs-lookup"><span data-stu-id="f80b9-150">New variable compensation setup entities</span></span> | <span data-ttu-id="f80b9-151">**Tipo de plano de remuneração variável**</span><span class="sxs-lookup"><span data-stu-id="f80b9-151">**Compensation variable plan type**</span></span></br><span data-ttu-id="f80b9-152">**Plano de remuneração variável**</span><span class="sxs-lookup"><span data-stu-id="f80b9-152">**Compensation variable plan**</span></span></br><span data-ttu-id="f80b9-153">**Regras de benefício proporcional diferido**</span><span class="sxs-lookup"><span data-stu-id="f80b9-153">**Vesting rules**</span></span></br><span data-ttu-id="f80b9-154">**Nível do plano de remuneração variável**</span><span class="sxs-lookup"><span data-stu-id="f80b9-154">**Compensation variable plan level**</span></span> |
| <span data-ttu-id="f80b9-155">Nova entidade **Emprego do calendário do trabalhador**</span><span class="sxs-lookup"><span data-stu-id="f80b9-155">New **Worker calendar employment** entity</span></span> | <span data-ttu-id="f80b9-156">**Entidade do calendário de trabalho** adicionada</span><span class="sxs-lookup"><span data-stu-id="f80b9-156">**Work calendar entity** added</span></span> |
| <span data-ttu-id="f80b9-157">Nova entidade **Detalhe da posição de folha de pagamento**</span><span class="sxs-lookup"><span data-stu-id="f80b9-157">New **Payroll position detail** entity</span></span> | <span data-ttu-id="f80b9-158">**Detalhe da posição de folha de pagamento** adicionado</span><span class="sxs-lookup"><span data-stu-id="f80b9-158">**Payroll position detail** added</span></span> |
| <span data-ttu-id="f80b9-159">Nova entidade **Bloco**</span><span class="sxs-lookup"><span data-stu-id="f80b9-159">New **Title** entity</span></span> | <span data-ttu-id="f80b9-160">**Bloco** adicionado.</span><span class="sxs-lookup"><span data-stu-id="f80b9-160">**Title** added.</span></span> <span data-ttu-id="f80b9-161">A nova entidade **Título** será incluída no processo de sincronização entre Human Resources e Dataverse.</span><span class="sxs-lookup"><span data-stu-id="f80b9-161">The new **Title** entity will be included in the sync process between Human Resources and Dataverse.</span></span> <span data-ttu-id="f80b9-162">Não será inicialmente referenciada de entidades **Cargo** ou **Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="f80b9-162">It won't be initially referenced from **Job Position** or **Job** entities.</span></span> |

## <a name="see-also"></a><span data-ttu-id="f80b9-163">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f80b9-163">See also</span></span>

[<span data-ttu-id="f80b9-164">Novidades ou alterações no Human Resources</span><span class="sxs-lookup"><span data-stu-id="f80b9-164">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="f80b9-165">Visão geral da onda 2 da versão 2019 do Dynamics 365 Human Resources</span><span class="sxs-lookup"><span data-stu-id="f80b9-165">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="f80b9-166">Atualizar processo</span><span class="sxs-lookup"><span data-stu-id="f80b9-166">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="f80b9-167">Gerenciar recursos</span><span class="sxs-lookup"><span data-stu-id="f80b9-167">Manage features</span></span>](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
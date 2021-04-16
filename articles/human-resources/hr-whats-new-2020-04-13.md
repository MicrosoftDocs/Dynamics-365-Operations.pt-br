---
title: Novidades ou alterações no Dynamics 365 Human Resources (13 de abril de 2020)
description: Este artigo descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 13 de abril de 2020.
author: andreabichsel
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-04-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3b7822782fda3c20d57df96af59e18b1725e4f9f
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800180"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-13-2020"></a><span data-ttu-id="b3e38-103">Novidades ou alterações no Dynamics 365 Human Resources (13 de abril de 2020)</span><span class="sxs-lookup"><span data-stu-id="b3e38-103">What's new or changed in Dynamics 365 Human Resources (April 13, 2020)</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="b3e38-104">Este artigo descreve os recursos novos ou alterados no Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b3e38-104">This article describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="b3e38-105">As alterações se aplicam ao número da compilação 8.1.3136.</span><span class="sxs-lookup"><span data-stu-id="b3e38-105">Changes apply to build number 8.1.3136.</span></span> <span data-ttu-id="b3e38-106">Os números entre parênteses em alguns títulos referem-se aos números de suporte do LCS para referência.</span><span class="sxs-lookup"><span data-stu-id="b3e38-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="new-production-release-cadence"></a><span data-ttu-id="b3e38-107">Nova cadência de liberação da produção</span><span class="sxs-lookup"><span data-stu-id="b3e38-107">New production release cadence</span></span>

<span data-ttu-id="b3e38-108">Com o lançamento desta semana, a cadência de liberação do Human Resources passará de uma atualização semanal para uma atualização quinzenal.</span><span class="sxs-lookup"><span data-stu-id="b3e38-108">With this week's release, the release cadence for Human Resources shifts from a weekly update to a biweekly update.</span></span> <span data-ttu-id="b3e38-109">Para garantir o alinhamento com práticas de implantação segura e manter altos padrões de estabilidade e confiabilidade no serviço, o processo de implantação de atualizações de serviço em todas as regiões agora será uma distribuição de duas semanas.</span><span class="sxs-lookup"><span data-stu-id="b3e38-109">To ensure alignment with safe deployment practices, and maintain high standards of stability and reliability in the service, the process of deploying service updates to all regions is now a two-week rollout.</span></span> <span data-ttu-id="b3e38-110">Testes e monitores adicionais serão feitos para verificar a implantação bem-sucedida em cada estágio do processo.</span><span class="sxs-lookup"><span data-stu-id="b3e38-110">Additional testing and monitors are in place to verify successful deployment at each stage of the process.</span></span> <span data-ttu-id="b3e38-111">Para obter mais informações sobre a cadência de liberação, consulte [Atualizar processo](hr-admin-setup-update-process.md).</span><span class="sxs-lookup"><span data-stu-id="b3e38-111">For more information on the release cadence, see [Update process](hr-admin-setup-update-process.md).</span></span>

## <a name="rounding-precision-field-isnt-editable-after-specifying-a-rounding-type-435616"></a><span data-ttu-id="b3e38-112">O campo Precisão de arredondamento não é editável após a especificação de um Tipo de arredondamento (435616)</span><span class="sxs-lookup"><span data-stu-id="b3e38-112">Rounding precision field isn't editable after specifying a Rounding type (435616)</span></span>

<span data-ttu-id="b3e38-113">Com essa alteração, o campo **Precisão de arredondamento** agora está disponível após a atualização do campo **Tipo de arredondamento**.</span><span class="sxs-lookup"><span data-stu-id="b3e38-113">With this change, the **Rounding precision** field is now available after you update the **Rounding type** field.</span></span>

## <a name="cant-edit-leave-enrollment-end-date-when-the-leave-plan-doesnt-have-accrual-periods-413628"></a><span data-ttu-id="b3e38-114">Não é possível editar a data de término do registro da licença quando o plano de licença não possui períodos de acumulação (413628)</span><span class="sxs-lookup"><span data-stu-id="b3e38-114">Can't edit leave enrollment end date when the leave plan doesn't have accrual periods (413628)</span></span>

<span data-ttu-id="b3e38-115">Agora é possível editar a data de término do registro sem receber o erro "O campo Data base da competência deve ser preenchido".</span><span class="sxs-lookup"><span data-stu-id="b3e38-115">You can now edit the enrollment end date without getting the error "Field Accrual date basis must be filled in."</span></span>

## <a name="employment-entity-doesnt-sync-to-dataverse-430834"></a><span data-ttu-id="b3e38-116">A entidade de emprego não sincroniza com o Dataverse (430834)</span><span class="sxs-lookup"><span data-stu-id="b3e38-116">Employment entity doesn't sync to Dataverse (430834)</span></span>

<span data-ttu-id="b3e38-117">Essa alteração corrige um problema em que os dados do emprego não estavam sendo sincronizados com o Dataverse após a adição de dimensões financeiras.</span><span class="sxs-lookup"><span data-stu-id="b3e38-117">This change corrects an issue where the employment data wasn't syncing to Dataverse after adding financial dimensions.</span></span> 

## <a name="remove-multi-parenting-for-work-calendar-time-interval-entity-431775"></a><span data-ttu-id="b3e38-118">Remover entidade com vários pais para a entidade Intervalo do Calendário de Trabalho (431775)</span><span class="sxs-lookup"><span data-stu-id="b3e38-118">Remove multi-parenting for Work Calendar Time Interval entity (431775)</span></span>

<span data-ttu-id="b3e38-119">Essa alteração remove os vários pais da entidade **Intervalo do Calendário de Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="b3e38-119">This change removes multi-parenting for the **Work Calendar Time Interval** entity.</span></span>

## <a name="filter-with-cast-function-doesnt-work-on-odata-call-position-worker-assignment-entity-431699"></a><span data-ttu-id="b3e38-120">O filtro com a função CAST não funciona na entidade Atribuição do Trabalhador da Posição da chamada do OData (431699)</span><span class="sxs-lookup"><span data-stu-id="b3e38-120">Filter with CAST function doesn't work on OData call Position Worker Assignment entity (431699)</span></span>

<span data-ttu-id="b3e38-121">Essa atualização inclui uma alteração para permitir o filtro com a função CAST no OData para a entidade **Atribuição do Trabalhador da Posição**.</span><span class="sxs-lookup"><span data-stu-id="b3e38-121">This update includes a change to allow  filter with CAST function within OData for the **Position Worker Assignment** entity.</span></span>

## <a name="in-preview"></a><span data-ttu-id="b3e38-122">Em Visualização</span><span class="sxs-lookup"><span data-stu-id="b3e38-122">In Preview</span></span>

## <a name="leave-suspension"></a><span data-ttu-id="b3e38-123">Sair da suspensão</span><span class="sxs-lookup"><span data-stu-id="b3e38-123">Leave suspension</span></span>

<span data-ttu-id="b3e38-124">Você pode suspender a licença e a ausência em Human Resources para um funcionário.</span><span class="sxs-lookup"><span data-stu-id="b3e38-124">You can suspend leave and absence in Human Resources for an employee.</span></span> <span data-ttu-id="b3e38-125">Suspender licença interrompe a acumulação de licenças de licença para os tipos de licença selecionados.</span><span class="sxs-lookup"><span data-stu-id="b3e38-125">Suspending leave stops the leave accruals for selected leave types.</span></span> <span data-ttu-id="b3e38-126">Se a suspensão ocorrer depois de um acúmulo ter sido processado, a suspensão da licença criará um ajuste rateado para o saldo de licença do funcionário.</span><span class="sxs-lookup"><span data-stu-id="b3e38-126">If the suspension occurs after an accrual has been processed, suspending leave creates a prorated adjustment to the employee's leave balance.</span></span> <span data-ttu-id="b3e38-127">Para obter mais informações, consulte [Suspender licença](hr-leave-and-absence-suspend-leave.md).</span><span class="sxs-lookup"><span data-stu-id="b3e38-127">For more information, see [Suspend leave](hr-leave-and-absence-suspend-leave.md).</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="b3e38-128">Regras de postergação</span><span class="sxs-lookup"><span data-stu-id="b3e38-128">Carry forward rules</span></span>

<span data-ttu-id="b3e38-129">Você pode especificar um tipo de licença postergada para saldos postergados nos quais ajustes postergados são transferidos.</span><span class="sxs-lookup"><span data-stu-id="b3e38-129">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="b3e38-130">Por exemplo, se um funcionário adianta 10 dias, você pode escolher um tipo de licença diferente para esses 10 dias.</span><span class="sxs-lookup"><span data-stu-id="b3e38-130">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="b3e38-131">Para obter mais informações, consulte [Configurar tipos de licença e ausência](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="b3e38-131">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="known-issues"></a><span data-ttu-id="b3e38-132">Problemas conhecidos</span><span class="sxs-lookup"><span data-stu-id="b3e38-132">Known issues</span></span>

## <a name="employment-details-entity"></a><span data-ttu-id="b3e38-133">Entidade Detalhes do emprego</span><span class="sxs-lookup"><span data-stu-id="b3e38-133">Employment Details entity</span></span>

<span data-ttu-id="b3e38-134">A entidade **Detalhes de emprego** foi atualizada com os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="b3e38-134">The **Employment Detail** entity has been updated with the following fields:</span></span>

- <span data-ttu-id="b3e38-135">**Frequência de Pagamento**</span><span class="sxs-lookup"><span data-stu-id="b3e38-135">**PayFrequency**</span></span>
- <span data-ttu-id="b3e38-136">**Categoria de emprego**</span><span class="sxs-lookup"><span data-stu-id="b3e38-136">**Employment Category ID**</span></span>
- <span data-ttu-id="b3e38-137">**Tipo de emprego**</span><span class="sxs-lookup"><span data-stu-id="b3e38-137">**Employment Type**</span></span>
- <span data-ttu-id="b3e38-138">**ID de EmploymentType**</span><span class="sxs-lookup"><span data-stu-id="b3e38-138">**EmploymentType ID**</span></span>
- <span data-ttu-id="b3e38-139">**Status de benefícios de emprego**</span><span class="sxs-lookup"><span data-stu-id="b3e38-139">**Benefit Employment Status**</span></span>

<span data-ttu-id="b3e38-140">Os dados de configuração desses campos dependem da ativação do gerenciamento de benefícios no espaço de trabalho **Gerenciamento de recursos**.</span><span class="sxs-lookup"><span data-stu-id="b3e38-140">The setup data for these fields rely on benefits management being enabled in the **Feature management** workspace.</span></span> <span data-ttu-id="b3e38-141">Não preencha ou atualize esses campos na entidade **Detalhes de emprego**, pois isso resultará em erros durante a importação.</span><span class="sxs-lookup"><span data-stu-id="b3e38-141">Don't populate or update these fields in the **Employment Detail** entity, because it will result in errors during import.</span></span>

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a><span data-ttu-id="b3e38-142">A visualização do SharePoint não funcionará em alguns ambientes</span><span class="sxs-lookup"><span data-stu-id="b3e38-142">SharePoint preview doesn't work in some environments</span></span>

<span data-ttu-id="b3e38-143">Se a visualização de documentos armazenados no SharePoint não funcionar, tente o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="b3e38-143">If document preview for documents stored in SharePoint doesn't work, try the following procedure:</span></span>

1. <span data-ttu-id="b3e38-144">Verifique se a conta de usuário do administrador possui um email associado ao registro do usuário.</span><span class="sxs-lookup"><span data-stu-id="b3e38-144">Verify the Admin user account has an email associated with the user record.</span></span> <span data-ttu-id="b3e38-145">Você pode exibir essas informações na página **Usuário**.</span><span class="sxs-lookup"><span data-stu-id="b3e38-145">You can view this information in the **User** page.</span></span> <span data-ttu-id="b3e38-146">Se o email não estiver configurado, você precisará adicionar o email e o provedor com o suplemento do OData Excel.</span><span class="sxs-lookup"><span data-stu-id="b3e38-146">If email isn't set up, you need to add the email and provider with the OData Excel add-in.</span></span> <span data-ttu-id="b3e38-147">Por padrão, o endereço de email não está presente no design do Excel.</span><span class="sxs-lookup"><span data-stu-id="b3e38-147">By default, the email address isn't present in the Excel design.</span></span> <span data-ttu-id="b3e38-148">Será preciso editar o design do Excel, adicionar todos os campos, aplicar e atualizar.</span><span class="sxs-lookup"><span data-stu-id="b3e38-148">You'll need to edit the Excel design, add all fields, apply, and refresh.</span></span> <span data-ttu-id="b3e38-149">Depois de concluir essas etapas, você pode atualizar a conta de administrador.</span><span class="sxs-lookup"><span data-stu-id="b3e38-149">Once you've completed those steps, you can update the admin account.</span></span>

2. <span data-ttu-id="b3e38-150">Depois que a conta de administrador tiver uma conta de email associada, entre no Human Resources com credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="b3e38-150">After the Admin account has an associated email account, sign in to Human Resources with Admin credentials.</span></span>

3. <span data-ttu-id="b3e38-151">Acesse um anexo no SharePoint para iniciar a visualização do documento.</span><span class="sxs-lookup"><span data-stu-id="b3e38-151">Access an attachment in SharePoint to start the document preview.</span></span>

4. <span data-ttu-id="b3e38-152">Entre com outra conta de usuário que tenha acesso a anexos e verifique se a visualização funciona conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="b3e38-152">Sign in with another user account that has access to attachments and verify that the preview works as expected.</span></span>

## <a name="see-also"></a><span data-ttu-id="b3e38-153">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b3e38-153">See also</span></span>

[<span data-ttu-id="b3e38-154">Novidades ou alterações no Human Resources</span><span class="sxs-lookup"><span data-stu-id="b3e38-154">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="b3e38-155">Visão geral da onda 2 da versão 2019 do Dynamics 365 Human Resources</span><span class="sxs-lookup"><span data-stu-id="b3e38-155">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="b3e38-156">Atualizar processo</span><span class="sxs-lookup"><span data-stu-id="b3e38-156">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="b3e38-157">Gerenciar recursos</span><span class="sxs-lookup"><span data-stu-id="b3e38-157">Manage features</span></span>](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
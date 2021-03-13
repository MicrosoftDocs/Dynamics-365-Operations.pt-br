---
title: Novidades ou alterações no Dynamics 365 Human Resources (25 de fevereiro de 2020)
description: Este artigo descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 25 de fevereiro de 2020.
author: andreabichsel
manager: tfehr
ms.date: 02/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-02-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4faecb83518f3ef8af825872abc2a6ffb94162fc
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "5128013"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-25-2020"></a><span data-ttu-id="2765f-103">Novidades ou alterações no Dynamics 365 Human Resources (25 de fevereiro de 2020)</span><span class="sxs-lookup"><span data-stu-id="2765f-103">What's new or changed in Dynamics 365 Human Resources (February 25, 2020)</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="2765f-104">Este artigo descreve os recursos novos ou alterados no Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2765f-104">This article describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="2765f-105">As alterações se aplicam ao número da compilação 8.1.2927.</span><span class="sxs-lookup"><span data-stu-id="2765f-105">Changes apply to build number 8.1.2927.</span></span> <span data-ttu-id="2765f-106">Os números entre parênteses em alguns títulos referem-se aos números de suporte do LCS para referência.</span><span class="sxs-lookup"><span data-stu-id="2765f-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="enable-case-management-navigation-and-data-management-framework-dmf-entity-414754"></a><span data-ttu-id="2765f-107">Habilitar a entidade de navegação de gerenciamento de casos e estrutura de gerenciamento de dados (DMF) (414754)</span><span class="sxs-lookup"><span data-stu-id="2765f-107">Enable Case Management navigation and data management framework (DMF) entity (414754)</span></span>

<span data-ttu-id="2765f-108">Este recurso de visualização permite a navegação adicional para casos de gerenciamento de casos.</span><span class="sxs-lookup"><span data-stu-id="2765f-108">This preview feature enables additional navigation to case management cases.</span></span> <span data-ttu-id="2765f-109">É possível habilitar esse recurso de visualização no espaço de trabalho **Gerenciamento de recursos**.</span><span class="sxs-lookup"><span data-stu-id="2765f-109">You can enable this preview feature in the **Feature Management** workspace.</span></span> <span data-ttu-id="2765f-110">Esses itens de menu são exibidos no espaço de trabalho **Conformidade** de Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2765f-110">These menu items appear in the **Compliance** workspace of Dynamics 365 Human Resources.</span></span> <span data-ttu-id="2765f-111">Com essa alteração, os recursos humanos podem acessar:</span><span class="sxs-lookup"><span data-stu-id="2765f-111">With this change, Human Resources can access:</span></span>

- <span data-ttu-id="2765f-112">Todos os casos</span><span class="sxs-lookup"><span data-stu-id="2765f-112">All cases</span></span>
- <span data-ttu-id="2765f-113">Meus casos</span><span class="sxs-lookup"><span data-stu-id="2765f-113">My cases</span></span>
- <span data-ttu-id="2765f-114">Meus casos abertos</span><span class="sxs-lookup"><span data-stu-id="2765f-114">My open cases</span></span>
- <span data-ttu-id="2765f-115">Meus casos expirados</span><span class="sxs-lookup"><span data-stu-id="2765f-115">My overdue cases</span></span>
- <span data-ttu-id="2765f-116">Ocorrências atribuídas a mim por meio do fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="2765f-116">Cases assigned to me through workflow</span></span>

<span data-ttu-id="2765f-117">Juntamente com essas novas exibições nos casos, a entidade DMF **Detalhe de casos** também está disponível.</span><span class="sxs-lookup"><span data-stu-id="2765f-117">Along with these new views into cases, the **Case detail** DMF entity is also available.</span></span>

## <a name="enable-relationship-definitions-in-global-address-bbook-414762"></a><span data-ttu-id="2765f-118">Habilitar definições de relacionamento no e-Book de endereço global (414762)</span><span class="sxs-lookup"><span data-stu-id="2765f-118">Enable Relationship definitions in global address bBook (414762)</span></span>

<span data-ttu-id="2765f-119">Agora as relações estão habilitadas no catálogo de endereços global.</span><span class="sxs-lookup"><span data-stu-id="2765f-119">Relationships are now enabled in the global address book.</span></span> <span data-ttu-id="2765f-120">Antes da liberação desta semana, a caixa de fatos **Relacionamento** exibiu qualquer relacionamento definido pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="2765f-120">Prior to this week's release, the **Relationship** fact box displayed any system-defined relationships.</span></span> <span data-ttu-id="2765f-121">Agora, você pode definir essas relações na página de catálogo de endereços global.</span><span class="sxs-lookup"><span data-stu-id="2765f-121">Now you can define those relationships within the global address book page.</span></span>

## <a name="a-position-can-be-removed-when-active-compensation-records-exist-for-the-position-414568"></a><span data-ttu-id="2765f-122">Uma posição pode ser removida quando há registros de compensação ativos para a posição (414568)</span><span class="sxs-lookup"><span data-stu-id="2765f-122">A position can be removed when active compensation records exist for the position (414568)</span></span>

<span data-ttu-id="2765f-123">Com essa alteração, um aviso é exibido quando você tenta excluir uma posição e um trabalhador tem um registro de compensação ativo para aquela mesma posição.</span><span class="sxs-lookup"><span data-stu-id="2765f-123">With this change, a warning appears when you attempt to delete a position and a worker has an active compensation record for that same position.</span></span> <span data-ttu-id="2765f-124">Quando isso acontece, você deve atualizar o registro de remuneração fixa do funcionário antes de remover a posição.</span><span class="sxs-lookup"><span data-stu-id="2765f-124">When this happens, you must update the employee fixed compensation record before removing the position.</span></span>

## <a name="performance-review-workflow-occasionally-adds-sign-offs-from-people-who-are-not-part-of-the-process-414171"></a><span data-ttu-id="2765f-125">O fluxo de trabalho de avaliação de desempenho adiciona ocasionalmente as aprovações de pessoas que não fazem parte do processo (414171)</span><span class="sxs-lookup"><span data-stu-id="2765f-125">Performance review workflow occasionally adds sign-offs from people who are not part of the process (414171)</span></span>

<span data-ttu-id="2765f-126">Essa alteração corrige um problema em que os participantes de aprovação extras são adicionados à avaliação de desempenho.</span><span class="sxs-lookup"><span data-stu-id="2765f-126">This change corrects an issue where additional sign-off participants are added to the performance review.</span></span>

## <a name="worker-position-assignment-not-created-in-dataverse-when-selected-on-the-new-worker-dialog-413479"></a><span data-ttu-id="2765f-127">Atribuição de posição de trabalhador no Dataverse não criada quando selecionada na caixa de diálogo Novo trabalhador (413479)</span><span class="sxs-lookup"><span data-stu-id="2765f-127">Worker position assignment not created in Dataverse when selected on the New Worker dialog (413479)</span></span>

<span data-ttu-id="2765f-128">Essa alteração corrige um problema durante a contratação de um novo trabalhador e a atribuição da nova contratação a uma posição por meio da caixa de diálogo **Novo trabalhador**.</span><span class="sxs-lookup"><span data-stu-id="2765f-128">This change corrects an issue when hiring a new worker and assigning the new hire to a position through the **New worker** dialog.</span></span> <span data-ttu-id="2765f-129">Agora, a atribuição de posição está refletida em Dataverse.</span><span class="sxs-lookup"><span data-stu-id="2765f-129">Now the position assignment is reflected in Dataverse.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="2765f-130">Em breve</span><span class="sxs-lookup"><span data-stu-id="2765f-130">Coming soon</span></span>

### <a name="updated-dataverse-solution"></a><span data-ttu-id="2765f-131">Solução Dataverse atualizada</span><span class="sxs-lookup"><span data-stu-id="2765f-131">Updated Dataverse solution</span></span>

<span data-ttu-id="2765f-132">Uma nova solução de Dataverse estará disponível em breve com as seguintes alterações:</span><span class="sxs-lookup"><span data-stu-id="2765f-132">A new Dataverse solution will be available soon with the following changes:</span></span>

| <span data-ttu-id="2765f-133">Descrição</span><span class="sxs-lookup"><span data-stu-id="2765f-133">Description</span></span> | <span data-ttu-id="2765f-134">Troco</span><span class="sxs-lookup"><span data-stu-id="2765f-134">Change</span></span> |
| ----------------------------------------- | --- |
| <span data-ttu-id="2765f-135">Alterações de entidade do **Trabalho/Posição**</span><span class="sxs-lookup"><span data-stu-id="2765f-135">**Job/Position** entity changes</span></span> | <span data-ttu-id="2765f-136">**Região de remuneração** adicionado</span><span class="sxs-lookup"><span data-stu-id="2765f-136">**Compensation region** added</span></span></br><span data-ttu-id="2765f-137">**Dimensões financeiras** adicionado</span><span class="sxs-lookup"><span data-stu-id="2765f-137">**Financial dimensions** added</span></span> |
| <span data-ttu-id="2765f-138">Alterações de entidade do **Trabalhador**</span><span class="sxs-lookup"><span data-stu-id="2765f-138">**Worker** entity changes</span></span> | <span data-ttu-id="2765f-139">**Sequência do nome** adicionado</span><span class="sxs-lookup"><span data-stu-id="2765f-139">**Name sequence** added</span></span></br><span data-ttu-id="2765f-140">**Trabalha de casa** adicionado</span><span class="sxs-lookup"><span data-stu-id="2765f-140">**Works from home** added</span></span></br><span data-ttu-id="2765f-141">**Idioma** adicionado</span><span class="sxs-lookup"><span data-stu-id="2765f-141">**Language** added</span></span></br><span data-ttu-id="2765f-142">**Aniversário de tempo de serviço** adicionado</span><span class="sxs-lookup"><span data-stu-id="2765f-142">**Seniority date** added</span></span></br><span data-ttu-id="2765f-143">**Data de aniversário** adicionado</span><span class="sxs-lookup"><span data-stu-id="2765f-143">**Anniversary date** added</span></span></br><span data-ttu-id="2765f-144">**Data original de contratação** adicionado</span><span class="sxs-lookup"><span data-stu-id="2765f-144">**Original hire date** added</span></span> |
| <span data-ttu-id="2765f-145">Alterações de entidade do **Emprego**</span><span class="sxs-lookup"><span data-stu-id="2765f-145">**Employment** entity changes</span></span> | <span data-ttu-id="2765f-146">**Dimensões financeiras** adicionado</span><span class="sxs-lookup"><span data-stu-id="2765f-146">**Financial dimensions** added</span></span></br><span data-ttu-id="2765f-147">**Motivo da demissão** adicionado</span><span class="sxs-lookup"><span data-stu-id="2765f-147">**Termination reason** added</span></span></br><span data-ttu-id="2765f-148">**Data da demissão** renomeada de **Data de transição**</span><span class="sxs-lookup"><span data-stu-id="2765f-148">**Termination date** renamed from **Transition date**</span></span></br><span data-ttu-id="2765f-149">**Data de experiência** adicionado</span><span class="sxs-lookup"><span data-stu-id="2765f-149">**Probation date** added</span></span> |
| <span data-ttu-id="2765f-150">Alterações de entidade do **Endereço do trabalhador**</span><span class="sxs-lookup"><span data-stu-id="2765f-150">**Worker address** entity changes</span></span> | <span data-ttu-id="2765f-151">**Endereço** adicionado</span><span class="sxs-lookup"><span data-stu-id="2765f-151">**Street address** added</span></span></br><span data-ttu-id="2765f-152">**Linha de endereço 1**, **Linha de endereço 2** e **Linha de endereço 3** marcadas para depreciação</span><span class="sxs-lookup"><span data-stu-id="2765f-152">**Address line 1**, **Address line 2**, and **Address line 3** marked for deprecation</span></span> |
| <span data-ttu-id="2765f-153">Novas entidades de configuração de remuneração variável</span><span class="sxs-lookup"><span data-stu-id="2765f-153">New variable compensation setup entities</span></span> | <span data-ttu-id="2765f-154">**Tipo de plano de remuneração variável**</span><span class="sxs-lookup"><span data-stu-id="2765f-154">**Compensation variable plan type**</span></span></br><span data-ttu-id="2765f-155">**Plano de remuneração variável**</span><span class="sxs-lookup"><span data-stu-id="2765f-155">**Compensation variable plan**</span></span></br><span data-ttu-id="2765f-156">**Regras de benefício proporcional diferido**</span><span class="sxs-lookup"><span data-stu-id="2765f-156">**Vesting rules**</span></span></br><span data-ttu-id="2765f-157">**Nível do plano de remuneração variável**</span><span class="sxs-lookup"><span data-stu-id="2765f-157">**Compensation variable plan level**</span></span> |
| <span data-ttu-id="2765f-158">Nova entidade **Emprego do calendário do trabalhador**</span><span class="sxs-lookup"><span data-stu-id="2765f-158">New **Worker calendar employment** entity</span></span> | <span data-ttu-id="2765f-159">**Entidade do calendário de trabalho** adicionada</span><span class="sxs-lookup"><span data-stu-id="2765f-159">**Work calendar entity** added</span></span> |
| <span data-ttu-id="2765f-160">Nova entidade **Detalhe da posição de folha de pagamento**</span><span class="sxs-lookup"><span data-stu-id="2765f-160">New **Payroll position detail** entity</span></span> | <span data-ttu-id="2765f-161">**Detalhe da posição de folha de pagamento** adicionado</span><span class="sxs-lookup"><span data-stu-id="2765f-161">**Payroll position detail** added</span></span> |
| <span data-ttu-id="2765f-162">Nova entidade **Bloco**</span><span class="sxs-lookup"><span data-stu-id="2765f-162">New **Title** entity</span></span> | <span data-ttu-id="2765f-163">**Bloco** adicionado.</span><span class="sxs-lookup"><span data-stu-id="2765f-163">**Title** added.</span></span> <span data-ttu-id="2765f-164">A nova entidade **Título** será incluída no processo de sincronização entre Human Resources e Dataverse.</span><span class="sxs-lookup"><span data-stu-id="2765f-164">The new **Title** entity will be included in the sync process between Human Resources and Dataverse.</span></span> <span data-ttu-id="2765f-165">Não será inicialmente referenciada de entidades **Cargo** ou **Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="2765f-165">It won't be initially referenced from **Job Position** or **Job** entities.</span></span> |

<span data-ttu-id="2765f-166">Nas próximas semanas, essas alterações de entidade estarão disponíveis em todos os ambientes.</span><span class="sxs-lookup"><span data-stu-id="2765f-166">Over the next few weeks, these entity changes will be available in all environments.</span></span> <span data-ttu-id="2765f-167">Para instalar manualmente a solução Dataverse mais recente para recursos humanos:</span><span class="sxs-lookup"><span data-stu-id="2765f-167">To manually install the latest Dataverse solution for Human Resources:</span></span>

1.  <span data-ttu-id="2765f-168">Vá para [Centro de administração do Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="2765f-168">Go to the [Power Platform Admin Center](https://admin.powerplatform.microsoft.com).</span></span>

2.  <span data-ttu-id="2765f-169">Selecione **Ambientes**.</span><span class="sxs-lookup"><span data-stu-id="2765f-169">Select **Environments**.</span></span>

3.  <span data-ttu-id="2765f-170">Localize o ambiente que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="2765f-170">Find the environment you want to upgrade.</span></span> <span data-ttu-id="2765f-171">Ele deve corresponder ao **Nome do ambiente** na seção **informações do Common Data Service** no formulário **Sobre** em Recursos Humanos.</span><span class="sxs-lookup"><span data-stu-id="2765f-171">This should correspond to **Environment name** in the **Common Data Service information** section in the **About** form in Human Resources.</span></span>

4.  <span data-ttu-id="2765f-172">Selecione o ambiente para exibir os detalhes do ambiente.</span><span class="sxs-lookup"><span data-stu-id="2765f-172">Select the environment to view the environment details.</span></span>

5.  <span data-ttu-id="2765f-173">Na barra de ação na parte superior, selecione **Gerenciar soluções**.</span><span class="sxs-lookup"><span data-stu-id="2765f-173">In the action bar at the top, select **Manage Solutions**.</span></span> <span data-ttu-id="2765f-174">Uma nova janela do navegador irá abrir e navegar até o **Centro de Administração do Dynamics 365** no contexto do seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="2765f-174">A new browser window will open and navigate to **Dynamics 365 Administration Center** in the context of your environment.</span></span>

6.  <span data-ttu-id="2765f-175">Na lista **Solução**, selecione **Ancoragem de Dynamics 365 Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="2765f-175">In the **Solution** list, select **Dynamics 365 Human Resources Anchor**.</span></span>

7.  <span data-ttu-id="2765f-176">Selecione **Atualizar** para aplicar a solução mais recente.</span><span class="sxs-lookup"><span data-stu-id="2765f-176">Select **Upgrade** to apply the latest solution.</span></span>

## <a name="in-preview"></a><span data-ttu-id="2765f-177">Em visualização</span><span class="sxs-lookup"><span data-stu-id="2765f-177">In preview</span></span>

<span data-ttu-id="2765f-178">Os seguintes recursos de visualização foram disponibilizados em 3 de fevereiro de 2020:</span><span class="sxs-lookup"><span data-stu-id="2765f-178">The following preview features became available on February 3, 2020:</span></span>

- <span data-ttu-id="2765f-179">**Recursos de exibição de licenças e ausências** - para obter mais informações, consulte [Recursos de exibição de licenças e ausências](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).</span><span class="sxs-lookup"><span data-stu-id="2765f-179">**Leave and absence preview features** - For more information, see [Leave and absence preview features](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).</span></span>

- <span data-ttu-id="2765f-180">**Recurso de visualização de gerenciamento de benefícios** - para obter mais informações, incluindo problemas conhecidos, consulte [Visão geral do gerenciamento de benefícios](hr-benefits-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2765f-180">**Benefits management preview feature** - For more information, including known issues, see [Benefits management overview](hr-benefits-management-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2765f-181">Consulte também</span><span class="sxs-lookup"><span data-stu-id="2765f-181">See also</span></span>

[<span data-ttu-id="2765f-182">Novidades ou alterações no Human Resources</span><span class="sxs-lookup"><span data-stu-id="2765f-182">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="2765f-183">Visão geral da onda 2 da versão 2019 do Dynamics 365 Human Resources</span><span class="sxs-lookup"><span data-stu-id="2765f-183">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="2765f-184">Atualizar processo</span><span class="sxs-lookup"><span data-stu-id="2765f-184">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="2765f-185">Gerenciar recursos</span><span class="sxs-lookup"><span data-stu-id="2765f-185">Manage features</span></span>](hr-admin-manage-features.md)
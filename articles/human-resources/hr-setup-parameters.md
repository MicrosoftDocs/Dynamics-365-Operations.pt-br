---
title: Configurar parâmetros de recursos do Human Resources
description: Este tópico explica como configurar parâmetros específicos da empresa no Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HRMParameters, HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 51941
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 10f3c62925f6b951f88b990cb8b103dde54c27d1
ms.sourcegitcommit: 45d10d0c25b3ec585323709bb97ba1895b500429
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2021
ms.locfileid: "5502931"
---
# <a name="configure-human-resources-parameters"></a><span data-ttu-id="85c18-103">Configurar parâmetros de recursos do Human Resources</span><span class="sxs-lookup"><span data-stu-id="85c18-103">Configure Human resources parameters</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="85c18-104">As configurações de alguns parâmetros do Human Resources são compartilhadas entre empresas, enquanto as configurações de outros parâmetros são específicas da empresa.</span><span class="sxs-lookup"><span data-stu-id="85c18-104">The settings of some Human resources parameters are shared across companies, while the settings of other parameters are company-specific.</span></span> <span data-ttu-id="85c18-105">Este tópico explica como configurar parâmetros específicos da empresa no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="85c18-105">This topic explains how to set up company-specific Human resources parameters.</span></span>

<span data-ttu-id="85c18-106">Duas páginas são usadas para definir parâmetros de recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="85c18-106">Two pages are used to set Human resources parameters.</span></span> <span data-ttu-id="85c18-107">Para os parâmetros que são compartilhados entre empresas, use a página **Parâmetros compartilhados de recursos humanos**.</span><span class="sxs-lookup"><span data-stu-id="85c18-107">For parameters that are shared across companies, you use the **Human resources shared parameters** page.</span></span> <span data-ttu-id="85c18-108">Para os parâmetros que são específicos da empresa (ou seja, as configurações se aplicam a uma única empresa), use a página **Parâmetros de recursos humanos**.</span><span class="sxs-lookup"><span data-stu-id="85c18-108">For parameters that are company-specific (in other words, the settings apply to a single company), you use the **Human resource parameters** page.</span></span>

![Acesse Parâmetros de recursos humanos](./media/hr-employee-self-service-human-resources-parameters.png)

<span data-ttu-id="85c18-110">Na página **Parâmetros de recursos humanos**, as configurações são divididas entre seis guias:</span><span class="sxs-lookup"><span data-stu-id="85c18-110">On the **Human resources parameters** page, the settings are divided among six tabs:</span></span>

- <span data-ttu-id="85c18-111">**Geral**</span><span class="sxs-lookup"><span data-stu-id="85c18-111">**General**</span></span>
- <span data-ttu-id="85c18-112">**Recrutamento** (esta guia não está incluída no Dynamics 365 Human Resources)</span><span class="sxs-lookup"><span data-stu-id="85c18-112">**Recruitment** (this tab isn't included in Dynamics 365 Human Resources)</span></span>
- <span data-ttu-id="85c18-113">**Remuneração**</span><span class="sxs-lookup"><span data-stu-id="85c18-113">**Compensation**</span></span>
- <span data-ttu-id="85c18-114">**Sequências numéricas**</span><span class="sxs-lookup"><span data-stu-id="85c18-114">**Number sequences**</span></span>
- <span data-ttu-id="85c18-115">**FMLA**</span><span class="sxs-lookup"><span data-stu-id="85c18-115">**FMLA**</span></span>
- <span data-ttu-id="85c18-116">**Autoatendimento para funcionários**</span><span class="sxs-lookup"><span data-stu-id="85c18-116">**Employee self service**</span></span>
- <span data-ttu-id="85c18-117">**Autoatendimento para gerentes**</span><span class="sxs-lookup"><span data-stu-id="85c18-117">**Manager self service**</span></span>
- <span data-ttu-id="85c18-118">**Gerenciamento de benefícios**</span><span class="sxs-lookup"><span data-stu-id="85c18-118">**Benefits management**</span></span>
- <span data-ttu-id="85c18-119">**Licença e ausência**</span><span class="sxs-lookup"><span data-stu-id="85c18-119">**Leave and absence**</span></span>
- <span data-ttu-id="85c18-120">**Formas de pagamento**</span><span class="sxs-lookup"><span data-stu-id="85c18-120">**Payment methods**</span></span>

<span data-ttu-id="85c18-121">Cada guia contém informações que pertencem a uma única empresa.</span><span class="sxs-lookup"><span data-stu-id="85c18-121">Each tab contains information that pertains to a single company.</span></span>

## <a name="general"></a><span data-ttu-id="85c18-122">Geral</span><span class="sxs-lookup"><span data-stu-id="85c18-122">General</span></span>

<span data-ttu-id="85c18-123">As configurações na guia **Geral** definem a aparência das informações sobre ausência, lesões e doenças, e novas contratações.</span><span class="sxs-lookup"><span data-stu-id="85c18-123">The settings on the **General** tab define the appearance of information about absence, injury and illness, and new hires.</span></span> <span data-ttu-id="85c18-124">As configurações nessa guia também definem algumas entradas padrão que aparecem enquanto você trabalha.</span><span class="sxs-lookup"><span data-stu-id="85c18-124">The settings on this tab also define some default entries that appear as you work.</span></span> <span data-ttu-id="85c18-125">Especificamente, esta guia permite:</span><span class="sxs-lookup"><span data-stu-id="85c18-125">Specifically, this tab lets you:</span></span>

- <span data-ttu-id="85c18-126">Selecione a cor a ser aplicada a transações de ausência abertas</span><span class="sxs-lookup"><span data-stu-id="85c18-126">Select a color to apply to open absence transactions</span></span>
- <span data-ttu-id="85c18-127">Especificar a folha de estilos a ser usada para relatórios</span><span class="sxs-lookup"><span data-stu-id="85c18-127">Specify the style sheet to use for reports</span></span>
- <span data-ttu-id="85c18-128">Habilitar a integração entre os cursos de treinamento e o registro de ausência</span><span class="sxs-lookup"><span data-stu-id="85c18-128">Enable the integration between training courses and absence registration</span></span>
- <span data-ttu-id="85c18-129">Selecione o código de ausência usado para controlar essa integração.</span><span class="sxs-lookup"><span data-stu-id="85c18-129">Select the absence code that is used to control this integration.</span></span>
- <span data-ttu-id="85c18-130">Indique por quanto tempo manter incidentes de caso de ferimentos e doenças.</span><span class="sxs-lookup"><span data-stu-id="85c18-130">Indicate how long to keep injury and illness case incidents.</span></span>
- <span data-ttu-id="85c18-131">Especifique o número de identificação padrão mostrado quando um novo trabalhador é contratado.</span><span class="sxs-lookup"><span data-stu-id="85c18-131">Specify the default identification number shown when a new worker is hired.</span></span>

![Guia Geral](./media/hr-setup-parameters-general.png)

## <a name="recruitment"></a><span data-ttu-id="85c18-133">Recrutamento</span><span class="sxs-lookup"><span data-stu-id="85c18-133">Recruitment</span></span>

<span data-ttu-id="85c18-134">As configurações na guia **Recrutamento** definem os tipos de documento usados para correspondência enviados automaticamente aos candidatos.</span><span class="sxs-lookup"><span data-stu-id="85c18-134">The settings on the **Recruitment** tab define the document types used for correspondence automatically sent to applicants.</span></span> <span data-ttu-id="85c18-135">Você também pode indicar o projeto de recrutamento usado para solicitações de emprego não solicitadas.</span><span class="sxs-lookup"><span data-stu-id="85c18-135">You can also indicate the recruitment project used for unsolicited applications.</span></span>

<span data-ttu-id="85c18-136">O período definido para o vencimento do projeto de recrutamento determina os projetos de recrutamento incluídos no bloco **Projetos de vencimento** no espaço de trabalho **Gerenciamento de recrutamento**.</span><span class="sxs-lookup"><span data-stu-id="85c18-136">The period defined for recruitment project aging determines the recruitment projects included on the **Aging projects** tile in the **Recruitment management** workspace.</span></span> <span data-ttu-id="85c18-137">O período definido para o aviso de prazo da solicitação de emprego é usado para exibir projetos de recrutamento que estão se aproximando do prazo final para solicitação de emprego no bloco **Prazo final para solicitação de emprego se aproximando** no espaço de trabalho **Recrutamento**.</span><span class="sxs-lookup"><span data-stu-id="85c18-137">The period defined for the application deadline warning is used to display recruitment projects that are approaching their application deadline on the **Application deadline approaching** tile in the **Recruitment** workspace.</span></span>

<span data-ttu-id="85c18-138">Para obter mais informações sobre recrutamento, consulte [Recrutar candidatos ao trabalho](hr-personnel-recruit.md).</span><span class="sxs-lookup"><span data-stu-id="85c18-138">For more information about recruiting, see [Recruit job candidates](hr-personnel-recruit.md).</span></span>

## <a name="compensation"></a><span data-ttu-id="85c18-139">Remuneração</span><span class="sxs-lookup"><span data-stu-id="85c18-139">Compensation</span></span>

<span data-ttu-id="85c18-140">No Dynamics 365 Finance, as configurações na guia **Remuneração** definem se os usuários devem confirmar que desejam salvar informações para um plano de remuneração fixo ou variável.</span><span class="sxs-lookup"><span data-stu-id="85c18-140">In Dynamics 365 Finance, the settings on the **Compensation** tab define whether users must confirm that they want to save information for a fixed or variable compensation plan.</span></span> <span data-ttu-id="85c18-141">Se você selecionar **Permitir salvar validação**, quando os usuários fecharem uma página relacionada à remuneração, eles receberão uma mensagem que pergunta se eles desejam salvar o registro.</span><span class="sxs-lookup"><span data-stu-id="85c18-141">If you select **Enable save validation**, when users close a compensation-related page, they receive a message that asks whether they want to save the record.</span></span> <span data-ttu-id="85c18-142">Algumas páginas no Gerenciamento de remuneração não permitem que usuários excluam informações.</span><span class="sxs-lookup"><span data-stu-id="85c18-142">Some pages in Compensation management don't let users delete information.</span></span> <span data-ttu-id="85c18-143">Ao solicitar que os usuários verifiquem se desejam salvar informações, é possível limitar a quantidade de informações que serão salvas, mas não poderão ser excluídas posteriormente.</span><span class="sxs-lookup"><span data-stu-id="85c18-143">By prompting users to verify that they want to save information, you might be able to limit the amount of information that is saved but can't be deleted later.</span></span> <span data-ttu-id="85c18-144">Se você desmarcar **Permitir salvar validação**, os registros serão salvos imediatamente, possivelmente antes que o usuário esteja pronto.</span><span class="sxs-lookup"><span data-stu-id="85c18-144">If you clear **Enable save validation**, records save immediately, possibly before the user is ready.</span></span> <span data-ttu-id="85c18-145">Se você estiver usando o Gerenciamento de desempenho, a guia **Remuneração** também permitirá que você selecione um modelo de avaliação a ser usado em vez do modelo atribuído aos planos de remuneração ao avaliar o desempenho.</span><span class="sxs-lookup"><span data-stu-id="85c18-145">If you're using Performance management, the **Compensation** tab also lets you select a rating model to use instead of the model assigned to compensation plans when rating performance.</span></span>

<span data-ttu-id="85c18-146">No Human Resources, você pode usar a guia **Remuneração** para optar por restringir o acesso aos planos de remuneração e definir uma moeda padrão.</span><span class="sxs-lookup"><span data-stu-id="85c18-146">In Human Resources, you can use the **Compensation** tab to choose to restrict access to compensation plans and to set a default currency.</span></span>

<span data-ttu-id="85c18-147">Para obter mais informações sobre remuneração, consulte [Visão geral de planos de remuneração](hr-compensation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="85c18-147">For more information about compensation, see [Compensation plans overview](hr-compensation-overview.md).</span></span>

![Guia Remuneração](./media/hr-setup-parameters-compensation.png)

## <a name="number-sequences"></a><span data-ttu-id="85c18-149">Sequências numéricas</span><span class="sxs-lookup"><span data-stu-id="85c18-149">Number sequences</span></span>

<span data-ttu-id="85c18-150">As configurações na guia **Sequência numérica** determinam as sequências usadas para atribuir IDs automaticamente a itens no Human Resources, como:</span><span class="sxs-lookup"><span data-stu-id="85c18-150">The settings on the **Number sequence** tab determine the sequences used to automatically assign IDs to items in Human Resources, such as:</span></span>

- <span data-ttu-id="85c18-151">Solicitações de emprego</span><span class="sxs-lookup"><span data-stu-id="85c18-151">Applications</span></span>
- <span data-ttu-id="85c18-152">Registros de Ausência</span><span class="sxs-lookup"><span data-stu-id="85c18-152">Absence registrations</span></span>
- <span data-ttu-id="85c18-153">Resultados do processo de remuneração</span><span class="sxs-lookup"><span data-stu-id="85c18-153">Compensation process results</span></span>
- <span data-ttu-id="85c18-154">Números de caso</span><span class="sxs-lookup"><span data-stu-id="85c18-154">Case numbers</span></span>
- <span data-ttu-id="85c18-155">Cursos</span><span class="sxs-lookup"><span data-stu-id="85c18-155">Courses</span></span>
- <span data-ttu-id="85c18-156">Agendas do curso</span><span class="sxs-lookup"><span data-stu-id="85c18-156">Course agendas</span></span>

<span data-ttu-id="85c18-157">Para manter referências e códigos de sequência numérica, use a página de lista **Sequências numéricas** (selecione **Administração organizacional > Sequências numéricas > Sequências numéricas**).</span><span class="sxs-lookup"><span data-stu-id="85c18-157">To maintain number sequence references and codes, use the **Number sequences** list page (select **Organization administration > Number sequences > Number sequences**).</span></span>

<span data-ttu-id="85c18-158">Para obter mais informações, consulte [Visão geral de sequências numéricas](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/number-sequence-overview?toc=/dynamics365/human-resources/toc.json).</span><span class="sxs-lookup"><span data-stu-id="85c18-158">For more information, see [Number sequences overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/number-sequence-overview?toc=/dynamics365/human-resources/toc.json).</span></span>

> [!NOTE]
> <span data-ttu-id="85c18-159">O número de horas que será trabalhado não pode exceder 1.250 e o tempo de emprego não pode exceder 12 meses.</span><span class="sxs-lookup"><span data-stu-id="85c18-159">The number of hours that are worked can't exceed 1,250, and the length of employment can't exceed 12 months.</span></span> <span data-ttu-id="85c18-160">Esses valores máximos estão de acordo com a legislação federal dos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="85c18-160">These maximum values are in accordance with federal law in the United States.</span></span>

![Guia Sequências numéricas](./media/hr-setup-parameters-number-sequences.png)

## <a name="fmla"></a><span data-ttu-id="85c18-162">FMLA</span><span class="sxs-lookup"><span data-stu-id="85c18-162">FMLA</span></span>

<span data-ttu-id="85c18-163">Na guia FMLA, defina requisitos de direito FMLA e horas de direito FMLA.</span><span class="sxs-lookup"><span data-stu-id="85c18-163">On the FMLA tab, you set FMLA eligibility requirements and FMLA entitlement hours.</span></span> <span data-ttu-id="85c18-164">Para obter mais informações, consulte [Configurar parâmetros de licença e ausência](hr-leave-and-absence-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="85c18-164">For more information, see [Configure leave and absence parameters](hr-leave-and-absence-parameters.md).</span></span>

![Guia FMLA](./media/hr-setup-parameters-fmla.png)

## <a name="employee-self-service"></a><span data-ttu-id="85c18-166">Autoatendimento para funcionários</span><span class="sxs-lookup"><span data-stu-id="85c18-166">Employee self service</span></span>

<span data-ttu-id="85c18-167">As configurações na guia **Autoatendimento para funcionários** afetam como o Autoatendimento para funcionários aparece para funcionários.</span><span class="sxs-lookup"><span data-stu-id="85c18-167">The settings on the **Employee self service** tab affect how Employee self service appears to employees.</span></span> <span data-ttu-id="85c18-168">Nesta guia, você pode:</span><span class="sxs-lookup"><span data-stu-id="85c18-168">On this tab, you can:</span></span>

- <span data-ttu-id="85c18-169">Inserir um nome para o espaço de trabalho de Autoatendimento para funcionários</span><span class="sxs-lookup"><span data-stu-id="85c18-169">Enter a name for the Employee self service workspace</span></span>
- <span data-ttu-id="85c18-170">Selecionar as informações que um gerente pode inserir para funcionários</span><span class="sxs-lookup"><span data-stu-id="85c18-170">Select which information a manager can enter for employees</span></span>
- <span data-ttu-id="85c18-171">Adicionar links úteis para funcionários</span><span class="sxs-lookup"><span data-stu-id="85c18-171">Add useful links for employees</span></span>
- <span data-ttu-id="85c18-172">Restringir a adição ou edição de detalhes de contato comercial por funcionários.</span><span class="sxs-lookup"><span data-stu-id="85c18-172">Restrict employees from adding or editing business contact details.</span></span> <span data-ttu-id="85c18-173">Para obter mais informações, consulte [Restringir a edição de informações pessoais](hr-employee-self-service-restrict-editing.md).</span><span class="sxs-lookup"><span data-stu-id="85c18-173">For more information, see [Restrict editing of personal information](hr-employee-self-service-restrict-editing.md).</span></span>

<span data-ttu-id="85c18-174">Para obter mais informações sobre como configurar o Autoatendimento para funcionários, consulte [Visão geral de autoatendimento para funcionários e gerentes](hr-employee-manager-self-service-overview.md).</span><span class="sxs-lookup"><span data-stu-id="85c18-174">For more information about setting up Employee self service, see [Employee and Manager self service overview](hr-employee-manager-self-service-overview.md).</span></span>

![Guia Autoatendimento para funcionários](./media/hr-setup-parameters-employee-self-service.png)

## <a name="manager-self-service"></a><span data-ttu-id="85c18-176">Autoatendimento para gerentes</span><span class="sxs-lookup"><span data-stu-id="85c18-176">Manager self service</span></span>

<span data-ttu-id="85c18-177">As configurações na guia **Autoatendimento para gerentes** afetam o que gerentes visualizam em Autoatendimento para gerentes.</span><span class="sxs-lookup"><span data-stu-id="85c18-177">The settings on the **Manager self service** tab affect what managers see in Manager self service.</span></span> <span data-ttu-id="85c18-178">Nessa guia, você pode configurar as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="85c18-178">On this tab, you can configure the following options:</span></span>

- <span data-ttu-id="85c18-179">O intervalo de registros em vencimento</span><span class="sxs-lookup"><span data-stu-id="85c18-179">The range for expiring records</span></span>
- <span data-ttu-id="85c18-180">Os gerentes de informações podem ver em registros em vencimento</span><span class="sxs-lookup"><span data-stu-id="85c18-180">Information managers can view in expiring records</span></span>
- <span data-ttu-id="85c18-181">Se os gerentes podem exibir posições abertas para relatórios estendidos</span><span class="sxs-lookup"><span data-stu-id="85c18-181">Whether managers can view open positions for extended reports</span></span>
- <span data-ttu-id="85c18-182">Exibições de trabalhadores saindo da empresa</span><span class="sxs-lookup"><span data-stu-id="85c18-182">Views of exiting workers</span></span>
- <span data-ttu-id="85c18-183">Links úteis para gerentes</span><span class="sxs-lookup"><span data-stu-id="85c18-183">Useful links for managers</span></span>

<span data-ttu-id="85c18-184">Para obter mais informações sobre como configurar o Autoatendimento para gerentes, consulte [Visão geral de autoatendimento para funcionários e gerentes](hr-employee-manager-self-service-overview.md).</span><span class="sxs-lookup"><span data-stu-id="85c18-184">For more information about setting up Manager self service, see [Employee and Manager self service overview](hr-employee-manager-self-service-overview.md).</span></span>

![Guia Autoatendimento para gerentes](./media/hr-setup-parameters-manager-self-service.png)

## <a name="benefits-management"></a><span data-ttu-id="85c18-186">Gerenciamento de benefícios</span><span class="sxs-lookup"><span data-stu-id="85c18-186">Benefits management</span></span>

<span data-ttu-id="85c18-187">Na guia Gerenciamento de benefícios, você pode configurar opções de email para o Gerenciamento de benefícios.</span><span class="sxs-lookup"><span data-stu-id="85c18-187">On the Benefits management tab, you can configure email options for Benefits management.</span></span> <span data-ttu-id="85c18-188">Para obter mais informações sobre como configurar e usar o Gerenciamento de benefícios, consulte [Visão geral do Gerenciamento de benefícios](hr-benefits-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="85c18-188">For information about setting up and using Benefits management, see [Benefits management overview](hr-benefits-management-overview.md).</span></span>

![Guia Gerenciamento de benefícios](./media/hr-setup-parameters-benefits-management.png)

## <a name="leave-and-absence"></a><span data-ttu-id="85c18-190">Licença e ausência</span><span class="sxs-lookup"><span data-stu-id="85c18-190">Leave and absence</span></span>

<span data-ttu-id="85c18-191">Para obter informações sobre como configurar e usar licenças e ausências, consulte [Visão geral de licença e ausência](hr-leave-and-absence-overview.md).</span><span class="sxs-lookup"><span data-stu-id="85c18-191">For information about setting up and using Leave and absence, see [Leave and absence overview](hr-leave-and-absence-overview.md).</span></span>

## <a name="payment-methods"></a><span data-ttu-id="85c18-192">Formas de pagamento</span><span class="sxs-lookup"><span data-stu-id="85c18-192">Payment methods</span></span>

<span data-ttu-id="85c18-193">Na guia **Métodos de pagamento**, você pode selecionar os métodos de pagamento com suporte da sua organização.</span><span class="sxs-lookup"><span data-stu-id="85c18-193">On the **Payment methods** tab, you can select the payment methods supported by your organization.</span></span> <span data-ttu-id="85c18-194">Para obter mais informações sobre como configurar a remuneração, consulte [Visão geral de planos de remuneração](hr-compensation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="85c18-194">For more information about configuring compensation, see [Compensation plans overview](hr-compensation-overview.md).</span></span>

![Guia Métodos de pagamento](./media/hr-setup-parameters-payment-methods.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
---
title: Gerar relatórios de Serviços de Saúde Acessíveis no gerenciamento de benefícios
description: Este tópico descreve como o gerenciamento de benefícios ajuda a rastrear informações relatadas no formulário 1095-B e no formulário 1095-C para o mandato de empregador da Lei de Serviços de Saúde Acessíveis (ACA).
author: andreabichsel
manager: tfehr
ms.date: 12/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-12-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 2e4b250f4a059719067a9e19bbf3ce4aecc9bb1f
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "5111528"
---
# <a name="generate-aca-reports-in-benefits-management"></a><span data-ttu-id="4d907-103">Gerar relatórios de ACA no gerenciamento de benefícios</span><span class="sxs-lookup"><span data-stu-id="4d907-103">Generate ACA reports in Benefits management</span></span>

<span data-ttu-id="4d907-104">O gerenciamento de benefícios ajuda a rastrear informações relatadas no formulário 1095-B e no formulário 1095-C para o mandato de empregador da ACA.</span><span class="sxs-lookup"><span data-stu-id="4d907-104">Benefits management helps you track information that is reported on Form 1095-B and Form 1095-C for the Affordable Care Act (ACA) employer mandate.</span></span> <span data-ttu-id="4d907-105">Como o recurso de relatório da ACA no espaço de trabalho **Benefícios** anterior, essa funcionalidade se aplica somente a entidades legais nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="4d907-105">Like the ACA reporting capability in the old **Benefits** workspace, this functionality applies only to legal entities in the United States.</span></span>

<span data-ttu-id="4d907-106">Para usar essa funcionalidade, você deve primeiro ativar o **Gerenciamento Avançado de Benefícios**.</span><span class="sxs-lookup"><span data-stu-id="4d907-106">To use this functionality, you must first turn on **Advanced Benefits Management**.</span></span> <span data-ttu-id="4d907-107">Para obter mais informações, incluindo advertências importantes sobre o gerenciamento de benefícios, consulte [Habilitar ou desabilitar o gerenciamento de benefícios](hr-admin-manage-features.md#enable-or-disable-benefits-management).</span><span class="sxs-lookup"><span data-stu-id="4d907-107">For more information, including important caveats about Benefits management, see [Enable or disable Benefits management](hr-admin-manage-features.md#enable-or-disable-benefits-management).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4d907-108">Você pode usar o relatório da ACA somente no espaço de trabalho de **Gerenciamento de benefícios** ou no espaço de trabalho de **Benefícios** antigo, não em ambos.</span><span class="sxs-lookup"><span data-stu-id="4d907-108">You can use ACA reporting only from either the **Benefits management** workspace or the old **Benefits** workspace, not from both.</span></span> <span data-ttu-id="4d907-109">Por exemplo, se você alternou para o gerenciamento de benefícios, o relatório da ACA estará disponível somente no espaço de trabalho **Gerenciamento de benefícios** e não no espaço de trabalho de **Benefícios** antigo.</span><span class="sxs-lookup"><span data-stu-id="4d907-109">For example, if you switched to Benefits management, ACA reporting is available only from the **Benefits management** workspace, not from the old **Benefits** workspace.</span></span>
>
> <span data-ttu-id="4d907-110">Se você alternar para o gerenciamento de benefícios no meio de um ano de inscrição, deverá configurar corretamente dados do funcionário para o ano inteiro no gerenciamento de benefícios.</span><span class="sxs-lookup"><span data-stu-id="4d907-110">If you switch to Benefits management in the middle of an enrollment year, you must correctly configure employee data for the whole year in Benefits management.</span></span> <span data-ttu-id="4d907-111">Dessa forma, você garante que receberá informações precisas sobre relatórios de todo o ano.</span><span class="sxs-lookup"><span data-stu-id="4d907-111">In this way, you ensure that you will receive accurate reporting information for the whole year.</span></span>

## <a name="getting-started"></a><span data-ttu-id="4d907-112">Introdução</span><span class="sxs-lookup"><span data-stu-id="4d907-112">Getting started</span></span>

<span data-ttu-id="4d907-113">Para rastrear informações de formulários 1095, primeiro crie um ou mais grupos de cobertura de Serviços de Saúde Acessíveis.</span><span class="sxs-lookup"><span data-stu-id="4d907-113">To track information for 1095 forms, first create one or more Affordable Care coverage groups.</span></span> <span data-ttu-id="4d907-114">Esses grupos indicam as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="4d907-114">These groups indicate the following information:</span></span>

- <span data-ttu-id="4d907-115">A oferta de cobertura que foi fornecida a um funcionário</span><span class="sxs-lookup"><span data-stu-id="4d907-115">The offer of coverage that was provided to an employee</span></span>
- <span data-ttu-id="4d907-116">A participação do funcionário com prêmio mensal de menor custo se o custo estiver acima da linha de pobreza estabelecida pelo governo</span><span class="sxs-lookup"><span data-stu-id="4d907-116">The employee's share of the lowest-cost monthly premium, if the cost is above the federal poverty line</span></span>
- <span data-ttu-id="4d907-117">O safe harbor que é usado pelo empregador, se aplicável</span><span class="sxs-lookup"><span data-stu-id="4d907-117">The safe harbor that is used by the employer, if applicable</span></span>

<span data-ttu-id="4d907-118">Os grupos de cobertura de Serviços de Saúde Acessíveis ajudam você a gerenciar essas informações para vários registros de funcionários que têm as mesmas condições.</span><span class="sxs-lookup"><span data-stu-id="4d907-118">Affordable Care coverage groups help you manage this information for multiple employee records that have the same conditions.</span></span> <span data-ttu-id="4d907-119">Você facilmente pode atribuir grupos a um ou mais funcionários.</span><span class="sxs-lookup"><span data-stu-id="4d907-119">You can easily assign groups to one or more employees.</span></span>

### <a name="create-or-edit-an-affordable-care-coverage-group"></a><span data-ttu-id="4d907-120">Criar ou editar um grupo de cobertura de Serviços de Saúde Acessíveis</span><span class="sxs-lookup"><span data-stu-id="4d907-120">Create or edit an Affordable Care coverage group</span></span>

1. <span data-ttu-id="4d907-121">No espaço de trabalho **Gerenciamento de benefícios**, selecione **grupo de cobertura de Serviços de Saúde Acessíveis**.</span><span class="sxs-lookup"><span data-stu-id="4d907-121">In the **Benefits management** workspace, select **Affordable Care coverage group**.</span></span>

    ![Selecionar grupo de cobertura de Serviços de Saúde Acessíveis](./media/hr-benefits-management-aca-coverage-group.png)

2. <span data-ttu-id="4d907-123">Selecione **Novo** para criar um novo grupo de cobertura de Serviços de Saúde Acessíveis ou **Editar** para alterar um grupo existente.</span><span class="sxs-lookup"><span data-stu-id="4d907-123">Select **New** to create a new Affordable Care coverage group or **Edit** to change an existing group.</span></span>

    ![Selecionar Novo ou Editar](./media/hr-benefits-management-aca-new.png)

3. <span data-ttu-id="4d907-125">Defina os campos a seguir.</span><span class="sxs-lookup"><span data-stu-id="4d907-125">Set the following fields.</span></span>

    | <span data-ttu-id="4d907-126">Campo</span><span class="sxs-lookup"><span data-stu-id="4d907-126">Field</span></span> | <span data-ttu-id="4d907-127">Descrição</span><span class="sxs-lookup"><span data-stu-id="4d907-127">Description</span></span> |
    |---|---|
    | <span data-ttu-id="4d907-128">Organização</span><span class="sxs-lookup"><span data-stu-id="4d907-128">Name</span></span> | <span data-ttu-id="4d907-129">Insira um nome para o grupo.</span><span class="sxs-lookup"><span data-stu-id="4d907-129">Enter a name for the group.</span></span> |
    | <span data-ttu-id="4d907-130">Descrição</span><span class="sxs-lookup"><span data-stu-id="4d907-130">Description</span></span> | <span data-ttu-id="4d907-131">Insira uma descrição do grupo.</span><span class="sxs-lookup"><span data-stu-id="4d907-131">Enter a description of the group.</span></span> |
    | <span data-ttu-id="4d907-132">Oferta de cobertura</span><span class="sxs-lookup"><span data-stu-id="4d907-132">Offer of coverage</span></span> | <span data-ttu-id="4d907-133">A cobertura oferecida aos funcionários, o cônjuge ou parceiro e dependentes.</span><span class="sxs-lookup"><span data-stu-id="4d907-133">The coverage that is offered to employees, their spouse or partner, and their dependents.</span></span> |
    | <span data-ttu-id="4d907-134">Cota de custo do funcionário</span><span class="sxs-lookup"><span data-stu-id="4d907-134">Employee share of cost</span></span> | <span data-ttu-id="4d907-135">O valor pelo qual o funcionário é responsável.</span><span class="sxs-lookup"><span data-stu-id="4d907-135">The amount that the employee is responsible for.</span></span> |
    | <span data-ttu-id="4d907-136">Seção 4980H Safe Harbor aplicável</span><span class="sxs-lookup"><span data-stu-id="4d907-136">Applicable section 4980H safe harbor</span></span> | <span data-ttu-id="4d907-137">O código de compensação de transição ou safe harbor do 4980H.</span><span class="sxs-lookup"><span data-stu-id="4d907-137">The 4980H safe harbor or transition relief code.</span></span> |
    | <span data-ttu-id="4d907-138">Mês de início do plano</span><span class="sxs-lookup"><span data-stu-id="4d907-138">Plan start month</span></span> | <span data-ttu-id="4d907-139">Selecione o mês do calendário quando começa o ano do plano de benefícios.</span><span class="sxs-lookup"><span data-stu-id="4d907-139">Select the calendar month when your benefit plan year begins.</span></span> |
    | <span data-ttu-id="4d907-140">Grupo válido desde</span><span class="sxs-lookup"><span data-stu-id="4d907-140">Group valid from</span></span> | <span data-ttu-id="4d907-141">A primeira data em que este registro é válido.</span><span class="sxs-lookup"><span data-stu-id="4d907-141">The first date when this record is valid.</span></span> |
    | <span data-ttu-id="4d907-142">Grupo válido até</span><span class="sxs-lookup"><span data-stu-id="4d907-142">Group valid through</span></span> | <span data-ttu-id="4d907-143">A última data em que este registro é válido.</span><span class="sxs-lookup"><span data-stu-id="4d907-143">The last date when this record is valid.</span></span> <span data-ttu-id="4d907-144">Se não houver data de validade, digite **Nunca**.</span><span class="sxs-lookup"><span data-stu-id="4d907-144">If there is no expiration date, enter **Never**.</span></span> |

    ![Criar um grupo de cobertura](./media/hr-benefits-management-aca-new-group.png)

4. <span data-ttu-id="4d907-146">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="4d907-146">Select **Save**.</span></span>

### <a name="assign-multiple-employees-to-an-affordable-care-coverage-group"></a><span data-ttu-id="4d907-147">Atribuir vários funcionários a um grupo de cobertura de Serviços de Saúde Acessíveis</span><span class="sxs-lookup"><span data-stu-id="4d907-147">Assign multiple employees to an Affordable Care coverage group</span></span>

1. <span data-ttu-id="4d907-148">No espaço de trabalho **Gerenciamento de benefícios**, selecione **grupo de cobertura de Serviços de Saúde Acessíveis**.</span><span class="sxs-lookup"><span data-stu-id="4d907-148">In the **Benefits management** workspace, select **Affordable Care coverage group**.</span></span>
2. <span data-ttu-id="4d907-149">Selecione o grupo ao qual funcionários serão atribuídos.</span><span class="sxs-lookup"><span data-stu-id="4d907-149">Select the group to assign employees to.</span></span>
3. <span data-ttu-id="4d907-150">Selecione **Atribuição em massa**.</span><span class="sxs-lookup"><span data-stu-id="4d907-150">Select **Mass assignment**.</span></span>

    ![Selecionar Atribuição em massa](./media/hr-benefits-management-aca-mass-assignment.png)

4. <span data-ttu-id="4d907-152">Selecione funcionários na lista e, em seguida, **Atribuir**.</span><span class="sxs-lookup"><span data-stu-id="4d907-152">Select employees in the list, and then select **Assign**.</span></span>

    ![Atribuir funcionários selecionados a um grupo](./media/hr-benefits-management-aca-assign-coverage-group.png)

## <a name="maintain-multiple-versions-of-coverage-options"></a><span data-ttu-id="4d907-154">Manter várias versões de opções de cobertura</span><span class="sxs-lookup"><span data-stu-id="4d907-154">Maintain multiple versions of coverage options</span></span>

<span data-ttu-id="4d907-155">Você pode manter várias versões de qualquer grupo de cobertura.</span><span class="sxs-lookup"><span data-stu-id="4d907-155">You can maintain multiple versions of any coverage group.</span></span> <span data-ttu-id="4d907-156">Quando algo é alterado em sua organização ou nos benefícios oferecidos, você pode manter as informações do grupo atualizadas sem precisar criar um novo grupo e reatribuir funcionários a ele.</span><span class="sxs-lookup"><span data-stu-id="4d907-156">When something changes in your organization or the benefits that are offered, you can keep the group's information up to date without having to create a new group and reassign employees to it.</span></span>

<span data-ttu-id="4d907-157">Depois de criar grupos de cobertura de Serviços de Saúde Acessíveis, você pode atribuir funcionários a eles em massa.</span><span class="sxs-lookup"><span data-stu-id="4d907-157">After you've created Affordable Care coverage groups, you can mass-assign employees to them.</span></span> <span data-ttu-id="4d907-158">Você também pode atribuir funcionários a grupos individualmente e indicar se as informações de ACA são rastreadas e relatadas.</span><span class="sxs-lookup"><span data-stu-id="4d907-158">You can also individually assign employees to groups, and indicate whether ACA information is tracked and reported.</span></span>

<span data-ttu-id="4d907-159">Se não for necessário rastrear e relatar informações de ACA de um funcionário, você poderá definir a opção **Cobertura de relatório** como **Não**.</span><span class="sxs-lookup"><span data-stu-id="4d907-159">If you don't have to track and report ACA information for an employee, you can set the **Report coverage** option to **No**.</span></span> <span data-ttu-id="4d907-160">Por exemplo, você pode ter funcionários de meio expediente que não exigem relatórios de ACA.</span><span class="sxs-lookup"><span data-stu-id="4d907-160">For example, you might have part-time employees who don't require ACA reporting.</span></span>

### <a name="override-default-values-for-an-employee"></a><span data-ttu-id="4d907-161">Substituir valores padrão para um funcionário</span><span class="sxs-lookup"><span data-stu-id="4d907-161">Override default values for an employee</span></span>

<span data-ttu-id="4d907-162">Para os funcionários atribuídos a um grupo de cobertura de Serviços de Saúde Acessíveis, você pode alterar as seguintes opções para todos os meses que exigem valores diferentes:</span><span class="sxs-lookup"><span data-stu-id="4d907-162">For employees who are assigned to an Affordable Care coverage group, you can change the following options for any months that require different values:</span></span>

- <span data-ttu-id="4d907-163">Oferta de cobertura</span><span class="sxs-lookup"><span data-stu-id="4d907-163">Offer of coverage</span></span>
- <span data-ttu-id="4d907-164">Cota de custo do funcionário</span><span class="sxs-lookup"><span data-stu-id="4d907-164">Employee share of cost</span></span>
- <span data-ttu-id="4d907-165">Seção 4980H Safe Harbor aplicável</span><span class="sxs-lookup"><span data-stu-id="4d907-165">Applicable section 4980H safe harbor</span></span>

> [!NOTE]
> <span data-ttu-id="4d907-166">Para relatórios de 2020 ACA, você deve relatar os dois CEPs de trabalho e residencial no formulário 1095-C.</span><span class="sxs-lookup"><span data-stu-id="4d907-166">For 2020 ACA reports, you must report both work and home ZIP Codes on Form 1095-C.</span></span> <span data-ttu-id="4d907-167">Os valores são preenchidos automaticamente, com base nos locais ativos atuais.</span><span class="sxs-lookup"><span data-stu-id="4d907-167">Values are automatically filled in, based on current active locations.</span></span> <span data-ttu-id="4d907-168">Se um local for diferente durante parte do ano, você deverá substituir o valor.</span><span class="sxs-lookup"><span data-stu-id="4d907-168">If either location was different during any part of the year, you must override the value.</span></span> <span data-ttu-id="4d907-169">O campo **CEP** (linha 17) do relatório 1095-C só será preenchido se o código **Oferta de cobertura** contiver **1L** até **1Q**, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="4d907-169">The **ZIP Code** field (line 17) of the 1095-C report is filled in only if the **Offer of coverage** code contains **1L** through **1Q**, as follows:</span></span>
>
> - <span data-ttu-id="4d907-170">**1L, 1M ou 1N:** o CEP de residência principal</span><span class="sxs-lookup"><span data-stu-id="4d907-170">**1L, 1M, or 1N:** The primary residence ZIP Code</span></span>
> - <span data-ttu-id="4d907-171">**1O, 1P, 1Q:** o CEP do trabalho principal</span><span class="sxs-lookup"><span data-stu-id="4d907-171">**1O, 1P, 1Q:** The primary work ZIP Code</span></span>

<span data-ttu-id="4d907-172">Para inserir exceções para valores de um grupo de cobertura de Serviços de Saúde Acessíveis, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="4d907-172">To enter exceptions for any values of an Affordable Care coverage group, follow these steps.</span></span>

1. <span data-ttu-id="4d907-173">No espaço de trabalho **Gerenciamento de pessoal**, selecione **Links** e, depois, **Trabalhadores**.</span><span class="sxs-lookup"><span data-stu-id="4d907-173">In the **Personnel management** workspace, select **Links**, and then select **Workers**.</span></span>
2. <span data-ttu-id="4d907-174">Selecione o funcionário na lista.</span><span class="sxs-lookup"><span data-stu-id="4d907-174">Select the employee in the list.</span></span>
3. <span data-ttu-id="4d907-175">Na guia **Emprego**, na seção **Mais informações**, selecione **Cobertura de Serviços de Saúde Acessíveis**.</span><span class="sxs-lookup"><span data-stu-id="4d907-175">On the **Employment** tab, in the **More information** section, select **Affordable Care coverage**.</span></span>

    ![Alterar opções para um funcionário](./media/hr-benefits-management-aca-change-single-employee.png)

4. <span data-ttu-id="4d907-177">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="4d907-177">Select **Edit**.</span></span>
5. <span data-ttu-id="4d907-178">Para cada mês que exija alterações, marque a caixa de seleção **Substituir padrão** e altere os outros valores, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="4d907-178">For each month that requires changes, select the **Override default** check box, and then change the other values as required.</span></span>

    ![Substituir valores padrão](./media/hr-benefits-management-aca-override-default.png)

6. <span data-ttu-id="4d907-180">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="4d907-180">Select **Save**.</span></span>

## <a name="report-health-care-coverage"></a><span data-ttu-id="4d907-181">Relatar cobertura do plano de saúde</span><span class="sxs-lookup"><span data-stu-id="4d907-181">Report health care coverage</span></span>

<span data-ttu-id="4d907-182">Você deve rastrear qualquer cobertura de plano de saúde autossegurada, patrocinada pelo empregador, para funcionários de tempo integral e meio expediente.</span><span class="sxs-lookup"><span data-stu-id="4d907-182">You must track any employer-sponsored, self-insured health care coverage for full-time and part-time employees.</span></span> <span data-ttu-id="4d907-183">Inclua cada funcionário, junto com os dependentes, no relatório 1095-C para os meses em que foram cobertos.</span><span class="sxs-lookup"><span data-stu-id="4d907-183">Include each employee, together with their dependents, on the 1095-C report for the months when they were covered.</span></span>

<span data-ttu-id="4d907-184">Para indicar se um plano de benefícios deve ser relatado, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="4d907-184">To indicate whether a benefit plan must be reported, follow these steps.</span></span>

1. <span data-ttu-id="4d907-185">No espaço de trabalho **Gerenciamento de benefícios**, selecione **Planos de benefícios**.</span><span class="sxs-lookup"><span data-stu-id="4d907-185">In the **Benefits management** workspace, select **Benefit plans**.</span></span>
2. <span data-ttu-id="4d907-186">Selecione o plano de benefícios a ser relatado.</span><span class="sxs-lookup"><span data-stu-id="4d907-186">Select the benefit plan to report.</span></span>
3. <span data-ttu-id="4d907-187">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="4d907-187">Select **Edit**.</span></span>
4. <span data-ttu-id="4d907-188">Defina a opção **Relatado segundo a Lei de Serviços de Saúde Acessíveis** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="4d907-188">Set the **Reported under the Affordable Care Act** option to **Yes**.</span></span>

    ![Relatórios de cobertura do plano de saúde](./media/hr-benefits-management-aca-report-coverage.png)

5. <span data-ttu-id="4d907-190">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="4d907-190">Select **Save**.</span></span>

<span data-ttu-id="4d907-191">Se um funcionário escolher a cobertura de plano de saúde para um dependente, o período de cobertura do dependente será determinado pela data em que o dependente foi inscrito ou removido.</span><span class="sxs-lookup"><span data-stu-id="4d907-191">If an employee chooses health care coverage for a dependent, the dependent's coverage period is determined by the date when the dependent was enrolled or removed.</span></span> <span data-ttu-id="4d907-192">As datas de cobertura para os dependentes são calculadas automaticamente com base no período em que o dependente estava qualificado e ativo em um plano durante o ano de inscrição.</span><span class="sxs-lookup"><span data-stu-id="4d907-192">Coverage dates for dependents are automatically calculated based on the period when the dependent was eligible and active in a plan during the enrollment year.</span></span>

## <a name="generate-1095-b-and-1095-c-forms"></a><span data-ttu-id="4d907-193">Gerar formulários 1095-B e 1095-C</span><span class="sxs-lookup"><span data-stu-id="4d907-193">Generate 1095-B and 1095-C forms</span></span>

<span data-ttu-id="4d907-194">Você pode gerar formulários 1095-B e 1095-C da ACA e distribuí-los a cada um dos funcionários.</span><span class="sxs-lookup"><span data-stu-id="4d907-194">You can generate ACA 1095-B and 1095-C forms, and then distribute them to each of your employees.</span></span> <span data-ttu-id="4d907-195">Você também pode gerar eletronicamente o formulário 1095-C e os arquivos de transmissão 1094-C correspondentes para enviar ao Serviço da Receita Federal (IRS).</span><span class="sxs-lookup"><span data-stu-id="4d907-195">You can also electronically generate Form 1095-C and the corresponding 1094-C transmittal files to send to the Internal Revenue Service (IRS).</span></span>

1. <span data-ttu-id="4d907-196">No espaço de trabalho **Gerenciamento de benefícios**, selecione **Formulário 1095-B da ACA** ou **Formulário 1095-C da ACA**.</span><span class="sxs-lookup"><span data-stu-id="4d907-196">In the **Benefits management** workspace, select **ACA 1095-B form** or **ACA 1095-C form**.</span></span>
2. <span data-ttu-id="4d907-197">Altere os parâmetros conforme necessário e, depois, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="4d907-197">Change the parameters as required, and then select **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4d907-198">Se você estiver imprimindo formulários 1095-C para mais de 500 funcionários, receberá mais de um arquivo PDF.</span><span class="sxs-lookup"><span data-stu-id="4d907-198">If you're printing 1095-C forms for more than 500 employees, you will receive more than one PDF file.</span></span> <span data-ttu-id="4d907-199">É recomendável aumentar o valor do campo **Tamanho máximo de arquivo em megabytes** na página **Parâmetros de gerenciamento de documentos** para **150**.</span><span class="sxs-lookup"><span data-stu-id="4d907-199">We recommend that you increase the value of the **Maximum file size in megabytes** field on the **Document management parameters** page to **150**.</span></span> <span data-ttu-id="4d907-200">(Para abrir rapidamente essa página, você pode usar o campo de pesquisa na barra de navegação.)</span><span class="sxs-lookup"><span data-stu-id="4d907-200">(To quickly open that page, you can use the search field on the navigation bar.)</span></span>
    >
    > ![Alterar o tamanho máximo do arquivo](./media/hr-benefits-management-aca-maximum-file-size.png)

3. <span data-ttu-id="4d907-202">Para verificar o status dos relatórios e exibi-los, use o campo de pesquisa na barra de navegação para abrir a página **Trabalhos de relatórios eletrônicos**.</span><span class="sxs-lookup"><span data-stu-id="4d907-202">To check the status of your reports and view them, use the search field on the navigation bar to open the **Electronic reporting jobs** page.</span></span>

    ![Pesquisar a página Trabalhos de relatórios eletrônicos](./media/hr-benefits-management-aca-search-electronic-reporting-jobs.png)

4. <span data-ttu-id="4d907-204">Selecione o relatório a ser exibido e, depois, selecione **Mostrar arquivos**.</span><span class="sxs-lookup"><span data-stu-id="4d907-204">Select the report to view, and then select **Show files**.</span></span>

    ![Mostrar arquivos](./media/hr-benefits-management-aca-show-files.png)

5. <span data-ttu-id="4d907-206">Selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="4d907-206">Select **Open**.</span></span>

    ![Abrir um arquivo](./media/hr-benefits-management-aca-open-file.png)

6. <span data-ttu-id="4d907-208">Na barra de notificação que aparece na parte inferior da janela do navegador, abra o arquivo zip e selecione o relatório.</span><span class="sxs-lookup"><span data-stu-id="4d907-208">From the Notification bar that appears at the bottom of the browser window, open the zip file, and then select the report.</span></span> <span data-ttu-id="4d907-209">Você pode exibir ou imprimir o arquivo PDF.</span><span class="sxs-lookup"><span data-stu-id="4d907-209">You can view or print the PDF file.</span></span>

    ![Formulário de exemplo 1095-C](./media/hr-benefits-management-aca-1095-c-form.png)

## <a name="view-aca-coverage-information"></a><span data-ttu-id="4d907-211">Exibir informações de cobertura de ACA</span><span class="sxs-lookup"><span data-stu-id="4d907-211">View ACA coverage information</span></span>

<span data-ttu-id="4d907-212">A página **Cobertura de Serviços de Saúde Acessíveis do Trabalhador** mostra as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="4d907-212">The **Worker Affordable Care coverage** page shows the following information:</span></span>

- <span data-ttu-id="4d907-213">Funcionários atribuídos a cada grupo de cobertura</span><span class="sxs-lookup"><span data-stu-id="4d907-213">Employees who are assigned to each coverage group</span></span>
- <span data-ttu-id="4d907-214">Funcionários que não precisam ser incluídos em um relatório</span><span class="sxs-lookup"><span data-stu-id="4d907-214">Employees who don't have to be included on a report</span></span>
- <span data-ttu-id="4d907-215">Funcionários não atribuídos</span><span class="sxs-lookup"><span data-stu-id="4d907-215">Unassigned employees</span></span>

<span data-ttu-id="4d907-216">Para exibir estas informações, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="4d907-216">To view this information, follow these steps.</span></span>

1. <span data-ttu-id="4d907-217">No espaço de trabalho **Gerenciamento de benefícios**, selecione **Cobertura de Serviços de Saúde Acessíveis do Trabalhador**.</span><span class="sxs-lookup"><span data-stu-id="4d907-217">In the **Benefits management** workspace, select **Worker Affordable Care coverage**.</span></span>
2. <span data-ttu-id="4d907-218">No campo **Nome do grupo**, selecione um grupo.</span><span class="sxs-lookup"><span data-stu-id="4d907-218">In the **Group name** field, select a group.</span></span>

    ![Exibir cobertura de ACA](./media/hr-benefits-management-aca-view-coverage.png)

<span data-ttu-id="4d907-220">Se algum dos valores padrão do grupo de cobertura de Serviços de Saúde Acessíveis for substituído, um asterisco aparecerá ao lado do valor que foi alterado.</span><span class="sxs-lookup"><span data-stu-id="4d907-220">If any default values from the Affordable Care coverage group have been overridden, an asterisk appears next to the value that was changed.</span></span> <span data-ttu-id="4d907-221">Se os valores para todos os 12 meses forem iguais e não tiverem sido substituídos, o valor aparecerá na coluna **Todos os 12 meses**.</span><span class="sxs-lookup"><span data-stu-id="4d907-221">If the values for all 12 months are the same and haven't been overridden, the value appears in the **All 12 months** column.</span></span>

<span data-ttu-id="4d907-222">Você pode exibir funcionários que estão marcados como Não pode ser relatado segundo a ACA e que não precisarão de um formulário 1095-C.</span><span class="sxs-lookup"><span data-stu-id="4d907-222">You can view employees who are marked as not ACA-reportable, and who won't require a Form 1095-C.</span></span> <span data-ttu-id="4d907-223">No campo **Filtrar por**, selecione **Não pode ser relatado segundo a ACA**.</span><span class="sxs-lookup"><span data-stu-id="4d907-223">In the **Filter by** field, select **Not ACA reportable**.</span></span>

<span data-ttu-id="4d907-224">Você pode exibir funcionários que não estão atribuídos a um grupo ou que estão atribuídos a um grupo expirado.</span><span class="sxs-lookup"><span data-stu-id="4d907-224">You can view employees who aren't assigned to a group, or who are assigned to an expired group.</span></span> <span data-ttu-id="4d907-225">No campo **Filtrar por**, selecione **Grupo não atribuído ou vencido**.</span><span class="sxs-lookup"><span data-stu-id="4d907-225">In the **Filter by** field, select **Unassigned or expired group**.</span></span>

### <a name="export-to-excel"></a><span data-ttu-id="4d907-226">Exportar para Excel</span><span class="sxs-lookup"><span data-stu-id="4d907-226">Export to Excel</span></span>

<span data-ttu-id="4d907-227">Para exportar uma das listas para o Microsoft Excel, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="4d907-227">To export any of the lists to Microsoft Excel, follow these steps.</span></span>

1. <span data-ttu-id="4d907-228">Selecione o botão **Abrir no Microsoft Office**.</span><span class="sxs-lookup"><span data-stu-id="4d907-228">Select the **Open in Microsoft Office** button.</span></span>
2. <span data-ttu-id="4d907-229">Selecione **Tabela temporária de HCM do Human Resources para uso interno**.</span><span class="sxs-lookup"><span data-stu-id="4d907-229">Select **HCM Human Resources temporary table for internal use**.</span></span>
3. <span data-ttu-id="4d907-230">Selecione **Baixar**.</span><span class="sxs-lookup"><span data-stu-id="4d907-230">Select **Download**.</span></span>

### <a name="view-aca-reportable-dependents"></a><span data-ttu-id="4d907-231">Exibir dependentes relatados segundo a ACA</span><span class="sxs-lookup"><span data-stu-id="4d907-231">View ACA-reportable dependents</span></span>

<span data-ttu-id="4d907-232">Se você precisar relatar as pessoas cobertas porque fornece cobertura autossegurada, poderá exibir os dependentes que são cobertos por planos de benefícios marcados como **Pode ser relatado segundo a ACA**.</span><span class="sxs-lookup"><span data-stu-id="4d907-232">If you must report covered individuals because you provide self-insured coverage, you can view dependents who are covered under benefit plans that are marked as **ACA reportable**.</span></span> <span data-ttu-id="4d907-233">No Painel de Ações, selecione **Exibir Cobertura de Dependentes**.</span><span class="sxs-lookup"><span data-stu-id="4d907-233">On the Action Pane, select **View Dependent coverage**.</span></span>

![Exibir cobertura de dependente](./media/hr-benefits-management-aca-view-dependent-coverage.png)

<span data-ttu-id="4d907-235">As informações de cobertura dos dependentes do funcionário são mostradas.</span><span class="sxs-lookup"><span data-stu-id="4d907-235">Coverage information for the employee's dependents is shown.</span></span>

![Cobertura de dependente](./media/hr-benefits-management-aca-dependents.png)

> [!NOTE]
> <span data-ttu-id="4d907-237">A página mostra somente os planos de benefícios marcados como **Pode ser relatado segundo a ACA**.</span><span class="sxs-lookup"><span data-stu-id="4d907-237">The page shows only benefits plans that are marked as **ACA reportable**.</span></span>

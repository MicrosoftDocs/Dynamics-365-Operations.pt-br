---
title: Gerar relatórios segundo o Affordable Care Act (ACA)
description: Relatórios de Affordable Care Act (ACA - Lei de Serviços de Saúde Acessíveis) gera formulários 1095-B e 1095-C para dar suporte à parte **obrigatória do empregador** do ACA.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
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
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: f46a8efefd8e41c08bf4de49cfec856dc0a86da1
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5468026"
---
# <a name="generate-aca-reports"></a><span data-ttu-id="b4fe0-103">Gerar relatórios ACA</span><span class="sxs-lookup"><span data-stu-id="b4fe0-103">Generate ACA reports</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="b4fe0-104">Relatórios de Affordable Care Act (ACA - Lei de Serviços de Saúde Acessíveis) gera formulários 1095-B e 1095-C para dar suporte à parte **obrigatória do empregador** do ACA.</span><span class="sxs-lookup"><span data-stu-id="b4fe0-104">Affordable Care Act (ACA) reporting generates forms 1095-B and 1095-C in support of the **Employer Mandate** portion of the Affordable Care Act.</span></span>

> [!NOTE]
> <span data-ttu-id="b4fe0-105">O relatório ACA só é habilitado para entidades legais nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="b4fe0-105">ACA reporting is only enabled for legal entities in the United States.</span></span>

## <a name="getting-started"></a><span data-ttu-id="b4fe0-106">Introdução</span><span class="sxs-lookup"><span data-stu-id="b4fe0-106">Getting started</span></span>

<span data-ttu-id="b4fe0-107">Para rastrear informações dos formulários 1095-B e 1095-C, primeiro crie um ou mais grupos de cobertura de Serviços de Saúde Acessíveis.</span><span class="sxs-lookup"><span data-stu-id="b4fe0-107">To track information for forms 1095-B and 1095-C, you must first create one or more Affordable care coverage groups.</span></span> <span data-ttu-id="b4fe0-108">Os grupos de cobertura de Serviços de Saúde Acessíveis indicam:</span><span class="sxs-lookup"><span data-stu-id="b4fe0-108">Affordable Care coverage groups indicate:</span></span>

- <span data-ttu-id="b4fe0-109">A oferta de cobertura para um funcionário</span><span class="sxs-lookup"><span data-stu-id="b4fe0-109">The offer of coverage for an employee</span></span>
- <span data-ttu-id="b4fe0-110">A cota do funcionário com o menor custo mensal se o custo estiver acima da linha de pobreza estabelecida pelo governo</span><span class="sxs-lookup"><span data-stu-id="b4fe0-110">The employee’s share of the lowest cost monthly premium, if the cost is above the federal poverty line</span></span>
- <span data-ttu-id="b4fe0-111">Safe Harbor usado pelo empregador, se aplicável</span><span class="sxs-lookup"><span data-stu-id="b4fe0-111">Safe Harbor used by the employer, if applicable</span></span>

<span data-ttu-id="b4fe0-112">Grupos de cobertura de Serviços de Saúde Acessíveis permitem que você gerencie as informações desses campos sem alterar cada registro de funcionário com as mesmas condições.</span><span class="sxs-lookup"><span data-stu-id="b4fe0-112">Affordable Care coverage groups allow you to manage the information for these fields without changing every employee record where the conditions are the same.</span></span> <span data-ttu-id="b4fe0-113">Você pode facilmente atribuir grupos de cobertura de Serviços de Saúde Acessíveis a um ou mais funcionários, utilizando a opção de **Atribuição em massa** na página.</span><span class="sxs-lookup"><span data-stu-id="b4fe0-113">You can easily assign Affordable Care coverage groups to one or more employees by using the **Mass assign** option on the page.</span></span>

## <a name="maintaining-multiple-versions-of-a-coverage-group"></a><span data-ttu-id="b4fe0-114">Manter várias versões de um grupo de cobertura</span><span class="sxs-lookup"><span data-stu-id="b4fe0-114">Maintaining multiple versions of a coverage group</span></span>

<span data-ttu-id="b4fe0-115">Você pode manter várias versões de qualquer grupo de cobertura.</span><span class="sxs-lookup"><span data-stu-id="b4fe0-115">You can maintain multiple versions of any coverage group.</span></span> <span data-ttu-id="b4fe0-116">Essa funcionalidade permite fazer alterações sem precisar criar um novo grupo e reatribuir funcionários a ele.</span><span class="sxs-lookup"><span data-stu-id="b4fe0-116">This functionality allows you to make changes without having to create a new group and reassign employees to it.</span></span> 

<span data-ttu-id="b4fe0-117">Depois de criar grupos de cobertura de ACA, você pode atribuir os grupos em massa a funcionários com a opção **Atribuição em massa**.</span><span class="sxs-lookup"><span data-stu-id="b4fe0-117">After you’ve created ACA coverage groups, you can mass assign the groups to employees with the **Mass assignment** option.</span></span> <span data-ttu-id="b4fe0-118">Você também pode indicar individualmente se deseja rastrear e relatar informações de ACA e atribuir um funcionário a um grupo de cobertura de Serviços de Saúde Acessíveis.</span><span class="sxs-lookup"><span data-stu-id="b4fe0-118">You can also individually indicate whether to track and report ACA information, and assign an employee to an Affordable Care coverage group.</span></span>

<span data-ttu-id="b4fe0-119">Não é necessário rastrear algumas informações de cobertura de ACA, por exemplo, para funcionários de meio expediente.</span><span class="sxs-lookup"><span data-stu-id="b4fe0-119">You don't need to track some ACA coverage information, such as for part-time employees.</span></span> <span data-ttu-id="b4fe0-120">Nesse caso, defina o campo **Cobertura do relatório** como **Não**.</span><span class="sxs-lookup"><span data-stu-id="b4fe0-120">In this case, set the **Report coverage** field to **No**.</span></span> <span data-ttu-id="b4fe0-121">Embora seja necessário atribuir a cada funcionário com informações de ACA rastreáveis um grupo de cobertura de Serviços de Saúde Acessíveis, você ainda pode alterar as seguintes opções para meses com valores diferentes:</span><span class="sxs-lookup"><span data-stu-id="b4fe0-121">Although you must assign each employee with trackable ACA information to an Affordable Care coverage group, you can still change the following options for months with different values:</span></span>

- <span data-ttu-id="b4fe0-122">**Oferta de cobertura**</span><span class="sxs-lookup"><span data-stu-id="b4fe0-122">**Offer of coverage**</span></span>
- <span data-ttu-id="b4fe0-123">**Cota de custo do funcionário**</span><span class="sxs-lookup"><span data-stu-id="b4fe0-123">**Employee share of cost**</span></span>
- <span data-ttu-id="b4fe0-124">**Safe Harbor**</span><span class="sxs-lookup"><span data-stu-id="b4fe0-124">**Safe Harbor**</span></span>

<span data-ttu-id="b4fe0-125">Para inserir exceções para valores do grupo de cobertura de Serviços de Saúde Acessíveis, selecione o link de **Cobertura de Serviços de Saúde Acessíveis** na página **Detalhes do trabalhador** na seção **Informações adicionais** na guia **Emprego**.</span><span class="sxs-lookup"><span data-stu-id="b4fe0-125">To enter exceptions for Affordable Care coverage group values, select the **Affordable Care Coverage** link on the **Worker detail** page under the **Additional information** section on the **Employment tab**.</span></span>

## <a name="reporting-health-care-coverage"></a><span data-ttu-id="b4fe0-126">Relatórios de cobertura do plano de saúde</span><span class="sxs-lookup"><span data-stu-id="b4fe0-126">Reporting health care coverage</span></span>

<span data-ttu-id="b4fe0-127">Além de rastrear se uma cobertura de plano de saúde oferecida a funcionários de tempo integral, se o empregador oferecer cobertura de saúde auto-segurada e patrocinada pelo empregador, na qual o funcionário esteja matriculado (independentemente do status de emprego ser tempo integral ou meio expediente), informações adicionais precisam ser relatadas no 1095-C.</span><span class="sxs-lookup"><span data-stu-id="b4fe0-127">In addition to tracking health insurance coverage offered to full-time employees, if the employer offers employer-sponsored self-insured health coverage for which the employee is enrolled (regardless of whether their employment status is full-time or part-time), additional information needs to be reported on the 1095-C.</span></span> <span data-ttu-id="b4fe0-128">Cada empregado (incluindo dependentes) coberto pelos planos de benefícios patrocinados pelo empregador deve ser incluído no relatório pelos meses em que esteve coberto.</span><span class="sxs-lookup"><span data-stu-id="b4fe0-128">Each employee (including dependents) covered by the employer-sponsored benefit plans needs to be included on the report for the months they were covered.</span></span> 

<span data-ttu-id="b4fe0-129">Você pode indicar se o plano de benefícios deve ou não ser relatado marcando a caixa de seleção **Pode ser relatado segundo a ACA**.</span><span class="sxs-lookup"><span data-stu-id="b4fe0-129">You can indicate whether or not each benefit plan must be reported by selecting the **ACA reportable** check box.</span></span>

<span data-ttu-id="b4fe0-130">Além disso, se os funcionários optarem por ter qualquer um dos dependentes cobertos por um benefício, você poderá indicar as datas em que o dependente foi coberto, referente a cada funcionário, na página **Manter benefícios**.</span><span class="sxs-lookup"><span data-stu-id="b4fe0-130">In addition, if employees have chosen to have any of their dependents covered under a benefit, you can indicate the dates the dependent was covered for each employee on the **Maintain benefits** page.</span></span> <span data-ttu-id="b4fe0-131">Para indicar que o dependente está coberto pelo benefício, selecione o botão **Editar** no painel de ações da FastTab **Dependentes**.</span><span class="sxs-lookup"><span data-stu-id="b4fe0-131">To indicate that the dependent is covered under the benefit, select the **Edit** button in the action pane of the **Dependents** fast tab.</span></span>

<span data-ttu-id="b4fe0-132">Na página **Gerenciador de data de cobertura de dependentes**, você pode indicar as datas em que o dependente foi coberto pelo benefício.</span><span class="sxs-lookup"><span data-stu-id="b4fe0-132">On the **Dependent coverage date manager** page, you can indicate the dates the dependent was covered by the benefit.</span></span> <span data-ttu-id="b4fe0-133">Inserir datas nessa página selecionará automaticamente a caixa de seleção **Coberto** na página **Manter benefícios**.</span><span class="sxs-lookup"><span data-stu-id="b4fe0-133">Entering dates on this page will automatically select the **Covered** checkbox on the **Maintain benefits** page.</span></span>

## <a name="generate-1095-b-and-1095-c-forms"></a><span data-ttu-id="b4fe0-134">Gerar formulários 1095-B e 1095-C</span><span class="sxs-lookup"><span data-stu-id="b4fe0-134">Generate 1095-B and 1095-C forms</span></span>

<span data-ttu-id="b4fe0-135">Você pode também gerar formulários 1095-B e 1095-C no produto e distribuí-los a cada um dos funcionários.</span><span class="sxs-lookup"><span data-stu-id="b4fe0-135">You can also generate 1095-B and 1095-C forms from within the product, and distribute them to each of your employees.</span></span> <span data-ttu-id="b4fe0-136">O sistema também pode gerar eletronicamente formulários 1095-C e os arquivos de transmissão IRS 1094-C.</span><span class="sxs-lookup"><span data-stu-id="b4fe0-136">The system can also electronically generate 1095-C forms and the 1094-C IRS transmittal files.</span></span>  

<span data-ttu-id="b4fe0-137">Ao gerar o formulário1095-C, insira o ano fiscal adequado e indique se os números de seguro social devem ser mascarados.</span><span class="sxs-lookup"><span data-stu-id="b4fe0-137">When generating the 1095-C form, enter the appropriate tax year and indicate if social security numbers should be masked.</span></span> <span data-ttu-id="b4fe0-138">Se você estiver imprimindo formulários 1095-C para mais de 500 funcionários, receberá mais de um arquivo PDF.</span><span class="sxs-lookup"><span data-stu-id="b4fe0-138">If you're printing 1095-C forms for more than 500 employees, you'll receive more than one PDF file.</span></span> <span data-ttu-id="b4fe0-139">É recomendável aumentar o **Tamanho máximo do arquivo** na janela **Parâmetros de gerenciamento de documentos** para 150 MB.</span><span class="sxs-lookup"><span data-stu-id="b4fe0-139">It’s recommended that you increase the **Maximum file size** in the **Document management parameters** window to 150 MB.</span></span>

## <a name="viewing-information"></a><span data-ttu-id="b4fe0-140">Visualizando informações</span><span class="sxs-lookup"><span data-stu-id="b4fe0-140">Viewing information</span></span>

<span data-ttu-id="b4fe0-141">Você pode usar a página **Cobertura de Serviços de Saúde Acessíveis do Trabalhador** para visualizar os funcionários que foram atribuídos a cada grupo de cobertura, os funcionários que não precisam ser incluídos em um relatório, e os funcionários que não foram atribuídos.</span><span class="sxs-lookup"><span data-stu-id="b4fe0-141">You can use the **Worker Affordable Care coverage** page to see which employees have been assigned to each coverage group, which employees don’t need to be included on a report, and which employees are unassigned.</span></span>

<span data-ttu-id="b4fe0-142">Se algum dos valores padrão do grupo de cobertura de Serviços de Saúde Acessíveis tiver sido substituído, um asterisco aparecerá ao lado do valor que foi alterado.</span><span class="sxs-lookup"><span data-stu-id="b4fe0-142">If any of the default values from the Affordable Care coverage group have been overridden, an asterisk will appear next to the value that was changed.</span></span> <span data-ttu-id="b4fe0-143">Se os valores para todos os 12 meses forem iguais e não tiverem sido substituídos, o valor será impresso na coluna **Todos os 12 meses**.</span><span class="sxs-lookup"><span data-stu-id="b4fe0-143">If the values for all 12 months are the same and haven’t been overridden, the value will print in the **All 12 months** column.</span></span>

<span data-ttu-id="b4fe0-144">Você também pode usar a janela de consulta para saber quais funcionários foram sinalizados como Não pode ser relatado segundo a ACA.</span><span class="sxs-lookup"><span data-stu-id="b4fe0-144">You can also use the inquiry window to understand which employees have been flagged as not ACA reportable.</span></span> <span data-ttu-id="b4fe0-145">Não é necessário rastrear se a cobertura foi oferecida a eles e nem emitir um 1095-C no final do ano.</span><span class="sxs-lookup"><span data-stu-id="b4fe0-145">You don’t need to track whether coverage was offered to them and won't need to issue a 1095-C to them at the end of the year.</span></span> <span data-ttu-id="b4fe0-146">Selecione **Não pode ser relatado segundo a ACA** no campo **Filtrar por** para gerar uma lista de todos os funcionários que não receberão um 1095-C.</span><span class="sxs-lookup"><span data-stu-id="b4fe0-146">Select **Not ACA reportable** in the **Filter by** field to generate a list of all employees who won't receive a 1095-C.</span></span>

<span data-ttu-id="b4fe0-147">Além disso, você pode exibir uma lista de funcionários que não foram atribuídos (o campo **Cobertura de relatório da ACA** está vazio) ou que foram atribuídos a um grupo de cobertura de Serviços de Saúde Acessíveis que expirou no ano selecionado no campo **Ano**.</span><span class="sxs-lookup"><span data-stu-id="b4fe0-147">In addition, you can view any employees who are unassigned (the **ACA Report coverage** field is empty) or who have been assigned to an Affordable Care coverage group that is expired for the year selected in the **Year** field.</span></span>

<span data-ttu-id="b4fe0-148">Você pode exportar listas de funcionários que foram geradas usando qualquer uma das opções de filtragem para o Excel.</span><span class="sxs-lookup"><span data-stu-id="b4fe0-148">You can export lists of employees that were generated using any of the filtering options to Excel.</span></span>

<span data-ttu-id="b4fe0-149">Se você precisar relatar as pessoas cobertas porque fornece cobertura auto-segurada, poderá exibir os dependentes cobertos por planos de benefícios marcados como **Pode ser relatado segundo a ACA**.</span><span class="sxs-lookup"><span data-stu-id="b4fe0-149">If you need to report covered individuals because you provide self-insured coverage, you can view any dependents covered under benefit plans marked as **ACA reportable**.</span></span> <span data-ttu-id="b4fe0-150">Selecione **Exibir Cobertura de Dependentes** no painel de ações.</span><span class="sxs-lookup"><span data-stu-id="b4fe0-150">Select **View Dependent coverage** on the action pane.</span></span>

> [!NOTE]
> <span data-ttu-id="b4fe0-151">Somente planos de benefícios marcados como **Pode ser relatado segundo a ACA** são exibidos na janela de consulta.</span><span class="sxs-lookup"><span data-stu-id="b4fe0-151">Only benefit plans marked as **ACA reportable** display in the inquiry window.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
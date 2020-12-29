---
title: Entrada e navegação simplificada de funcionário
description: A entrada de dados para trabalhadores no Dynamics 365 Talent foi aprimorada para permitir entrada rápida para todos os funcionários, do passado, ativos ou futuros. Um modelo de navegação simplificado/consolidado foi atualizado para localizar rapidamente as informações relacionadas e exibir e fazer as atualizações necessárias.
author: andreabichsel
manager: AnnBe
ms.date: 08/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 15681
ms.assetid: 6aee97ac-29f7-4b3c-8aa1-c65810de3090
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent October 2019 update
ms.openlocfilehash: b73b420c2eb75077814fbfeb6cd17404c7efc11e
ms.sourcegitcommit: 436731d8b3889bebfe6f17922b0a31b1994f6796
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/26/2020
ms.locfileid: "4460390"
---
# <a name="streamlined-employee-entry-and-navigation"></a><span data-ttu-id="a692e-104">Entrada e navegação simplificada de funcionário</span><span class="sxs-lookup"><span data-stu-id="a692e-104">Streamlined employee entry and navigation</span></span>

<span data-ttu-id="a692e-105">O Dynamics 365 Talent permite a entrada eficiente do funcionário e dos dados de emprego.</span><span class="sxs-lookup"><span data-stu-id="a692e-105">Dynamics 365 Talent allows efficient entry of employee and employment data.</span></span> <span data-ttu-id="a692e-106">Você pode atualizar rapidamente as informações de histórico de trabalho para funcionários e prestadores de serviço do passado, ativos e futuros.</span><span class="sxs-lookup"><span data-stu-id="a692e-106">You can quickly update work history information for past, active, and future employees and contractors.</span></span>

<span data-ttu-id="a692e-107">Você também pode habilitar uma experiência de navegação simplificada para localizar informações relacionadas rapidamente e fazer as alterações necessárias.</span><span class="sxs-lookup"><span data-stu-id="a692e-107">You can also enable a simplified navigation experience to quickly find related information and make any necessary changes.</span></span> <span data-ttu-id="a692e-108">Agora, esta funcionalidade está disponível em todos os ambientes.</span><span class="sxs-lookup"><span data-stu-id="a692e-108">This functionality is now available in all environments.</span></span> <span data-ttu-id="a692e-109">Para ativar esse recurso, navegue até **Administração do sistema > Gerenciamento de recursos > Novo > Entrada simplificada de funcionário > Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="a692e-109">To turn this feature on, navigate to **System administration > Feature Management > New > Streamlined employee entry > Enable**.</span></span> <span data-ttu-id="a692e-110">Isso habilitará estas alterações para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="a692e-110">This will enable these changes for all users.</span></span> <span data-ttu-id="a692e-111">Você pode desativar esta opção a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="a692e-111">You can turn this option off at any time.</span></span>

## <a name="view-options"></a><span data-ttu-id="a692e-112">Opções de exibição</span><span class="sxs-lookup"><span data-stu-id="a692e-112">View options</span></span>

<span data-ttu-id="a692e-113">Você pode usar **Opções de exibição** no formulário do trabalhador para selecionar qualquer combinação de funcionários ou prestadores de serviço de uma única lista.</span><span class="sxs-lookup"><span data-stu-id="a692e-113">You can use **View options** on the worker form to select any combination of employees and contractors from a single list.</span></span> <span data-ttu-id="a692e-114">Essas opções permitem exibir trabalhadores entre entidades legais ou para a entidade legal na qual você está conectado no momento.</span><span class="sxs-lookup"><span data-stu-id="a692e-114">These options allow you to view workers across legal entities or for the legal entity you're currently signed into.</span></span> <span data-ttu-id="a692e-115">Também é possível exibir trabalhadores ativos, pendentes e demitidos e você pode restringir os resultados com base no tipo de trabalhador (funcionário ou prestador de serviço).</span><span class="sxs-lookup"><span data-stu-id="a692e-115">You can also view active, pending, and exited workers, and you can restrict results based on the type of worker (employee or contractor).</span></span> <span data-ttu-id="a692e-116">Se a segurança avançada estiver habilitada, você verá apenas os funcionários e prestadores de serviços nas entidades legais às quais tem acesso.</span><span class="sxs-lookup"><span data-stu-id="a692e-116">If advanced security is enabled, you will only see those employees and contractors in the legal entities you have access to.</span></span>

<span data-ttu-id="a692e-117">As colunas na exibição de lista são alteradas com base em suas seleções.</span><span class="sxs-lookup"><span data-stu-id="a692e-117">Columns in the list view change based on your selections.</span></span> <span data-ttu-id="a692e-118">Por exemplo, ao exibir funcionários demitidos, a data de demissão e os códigos de motivo são exibidos como colunas adicionais na lista.</span><span class="sxs-lookup"><span data-stu-id="a692e-118">For example, when viewing exited employees, the termination date and reason codes display as additional columns in the list.</span></span> 

<span data-ttu-id="a692e-119">[![Opções de exibição](./media/Worker-view-option.png)](./media/worker-view-option.png)</span><span class="sxs-lookup"><span data-stu-id="a692e-119">[![View options](./media/Worker-view-option.png)](./media/worker-view-option.png)</span></span>

## <a name="navigation-and-banner"></a><span data-ttu-id="a692e-120">Navegação e banner</span><span class="sxs-lookup"><span data-stu-id="a692e-120">Navigation and banner</span></span>

<span data-ttu-id="a692e-121">Uma faixa exibe as informações importantes de cada trabalhador.</span><span class="sxs-lookup"><span data-stu-id="a692e-121">A banner displays key information for each worker.</span></span> <span data-ttu-id="a692e-122">A faixa para trabalhadores ativos exibe os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="a692e-122">The banner for active workers displays the following fields:</span></span>

- <span data-ttu-id="a692e-123">**Cargo**</span><span class="sxs-lookup"><span data-stu-id="a692e-123">**Title**</span></span>
- <span data-ttu-id="a692e-124">**Departamento**</span><span class="sxs-lookup"><span data-stu-id="a692e-124">**Department**</span></span>
- <span data-ttu-id="a692e-125">**Tipo de posição**</span><span class="sxs-lookup"><span data-stu-id="a692e-125">**Position type**</span></span>
- <span data-ttu-id="a692e-126">**Tipo de trabalhador**</span><span class="sxs-lookup"><span data-stu-id="a692e-126">**Worker type**</span></span>
- <span data-ttu-id="a692e-127">**Gerente**</span><span class="sxs-lookup"><span data-stu-id="a692e-127">**Manager**</span></span>
- <span data-ttu-id="a692e-128">**Pessoa jurídica em geral**</span><span class="sxs-lookup"><span data-stu-id="a692e-128">**Legal entity**</span></span>

<span data-ttu-id="a692e-129">A faixa para trabalhadores demitidos exibe os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="a692e-129">The banner for exited workers displays the following fields:</span></span>

- <span data-ttu-id="a692e-130">**Data da saída**</span><span class="sxs-lookup"><span data-stu-id="a692e-130">**Exited date**</span></span>
- <span data-ttu-id="a692e-131">**Motivo**</span><span class="sxs-lookup"><span data-stu-id="a692e-131">**Reason**</span></span>

<span data-ttu-id="a692e-132">A faixa para trabalhadores pendentes exibe os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="a692e-132">The banner for pending employees displays the following fields:</span></span>

- <span data-ttu-id="a692e-133">**Cargo**</span><span class="sxs-lookup"><span data-stu-id="a692e-133">**Title**</span></span>
- <span data-ttu-id="a692e-134">**Departamento**</span><span class="sxs-lookup"><span data-stu-id="a692e-134">**Department**</span></span>
- <span data-ttu-id="a692e-135">**Tipo de posição**</span><span class="sxs-lookup"><span data-stu-id="a692e-135">**Position type**</span></span>
- <span data-ttu-id="a692e-136">**Gerente**</span><span class="sxs-lookup"><span data-stu-id="a692e-136">**Manager**</span></span>
- <span data-ttu-id="a692e-137">**Data inicial**</span><span class="sxs-lookup"><span data-stu-id="a692e-137">**Starting date**</span></span>
- <span data-ttu-id="a692e-138">**Pessoa jurídica em geral**</span><span class="sxs-lookup"><span data-stu-id="a692e-138">**Legal entity**</span></span>

<span data-ttu-id="a692e-139">O painel de ações da página do trabalhador foi reorganizado para incluir menos opções.</span><span class="sxs-lookup"><span data-stu-id="a692e-139">The action pane of the worker page has been re-organized to include fewer options.</span></span> <span data-ttu-id="a692e-140">As informações agora são organizadas nas seguintes categorias:</span><span class="sxs-lookup"><span data-stu-id="a692e-140">Information is now organized in the following categories:</span></span> 

- <span data-ttu-id="a692e-141">Trabalho</span><span class="sxs-lookup"><span data-stu-id="a692e-141">Work</span></span>
- <span data-ttu-id="a692e-142">Pessoa</span><span class="sxs-lookup"><span data-stu-id="a692e-142">Person</span></span>
- <span data-ttu-id="a692e-143">Sair</span><span class="sxs-lookup"><span data-stu-id="a692e-143">Leave</span></span>
- <span data-ttu-id="a692e-144">Remuneração</span><span class="sxs-lookup"><span data-stu-id="a692e-144">Compensation</span></span>
- <span data-ttu-id="a692e-145">Benefícios</span><span class="sxs-lookup"><span data-stu-id="a692e-145">Benefits</span></span>
- <span data-ttu-id="a692e-146">Conformidade</span><span class="sxs-lookup"><span data-stu-id="a692e-146">Compliance</span></span>

<span data-ttu-id="a692e-147">Além disso, uma nova guia **Links** na página principal do trabalhador fornece aos usuários um local central para acessar todas as informações relacionadas a um trabalhador.</span><span class="sxs-lookup"><span data-stu-id="a692e-147">In addition, a new **Links** tab on the main worker page gives users a central location to access all related information for a worker.</span></span>

<span data-ttu-id="a692e-148">Devido a essas alterações, as informações podem aparecer em um local diferente do que você está acostumado.</span><span class="sxs-lookup"><span data-stu-id="a692e-148">Due to these changes, information may appear in a different location than you're used to.</span></span> <span data-ttu-id="a692e-149">Por exemplo, as informações da folha de pagamento exibidas anteriormente no formulário do trabalhador agora aparecem no painel de ações em **Remuneração > Folha de Pagamento** e na guia **Informações Pessoais** agora tem um botão **Mais informações** para ocultar os campos que não são acessados com frequência.</span><span class="sxs-lookup"><span data-stu-id="a692e-149">For example, payroll information that previously displayed on the worker form now appears in the action pane under **Compensation > Payroll**, and the **Personal information** tab now has a **More information** button to hide fields that aren't accessed often.</span></span>

<span data-ttu-id="a692e-150">[![Faixa](./media/Banner.png)](./media/Banner.png)</span><span class="sxs-lookup"><span data-stu-id="a692e-150">[![Banner](./media/Banner.png)](./media/Banner.png)</span></span>

## <a name="work-history"></a><span data-ttu-id="a692e-151">Histórico de trabalho</span><span class="sxs-lookup"><span data-stu-id="a692e-151">Work history</span></span>

<span data-ttu-id="a692e-152">A guia **Histórico de trabalho** mostra o histórico de trabalho de todas as entidades legais e está disponível para funcionários e prestadores de serviço demitidos, ativos e pendentes.</span><span class="sxs-lookup"><span data-stu-id="a692e-152">The **Work history** tab shows work history across all legal entities and is available for exited, active, and pending employees and contractors.</span></span> <span data-ttu-id="a692e-153">Agora você pode visualizar todo o histórico de trabalho de uma só vez para as entidades legais às quais você tem acesso.</span><span class="sxs-lookup"><span data-stu-id="a692e-153">You can now view all work history at once for the legal entities you have access to.</span></span> <span data-ttu-id="a692e-154">Além disso, você pode editar as informações de cada uma das entradas do histórico de trabalho sem alterar o contexto dos dados.</span><span class="sxs-lookup"><span data-stu-id="a692e-154">In addition, you can edit information for each of the work history entries without changing the data context.</span></span> <span data-ttu-id="a692e-155">Você pode atualizar todas as informações diretamente na página.</span><span class="sxs-lookup"><span data-stu-id="a692e-155">You can update all information directly on the page.</span></span> 

<span data-ttu-id="a692e-156">[![Histórico de trabalho](./media/Worker-work-history.png)](./media/Worker-work-history.png)</span><span class="sxs-lookup"><span data-stu-id="a692e-156">[![Work history](./media/Worker-work-history.png)](./media/Worker-work-history.png)</span></span>

## <a name="position-history"></a><span data-ttu-id="a692e-157">Histórico de cargos</span><span class="sxs-lookup"><span data-stu-id="a692e-157">Position history</span></span>

<span data-ttu-id="a692e-158">A guia **Cargos**, na página principal do trabalhador, fornece uma visão completa de todos os cargos ocupados na organização, incluindo atribuições passadas, presentes e futuras.</span><span class="sxs-lookup"><span data-stu-id="a692e-158">The **Positions** tab on the main worker page provides a full view of all positions held within the organization, including past, present, and any future assignments.</span></span> <span data-ttu-id="a692e-159">Você ainda pode navegar diretamente para o histórico de cargos do trabalhador no painel de ações.</span><span class="sxs-lookup"><span data-stu-id="a692e-159">You can still navigate directly to the worker's position history in the action pane as well.</span></span>

<span data-ttu-id="a692e-160">[![Cargos](./media/Worker-position-history.png)](./media/Worker-position-history.png)</span><span class="sxs-lookup"><span data-stu-id="a692e-160">[![Positions](./media/Worker-position-history.png)](./media/Worker-position-history.png)</span></span>


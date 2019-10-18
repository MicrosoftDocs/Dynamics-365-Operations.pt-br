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
ms.openlocfilehash: 40bbb8429355fa18fe12c7cf56f8d58f19766cad
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2019
ms.locfileid: "2009413"
---
# <a name="streamlined-employee-entry-and-navigation"></a><span data-ttu-id="8bdc3-104">Entrada e navegação simplificada de funcionário</span><span class="sxs-lookup"><span data-stu-id="8bdc3-104">Streamlined employee entry and navigation</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8bdc3-105">O Dynamics 365 Talent permite a entrada eficiente do funcionário e dos dados de emprego.</span><span class="sxs-lookup"><span data-stu-id="8bdc3-105">Dynamics 365 Talent allows efficient entry of employee and employment data.</span></span> <span data-ttu-id="8bdc3-106">Você pode atualizar rapidamente as informações de histórico de trabalho para funcionários e prestadores de serviço do passado, ativos e futuros.</span><span class="sxs-lookup"><span data-stu-id="8bdc3-106">You can quickly update work history information for past, active, and future employees and contractors.</span></span>

<span data-ttu-id="8bdc3-107">Você também pode habilitar uma experiência de navegação simplificada para localizar informações relacionadas rapidamente e fazer as alterações necessárias.</span><span class="sxs-lookup"><span data-stu-id="8bdc3-107">You can also enable a simplified navigation experience to quickly find related information and make any necessary changes.</span></span> <span data-ttu-id="8bdc3-108">Esta funcionalidade agora está disponível em ambientes de área restrita.</span><span class="sxs-lookup"><span data-stu-id="8bdc3-108">This functionality is now available in sandbox environments.</span></span> <span data-ttu-id="8bdc3-109">Para ativar este recurso, navegue até **Administração do sistema > Links > Configuração > Parâmetros do sistema > Recursos de visualização**.</span><span class="sxs-lookup"><span data-stu-id="8bdc3-109">To turn this feature on, navigate to **System administration > Links > Setup > System parameters > Preview features**.</span></span> <span data-ttu-id="8bdc3-110">Selecione **Formulário e a navegação aprimorados do Trabalhador**.</span><span class="sxs-lookup"><span data-stu-id="8bdc3-110">Select **Enhanced worker form and navigation**.</span></span> <span data-ttu-id="8bdc3-111">Isso habilitará estas alterações para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="8bdc3-111">This will enable these changes for all users.</span></span> <span data-ttu-id="8bdc3-112">Você pode desativar esta opção a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="8bdc3-112">You can turn this option off at any time.</span></span>

## <a name="view-options"></a><span data-ttu-id="8bdc3-113">Opções de exibição</span><span class="sxs-lookup"><span data-stu-id="8bdc3-113">View options</span></span>

<span data-ttu-id="8bdc3-114">Você pode usar **Opções de exibição** no formulário do trabalhador para selecionar qualquer combinação de funcionários ou prestadores de serviço de uma única lista.</span><span class="sxs-lookup"><span data-stu-id="8bdc3-114">You can use **View options** on the worker form to select any combination of employees and contractors from a single list.</span></span> <span data-ttu-id="8bdc3-115">Essas opções permitem exibir trabalhadores entre entidades legais ou para a entidade legal na qual você está conectado no momento.</span><span class="sxs-lookup"><span data-stu-id="8bdc3-115">These options allow you to view workers across legal entities or for the legal entity you're currently signed into.</span></span> <span data-ttu-id="8bdc3-116">Também é possível exibir trabalhadores ativos, pendentes e demitidos e você pode restringir os resultados com base no tipo de trabalhador (funcionário ou prestador de serviço).</span><span class="sxs-lookup"><span data-stu-id="8bdc3-116">You can also view active, pending, and exited workers, and you can restrict results based on the type of worker (employee or contractor).</span></span> <span data-ttu-id="8bdc3-117">Se a segurança avançada estiver habilitada, você verá apenas os funcionários e prestadores de serviços nas entidades legais às quais tem acesso.</span><span class="sxs-lookup"><span data-stu-id="8bdc3-117">If advanced security is enabled, you will only see those employees and contractors in the legal entities you have access to.</span></span>

<span data-ttu-id="8bdc3-118">As colunas na exibição de lista são alteradas com base em suas seleções.</span><span class="sxs-lookup"><span data-stu-id="8bdc3-118">Columns in the list view change based on your selections.</span></span> <span data-ttu-id="8bdc3-119">Por exemplo, ao exibir funcionários demitidos, a data de demissão e os códigos de motivo são exibidos como colunas adicionais na lista.</span><span class="sxs-lookup"><span data-stu-id="8bdc3-119">For example, when viewing exited employees, the termination date and reason codes display as additional columns in the list.</span></span> 

<span data-ttu-id="8bdc3-120">[![Opções de exibição](./media/Worker-view-option.png)](./media/worker-view-option.png)</span><span class="sxs-lookup"><span data-stu-id="8bdc3-120">[![View options](./media/Worker-view-option.png)](./media/worker-view-option.png)</span></span>

## <a name="navigation-and-banner"></a><span data-ttu-id="8bdc3-121">Navegação e banner</span><span class="sxs-lookup"><span data-stu-id="8bdc3-121">Navigation and banner</span></span>

<span data-ttu-id="8bdc3-122">Uma faixa exibe as informações importantes de cada trabalhador.</span><span class="sxs-lookup"><span data-stu-id="8bdc3-122">A banner displays key information for each worker.</span></span> <span data-ttu-id="8bdc3-123">A faixa para trabalhadores ativos exibe os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="8bdc3-123">The banner for active workers displays the following fields:</span></span>

- <span data-ttu-id="8bdc3-124">**Cargo**</span><span class="sxs-lookup"><span data-stu-id="8bdc3-124">**Title**</span></span>
- <span data-ttu-id="8bdc3-125">**Departamento**</span><span class="sxs-lookup"><span data-stu-id="8bdc3-125">**Department**</span></span>
- <span data-ttu-id="8bdc3-126">**Tipo de posição**</span><span class="sxs-lookup"><span data-stu-id="8bdc3-126">**Position type**</span></span>
- <span data-ttu-id="8bdc3-127">**Tipo de trabalhador**</span><span class="sxs-lookup"><span data-stu-id="8bdc3-127">**Worker type**</span></span>
- <span data-ttu-id="8bdc3-128">**Gerente**</span><span class="sxs-lookup"><span data-stu-id="8bdc3-128">**Manager**</span></span>
- <span data-ttu-id="8bdc3-129">**Pessoa jurídica em geral**</span><span class="sxs-lookup"><span data-stu-id="8bdc3-129">**Legal entity**</span></span>

<span data-ttu-id="8bdc3-130">A faixa para trabalhadores demitidos exibe os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="8bdc3-130">The banner for exited workers displays the following fields:</span></span>

- <span data-ttu-id="8bdc3-131">**Data da saída**</span><span class="sxs-lookup"><span data-stu-id="8bdc3-131">**Exited date**</span></span>
- <span data-ttu-id="8bdc3-132">**Motivo**</span><span class="sxs-lookup"><span data-stu-id="8bdc3-132">**Reason**</span></span>

<span data-ttu-id="8bdc3-133">A faixa para trabalhadores pendentes exibe os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="8bdc3-133">The banner for pending employees displays the following fields:</span></span>

- <span data-ttu-id="8bdc3-134">**Cargo**</span><span class="sxs-lookup"><span data-stu-id="8bdc3-134">**Title**</span></span>
- <span data-ttu-id="8bdc3-135">**Departamento**</span><span class="sxs-lookup"><span data-stu-id="8bdc3-135">**Department**</span></span>
- <span data-ttu-id="8bdc3-136">**Tipo de posição**</span><span class="sxs-lookup"><span data-stu-id="8bdc3-136">**Position type**</span></span>
- <span data-ttu-id="8bdc3-137">**Gerente**</span><span class="sxs-lookup"><span data-stu-id="8bdc3-137">**Manager**</span></span>
- <span data-ttu-id="8bdc3-138">**Data inicial**</span><span class="sxs-lookup"><span data-stu-id="8bdc3-138">**Starting date**</span></span>
- <span data-ttu-id="8bdc3-139">**Pessoa jurídica em geral**</span><span class="sxs-lookup"><span data-stu-id="8bdc3-139">**Legal entity**</span></span>

<span data-ttu-id="8bdc3-140">O painel de ações da página do trabalhador foi reorganizado para incluir menos opções.</span><span class="sxs-lookup"><span data-stu-id="8bdc3-140">The action pane of the worker page has been re-organized to include fewer options.</span></span> <span data-ttu-id="8bdc3-141">As informações agora são organizadas nas seguintes categorias:</span><span class="sxs-lookup"><span data-stu-id="8bdc3-141">Information is now organized in the following categories:</span></span> 

- <span data-ttu-id="8bdc3-142">Trabalho</span><span class="sxs-lookup"><span data-stu-id="8bdc3-142">Work</span></span>
- <span data-ttu-id="8bdc3-143">Pessoa</span><span class="sxs-lookup"><span data-stu-id="8bdc3-143">Person</span></span>
- <span data-ttu-id="8bdc3-144">Deixar</span><span class="sxs-lookup"><span data-stu-id="8bdc3-144">Leave</span></span>
- <span data-ttu-id="8bdc3-145">Remuneração</span><span class="sxs-lookup"><span data-stu-id="8bdc3-145">Compensation</span></span>
- <span data-ttu-id="8bdc3-146">Benefícios</span><span class="sxs-lookup"><span data-stu-id="8bdc3-146">Benefits</span></span>
- <span data-ttu-id="8bdc3-147">Conformidade</span><span class="sxs-lookup"><span data-stu-id="8bdc3-147">Compliance</span></span>

<span data-ttu-id="8bdc3-148">Além disso, uma nova guia **Links** na página principal do trabalhador fornece aos usuários um local central para acessar todas as informações relacionadas a um trabalhador.</span><span class="sxs-lookup"><span data-stu-id="8bdc3-148">In addtion, a new **Links** tab on the main worker page gives users a central location to access all related information for a worker.</span></span>

<span data-ttu-id="8bdc3-149">Devido a essas alterações, as informações podem aparecer em um local diferente do que você está acostumado.</span><span class="sxs-lookup"><span data-stu-id="8bdc3-149">Due to these changes, information may appear in a different location than you're used to.</span></span> <span data-ttu-id="8bdc3-150">Por exemplo, as informações da folha de pagamento exibidas anteriormente no formulário do trabalhador agora aparecem no painel de ações em **Remuneração > Folha de Pagamento** e na guia **Informações Pessoais** agora tem um botão **Mais informações** para ocultar os campos que não são acessados com frequência.</span><span class="sxs-lookup"><span data-stu-id="8bdc3-150">For example, payroll information that previously displayed on the worker form now appears in the action pane under **Compensation > Payroll**, and the **Personal information** tab now has a **More information** button to hide fields that aren't accessed often.</span></span>

<span data-ttu-id="8bdc3-151">[![Faixa](./media/Banner.png)](./media/Banner.png)</span><span class="sxs-lookup"><span data-stu-id="8bdc3-151">[![Banner](./media/Banner.png)](./media/Banner.png)</span></span>

## <a name="work-history"></a><span data-ttu-id="8bdc3-152">Histórico de trabalho</span><span class="sxs-lookup"><span data-stu-id="8bdc3-152">Work history</span></span>

<span data-ttu-id="8bdc3-153">A guia **Histórico de trabalho** mostra o histórico de trabalho de todas as entidades legais e está disponível para funcionários e prestadores de serviço demitidos, ativos e pendentes.</span><span class="sxs-lookup"><span data-stu-id="8bdc3-153">The **Work history** tab shows work history accross all legal entities and is available for exited, active, and pending employees and contractors.</span></span> <span data-ttu-id="8bdc3-154">Agora você pode visualizar todo o histórico de trabalho de uma só vez para as entidades legais às quais você tem acesso.</span><span class="sxs-lookup"><span data-stu-id="8bdc3-154">You can now view all work history at once for the legal entities you have access to.</span></span> <span data-ttu-id="8bdc3-155">Além disso, você pode editar as informações de cada uma das entradas do histórico de trabalho sem alterar o contexto dos dados.</span><span class="sxs-lookup"><span data-stu-id="8bdc3-155">In addition, you can edit information for each of the work history entries without changing the data context.</span></span> <span data-ttu-id="8bdc3-156">Você pode atualizar todas as informações diretamente na página.</span><span class="sxs-lookup"><span data-stu-id="8bdc3-156">You can update all information directly on the page.</span></span> 

<span data-ttu-id="8bdc3-157">[![Histórico de trabalho](./media/Worker-work-history.png)](./media/Worker-work-history.png)</span><span class="sxs-lookup"><span data-stu-id="8bdc3-157">[![Work history](./media/Worker-work-history.png)](./media/Worker-work-history.png)</span></span>

## <a name="position-history"></a><span data-ttu-id="8bdc3-158">Histórico de cargos</span><span class="sxs-lookup"><span data-stu-id="8bdc3-158">Position history</span></span>

<span data-ttu-id="8bdc3-159">A guia **Cargos**, na página principal do trabalhador, fornece uma visão completa de todos os cargos ocupados na organização, incluindo atribuições passadas, presentes e futuras.</span><span class="sxs-lookup"><span data-stu-id="8bdc3-159">The **Positions** tab on the main worker page provides a full view of all positions held within the organization, including past, present, and any future assignments.</span></span> <span data-ttu-id="8bdc3-160">Você ainda pode navegar diretamente para o histórico de cargos do trabalhador no painel de ações.</span><span class="sxs-lookup"><span data-stu-id="8bdc3-160">You can still navigate directly to the worker's position history in the action pane as well.</span></span>

<span data-ttu-id="8bdc3-161">[![Cargos](./media/Worker-position-history.png)](./media/Worker-position-history.png)</span><span class="sxs-lookup"><span data-stu-id="8bdc3-161">[![Positions](./media/Worker-position-history.png)](./media/Worker-position-history.png)</span></span>


---
title: Criar a interface de execução de piso de produção
description: Este tópico descreve como criar o conteúdo da interface do usuário para cada configuração.
author: johanhoffmann
manager: tfehr
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 81c5c83128bb81523dee6ede549eece7b0d80e30
ms.sourcegitcommit: d9d1ddce6a334ade8b32b5ea3ac4c1e1a8f72715
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2020
ms.locfileid: "4664263"
---
# <a name="design-the-production-floor-execution-interface"></a><span data-ttu-id="fa49b-103">Criar a interface de execução de piso de produção</span><span class="sxs-lookup"><span data-stu-id="fa49b-103">Design the production floor execution interface</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="fa49b-104">Você pode criar o conteúdo da interface do usuário para cada configuração usada pela interface de execução de piso de produção.</span><span class="sxs-lookup"><span data-stu-id="fa49b-104">You can design the content of the user interface for each configuration used by the production floor execution interface.</span></span> <span data-ttu-id="fa49b-105">Por exemplo, os trabalhadores em uma célula de trabalho podem precisar abrir instruções de trabalho no piso de produção, enquanto que, em outra célula de trabalho, instruções não são necessárias.</span><span class="sxs-lookup"><span data-stu-id="fa49b-105">For example, workers in one work cell might need to be able to open job instructions on the production floor, while in another work cell, instructions are not needed.</span></span> <span data-ttu-id="fa49b-106">Nesse caso, duas configurações devem ser criadas, uma com um botão para abrir anexos de documentos e uma sem esse botão.</span><span class="sxs-lookup"><span data-stu-id="fa49b-106">In that case, two configurations should be created, one with a button for opening document attachments and one without this button.</span></span>

## <a name="design-a-tab"></a><span data-ttu-id="fa49b-107">Criar uma guia</span><span class="sxs-lookup"><span data-stu-id="fa49b-107">Design a tab</span></span>

<span data-ttu-id="fa49b-108">Na página **Configurar execução de piso de produção**, você pode criar e configurar guias selecionando **Criar guias** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="fa49b-108">On the **Configure production floor execution** page, you can create and configure tabs by selecting **Design tabs** on the Action Pane.</span></span>

<span data-ttu-id="fa49b-109">Cada guia é dividida em quatro seções, conforme mostrado na ilustração a seguir.</span><span class="sxs-lookup"><span data-stu-id="fa49b-109">Each tab is divided into four sections, as shown in the following illustration.</span></span>

<span data-ttu-id="fa49b-110">![Layout da guia](media/pfe-tab-layout.png "Layout da guia")</span><span class="sxs-lookup"><span data-stu-id="fa49b-110">![Tab layout](media/pfe-tab-layout.png "Tab layout")</span></span>

<span data-ttu-id="fa49b-111">Os seguintes elementos são mostrados na ilustração:</span><span class="sxs-lookup"><span data-stu-id="fa49b-111">The following elements are shown in the illustration:</span></span>

1. <span data-ttu-id="fa49b-112">Barra de ferramentas principal</span><span class="sxs-lookup"><span data-stu-id="fa49b-112">Primary toolbar</span></span>
1. <span data-ttu-id="fa49b-113">Barra de ferramentas secundária</span><span class="sxs-lookup"><span data-stu-id="fa49b-113">Secondary toolbar</span></span>
1. <span data-ttu-id="fa49b-114">Exibição principal</span><span class="sxs-lookup"><span data-stu-id="fa49b-114">Main view</span></span>
1. <span data-ttu-id="fa49b-115">Exibição detalhada</span><span class="sxs-lookup"><span data-stu-id="fa49b-115">Detailed view</span></span>

<span data-ttu-id="fa49b-116">Para criar e configurar uma nova guia, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="fa49b-116">To create and configure a new tab, follow these steps:</span></span>

1. <span data-ttu-id="fa49b-117">Vá para **Controle de produção &gt; Configuração &gt; Execução de fabricação**.</span><span class="sxs-lookup"><span data-stu-id="fa49b-117">Go to **Production control &gt; Setup &gt; Manufacturing execution**.</span></span>

1. <span data-ttu-id="fa49b-118">Selecione **Criar guias** no Painel de Ações para abrir a página **Criar guias**.</span><span class="sxs-lookup"><span data-stu-id="fa49b-118">Select **Design tabs** on the Action Pane to open the **Design tabs** page.</span></span>

    <span data-ttu-id="fa49b-119">![A página Criar guias](media/pfe-design-tabs.png "A página Criar guias")</span><span class="sxs-lookup"><span data-stu-id="fa49b-119">![The Design tabs page](media/pfe-design-tabs.png "The Design tabs page")</span></span>

1. <span data-ttu-id="fa49b-120">Selecione **Novo** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="fa49b-120">Select **New** on the Action Pane.</span></span>

1. <span data-ttu-id="fa49b-121">Faça as seguintes configurações no cabeçalho da página:</span><span class="sxs-lookup"><span data-stu-id="fa49b-121">Make the following settings in the header of the page:</span></span>

    - <span data-ttu-id="fa49b-122">**Nome da guia** - Especifique um nome para a guia.</span><span class="sxs-lookup"><span data-stu-id="fa49b-122">**Tab name** - Specify a name for the tab.</span></span>
    - <span data-ttu-id="fa49b-123">**Exibição principal** - Selecione entre as duas listas de trabalhos predefinidas (*Trabalhos ativos* ou *Todos os trabalhos*).</span><span class="sxs-lookup"><span data-stu-id="fa49b-123">**Main view** - Select between the two pre-defined job lists (*Active jobs* or *All jobs*).</span></span>
    - <span data-ttu-id="fa49b-124">**Exibição detalhada** - Selecione entre um valor em branco ou **Detalhes do trabalho**.</span><span class="sxs-lookup"><span data-stu-id="fa49b-124">**Details view** - Select between a blank value or **Job details**.</span></span> <span data-ttu-id="fa49b-125">Se você selecionar o valor em branco, não haverá uma exibição detalhada na guia. Se você selecionar **Detalhes do trabalho**, a exibição detalhada conterá uma descrição detalhada do trabalho selecionado na lista de trabalhos na exibição principal.</span><span class="sxs-lookup"><span data-stu-id="fa49b-125">If you select the blank value, there will be no detailed view in the tab. If you select **Job details**, the detailed view will contain a detailed description of the job selected in the job list in the main view.</span></span>

1. <span data-ttu-id="fa49b-126">Na seção **Barra de ferramentas principal**, escolha quais botões devem estar disponíveis na barra de ferramentas principal.</span><span class="sxs-lookup"><span data-stu-id="fa49b-126">In the **Primary toolbar** section, choose which buttons should be available in the primary toolbar.</span></span> <span data-ttu-id="fa49b-127">A coluna **Ações disponíveis** mostra uma lista de todos os botões que podem ser adicionados.</span><span class="sxs-lookup"><span data-stu-id="fa49b-127">The **Available actions** column shows a list of all the buttons that can be added.</span></span> <span data-ttu-id="fa49b-128">As colunas **Ações selecionadas** mostram uma lista de todos os botões incluídos na configuração atual.</span><span class="sxs-lookup"><span data-stu-id="fa49b-128">The **Selected actions** columns shows a list of all the buttons that are included in the current configuration.</span></span> <span data-ttu-id="fa49b-129">Use os botões para mover itens selecionados entre as colunas, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="fa49b-129">Use the buttons between the columns to move selected items between the columns as needed.</span></span> <span data-ttu-id="fa49b-130">Use os botões para cima e para baixo ao lado da coluna **Ações selecionadas** para controlar a ordem na qual os botões são apresentados na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="fa49b-130">Use the up and down buttons next to the **Selected actions** column to control the order in which the buttons are presented in the user interface.</span></span>

1. <span data-ttu-id="fa49b-131">Na seção **Barra de ferramentas** **secundária**, escolha quais botões devem estar disponíveis na barra de ferramentas secundária.</span><span class="sxs-lookup"><span data-stu-id="fa49b-131">In the **Secondary** **toolbar** section, choose which buttons should be available in the secondary toolbar.</span></span> <span data-ttu-id="fa49b-132">A coluna **Ações disponíveis** mostra uma lista de todos os botões que podem ser adicionados.</span><span class="sxs-lookup"><span data-stu-id="fa49b-132">The **Available actions** column shows a list of all the buttons that can be added.</span></span> <span data-ttu-id="fa49b-133">As colunas **Ações selecionadas** mostram uma lista de todos os botões incluídos na configuração atual.</span><span class="sxs-lookup"><span data-stu-id="fa49b-133">The **Selected actions** columns shows a list of all the buttons that are included in the current configuration.</span></span> <span data-ttu-id="fa49b-134">Use os botões para mover itens selecionados entre as colunas, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="fa49b-134">Use the buttons between the columns to move selected items between the columns as needed.</span></span> <span data-ttu-id="fa49b-135">Use os botões para cima e para baixo ao lado da coluna **Ações selecionadas** para controlar a ordem na qual os botões são apresentados na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="fa49b-135">Use the up and down buttons next to the **Selected actions** column to control the order in which the buttons are presented in the user interface.</span></span>

## <a name="associate-a-tab-with-a-configuration"></a><span data-ttu-id="fa49b-136">Associar uma guia a uma configuração</span><span class="sxs-lookup"><span data-stu-id="fa49b-136">Associate a tab with a configuration</span></span>

<span data-ttu-id="fa49b-137">Depois de criar todas as guias necessárias, você pode associá-las a uma configuração.</span><span class="sxs-lookup"><span data-stu-id="fa49b-137">After you designed all the tabs you need, you can associate them with a configuration.</span></span>

1. <span data-ttu-id="fa49b-138">Vá para **Controle de produção &gt; Configuração &gt; Configurar execução de piso de produção**.</span><span class="sxs-lookup"><span data-stu-id="fa49b-138">Go to **Production control &gt; Setup &gt; Configure production floor execution**.</span></span>

    <span data-ttu-id="fa49b-139">![Configurar execução de chão de produção](media/pfe-config-prod-floor-execution.png "Configurar execução de chão de produção")</span><span class="sxs-lookup"><span data-stu-id="fa49b-139">![Configure production floor execution](media/pfe-config-prod-floor-execution.png "Configure production floor execution")</span></span>

1. <span data-ttu-id="fa49b-140">Na FastTab **Seleção de guias**, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="fa49b-140">On the **Tab selection** FastTab, select **Add**.</span></span>

1. <span data-ttu-id="fa49b-141">Uma nova linha será adicionada à grade.</span><span class="sxs-lookup"><span data-stu-id="fa49b-141">A new row is added to the grid.</span></span> <span data-ttu-id="fa49b-142">Para essa nova linha, selecione o nome de uma guia que você deseja adicionar à configuração.</span><span class="sxs-lookup"><span data-stu-id="fa49b-142">For this new row, select the name of a tab that you want to add to the configuration.</span></span>

1. <span data-ttu-id="fa49b-143">Continue adicionando outras guias, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="fa49b-143">Continue to add additional tabs as needed.</span></span>

1. <span data-ttu-id="fa49b-144">Use os botões **Mover para cima** e **Mover para baixo** na barra de ferramentas para organizar as guias, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="fa49b-144">Use the **Move up** and **Move down** buttons on the toolbar to arrange the tabs as needed.</span></span> <span data-ttu-id="fa49b-145">As guias serão exibidas da esquerda para a direita na ordem mostrada na captura de tela acima (a guia na parte superior é mostrada à esquerda).</span><span class="sxs-lookup"><span data-stu-id="fa49b-145">The tabs will be displayed from left to right in the order shown in the above screenshot (the tab at the top is shown on the left).</span></span>

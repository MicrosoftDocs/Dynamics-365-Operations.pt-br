---
title: "Pesquisa de ação"
description: "Este artigo descreve a funcionalidade de pesquisa de ação no Microsoft Dynamics 365 for Finance and Operations. A pesquisa de ação ajudará a encontrar e executar ações em uma página."
author: jasongre
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 62303
ms.assetid: 62c70de0-fdde-4417-8e08-0583fb095a40
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 3ee5334c87b2b0acae2afa6882feca63e3b9cc8e
ms.openlocfilehash: 960c715c487fbda5d93630327f07380e6d8fbd3c
ms.contentlocale: pt-br
ms.lasthandoff: 12/18/2018

---

# <a name="action-search"></a><span data-ttu-id="f4b40-104">Pesquisa de ação</span><span class="sxs-lookup"><span data-stu-id="f4b40-104">Action search</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f4b40-105">Este artigo descreve a funcionalidade de pesquisa de ação no Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f4b40-105">This article describes the action search functionality in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="f4b40-106">A pesquisa de ação ajudará a encontrar e executar ações em uma página.</span><span class="sxs-lookup"><span data-stu-id="f4b40-106">Action search will help you find and run actions on a page.</span></span>

## <a name="introduction"></a><span data-ttu-id="f4b40-107">Introdução</span><span class="sxs-lookup"><span data-stu-id="f4b40-107">Introduction</span></span>

<span data-ttu-id="f4b40-108">As páginas no Microsoft Dynamics 365 for Finance and Operations expõem principalmente comandos em Painéis de Ação: o Painel de Ação padrão que aparece na parte superior da página e as barras de ferramentas que aparecem em várias seções da página.</span><span class="sxs-lookup"><span data-stu-id="f4b40-108">Pages in Microsoft Dynamics 365 for Finance and Operations primarily expose commands on Action Panes, both the standard Action Pane that appears at the top of a page and the toolbars that appear in various sections of the page.</span></span> <span data-ttu-id="f4b40-109">Em versões anteriores, um recurso Dicas de Tecla permitia acessar rapidamente qualquer botão de um Painel de Ação pressionando a tecla Alt e depois uma série de letras.</span><span class="sxs-lookup"><span data-stu-id="f4b40-109">In previous versions, a Key Tips feature let you quickly access any button on an Action Pane by pressing the Alt key and then a series of letters.</span></span>

<span data-ttu-id="f4b40-110">[![keyTipsAX6](./media/keytipsax6.png)](./media/keytipsax6.png)</span><span class="sxs-lookup"><span data-stu-id="f4b40-110">[![keyTipsAX6](./media/keytipsax6.png)](./media/keytipsax6.png)</span></span>

<span data-ttu-id="f4b40-111">Entretanto, na versão atual de Finance and Operations, Dicas de Tecla não estão mais disponíveis, mas foram substituídas pelo recurso de pesquisa de ação.</span><span class="sxs-lookup"><span data-stu-id="f4b40-111">However, in the current version of Finance and Operations, Key Tips are no longer available but have been replaced by the action search feature.</span></span> <span data-ttu-id="f4b40-112">Esse novo recurso permite procurar e executar rapidamente um botão em qualquer Painel de Ação visível.</span><span class="sxs-lookup"><span data-stu-id="f4b40-112">This new feature lets you quickly search for and run a button from any visible Action Pane.</span></span>

## <a name="using-action-search"></a><span data-ttu-id="f4b40-113">Usando a pesquisa de ação</span><span class="sxs-lookup"><span data-stu-id="f4b40-113">Using action search</span></span>

<span data-ttu-id="f4b40-114">Para usar o recurso de pesquisa de ação, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f4b40-114">To use the action search feature, follow these steps.</span></span>

1. <span data-ttu-id="f4b40-115">No Painel de Ação, clique no campo **pesquisa de ação**.</span><span class="sxs-lookup"><span data-stu-id="f4b40-115">On the Action Pane, click in the **action search** field.</span></span> <span data-ttu-id="f4b40-116">(O campo **pesquisa de ação** tem um ícone de lupa).</span><span class="sxs-lookup"><span data-stu-id="f4b40-116">(The **action search** field contains a magnifying glass icon.)</span></span>
2. <span data-ttu-id="f4b40-117">Digite todo ou parte do nome do botão que deseja executar.</span><span class="sxs-lookup"><span data-stu-id="f4b40-117">Type all or part of the name of the button that you want to run.</span></span> <span data-ttu-id="f4b40-118">Também é possível pesquisar usando palavras do "caminho" do botão.</span><span class="sxs-lookup"><span data-stu-id="f4b40-118">You can also search by using words from the button's "path."</span></span> <span data-ttu-id="f4b40-119">(Para obter mais informações, consulte a próxima seção deste artigo.) Normalmente, um botão aparecerá próximo ao topo da lista de resultados depois que você digitar dois a quatro caracteres.</span><span class="sxs-lookup"><span data-stu-id="f4b40-119">(For more information, see the next section of this article.) Typically, a button will appear near the top of the results list after you've typed two to four characters.</span></span>
3. <span data-ttu-id="f4b40-120">Localize e execute o botão na lista de resultados (usando o mouse ou o teclado).</span><span class="sxs-lookup"><span data-stu-id="f4b40-120">Find and run the button in the results list (by using your mouse or keyboard).</span></span>

<span data-ttu-id="f4b40-121">Depois que o botão é executado, o foco retorna à sua última posição na página, para que você possa continuar trabalhando.</span><span class="sxs-lookup"><span data-stu-id="f4b40-121">After the button is run, the focus is returned to your last position on the page, so that you can continue to work.</span></span>

<span data-ttu-id="f4b40-122">[![action-search-field](./media/action-search-field.png)](./media/action-search-field.png)</span><span class="sxs-lookup"><span data-stu-id="f4b40-122">[![action-search-field](./media/action-search-field.png)](./media/action-search-field.png)</span></span>

<span data-ttu-id="f4b40-123">Você também pode iniciar a pesquisa de ação pressionando Ctrl+/ ou Alt+Q.</span><span class="sxs-lookup"><span data-stu-id="f4b40-123">You can also start action search by pressing Ctrl+/ or Alt+Q.</span></span> <span data-ttu-id="f4b40-124">Pressione o atalho de teclado novamente para retornar o foco à sua última posição na página.</span><span class="sxs-lookup"><span data-stu-id="f4b40-124">Press the keyboard shortcut again to return the focus to your last position on the page.</span></span>

## <a name="understanding-the-results-list"></a><span data-ttu-id="f4b40-125">Noção básica da lista de resultados</span><span class="sxs-lookup"><span data-stu-id="f4b40-125">Understanding the results list</span></span>

<span data-ttu-id="f4b40-126">Frequentemente, no Finance and Operations, você deve conhecer o local e o contexto de um botão para compreender totalmente a finalidade desse botão.</span><span class="sxs-lookup"><span data-stu-id="f4b40-126">Often, in Finance and Operations, you must know both the location and the context of a button to fully understand the purpose of that button.</span></span> <span data-ttu-id="f4b40-127">Por isso, as informações adicionais são mostradas para cada item da lista de resultados, para ajudar a entender completamente os botões que aparecem na lista.</span><span class="sxs-lookup"><span data-stu-id="f4b40-127">Therefore, additional information is shown for each item in the results list, to help you understand exactly which buttons appear in the list.</span></span> <span data-ttu-id="f4b40-128">Particularmente, o "caminho" do botão é exibido.</span><span class="sxs-lookup"><span data-stu-id="f4b40-128">In particular, the "path" of the button is shown.</span></span> <span data-ttu-id="f4b40-129">Esse caminho pode incluir os rótulos dos seguintes elementos da interface do usuário, conforme relevantes:</span><span class="sxs-lookup"><span data-stu-id="f4b40-129">This path might include the labels of the following UI elements, as relevant:</span></span>

- <span data-ttu-id="f4b40-130">Guia Painel de Ação</span><span class="sxs-lookup"><span data-stu-id="f4b40-130">Action Pane tab</span></span>
- <span data-ttu-id="f4b40-131">Grupo de botões</span><span class="sxs-lookup"><span data-stu-id="f4b40-131">Button group</span></span>
- <span data-ttu-id="f4b40-132">Botão de menu (se o botão estiver em um botão de menu)</span><span class="sxs-lookup"><span data-stu-id="f4b40-132">Menu button (if the button is inside a menu button)</span></span>
- <span data-ttu-id="f4b40-133">Separador de menu (se o botão estiver em um grupo nomeado, dentro de um botão de menu)</span><span class="sxs-lookup"><span data-stu-id="f4b40-133">Menu separator (if the button is inside a named group inside a menu button)</span></span>
- <span data-ttu-id="f4b40-134">Grupo ou guia na página (por exemplo, o nome de uma Guia Rápida)</span><span class="sxs-lookup"><span data-stu-id="f4b40-134">Group or tab on the page (for example, the name of a FastTab)</span></span>

<span data-ttu-id="f4b40-135">Por exemplo, você digitou **tot** no campo de **pesquisa de ação** e agora está examinando a lista de resultados.</span><span class="sxs-lookup"><span data-stu-id="f4b40-135">For example, you typed **tot** in the **action search** field and are now examining the results list.</span></span> <span data-ttu-id="f4b40-136">A primeira ocorrência, referente ao botão **Totais**, é realçada.</span><span class="sxs-lookup"><span data-stu-id="f4b40-136">The first entry, for a button that is named **Totals**, is highlighted.</span></span> <span data-ttu-id="f4b40-137">O caminho de botão **Ordem de venda** &gt; **Exibir** também é exibido.</span><span class="sxs-lookup"><span data-stu-id="f4b40-137">A button path of **Sales order** &gt; **View** is also shown.</span></span> <span data-ttu-id="f4b40-138">A parte da **Ordem de venda** do caminho corresponde à guia **Ordem de venda** no Painel Ação e a parte **Exibir** do caminho corresponde ao grupo **Exibir** daquela guia. Da mesma forma, a parte do botão **Desconto total** (**Vender** &gt; **Calcular**) informa que este botão está localizado no grupo **Calcular** na guia **Vender** do Painel Ação.</span><span class="sxs-lookup"><span data-stu-id="f4b40-138">The **Sales order** part of the path corresponds to the **Sales order** tab on the Action Pane, and the **View** part of the path corresponds to the **View** group on that tab. Similarly, the path of the **Total discount** button (**Sell** &gt; **Calculate**) informs you that this button is located in the **Calculate** group on the **Sell** tab of the Action Pane.</span></span> <span data-ttu-id="f4b40-139">Portanto, essas informações ajudam você a compreender exatamente qual botão será acionado pela pesquisa de ação (se você selecionar esse botão na lista de resultados).</span><span class="sxs-lookup"><span data-stu-id="f4b40-139">Therefore, this information helps you understand exactly which button will be triggered by action search (if you select that button in the results list).</span></span>

<span data-ttu-id="f4b40-140">[![action-search-field-with-data](./media/action-search-field-with-data.png)](./media/action-search-field-with-data.png)</span><span class="sxs-lookup"><span data-stu-id="f4b40-140">[![action-search-field-with-data](./media/action-search-field-with-data.png)](./media/action-search-field-with-data.png)</span></span>

<span data-ttu-id="f4b40-141">No exemplo anterior, a pesquisa de ação mostrou resultados do painel de ações padrão na parte superior da página.</span><span class="sxs-lookup"><span data-stu-id="f4b40-141">In the previous example, action search showed results from the standard Action Pane at the top of a page.</span></span> <span data-ttu-id="f4b40-142">No entanto, a pesquisa de ação também exibe resultados de barras de ferramentas visíveis que estão localizadas em outros locais da página.</span><span class="sxs-lookup"><span data-stu-id="f4b40-142">However, action search also shows results from visible toolbars that are located in other places on the page.</span></span> <span data-ttu-id="f4b40-143">Por exemplo, você está procurando o botão **Estoque disponível**, localizado na Guia Rápida **Linhas de ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="f4b40-143">For example, you're searching for the **On-hand inventory** button that is located on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="f4b40-144">Nesse caso, o caminho do botão na lista de resultados (**Linhas de ordem de venda** &gt; **Estoque** &gt; **Exibir**) informa que esse botão está localizado abaixo do cabeçalho **Exibir** no botão de menu **Estoque**, na Guia Rápida **Linhas de ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="f4b40-144">In this case, the button path in the results list (**Sales order lines** &gt; **Inventory** &gt; **View**) informs you that this button is located under the **View** heading on the **Inventory** menu button on the **Sales order lines** FastTab.</span></span>

<span data-ttu-id="f4b40-145">[![on-hand-inventory](./media/on-hand-inventory.png)](./media/on-hand-inventory.png)</span><span class="sxs-lookup"><span data-stu-id="f4b40-145">[![on-hand-inventory](./media/on-hand-inventory.png)](./media/on-hand-inventory.png)</span></span>

## <a name="action-search-vs-navigation-search"></a><span data-ttu-id="f4b40-146">Pesquisa de ação x pesquisa de navegação</span><span class="sxs-lookup"><span data-stu-id="f4b40-146">Action search vs. Navigation search</span></span>

<span data-ttu-id="f4b40-147">Enquanto a pesquisa de ação tem como objetivo localizar e executar ações em uma página, existe um mecanismo de pesquisa destinado especificamente à localização e navegação nas páginas do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f4b40-147">Whereas action search is intended to find and run actions on a page, there is a separate search mechanism for finding and navigating to pages in Finance and Operations.</span></span> <span data-ttu-id="f4b40-148">Para obter mais informações sobre esse recurso, consulte o artigo [Pesquisa de navegação](navigation-search.md).</span><span class="sxs-lookup"><span data-stu-id="f4b40-148">For more information about that feature, see the [Navigation search](navigation-search.md) article.</span></span>

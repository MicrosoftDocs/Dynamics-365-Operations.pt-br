---
title: Localizar informações usando pesquisas
description: Vários campos têm pesquisas que podem ajudá-lo a encontrar facilmente o valor correto ou desejado. Vários aprimoramentos foram adicionados às pesquisas tornando esses controles mais úteis e os usuários mais produtivos. Neste tópico, você aprenderá sobre esses novos recursos das pesquisas e receberá algumas dicas úteis para fazer o melhor uso possível delas no sistema.
author: jasongre
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 269934
ms.assetid: f20cbd2c-14e0-47e7-b351-8e60d3537f96
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7c7cd0042e5b801cc6c60b966709673351601eed
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176537"
---
# <a name="find-information-by-using-lookups"></a><span data-ttu-id="52930-105">Localizar informações usando pesquisas</span><span class="sxs-lookup"><span data-stu-id="52930-105">Find information by using lookups</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="52930-106">Vários campos têm pesquisas que podem ajudá-lo a encontrar facilmente o valor correto ou desejado.</span><span class="sxs-lookup"><span data-stu-id="52930-106">Many fields have lookups that can help you easily find the correct or desired value.</span></span> <span data-ttu-id="52930-107">Vários aprimoramentos foram adicionados às pesquisas tornando esses controles mais úteis e os usuários mais produtivos.</span><span class="sxs-lookup"><span data-stu-id="52930-107">Several enhancements have been added to lookups that make these controls more usable and make users more productive.</span></span> <span data-ttu-id="52930-108">Neste tópico, você aprenderá sobre esses novos recursos das pesquisas e receberá algumas dicas úteis para fazer o melhor uso possível delas no sistema.</span><span class="sxs-lookup"><span data-stu-id="52930-108">In this topic, you will learn about these new lookup features and will receive some helpful tips to get the optimal use out of lookups in the system.</span></span>

## <a name="responsive-lookups"></a><span data-ttu-id="52930-109">Pesquisas adequadas</span><span class="sxs-lookup"><span data-stu-id="52930-109">Responsive lookups</span></span>

<span data-ttu-id="52930-110">Em versões anteriores, ao interagir com um controle da pesquisa, um usuário precisava realizar uma ação explícita para abrir o menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="52930-110">In previous versions, when interacting with a lookup control, a user would have to take an explicit action to open the drop-down menu.</span></span> <span data-ttu-id="52930-111">Isso poderia ser digitando um asterisco (\*) no controle para filtrar a pesquisa com base no valor atual do controle, clicando no botão suspenso ou utilizando o atalho **Alt**+**Seta para baixo**.</span><span class="sxs-lookup"><span data-stu-id="52930-111">This may have been by typing an asterisk (\*) in the control to filter the lookup based on the current value of the control, clicking the drop-down button, or by using the **Alt**+**Down arrow** keyboard shortcut.</span></span> <span data-ttu-id="52930-112">Os controles da pesquisa foram modificados das seguintes maneiras para melhor se alinhar às práticas atuais da web:</span><span class="sxs-lookup"><span data-stu-id="52930-112">Lookup controls have been modified in the following ways to better align with current web practices:</span></span>

- <span data-ttu-id="52930-113">Os menus suspensos da pesquisa agora abrirão automaticamente após uma breve pausa na digitação, com o conteúdo do menu suspenso filtrado com base no valor do controle da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="52930-113">Lookup drop-down menus will now open automatically after a slight pause in typing, with the drop-down menu contents filtered based on the lookup control's value.</span></span>

    <span data-ttu-id="52930-114">Observe que o comportamento antigo de abertura automática do menu suspenso após digitar um asterisco (\*) foi substituído.</span><span class="sxs-lookup"><span data-stu-id="52930-114">Note that the old behavior of automatic opening of the dropdown after typing an asterisk (\*) has been deprecated.</span></span>

- <span data-ttu-id="52930-115">Assim que o menu suspenso da pesquisa é aberto, ocorrerá o seguinte:</span><span class="sxs-lookup"><span data-stu-id="52930-115">After the lookup drop-down menu has opened, the following will occur:</span></span>

    - <span data-ttu-id="52930-116">O cursor ficará no controle da pesquisa (em vez do foco se mover para o menu suspenso) para que você possa continuar fazendo modificações no valor do controle.</span><span class="sxs-lookup"><span data-stu-id="52930-116">The cursor will stay in the lookup control (instead of focus moving into the drop-down menu) so you can continue to make modifications to the control's value.</span></span> <span data-ttu-id="52930-117">No entanto, o usuário ainda pode utilizar as setas **Para cima** e **Para baixo** para mudar de linha no menu suspenso, e o enter para selecionar a linha atual no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="52930-117">However, the user can still use the **Up arrow** and **Down arrow** to change rows in the drop-down menu, and enter to select the current row in the drop-down menu.</span></span>
    - <span data-ttu-id="52930-118">O conteúdo do menu suspenso irá se ajustar após qualquer modificação no valor do controle da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="52930-118">The contents of the drop-down menu will adjust after any modifications are made to the lookup control's value.</span></span>

<span data-ttu-id="52930-119">Por exemplo, considere um campo de pesquisa chamado **Cidade**.</span><span class="sxs-lookup"><span data-stu-id="52930-119">For example, consider a lookup field called **City**.</span></span>

<span data-ttu-id="52930-120">Quando o foco estiver no campo **Cidade**, você pode começar a procurar a cidade desejada digitando algumas letras, como "col."</span><span class="sxs-lookup"><span data-stu-id="52930-120">When focus is in the **City** field, you can start looking for the city that you want by typing a few letters, like "col."</span></span> <span data-ttu-id="52930-121">Assim que você parar de digitar, a pesquisa abrirá automaticamente, filtrando apenas as cidades que começam com "col".</span><span class="sxs-lookup"><span data-stu-id="52930-121">After you stop typing, the lookup will open automatically, filtered to those cities that begin with "col".</span></span>

<span data-ttu-id="52930-122">[![typeaheadLookupExample](./media/typeaheadlookupexample.png)](./media/typeaheadlookupexample.png)</span><span class="sxs-lookup"><span data-stu-id="52930-122">[![typeaheadLookupExample](./media/typeaheadlookupexample.png)](./media/typeaheadlookupexample.png)</span></span>

<span data-ttu-id="52930-123">Nesse momento, o cursor ainda está no campo de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="52930-123">At this point, the cursor is still in the lookup field.</span></span> <span data-ttu-id="52930-124">Se você continuar digitando o valor "colum", o conteúdo da pesquisa se ajusta automaticamente para refletir o valor mais atual no controle.</span><span class="sxs-lookup"><span data-stu-id="52930-124">If you continue typing so the value is "colum," the lookup contents adjust automatically to reflect the latest value in the control.</span></span>

![updateFilterLookupExample](./media/updatefilterlookupexample.png)

<span data-ttu-id="52930-126">Ainda que o foco continue no controle da pesquisa, você também pode utilizar as teclas **Para cima** ou **Para baixo** para realçar a linha que deseja selecionar.</span><span class="sxs-lookup"><span data-stu-id="52930-126">Even though focus is still in the lookup control, you can also use the **Up arrow** or **Down arrow** keys to highlight the row that you want to select.</span></span> <span data-ttu-id="52930-127">Se você apertar **Enter** a linha realçada será selecionada na pesquisa e o valor do controle será atualizado.</span><span class="sxs-lookup"><span data-stu-id="52930-127">If you press **Enter** the highlighted row will be selected from the lookup and the control's value will be updated.</span></span>

![changingSelectionLookup](./media/changingselectionlookup.png)

## <a name="typing-in-more-than-ids"></a><span data-ttu-id="52930-129">Digitando mais que IDs</span><span class="sxs-lookup"><span data-stu-id="52930-129">Typing in more than IDs</span></span>

<span data-ttu-id="52930-130">Ao inserir dados, é natural que os usuários tentem identificar uma entidade, como um cliente ou fornecedor, em termos do nome em vez de um identificador que represente a entidade.</span><span class="sxs-lookup"><span data-stu-id="52930-130">When entering data, it's natural for users to attempt to identify an entity, such as a customer or vendor, in terms of the name rather than an identifier representing the entity.</span></span> <span data-ttu-id="52930-131">Muitas pesquisas (mas não todas) agora permitem a entrada de dados contextuais.</span><span class="sxs-lookup"><span data-stu-id="52930-131">Many (but not all) lookups now allow contextual data entry.</span></span> <span data-ttu-id="52930-132">Este recurso poderoso permite que o usuário digite o ID ou o nome correspondente no controle da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="52930-132">This powerful feature allows the user to type the ID or the corresponding name into the lookup control.</span></span>

<span data-ttu-id="52930-133">Por exemplo, considere o campo **Conta do cliente** ao criar uma ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="52930-133">For example, consider the **Customer account** field when creating a sales order.</span></span> <span data-ttu-id="52930-134">Esse campo mostra o **ID da conta** do cliente, mas um usuário iria tipicamente preferir inserir um **Nome da conta** em vez do **ID da conta** para esse campo ao criar uma ordem de venda, como "Forest Wholesales" em vez de "US-003."</span><span class="sxs-lookup"><span data-stu-id="52930-134">This field shows the **Account ID** for the customer, but a user would typically prefer to enter an **Account name** instead of an **Account ID** for this field when creating a sales order, such as "Forest Wholesales" instead of "US-003."</span></span>

<span data-ttu-id="52930-135">Se o usuário começou a inserir um **ID da conta** no controle da pesquisa, o menu suspenso abriria automaticamente como descrito na seção anterior e o usuário veria a pesquisa como mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="52930-135">If the user started to enter an **Account ID** into the lookup control, the drop-down menu would automatically open as described in the previous section and the user would see the lookup as shown below.</span></span>

<span data-ttu-id="52930-136">[![Pesquisa contextual quando um ID da conta do cliente é inserido](./media/howtocontextuallookups-1.png)](./media/howtocontextuallookups-1.png)</span><span class="sxs-lookup"><span data-stu-id="52930-136">[![Contextual lookup when a customer account ID is entered](./media/howtocontextuallookups-1.png)](./media/howtocontextuallookups-1.png)</span></span>

<span data-ttu-id="52930-137">No entanto, o usuário agora também pode inserir o início de um **Nome da conta**.</span><span class="sxs-lookup"><span data-stu-id="52930-137">However, the user can also now enter the beginning of an **Account name** as well.</span></span> <span data-ttu-id="52930-138">Se isso for detectado, o usuário verá a seguinte pesquisa.</span><span class="sxs-lookup"><span data-stu-id="52930-138">If this is detected, then the user will see the following lookup.</span></span> <span data-ttu-id="52930-139">Observe como a coluna **Nome** é movida para se tornar a primeira coluna na pesquisa, e como a pesquisa é classificada e filtrada com base na coluna **Nome**.</span><span class="sxs-lookup"><span data-stu-id="52930-139">Notice how the **Name** column is moved to be the first column in the lookup, and how the lookup is sorted and filtered based on the **Name** column.</span></span>

<span data-ttu-id="52930-140">[![Pesquisa contextual quando um nome do cliente é inserido](./media/howtocontextuallookups-2.png)](./media/howtocontextuallookups-2.png)</span><span class="sxs-lookup"><span data-stu-id="52930-140">[![Contextual lookup when a customer name is entered](./media/howtocontextuallookups-2.png)](./media/howtocontextuallookups-2.png)</span></span>

## <a name="using-grid-column-headers-for-more-advanced-filtering-and-sorting"></a><span data-ttu-id="52930-141">Usando cabeçalhos de coluna da tabela para filtragem e classificação mais avançada</span><span class="sxs-lookup"><span data-stu-id="52930-141">Using grid column headers for more advanced filtering and sorting</span></span>

<span data-ttu-id="52930-142">Os aprimoramentos na pesquisa discutidos nas duas seções anteriores aumentam significativamente a habilidade do usuário navegar pelas linhas em uma pesquisa com base em uma busca do tipo "começa com" nos campos **ID** ou **Nome** na pesquisa.</span><span class="sxs-lookup"><span data-stu-id="52930-142">The lookup enhancements discussed in the previous two sections greatly improve a user's ability to navigate the rows in a lookup based on a "begins with" search of the **ID** or **Name** field in the lookup.</span></span> <span data-ttu-id="52930-143">No entanto, existem situações em que filtros (ou classificações) mais avançados são necessários para encontrar a linha correta.</span><span class="sxs-lookup"><span data-stu-id="52930-143">However, there are situations in which more advanced filtering (or sorting) is needed to find the correct row.</span></span> <span data-ttu-id="52930-144">Nessas situações, o usuário precisa usar as opções de filtragem e classificação nos cabeçalhos de coluna da tabela dentro da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="52930-144">In these situations, the user needs to use the filtering and sorting options in the grid column headers inside the lookup.</span></span> <span data-ttu-id="52930-145">Por exemplo, considere um funcionário inserindo uma linha da ordem de venda que precisa localizar o "cabo" certo como produto.</span><span class="sxs-lookup"><span data-stu-id="52930-145">For example, consider an employee entering a sales order line who needs to locate the right "cable" as the product.</span></span> <span data-ttu-id="52930-146">Digitar "cabo" no controle **Número do item** não é útil, já que não existem nomes de produtos que começam com "cabo".</span><span class="sxs-lookup"><span data-stu-id="52930-146">Typing "cable" into the **Item number** control isn't helpful, as there are no product names that begin with "cable."</span></span>

![emptyitemlookup](./media/emptyitemlookup.png)

<span data-ttu-id="52930-148">Em vez disso, o usuário precisa limpar o valor do controle da pesquisa, abrir o menu suspenso da pesquisa e filtrar o menu suspenso usando o cabeçalho de coluna da tabela, como mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="52930-148">Instead, the user needs to clear the value of the lookup control, open the lookup drop-down menu, and filter the drop-down menu using the grid column header, as shown below.</span></span> <span data-ttu-id="52930-149">Um usuário de mouse (ou de toque) pode simplesmente clicar em qualquer cabeçalho de coluna para acessar as opções de filtragem e classificação para aquela coluna.</span><span class="sxs-lookup"><span data-stu-id="52930-149">A mouse (or touch) user can simply click (or touch) any column header to access the filtering and sorting options for that column.</span></span> <span data-ttu-id="52930-150">Para um usuário de teclado, é necessário simplesmente pressionar **Alt**+**seta** **Para baixo** uma segunda vez para mover o foco para o menu suspenso, quando o usuário poderá selecionar a coluna correta utilizando o Tab, e pressionando **Ctrl**+**G** para abrir o menu suspenso do cabeçalho de coluna da tabela.</span><span class="sxs-lookup"><span data-stu-id="52930-150">For a keyboard user, the user simply needs to press **Alt**+**Down** **arrow** a second time to move focus into the drop-down menu, after which the user can tab to the correct column, and then press **Ctrl**+**G** to open the grid column header drop-down menu.</span></span>

<span data-ttu-id="52930-151">[![gridfilteritemlookup](./media/gridfilteritemlookup.png)](./media/gridfilteritemlookup.png)</span><span class="sxs-lookup"><span data-stu-id="52930-151">[![gridfilteritemlookup](./media/gridfilteritemlookup.png)](./media/gridfilteritemlookup.png)</span></span>

<span data-ttu-id="52930-152">Assim que o filtro for aplicado (veja a imagem abaixo), o usuário pode encontrar e selecionar a linha como de costume.</span><span class="sxs-lookup"><span data-stu-id="52930-152">After the filter has been applied (see the image below), the user can find and select the row as usual.</span></span>

![filtereditemlookup](./media/filtereditemlookup.png)
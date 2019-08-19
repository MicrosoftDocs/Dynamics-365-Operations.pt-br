---
title: Exibir e exportar descrições de campos
description: Este artigo descreve como exibir descrições dos campos e como usar a página de descrições de campo para exportação de descrições.
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FieldDescriptions
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 11534
ms.assetid: e2795f51-a8a7-4c74-bdb9-b1be93bdd358
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3a94f7ab9df19200754e39ba5a46f13bfdb1a3ab
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/02/2019
ms.locfileid: "1852096"
---
# <a name="view-and-export-field-descriptions"></a><span data-ttu-id="53160-103">Exibir e exportar descrições de campos</span><span class="sxs-lookup"><span data-stu-id="53160-103">View and export field descriptions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="53160-104">Este artigo descreve como exibir descrições dos campos e como usar a página de descrições de campo para exportação de descrições.</span><span class="sxs-lookup"><span data-stu-id="53160-104">This article describes how to view field descriptions and how to use the Field descriptions page to export descriptions.</span></span>

<span data-ttu-id="53160-105">O Microsoft Dynamics 365 for Finance and Operations tem descrições para alguns dos campos mais complexos.</span><span class="sxs-lookup"><span data-stu-id="53160-105">Microsoft Dynamics 365 for Finance and Operations has descriptions for some of the more complex fields.</span></span> <span data-ttu-id="53160-106">Essas descrições aparecem ao passar o mouse sobre um campo.</span><span class="sxs-lookup"><span data-stu-id="53160-106">These descriptions appear when you hover over a field.</span></span> <span data-ttu-id="53160-107">Você também pode exibir e exportar descrições na página **Descrições de campo**.</span><span class="sxs-lookup"><span data-stu-id="53160-107">You can also view and export descriptions on the **Field descriptions** page.</span></span>

<span data-ttu-id="53160-108">Nem todas as páginas têm descrições de campo.</span><span class="sxs-lookup"><span data-stu-id="53160-108">Not all pages have field descriptions.</span></span> <span data-ttu-id="53160-109">Pretendemos fornecer descrições apenas dos campos mais complexos, e não daqueles cujo uso é evidente.</span><span class="sxs-lookup"><span data-stu-id="53160-109">We want to provide descriptions only for the more complex fields, not where the use of the field is obvious.</span></span> <span data-ttu-id="53160-110">Portanto, algumas páginas não têm todas as descrições de campo, algumas páginas possuem algumas descrições e algumas das páginas mais complexas, como muitas das páginas de parâmetros, há muitas descrições.</span><span class="sxs-lookup"><span data-stu-id="53160-110">Therefore, some pages don't have any field descriptions, some pages have a few descriptions, and some of the more complex pages, such as many of the parameters pages, have many descriptions.</span></span>

<span data-ttu-id="53160-111">Se você tiver acesso ao ambiente de desenvolvimento do Finance and Operations, poderá adicionar suas próprias novas descrições aos campos e personalizar as descrições existentes.</span><span class="sxs-lookup"><span data-stu-id="53160-111">If you have access to the Finance and Operations development environment, you can add new field descriptions and customize existing descriptions.</span></span> <span data-ttu-id="53160-112">Por exemplo, você pode adicionar informações específicas da empresa para uma descrição de campo.</span><span class="sxs-lookup"><span data-stu-id="53160-112">For example, you can add company-specific information to a field description.</span></span> <span data-ttu-id="53160-113">Para mais informações, consulte [Personalizar campo de ajuda](../../dev-itpro/user-interface/customize-field-help.md).</span><span class="sxs-lookup"><span data-stu-id="53160-113">For more information, see [Customize field help](../../dev-itpro/user-interface/customize-field-help.md).</span></span>

## <a name="see-field-descriptions-in-the-user-interface"></a><span data-ttu-id="53160-114">Consulte as descrições na interface de usuário</span><span class="sxs-lookup"><span data-stu-id="53160-114">See field descriptions in the user interface</span></span>

<span data-ttu-id="53160-115">Você pode exibir descrições de campo focalizando sobre um campo.</span><span class="sxs-lookup"><span data-stu-id="53160-115">You can view field descriptions by hovering over a field.</span></span> <span data-ttu-id="53160-116">Se nenhuma descrição estiver disponível, você verá o nome do campo quando passar o mouse no campo.</span><span class="sxs-lookup"><span data-stu-id="53160-116">If no description is available, you see the field name when you hover over the field.</span></span>

> [!NOTE]
> <span data-ttu-id="53160-117">No Dynamics AX 7.0 (fevereiro de 2016), as descrições de campos podem ser exibidas somente na página **Descrições dos campos**.</span><span class="sxs-lookup"><span data-stu-id="53160-117">In Dynamics AX 7.0 (February 2016), field descriptions can be viewed only on the **Field descriptions** page.</span></span>

<span data-ttu-id="53160-118">A ilustração a seguir mostra a descrição do campo que aparece quando você passa o mouse no campo **Bloquear itens durante a contagem**.</span><span class="sxs-lookup"><span data-stu-id="53160-118">The following illustration shows the field description that appears when you hover over the **Lock items during count** field.</span></span>

<span data-ttu-id="53160-119">[![Exemplo de uma descrição de campo](./media/field-description.png)](./media/field-description.png)</span><span class="sxs-lookup"><span data-stu-id="53160-119">[![Example of a field description](./media/field-description.png)](./media/field-description.png)</span></span>

## <a name="use-the-field-descriptions-page-to-view-and-export-field-help"></a><span data-ttu-id="53160-120">Use a página Descrições de campo para exibir e exportar ajuda de campo</span><span class="sxs-lookup"><span data-stu-id="53160-120">Use the Field descriptions page to view and export field help</span></span>

<span data-ttu-id="53160-121">A página **Descrições de campos** permite exibir e exportar descrições de campos.</span><span class="sxs-lookup"><span data-stu-id="53160-121">The **Field descriptions** page lets you view and export field descriptions.</span></span> <span data-ttu-id="53160-122">Você pode ver, uma de cada vez, as descrições que estão disponíveis para uma página.</span><span class="sxs-lookup"><span data-stu-id="53160-122">You can see the descriptions that are available for one page at a time.</span></span>

### <a name="view-the-descriptions-for-a-page"></a><span data-ttu-id="53160-123">Exibir as descrições de uma página</span><span class="sxs-lookup"><span data-stu-id="53160-123">View the descriptions for a page</span></span>

<span data-ttu-id="53160-124">Para exibir as descrições para uma página, siga esta etapa.</span><span class="sxs-lookup"><span data-stu-id="53160-124">To view the descriptions for a page, follow this step.</span></span>

- <span data-ttu-id="53160-125">No campo **Selecionar uma página**, digite o nome da página.</span><span class="sxs-lookup"><span data-stu-id="53160-125">In the **Select a page** field, type the name of the page.</span></span> <span data-ttu-id="53160-126">Como alternativa, clique na seta para abrir uma lista de todas as páginas e, em seguida, procure ou filtre a lista.</span><span class="sxs-lookup"><span data-stu-id="53160-126">Alternatively, click the arrow to open a list of all the pages, and then browse or filter the list.</span></span>

<span data-ttu-id="53160-127">Você pode usar o nome da página que é exibido na interface do usuário (IU) (por exemplo: **Clientes**) ou o nome do código (nome da AOT) da página que está disponível quando você clica com botão direito do mouse nela (por exemplo: **CustTable**).</span><span class="sxs-lookup"><span data-stu-id="53160-127">You can use either the name of the page that is shown in the user interface (UI) (for example, **Customers**) or the code name (AOT name) that's available when you right-click a page (for example, **CustTable**).</span></span>

<span data-ttu-id="53160-128">Para obter informações sobre as várias maneiras de filtrar a lista de páginas, consulte a seção "Procurando uma página" posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="53160-128">For information about the various ways to filter the list of pages, see the "Searching for a page" section later in this article.</span></span>

<span data-ttu-id="53160-129">Se você definir a opção **Incluir campos sem uma descrição** para **Sim**, serão mostrados todos os campos da página, independentemente de terem ou não uma descrição.</span><span class="sxs-lookup"><span data-stu-id="53160-129">If you set the **Include fields without a description** option to **Yes**, all the fields on the page are shown, even if they don't have a field description.</span></span>

### <a name="export-the-descriptions-for-a-page"></a><span data-ttu-id="53160-130">Exportar as descrições de uma página</span><span class="sxs-lookup"><span data-stu-id="53160-130">Export the descriptions for a page</span></span>

<span data-ttu-id="53160-131">Para exportar as descrições para uma página, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="53160-131">To export the descriptions for a page, follow these steps.</span></span>

1. <span data-ttu-id="53160-132">No campo **Selecionar uma página**, selecione uma página.</span><span class="sxs-lookup"><span data-stu-id="53160-132">In the **Select a page** field, select a page.</span></span>
2. <span data-ttu-id="53160-133">Clique no botão **Abrir no Microsoft Office** no canto superior direito e, depois, clique em **FieldDescriptionTmp**.</span><span class="sxs-lookup"><span data-stu-id="53160-133">Click the **Open in Microsoft Office** button in the upper-right corner, and then click **FieldDescriptionTmp**.</span></span>

### <a name="searching-for-a-page"></a><span data-ttu-id="53160-134">Procurar uma página</span><span class="sxs-lookup"><span data-stu-id="53160-134">Searching for a page</span></span>

<span data-ttu-id="53160-135">Há várias maneiras de se pesquisar uma página no campo **Selecionar uma página**.</span><span class="sxs-lookup"><span data-stu-id="53160-135">There are several ways to search for a page in the **Select a page** field.</span></span> <span data-ttu-id="53160-136">Em muitos casos, você precisará clicar na seta no campo **Selecionar uma página** para abrir o menu suspenso e selecionar uma opção em uma lista filtrada de páginas.</span><span class="sxs-lookup"><span data-stu-id="53160-136">In many cases, you must click the arrow in the **Select a page** field to open the drop-down list, and then select from a filtered list of pages.</span></span>

- <span data-ttu-id="53160-137">Digite uma parte do nome e, em seguida, abra a lista suspensa para selecionar uma lista filtrada de páginas.</span><span class="sxs-lookup"><span data-stu-id="53160-137">Type part of the name, and then open the drop-down list to select from a filtered list of pages.</span></span>
- <span data-ttu-id="53160-138">Abra o menu suspenso e clique no cabeçalho **Nome da página** na parte superior da lista ou no cabeçalho **Nome da AOT da página**.</span><span class="sxs-lookup"><span data-stu-id="53160-138">Open the drop-down list, and then click either the **Page name** heading at the top of the list or the **Page AOT name** heading.</span></span> <span data-ttu-id="53160-139">Isso abre uma caixa de diálogo na qual é possível usar opções de filtragem avançada, como **O nome da página começar com**.</span><span class="sxs-lookup"><span data-stu-id="53160-139">A dialog box appears, where you can use advanced filtering options, such as **Page name begins with**.</span></span>
- <span data-ttu-id="53160-140">Digite o nome completo da página.</span><span class="sxs-lookup"><span data-stu-id="53160-140">Type the full name of the page.</span></span> <span data-ttu-id="53160-141">Quando você usa esta opção, é aconselhável abrir o menu suspenso e verificar o que mais consta na lista, mesmo que as descrições dos campos sejam exibidas.</span><span class="sxs-lookup"><span data-stu-id="53160-141">When you use this option, it's best to open the drop-down list and see what else is in the list, even if field descriptions are shown.</span></span>

    - <span data-ttu-id="53160-142">Se houver uma única correspondência exata ao nome, as descrições dos campos da página são exibidas.</span><span class="sxs-lookup"><span data-stu-id="53160-142">If there is a single exact match to the name, the field descriptions for that page are shown.</span></span>
    - <span data-ttu-id="53160-143">Se houver mais de uma correspondência exata, não há descrições mostradas.</span><span class="sxs-lookup"><span data-stu-id="53160-143">If there is more than one exact match, no descriptions are shown.</span></span> <span data-ttu-id="53160-144">Você deve abrir a lista suspensa e selecionar a página que você deseja.</span><span class="sxs-lookup"><span data-stu-id="53160-144">You must open the drop-down list and select the page that you want.</span></span>
    - <span data-ttu-id="53160-145">Se o nome que você digitou é parte do nome de uma outra página, você verá as descrições da sua página.</span><span class="sxs-lookup"><span data-stu-id="53160-145">If the name that you typed is part of the name of another page, you see the descriptions for your page.</span></span> <span data-ttu-id="53160-146">No entanto, se você abrir a lista suspensa, você verá outras páginas que contêm esse nome.</span><span class="sxs-lookup"><span data-stu-id="53160-146">However, if you open the drop-down list, you see additional pages that contain that name.</span></span>

<span data-ttu-id="53160-147">Por exemplo, nenhuma descrição é mostrada quando você digita **Contagem** no campo **Selecionar uma página**.</span><span class="sxs-lookup"><span data-stu-id="53160-147">For example, no descriptions are shown when you type **Counting** in the **Select a page** field.</span></span> <span data-ttu-id="53160-148">Você abre a lista suspensa, e vê que há duas páginas que têm o nome de **Contagem** e diversas páginas que contêm a palavra "Contagem" no nome.</span><span class="sxs-lookup"><span data-stu-id="53160-148">You open the drop-down list, and see that there are two pages that have the name **Counting** and several pages that contain the word "Counting" in the name.</span></span> <span data-ttu-id="53160-149">Se você escolher a página que tem o mesmo nome da AOT **InventJournalCount**, as descrições dos campos dessa página serão mostradas.</span><span class="sxs-lookup"><span data-stu-id="53160-149">If you select the page that has the AOT name **InventJournalCount**, the field descriptions are shown for that page.</span></span> <span data-ttu-id="53160-150">No entanto, ao abrir o menu suspenso novamente, você verá que a lista agora exibe todas as páginas que contêm “InventJournalCount” como parte do nome da página da AOT.</span><span class="sxs-lookup"><span data-stu-id="53160-150">However, if you open the drop-down list again, you will see that the list now contains all pages that have "InventJournalCount" as part of their AOT name.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="53160-151">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="53160-151">Troubleshooting</span></span>

<span data-ttu-id="53160-152">Esta seção oferece informações para ajudá-lo a solucionar problemas que possam surgir durante o uso da página Descrições dos campos.</span><span class="sxs-lookup"><span data-stu-id="53160-152">This section provides information to help you troubleshoot issues that you might encounter when you use field descriptions.</span></span>

### <a name="i-cant-find-a-field-description"></a><span data-ttu-id="53160-153">Não consigo encontrar uma descrição de campo</span><span class="sxs-lookup"><span data-stu-id="53160-153">I can't find a field description</span></span>

<span data-ttu-id="53160-154">Estamos no processo de adição de descrições aos campos mais complexos.</span><span class="sxs-lookup"><span data-stu-id="53160-154">We're in the process of adding descriptions for the more complex fields.</span></span> <span data-ttu-id="53160-155">Se você precisar de ajuda em relação a um determinado campo, avise-nos adicionando um comentário neste tópico.</span><span class="sxs-lookup"><span data-stu-id="53160-155">If you require help for a particular field, let us know by adding a comment for this topic.</span></span>

### <a name="the-field-description-isnt-helpful"></a><span data-ttu-id="53160-156">A descrição do campo não é útil</span><span class="sxs-lookup"><span data-stu-id="53160-156">The field description isn't helpful</span></span>

<span data-ttu-id="53160-157">Avise-nos adicionando um comentário a este tópico.</span><span class="sxs-lookup"><span data-stu-id="53160-157">Let us know by adding a comment for this topic.</span></span> <span data-ttu-id="53160-158">Se possível, descreva as informações adicionais que você precisar.</span><span class="sxs-lookup"><span data-stu-id="53160-158">If you can, describe the additional information that you require.</span></span>

### <a name="i-cant-find-a-field-on-the-field-descriptions-page"></a><span data-ttu-id="53160-159">Não consigo localizar um campo na página de descrições de campo</span><span class="sxs-lookup"><span data-stu-id="53160-159">I can't find a field on the Field descriptions page</span></span>

<span data-ttu-id="53160-160">Para mostrar todos os campos em uma página, defina a opção **Incluir campos sem uma descrição** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="53160-160">To show all the fields on a page, set the **Include fields without a description** option to **Yes**.</span></span> <span data-ttu-id="53160-161">Clique no campo **Selecionar uma página** para verificar se você selecionou a página correta.</span><span class="sxs-lookup"><span data-stu-id="53160-161">Click the **Select a page** field to verify that you've selected the correct page.</span></span> <span data-ttu-id="53160-162">Se o nome que você digitou é parte de outro nome de campo, talvez você tenha selecionado na página que tenha o nome mais longo.</span><span class="sxs-lookup"><span data-stu-id="53160-162">If the name that you typed is part of another field name, you might have selected the page that has the longer name.</span></span>

### <a name="i-cant-find-a-page-on-the-field-descriptions-page"></a><span data-ttu-id="53160-163">Não consigo localizar uma página na página Descrições de campo</span><span class="sxs-lookup"><span data-stu-id="53160-163">I can't find a page on the Field descriptions page</span></span>

<span data-ttu-id="53160-164">Para obter informações sobre as várias maneiras de filtrar a lista de páginas, consulte a seção "Procurando uma página" anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="53160-164">For information about the various way to find pages, see the "Searching for pages" section earlier in this article.</span></span> <span data-ttu-id="53160-165">Se você digitar o nome exato da página, talvez as descrições dos campos não sejam exibidas se houver mais de uma página com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="53160-165">If you've typed the exact name of the page, the field descriptions might not be shown if more than one page has the same name.</span></span> <span data-ttu-id="53160-166">Clique na seta no campo **Selecionar uma página** para abrir uma lista filtrada de páginas disponíveis.</span><span class="sxs-lookup"><span data-stu-id="53160-166">Click the arrow in the **Select a page** field to open a filtered list of the pages that are available.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="53160-167">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="53160-167">Additional resources</span></span>

[<span data-ttu-id="53160-168">Personalizar campo de ajuda</span><span class="sxs-lookup"><span data-stu-id="53160-168">Customize field help</span></span>](../../dev-itpro/user-interface/customize-field-help.md)

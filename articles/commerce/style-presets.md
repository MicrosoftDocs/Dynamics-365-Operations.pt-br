---
title: Trabalhar com estilos predefinidos
description: Este tópico descreve como trabalhar com layouts predefinidos de site no Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: b972c1de9f110ffb1ee1a52d9a9a1e3fa3fd9513
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411505"
---
# <a name="work-with-style-presets"></a><span data-ttu-id="1223c-103">Trabalhar com estilos predefinidos</span><span class="sxs-lookup"><span data-stu-id="1223c-103">Work with style presets</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="1223c-104">Este tópico descreve como trabalhar com layouts predefinidos de site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1223c-104">This topic describes how to work with site style presets in Microsoft Dynamics 365 Commerce site builder.</span></span>

## <a name="overview"></a><span data-ttu-id="1223c-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="1223c-105">Overview</span></span>

<span data-ttu-id="1223c-106">Uma predefinição de estilo é um conjunto armazenado de todos os valores de estilo que pode ser criado no tema de um site.</span><span class="sxs-lookup"><span data-stu-id="1223c-106">A style preset is a stored set of all authorable style values across a site's theme.</span></span> <span data-ttu-id="1223c-107">Ele pode ser usado para alterar imediatamente a aparência de um site do construtor de sites.</span><span class="sxs-lookup"><span data-stu-id="1223c-107">It can be used to immediately change the look of a site from site builder.</span></span> <span data-ttu-id="1223c-108">As predefinições de estilo permitem que o criador de sites do Commerce altere, visualize e ative rapidamente um conjunto de valores de estilo no site sem a necessidade de usar folhas de estilo em cascata (CSS) ou implantar temas.</span><span class="sxs-lookup"><span data-stu-id="1223c-108">Style presets let Commerce site builder authors quickly change, preview, and activate a set of style values across their site, without having to use Cascading Style Sheets (CSS) or deploy themes.</span></span> <span data-ttu-id="1223c-109">Estilos de fonte, estilos de botão e cores de site são exemplos típicos de variáveis de estilo que podem ser gerenciadas por meio de predefinições de estilo.</span><span class="sxs-lookup"><span data-stu-id="1223c-109">Font styles, button styles, and site colors are typical examples of style variables that can be managed through style presets.</span></span>

<span data-ttu-id="1223c-110">O conjunto de variáveis de estilo que está disponível em um site é determinado pelo tema e pela biblioteca de módulos que é implantado para o locatário de um site.</span><span class="sxs-lookup"><span data-stu-id="1223c-110">The set of style variables that is available in a site is determined by the theme and module library that is deployed to a site's tenant.</span></span> <span data-ttu-id="1223c-111">O kit de desenvolvimento de software (SDK) online do Dynamics 365 Commerce permite que os desenvolvedores implementem o máximo (ou o mínimo) de variáveis de estilo que podem ser criadas quanto forem necessárias para um determinado tema.</span><span class="sxs-lookup"><span data-stu-id="1223c-111">The Dynamics 365 Commerce online software development kit (SDK) lets developers implement as many (or as few) authorable style variables as they require for a given theme.</span></span> <span data-ttu-id="1223c-112">Ao habilitar mais variáveis de estilo, um desenvolvedor de temas poderá colocar as escolhas finais sobre os estilos de site nas mãos dos autores do construtor de sites.</span><span class="sxs-lookup"><span data-stu-id="1223c-112">By enabling more style variables, a theme developer can put final choices about site styles into the hands of site builder authors.</span></span> <span data-ttu-id="1223c-113">Portanto, os não desenvolvedores podem atualizar e visualizar estilos de site usando o conjunto de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="1223c-113">Therefore, non-developers can update and preview site styles by using the toolset.</span></span> <span data-ttu-id="1223c-114">O recurso também é útil para qualquer cenário no qual as alterações diretas nos temas ou CSS causarão sobrecarga desnecessária.</span><span class="sxs-lookup"><span data-stu-id="1223c-114">The capability is also useful for any scenario where direct changes to themes or CSS will cause unnecessary overhead.</span></span>

<span data-ttu-id="1223c-115">Os temas nos quais as variáveis de estilo são habilitadas exigem uma predefinição de estilo padrão.</span><span class="sxs-lookup"><span data-stu-id="1223c-115">Themes where authorable style variables are enabled require a default style preset.</span></span> <span data-ttu-id="1223c-116">Opcionalmente, eles podem incluir opções de predefinição adicionais como parte de um pacote de tema implantado.</span><span class="sxs-lookup"><span data-stu-id="1223c-116">They can optionally include additional preset options as part of a deployed theme package.</span></span> <span data-ttu-id="1223c-117">Por exemplo, um tema pode ser implantado e ter uma única predefinição de estilo padrão de "luz moderna".</span><span class="sxs-lookup"><span data-stu-id="1223c-117">For example, a theme can be deployed that has a single default "modern light" style preset.</span></span> <span data-ttu-id="1223c-118">Como alternativa, ele pode incluir opções de predefinição de estilo adicionais além da predefinição padrão, como "escuro moderno", "claro vintage" ou "escuro vintage".</span><span class="sxs-lookup"><span data-stu-id="1223c-118">Alternatively, it might include additional style preset options besides the default preset, such as "modern dark," "vintage light," or "vintage dark."</span></span> <span data-ttu-id="1223c-119">Essas predefinições de tema internas são criadas por desenvolvedores e podem ser usadas como pontos de partida para novos designs de site.</span><span class="sxs-lookup"><span data-stu-id="1223c-119">These built-in theme presets are created by developers and can be used as starting points for new site designs.</span></span>

<span data-ttu-id="1223c-120">No construtor de sites, os autores podem selecionar entre as predefinições internas de um tema ou podem criar suas próprias predefinições e personalizações de estilo usando as variáveis de estilo habilitadas.</span><span class="sxs-lookup"><span data-stu-id="1223c-120">In site builder, authors can select among a theme's built-in presets, or they can create their own style presets and customizations by using the enabled style variables.</span></span> <span data-ttu-id="1223c-121">Uma predefinição de estilo pode ser visualizada no construtor de sites antes de ser ativada no site ao vivo.</span><span class="sxs-lookup"><span data-stu-id="1223c-121">A style preset can be previewed in site builder before it's activated on the live site.</span></span> <span data-ttu-id="1223c-122">Depois que as alterações de estilo do autor forem revisadas, a predefinição de estilo poderá, então, ser definida como "ativa" para o site ao vivo.</span><span class="sxs-lookup"><span data-stu-id="1223c-122">After an author's style changes are reviewed, the style preset can then be set to "active" for the live site.</span></span>

## <a name="preview-a-style-preset"></a><span data-ttu-id="1223c-123">Visualizar uma predefinição de estilo</span><span class="sxs-lookup"><span data-stu-id="1223c-123">Preview a style preset</span></span>

<span data-ttu-id="1223c-124">Para visualizar uma predefinição de estilo no seu site no construtor de sites, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="1223c-124">To preview a style preset on your site in site builder, follow these steps.</span></span>

1. <span data-ttu-id="1223c-125">No painel de navegação esquerdo do site, vá para **Configurações do Site \> Design**.</span><span class="sxs-lookup"><span data-stu-id="1223c-125">In the left navigation pane for your site, go to **Site Settings \> Design**.</span></span>
1. <span data-ttu-id="1223c-126">Na guia **Predefinições de estilo** na parte superior do editor de design, na lista **Predefinições disponíveis**, selecione uma predefinição e, em seguida, selecione **Exibir** para ir para o editor de predefinições.</span><span class="sxs-lookup"><span data-stu-id="1223c-126">On the **Style presets** tab at the top of the design editor, in the **Available presets** list, select a preset, and then select **View** to go to the preset editor.</span></span>

    <span data-ttu-id="1223c-127">No momento, se não houver predefinições na lista **Predefinições disponíveis**, consulte [Criar uma predefinição de estilo personalizada](#create-a-custom-style-preset) para obter informações sobre como criar uma predefinição de estilo personalizada.</span><span class="sxs-lookup"><span data-stu-id="1223c-127">If there are currently no presets in the **Available presets** list, see [Create a custom style preset](#create-a-custom-style-preset) for information about how to create a custom style preset.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1223c-128">As predefinições incluídas no tema são indicadas por um emblema **Interno**.</span><span class="sxs-lookup"><span data-stu-id="1223c-128">Presets that were included with the theme are indicated by a **Built-in** badge.</span></span> <span data-ttu-id="1223c-129">Essas predefinições internas são somente leitura.</span><span class="sxs-lookup"><span data-stu-id="1223c-129">These built-in presets are read-only.</span></span> <span data-ttu-id="1223c-130">Para copiar uma predefinição interna como uma nova predefinição personalizável, selecione o botão de reticências (**...**) para a predefinição e selecione **Calvar como**.</span><span class="sxs-lookup"><span data-stu-id="1223c-130">To copy a built-in preset as a new customizable preset, select the ellipsis button (**...**) for the preset, and then select **Save as**.</span></span>

1. <span data-ttu-id="1223c-131">Na barra de comandos, selecione **Visualização**.</span><span class="sxs-lookup"><span data-stu-id="1223c-131">On the command bar, select **Preview**.</span></span>
1. <span data-ttu-id="1223c-132">Selecione uma URL do site a ser usada para visualizar a predefinição de estilo e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="1223c-132">Select a URL from your site to use to preview the style preset, and then select **OK**.</span></span>
1. <span data-ttu-id="1223c-133">Selecione a variante de URL específica do canal e da localidade a ser visualizada selecionando o nome da variante.</span><span class="sxs-lookup"><span data-stu-id="1223c-133">Select the channel-specific and locale-specific URL variant to preview by selecting the variant's name.</span></span> <span data-ttu-id="1223c-134">Uma nova janela de visualização do navegador é aberta, na qual a predefinição de estilo selecionada é aplicada à página especificada.</span><span class="sxs-lookup"><span data-stu-id="1223c-134">A new preview browser window is opened, where the selected style preset is applied to the specified page.</span></span>

> [!NOTE]
> <span data-ttu-id="1223c-135">A URL de visualização é persistente e autenticada.</span><span class="sxs-lookup"><span data-stu-id="1223c-135">The preview URL is persistent and authenticated.</span></span> <span data-ttu-id="1223c-136">Portanto, você pode copiá-la, colá-la e enviá-la a outros colaboradores autenticados para revisão antes de defini-la como "ativa" no seu site ao vivo.</span><span class="sxs-lookup"><span data-stu-id="1223c-136">Therefore, you can copy, paste, and send it to other authenticated co-workers for review before you set it to "active" on your live site.</span></span> <span data-ttu-id="1223c-137">A URL de visualização também é útil para verificar estilos em diferentes dispositivos, em navegadores diferentes e em telas diferentes.</span><span class="sxs-lookup"><span data-stu-id="1223c-137">The preview URL is also useful for checking styles on different devices, in different browsers, and on different screens.</span></span>

> [!TIP]
> <span data-ttu-id="1223c-138">Enquanto você edita uma predefinição de estilo, pode ser útil deixar a janela de visualização do navegador aberta em uma janela separada do navegador, para que você possa validar rapidamente suas alterações.</span><span class="sxs-lookup"><span data-stu-id="1223c-138">While you edit a style preset, you might find it helpful to leave the preview browser window for it open in a separate browser window, so that you can quickly validate your changes.</span></span> <span data-ttu-id="1223c-139">Depois de salvar as alterações em uma predefinição, atualize a janela do navegador de visualização para validar a experiência do usuário.</span><span class="sxs-lookup"><span data-stu-id="1223c-139">After you save your changes to a preset, refresh the open preview browser window to validate the user experience.</span></span>

## <a name="create-a-custom-style-preset"></a><span data-ttu-id="1223c-140">Criar uma predefinição de estilo personalizada</span><span class="sxs-lookup"><span data-stu-id="1223c-140">Create a custom style preset</span></span>

<span data-ttu-id="1223c-141">Para criar uma predefinição de estilo personalizada no construtor de sites, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="1223c-141">To create a custom style preset in site builder, follow these steps.</span></span>

1. <span data-ttu-id="1223c-142">No painel de navegação esquerdo do site, vá para **Configurações do Site \> Design**.</span><span class="sxs-lookup"><span data-stu-id="1223c-142">In the left navigation pane for your site, go to **Site Settings \> Design**.</span></span>
1. <span data-ttu-id="1223c-143">Na guia **Predefinições de estilo** na parte superior do editor de design, na barra de comandos, selecione **Nova predefinição**.</span><span class="sxs-lookup"><span data-stu-id="1223c-143">On the **Style presets** tab at the top of the design editor, on the command bar, select **New preset**.</span></span>
1. <span data-ttu-id="1223c-144">Insira um nome e um descrição para a nova predefinição e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="1223c-144">Enter a name and description for the new preset, and then select **Save**.</span></span> <span data-ttu-id="1223c-145">É criada uma nova predefinição personalizável que usa os valores padrão do tema como ponto de partida.</span><span class="sxs-lookup"><span data-stu-id="1223c-145">A new customizable preset is created that uses the theme's default values as a starting point.</span></span>

> [!NOTE]
> <span data-ttu-id="1223c-146">Você também pode criar uma nova predefinição de estilo personalizado de qualquer predefinição existente, selecionando o botão de reticências (**...**) para essa predefinição e selecionando **Salvar como**.</span><span class="sxs-lookup"><span data-stu-id="1223c-146">You can also create a new custom style preset from any existing preset by selecting the ellipsis button (**...**) for that preset and then selecting **Save as**.</span></span> <span data-ttu-id="1223c-147">Como alternativa, selecione **Salvar como** na barra de comandos no editor de predefinições.</span><span class="sxs-lookup"><span data-stu-id="1223c-147">Alternatively, select **Save as** on the command bar in the preset editor.</span></span>

## <a name="modify-global-and-module-type-style-values"></a><span data-ttu-id="1223c-148">Modificar valores de estilo de tipo global e de módulo</span><span class="sxs-lookup"><span data-stu-id="1223c-148">Modify global and module type style values</span></span>

<span data-ttu-id="1223c-149">Algumas variáveis de estilo de um tema são compartilhadas entre vários tipos de módulo.</span><span class="sxs-lookup"><span data-stu-id="1223c-149">Some of a theme's style variables are shared among multiple module types.</span></span> <span data-ttu-id="1223c-150">Essas variáveis de estilo são mencionadas como variáveis de estilo *globais*.</span><span class="sxs-lookup"><span data-stu-id="1223c-150">These style variables are referred to as *global* style variables.</span></span> <span data-ttu-id="1223c-151">Exemplos incluem cores de site principal, estilos de fonte padrão e estilos de botão.</span><span class="sxs-lookup"><span data-stu-id="1223c-151">Examples include primary site colors, default font styles, and button styles.</span></span> <span data-ttu-id="1223c-152">Ao definir variáveis globais, você poderá alterar a aparência entre vários tipos diferentes de módulo.</span><span class="sxs-lookup"><span data-stu-id="1223c-152">By setting global variables, you might change the look across many different module types.</span></span>

<span data-ttu-id="1223c-153">Alguns valores de estilo podem ser exclusivos para um tipo de módulo, ou talvez precisem substituir um valor global padrão.</span><span class="sxs-lookup"><span data-stu-id="1223c-153">Some style values can be unique to a module type, or they might have to optionally override a default global value.</span></span> <span data-ttu-id="1223c-154">Se o tema de um site tiver implementado variáveis de estilo de tipo de módulo, os autores do construtor de sites poderão personalizar o estilo de um tipo de módulo independentemente das configurações globais.</span><span class="sxs-lookup"><span data-stu-id="1223c-154">If a site's theme has implemented module type style variables, site builder authors can customize the style of a module type independently of the global settings.</span></span> <span data-ttu-id="1223c-155">As variáveis de tipo de módulo podem aumentar ou substituir as variáveis de estilo globais em um tema.</span><span class="sxs-lookup"><span data-stu-id="1223c-155">Module type variables can either augment or override the global style variables in a theme.</span></span>

> [!NOTE]
> <span data-ttu-id="1223c-156">A hierarquia de valores de estilo em um site se comporta da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="1223c-156">The hierarchy of style values in a site behaves in the following manner.</span></span> <span data-ttu-id="1223c-157">Os valores de estilo que aparecem mais distantes da direita substituem os valores de estilo à esquerda deles.</span><span class="sxs-lookup"><span data-stu-id="1223c-157">Style values that appear farther to the right override the style values to the left of them.</span></span>
>
> <span data-ttu-id="1223c-158">Valores padrão do tema \< Valores de estilo globais \< Valores de estilo de tipo de módulo \< Substituição de CSS</span><span class="sxs-lookup"><span data-stu-id="1223c-158">Theme default values \< Global style values \< Module type style values \< CSS override</span></span>

<span data-ttu-id="1223c-159">Para alterar os valores de tipo global ou de módulo de uma predefinição de estilo no construtor de sites, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="1223c-159">To change a style preset's global or module type values in site builder, follow these steps.</span></span>

1. <span data-ttu-id="1223c-160">No painel de navegação esquerdo do site, vá para **Configurações do Site \> Design**.</span><span class="sxs-lookup"><span data-stu-id="1223c-160">In the left navigation pane for your site, go to **Site Settings \> Design**.</span></span>
1. <span data-ttu-id="1223c-161">Na guia **Predefinições de estilo** na parte superior do editor de design, selecione **Exibir** para qualquer predefinição de estilo para ir para o editor de predefinições.</span><span class="sxs-lookup"><span data-stu-id="1223c-161">On the **Style presets** tab at the top of the design editor, select **View** for any style preset to go to the preset editor.</span></span>
1. <span data-ttu-id="1223c-162">Selecione **Visualização** e, em seguida, siga as etapas de seleção da URL para abrir uma visualização de janela inteira do navegador para a predefinição.</span><span class="sxs-lookup"><span data-stu-id="1223c-162">Select **Preview**, and then follow the URL selection steps to open a full-browser-window preview for your preset.</span></span> <span data-ttu-id="1223c-163">Deixe esta janela de visualização do navegador aberta.</span><span class="sxs-lookup"><span data-stu-id="1223c-163">Leave this preview browser window open.</span></span>
1. <span data-ttu-id="1223c-164">No editor de predefinições, selecione **Editar** no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="1223c-164">In the preset editor, select **Edit** in the upper right.</span></span>
1. <span data-ttu-id="1223c-165">Use os controles de variável de estilo no editor para alterar alguns valores de estilo global.</span><span class="sxs-lookup"><span data-stu-id="1223c-165">Use the style variable controls in the editor to change some global style values.</span></span>
1. <span data-ttu-id="1223c-166">Na parte superior do editor, na guia **Módulos** à direita da guia **Global**, selecione um tipo de módulo que deve ser estilizado.</span><span class="sxs-lookup"><span data-stu-id="1223c-166">At the top of the editor, on the **Modules** tab to the right of the **Global** tab, select a module type that must be styled.</span></span>
1. <span data-ttu-id="1223c-167">Use os controles de estilo para alterar alguns valores para o tipo de módulo.</span><span class="sxs-lookup"><span data-stu-id="1223c-167">Use the style controls to change some values for the module type.</span></span>
1. <span data-ttu-id="1223c-168">Quando estiver pronto para visualizar as alterações, selecione **Salvar** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="1223c-168">When you're ready to preview your changes, select **Save** on the command bar.</span></span>
1. <span data-ttu-id="1223c-169">Retorne à janela de visualização do navegador aberta e atualize-a.</span><span class="sxs-lookup"><span data-stu-id="1223c-169">Return to the open preview browser window, and refresh it.</span></span> <span data-ttu-id="1223c-170">A visualização de tela inteira do navegador é útil para verificar alterações de estilo em diferentes pontos de quebra de exibição, em diferentes navegadores e em diferentes plataformas de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1223c-170">The full-browser-window preview is useful for checking style changes at different view breakpoints, in different browsers, and on different device platforms.</span></span>
1. <span data-ttu-id="1223c-171">Quando todas as alterações tiverem sido concluídas e validadas, selecione **Terminar edição** no canto superior direito do editor.</span><span class="sxs-lookup"><span data-stu-id="1223c-171">When all changes have been completed and validated, select **Finish editing** in the upper right of the editor.</span></span>

> [!NOTE]
> <span data-ttu-id="1223c-172">Se você estiver editando a predefinição de estilo atualmente ativa no seu site, verá um emblema **Ativo** azul no editor.</span><span class="sxs-lookup"><span data-stu-id="1223c-172">If you're editing the style preset that is currently active on your site, you will see a blue **Active** badge in the editor.</span></span> <span data-ttu-id="1223c-173">Esse emblema indica que a predefinição está atualmente ativa no seu site.</span><span class="sxs-lookup"><span data-stu-id="1223c-173">This badge indicates that the preset is currently live on your website.</span></span> <span data-ttu-id="1223c-174">Se você alterar a predefinição ativa, selecione **Publicar** para enviar essas alterações ao seu site ao vivo.</span><span class="sxs-lookup"><span data-stu-id="1223c-174">If you change the active preset, select **Publish** to push those changes to your live site.</span></span>

## <a name="make-a-new-style-preset-active-on-your-live-site"></a><span data-ttu-id="1223c-175">Tornar uma nova predefinição de estilo ativa no seu site ao vivo</span><span class="sxs-lookup"><span data-stu-id="1223c-175">Make a new style preset active on your live site</span></span>

<span data-ttu-id="1223c-176">Para definir uma predefinição de estilo como a nova predefinição ativa no seu site, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="1223c-176">To set a style preset as the new active preset on your site, follow these steps.</span></span>

- <span data-ttu-id="1223c-177">Selecione o **botão Definir como ativo** em um dos seguintes locais:</span><span class="sxs-lookup"><span data-stu-id="1223c-177">Select the **Set as active button** in one of these places:</span></span>

    - <span data-ttu-id="1223c-178">A barra de comandos no editor de predefinição de estilo</span><span class="sxs-lookup"><span data-stu-id="1223c-178">The command bar in the style preset editor</span></span>
    - <span data-ttu-id="1223c-179">O menu de reticências (**...**) para qualquer predefinição disponível na exibição principal da guia **Predefinições de estilo** em **Configurações do Site \> Design**</span><span class="sxs-lookup"><span data-stu-id="1223c-179">The ellipsis menu (**...**) for any available preset in the main view on the **Style presets** tab at **Site Settings \> Design**</span></span>

<span data-ttu-id="1223c-180">Os valores de estilo da predefinição são ativados no seu site público.</span><span class="sxs-lookup"><span data-stu-id="1223c-180">The preset's style values are made active across your public-facing website.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1223c-181">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="1223c-181">Additional resources</span></span>

[<span data-ttu-id="1223c-182">Adicionar um logotipo</span><span class="sxs-lookup"><span data-stu-id="1223c-182">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="1223c-183">Selecionar um tema de site</span><span class="sxs-lookup"><span data-stu-id="1223c-183">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="1223c-184">Trabalhar com arquivos de substituição CSS</span><span class="sxs-lookup"><span data-stu-id="1223c-184">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="1223c-185">Adicionar um favicon</span><span class="sxs-lookup"><span data-stu-id="1223c-185">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="1223c-186">Adicionar uma mensagem de boas-vindas</span><span class="sxs-lookup"><span data-stu-id="1223c-186">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="1223c-187">Adicionar um aviso de direitos autorais</span><span class="sxs-lookup"><span data-stu-id="1223c-187">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="1223c-188">Adicionar idiomas ao seu site</span><span class="sxs-lookup"><span data-stu-id="1223c-188">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="1223c-189">Adicionar o código de script a páginas do site para oferecer suporte à telemetria</span><span class="sxs-lookup"><span data-stu-id="1223c-189">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)
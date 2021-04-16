---
title: Trabalhar com arquivos de substituição CSS
description: Este tópico descreve por que, quando e como usar Folhas de Estilos em Cascata (CSS) na substituição de arquivos no Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-12-12
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: ef96070fe77b46622667301c7c7c402909ee7dfc
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799484"
---
# <a name="work-with-css-override-files"></a><span data-ttu-id="05065-103">Trabalhar com arquivos de substituição do CSS</span><span class="sxs-lookup"><span data-stu-id="05065-103">Work with CSS override files</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="05065-104">Este tópico descreve por que, quando e como usar Folhas de Estilos em Cascata (CSS) na substituição de arquivos no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="05065-104">This topic describes why, when, and how to use Cascading Style Sheets (CSS) override files in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="05065-105">Normalmente, os estilos de site permanentes devem ser manipulados por meio do tema de um site.</span><span class="sxs-lookup"><span data-stu-id="05065-105">Permanent site styles should usually be handled through a site's theme.</span></span> <span data-ttu-id="05065-106">Os temas fornecem as configurações base de CSS e estilo para os módulos em qualquer página do seu site.</span><span class="sxs-lookup"><span data-stu-id="05065-106">Themes provide the foundational CSS and style settings for the modules on any page of your site.</span></span> <span data-ttu-id="05065-107">Os temas são criados usando o kit de desenvolvimento de software Dynamics 365 Commerce online (SDK) e são implantados em seus sites por meio do Lifecycle Services (LCS) do Microsoft Dynamics.</span><span class="sxs-lookup"><span data-stu-id="05065-107">Themes are created by using the Dynamics 365 Commerce online software development kit (SDK), and they are deployed to your websites through Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="05065-108">Recursos de depuração de tema e configurações de interface de módulo nos desenvolvedores de site da ajuda do SDK criam pacotes de design de site personalizáveis e coesos.</span><span class="sxs-lookup"><span data-stu-id="05065-108">Theme debugging capabilities and module interface configurations in the SDK help site developers create customizable and cohesive site design packages.</span></span> <span data-ttu-id="05065-109">Quando esses pacotes de design são implantados em um site, os autores do site podem se concentrar na criação, na edição e na publicação de conteúdo, e não no desenvolvimento do site.</span><span class="sxs-lookup"><span data-stu-id="05065-109">When these design packages are deployed to a site, site authors can focus on creating, editing, and publishing content instead of site development.</span></span>

<span data-ttu-id="05065-110">Devido ao ciclo de vida normal de um tema, a dependência dos desenvolvedores de fazer alterações de estilo por meio do pipeline de implantação do SDK e do LCS pode ser proibitiva em alguns cenários.</span><span class="sxs-lookup"><span data-stu-id="05065-110">Given the usual lifecycle of a theme, the dependency on developers to make style changes through the SDK and LCS deployment pipeline can be prohibitive in some scenarios.</span></span> <span data-ttu-id="05065-111">Os protótipos de site ou hotfixes podem parecer complicados se o SDK não estiver configurado ou se você não tiver tempo para esperar por uma implantação do LCS.</span><span class="sxs-lookup"><span data-stu-id="05065-111">Site prototypes or hotfixes can seem cumbersome if the SDK isn't configured, or if you don't have time to wait for an LCS deployment.</span></span>

<span data-ttu-id="05065-112">Nessas situações, arquivos de substituição do CSS podem ajudar.</span><span class="sxs-lookup"><span data-stu-id="05065-112">In these scenarios, CSS override files can help.</span></span> <span data-ttu-id="05065-113">Nas ferramentas de criação do Commerce, os usuários autenticados podem carregar um arquivo CSS, visualizá-lo e depois ativá-lo para substituir o tema de um site.</span><span class="sxs-lookup"><span data-stu-id="05065-113">In the Commerce authoring tools, authenticated users can upload a CSS file, preview it, and then activate it to override a site's theme.</span></span> <span data-ttu-id="05065-114">A sobrecarga da implantação do SDK ou LCS não é necessária.</span><span class="sxs-lookup"><span data-stu-id="05065-114">The overhead of SDK or LCS deployment isn't required.</span></span> <span data-ttu-id="05065-115">As substituições especificadas em um arquivo de substituição do CSS podem ser tão pequenas quanto uma alteração em um único estilo de texto ou como uma revisão de marca completa.</span><span class="sxs-lookup"><span data-stu-id="05065-115">The overrides that are specified in a CSS override file can be as small as a change to a single text style or as wide-ranging as a complete brand overhaul.</span></span>

<span data-ttu-id="05065-116">Antes de usar os arquivos de substituição CSS, esteja ciente das seguintes limitações:</span><span class="sxs-lookup"><span data-stu-id="05065-116">Before you use CSS override files, be aware of the following limitations:</span></span>

- <span data-ttu-id="05065-117">Somente um arquivo de substituição CSS pode estar ativo em um site de cada vez.</span><span class="sxs-lookup"><span data-stu-id="05065-117">Only one CSS override file can be active on a site at a time.</span></span> <span data-ttu-id="05065-118">Portanto, todas as substituições ativas devem estar presentes em um único arquivo de substituição.</span><span class="sxs-lookup"><span data-stu-id="05065-118">Therefore, all active overrides must be present in a single override file.</span></span>
- <span data-ttu-id="05065-119">Embora seja possível visualizar as substituições nas ferramentas de criação do Commerce, não há recursos de depuração dedicados para ajudar a identificar os bugs introduzidos por essas substituições.</span><span class="sxs-lookup"><span data-stu-id="05065-119">Although you can preview the overrides in the Commerce authoring tools, there are no dedicated debugging features to help identify any bugs that the overrides introduce.</span></span> <span data-ttu-id="05065-120">Em outras palavras, ao usar os arquivos de substituição CSS, você não tem o mesmo conjunto de ferramentas que o SDK oferece para validação de módulo e criação de páginas.</span><span class="sxs-lookup"><span data-stu-id="05065-120">In other words, when you use CSS override files, you don't have the same toolset that the SDK provides for module and authoring validation.</span></span>

<span data-ttu-id="05065-121">No entanto, os arquivos de substituição CSS fornecem uma maneira rápida de criar um protótipo de um projeto ou implementar um hotfix antes que uma atualização de tema completa seja desenvolvida e implantada.</span><span class="sxs-lookup"><span data-stu-id="05065-121">Nevertheless, CSS override files provide a quick way to prototype a design or implement a hotfix before a full theme update is developed and deployed.</span></span>

## <a name="create-a-css-override-file"></a><span data-ttu-id="05065-122">Criar um arquivo de substituição do CSS</span><span class="sxs-lookup"><span data-stu-id="05065-122">Create a CSS override file</span></span>

<span data-ttu-id="05065-123">Para criar um arquivo de substituição CSS, você pode usar qualquer ambiente de desenvolvimento integrado (IDE), editor de texto ou editor de código fonte.</span><span class="sxs-lookup"><span data-stu-id="05065-123">To create a CSS override file, you can use any integrated development environment (IDE), text editor, or source code editor.</span></span> <span data-ttu-id="05065-124">Uma abordagem típica é usar os depuradores da Web padrão no seu navegador para identificar seletores de estilo, propriedades e valores no site existente.</span><span class="sxs-lookup"><span data-stu-id="05065-124">A typical approach is to use standard web debuggers in your browser to identify style selectors, properties, and values on your existing site.</span></span> <span data-ttu-id="05065-125">A maioria dos navegadores permite que você altere valores e visualize-os no depurador.</span><span class="sxs-lookup"><span data-stu-id="05065-125">Most browsers let you change values and preview them in the debugger.</span></span> <span data-ttu-id="05065-126">Depois de identificar as alterações que deseja fazer, você pode salvá-las no seu próprio arquivo CSS.</span><span class="sxs-lookup"><span data-stu-id="05065-126">After you've identified the changes that you want to make, you can save them to your own CSS file.</span></span>

## <a name="upload-a-css-override-file"></a><span data-ttu-id="05065-127">Carregar um arquivo de substituição CSS</span><span class="sxs-lookup"><span data-stu-id="05065-127">Upload a CSS override file</span></span>

<span data-ttu-id="05065-128">Para carregar um arquivo CSS em seu site no Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="05065-128">To upload a CSS file to your site in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="05065-129">Nas ferramentas de criação, vá para nosso site.</span><span class="sxs-lookup"><span data-stu-id="05065-129">In the authoring tools, go to your site.</span></span>
1. <span data-ttu-id="05065-130">No painel de navegação à esquerda, selecione **Design**.</span><span class="sxs-lookup"><span data-stu-id="05065-130">In the navigation pane on the left, select **Design**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="05065-131">Dependendo da versão das ferramentas de criação do Commerce que você está usando, talvez você precise expandir **Configurações** no painel de navegação antes de poder selecionar **Design**.</span><span class="sxs-lookup"><span data-stu-id="05065-131">Depending on the version of the Commerce authoring tools that you're using, you might have to expand **Settings** in the navigation pane before you can select **Design**.</span></span>

1. <span data-ttu-id="05065-132">Na parte superior do painel de design principal, selecione a guia **Substituir CSS**, caso ainda não esteja selecionada.</span><span class="sxs-lookup"><span data-stu-id="05065-132">At the top of the main design pane, select the **CSS override** tab, if it isn't already selected.</span></span>
1. <span data-ttu-id="05065-133">Under **Substituição de CSS disponível**, selecione **Carregar arquivo CSS**.</span><span class="sxs-lookup"><span data-stu-id="05065-133">Under **Available CSS overrides**, select **Upload CSS file**.</span></span> <span data-ttu-id="05065-134">Uma janela do explorador de arquivos é exibida.</span><span class="sxs-lookup"><span data-stu-id="05065-134">A File Explorer window appears.</span></span>
1. <span data-ttu-id="05065-135">No explorador de arquivos, procure e selecione um arquivo CSS e depois selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="05065-135">In File Explorer, browse to and select a CSS file, and then select **Open**.</span></span> <span data-ttu-id="05065-136">O arquivo carregado CSS agora aparece em **Substituição de CSS disponível**.</span><span class="sxs-lookup"><span data-stu-id="05065-136">The uploaded CSS file now appears under **Available CSS overrides**.</span></span>

## <a name="preview-a-css-override-file"></a><span data-ttu-id="05065-137">Visualizar um arquivo de substituição CSS</span><span class="sxs-lookup"><span data-stu-id="05065-137">Preview a CSS override file</span></span>

<span data-ttu-id="05065-138">Para visualizar um arquivo de substituição CSS antes de torná-lo ativo no seu site ao vivo, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="05065-138">To preview a CSS override file before you make it active on your live site, follow these steps.</span></span>

1. <span data-ttu-id="05065-139">No painel de navegação à esquerda, selecione **Design**, e depois, na guia **Substituição de CSS**, em **Substituição de CSS disponível**, encontra o arquivo CSS que deseja visualizar.</span><span class="sxs-lookup"><span data-stu-id="05065-139">In the navigation pane on the left, select **Design**, and then, on the **CSS override** tab, under **Available CSS overrides**, find the CSS file that you want to preview.</span></span>
1. <span data-ttu-id="05065-140">Ao lado do nome do arquivo do CSS, selecione **Visualizar site**.</span><span class="sxs-lookup"><span data-stu-id="05065-140">Next to the CSS file name, select **Preview site**.</span></span>
1. <span data-ttu-id="05065-141">Na caixa de seleção **Selecionar uma URL**, selecione a URL do site no qual você deseja que a substituição seja aplicada, e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="05065-141">In the **Select a URL** dialog box, select the URL of the site that you want to see the override applied to, and then select **OK**.</span></span>
1. <span data-ttu-id="05065-142">Se houver várias grades para a URL selecionada, selecione a grade desejada na caixa de diálogo **Visualizar grades** exibida.</span><span class="sxs-lookup"><span data-stu-id="05065-142">If there are multiple variants for the selected URL, select the desired variant in the **Preview variations** dialog box that appears.</span></span>

<span data-ttu-id="05065-143">Uma nova guia ou janela do navegador é aberta, na qual você pode validar suas substituições de estilo no site.</span><span class="sxs-lookup"><span data-stu-id="05065-143">A new browser tab or window is opened, where you can validate your style overrides against your site.</span></span> <span data-ttu-id="05065-144">Em seguida, você poderá compartilhar a URL com outros usuários autenticados do Commerce para revisão e comentários.</span><span class="sxs-lookup"><span data-stu-id="05065-144">You can then share the URL with other authenticated Commerce users for review and feedback.</span></span>

## <a name="activate-a-css-override-file-on-your-live-site"></a><span data-ttu-id="05065-145">Ativar um arquivo de substituição CSS no site ao vivo</span><span class="sxs-lookup"><span data-stu-id="05065-145">Activate a CSS override file on your live site</span></span>

<span data-ttu-id="05065-146">Depois de exibir e aprovar o arquivo de substituição CSS, você poderá ativá-lo no seu site.</span><span class="sxs-lookup"><span data-stu-id="05065-146">After you've previewed and approved the CSS override file, you can activate it on your live site.</span></span>

> [!NOTE]
> <span data-ttu-id="05065-147">Somente um arquivo de substituição CSS pode estar ativo em seu site de cada vez.</span><span class="sxs-lookup"><span data-stu-id="05065-147">Only one CSS override file can be active on your site at a time.</span></span> <span data-ttu-id="05065-148">Se você ativar um novo arquivo de substituição, o arquivo de substituição anterior será desativado.</span><span class="sxs-lookup"><span data-stu-id="05065-148">If you activate a new override file, the previous override file is inactivated.</span></span> <span data-ttu-id="05065-149">Portanto, verifique se todas as substituições necessárias estão presentes em um único arquivo de substituição CSS.</span><span class="sxs-lookup"><span data-stu-id="05065-149">Therefore, make sure that all required overrides are present in a single CSS override file.</span></span>

<span data-ttu-id="05065-150">Para ativar um arquivo de substituição CSS, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="05065-150">To activate a CSS override file, follow these steps.</span></span>

1. <span data-ttu-id="05065-151">No painel de navegação à esquerda, selecione **Design**, e depois, na guia **Substituição de CSS**, em **Substituição de CSS disponível**, encontra o arquivo CSS que deseja ativar.</span><span class="sxs-lookup"><span data-stu-id="05065-151">In the navigation pane on the left, select **Design**, and then, on the **CSS override** tab, under **Available CSS overrides**, find the CSS file that you want to activate.</span></span>
1. <span data-ttu-id="05065-152">No nome do arquivo CSS, selecione **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="05065-152">Under the CSS file name, select **Activate**.</span></span> <span data-ttu-id="05065-153">O arquivo de substituição se tornará imediatamente ativo no seu site ao vivo.</span><span class="sxs-lookup"><span data-stu-id="05065-153">The override file immediately becomes active on your live site.</span></span>

## <a name="deactivate-a-css-override-file-on-your-live-site"></a><span data-ttu-id="05065-154">Desativar um arquivo de substituição CSS no site ao vivo</span><span class="sxs-lookup"><span data-stu-id="05065-154">Deactivate a CSS override file on your live site</span></span>

<span data-ttu-id="05065-155">Para desativar um arquivo de substituição CSS no site, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="05065-155">To deactivate a CSS override file on your site, follow these steps.</span></span>

1. <span data-ttu-id="05065-156">No painel de navegação à esquerda, selecione **Design**, e depois, na guia **Substituição de CSS**, em **Substituição de CSS disponível**, encontra o arquivo CSS que deseja desativar.</span><span class="sxs-lookup"><span data-stu-id="05065-156">In the navigation pane on the left, select **Design**, and then, on the **CSS override** tab, under **Available CSS overrides**, find the CSS file that you want to deactivate.</span></span>
1. <span data-ttu-id="05065-157">No nome do arquivo CSS, selecione **Desativar**.</span><span class="sxs-lookup"><span data-stu-id="05065-157">Under the CSS file name, select **Deactivate**.</span></span> <span data-ttu-id="05065-158">O arquivo de substituição se tornará imediatamente inativo no seu site ao vivo.</span><span class="sxs-lookup"><span data-stu-id="05065-158">The override file immediately becomes inactive on your live site.</span></span>

> [!TIP]
> <span data-ttu-id="05065-159">Para acessar opções adicionais para arquivos de substituição CSS, selecione as reticências (**...**) ao lado do nome do arquivo CSS.</span><span class="sxs-lookup"><span data-stu-id="05065-159">To access additional options for CSS override files, select the ellipsis (**...**) next to the CSS file name.</span></span> <span data-ttu-id="05065-160">As opções **Baixar**, **Renomear** e **Substituir** são úteis para mudanças rápidas a um arquivo de substituição CSS existente.</span><span class="sxs-lookup"><span data-stu-id="05065-160">The **Download**, **Rename**, and **Replace** options are useful for quick changes to an existing CSS override file.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="05065-161">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="05065-161">Additional resources</span></span>

[<span data-ttu-id="05065-162">Adicionar um logotipo</span><span class="sxs-lookup"><span data-stu-id="05065-162">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="05065-163">Selecionar um tema de site</span><span class="sxs-lookup"><span data-stu-id="05065-163">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="05065-164">Trabalhar com estilos predefinidos</span><span class="sxs-lookup"><span data-stu-id="05065-164">Work with style presets</span></span>](style-presets.md)

[<span data-ttu-id="05065-165">Adicionar um favicon</span><span class="sxs-lookup"><span data-stu-id="05065-165">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="05065-166">Adicionar uma mensagem de boas-vindas</span><span class="sxs-lookup"><span data-stu-id="05065-166">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="05065-167">Adicionar um aviso de direitos autorais</span><span class="sxs-lookup"><span data-stu-id="05065-167">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="05065-168">Adicionar idiomas ao seu site</span><span class="sxs-lookup"><span data-stu-id="05065-168">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="05065-169">Adicionar o código de script a páginas do site para oferecer suporte à telemetria</span><span class="sxs-lookup"><span data-stu-id="05065-169">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

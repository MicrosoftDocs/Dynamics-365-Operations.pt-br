---
title: Trabalhar com arquivos de substituição CSS
description: Este tópico descreve porque, quando e como usar Folhas de Estilos em Cascata (CSS) substituem arquivos no Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-12-12
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 3c40145ea76296c1b8df9284af820534e3c869d4
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001843"
---
# <a name="work-with-css-override-files"></a><span data-ttu-id="86f20-103">Trabalhar com arquivos de substituição CSS</span><span class="sxs-lookup"><span data-stu-id="86f20-103">Work with CSS override files</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="86f20-104">Este tópico descreve porque, quando e como usar Folhas de Estilos em Cascata (CSS) substituem arquivos no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="86f20-104">This topic describes why, when, and how to use Cascading Style Sheets (CSS) override files in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="86f20-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="86f20-105">Overview</span></span>

<span data-ttu-id="86f20-106">Normalmente, os estilos de site permanentes devem ser manipulados por meio do tema de um site.</span><span class="sxs-lookup"><span data-stu-id="86f20-106">Permanent site styles should usually be handled through a site's theme.</span></span> <span data-ttu-id="86f20-107">Os temas fornecem as configurações base de CSS e estilo para os módulos em qualquer página do seu site.</span><span class="sxs-lookup"><span data-stu-id="86f20-107">Themes provide the foundational CSS and style settings for the modules on any page of your site.</span></span> <span data-ttu-id="86f20-108">Os temas são criados usando o kit de desenvolvimento de software Dynamics 365 Commerce online (SDK) e são implantados em seus sites por meio do Lifecycle Services (LCS) do Microsoft Dynamics.</span><span class="sxs-lookup"><span data-stu-id="86f20-108">Themes are created by using the Dynamics 365 Commerce online software development kit (SDK), and they are deployed to your websites through Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="86f20-109">Recursos de depuração de tema e configurações de interface de módulo nos desenvolvedores de site da ajuda do SDK criam pacotes de design de site personalizáveis e coesos.</span><span class="sxs-lookup"><span data-stu-id="86f20-109">Theme debugging capabilities and module interface configurations in the SDK help site developers create customizable and cohesive site design packages.</span></span> <span data-ttu-id="86f20-110">Quando esses pacotes de design são implantados em um site, os autores do site podem se concentrar na criação, na edição e na publicação de conteúdo, e não no desenvolvimento do site.</span><span class="sxs-lookup"><span data-stu-id="86f20-110">When these design packages are deployed to a site, site authors can focus on creating, editing, and publishing content instead of site development.</span></span>

<span data-ttu-id="86f20-111">Devido ao ciclo de vida normal de um tema, a dependência dos desenvolvedores de fazer alterações de estilo por meio do pipeline de implantação do SDK e do LCS pode ser proibitiva em alguns cenários.</span><span class="sxs-lookup"><span data-stu-id="86f20-111">Given the usual lifecycle of a theme, the dependency on developers to make style changes through the SDK and LCS deployment pipeline can be prohibitive in some scenarios.</span></span> <span data-ttu-id="86f20-112">Os protótipos de site ou hotfixes podem parecer complicados se o SDK não estiver configurado ou se você não tiver tempo para esperar por uma implantação do LCS.</span><span class="sxs-lookup"><span data-stu-id="86f20-112">Site prototypes or hotfixes can seem cumbersome if the SDK isn't configured, or if you don't have time to wait for an LCS deployment.</span></span>

<span data-ttu-id="86f20-113">Nessas situações, arquivos de substituição do CSS podem ajudar.</span><span class="sxs-lookup"><span data-stu-id="86f20-113">In these scenarios, CSS override files can help.</span></span> <span data-ttu-id="86f20-114">Nas ferramentas de criação do Commerce, os usuários autenticados podem carregar um arquivo CSS, visualizá-lo e depois ativá-lo para substituir o tema de um site.</span><span class="sxs-lookup"><span data-stu-id="86f20-114">In the Commerce authoring tools, authenticated users can upload a CSS file, preview it, and then activate it to override a site's theme.</span></span> <span data-ttu-id="86f20-115">A sobrecarga da implantação do SDK ou LCS não é necessária.</span><span class="sxs-lookup"><span data-stu-id="86f20-115">The overhead of SDK or LCS deployment isn't required.</span></span> <span data-ttu-id="86f20-116">As substituições especificadas em um arquivo de substituição do CSS podem ser tão pequenas quanto uma alteração em um único estilo de texto ou como uma revisão de marca completa.</span><span class="sxs-lookup"><span data-stu-id="86f20-116">The overrides that are specified in a CSS override file can be as small as a change to a single text style or as wide-ranging as a complete brand overhaul.</span></span>

<span data-ttu-id="86f20-117">Antes de usar os arquivos de substituição CSS, esteja ciente das seguintes limitações:</span><span class="sxs-lookup"><span data-stu-id="86f20-117">Before you use CSS override files, be aware of the following limitations:</span></span>

- <span data-ttu-id="86f20-118">Somente um arquivo de substituição CSS pode estar ativo em um site de cada vez.</span><span class="sxs-lookup"><span data-stu-id="86f20-118">Only one CSS override file can be active on a site at a time.</span></span> <span data-ttu-id="86f20-119">Portanto, todas as substituições ativas devem estar presentes em um único arquivo de substituição.</span><span class="sxs-lookup"><span data-stu-id="86f20-119">Therefore, all active overrides must be present in a single override file.</span></span>
- <span data-ttu-id="86f20-120">Embora seja possível visualizar as substituições nas ferramentas de criação do Commerce, não há recursos de depuração dedicados para ajudar a identificar os bugs introduzidos por essas substituições.</span><span class="sxs-lookup"><span data-stu-id="86f20-120">Although you can preview the overrides in the Commerce authoring tools, there are no dedicated debugging features to help identify any bugs that the overrides introduce.</span></span> <span data-ttu-id="86f20-121">Em outras palavras, ao usar os arquivos de substituição CSS, você não tem o mesmo conjunto de ferramentas que o SDK oferece para validação de módulo e criação de páginas.</span><span class="sxs-lookup"><span data-stu-id="86f20-121">In other words, when you use CSS override files, you don't have the same toolset that the SDK provides for module and authoring validation.</span></span>

<span data-ttu-id="86f20-122">No entanto, os arquivos de substituição CSS fornecem uma maneira rápida de criar um protótipo de um projeto ou implementar um hotfix antes que uma atualização de tema completa seja desenvolvida e implantada.</span><span class="sxs-lookup"><span data-stu-id="86f20-122">Nevertheless, CSS override files provide a quick way to prototype a design or implement a hotfix before a full theme update is developed and deployed.</span></span>

## <a name="create-a-css-override-file"></a><span data-ttu-id="86f20-123">Criar um arquivo de substituição do CSS</span><span class="sxs-lookup"><span data-stu-id="86f20-123">Create a CSS override file</span></span>

<span data-ttu-id="86f20-124">Para criar um arquivo de substituição CSS, você pode usar qualquer ambiente de desenvolvimento integrado (IDE), editor de texto ou editor de código fonte.</span><span class="sxs-lookup"><span data-stu-id="86f20-124">To create a CSS override file, you can use any integrated development environment (IDE), text editor, or source code editor.</span></span> <span data-ttu-id="86f20-125">Uma abordagem típica é usar os depuradores da Web padrão no seu navegador para identificar seletores de estilo, propriedades e valores no site existente.</span><span class="sxs-lookup"><span data-stu-id="86f20-125">A typical approach is to use standard web debuggers in your browser to identify style selectors, properties, and values on your existing site.</span></span> <span data-ttu-id="86f20-126">A maioria dos navegadores permite que você altere valores e visualize-os no depurador.</span><span class="sxs-lookup"><span data-stu-id="86f20-126">Most browsers let you change values and preview them in the debugger.</span></span> <span data-ttu-id="86f20-127">Depois de identificar as alterações que deseja fazer, você pode salvá-las no seu próprio arquivo CSS.</span><span class="sxs-lookup"><span data-stu-id="86f20-127">After you've identified the changes that you want to make, you can save them to your own CSS file.</span></span>

## <a name="upload-a-css-override-file"></a><span data-ttu-id="86f20-128">Carregar um arquivo de substituição CSS</span><span class="sxs-lookup"><span data-stu-id="86f20-128">Upload a CSS override file</span></span>

<span data-ttu-id="86f20-129">Para carregar um arquivo CSS em seu site no Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="86f20-129">To upload a CSS file to your site in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="86f20-130">Nas ferramentas de criação, vá para nosso site.</span><span class="sxs-lookup"><span data-stu-id="86f20-130">In the authoring tools, go to your site.</span></span>
1. <span data-ttu-id="86f20-131">No painel de navegação à esquerda, selecione **Design**.</span><span class="sxs-lookup"><span data-stu-id="86f20-131">In the navigation pane on the left, select **Design**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="86f20-132">Dependendo da versão das ferramentas de criação do Commerce que você está usando, talvez você precise expandir **Configurações** no painel de navegação antes de poder selecionar **Design**.</span><span class="sxs-lookup"><span data-stu-id="86f20-132">Depending on the version of the Commerce authoring tools that you're using, you might have to expand **Settings** in the navigation pane before you can select **Design**.</span></span>

1. <span data-ttu-id="86f20-133">Na parte superior do painel de design principal, selecione a guia **Substituir CSS**, caso ainda não esteja selecionada.</span><span class="sxs-lookup"><span data-stu-id="86f20-133">At the top of the main design pane, select the **CSS override** tab, if it isn't already selected.</span></span>
1. <span data-ttu-id="86f20-134">Under **Substituição de CSS disponível**, selecione **Carregar arquivo CSS**.</span><span class="sxs-lookup"><span data-stu-id="86f20-134">Under **Available CSS overrides**, select **Upload CSS file**.</span></span> <span data-ttu-id="86f20-135">Uma janela do explorador de arquivos é exibida.</span><span class="sxs-lookup"><span data-stu-id="86f20-135">A File Explorer window appears.</span></span>
1. <span data-ttu-id="86f20-136">No explorador de arquivos, procure e selecione um arquivo CSS e depois selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="86f20-136">In File Explorer, browse to and select a CSS file, and then select **Open**.</span></span> <span data-ttu-id="86f20-137">O arquivo carregado CSS agora aparece em **Substituição de CSS disponível**.</span><span class="sxs-lookup"><span data-stu-id="86f20-137">The uploaded CSS file now appears under **Available CSS overrides**.</span></span>

## <a name="preview-a-css-override-file"></a><span data-ttu-id="86f20-138">Visualizar um arquivo de substituição CSS</span><span class="sxs-lookup"><span data-stu-id="86f20-138">Preview a CSS override file</span></span>

<span data-ttu-id="86f20-139">Para visualizar um arquivo de substituição CSS antes de torná-lo ativo no seu site ao vivo, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="86f20-139">To preview a CSS override file before you make it active on your live site, follow these steps.</span></span>

1. <span data-ttu-id="86f20-140">No painel de navegação à esquerda, selecione **Design**, e depois, na guia **Substituição de CSS**, em **Substituição de CSS disponível**, encontra o arquivo CSS que deseja visualizar.</span><span class="sxs-lookup"><span data-stu-id="86f20-140">In the navigation pane on the left, select **Design**, and then, on the **CSS override** tab, under **Available CSS overrides**, find the CSS file that you want to preview.</span></span>
1. <span data-ttu-id="86f20-141">Ao lado do nome do arquivo do CSS, selecione **Visualizar site**.</span><span class="sxs-lookup"><span data-stu-id="86f20-141">Next to the CSS file name, select **Preview site**.</span></span>
1. <span data-ttu-id="86f20-142">Na caixa de seleção **Selecionar uma URL**, selecione a URL do site no qual você deseja que a substituição seja aplicada, e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="86f20-142">In the **Select a URL** dialog box, select the URL of the site that you want to see the override applied to, and then select **OK**.</span></span>
1. <span data-ttu-id="86f20-143">Se houver várias grades para a URL selecionada, selecione a grade desejada na caixa de diálogo **Visualizar grades** exibida.</span><span class="sxs-lookup"><span data-stu-id="86f20-143">If there are multiple variants for the selected URL, select the desired variant in the **Preview variations** dialog box that appears.</span></span>

<span data-ttu-id="86f20-144">Uma nova guia ou janela do navegador é aberta, na qual você pode validar suas substituições de estilo no site.</span><span class="sxs-lookup"><span data-stu-id="86f20-144">A new browser tab or window is opened, where you can validate your style overrides against your site.</span></span> <span data-ttu-id="86f20-145">Em seguida, você poderá compartilhar a URL com outros usuários autenticados do Commerce para revisão e comentários.</span><span class="sxs-lookup"><span data-stu-id="86f20-145">You can then share the URL with other authenticated Commerce users for review and feedback.</span></span>

## <a name="activate-a-css-override-file-on-your-live-site"></a><span data-ttu-id="86f20-146">Ativar um arquivo de substituição CSS no site ao vivo</span><span class="sxs-lookup"><span data-stu-id="86f20-146">Activate a CSS override file on your live site</span></span>

<span data-ttu-id="86f20-147">Depois de exibir e aprovar o arquivo de substituição CSS, você poderá ativá-lo no seu site.</span><span class="sxs-lookup"><span data-stu-id="86f20-147">After you've previewed and approved the CSS override file, you can activate it on your live site.</span></span>

> [!NOTE]
> <span data-ttu-id="86f20-148">Somente um arquivo de substituição CSS pode estar ativo em seu site de cada vez.</span><span class="sxs-lookup"><span data-stu-id="86f20-148">Only one CSS override file can be active on your site at a time.</span></span> <span data-ttu-id="86f20-149">Se você ativar um novo arquivo de substituição, o arquivo de substituição anterior será desativado.</span><span class="sxs-lookup"><span data-stu-id="86f20-149">If you activate a new override file, the previous override file is inactivated.</span></span> <span data-ttu-id="86f20-150">Portanto, verifique se todas as substituições necessárias estão presentes em um único arquivo de substituição CSS.</span><span class="sxs-lookup"><span data-stu-id="86f20-150">Therefore, make sure that all required overrides are present in a single CSS override file.</span></span>

<span data-ttu-id="86f20-151">Para ativar um arquivo de substituição CSS, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="86f20-151">To activate a CSS override file, follow these steps.</span></span>

1. <span data-ttu-id="86f20-152">No painel de navegação à esquerda, selecione **Design**, e depois, na guia **Substituição de CSS**, em **Substituição de CSS disponível**, encontra o arquivo CSS que deseja ativar.</span><span class="sxs-lookup"><span data-stu-id="86f20-152">In the navigation pane on the left, select **Design**, and then, on the **CSS override** tab, under **Available CSS overrides**, find the CSS file that you want to activate.</span></span>
1. <span data-ttu-id="86f20-153">No nome do arquivo CSS, selecione **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="86f20-153">Under the CSS file name, select **Activate**.</span></span> <span data-ttu-id="86f20-154">O arquivo de substituição se tornará imediatamente ativo no seu site ao vivo.</span><span class="sxs-lookup"><span data-stu-id="86f20-154">The override file immediately becomes active on your live site.</span></span>

## <a name="deactivate-a-css-override-file-on-your-live-site"></a><span data-ttu-id="86f20-155">Desativar um arquivo de substituição CSS no site ao vivo</span><span class="sxs-lookup"><span data-stu-id="86f20-155">Deactivate a CSS override file on your live site</span></span>

<span data-ttu-id="86f20-156">Para desativar um arquivo de substituição CSS no site, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="86f20-156">To deactivate a CSS override file on your site, follow these steps.</span></span>

1. <span data-ttu-id="86f20-157">No painel de navegação à esquerda, selecione **Design**, e depois, na guia **Substituição de CSS**, em **Substituição de CSS disponível**, encontra o arquivo CSS que deseja desativar.</span><span class="sxs-lookup"><span data-stu-id="86f20-157">In the navigation pane on the left, select **Design**, and then, on the **CSS override** tab, under **Available CSS overrides**, find the CSS file that you want to deactivate.</span></span>
1. <span data-ttu-id="86f20-158">No nome do arquivo CSS, selecione **Desativar**.</span><span class="sxs-lookup"><span data-stu-id="86f20-158">Under the CSS file name, select **Deactivate**.</span></span> <span data-ttu-id="86f20-159">O arquivo de substituição se tornará imediatamente inativo no seu site ao vivo.</span><span class="sxs-lookup"><span data-stu-id="86f20-159">The override file immediately becomes inactive on your live site.</span></span>

> [!TIP]
> <span data-ttu-id="86f20-160">Para acessar opções adicionais para arquivos de substituição CSS, selecione as reticências (**...**) ao lado do nome do arquivo CSS.</span><span class="sxs-lookup"><span data-stu-id="86f20-160">To access additional options for CSS override files, select the ellipsis (**...**) next to the CSS file name.</span></span> <span data-ttu-id="86f20-161">As opções **Baixar**, **Renomear** e **Substituir** são úteis para mudanças rápidas a um arquivo de substituição CSS existente.</span><span class="sxs-lookup"><span data-stu-id="86f20-161">The **Download**, **Rename**, and **Replace** options are useful for quick changes to an existing CSS override file.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="86f20-162">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="86f20-162">Additional resources</span></span>

[<span data-ttu-id="86f20-163">Adicionar um logotipo</span><span class="sxs-lookup"><span data-stu-id="86f20-163">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="86f20-164">Selecionar um tema de site</span><span class="sxs-lookup"><span data-stu-id="86f20-164">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="86f20-165">Adicionar um favicon</span><span class="sxs-lookup"><span data-stu-id="86f20-165">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="86f20-166">Adicionar uma mensagem de boas-vindas</span><span class="sxs-lookup"><span data-stu-id="86f20-166">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="86f20-167">Adicionar um aviso de direitos autorais</span><span class="sxs-lookup"><span data-stu-id="86f20-167">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="86f20-168">Adicionar idiomas ao seu site</span><span class="sxs-lookup"><span data-stu-id="86f20-168">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="86f20-169">Adicionar o código de script a páginas do site para oferecer suporte à telemetria</span><span class="sxs-lookup"><span data-stu-id="86f20-169">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

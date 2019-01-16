---
title: Abrir URL no POS
description: "Este tópico fornece uma visão geral de melhorias feitas à funcionalidade de pesquisa de produto e cliente no Microsoft Dynamics 365 for Retail."
author: AamirAllaq
manager: AnnBe
ms.date: 11/14/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application user
ms.reviewer: sericks
ms.search.scope: Core, Operations, Retail
ms.custom: 141393
ms.assetid: 
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2018-10-30
ms.dyn365.ops.version: 8.1.1
ms.translationtype: HT
ms.sourcegitcommit: 190d0b59ad2e232b33b3c0d1700cbaf95c45aeca
ms.openlocfilehash: d2b692ac86244eca31780a558112167391fc6d77
ms.contentlocale: pt-br
ms.lasthandoff: 01/04/2019

---

# <a name="open-url-in-pos"></a><span data-ttu-id="47172-103">Abrir URL no POS</span><span class="sxs-lookup"><span data-stu-id="47172-103">Open URL in POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="47172-104">Este tópico descreve como você pode configurar um botão no ponto de venda de Retail (POS) para abrir uma URL.</span><span class="sxs-lookup"><span data-stu-id="47172-104">This topic describes how you can configure a button in Retail point of sale (POS) to open a URL.</span></span> <span data-ttu-id="47172-105">Este recurso não requer uma personalização de código, e pode ser configurado por alguém em uma função de não desenvolvedor.</span><span class="sxs-lookup"><span data-stu-id="47172-105">This feature does not require a code customization, and can be configured by someone in a non-developer role.</span></span>

<span data-ttu-id="47172-106">Esse recurso permite a configuração de um botão no POS, usando o criador de grade de botões para abrir uma URL.</span><span class="sxs-lookup"><span data-stu-id="47172-106">This feature allows configuration of a button in POS, using the button grid designer to open a URL.</span></span> <span data-ttu-id="47172-107">Atualmente, isso é suportado nas seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="47172-107">Currently, this is supported in the following configurations:</span></span>

- <span data-ttu-id="47172-108">Abrir em nova janela.</span><span class="sxs-lookup"><span data-stu-id="47172-108">Open in new window.</span></span>
- <span data-ttu-id="47172-109">Abra dentro do POS.</span><span class="sxs-lookup"><span data-stu-id="47172-109">Open within POS.</span></span>
- <span data-ttu-id="47172-110">Abrir um aplicativo nativo.</span><span class="sxs-lookup"><span data-stu-id="47172-110">Open a native app.</span></span>

## <a name="open-in-new-window"></a><span data-ttu-id="47172-111">Abrir em nova janela</span><span class="sxs-lookup"><span data-stu-id="47172-111">Open in new window</span></span>

<span data-ttu-id="47172-112">Essa configuração define se abre a URL em uma nova janela ou dentro do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="47172-112">This configuration defines whether to open the URL in a new window or within the app.</span></span> <span data-ttu-id="47172-113">Quando configurado para abrir uma URL dentro do aplicativo, o painel de navegação lateral e barra superior de POS estão disponíveis e visíveis para interação de usuário.</span><span class="sxs-lookup"><span data-stu-id="47172-113">When configured to open a web URL within the app, the side navigation panel and top bar of POS are visible and available for user interaction.</span></span> <span data-ttu-id="47172-114">Quando configurado para abrir em uma nova janela, a URL será aberta em uma nova janela no Modern POS para Windows, e em uma guia de um novo navegador em todos outros clientes de POS.</span><span class="sxs-lookup"><span data-stu-id="47172-114">When configured to open in a new window, the URL will open in a new app window on Modern POS for Windows, and in a new browser tab in all other POS clients.</span></span> <span data-ttu-id="47172-115">Para habilitar isso, você deve configurar a URL na opção **Abrir em nova janela** selecionada.</span><span class="sxs-lookup"><span data-stu-id="47172-115">To enable this, you must configure the URL with the **Open in new window** option selected.</span></span>

## <a name="open-within-pos"></a><span data-ttu-id="47172-116">Abra dentro do POS</span><span class="sxs-lookup"><span data-stu-id="47172-116">Open within POS</span></span>

<span data-ttu-id="47172-117">Abrir uma URL da Web dentro do POS atualmente só é suportado para Modern POS no Windows.</span><span class="sxs-lookup"><span data-stu-id="47172-117">Opening a web URL within POS is currently only supported for Modern POS on Windows.</span></span> <span data-ttu-id="47172-118">Em outros clientes, esse recurso está em desenvolvimento e planejado para liberação em atualizações futuras.</span><span class="sxs-lookup"><span data-stu-id="47172-118">On other clients, this capability is under development and planned for release in future updates.</span></span> <span data-ttu-id="47172-119">Para habilitar isso, você deve configurar a URL na opção **Abrir em nova janela** não selecionada.</span><span class="sxs-lookup"><span data-stu-id="47172-119">To enable this, you must configure the URL with the **Open in new window** option not selected.</span></span>

## <a name="open-a-native-app"></a><span data-ttu-id="47172-120">Abrir um aplicativo nativo</span><span class="sxs-lookup"><span data-stu-id="47172-120">Open a native app</span></span>

<span data-ttu-id="47172-121">Este recurso também permite que você especifique URLs da Web para abrir um descritivo nativo.</span><span class="sxs-lookup"><span data-stu-id="47172-121">This feature also allows you to specify non-web URLs to open a native app.</span></span> <span data-ttu-id="47172-122">Por exemplo, você pode especificar os protocolos de URL como MailTo, SIP, IM ou MSTEAMS, que podem ser lidados por aplicativos respectivos nativos no dispositivo host.</span><span class="sxs-lookup"><span data-stu-id="47172-122">For example, you can specify URL protocols such as MailTo, SIP, IM, or MSTEAMS, which can then be handled by respective native apps on the host device.</span></span> <span data-ttu-id="47172-123">Para habilitar isso, você deve configurar a URL na opção **Abrir em nova janela** selecionada.</span><span class="sxs-lookup"><span data-stu-id="47172-123">To enable this, you must configure the URL with the **Open in new window** option selected.</span></span>

- <span data-ttu-id="47172-124">Para computadores Windows, consulte [Exportar ou importar Associações de aplicação padrão](https://docs.microsoft.com/windows-hardware/manufacture/desktop/export-or-import-default-application-associations) para definir as associações de protocolo padrão se você estiver configurando seu computador usando Deployment Image Servicing and Management (DISM).</span><span class="sxs-lookup"><span data-stu-id="47172-124">For Windows computers, see [Export or Import Default Application Associations](https://docs.microsoft.com/windows-hardware/manufacture/desktop/export-or-import-default-application-associations) to set the default protocol associations if you are setting up your computer using Deployment Image Servicing and Management (DISM).</span></span>
- <span data-ttu-id="47172-125">Se estiver usando MDM, como Intune para gerenciar os computadores do Windows, consulte [CSP de política - ApplicationDefaults](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults).</span><span class="sxs-lookup"><span data-stu-id="47172-125">If you are using MDM, such as Intune to manage your Windows computers, see [Policy CSP - ApplicationDefaults](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults).</span></span>
- <span data-ttu-id="47172-126">Se você for um desenvolvedor que cria um local personalizado, consulte [Iniciar o aplicativo padrão para uma URI](https://docs.microsoft.com/windows/uwp/launch-resume/launch-default-app).</span><span class="sxs-lookup"><span data-stu-id="47172-126">If you are a developer building a custom website, see [Launch the default app for a URI](https://docs.microsoft.com/windows/uwp/launch-resume/launch-default-app).</span></span>

## <a name="open-a-native-app-seamlessly"></a><span data-ttu-id="47172-127">Abrir um aplicativo nativo perfeitamente</span><span class="sxs-lookup"><span data-stu-id="47172-127">Open a native app seamlessly</span></span>

<span data-ttu-id="47172-128">Windows, iOS e Android também permitem abrir aplicativos de forma perfeita, com base em uma associação de protocolo de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="47172-128">Windows, iOS, and Android also allow opening of apps more seamlessly, based on app protocol association.</span></span> <span data-ttu-id="47172-129">Se seu aplicativo não estiver configurado para lidar com a abertura de um navegador da Web, você pode precisar de um desenvolvedor para configurar essa parte.</span><span class="sxs-lookup"><span data-stu-id="47172-129">If your app is not already configured to handle opening from a web browser, you may need a developer to configure this.</span></span>

- <span data-ttu-id="47172-130">Para Windows, consulte [Habilitar aplicativo para websites usando manipuladores de URI de aplicativo](https://docs.microsoft.com/windows/uwp/launch-resume/web-to-app-linking).</span><span class="sxs-lookup"><span data-stu-id="47172-130">For Windows, see [Enable apps for websites using app URI handlers](https://docs.microsoft.com/windows/uwp/launch-resume/web-to-app-linking).</span></span>
- <span data-ttu-id="47172-131">Para iOS, consulte [Links universais para desenvolvedores](https://developer.apple.com/ios/universal-links/).</span><span class="sxs-lookup"><span data-stu-id="47172-131">For iOS, see [Universal Links for Developers](https://developer.apple.com/ios/universal-links/).</span></span>
- <span data-ttu-id="47172-132">Para Android, consulte [Links de aplicativo de android para manipuladores](https://developer.android.com/training/app-links/).</span><span class="sxs-lookup"><span data-stu-id="47172-132">For Android, see [Handling Android App Links](https://developer.android.com/training/app-links/).</span></span>

| <span data-ttu-id="47172-133">Cliente</span><span class="sxs-lookup"><span data-stu-id="47172-133">Client</span></span>                | <span data-ttu-id="47172-134">Abrir em nova janela</span><span class="sxs-lookup"><span data-stu-id="47172-134">Open in new window</span></span> | <span data-ttu-id="47172-135">Abrir aplicativo nativo</span><span class="sxs-lookup"><span data-stu-id="47172-135">Open native app</span></span> | <span data-ttu-id="47172-136">Abra dentro do POS</span><span class="sxs-lookup"><span data-stu-id="47172-136">Open within POS</span></span> | <span data-ttu-id="47172-137">Detalhes</span><span class="sxs-lookup"><span data-stu-id="47172-137">Details</span></span>                           |
|-----------------------|--------------------|-----------------|-----------------|-----------------------------------|
| <span data-ttu-id="47172-138">Modern POS no Windows</span><span class="sxs-lookup"><span data-stu-id="47172-138">Modern POS on Windows</span></span> | <span data-ttu-id="47172-139">✓\*</span><span class="sxs-lookup"><span data-stu-id="47172-139">✓\*</span></span>                | <span data-ttu-id="47172-140">✓</span><span class="sxs-lookup"><span data-stu-id="47172-140">✓</span></span>               | <span data-ttu-id="47172-141">✓</span><span class="sxs-lookup"><span data-stu-id="47172-141">✓</span></span>              | <span data-ttu-id="47172-142">\* Abre em uma nova janela Modern POS</span><span class="sxs-lookup"><span data-stu-id="47172-142">\* Opens in new Modern POS window</span></span> |
| <span data-ttu-id="47172-143">PDV em Nuvem</span><span class="sxs-lookup"><span data-stu-id="47172-143">Cloud POS</span></span>             | <span data-ttu-id="47172-144">✓\*</span><span class="sxs-lookup"><span data-stu-id="47172-144">✓\*</span></span>                | <span data-ttu-id="47172-145">✓</span><span class="sxs-lookup"><span data-stu-id="47172-145">✓</span></span>               | <span data-ttu-id="47172-146">X</span><span class="sxs-lookup"><span data-stu-id="47172-146">X</span></span>              | <span data-ttu-id="47172-147">\* Abre em uma nova guia do navegador</span><span class="sxs-lookup"><span data-stu-id="47172-147">\* Opens in new browser tab</span></span>        |
| <span data-ttu-id="47172-148">Modern POS no iOS</span><span class="sxs-lookup"><span data-stu-id="47172-148">Modern POS on iOS</span></span>     | <span data-ttu-id="47172-149">✓\*</span><span class="sxs-lookup"><span data-stu-id="47172-149">✓\*</span></span>                | <span data-ttu-id="47172-150">✓</span><span class="sxs-lookup"><span data-stu-id="47172-150">✓</span></span>               | <span data-ttu-id="47172-151">X</span><span class="sxs-lookup"><span data-stu-id="47172-151">X</span></span>              | <span data-ttu-id="47172-152">\* Abre em uma nova guia do navegador</span><span class="sxs-lookup"><span data-stu-id="47172-152">\* Opens in new browser tab</span></span>        |
| <span data-ttu-id="47172-153">Modern POS no Android</span><span class="sxs-lookup"><span data-stu-id="47172-153">Modern POS on Android</span></span> | <span data-ttu-id="47172-154">✓\*</span><span class="sxs-lookup"><span data-stu-id="47172-154">✓\*</span></span>                | <span data-ttu-id="47172-155">✓</span><span class="sxs-lookup"><span data-stu-id="47172-155">✓</span></span>               | <span data-ttu-id="47172-156">X</span><span class="sxs-lookup"><span data-stu-id="47172-156">X</span></span>              | <span data-ttu-id="47172-157">\* Abre em uma nova guia do navegador</span><span class="sxs-lookup"><span data-stu-id="47172-157">\* Opens in new browser tab</span></span>        |

## <a name="before-you-begin"></a><span data-ttu-id="47172-158">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="47172-158">Before you begin</span></span>

<span data-ttu-id="47172-159">Antes de começar, verifique como configurar [Layouts de tela para ponto de venda (POS)](pos-screen-layouts.md).</span><span class="sxs-lookup"><span data-stu-id="47172-159">Before you begin, review how to configure [Screen layouts for the point of sale (POS)](pos-screen-layouts.md).</span></span>

## <a name="open-url-in-pos"></a><span data-ttu-id="47172-160">Abrir URL no POS</span><span class="sxs-lookup"><span data-stu-id="47172-160">Open URL in POS</span></span>

<span data-ttu-id="47172-161">Para configurar uma URL a ser aberta no POS, execute estas etapas.</span><span class="sxs-lookup"><span data-stu-id="47172-161">To configure a URL to be opened in POS, perform the following steps.</span></span>

1. <span data-ttu-id="47172-162">Na matriz, acesse **Varejo\> Configuração do canal \> Configuração do PDV \> PDV \> Layouts da Tela**.</span><span class="sxs-lookup"><span data-stu-id="47172-162">In head office, go to **Retail \> Channel Setup \> POS Setup \> POS \> Screen Layouts**.</span></span>
2. <span data-ttu-id="47172-163">Selecione **Grades de Botões \> Designer**.</span><span class="sxs-lookup"><span data-stu-id="47172-163">Select **Button Grids \> Designer**.</span></span>
3. <span data-ttu-id="47172-164">Crie um novo botão.</span><span class="sxs-lookup"><span data-stu-id="47172-164">Create a new button.</span></span>
4. <span data-ttu-id="47172-165">Selecione o botão **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="47172-165">Select **Button** properties.</span></span>
5. <span data-ttu-id="47172-166">Selecione **Abrir URL** como a ação.</span><span class="sxs-lookup"><span data-stu-id="47172-166">Select **Open URL** as the action.</span></span>
6. <span data-ttu-id="47172-167">Insira a URL que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="47172-167">Enter the URL that you want to use.</span></span>
7. <span data-ttu-id="47172-168">Configure se deseja abrir a URL em uma nova janela.</span><span class="sxs-lookup"><span data-stu-id="47172-168">Configure whether to open the URL in a new window.</span></span>


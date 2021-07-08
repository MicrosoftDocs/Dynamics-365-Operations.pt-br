---
title: O que há de novo ou mudou no aplicativo móvel Warehouse Management
description: Este tópico lista os recursos novos e alterados para cada versão lançada do aplicativo móvel Warehouse Management para o Microsoft Dynamics 365 Supply Chain Management.
author: ivanv-microsoft
ms.date: 06/07/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ivanv
ms.search.validFrom: 2021-06-07
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 61124728942c0b8162de9f687ae752773c47d07e
ms.sourcegitcommit: 4cbd83e21a78459e4711a2dedba0f5a7acc3c841
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2021
ms.locfileid: "6261762"
---
# <a name="whats-new-or-changed-in-the-warehouse-management-mobile-app"></a><span data-ttu-id="6ab91-103">O que há de novo ou mudou no aplicativo móvel Warehouse Management</span><span class="sxs-lookup"><span data-stu-id="6ab91-103">What's new or changed in the Warehouse Management mobile app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6ab91-104">Este tópico lista recursos novos, correções, aprimoramentos e problemas conhecidos para cada versão lançada do aplicativo móvel Warehouse Management para o Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="6ab91-104">This topic lists new features, fixes, improvements, and known issues for each released version of the Warehouse Management mobile app for Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="version-2060"></a><span data-ttu-id="6ab91-105">Versão 2.0.6.0</span><span class="sxs-lookup"><span data-stu-id="6ab91-105">Version 2.0.6.0</span></span>

### <a name="new-features-fixes-and-improvements-in-version-2060"></a><span data-ttu-id="6ab91-106">Novos recursos, correções e aprimoramentos na versão 2.0.6.0</span><span class="sxs-lookup"><span data-stu-id="6ab91-106">New features, fixes, and improvements in version 2.0.6.0</span></span>

<span data-ttu-id="6ab91-107">Esta versão introduz os novos recursos, correções e aprimoramentos a seguir:</span><span class="sxs-lookup"><span data-stu-id="6ab91-107">This version introduces the following new features, fixes, and improvements:</span></span>

- <span data-ttu-id="6ab91-108">O modo de demonstração agora mostra todos os rótulos no idioma do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6ab91-108">Demo mode now shows all labels in the device language.</span></span>
- <span data-ttu-id="6ab91-109">É menos provável que você receba a seguinte mensagem de erro: "Não é possível encontrar uma exibição adequada para o tamanho especificado."</span><span class="sxs-lookup"><span data-stu-id="6ab91-109">You're less likely to receive the following error message: "Cannot find a suitable view for the specified size."</span></span>
- <span data-ttu-id="6ab91-110">A altura mínima para cartões de trabalho foi aumentada (para casos em que três ou menos campos estão configurados para aparecer na lista de trabalho).</span><span class="sxs-lookup"><span data-stu-id="6ab91-110">The minimum height for work cards has been increased (for cases where three or fewer fields are configured to appear in the work list).</span></span>
- <span data-ttu-id="6ab91-111">As margens (em degradê) na parte inferior dos cartões de detalhes foram melhoradas.</span><span class="sxs-lookup"><span data-stu-id="6ab91-111">Margins (fade out) at the bottom of details cards have been improved.</span></span>
- <span data-ttu-id="6ab91-112">Os símbolos inválidos em arquivos XML que são trocados com o servidor agora são tratados adequadamente.</span><span class="sxs-lookup"><span data-stu-id="6ab91-112">Invalid symbols in XML files that are exchanged with the server are now handled gracefully.</span></span> <span data-ttu-id="6ab91-113">(Por exemplo, caracteres não imprimíveis agora são tratados adequadamente e não fazem mais com que o aplicativo pare de responder.)</span><span class="sxs-lookup"><span data-stu-id="6ab91-113">(For example, non-printable characters are now handled gracefully and no longer cause the app to stop responding.)</span></span>
- <span data-ttu-id="6ab91-114">Os erros HTTP (como "erro 503") quando uma solicitação de servidor é enviada agora são tratados adequadamente.</span><span class="sxs-lookup"><span data-stu-id="6ab91-114">HTTP errors (such as "error 503") when a server request is submitted are now handled gracefully.</span></span>
- <span data-ttu-id="6ab91-115">Enquanto um erro está sendo mostrado, a lista de opções não é mais mostrada automaticamente para controles de caixa combinação.</span><span class="sxs-lookup"><span data-stu-id="6ab91-115">While an error is being shown, the options list is no longer automatically shown for combo box controls.</span></span>
- <span data-ttu-id="6ab91-116">O aplicativo não para mais de responder por causa da orientação de exibição selecionada nas configurações do usuário.</span><span class="sxs-lookup"><span data-stu-id="6ab91-116">The app no longer stops responding because of the display orientation that is selected in user settings.</span></span>
- <span data-ttu-id="6ab91-117">As imagens do produto agora são mostradas em ambientes de autoatendimento.</span><span class="sxs-lookup"><span data-stu-id="6ab91-117">Product images are now shown in self-service environments.</span></span> <span data-ttu-id="6ab91-118">(Esta alteração aplica-se apenas a versões de baixa resolução.</span><span class="sxs-lookup"><span data-stu-id="6ab91-118">(This change applies to low-resolution versions only.</span></span> <span data-ttu-id="6ab91-119">O serviço de gerenciamento de arquivos não permite imagens em tamanho real em ambientes de autoatendimento.)</span><span class="sxs-lookup"><span data-stu-id="6ab91-119">The file management service doesn't support full-sized images in self-service environments.)</span></span>
- <span data-ttu-id="6ab91-120">Um problema que envolvia separações curtas de quantidade zero foi corrigido.</span><span class="sxs-lookup"><span data-stu-id="6ab91-120">An issue that involved zero-quantity short picks has been fixed.</span></span>
- <span data-ttu-id="6ab91-121">O aplicativo não para mais de responder quando um cartão de detalhes mostra vários campos idênticos.</span><span class="sxs-lookup"><span data-stu-id="6ab91-121">The app no longer stops responding when a details card shows multiple identical fields.</span></span>

### <a name="known-issues-in-version-2060"></a><span data-ttu-id="6ab91-122">Problemas conhecidos na versão 2.0.6.0</span><span class="sxs-lookup"><span data-stu-id="6ab91-122">Known issues in version 2.0.6.0</span></span>

<span data-ttu-id="6ab91-123">Os seguintes problemas conhecidos existem nesta versão:</span><span class="sxs-lookup"><span data-stu-id="6ab91-123">The following known issues exist in this version:</span></span>

- <span data-ttu-id="6ab91-124">O aplicativo (especialmente a lista de trabalho) torna-se mais lento com o tempo.</span><span class="sxs-lookup"><span data-stu-id="6ab91-124">The app (especially the work list) becomes slower over time.</span></span>
- <span data-ttu-id="6ab91-125">**Versão do Windows:** quando uma pistola USB é usada para digitalizar no Windows, resultados inconsistentes fazem com que os símbolos digitalizados sejam misturados.</span><span class="sxs-lookup"><span data-stu-id="6ab91-125">**Windows version:** When a USB gun is used for scanning on Windows, inconsistent results cause scanned symbols to be mixed up.</span></span>

## <a name="version-2050"></a><span data-ttu-id="6ab91-126">Versão 2.0.5.0</span><span class="sxs-lookup"><span data-stu-id="6ab91-126">Version 2.0.5.0</span></span>

<span data-ttu-id="6ab91-127">Esta versão introduz os novos recursos, correções e aprimoramentos a seguir:</span><span class="sxs-lookup"><span data-stu-id="6ab91-127">This version introduces the following new features, fixes, and improvements:</span></span>

- <span data-ttu-id="6ab91-128">O segredo do cliente não está mais escondido na configuração de definições de conexão.</span><span class="sxs-lookup"><span data-stu-id="6ab91-128">The client secret is no longer hidden in the connection settings setup.</span></span>
- <span data-ttu-id="6ab91-129">Agora você pode manter pressionado qualquer texto para vê-lo completamente.</span><span class="sxs-lookup"><span data-stu-id="6ab91-129">You can now long-press on any text to see it fully.</span></span>
- <span data-ttu-id="6ab91-130">A mensagem de erro quando não há permissões de armazenamento foi melhorada.</span><span class="sxs-lookup"><span data-stu-id="6ab91-130">The error message when storage permissions are missing has been improved.</span></span>
- <span data-ttu-id="6ab91-131">Novas sequências de controle foram adicionadas para alguns fluxos.</span><span class="sxs-lookup"><span data-stu-id="6ab91-131">New control sequences have been added for some flows.</span></span>
- <span data-ttu-id="6ab91-132">O botão de envio não fica mais disponível incorretamente devido ao tamanho da janela.</span><span class="sxs-lookup"><span data-stu-id="6ab91-132">The submit button no longer incorrectly becomes available because of the window size.</span></span>
- <span data-ttu-id="6ab91-133">Os controles deslizantes agora podem continuar em telas menores quando são usados tamanhos de botões maiores.</span><span class="sxs-lookup"><span data-stu-id="6ab91-133">Sliders can now proceed on smaller screens when larger button sizes are used.</span></span>
- <span data-ttu-id="6ab91-134">A sobreposição de quatro botões não aparece mais cortada.</span><span class="sxs-lookup"><span data-stu-id="6ab91-134">The four-button overlay is no longer cut off.</span></span>
- <span data-ttu-id="6ab91-135">O teclado agora dá suporte ao botão delete.</span><span class="sxs-lookup"><span data-stu-id="6ab91-135">The keyboard now supports the delete button.</span></span>
- <span data-ttu-id="6ab91-136">Um problema de brilho que pode ocorrer quando o teclado é pressionado foi corrigido.</span><span class="sxs-lookup"><span data-stu-id="6ab91-136">A brightness issue that could occur when the keyboard is pressed has been fixed.</span></span>
- <span data-ttu-id="6ab91-137">Vários problemas de dados de demonstração foram corrigidos.</span><span class="sxs-lookup"><span data-stu-id="6ab91-137">Various demo data issues have been fixed.</span></span>
- <span data-ttu-id="6ab91-138">Um problema que afetava campos numéricos na página de detalhes foi corrigido.</span><span class="sxs-lookup"><span data-stu-id="6ab91-138">An issue that affected numeric fields on the details page has been fixed.</span></span>
- <span data-ttu-id="6ab91-139">O teclado virtual não desaparece mais ocasionalmente em alguns dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6ab91-139">The screen keyboard no longer occasionally disappears on some devices.</span></span>
- <span data-ttu-id="6ab91-140">Vários bugs de interface de usuário foram corrigidos, como bugs que afetavam a cor de fundo e posicionamento.</span><span class="sxs-lookup"><span data-stu-id="6ab91-140">Various user interface (UI) bugs have been fixed, such as bugs that affected the background color and positioning.</span></span>
- <span data-ttu-id="6ab91-141">A interface do usuário no idioma russo foi melhorada.</span><span class="sxs-lookup"><span data-stu-id="6ab91-141">The Russian-language UI has been improved.</span></span>
- <span data-ttu-id="6ab91-142">Vários problemas que fizeram com que o sistema parasse de responder foram corrigidos.</span><span class="sxs-lookup"><span data-stu-id="6ab91-142">Various issues that caused the system to stop responding have been fixed.</span></span>
- <span data-ttu-id="6ab91-143">Um problema relacionado à reabertura da calculadora foi corrigido.</span><span class="sxs-lookup"><span data-stu-id="6ab91-143">An issue that was related to reopening the calculator has been fixed.</span></span>
- <span data-ttu-id="6ab91-144">**Versão do Android:** um problema que fazia com que o Android 4.4 parasse de responder na inicialização foi corrigido.</span><span class="sxs-lookup"><span data-stu-id="6ab91-144">**Android version:** An issue that caused Android 4.4 to stop responding on startup has been fixed.</span></span>
- <span data-ttu-id="6ab91-145">**Versão do Android:** o dimensionamento mínimo foi reduzido para 50%.</span><span class="sxs-lookup"><span data-stu-id="6ab91-145">**Android version:** Minimum scaling has been reduced to 50 percent.</span></span>

## <a name="version-2040"></a><span data-ttu-id="6ab91-146">Versão 2.0.4.0</span><span class="sxs-lookup"><span data-stu-id="6ab91-146">Version 2.0.4.0</span></span>

<span data-ttu-id="6ab91-147">A versão 2.0.4.0 foi a primeira versão geralmente disponível do aplicativo móvel Warehouse Management.</span><span class="sxs-lookup"><span data-stu-id="6ab91-147">Version 2.0.4.0 was the first generally available release of the Warehouse Management mobile app.</span></span>

### <a name="new-features-fixes-and-improvements-in-version-2040"></a><span data-ttu-id="6ab91-148">Novos recursos, correções e aprimoramentos na versão 2.0.4.0</span><span class="sxs-lookup"><span data-stu-id="6ab91-148">New features, fixes, and improvements in version 2.0.4.0</span></span>

<span data-ttu-id="6ab91-149">Esta versão introduz os seguintes novos recursos, correções e aprimoramentos que não estavam disponíveis na versão prévia:</span><span class="sxs-lookup"><span data-stu-id="6ab91-149">This version introduces the following new features, fixes, and improvements that weren't available in the preview version:</span></span>

- <span data-ttu-id="6ab91-150">Se um cartão de detalhes incluir dois rótulos que tenham dados idênticos, um dos rótulos será oculto.</span><span class="sxs-lookup"><span data-stu-id="6ab91-150">If a details card includes two labels that have identical data, one of the labels is hidden.</span></span>
- <span data-ttu-id="6ab91-151">Os caracteres especiais agora são mostrados por padrão, e a opção de escondê-los foi removida das configurações do usuário.</span><span class="sxs-lookup"><span data-stu-id="6ab91-151">Special characters are now shown by default, and the option to hide them has been removed from user settings.</span></span>
- <span data-ttu-id="6ab91-152">Os botões de envio desativados agora são mostrados como não disponíveis na exibição compacta portátil.</span><span class="sxs-lookup"><span data-stu-id="6ab91-152">Disabled submit buttons are now shown as unavailable in compact arm-held view.</span></span>
- <span data-ttu-id="6ab91-153">Uma alteração na lógica de sequenciamento para controles garante um dimensionamento mais suave entre os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6ab91-153">A change to the sequencing logic for controls ensures smoother scaling across devices.</span></span> <span data-ttu-id="6ab91-154">Portanto, há menos necessidade de ajustar o dimensionamento de fontes ou botões.</span><span class="sxs-lookup"><span data-stu-id="6ab91-154">Therefore, there is less need to adjust the scaling of fonts or buttons.</span></span>
- <span data-ttu-id="6ab91-155">O tema de cor padrão foi alterado para *Escuro*.</span><span class="sxs-lookup"><span data-stu-id="6ab91-155">The default color theme has been changed to *Dark*.</span></span>
- <span data-ttu-id="6ab91-156">O ícone ausente para o botão de envio desativado foi adicionado na exibição da faixa de exibições.</span><span class="sxs-lookup"><span data-stu-id="6ab91-156">The missing icon for the disabled submit button has been added in ribbon view.</span></span>
- <span data-ttu-id="6ab91-157">Exceções de tempo agora levam você para a página de conexão em vez de mostrar um erro em linha.</span><span class="sxs-lookup"><span data-stu-id="6ab91-157">Time-out exceptions now take you to the connection page instead of showing an in-line error.</span></span>
- <span data-ttu-id="6ab91-158">Se nenhuma ação de envio estiver disponível (como **OK**, **Sim**, **Aceitar**, **Concluído** ou **Finalizado**), o botão de envio será desativado.</span><span class="sxs-lookup"><span data-stu-id="6ab91-158">If no submit action is available (such as **OK**, **Yes**, **Accept**, **Done**, or **Finished**), the submit button will be disabled.</span></span>
- <span data-ttu-id="6ab91-159">A estabilidade do aplicativo foi melhorada.</span><span class="sxs-lookup"><span data-stu-id="6ab91-159">App stability has been improved.</span></span>
- <span data-ttu-id="6ab91-160">Há uma correção para vulnerabilidade de segurança [CVE-2021-26701](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-26701).</span><span class="sxs-lookup"><span data-stu-id="6ab91-160">There is a fix for security vulnerability [CVE-2021-26701](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-26701).</span></span>
- <span data-ttu-id="6ab91-161">**Versão do Windows:** foi corrigido um problema no Windows, no qual os menus não respondiam mais depois que a janela era redimensionada.</span><span class="sxs-lookup"><span data-stu-id="6ab91-161">**Windows version:** An issue on Windows, where menus were unresponsive after the window was resized, has been fixed.</span></span>

### <a name="known-issue-in-version-2040"></a><span data-ttu-id="6ab91-162">Problemas conhecidos na versão 2.0.4.0</span><span class="sxs-lookup"><span data-stu-id="6ab91-162">Known issue in version 2.0.4.0</span></span>

<span data-ttu-id="6ab91-163">O seguinte problema conhecido existe nesta versão:</span><span class="sxs-lookup"><span data-stu-id="6ab91-163">The following known issue exists in this version:</span></span>

- <span data-ttu-id="6ab91-164">Esta versão tem um problema com dispositivos que usam Android 4.4.</span><span class="sxs-lookup"><span data-stu-id="6ab91-164">This version has an issue with devices that use Android 4.4.</span></span> <span data-ttu-id="6ab91-165">Você pode ter problemas quando usar o aplicativo nesta versão do Android.</span><span class="sxs-lookup"><span data-stu-id="6ab91-165">You might experience issues when you use the app on this Android version.</span></span>

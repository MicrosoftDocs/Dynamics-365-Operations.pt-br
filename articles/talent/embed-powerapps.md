---
title: Inserir aplicativos do Power Apps no Dynamics 365 Human Resources
description: Este tópico explica como resolver o problema quando o item do menu Microsoft Power Apps desapareceu do módulo de administração do sistema.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 8275a8a7c68fa13d6b9880c4c411deaa2dcbb998
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "3017864"
---
# <a name="embed-power-apps-apps-in-dynamics-365-human-resources"></a><span data-ttu-id="3e9ba-103">Inserir aplicativos do Power Apps no Dynamics 365 Human Resources</span><span class="sxs-lookup"><span data-stu-id="3e9ba-103">Embed Power Apps apps in Dynamics 365 Human Resources</span></span>

<span data-ttu-id="3e9ba-104">**Emissão**</span><span class="sxs-lookup"><span data-stu-id="3e9ba-104">**Issue**</span></span>

<span data-ttu-id="3e9ba-105">O item de menu **Power Apps** desapareceu do módulo de **Administração do sistema**.</span><span class="sxs-lookup"><span data-stu-id="3e9ba-105">The **Power Apps** menu item has disappeared from the **System administration** module.</span></span>

<span data-ttu-id="3e9ba-106">**Causa**</span><span class="sxs-lookup"><span data-stu-id="3e9ba-106">**Cause**</span></span>

<span data-ttu-id="3e9ba-107">O design de interface de usuário (IU) foi alterado, e agora o Microsoft Power Apps está incluído no modelo de personalização padrão.</span><span class="sxs-lookup"><span data-stu-id="3e9ba-107">The user interface (UI) design has been changed, and Microsoft Power Apps is now included in the standard personalization model.</span></span>

<span data-ttu-id="3e9ba-108">**Resolução**</span><span class="sxs-lookup"><span data-stu-id="3e9ba-108">**Resolution**</span></span>

<span data-ttu-id="3e9ba-109">A maneira como os Power Apps são inseridos mudou.</span><span class="sxs-lookup"><span data-stu-id="3e9ba-109">The way that Power Apps are embedded has been changed.</span></span> <span data-ttu-id="3e9ba-110">Agora os Power Apps são adicionados por meio do modelo de personalização.</span><span class="sxs-lookup"><span data-stu-id="3e9ba-110">Power Apps are now added through the personalization model.</span></span> <span data-ttu-id="3e9ba-111">Você pode adicionar Power Apps a quase todas as páginas do Microsoft Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="3e9ba-111">You can add Power Apps to almost all pages in Microsoft Dynamics 365 Talent.</span></span>

<span data-ttu-id="3e9ba-112">Para obter informações sobre como inserir Power Apps no Talent, consulte [Inserir o Power Apps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span><span class="sxs-lookup"><span data-stu-id="3e9ba-112">For information about how to embed Power Apps in Talent, see [Embed Power Apps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span></span>

<span data-ttu-id="3e9ba-113">Qualquer cliente do Power Apps que inseriu aplicativos antes da mudança deve ter sido atualizado para o novo modelo.</span><span class="sxs-lookup"><span data-stu-id="3e9ba-113">Any Power Apps customer who embedded apps before the change should have been upgraded to the new model.</span></span>

<span data-ttu-id="3e9ba-114">O botão **Power Apps** fica no canto superior direito de quase todas as páginas do Talent.</span><span class="sxs-lookup"><span data-stu-id="3e9ba-114">The **Power Apps** button is in the upper-right corner of almost every page in Talent.</span></span> <span data-ttu-id="3e9ba-115">Você pode usar esse botão para inserir aplicativos.</span><span class="sxs-lookup"><span data-stu-id="3e9ba-115">You can use this button to insert apps.</span></span>

<span data-ttu-id="3e9ba-116">Veja aqui um exemplo.</span><span class="sxs-lookup"><span data-stu-id="3e9ba-116">Here is an example.</span></span>

1. <span data-ttu-id="3e9ba-117">Acesse **Gerenciamento de equipe \> Links \> Trabalhadores \> Funcionários**.</span><span class="sxs-lookup"><span data-stu-id="3e9ba-117">Go to **Personnel management \> Links \> Workers \> Employees**.</span></span>
2. <span data-ttu-id="3e9ba-118">Selecione o botão do **Power Apps** e, em seguida, selecione **Adicionar um aplicativo do Power Apps**.</span><span class="sxs-lookup"><span data-stu-id="3e9ba-118">Select the **Power Apps** button, and then select **Add an app from Power Apps**.</span></span>

    ![Botão Power Apps](media/png.png)

3. <span data-ttu-id="3e9ba-120">Preencha os campos na caixa de diálogo **Adicionar aplicativo do Power Apps**.</span><span class="sxs-lookup"><span data-stu-id="3e9ba-120">Complete the fields in the **Add an app from Power Apps** dialog box.</span></span>

    ![Adicionar um aplicativo da caixa de diálogo do Power Apps](media/insert-powerapp.png)

<span data-ttu-id="3e9ba-122">Alternativamente, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="3e9ba-122">Alternatively, follow these steps.</span></span>

1. <span data-ttu-id="3e9ba-123">No painel de ação da página, na guia **Opções**, no grupo **Personalizar**, selecione **Personalizar essa página**.</span><span class="sxs-lookup"><span data-stu-id="3e9ba-123">On the page's Action Pane, on the **Options** tab, in the **Personalize** group, select **Personalize this page**.</span></span>

    ![Personalizar grupo na guia Opções](media/options.png)

    <span data-ttu-id="3e9ba-125">A barra de ferramentas de personalização aparece.</span><span class="sxs-lookup"><span data-stu-id="3e9ba-125">The personalization toolbar appears.</span></span>

2. <span data-ttu-id="3e9ba-126">Na barra de ferramentas, selecione **Adicionar um aplicativo do Power Apps**.</span><span class="sxs-lookup"><span data-stu-id="3e9ba-126">On the toolbar, select **Add an app from Power Apps**.</span></span>

    ![Adicionar um aplicativo do Power Apps usando a barra de ferramentas de personalização](media/powerapp-bar.png)

---
title: Inserir aplicativos PowerApps no Dynamics 365 - Core HR
description: Este tópico explica como resolver o problema quando o item do menu PowerApps desapareceu do módulo de administração do sistema.
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
ms.openlocfilehash: b510c10ebfcf4939eb2e1297972d27aa1812ae5a
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550994"
---
# <a name="embed-powerapps-apps-in-dynamics-365---core-hr"></a><span data-ttu-id="3470c-103">Inserir aplicativos PowerApps no Dynamics 365 - Core HR</span><span class="sxs-lookup"><span data-stu-id="3470c-103">Embed PowerApps apps in Dynamics 365 - Core HR</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3470c-104">**Emissão**</span><span class="sxs-lookup"><span data-stu-id="3470c-104">**Issue**</span></span>

<span data-ttu-id="3470c-105">O item de menu **PowerApps** desapareceu do módulo de **Administração do sistema**.</span><span class="sxs-lookup"><span data-stu-id="3470c-105">The **PowerApps** menu item has disappeared from the **System administration** module.</span></span>

<span data-ttu-id="3470c-106">**Causa**</span><span class="sxs-lookup"><span data-stu-id="3470c-106">**Cause**</span></span>

<span data-ttu-id="3470c-107">O design de interface de usuário (IU) foi alterado, e agora o Microsoft PowerApps está incluído no modelo de personalização padrão.</span><span class="sxs-lookup"><span data-stu-id="3470c-107">The user interface (UI) design has been changed, and Microsoft PowerApps is now included in the standard personalization model.</span></span>

<span data-ttu-id="3470c-108">**Resolução**</span><span class="sxs-lookup"><span data-stu-id="3470c-108">**Resolution**</span></span>

<span data-ttu-id="3470c-109">A maneira como os aplicativos PowerApps são inseridos mudou.</span><span class="sxs-lookup"><span data-stu-id="3470c-109">The way that PowerApps apps are embedded has been changed.</span></span> <span data-ttu-id="3470c-110">Os aplicativos PowerApps agora são adicionados por meio do modelo de personalização.</span><span class="sxs-lookup"><span data-stu-id="3470c-110">PowerApps apps are now added through the personalization model.</span></span> <span data-ttu-id="3470c-111">Você pode adicionar aplicativos PowerApps a quase todas as páginas do Microsoft Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="3470c-111">You can add PowerApps apps to almost all pages in Microsoft Dynamics 365 Talent.</span></span>

<span data-ttu-id="3470c-112">Para obter informações sobre como inserir aplicativos PowerApps no Talent, consulte [Inserir aplicativos PowerApps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span><span class="sxs-lookup"><span data-stu-id="3470c-112">For information about how to embed PowerApps apps in Talent, see [Embed PowerApps apps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span></span>

<span data-ttu-id="3470c-113">Qualquer cliente do PowerApps que inseriu aplicativos antes da mudança deve ter sido atualizado para o novo modelo.</span><span class="sxs-lookup"><span data-stu-id="3470c-113">Any PowerApps customer who embedded apps before the change should have been upgraded to the new model.</span></span>

<span data-ttu-id="3470c-114">O botão **PowerApps** fica no canto superior direito de quase todas as páginas do Talent.</span><span class="sxs-lookup"><span data-stu-id="3470c-114">The **PowerApps** button is in the upper-right corner of almost every page in Talent.</span></span> <span data-ttu-id="3470c-115">Você pode usar esse botão para inserir um aplicativo PowerApps.</span><span class="sxs-lookup"><span data-stu-id="3470c-115">You can use this button to insert a PowerApps app.</span></span>

<span data-ttu-id="3470c-116">Veja aqui um exemplo.</span><span class="sxs-lookup"><span data-stu-id="3470c-116">Here is an example.</span></span>

1. <span data-ttu-id="3470c-117">Acesse **Gerenciamento de equipe \> Links \> Trabalhadores \> Funcionários**.</span><span class="sxs-lookup"><span data-stu-id="3470c-117">Go to **Personnel management \> Links \> Workers \> Employees**.</span></span>
2. <span data-ttu-id="3470c-118">Selecione o botão **PowerApps** e selecione **Inserir um PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="3470c-118">Select the **PowerApps** button, and then select **Insert a PowerApp**.</span></span>

    ![Botão PowerApps](media/png.png)

3. <span data-ttu-id="3470c-120">Preencha os campos na caixa de diálogo **Inserir um PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="3470c-120">Complete the fields in the **Insert a PowerApp** dialog box.</span></span>

    ![Inserir uma caixa de diálogo do PowerApp](media/insert-powerapp.png)

<span data-ttu-id="3470c-122">Alternativamente, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="3470c-122">Alternatively, follow these steps.</span></span>

1. <span data-ttu-id="3470c-123">No painel de ação da página, na guia **Opções**, no grupo **Personalizar**, selecione **Personalizar esse formulário**.</span><span class="sxs-lookup"><span data-stu-id="3470c-123">On the page's Action Pane, on the **Options** tab, in the **Personalize** group, select **Personalize this form**.</span></span>

    ![Personalizar grupo na guia Opções](media/options.png)

    <span data-ttu-id="3470c-125">A barra de ferramentas de personalização aparece.</span><span class="sxs-lookup"><span data-stu-id="3470c-125">The personalization toolbar appears.</span></span>

2. <span data-ttu-id="3470c-126">Na barra de ferramentas, selecione **Inserir \> PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="3470c-126">On the toolbar, select **Insert \> PowerApp**.</span></span>

    ![Inserir um aplicativo PowerApps usando a barra de ferramentas de personalização](media/powerapp-bar.png)

---
title: Incorporar Aplicativos PowerApps no Core HR
description: Este tópico explica como resolver o problema onde o item de menu do PowerApps desapareceu do módulo de administração do sistema.
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 197b553f0b202ee29ad42274e2c0e03446ec782c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "303291"
---
# <a name="embed-powerapps-apps-in-core-hr"></a><span data-ttu-id="db5b2-103">Incorporar Aplicativos PowerApps no Core HR</span><span class="sxs-lookup"><span data-stu-id="db5b2-103">Embed PowerApps apps in Core HR</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="db5b2-104">**Saída**</span><span class="sxs-lookup"><span data-stu-id="db5b2-104">**Issue**</span></span>

<span data-ttu-id="db5b2-105">O item de menu **PowerApps** desapareceu do módulo de **Administração do sistema**.</span><span class="sxs-lookup"><span data-stu-id="db5b2-105">The **PowerApps** menu item has disappeared from the **System administration** module.</span></span>

<span data-ttu-id="db5b2-106">**Causa**</span><span class="sxs-lookup"><span data-stu-id="db5b2-106">**Cause**</span></span>

<span data-ttu-id="db5b2-107">O design de interface de usuário (IU) foi alterado, e agora o Microsoft PowerApps está incluído no modelo de personalização padrão.</span><span class="sxs-lookup"><span data-stu-id="db5b2-107">The user interface (UI) design has been changed, and Microsoft PowerApps is now included in the standard personalization model.</span></span>

<span data-ttu-id="db5b2-108">**Resolução**</span><span class="sxs-lookup"><span data-stu-id="db5b2-108">**Resolution**</span></span>

<span data-ttu-id="db5b2-109">A maneira como os aplicativos do PowerApps são integrados, mudou.</span><span class="sxs-lookup"><span data-stu-id="db5b2-109">The way that PowerApps apps are embedded has been changed.</span></span> <span data-ttu-id="db5b2-110">Os aplicativos de PowerApps agora estão adicionados por meio do modelo de personalização.</span><span class="sxs-lookup"><span data-stu-id="db5b2-110">PowerApps apps are now added through the personalization model.</span></span> <span data-ttu-id="db5b2-111">Você pode adicionar aplicativos do PowerApps a quase todas as páginas no Microsoft Dynamics 365 for Talent.</span><span class="sxs-lookup"><span data-stu-id="db5b2-111">You can add PowerApps apps to almost all pages in Microsoft Dynamics 365 for Talent.</span></span>

<span data-ttu-id="db5b2-112">Para obter informações sobre como inserir um aplicativo PowerApps no Talent, consulte [Aplicativos do PowerApps integrados](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span><span class="sxs-lookup"><span data-stu-id="db5b2-112">For information about how to embed PowerApps apps in Talent, see [Embed PowerApps apps](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span></span>

<span data-ttu-id="db5b2-113">Qualquer cliente do PowerApps que adicionou aplicativos antes da mudança deve ter recebido e atualizado para o novo modelo.</span><span class="sxs-lookup"><span data-stu-id="db5b2-113">Any PowerApps customer who embedded apps before the change should have been upgraded to the new model.</span></span>

<span data-ttu-id="db5b2-114">O botão **PowerApps** está no canto superior direito de quase todas as páginas do Talent.</span><span class="sxs-lookup"><span data-stu-id="db5b2-114">The **PowerApps** button is in the upper-right corner of almost every page in Talent.</span></span> <span data-ttu-id="db5b2-115">Você pode usar este botão para inserir um aplicativo do PowerApps.</span><span class="sxs-lookup"><span data-stu-id="db5b2-115">You can use this button to insert a PowerApps app.</span></span>

<span data-ttu-id="db5b2-116">Veja aqui um exemplo.</span><span class="sxs-lookup"><span data-stu-id="db5b2-116">Here is an example.</span></span>

1. <span data-ttu-id="db5b2-117">Acesse **Gerenciamento de equipe \> Links \> Trabalhadores \> Funcionários**.</span><span class="sxs-lookup"><span data-stu-id="db5b2-117">Go to **Personnel management \> Links \> Workers \> Employees**.</span></span>
2. <span data-ttu-id="db5b2-118">Selecione o botão **PowerApps**, e depois selecione **Inserir um PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="db5b2-118">Select the **PowerApps** button, and then select **Insert a PowerApp**.</span></span>

    ![Botão do PowerApps](media/png.png)

3. <span data-ttu-id="db5b2-120">Preencha os campos na caixa de diálogo **Inserir um PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="db5b2-120">Complete the fields in the **Insert a PowerApp** dialog box.</span></span>

    ![Inserir uma caixa de diálogo do PowerApp](media/insert-powerapp.png)

<span data-ttu-id="db5b2-122">Alternativamente, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="db5b2-122">Alternatively, follow these steps.</span></span>

1. <span data-ttu-id="db5b2-123">No painel de ação da página, na guia **Opções**, no grupo **Personalizar**, selecione **Personalizar esse formulário**.</span><span class="sxs-lookup"><span data-stu-id="db5b2-123">On the page's Action Pane, on the **Options** tab, in the **Personalize** group, select **Personalize this form**.</span></span>

    ![Personalizar grupo na guia Opções](media/options.png)

    <span data-ttu-id="db5b2-125">A barra de ferramentas de personalização aparece.</span><span class="sxs-lookup"><span data-stu-id="db5b2-125">The personalization toolbar appears.</span></span>

2. <span data-ttu-id="db5b2-126">Na barra de ferramentas, selecione **Inserir \> PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="db5b2-126">On the toolbar, select **Insert \> PowerApp**.</span></span>

    ![Inserir um aplicativo do PowerApps usando a barra de ferramentas de personalização](media/powerapp-bar.png)

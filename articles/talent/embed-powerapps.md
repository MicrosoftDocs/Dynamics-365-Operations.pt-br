---
title: Inserir aplicativos Power Apps no Dynamics 365 - Core HR
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
ms.openlocfilehash: 6d1b7f1dd71e6bcbf10c4d91fe33e9494b041a2c
ms.sourcegitcommit: ae0efac749ab34d423fac44d00a597801c143fbb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/22/2019
ms.locfileid: "2830200"
---
# <a name="embed-power-apps-apps-in-dynamics-365---core-hr"></a><span data-ttu-id="b122e-103">Inserir aplicativos Power Apps no Dynamics 365 - Core HR</span><span class="sxs-lookup"><span data-stu-id="b122e-103">Embed Power Apps apps in Dynamics 365 - Core HR</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b122e-104">**Emissão**</span><span class="sxs-lookup"><span data-stu-id="b122e-104">**Issue**</span></span>

<span data-ttu-id="b122e-105">O item de menu **Power Apps** desapareceu do módulo de **Administração do sistema**.</span><span class="sxs-lookup"><span data-stu-id="b122e-105">The **Power Apps** menu item has disappeared from the **System administration** module.</span></span>

<span data-ttu-id="b122e-106">**Causa**</span><span class="sxs-lookup"><span data-stu-id="b122e-106">**Cause**</span></span>

<span data-ttu-id="b122e-107">O design de interface de usuário (IU) foi alterado, e agora o Microsoft Power Apps está incluído no modelo de personalização padrão.</span><span class="sxs-lookup"><span data-stu-id="b122e-107">The user interface (UI) design has been changed, and Microsoft Power Apps is now included in the standard personalization model.</span></span>

<span data-ttu-id="b122e-108">**Resolução**</span><span class="sxs-lookup"><span data-stu-id="b122e-108">**Resolution**</span></span>

<span data-ttu-id="b122e-109">A maneira como os Power Apps são inseridos mudou.</span><span class="sxs-lookup"><span data-stu-id="b122e-109">The way that Power Apps are embedded has been changed.</span></span> <span data-ttu-id="b122e-110">Agora os Power Apps são adicionados por meio do modelo de personalização.</span><span class="sxs-lookup"><span data-stu-id="b122e-110">Power Apps are now added through the personalization model.</span></span> <span data-ttu-id="b122e-111">Você pode adicionar Power Apps a quase todas as páginas do Microsoft Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="b122e-111">You can add Power Apps to almost all pages in Microsoft Dynamics 365 Talent.</span></span>

<span data-ttu-id="b122e-112">Para obter informações sobre como inserir Power Apps no Talent, consulte [Inserir o Microsoft Power Apps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span><span class="sxs-lookup"><span data-stu-id="b122e-112">For information about how to embed Power Apps in Talent, see [Embed Microsoft Power Apps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span></span>

<span data-ttu-id="b122e-113">Qualquer cliente do Power Apps que inseriu aplicativos antes da mudança deve ter sido atualizado para o novo modelo.</span><span class="sxs-lookup"><span data-stu-id="b122e-113">Any Power Apps customer who embedded apps before the change should have been upgraded to the new model.</span></span>

<span data-ttu-id="b122e-114">O botão **Power Apps** fica no canto superior direito de quase todas as páginas do Talent.</span><span class="sxs-lookup"><span data-stu-id="b122e-114">The **Power Apps** button is in the upper-right corner of almost every page in Talent.</span></span> <span data-ttu-id="b122e-115">Você pode usar esse botão para inserir Power Apps.</span><span class="sxs-lookup"><span data-stu-id="b122e-115">You can use this button to insert Power Apps.</span></span>

<span data-ttu-id="b122e-116">Veja aqui um exemplo.</span><span class="sxs-lookup"><span data-stu-id="b122e-116">Here is an example.</span></span>

1. <span data-ttu-id="b122e-117">Acesse **Gerenciamento de equipe \> Links \> Trabalhadores \> Funcionários**.</span><span class="sxs-lookup"><span data-stu-id="b122e-117">Go to **Personnel management \> Links \> Workers \> Employees**.</span></span>
2. <span data-ttu-id="b122e-118">Selecione o botão **Power Apps** e selecione **Inserir um PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="b122e-118">Select the **Power Apps** button, and then select **Insert a PowerApp**.</span></span>

    ![Botão Power Apps](media/png.png)

3. <span data-ttu-id="b122e-120">Preencha os campos na caixa de diálogo **Inserir um PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="b122e-120">Complete the fields in the **Insert a PowerApp** dialog box.</span></span>

    ![Inserir uma caixa de diálogo do PowerApp](media/insert-powerapp.png)

<span data-ttu-id="b122e-122">Alternativamente, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="b122e-122">Alternatively, follow these steps.</span></span>

1. <span data-ttu-id="b122e-123">No painel de ação da página, na guia **Opções**, no grupo **Personalizar**, selecione **Personalizar esse formulário**.</span><span class="sxs-lookup"><span data-stu-id="b122e-123">On the page's Action Pane, on the **Options** tab, in the **Personalize** group, select **Personalize this form**.</span></span>

    ![Personalizar grupo na guia Opções](media/options.png)

    <span data-ttu-id="b122e-125">A barra de ferramentas de personalização aparece.</span><span class="sxs-lookup"><span data-stu-id="b122e-125">The personalization toolbar appears.</span></span>

2. <span data-ttu-id="b122e-126">Na barra de ferramentas, selecione **Inserir \> PowerApp**.</span><span class="sxs-lookup"><span data-stu-id="b122e-126">On the toolbar, select **Insert \> PowerApp**.</span></span>

    ![Inserir um aplicativo Power Apps usando a barra de ferramentas de personalização](media/powerapp-bar.png)

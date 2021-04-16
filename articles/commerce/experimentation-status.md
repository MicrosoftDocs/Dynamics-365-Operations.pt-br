---
title: Revisar o status de um experimento
description: Este tópico explica o status de um experimento no ciclo de vida da experimentação no Dynamics 365 Commerce.
author: sushma-rao
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: f7bdd292893ee42d49bdf977a55d8b10896ca1cd
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792430"
---
# <a name="review-the-status-of-an-experiment"></a><span data-ttu-id="c17fc-103">Revisar o status de um experimento</span><span class="sxs-lookup"><span data-stu-id="c17fc-103">Review the status of an experiment</span></span>
<span data-ttu-id="c17fc-104">Há várias etapas envolvidas na configuração e na execução de um experimento no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c17fc-104">There are many steps involved in setting up and running an experiment in Dynamics 365 Commerce.</span></span> <span data-ttu-id="c17fc-105">Para obter informações sobre o ciclo de vida de experimentação, consulte [Experimentação no Dynamics 365 Commerce](experimentation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c17fc-105">For information about the experimentation lifecycle, see [Experimentation in Dynamics 365 Commerce](experimentation-overview.md).</span></span>

<span data-ttu-id="c17fc-106">Para saber onde um experimento está no ciclo de vida, no construtor de sites do Commerce, selecione **Experimentos** no painel de navegação esquerdo.</span><span class="sxs-lookup"><span data-stu-id="c17fc-106">To learn where an experiment is in the lifecycle, in Commerce site builder select **Experiments** in the left navigation pane.</span></span> <span data-ttu-id="c17fc-107">Uma lista de experimentos é exibida com o status de cada experimento no Commerce e no serviço de terceiros que está sendo usado para habilitar a criação de experimentos, atribuir variações e analisar dados.</span><span class="sxs-lookup"><span data-stu-id="c17fc-107">A list of experiments is displayed with the status of each experiment in both Commerce and the third-party service that is being used to enable the creation of experiments, assign variations, and analyze data.</span></span>

<span data-ttu-id="c17fc-108">Na coluna **Status do Commerce**, os valores a seguir podem ser exibidos.</span><span class="sxs-lookup"><span data-stu-id="c17fc-108">In the **Commerce status** column, the following values may be displayed.</span></span> 
- <span data-ttu-id="c17fc-109">**Rascunho** - o experimento está conectado a uma página ou fragmento no Commerce e está sendo editado.</span><span class="sxs-lookup"><span data-stu-id="c17fc-109">**Draft** - The experiment is connected to a page or fragment in Commerce and is being edited.</span></span>
- <span data-ttu-id="c17fc-110">**Publicado** - as variações do experimento estão prontas para serem exibidas no seu site.</span><span class="sxs-lookup"><span data-stu-id="c17fc-110">**Published** - The experiment variations are ready to be displayed on your website.</span></span> <span data-ttu-id="c17fc-111">Se o experimento estiver sendo executado no serviço de terceiros, os usuários do site verão uma variação da página ou do fragmento, conforme selecionado pelo serviço de terceiros.</span><span class="sxs-lookup"><span data-stu-id="c17fc-111">If the experiment is running in the third-party service, website users will see a variation of the page or fragment as selected by the third-party service.</span></span>
- <span data-ttu-id="c17fc-112">**Não publicado** - o experimento não está mais disponível no seu site.</span><span class="sxs-lookup"><span data-stu-id="c17fc-112">**Unpublished** - The experiment is no longer available on your website.</span></span> <span data-ttu-id="c17fc-113">Os usuários do site verão apenas a versão padrão da página ou fragmento, mesmo se o experimento estiver sendo executado no serviço de terceiros.</span><span class="sxs-lookup"><span data-stu-id="c17fc-113">Website users will only see the default version of the page or fragment even if the experiment is running in the third-party service.</span></span>
- <span data-ttu-id="c17fc-114">**Concluído** - o experimento foi executado e uma variação foi promovida a ativa para todos os usuários do site.</span><span class="sxs-lookup"><span data-stu-id="c17fc-114">**Completed** - The experiment has run its course and a variation was promoted to live for all website users.</span></span>

<span data-ttu-id="c17fc-115">Da mesma forma, na coluna **status de terceiros**, os valores a seguir podem ser exibidos para indicar que status são os experimentos no serviço de terceiros.</span><span class="sxs-lookup"><span data-stu-id="c17fc-115">Similarly, in the **third-party status** column, the following values may be displayed to indicate what status the experiments are in the third-party service.</span></span>
- <span data-ttu-id="c17fc-116">**Rascunho** - o experimento é configurado no serviço de terceiros, mas ainda não foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="c17fc-116">**Draft** - The experiment is set up in the third-party service but hasn't been started.</span></span>
- <span data-ttu-id="c17fc-117">**Em execução** - o experimento foi iniciado no serviço de terceiros e está retirando dados.</span><span class="sxs-lookup"><span data-stu-id="c17fc-117">**Running** - The experiment was started in the third-party service and is collecting data.</span></span>
- <span data-ttu-id="c17fc-118">**Em pausa** - o experimento está pausado e não está retirando dados.</span><span class="sxs-lookup"><span data-stu-id="c17fc-118">**Paused** - The experiment is paused and not collecting data.</span></span> <span data-ttu-id="c17fc-119">Você deve continuar o experimento para retirar dados novamente.</span><span class="sxs-lookup"><span data-stu-id="c17fc-119">You must resume the experiment for it to collect data again.</span></span>
- <span data-ttu-id="c17fc-120">**Arquivado** - o experimento foi executado no curso e foi catalogado no serviço de terceiros para referência futura.</span><span class="sxs-lookup"><span data-stu-id="c17fc-120">**Archived** - The experiment has run its course and has been cataloged in the third-party service for future reference.</span></span>

<span data-ttu-id="c17fc-121">O diagrama a seguir mostra os dois conjuntos de status e como eles se relacionam entre si.</span><span class="sxs-lookup"><span data-stu-id="c17fc-121">The diagram below shows both sets of statuses and how they relate to each other.</span></span>

<span data-ttu-id="c17fc-122">[ ![Status da experimentação](./media/experimentation_statuses.svg) ](./media/experimentation_statuses.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="c17fc-122">[ ![Experimentation statuses](./media/experimentation_statuses.svg) ](./media/experimentation_statuses.svg#lightbox)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
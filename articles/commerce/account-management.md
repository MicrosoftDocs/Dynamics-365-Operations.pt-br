---
title: Páginas e módulos de gerenciamento de contas
description: Este tópico aborda páginas e módulos de gerenciamento de contas no Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 12/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: f9fc3731cd9d21294b0161e1d419f255096d7790
ms.sourcegitcommit: 96bfc20eb748f4090a2b5e1ff9f54997d5a5d359
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/04/2019
ms.locfileid: "2885800"
---
# <a name="account-management-pages-and-modules"></a><span data-ttu-id="65ee1-103">Páginas e módulos de gerenciamento de contas</span><span class="sxs-lookup"><span data-stu-id="65ee1-103">Account management pages and modules</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="65ee1-104">Este tópico aborda páginas e módulos de gerenciamento de contas no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="65ee1-104">This topic covers account management pages and modules in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="65ee1-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="65ee1-105">Overview</span></span>

<span data-ttu-id="65ee1-106">O gerenciamento de contas refere-se a um grupo de páginas que é usado para gerenciar informações relacionadas à conta do usuário no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="65ee1-106">Account management refers to a group of pages that is used to manage user account–related information in Dynamics 365 Commerce.</span></span> <span data-ttu-id="65ee1-107">As páginas de gerenciamento de contas incluem a página de aterrissagem do gerenciamento de contas, a página de perfil do usuário, a página de endereço do usuário, a página do histórico de ordens, a página de detalhes de ordens, a página de fidelidade e a página da lista de desejos.</span><span class="sxs-lookup"><span data-stu-id="65ee1-107">Account management pages include the account management landing page, user profile page, user address page, order history page, order details page, loyalty page, and wish list page.</span></span>

### <a name="account-management-landing-page"></a><span data-ttu-id="65ee1-108">Página de aterrissagem de gerenciamento de contas</span><span class="sxs-lookup"><span data-stu-id="65ee1-108">Account management landing page</span></span>

<span data-ttu-id="65ee1-109">A página de aterrissagem do gerenciamento de contas usa os seguintes módulos:</span><span class="sxs-lookup"><span data-stu-id="65ee1-109">The account management landing page uses the following modules:</span></span>

- <span data-ttu-id="65ee1-110">**Posicionamento de conteúdo** – Este módulo é um módulo de contêiner que contém todos os módulos na página de aterrissagem de gerenciamento de contas.</span><span class="sxs-lookup"><span data-stu-id="65ee1-110">**Content placement** – This module is a container module that holds all the modules on the account management landing page.</span></span>
- <span data-ttu-id="65ee1-111">**Item de boas-vindas da conta** – Este módulo é usado para fornecer uma mensagem de boas-vindas na página de gerenciamento de contas.</span><span class="sxs-lookup"><span data-stu-id="65ee1-111">**Account welcome item** – This module is used to provide a welcome message on the account management page.</span></span> <span data-ttu-id="65ee1-112">Inclui propriedades para o cabeçalho e o tamanho do bloco.</span><span class="sxs-lookup"><span data-stu-id="65ee1-112">It includes properties for the heading and the tile size.</span></span> <span data-ttu-id="65ee1-113">A propriedade **Tamanho do bloco** define a largura do módulo no módulo de posicionamento de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="65ee1-113">The **Tile size** property defines the width of the module in the content placement module.</span></span> <span data-ttu-id="65ee1-114">Os valores variam de **1** a **12**, em que **12** representa a largura total do contêiner de posicionamento de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="65ee1-114">Values range from **1** through **12**, where **12** represents the full width of the content placement container.</span></span>
- <span data-ttu-id="65ee1-115">**Item de colocação de ordens da conta** – Este módulo é usado para fornecer um resumo do número de ordens que foram realizadas pela conta do usuário.</span><span class="sxs-lookup"><span data-stu-id="65ee1-115">**Account order placement item** – This module is used to provide a summary of the number of orders that have been placed by the user account.</span></span> <span data-ttu-id="65ee1-116">Inclui propriedades para o cabeçalho, o tamanho do bloco e o link "exibir detalhes".</span><span class="sxs-lookup"><span data-stu-id="65ee1-116">It includes properties for the heading, the tile size, and the "view details" link.</span></span> <span data-ttu-id="65ee1-117">O link "exibir detalhes" deve ser configurado para redirecionamento à página do histórico de ordens.</span><span class="sxs-lookup"><span data-stu-id="65ee1-117">The "view details" link should be configured to redirect to the order history page.</span></span>
- <span data-ttu-id="65ee1-118">**Item de colocação do perfil da conta** – Este módulo é usado para fornecer um resumo do perfil do usuário.</span><span class="sxs-lookup"><span data-stu-id="65ee1-118">**Account profile placement item** – This module is used to provide a summary of the user profile.</span></span> <span data-ttu-id="65ee1-119">Inclui propriedades para o cabeçalho, o tamanho do bloco e o link "exibir detalhes".</span><span class="sxs-lookup"><span data-stu-id="65ee1-119">It includes properties for the heading, the tile size, and the "view details" link.</span></span> <span data-ttu-id="65ee1-120">O link "exibir detalhes" deve ser configurado para redirecionamento à página do perfil do usuário.</span><span class="sxs-lookup"><span data-stu-id="65ee1-120">The "view details" link should be configured to redirect to the user profile page.</span></span>
- <span data-ttu-id="65ee1-121">**Item da lista de desejos da conta** – Este módulo é usado para fornecer um resumo dos itens na lista de desejos do cliente.</span><span class="sxs-lookup"><span data-stu-id="65ee1-121">**Account wishlist item** – This module is used to provide a summary of the items on the customer's wish list.</span></span> <span data-ttu-id="65ee1-122">Por exemplo, pode indicar: "Você tem 10 itens na sua lista de desejos".</span><span class="sxs-lookup"><span data-stu-id="65ee1-122">For example, it might state, "You have 10 items in your wish list."</span></span> <span data-ttu-id="65ee1-123">Inclui propriedades para o cabeçalho, o tamanho do bloco e o link "exibir detalhes".</span><span class="sxs-lookup"><span data-stu-id="65ee1-123">It includes properties for the heading, the tile size, and the "view details" link.</span></span> <span data-ttu-id="65ee1-124">O link "exibir detalhes" deve ser configurado para redirecionamento à página da lista de desejos.</span><span class="sxs-lookup"><span data-stu-id="65ee1-124">The "view details" link should be configured to redirect to the wish list page.</span></span>
- <span data-ttu-id="65ee1-125">**Item de endereço da conta** – Este módulo é usado para fornecer um resumo dos endereços do usuário.</span><span class="sxs-lookup"><span data-stu-id="65ee1-125">**Account address item** – This module is used to provide a summary of the user's addresses.</span></span> <span data-ttu-id="65ee1-126">Por exemplo, pode indicar: "Você tem 2 endereços adicionados à sua conta".</span><span class="sxs-lookup"><span data-stu-id="65ee1-126">For example, it might state, "You have 2 addresses added to your account."</span></span> <span data-ttu-id="65ee1-127">Inclui propriedades para o cabeçalho, o tamanho do bloco e o link "exibir detalhes".</span><span class="sxs-lookup"><span data-stu-id="65ee1-127">It includes properties for the heading, the tile size, and the "view details" link.</span></span> <span data-ttu-id="65ee1-128">O link "exibir detalhes" deve ser configurado para redirecionamento à página do endereço do usuário.</span><span class="sxs-lookup"><span data-stu-id="65ee1-128">The "view details" link should be configured to redirect to the user address page.</span></span>
- <span data-ttu-id="65ee1-129">**Item de fidelidade da conta** – Este módulo é usado para mostrar e vincular às informações do programa de fidelidade.</span><span class="sxs-lookup"><span data-stu-id="65ee1-129">**Account loyalty item** – This module is used to show and link to loyalty program information.</span></span> <span data-ttu-id="65ee1-130">Inclui propriedades para o cabeçalho, o tamanho do bloco, o link "exibir detalhes" e o link "tornar-se membro".</span><span class="sxs-lookup"><span data-stu-id="65ee1-130">It includes properties for the heading, the tile size, the "view details" link, and the "become a member" link.</span></span> <span data-ttu-id="65ee1-131">O link "exibir detalhes" deve ser configurado para redirecionamento à página de fidelidade.</span><span class="sxs-lookup"><span data-stu-id="65ee1-131">The "view details" link should be configured to redirect to the loyalty page.</span></span> <span data-ttu-id="65ee1-132">O link "tornar-se membro" deve ser configurado para redirecionamento a uma página onde os usuários podem participar do programa de fidelidade.</span><span class="sxs-lookup"><span data-stu-id="65ee1-132">The "become a member" link should be configured to redirect to a page where users can join the loyalty program.</span></span>

### <a name="order-history-page"></a><span data-ttu-id="65ee1-133">Página de histórico de ordens</span><span class="sxs-lookup"><span data-stu-id="65ee1-133">Order history page</span></span>

<span data-ttu-id="65ee1-134">A página de histórico de ordens usa o módulo de histórico de ordens para mostrar todas as ordens recentes que o usuário fez.</span><span class="sxs-lookup"><span data-stu-id="65ee1-134">The order history page uses the order history module to show all the recent orders that the user has placed.</span></span>

### <a name="order-details-page"></a><span data-ttu-id="65ee1-135">Página detalhes da ordem</span><span class="sxs-lookup"><span data-stu-id="65ee1-135">Order details page</span></span>

<span data-ttu-id="65ee1-136">A página de detalhes da ordem fornece informações detalhadas para cada ordem e é acessada na página de histórico de ordens.</span><span class="sxs-lookup"><span data-stu-id="65ee1-136">The order details page provides detailed information for each order and is accessed from the order history page.</span></span> <span data-ttu-id="65ee1-137">Ela usa o módulo de detalhes da ordem, que requer a ID da venda ou da transação para recuperar os detalhes da ordem.</span><span class="sxs-lookup"><span data-stu-id="65ee1-137">It uses the order details module, which requires the sales ID or transaction ID to retrieve the order details.</span></span>

### <a name="user-profile-page"></a><span data-ttu-id="65ee1-138">Página de perfil do usuário</span><span class="sxs-lookup"><span data-stu-id="65ee1-138">User profile page</span></span>

<span data-ttu-id="65ee1-139">A página de perfil do usuário mostra detalhes da conta do usuário, como um nome e endereço de email do usuário.</span><span class="sxs-lookup"><span data-stu-id="65ee1-139">The user profile page shows user account details, such as a user's name and email address.</span></span> <span data-ttu-id="65ee1-140">Ela usa o módulo de perfil de usuário.</span><span class="sxs-lookup"><span data-stu-id="65ee1-140">It uses the user profile module.</span></span> <span data-ttu-id="65ee1-141">Embora o endereço de email não possa ser removido, ele pode ser editado.</span><span class="sxs-lookup"><span data-stu-id="65ee1-141">Although the email address can't be removed, it can be edited.</span></span> <span data-ttu-id="65ee1-142">A página de perfil do usuário também mostra as preferências do usuário que permitem a um usuário optar por ou cancelar a partir de certos recursos, como personalização de listas de recomendação.</span><span class="sxs-lookup"><span data-stu-id="65ee1-142">The user profile page also shows user preferences that enable a user to opt in or opt out from certain features such as personalization of recommendation lists.</span></span> 

### <a name="user-address-page"></a><span data-ttu-id="65ee1-143">Página de endereço do usuário</span><span class="sxs-lookup"><span data-stu-id="65ee1-143">User address page</span></span>

<span data-ttu-id="65ee1-144">A página de endereço do usuário mostra a lista de endereços associados à conta do usuário.</span><span class="sxs-lookup"><span data-stu-id="65ee1-144">The user address page shows the list of addresses that are associated with the user account.</span></span> <span data-ttu-id="65ee1-145">O usuário forneceu esses endereços durante a finalização da compra ou os adicionou diretamente nesta página.</span><span class="sxs-lookup"><span data-stu-id="65ee1-145">The user either provided these addresses during checkout or added them directly on  this page.</span></span> <span data-ttu-id="65ee1-146">O módulo de endereço do usuário é usado para adicionar e editar endereços, definir o endereço principal e renderizar endereços existentes na página.</span><span class="sxs-lookup"><span data-stu-id="65ee1-146">The user address module is used add and edit addresses, set the primary address, and render existing addresses on the page.</span></span>

### <a name="wish-list-page"></a><span data-ttu-id="65ee1-147">Página da lista de desejos</span><span class="sxs-lookup"><span data-stu-id="65ee1-147">Wish list page</span></span>

<span data-ttu-id="65ee1-148">A página da lista de desejos mostra os itens que foram adicionados à lista de desejos do cliente.</span><span class="sxs-lookup"><span data-stu-id="65ee1-148">The wish list page shows the items that have been added to the customer's wish list.</span></span> <span data-ttu-id="65ee1-149">Ele usa o módulo da lista de desejos para renderizar itens da lista de desejos.</span><span class="sxs-lookup"><span data-stu-id="65ee1-149">It uses the wish list module to render wish list items.</span></span>

### <a name="loyalty-page"></a><span data-ttu-id="65ee1-150">Página de fidelidade</span><span class="sxs-lookup"><span data-stu-id="65ee1-150">Loyalty page</span></span>

<span data-ttu-id="65ee1-151">A página de fidelidade permite que os clientes participem de um programa de fidelidade ou, se já são membros do programa de fidelidade, visualizem os detalhes do programa.</span><span class="sxs-lookup"><span data-stu-id="65ee1-151">The loyalty page lets customers join a loyalty program or, if they are already loyalty program members, view their program details.</span></span> <span data-ttu-id="65ee1-152">Eles também podem ver os pontos que ganharam e resgataram em transações recentes.</span><span class="sxs-lookup"><span data-stu-id="65ee1-152">They can also view the points that they have earned and redeemed in recent transactions.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="65ee1-153">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="65ee1-153">Additional resources</span></span>

[<span data-ttu-id="65ee1-154">Visão geral do kit de início</span><span class="sxs-lookup"><span data-stu-id="65ee1-154">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="65ee1-155">Módulo de contêiner</span><span class="sxs-lookup"><span data-stu-id="65ee1-155">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="65ee1-156">Comprar módulo de caixa</span><span class="sxs-lookup"><span data-stu-id="65ee1-156">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="65ee1-157">Módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="65ee1-157">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="65ee1-158">Módulo de finalização da compra</span><span class="sxs-lookup"><span data-stu-id="65ee1-158">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="65ee1-159">Módulo de confirmação da ordem</span><span class="sxs-lookup"><span data-stu-id="65ee1-159">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="65ee1-160">Módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="65ee1-160">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="65ee1-161">Módulo de rodapé</span><span class="sxs-lookup"><span data-stu-id="65ee1-161">Footer module</span></span>](author-footer-module.md)

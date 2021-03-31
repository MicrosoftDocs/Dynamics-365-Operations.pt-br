---
title: Páginas e módulos de gerenciamento de contas
description: Este tópico aborda páginas e módulos de gerenciamento de contas no Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 29523d03fb687684dae7d0ce08208905cce702df
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206622"
---
# <a name="account-management-pages-and-modules"></a><span data-ttu-id="aa87c-103">Páginas e módulos de gerenciamento de contas</span><span class="sxs-lookup"><span data-stu-id="aa87c-103">Account management pages and modules</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="aa87c-104">Este tópico aborda páginas e módulos de gerenciamento de contas no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="aa87c-104">This topic covers account management pages and modules in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="aa87c-105">O gerenciamento de contas refere-se a um grupo de páginas que é usado para gerenciar informações relacionadas à conta do usuário no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="aa87c-105">Account management refers to a group of pages that is used to manage user account–related information in Dynamics 365 Commerce.</span></span> <span data-ttu-id="aa87c-106">As páginas de gerenciamento de contas incluem a página de aterrissagem do gerenciamento de contas, a página de perfil do usuário, a página de endereço do usuário, a página do histórico de ordens, a página de detalhes de ordens, a página de fidelidade e a página da lista de desejos.</span><span class="sxs-lookup"><span data-stu-id="aa87c-106">Account management pages include the account management landing page, user profile page, user address page, order history page, order details page, loyalty page, and wish list page.</span></span>

### <a name="account-management-landing-page"></a><span data-ttu-id="aa87c-107">Página de aterrissagem de gerenciamento de contas</span><span class="sxs-lookup"><span data-stu-id="aa87c-107">Account management landing page</span></span>

<span data-ttu-id="aa87c-108">A página de aterrissagem do gerenciamento de contas usa os seguintes módulos:</span><span class="sxs-lookup"><span data-stu-id="aa87c-108">The account management landing page uses the following modules:</span></span>

- <span data-ttu-id="aa87c-109">**Contêiner** - Todos os módulos de página de aterrissagem de gerenciamento de contas devem ser colocados em um contêiner.</span><span class="sxs-lookup"><span data-stu-id="aa87c-109">**Container** - All account management landing page modules should be placed within a container.</span></span> 
- <span data-ttu-id="aa87c-110">**Bloco de boas-vindas da conta** – Este módulo é usado para fornecer uma mensagem de boas-vindas na página de gerenciamento de contas.</span><span class="sxs-lookup"><span data-stu-id="aa87c-110">**Account welcome tile** – This module is used to provide a welcome message on the account management page.</span></span> <span data-ttu-id="aa87c-111">Ele inclui propriedades para o título.</span><span class="sxs-lookup"><span data-stu-id="aa87c-111">It includes properties for the heading.</span></span>
- <span data-ttu-id="aa87c-112">**Bloco genérico de conta** - Este módulo pode ser usado para fornecer títulos e links às páginas de gerenciamento de contas, como as páginas "Histórico de pedidos" ou "Meu perfil".</span><span class="sxs-lookup"><span data-stu-id="aa87c-112">**Account generic tile** - This module can be used to provide headings and links to account management pages, such as the "Order history" or "My profile" pages.</span></span> <span data-ttu-id="aa87c-113">O módulo de bloco genérico pode ser usado para configurar um bloco para qualquer página.</span><span class="sxs-lookup"><span data-stu-id="aa87c-113">The generic tile module can be used to configure a tile for any page.</span></span> <span data-ttu-id="aa87c-114">Na Fabrikam, esse módulo é usado para links a página Histórico de pedidos" e "Meu perfil" na página de aterrissagem do gerenciamento de conta.</span><span class="sxs-lookup"><span data-stu-id="aa87c-114">In Fabrikam, this module is used for "Order history" and "My profile" page links on the account management landing page.</span></span>
- <span data-ttu-id="aa87c-115">**Bloco da lista de desejos da conta** – Este módulo é usado para fornecer um resumo dos itens na lista de desejos do cliente.</span><span class="sxs-lookup"><span data-stu-id="aa87c-115">**Account wishlist tile** – This module is used to provide a summary of the items on the customer's wish list.</span></span> <span data-ttu-id="aa87c-116">Por exemplo, pode indicar: "Você tem 10 itens na sua lista de desejos".</span><span class="sxs-lookup"><span data-stu-id="aa87c-116">For example, it might state, "You have 10 items in your wish list."</span></span> <span data-ttu-id="aa87c-117">Inclui propriedades para o título e o link "Exibir detalhes".</span><span class="sxs-lookup"><span data-stu-id="aa87c-117">It includes properties for the heading and the "View details" link.</span></span> <span data-ttu-id="aa87c-118">O link "Exibir detalhes" deve ser configurado para redirecionamento à página da lista de desejos.</span><span class="sxs-lookup"><span data-stu-id="aa87c-118">The "View details" link should be configured to redirect to the wish list page.</span></span> 
- <span data-ttu-id="aa87c-119">**Bloco de endereços da conta** – Este módulo é usado para fornecer um resumo dos endereços do usuário.</span><span class="sxs-lookup"><span data-stu-id="aa87c-119">**Account address tile** – This module is used to provide a summary of the user's addresses.</span></span> <span data-ttu-id="aa87c-120">Por exemplo, pode indicar: "Você tem 2 endereços adicionados à sua conta".</span><span class="sxs-lookup"><span data-stu-id="aa87c-120">For example, it might state, "You have 2 addresses added to your account."</span></span> <span data-ttu-id="aa87c-121">Inclui propriedades para o título e o link "Exibir detalhes".</span><span class="sxs-lookup"><span data-stu-id="aa87c-121">It includes properties for the heading and the "View details" link.</span></span> <span data-ttu-id="aa87c-122">O link "Exibir detalhes" deve ser configurado para redirecionamento à página de endereços do usuário.</span><span class="sxs-lookup"><span data-stu-id="aa87c-122">The "View details" link should be configured to redirect to the user address page.</span></span>
- <span data-ttu-id="aa87c-123">**Bloco de fidelidade da conta** – Este módulo é usado para exibir e vincular às informações do programa de fidelidade.</span><span class="sxs-lookup"><span data-stu-id="aa87c-123">**Account loyalty tile** – This module is used to display and link to loyalty program information.</span></span> <span data-ttu-id="aa87c-124">Este bloco tem dois estados: um estado mostra links para ingressar em um programa de fidelidade se o usuário ainda não for um membro.</span><span class="sxs-lookup"><span data-stu-id="aa87c-124">This tile has two states: one state shows links to join a loyalty progam if the user is not a member already.</span></span> <span data-ttu-id="aa87c-125">O outro estado mostra links para exibir a página de detalhes do programa de fidelidade quando o usuário já for membro.</span><span class="sxs-lookup"><span data-stu-id="aa87c-125">The other state shows links to view the loyalty details page when the user is already a member.</span></span> <span data-ttu-id="aa87c-126">As propriedades incluem o título, o link "Inscrição" e o link "Exibir fidelidade".</span><span class="sxs-lookup"><span data-stu-id="aa87c-126">Properties include the heading, the "Sign-up" link, and the "View loyalty" link.</span></span> <span data-ttu-id="aa87c-127">O link "Exibir fidelidade" deve ser configurado para redirecionamento à página do programa de fidelidade.</span><span class="sxs-lookup"><span data-stu-id="aa87c-127">The "View loyalty" link should be configured to redirect to the loyalty page.</span></span> <span data-ttu-id="aa87c-128">O link "Inscrição" deve ser configurado para redirecionamento a uma página onde os usuários podem ingressar no programa de fidelidade.</span><span class="sxs-lookup"><span data-stu-id="aa87c-128">The "Sign-up" link should be configured to redirect to a page where users can join the loyalty program.</span></span> 

### <a name="order-history-page"></a><span data-ttu-id="aa87c-129">Página de histórico de ordens</span><span class="sxs-lookup"><span data-stu-id="aa87c-129">Order history page</span></span>

<span data-ttu-id="aa87c-130">A página de histórico de ordens usa o módulo de histórico de ordens para mostrar todas as ordens recentes que o usuário fez.</span><span class="sxs-lookup"><span data-stu-id="aa87c-130">The order history page uses the order history module to show all the recent orders that the user has placed.</span></span>

### <a name="order-details-page"></a><span data-ttu-id="aa87c-131">Página detalhes da ordem</span><span class="sxs-lookup"><span data-stu-id="aa87c-131">Order details page</span></span>

<span data-ttu-id="aa87c-132">A página de detalhes da ordem fornece informações detalhadas para cada ordem e é acessada na página de histórico de ordens.</span><span class="sxs-lookup"><span data-stu-id="aa87c-132">The order details page provides detailed information for each order and is accessed from the order history page.</span></span> <span data-ttu-id="aa87c-133">Ela usa o módulo de detalhes da ordem, que requer a ID da venda ou da transação para recuperar os detalhes da ordem.</span><span class="sxs-lookup"><span data-stu-id="aa87c-133">It uses the order details module, which requires the sales ID or transaction ID to retrieve the order details.</span></span>

### <a name="user-profile-page"></a><span data-ttu-id="aa87c-134">Página de perfil do usuário</span><span class="sxs-lookup"><span data-stu-id="aa87c-134">User profile page</span></span>

<span data-ttu-id="aa87c-135">A página de perfil do usuário mostra detalhes da conta do usuário, como um nome e endereço de email do usuário.</span><span class="sxs-lookup"><span data-stu-id="aa87c-135">The user profile page shows user account details, such as a user's name and email address.</span></span> <span data-ttu-id="aa87c-136">Ela usa os detalhes do perfil de usuário e os módulos de edição do perfil de usuário.</span><span class="sxs-lookup"><span data-stu-id="aa87c-136">It uses the user profile details and user profile edit modules.</span></span> <span data-ttu-id="aa87c-137">Embora o endereço de email não possa ser removido, ele pode ser editado.</span><span class="sxs-lookup"><span data-stu-id="aa87c-137">Although the email address can't be removed, it can be edited.</span></span> <span data-ttu-id="aa87c-138">A página de perfil do usuário também mostra as preferências do usuário que permitem a um usuário aceitar ou recusar o uso de alguns recursos, como personalização de listas de recomendação.</span><span class="sxs-lookup"><span data-stu-id="aa87c-138">The user profile page also shows user preferences that enable a user to opt in or opt out from certain features, such as personalization of recommendation lists.</span></span> 

### <a name="user-address-page"></a><span data-ttu-id="aa87c-139">Página de endereço do usuário</span><span class="sxs-lookup"><span data-stu-id="aa87c-139">User address page</span></span>

<span data-ttu-id="aa87c-140">A página de endereço do usuário mostra a lista de endereços associados à conta do usuário.</span><span class="sxs-lookup"><span data-stu-id="aa87c-140">The user address page shows the list of addresses that are associated with the user account.</span></span> <span data-ttu-id="aa87c-141">O usuário forneceu esses endereços durante a finalização da compra ou os adicionou diretamente nesta página.</span><span class="sxs-lookup"><span data-stu-id="aa87c-141">The user either provided these addresses during checkout or added them directly on  this page.</span></span> <span data-ttu-id="aa87c-142">O módulo de endereço do usuário é usado para adicionar e editar endereços, definir o endereço principal e renderizar endereços existentes na página.</span><span class="sxs-lookup"><span data-stu-id="aa87c-142">The user address module is used add and edit addresses, set the primary address, and render existing addresses on the page.</span></span>

### <a name="wish-list-page"></a><span data-ttu-id="aa87c-143">Página da lista de desejos</span><span class="sxs-lookup"><span data-stu-id="aa87c-143">Wish list page</span></span>

<span data-ttu-id="aa87c-144">A página da lista de desejos mostra os itens que foram adicionados à lista de desejos do cliente.</span><span class="sxs-lookup"><span data-stu-id="aa87c-144">The wish list page shows the items that have been added to the customer's wish list.</span></span> <span data-ttu-id="aa87c-145">Ele usa o módulo da lista de desejos para renderizar itens da lista de desejos.</span><span class="sxs-lookup"><span data-stu-id="aa87c-145">It uses the wish list module to render wish list items.</span></span>

### <a name="loyalty-page"></a><span data-ttu-id="aa87c-146">Página de fidelidade</span><span class="sxs-lookup"><span data-stu-id="aa87c-146">Loyalty page</span></span>

<span data-ttu-id="aa87c-147">A página do programa de fidelidade permite que os clientes vejam os detalhes de sua participação se já forem membros do programa de fidelidade.</span><span class="sxs-lookup"><span data-stu-id="aa87c-147">The loyalty page lets customers view their loyalty details if they are already loyalty program members.</span></span> <span data-ttu-id="aa87c-148">Eles também podem ver os pontos que ganharam e resgataram em transações recentes.</span><span class="sxs-lookup"><span data-stu-id="aa87c-148">They can also view the points that they have earned and redeemed in recent transactions.</span></span> <span data-ttu-id="aa87c-149">A página usa o módulo de detalhes da fidelidade para apresentar os detalhes da fidelidade.</span><span class="sxs-lookup"><span data-stu-id="aa87c-149">The page uses the loyalty details module to showcase the loyalty details.</span></span> 

<span data-ttu-id="aa87c-150">Para ingressar no programa de fidelidade, uma página de marketing pode ser criada com módulos de condições de inscrição e fidelidade.</span><span class="sxs-lookup"><span data-stu-id="aa87c-150">To join loyalty program, a marketing page can be created with loyalty sign up and loyalty terms modules.</span></span> <span data-ttu-id="aa87c-151">Se o usuário não for membro de um programa de fidelidade, esses módulos permitirão que o usuário se inscreva.</span><span class="sxs-lookup"><span data-stu-id="aa87c-151">If the user is not a member of a loyalty program, these modules will enable the user to sign up.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="aa87c-152">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="aa87c-152">Additional resources</span></span>

[<span data-ttu-id="aa87c-153">Visão geral da biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="aa87c-153">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="aa87c-154">Módulo de contêiner</span><span class="sxs-lookup"><span data-stu-id="aa87c-154">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="aa87c-155">Módulo de caixa de compra</span><span class="sxs-lookup"><span data-stu-id="aa87c-155">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="aa87c-156">Módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="aa87c-156">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="aa87c-157">Módulo de finalização da compra</span><span class="sxs-lookup"><span data-stu-id="aa87c-157">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="aa87c-158">Módulo de confirmação da ordem</span><span class="sxs-lookup"><span data-stu-id="aa87c-158">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="aa87c-159">Módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="aa87c-159">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="aa87c-160">Módulo de rodapé</span><span class="sxs-lookup"><span data-stu-id="aa87c-160">Footer module</span></span>](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
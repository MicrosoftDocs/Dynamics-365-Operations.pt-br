---
title: Criar um perfil de funcionalidade online
description: Este tópico descreve como criar um perfil de funcionalidade online no Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
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
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 5ecbfcf3fa78ad2909a7cc9988ab1edaf2b98376
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3003363"
---
# <a name="create-an-online-functionality-profile"></a><span data-ttu-id="3111f-103">Criar um perfil de funcionalidade online</span><span class="sxs-lookup"><span data-stu-id="3111f-103">Create an online functionality profile</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="3111f-104">Este tópico apresenta uma visão geral da configuração de um perfil de funcionalidade online para o Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3111f-104">This topic presents an overview of setting up an online functionality profile for Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="3111f-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="3111f-105">Overview</span></span>

<span data-ttu-id="3111f-106">O perfil de funcionalidade online fornece várias configurações usadas em canais online.</span><span class="sxs-lookup"><span data-stu-id="3111f-106">The online functionality profile provides various settings used for online channels.</span></span> <span data-ttu-id="3111f-107">Cada canal online deve especificar um perfil de funcionalidade online.</span><span class="sxs-lookup"><span data-stu-id="3111f-107">Each online channel must specify an online functionality profile.</span></span>

## <a name="create-an-online-functionality-profile"></a><span data-ttu-id="3111f-108">Criar um perfil de funcionalidade online</span><span class="sxs-lookup"><span data-stu-id="3111f-108">Create an online functionality profile</span></span>

<span data-ttu-id="3111f-109">O procedimento a seguir explica como criar um perfil de funcionalidade online no aplicativo da sede do Commerce.</span><span class="sxs-lookup"><span data-stu-id="3111f-109">The following procedure explains how to create an online functionality profile from within Commerce Headquarters app.</span></span>

1. <span data-ttu-id="3111f-110">No painel de navegação, vá para **Módulos \> Configuração de canal \> Configuração de loja online \> Perfis de funcionalidade**.</span><span class="sxs-lookup"><span data-stu-id="3111f-110">In the navigation pane, go to **Modules \> Channel setup \> Online store setup \> Functionality profiles**.</span></span>
1. <span data-ttu-id="3111f-111">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="3111f-111">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="3111f-112">No campo **Perfil**, insira uma ID para o perfil.</span><span class="sxs-lookup"><span data-stu-id="3111f-112">In the **Profile** field, enter an ID for the profile.</span></span>
1. <span data-ttu-id="3111f-113">No campo **Descrição**, insira um valor ("perfil da Adventure Works" no exemplo da imagem abaixo).</span><span class="sxs-lookup"><span data-stu-id="3111f-113">In the **Description** field, enter a value ("Adventure Works Profile" in the example image below).</span></span>
1. <span data-ttu-id="3111f-114">Na seção **Funções**, modifique as configurações de **CARRINHO**, **CLIENTES DE VAREJO** ou **FINALIZAR COMPRA**, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="3111f-114">In the **Functions** section, modify the **CART**, **RETAIL CUSTOMERS**, or **CHECKOUT** settings, as needed.</span></span>
1. <span data-ttu-id="3111f-115">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="3111f-115">On the action pane, select **Save**.</span></span>

<span data-ttu-id="3111f-116">A imagem a seguir mostra um exemplo de perfil de funcionalidade online.</span><span class="sxs-lookup"><span data-stu-id="3111f-116">The following image shows an example online functionality profile.</span></span>
  
![Exemplo de perfil de funcionalidade online](media/online-functionality-profile.png)

## <a name="functions"></a><span data-ttu-id="3111f-118">Funções</span><span class="sxs-lookup"><span data-stu-id="3111f-118">Functions</span></span>

- <span data-ttu-id="3111f-119">**Produtos agregados**: quando habilitados, esta função permite que o carrinho atualize a quantidade quando o mesmo item é adicionado várias vezes.</span><span class="sxs-lookup"><span data-stu-id="3111f-119">**Aggregate products**: When enabled, this function allows the cart to update quantity when the same item is added multiple times.</span></span>
- <span data-ttu-id="3111f-120">**Permitir finalizar a compra sem pagamentos**: quando habilitada, esta função trata o cenário quando os itens adicionados ao carrinho têm um preço de US$0,00.</span><span class="sxs-lookup"><span data-stu-id="3111f-120">**Allow checkout with no payments**: When enabled, this function handles the scenario when items added to cart have a price $0.00.</span></span>
- <span data-ttu-id="3111f-121">**Criar cliente no modo assíncrono**: esta é uma configuração herdada aplicável a canais de comércio eletrônico de terceiros e não se aplica ao site de comércio eletrônico do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="3111f-121">**Create customer in async mode**: This is a legacy setting applicable to third-party e-Commerce channels and is not applicable to the Dynamics 365 e-Commerce site.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3111f-122">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="3111f-122">Additional resources</span></span>

[<span data-ttu-id="3111f-123">Visão geral de canais</span><span class="sxs-lookup"><span data-stu-id="3111f-123">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="3111f-124">Pré-requisitos de configuração de canal</span><span class="sxs-lookup"><span data-stu-id="3111f-124">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="3111f-125">Configurar um canal online</span><span class="sxs-lookup"><span data-stu-id="3111f-125">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="3111f-126">Configurar um canal de varejo</span><span class="sxs-lookup"><span data-stu-id="3111f-126">Set up a retail channel</span></span>](channel-setup-retail.md)

[<span data-ttu-id="3111f-127">Configurar um canal de call center</span><span class="sxs-lookup"><span data-stu-id="3111f-127">Set up a call center channel</span></span>](channel-setup-callcenter.md)

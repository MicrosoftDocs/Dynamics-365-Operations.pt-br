---
title: Configure seu nome de domínio
description: Este tópico explica como configurar um nome de domínio para um site comercial online do Microsoft Dynamics 365.
author: psimolin
manager: AnnBe
ms.date: 03/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2ad9ca3aee21301ef6d830d7b29982a45cd53f60
ms.sourcegitcommit: 567132f4e4f7a1d76dccf762068209a42c788b52
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/03/2020
ms.locfileid: "3096811"
---
# <a name="configure-your-domain-name"></a><span data-ttu-id="65f42-103">Configure seu nome de domínio</span><span class="sxs-lookup"><span data-stu-id="65f42-103">Configure your domain name</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="65f42-104">Este tópico explica como configurar um nome de domínio para um site comercial online do Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="65f42-104">This topic explains how to configure a domain name for a Microsoft Dynamics 365 e-commerce site.</span></span> 

## <a name="add-domains-during-e-commerce-initialization"></a><span data-ttu-id="65f42-105">Adicionar domínios durante a inicialização do comércio online</span><span class="sxs-lookup"><span data-stu-id="65f42-105">Add domains during e-Commerce initialization</span></span>

<span data-ttu-id="65f42-106">Para associar domínios com seu ambiente de comércio online, inicialize o comércio online como descrito em [Implantar um novo site comercial online](deploy-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="65f42-106">To associate domains with your e-commerce environment, initialize e-Commerce as described in [Deploy a new e-Commerce site](deploy-ecommerce-site.md).</span></span> <span data-ttu-id="65f42-107">Durante a inicialização, é solicitado que você forneça as informações que serão usadas para provisionar seu ambiente de comércio online.</span><span class="sxs-lookup"><span data-stu-id="65f42-107">During initialization, you're asked to provide information that will be used to provision your e-Commerce environment.</span></span> <span data-ttu-id="65f42-108">No campo **Nomes de hospedagem com suporte**, adicione todos os domínios que você planeja usar com esse ambiente.</span><span class="sxs-lookup"><span data-stu-id="65f42-108">In the **Supported host names** field, add all the domains that you plan to use with this environment.</span></span> <span data-ttu-id="65f42-109">Vários domínios devem ser separados com ponto-e-vírgula.</span><span class="sxs-lookup"><span data-stu-id="65f42-109">Multiple domains should be separated with semi-colon.</span></span> <span data-ttu-id="65f42-110">Assim, os domínios são configurados nos componentes obrigatórios de comércio online, e está pronto para ser usado quando alternar o tráfego da rede de entrega de conteúdo (CDN) ou servidor da Web e apontá-lo para o front-end de comércios online.</span><span class="sxs-lookup"><span data-stu-id="65f42-110">In this way, the domains are configured in all the required e-Commerce components, and they are ready to be used when you switch traffic from your content delivery network (CDN) or web server and point it to the e-Commerce front ends.</span></span>

## <a name="add-domains-after-e-commerce-initialization"></a><span data-ttu-id="65f42-111">Adicionar domínios após a inicialização do comércio online</span><span class="sxs-lookup"><span data-stu-id="65f42-111">Add domains after e-Commerce initialization</span></span>

<span data-ttu-id="65f42-112">Para associar novos domínios com o ambiente de comércio online após a inicialização de comércio online, você deve enviar uma solicitação de serviço.</span><span class="sxs-lookup"><span data-stu-id="65f42-112">To associate new domains with your e-Commerce environment after e-Commerce initialization, you must submit a service request.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="65f42-113">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="65f42-113">Additional resources</span></span>

[<span data-ttu-id="65f42-114">Implantar um novo site de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="65f42-114">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="65f42-115">Configurar um canal da loja online</span><span class="sxs-lookup"><span data-stu-id="65f42-115">Set up an online store channel</span></span>](online-stores.md)

[<span data-ttu-id="65f42-116">Criar um site de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="65f42-116">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="65f42-117">Associar um site online a um canal</span><span class="sxs-lookup"><span data-stu-id="65f42-117">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="65f42-118">Gerenciar arquivos robots.txt</span><span class="sxs-lookup"><span data-stu-id="65f42-118">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="65f42-119">Carregar redirecionamentos de URL em massa</span><span class="sxs-lookup"><span data-stu-id="65f42-119">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="65f42-120">Configurar um locatário B2C do Commerce</span><span class="sxs-lookup"><span data-stu-id="65f42-120">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="65f42-121">Configurar páginas personalizadas para logons dos usuários</span><span class="sxs-lookup"><span data-stu-id="65f42-121">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="65f42-122">Configurar múltiplos locatários B2C em um ambiente do Commerce</span><span class="sxs-lookup"><span data-stu-id="65f42-122">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="65f42-123">Adicionar suporte para uma rede de entrega de conteúdo (CDN)</span><span class="sxs-lookup"><span data-stu-id="65f42-123">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="65f42-124">Habilitar detecção de lojas com base na localização</span><span class="sxs-lookup"><span data-stu-id="65f42-124">Enable location-based store detection</span></span>](enable-store-detection.md)

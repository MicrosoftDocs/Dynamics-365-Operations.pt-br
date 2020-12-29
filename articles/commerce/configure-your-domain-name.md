---
title: Configure seu nome de domínio
description: Este tópico explica como configurar um nome de domínio para um site comercial online do Microsoft Dynamics 365.
author: psimolin
manager: AnnBe
ms.date: 07/02/2020
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
ms.openlocfilehash: ac1b0c8baaddd6ca62cc49657fff364df21c14f2
ms.sourcegitcommit: 4bf5ae2f2f144a28e431ed574c7e8438dc5935de
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2020
ms.locfileid: "4517104"
---
# <a name="configure-your-domain-name"></a><span data-ttu-id="67ea1-103">Configure seu nome de domínio</span><span class="sxs-lookup"><span data-stu-id="67ea1-103">Configure your domain name</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="67ea1-104">Este tópico explica como configurar um nome de domínio para um site comercial online do Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="67ea1-104">This topic explains how to configure a domain name for a Microsoft Dynamics 365 e-commerce site.</span></span> 

## <a name="add-domains-during-e-commerce-initialization"></a><span data-ttu-id="67ea1-105">Adicionar domínios durante a inicialização do comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="67ea1-105">Add domains during e-commerce initialization</span></span>

<span data-ttu-id="67ea1-106">Para associar domínios com o ambiente de comércio eletrônico do Dynamics 365 Commerce, inicialize o comércio eletrônico como descrito em [Implantar um novo locatário de comércio eletrônico](deploy-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="67ea1-106">To associate domains with your Dynamics 365 Commerce e-commerce environment, initialize e-commerce as described in [Deploy a new e-commerce tenant](deploy-ecommerce-site.md).</span></span> <span data-ttu-id="67ea1-107">Durante a inicialização, é solicitado que você forneça as informações que serão usadas para provisionar seu ambiente de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="67ea1-107">During initialization, you're asked to provide information that will be used to provision your e-commerce environment.</span></span> <span data-ttu-id="67ea1-108">No campo **Nomes de hospedagem com suporte**, adicione todos os domínios que você planeja usar com esse ambiente.</span><span class="sxs-lookup"><span data-stu-id="67ea1-108">In the **Supported host names** field, add all the domains that you plan to use with this environment.</span></span> <span data-ttu-id="67ea1-109">Vários domínios devem ser separados com ponto-e-vírgula.</span><span class="sxs-lookup"><span data-stu-id="67ea1-109">Multiple domains should be separated with semi-colon.</span></span> <span data-ttu-id="67ea1-110">Assim, os domínios são configurados nos componentes obrigatórios de comércio e estão prontos para serem usados quando você alternar o tráfego da rede de entrega de conteúdo (CDN) ou servidor Web e apontá-lo para os front-ends de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="67ea1-110">In this way, the domains are configured in all the required Commerce components, and they are ready to be used when you switch traffic from your content delivery network (CDN) or web server and point it to the e-commerce front ends.</span></span>

## <a name="add-domains-after-e-commerce-initialization"></a><span data-ttu-id="67ea1-111">Adicionar domínios após a inicialização do comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="67ea1-111">Add domains after e-commerce initialization</span></span>

<span data-ttu-id="67ea1-112">Para associar novos domínios com o ambiente de comércio eletrônico após a inicialização de comércio eletrônico, você deve enviar uma solicitação de serviço.</span><span class="sxs-lookup"><span data-stu-id="67ea1-112">To associate new domains with your e-commerce environment after e-commerce initialization, you must submit a service request.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="67ea1-113">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="67ea1-113">Additional resources</span></span>

[<span data-ttu-id="67ea1-114">Implantar um novo locatário de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="67ea1-114">Deploy a new e-commerce tenant</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="67ea1-115">Criar um site de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="67ea1-115">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="67ea1-116">Associar um site do Dynamics 365 Commerce a um canal online</span><span class="sxs-lookup"><span data-stu-id="67ea1-116">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="67ea1-117">Gerenciar arquivos robots.txt</span><span class="sxs-lookup"><span data-stu-id="67ea1-117">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="67ea1-118">Carregar redirecionamentos de URL em massa</span><span class="sxs-lookup"><span data-stu-id="67ea1-118">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="67ea1-119">Configurar um locatário B2C do Commerce</span><span class="sxs-lookup"><span data-stu-id="67ea1-119">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="67ea1-120">Configurar páginas personalizadas para logons dos usuários</span><span class="sxs-lookup"><span data-stu-id="67ea1-120">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="67ea1-121">Configurar múltiplos locatários B2C em um ambiente do Commerce</span><span class="sxs-lookup"><span data-stu-id="67ea1-121">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="67ea1-122">Adicionar suporte para uma rede de entrega de conteúdo (CDN)</span><span class="sxs-lookup"><span data-stu-id="67ea1-122">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="67ea1-123">Habilitar detecção de lojas com base na localização</span><span class="sxs-lookup"><span data-stu-id="67ea1-123">Enable location-based store detection</span></span>](enable-store-detection.md)

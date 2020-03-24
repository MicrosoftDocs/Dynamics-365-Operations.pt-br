---
title: Habilitar detecção de lojas com base na localização
description: Este tópico descreve como ativar a detecção de loja baseada em local para seu site do Dynamics 365 Commerce.
author: brianshook
manager: annbe
ms.date: 03/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 66ffe56f9d969c9d62ed4ff49f0848fab7e58a56
ms.sourcegitcommit: 567132f4e4f7a1d76dccf762068209a42c788b52
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/03/2020
ms.locfileid: "3096860"
---
# <a name="enable-location-based-store-detection"></a><span data-ttu-id="55188-103">Habilitar detecção de lojas com base na localização</span><span class="sxs-lookup"><span data-stu-id="55188-103">Enable location-based store detection</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="55188-104">Este tópico descreve como ativar a detecção de loja baseada em local para seu site do Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="55188-104">This topic describes how to turn on location-based store detection for your Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="55188-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="55188-105">Overview</span></span>

<span data-ttu-id="55188-106">A detecção de loja baseada em local no Comércio permite fornecer conteúdo de site relevante aos clientes, com base em sua localização.</span><span class="sxs-lookup"><span data-stu-id="55188-106">Location-based store detection in Commerce lets you provide relevant site content to customers, based on their location.</span></span> <span data-ttu-id="55188-107">Quando a detecção de loja baseada em local é ativada, o serviço de renderização de Comércio usa as informações de país/região do endereço IP do navegador da Web do cliente para direcionar o cliente às melhores configurações de site geográficas disponíveis.</span><span class="sxs-lookup"><span data-stu-id="55188-107">When location-based store detection is turned on, the Commerce rendering service uses the country/region information from the IP address of the customer's web browser to direct the customer to the best geographical site configuration that is available.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="55188-108">Aviso de privacidade</span><span class="sxs-lookup"><span data-stu-id="55188-108">Privacy notice</span></span>

<span data-ttu-id="55188-109">Se você ativar o recurso de detecção de loja baseada em local, as informações do navegador do cliente são enviadas para o serviço local da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="55188-109">If you turn on the location-based store detection feature, information from the customer's browser is sent to a Microsoft location service.</span></span> <span data-ttu-id="55188-110">Essas informações são usadas para fornecer conteúdo relevantes à localização aos clientes.</span><span class="sxs-lookup"><span data-stu-id="55188-110">This information is then used to provide the customer content that is relevant to his or her location.</span></span> <span data-ttu-id="55188-111">As informações enviadas do navegador do cliente e as informações baseadas em local retornadas ao cliente são sujeitas a política de conformidade de privacidade e cookie.</span><span class="sxs-lookup"><span data-stu-id="55188-111">Both the information that is sent from the customer's browser and the location-based information that is returned to the customer are subject to privacy and cookie compliance policies.</span></span>

## <a name="turn-on-location-based-store-detection"></a><span data-ttu-id="55188-112">Ativar detecção de lojas com base na localização</span><span class="sxs-lookup"><span data-stu-id="55188-112">Turn on location-based store detection</span></span>

<span data-ttu-id="55188-113">Para ativar a detecção de loja baseada em local no Comércio, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="55188-113">To turn on location-based store detection in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="55188-114">Nas ferramentas de criação, vá para nosso site.</span><span class="sxs-lookup"><span data-stu-id="55188-114">In the authoring tool, go to your site.</span></span>
1. <span data-ttu-id="55188-115">No painel de navegação à esquerda, selecione **Gerenciamento de sites**.</span><span class="sxs-lookup"><span data-stu-id="55188-115">In the navigation pane on the left, select **Site Management**.</span></span>
1. <span data-ttu-id="55188-116">Selecione **Configurações de site**.</span><span class="sxs-lookup"><span data-stu-id="55188-116">Select **Site Settings**.</span></span>
1. <span data-ttu-id="55188-117">Defina a opção **Habilitar detecção de loja baseada em local** como **Ligado**.</span><span class="sxs-lookup"><span data-stu-id="55188-117">Set the **Enable location based store detection** option to **On**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="55188-118">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="55188-118">Additional resources</span></span>

[<span data-ttu-id="55188-119">Configurar seu nome de domínio</span><span class="sxs-lookup"><span data-stu-id="55188-119">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="55188-120">Implantar um novo site de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="55188-120">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="55188-121">Configurar um canal da loja online</span><span class="sxs-lookup"><span data-stu-id="55188-121">Set up an online store channel</span></span>](online-stores.md)

[<span data-ttu-id="55188-122">Criar um site de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="55188-122">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="55188-123">Associar um site online a um canal</span><span class="sxs-lookup"><span data-stu-id="55188-123">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="55188-124">Gerenciar arquivos robots.txt</span><span class="sxs-lookup"><span data-stu-id="55188-124">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="55188-125">Carregar redirecionamentos de URL em massa</span><span class="sxs-lookup"><span data-stu-id="55188-125">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="55188-126">Configurar um locatário B2C do Commerce</span><span class="sxs-lookup"><span data-stu-id="55188-126">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="55188-127">Configurar páginas personalizadas para logons dos usuários</span><span class="sxs-lookup"><span data-stu-id="55188-127">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="55188-128">Configurar múltiplos locatários B2C em um ambiente do Commerce</span><span class="sxs-lookup"><span data-stu-id="55188-128">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="55188-129">Adicionar suporte para uma rede de entrega de conteúdo (CDN)</span><span class="sxs-lookup"><span data-stu-id="55188-129">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

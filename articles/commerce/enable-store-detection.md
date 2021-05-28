---
title: Habilitar detecção de lojas com base na localização
description: Este tópico descreve como ativar a detecção de loja baseada em local para seu site do Dynamics 365 Commerce.
author: brianshook
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3e26c3130914ebef5a63b79c477d7d5846fd5b71
ms.sourcegitcommit: cabd991fda2bfcabb55db84c225b24a7bb061631
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6027591"
---
# <a name="enable-location-based-store-detection"></a><span data-ttu-id="1a841-103">Habilitar detecção de lojas com base na localização</span><span class="sxs-lookup"><span data-stu-id="1a841-103">Enable location-based store detection</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1a841-104">Este tópico descreve como ativar a detecção de loja baseada em local para seu site do Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1a841-104">This topic describes how to turn on location-based store detection for your Dynamics 365 Commerce site.</span></span>

<span data-ttu-id="1a841-105">A detecção de loja baseada em local no Comércio permite fornecer conteúdo de site relevante aos clientes, com base em sua localização.</span><span class="sxs-lookup"><span data-stu-id="1a841-105">Location-based store detection in Commerce lets you provide relevant site content to customers, based on their location.</span></span> <span data-ttu-id="1a841-106">Quando a detecção de loja baseada em local é ativada, o serviço de renderização de Comércio usa as informações de país/região do endereço IP do navegador da Web do cliente para direcionar o cliente às melhores configurações de site geográficas disponíveis.</span><span class="sxs-lookup"><span data-stu-id="1a841-106">When location-based store detection is turned on, the Commerce rendering service uses the country/region information from the IP address of the customer's web browser to direct the customer to the best geographical site configuration that is available.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="1a841-107">Aviso de privacidade</span><span class="sxs-lookup"><span data-stu-id="1a841-107">Privacy notice</span></span>

<span data-ttu-id="1a841-108">Se você ativar o recurso de detecção de loja baseada em local, as informações do navegador do cliente são enviadas para o serviço local da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1a841-108">If you turn on the location-based store detection feature, information from the customer's browser is sent to a Microsoft location service.</span></span> <span data-ttu-id="1a841-109">Essas informações são usadas para fornecer ao cliente conteúdo relevante sobre o local do cliente.</span><span class="sxs-lookup"><span data-stu-id="1a841-109">This information is then used to provide the customer content that is relevant to the customer's location.</span></span> <span data-ttu-id="1a841-110">As informações enviadas do navegador do cliente e as informações baseadas em local retornadas ao cliente são sujeitas a política de conformidade de privacidade e cookie.</span><span class="sxs-lookup"><span data-stu-id="1a841-110">Both the information that is sent from the customer's browser and the location-based information that is returned to the customer are subject to privacy and cookie compliance policies.</span></span>

## <a name="turn-on-location-based-store-detection"></a><span data-ttu-id="1a841-111">Ativar detecção de lojas com base na localização</span><span class="sxs-lookup"><span data-stu-id="1a841-111">Turn on location-based store detection</span></span>

<span data-ttu-id="1a841-112">Para ativar a detecção de loja baseada em local no Comércio, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="1a841-112">To turn on location-based store detection in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="1a841-113">Nas ferramentas de criação, vá para nosso site.</span><span class="sxs-lookup"><span data-stu-id="1a841-113">In the authoring tool, go to your site.</span></span>
1. <span data-ttu-id="1a841-114">No painel de navegação à esquerda, selecione **Gerenciamento de sites**.</span><span class="sxs-lookup"><span data-stu-id="1a841-114">In the navigation pane on the left, select **Site Management**.</span></span>
1. <span data-ttu-id="1a841-115">Selecione **Configurações de site**.</span><span class="sxs-lookup"><span data-stu-id="1a841-115">Select **Site Settings**.</span></span>
1. <span data-ttu-id="1a841-116">Defina a opção **Habilitar detecção de loja baseada em local** como **Ligado**.</span><span class="sxs-lookup"><span data-stu-id="1a841-116">Set the **Enable location based store detection** option to **On**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1a841-117">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="1a841-117">Additional resources</span></span>

[<span data-ttu-id="1a841-118">Configurar seu nome de domínio</span><span class="sxs-lookup"><span data-stu-id="1a841-118">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="1a841-119">Implantar um novo locatário de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="1a841-119">Deploy a new e-commerce tenant</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="1a841-120">Criar um site de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="1a841-120">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="1a841-121">Associar um site do Dynamics 365 Commerce a um canal online</span><span class="sxs-lookup"><span data-stu-id="1a841-121">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="1a841-122">Gerenciar arquivos robots.txt</span><span class="sxs-lookup"><span data-stu-id="1a841-122">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="1a841-123">Carregar redirecionamentos de URL em massa</span><span class="sxs-lookup"><span data-stu-id="1a841-123">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="1a841-124">Configurar um locatário B2C do Commerce</span><span class="sxs-lookup"><span data-stu-id="1a841-124">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="1a841-125">Configurar páginas personalizadas para logons dos usuários</span><span class="sxs-lookup"><span data-stu-id="1a841-125">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="1a841-126">Configurar múltiplos locatários B2C em um ambiente do Commerce</span><span class="sxs-lookup"><span data-stu-id="1a841-126">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="1a841-127">Adicionar suporte para uma rede de entrega de conteúdo (CDN)</span><span class="sxs-lookup"><span data-stu-id="1a841-127">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

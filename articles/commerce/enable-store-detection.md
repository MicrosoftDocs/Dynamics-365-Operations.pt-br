---
title: Habilitar detecção de lojas com base na localização
description: Este tópico descreve como ativar a detecção de loja baseada em local para seu site do Dynamics 365 Commerce.
author: brianshook
manager: annbe
ms.date: 10/01/2019
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
ms.openlocfilehash: c5fb59a9798e2cddfb75b71235ee7754e54b0e28
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "2945757"
---
# <a name="enable-location-based-store-detection"></a><span data-ttu-id="7521c-103">Habilitar detecção de lojas com base na localização</span><span class="sxs-lookup"><span data-stu-id="7521c-103">Enable location-based store detection</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="7521c-104">Este tópico descreve como ativar a detecção de loja baseada em local para seu site do Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="7521c-104">This topic describes how to turn on location-based store detection for your Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="7521c-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="7521c-105">Overview</span></span>

<span data-ttu-id="7521c-106">A detecção de loja baseada em local no Comércio permite fornecer conteúdo de site relevante aos clientes, com base em sua localização.</span><span class="sxs-lookup"><span data-stu-id="7521c-106">Location-based store detection in Commerce lets you provide relevant site content to customers, based on their location.</span></span> <span data-ttu-id="7521c-107">Quando a detecção de loja baseada em local é ativada, o serviço de renderização de Comércio usa as informações de país/região do endereço IP do navegador da Web do cliente para direcionar o cliente às melhores configurações de site geográficas disponíveis.</span><span class="sxs-lookup"><span data-stu-id="7521c-107">When location-based store detection is turned on, the Commerce rendering service uses the country/region information from the IP address of the customer's web browser to direct the customer to the best geographical site configuration that is available.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="7521c-108">Aviso de privacidade</span><span class="sxs-lookup"><span data-stu-id="7521c-108">Privacy notice</span></span>

<span data-ttu-id="7521c-109">Se você ativar o recurso de detecção de loja baseada em local, as informações do navegador do cliente são enviadas para o serviço local da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7521c-109">If you turn on the location-based store detection feature, information from the customer's browser is sent to a Microsoft location service.</span></span> <span data-ttu-id="7521c-110">Essas informações são usadas para fornecer conteúdo relevantes à localização aos clientes.</span><span class="sxs-lookup"><span data-stu-id="7521c-110">This information is then used to provide the customer content that is relevant to his or her location.</span></span> <span data-ttu-id="7521c-111">As informações enviadas do navegador do cliente e as informações baseadas em local retornadas ao cliente são sujeitas a política de conformidade de privacidade e cookie.</span><span class="sxs-lookup"><span data-stu-id="7521c-111">Both the information that is sent from the customer's browser and the location-based information that is returned to the customer are subject to privacy and cookie compliance policies.</span></span>

## <a name="turn-on-location-based-store-detection"></a><span data-ttu-id="7521c-112">Ativar detecção de lojas com base na localização</span><span class="sxs-lookup"><span data-stu-id="7521c-112">Turn on location-based store detection</span></span>

<span data-ttu-id="7521c-113">Para ativar a detecção de loja baseada em local no Comércio, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="7521c-113">To turn on location-based store detection in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="7521c-114">Nas ferramentas de criação, vá para nosso site.</span><span class="sxs-lookup"><span data-stu-id="7521c-114">In the authoring tool, go to your site.</span></span>
1. <span data-ttu-id="7521c-115">No painel de navegação à esquerda, selecione **Gerenciamento de sites**.</span><span class="sxs-lookup"><span data-stu-id="7521c-115">In the navigation pane on the left, select **Site Management**.</span></span>
1. <span data-ttu-id="7521c-116">Selecione **Configurações de site**.</span><span class="sxs-lookup"><span data-stu-id="7521c-116">Select **Site Settings**.</span></span>
1. <span data-ttu-id="7521c-117">Defina a opção **Habilitar detecção de loja baseada em local** como **Ligado**.</span><span class="sxs-lookup"><span data-stu-id="7521c-117">Set the **Enable location based store detection** option to **On**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7521c-118">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="7521c-118">Additional resources</span></span>

[<span data-ttu-id="7521c-119">Configure seu nome de domínio</span><span class="sxs-lookup"><span data-stu-id="7521c-119">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="7521c-120">Implantar um novo site de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="7521c-120">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="7521c-121">Criar um site de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="7521c-121">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="7521c-122">Associar um site online a um canal</span><span class="sxs-lookup"><span data-stu-id="7521c-122">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="7521c-123">Gerenciar arquivos robots.txt</span><span class="sxs-lookup"><span data-stu-id="7521c-123">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="7521c-124">Configurar páginas personalizadas para logons dos usuários</span><span class="sxs-lookup"><span data-stu-id="7521c-124">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="7521c-125">Adicionar suporte para uma rede de entrega de conteúdo (CDN)</span><span class="sxs-lookup"><span data-stu-id="7521c-125">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

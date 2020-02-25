---
title: Criar um site de comércio eletrônico
description: Este tópico descreve as etapas e informações necessárias para criar um novo site de comércio eletrônico no assistente para criação de sites do Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 01/23/2020
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
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3d3d8a290f06d9734be21f2d59152acac6857506
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002004"
---
# <a name="create-an-e-commerce-site"></a><span data-ttu-id="6ac4f-103">Criar um site de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="6ac4f-103">Create an e-Commerce site</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="6ac4f-104">Este tópico descreve as etapas e informações necessárias para criar um novo site de comércio eletrônico no assistente para criação de sites do Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6ac4f-104">This topic describes the steps and information required to create a new e-Commerce site in Dynamics 365 Commerce site builder.</span></span>

<span data-ttu-id="6ac4f-105">Antes de começar a desenvolver seu site de comércio eletrônico, primeiro você deve estabelecer um novo site no assistente para criação de sites.</span><span class="sxs-lookup"><span data-stu-id="6ac4f-105">Before you can start developing your e-Commerce site, you must first establish a new site in site builder.</span></span> 


<span data-ttu-id="6ac4f-106">Para começar a desenvolver seu site comercial online, primeiro você deve estabelecer um novo site no ambiente de criação de site.</span><span class="sxs-lookup"><span data-stu-id="6ac4f-106">To start to develop your e-Commerce site, you must first establish a new site in the site authoring environment.</span></span> <span data-ttu-id="6ac4f-107">Antes de criar um novo site, crie pelo menos uma loja online no Commerce.</span><span class="sxs-lookup"><span data-stu-id="6ac4f-107">Before you can create a new site, at least one online store must be created in Commerce.</span></span> 


## <a name="set-up-your-site"></a><span data-ttu-id="6ac4f-108">Configurar seu site</span><span class="sxs-lookup"><span data-stu-id="6ac4f-108">Set up your site</span></span>

<span data-ttu-id="6ac4f-109">Para configurar seu site, faça o seguinte.</span><span class="sxs-lookup"><span data-stu-id="6ac4f-109">To set up your site, do the following.</span></span>

1. <span data-ttu-id="6ac4f-110">Abra o ambiente do assistente para criação de sites.</span><span class="sxs-lookup"><span data-stu-id="6ac4f-110">Open the site builder environment.</span></span> <span data-ttu-id="6ac4f-111">Você pode encontrar um link para o assistente de criação de sites no Microsoft Lifecycle Services (LCS), na página de recursos do ambiente do Commerce.</span><span class="sxs-lookup"><span data-stu-id="6ac4f-111">You can find a link to site builder in Microsoft Lifecycle Services (LCS) in the environment features page for Commerce.</span></span>
1. <span data-ttu-id="6ac4f-112">Na página inicial do ambiente de criação local, selecione **Novo site**.</span><span class="sxs-lookup"><span data-stu-id="6ac4f-112">On the home page for the site authoring environment, select **New site**.</span></span>
1. <span data-ttu-id="6ac4f-113">Na caixa de diálogo **Novo site**, forneça as seguintes informações.</span><span class="sxs-lookup"><span data-stu-id="6ac4f-113">In the **New site** dialog box, provide the following information.</span></span>

| <span data-ttu-id="6ac4f-114">Campo</span><span class="sxs-lookup"><span data-stu-id="6ac4f-114">Field</span></span>                               | <span data-ttu-id="6ac4f-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="6ac4f-115">Description</span></span> |
|-------------------------------------|-------------|
| <span data-ttu-id="6ac4f-116">Nome do site</span><span class="sxs-lookup"><span data-stu-id="6ac4f-116">Site name</span></span>                           | <span data-ttu-id="6ac4f-117">Insira o nome para exibição a ser usado para o site no ambiente de criação do site.</span><span class="sxs-lookup"><span data-stu-id="6ac4f-117">Enter the display name that should be used for your site in the site authoring environment.</span></span> <span data-ttu-id="6ac4f-118">Este nome é visível somente no ambiente de criação e não será exibido a clientes.</span><span class="sxs-lookup"><span data-stu-id="6ac4f-118">This name is visible only in the authoring environment and will not be shown to customers.</span></span> |
| <span data-ttu-id="6ac4f-119">Grupo de segurança dos administradores de sistema</span><span class="sxs-lookup"><span data-stu-id="6ac4f-119">Site administrator's security group</span></span> | <span data-ttu-id="6ac4f-120">Especifique o grupo de segurança do Microsoft Azure Active Directory (Azure AD) que gerencia os usuários com a função de administrador de site nesse site.</span><span class="sxs-lookup"><span data-stu-id="6ac4f-120">Specify the Microsoft Azure Active Directory (Azure AD) security group that manages users who have the site administrator role in this site.</span></span> |
| <span data-ttu-id="6ac4f-121">Canal padrão (número da unidade operacional)</span><span class="sxs-lookup"><span data-stu-id="6ac4f-121">Default channel (operating unit number)</span></span> | <span data-ttu-id="6ac4f-122">Selecione a loja online para a qual esse site servirá de loja da Web.</span><span class="sxs-lookup"><span data-stu-id="6ac4f-122">Select the online store that this site will serve as the web storefront for.</span></span> <span data-ttu-id="6ac4f-123">Se desejar que seu site de comércio online dê suporte a vários armazenamentos online, você deve associar as lojas com o site nas **Configurações de site** depois de configurar o site.</span><span class="sxs-lookup"><span data-stu-id="6ac4f-123">If you want your e-Commerce site to support multiple online stores, you must associate the stores with your site in **Site settings** after the site is set up.</span></span> |
| <span data-ttu-id="6ac4f-124">Idioma padrão</span><span class="sxs-lookup"><span data-stu-id="6ac4f-124">Default language</span></span>                            | <span data-ttu-id="6ac4f-125">Especifique o idioma padrão para esses armazenamento e marketing online.</span><span class="sxs-lookup"><span data-stu-id="6ac4f-125">Specify the default language for this online store and market.</span></span> <span data-ttu-id="6ac4f-126">Uma loja online pode oferecer suporte a vários idiomas.</span><span class="sxs-lookup"><span data-stu-id="6ac4f-126">An online store can support multiple languages.</span></span> <span data-ttu-id="6ac4f-127">Se desejar oferecer suporte a vários idiomas para esta armazenamento online ou outra loja online, você pode configurar o suporte em **Configurações de site** depois de configurá-lo.</span><span class="sxs-lookup"><span data-stu-id="6ac4f-127">If you want to support multiple languages for this online store or another online store, you can configure that support in **Site settings** after the site is set up.</span></span>  |
| <span data-ttu-id="6ac4f-128">Domínio</span><span class="sxs-lookup"><span data-stu-id="6ac4f-128">Domain</span></span>                              | <span data-ttu-id="6ac4f-129">Selecione um nome de domínio que servirá como o domínio para essa loja online.</span><span class="sxs-lookup"><span data-stu-id="6ac4f-129">Select a domain name that will serve as the domain for this online store.</span></span> <span data-ttu-id="6ac4f-130">Se você não tiver configurado quaisquer domínios no LCS, você pode deixar esse campo em branco.</span><span class="sxs-lookup"><span data-stu-id="6ac4f-130">If you haven't configured any domains in LCS, you can leave this field blank.</span></span> <span data-ttu-id="6ac4f-131">Depois de seu domínio ser configurado no LCS, você deve adicioná-lo em sua loja online em **Configurações de site**.</span><span class="sxs-lookup"><span data-stu-id="6ac4f-131">After your domain is configured in LCS, you must add it to your online store in **Site settings**.</span></span>  |
| <span data-ttu-id="6ac4f-132">Caminho</span><span class="sxs-lookup"><span data-stu-id="6ac4f-132">Path</span></span>                              | <span data-ttu-id="6ac4f-133">Quando o site oferece suporte a mais de um idioma em determinado nome de domínio, use o campo de caminho para criar uma URL de site única para esse domínio e combinação de idioma.</span><span class="sxs-lookup"><span data-stu-id="6ac4f-133">When your site supports more than one language for a given domain name, use the path field to create a unique site URL for that domain and language combination.</span></span> <span data-ttu-id="6ac4f-134">Se o idioma especificado no campo **Idioma padrão** é o único idioma para o qual você oferecerá suporte nesse domínio ou continuará a ser o idioma padrão após ter localizado seu site em idiomas adicionais, recomendamos que você deixe essa campo em branco.</span><span class="sxs-lookup"><span data-stu-id="6ac4f-134">If the language you specified in the **Default language** field is the only language you will support for this domain, or will continue to be the default language after you have localized your site into additional languages, we recommend that you leave this field empty.</span></span> |


<span data-ttu-id="6ac4f-135">Depois que o site for criado, você pode verificar se está associado ao repositório online selecionando a guia **Produtos**. Você deve verificar a classificação do produto que foi atribuída à loja online.</span><span class="sxs-lookup"><span data-stu-id="6ac4f-135">After your site is created, you can verify that it is associated with your online store by selecting the **Products** tab. You should see the assortment of products that has been allocated to the online store.</span></span> <span data-ttu-id="6ac4f-136">Você também pode usar o menu suspenso na parte superior esquerda da página para acessar os produtos alocados por categoria.</span><span class="sxs-lookup"><span data-stu-id="6ac4f-136">You can also use the drop-down menu in the upper left of the page to access the allocated products by category.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6ac4f-137">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="6ac4f-137">Additional resources</span></span>

[<span data-ttu-id="6ac4f-138">Configure seu nome de domínio</span><span class="sxs-lookup"><span data-stu-id="6ac4f-138">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="6ac4f-139">Implantar um novo site de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="6ac4f-139">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="6ac4f-140">Associar um site online a um canal</span><span class="sxs-lookup"><span data-stu-id="6ac4f-140">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="6ac4f-141">Gerenciar arquivos robots.txt</span><span class="sxs-lookup"><span data-stu-id="6ac4f-141">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="6ac4f-142">Configurar páginas personalizadas para logons dos usuários</span><span class="sxs-lookup"><span data-stu-id="6ac4f-142">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="6ac4f-143">Adicionar suporte para uma rede de entrega de conteúdo (CDN)</span><span class="sxs-lookup"><span data-stu-id="6ac4f-143">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="6ac4f-144">Habilitar detecção de lojas com base na localização</span><span class="sxs-lookup"><span data-stu-id="6ac4f-144">Enable location-based store detection</span></span>](enable-store-detection.md)

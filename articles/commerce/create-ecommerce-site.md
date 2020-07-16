---
title: Criar um site de comércio eletrônico
description: Este tópico descreve as etapas e informações necessárias para criar um novo site de comércio eletrônico no assistente para criação de sites do Dynamics 365 Commerce.
author: bicyclingfool
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
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ea3517a4f2b84db8a87a97d2f644bb4436f8693f
ms.sourcegitcommit: adf196c51e2b6f532d99c177b4c6778cea8a2efc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2020
ms.locfileid: "3533427"
---
# <a name="create-an-e-commerce-site"></a><span data-ttu-id="ff2ce-103">Criar um site de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="ff2ce-103">Create an e-Commerce site</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ff2ce-104">Este tópico descreve as etapas e informações necessárias para criar um novo site de comércio eletrônico no assistente para criação de sites do Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ff2ce-104">This topic describes the steps and information required to create a new e-Commerce site in Dynamics 365 Commerce site builder.</span></span>

<span data-ttu-id="ff2ce-105">Quando você licenciar os recursos de comércio eletrônico, o Site Builder será provisionado com um site de início que você poderá usar como base para seu próprio site.</span><span class="sxs-lookup"><span data-stu-id="ff2ce-105">When you license the e-Commerce capabilities, site builder will be provisioned with a starter site that you can use as a basis for your own site.</span></span> <span data-ttu-id="ff2ce-106">Mas se você quiser começar do zero ou estabelecer um segundo site, precisará estabelecer um novo site no ambiente de criação de sites.</span><span class="sxs-lookup"><span data-stu-id="ff2ce-106">However, if you want to start from scratch or if you want to establish a second site, you will need to establish a new site in the site authoring environment.</span></span> 

## <a name="set-up-your-site"></a><span data-ttu-id="ff2ce-107">Configurar seu site</span><span class="sxs-lookup"><span data-stu-id="ff2ce-107">Set up your site</span></span>

<span data-ttu-id="ff2ce-108">Para configurar seu site, faça o seguinte.</span><span class="sxs-lookup"><span data-stu-id="ff2ce-108">To set up your site, do the following.</span></span>

1. <span data-ttu-id="ff2ce-109">Abra o ambiente do assistente para criação de sites.</span><span class="sxs-lookup"><span data-stu-id="ff2ce-109">Open the site builder environment.</span></span> <span data-ttu-id="ff2ce-110">Você pode encontrar um link para o assistente de criação de sites no Microsoft Lifecycle Services (LCS), na página de recursos do ambiente do Commerce.</span><span class="sxs-lookup"><span data-stu-id="ff2ce-110">You can find a link to site builder in Microsoft Lifecycle Services (LCS) in the environment features page for Commerce.</span></span>
1. <span data-ttu-id="ff2ce-111">Na página inicial do ambiente de criação local, selecione **Novo site**.</span><span class="sxs-lookup"><span data-stu-id="ff2ce-111">On the home page for the site authoring environment, select **New site**.</span></span>
1. <span data-ttu-id="ff2ce-112">Na caixa de diálogo **Novo site**, forneça as seguintes informações.</span><span class="sxs-lookup"><span data-stu-id="ff2ce-112">In the **New site** dialog box, provide the following information.</span></span>

| <span data-ttu-id="ff2ce-113">Campo</span><span class="sxs-lookup"><span data-stu-id="ff2ce-113">Field</span></span>                               | <span data-ttu-id="ff2ce-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="ff2ce-114">Description</span></span> |
|-------------------------------------|-------------|
| <span data-ttu-id="ff2ce-115">Nome do site</span><span class="sxs-lookup"><span data-stu-id="ff2ce-115">Site name</span></span>                           | <span data-ttu-id="ff2ce-116">Insira o nome para exibição a ser usado para o site no ambiente de criação do site.</span><span class="sxs-lookup"><span data-stu-id="ff2ce-116">Enter the display name that should be used for your site in the site authoring environment.</span></span> <span data-ttu-id="ff2ce-117">Este nome é visível somente no ambiente de criação e não será exibido a clientes.</span><span class="sxs-lookup"><span data-stu-id="ff2ce-117">This name is visible only in the authoring environment and will not be shown to customers.</span></span> |
| <span data-ttu-id="ff2ce-118">Grupo de segurança dos administradores de sistema</span><span class="sxs-lookup"><span data-stu-id="ff2ce-118">Site administrator's security group</span></span> | <span data-ttu-id="ff2ce-119">Especifique o grupo de segurança do Microsoft Azure Active Directory (Azure AD) que gerencia os usuários com a função de administrador de site nesse site.</span><span class="sxs-lookup"><span data-stu-id="ff2ce-119">Specify the Microsoft Azure Active Directory (Azure AD) security group that manages users who have the site administrator role in this site.</span></span> |
| <span data-ttu-id="ff2ce-120">Canal padrão (número da unidade operacional)</span><span class="sxs-lookup"><span data-stu-id="ff2ce-120">Default channel (operating unit number)</span></span> | <span data-ttu-id="ff2ce-121">Selecione a loja online para a qual esse site servirá de loja da Web.</span><span class="sxs-lookup"><span data-stu-id="ff2ce-121">Select the online store that this site will serve as the web storefront for.</span></span> <span data-ttu-id="ff2ce-122">Se desejar que seu site de comércio online dê suporte a vários armazenamentos online, você deve associar as lojas com o site nas **Configurações de site** depois de configurar o site.</span><span class="sxs-lookup"><span data-stu-id="ff2ce-122">If you want your e-Commerce site to support multiple online stores, you must associate the stores with your site in **Site settings** after the site is set up.</span></span> |
| <span data-ttu-id="ff2ce-123">Idioma padrão</span><span class="sxs-lookup"><span data-stu-id="ff2ce-123">Default language</span></span>                            | <span data-ttu-id="ff2ce-124">Especifique o idioma padrão para esses armazenamento e marketing online.</span><span class="sxs-lookup"><span data-stu-id="ff2ce-124">Specify the default language for this online store and market.</span></span> <span data-ttu-id="ff2ce-125">Uma loja online pode oferecer suporte a vários idiomas.</span><span class="sxs-lookup"><span data-stu-id="ff2ce-125">An online store can support multiple languages.</span></span> <span data-ttu-id="ff2ce-126">Se desejar oferecer suporte a vários idiomas para esta armazenamento online ou outra loja online, você pode configurar o suporte em **Configurações de site** depois de configurá-lo.</span><span class="sxs-lookup"><span data-stu-id="ff2ce-126">If you want to support multiple languages for this online store or another online store, you can configure that support in **Site settings** after the site is set up.</span></span>  |
| <span data-ttu-id="ff2ce-127">Domínio</span><span class="sxs-lookup"><span data-stu-id="ff2ce-127">Domain</span></span>                              | <span data-ttu-id="ff2ce-128">Selecione um nome de domínio que servirá como o domínio para essa loja online.</span><span class="sxs-lookup"><span data-stu-id="ff2ce-128">Select a domain name that will serve as the domain for this online store.</span></span> <span data-ttu-id="ff2ce-129">Se você não tiver configurado quaisquer domínios no LCS, você pode deixar esse campo em branco.</span><span class="sxs-lookup"><span data-stu-id="ff2ce-129">If you haven't configured any domains in LCS, you can leave this field blank.</span></span> <span data-ttu-id="ff2ce-130">Depois de seu domínio ser configurado no LCS, você deve adicioná-lo em sua loja online em **Configurações de site**.</span><span class="sxs-lookup"><span data-stu-id="ff2ce-130">After your domain is configured in LCS, you must add it to your online store in **Site settings**.</span></span>  |
| <span data-ttu-id="ff2ce-131">Caminho</span><span class="sxs-lookup"><span data-stu-id="ff2ce-131">Path</span></span>                              | <span data-ttu-id="ff2ce-132">Quando o site oferece suporte a mais de um idioma em determinado nome de domínio, use o campo de caminho para criar uma URL de site única para esse domínio e combinação de idioma.</span><span class="sxs-lookup"><span data-stu-id="ff2ce-132">When your site supports more than one language for a given domain name, use the path field to create a unique site URL for that domain and language combination.</span></span> <span data-ttu-id="ff2ce-133">Se o idioma especificado no campo **Idioma padrão** é o único idioma para o qual você oferecerá suporte nesse domínio ou continuará a ser o idioma padrão após ter localizado seu site em idiomas adicionais, recomendamos que você deixe essa campo em branco.</span><span class="sxs-lookup"><span data-stu-id="ff2ce-133">If the language you specified in the **Default language** field is the only language you will support for this domain, or will continue to be the default language after you have localized your site into additional languages, we recommend that you leave this field empty.</span></span> |


<span data-ttu-id="ff2ce-134">Depois que o site for criado, você pode verificar se está associado ao repositório online selecionando a guia **Produtos**. Você deve verificar a classificação do produto que foi atribuída à loja online.</span><span class="sxs-lookup"><span data-stu-id="ff2ce-134">After your site is created, you can verify that it is associated with your online store by selecting the **Products** tab. You should see the assortment of products that has been allocated to the online store.</span></span> <span data-ttu-id="ff2ce-135">Você também pode usar o menu suspenso na parte superior esquerda da página para acessar os produtos alocados por categoria.</span><span class="sxs-lookup"><span data-stu-id="ff2ce-135">You can also use the drop-down menu in the upper left of the page to access the allocated products by category.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ff2ce-136">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="ff2ce-136">Additional resources</span></span>

[<span data-ttu-id="ff2ce-137">Configure seu nome de domínio</span><span class="sxs-lookup"><span data-stu-id="ff2ce-137">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="ff2ce-138">Implantar um novo site de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="ff2ce-138">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="ff2ce-139">Associar um site online a um canal</span><span class="sxs-lookup"><span data-stu-id="ff2ce-139">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="ff2ce-140">Gerenciar arquivos robots.txt</span><span class="sxs-lookup"><span data-stu-id="ff2ce-140">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="ff2ce-141">Carregar redirecionamentos de URL em massa</span><span class="sxs-lookup"><span data-stu-id="ff2ce-141">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="ff2ce-142">Configurar um locatário B2C do Commerce</span><span class="sxs-lookup"><span data-stu-id="ff2ce-142">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="ff2ce-143">Configurar páginas personalizadas para logons dos usuários</span><span class="sxs-lookup"><span data-stu-id="ff2ce-143">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="ff2ce-144">Configurar múltiplos locatários B2C em um ambiente do Commerce</span><span class="sxs-lookup"><span data-stu-id="ff2ce-144">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="ff2ce-145">Adicionar suporte para uma rede de entrega de conteúdo (CDN)</span><span class="sxs-lookup"><span data-stu-id="ff2ce-145">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="ff2ce-146">Habilitar detecção de lojas com base na localização</span><span class="sxs-lookup"><span data-stu-id="ff2ce-146">Enable location-based store detection</span></span>](enable-store-detection.md)

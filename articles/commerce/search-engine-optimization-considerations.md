---
title: Considerações de otimização do mecanismo de pesquisa (SEO) para seu site
description: Este tópico abrange considerações de otimização do mecanismo de pesquisa (SEO) para seu site desde o desenvolvimento até a produção.
author: psimolin
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c4d1a4a1b14f7af1db1c53bd9ee1993cc9187609
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254784"
---
# <a name="search-engine-optimization-seo-considerations-for-your-site"></a><span data-ttu-id="08e5c-103">Considerações de otimização do mecanismo de pesquisa (SEO) para seu site</span><span class="sxs-lookup"><span data-stu-id="08e5c-103">Search engine optimization (SEO) considerations for your site</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="08e5c-104">Este tópico abrange cada consideração de otimização do mecanismo de pesquisa (SEO) para seu site desde o desenvolvimento até a produção.</span><span class="sxs-lookup"><span data-stu-id="08e5c-104">This topic covers earch engine optimization (SEO) considerations for your site from development to production.</span></span>

## <a name="a-site-that-is-under-development"></a><span data-ttu-id="08e5c-105">Um site que está em desenvolvimento</span><span class="sxs-lookup"><span data-stu-id="08e5c-105">A site that is under development</span></span>

<span data-ttu-id="08e5c-106">Quando um site estiver em desenvolvimento, todas as páginas do local deverão ter a meta de **NOINDEX** e **NOFOLLOW** , de forma que os mecanismos de pesquisa não indexem páginas e versões de desenvolvimento de armazenamento do site no cache.</span><span class="sxs-lookup"><span data-stu-id="08e5c-106">While a site is under development, all site pages should have the **NOINDEX** and **NOFOLLOW** meta tags, so that search engines don't index the pages and store development versions of your site in their cache.</span></span> <span data-ttu-id="08e5c-107">Para fazer essa configuração, você deve adicionar o módulo de marcas meta padrão ao modelo de página do site.</span><span class="sxs-lookup"><span data-stu-id="08e5c-107">To do this configuration, you must add the default meta tags module to the site page template.</span></span> <span data-ttu-id="08e5c-108">As propriedades de marcas meta padrão ficarão disponíveis na seção de propriedades de SEO no editor de páginas.</span><span class="sxs-lookup"><span data-stu-id="08e5c-108">The default meta tags properties will then be available in the SEO properties section in the page editor.</span></span> <span data-ttu-id="08e5c-109">Você pode usar essas propriedades para gerenciar as marcas meta.</span><span class="sxs-lookup"><span data-stu-id="08e5c-109">You can use these properties to manage the meta tags.</span></span>

## <a name="soft-launch-of-a-site"></a><span data-ttu-id="08e5c-110">Inicialização flexível de um site</span><span class="sxs-lookup"><span data-stu-id="08e5c-110">Soft launch of a site</span></span>

<span data-ttu-id="08e5c-111">Durante uma "inicialização flexível", um site é disponibilizado para um público ou mercado limitado antes que ocorra o lançamento completo.</span><span class="sxs-lookup"><span data-stu-id="08e5c-111">During a "soft launch," a website is made available to a limited audience or market before the full launch occurs.</span></span> <span data-ttu-id="08e5c-112">Se não fizer uma inicialização flexível de seu site, deixe as meta marcas **NOINDEX** no lugar.</span><span class="sxs-lookup"><span data-stu-id="08e5c-112">If you do a soft launch of your website, you should consider leaving the **NOINDEX** meta tags in place.</span></span> <span data-ttu-id="08e5c-113">Assim, você ajuda a garantir que a inicialização flexível permaneça restrita ao público limitado que você deseja alcançar.</span><span class="sxs-lookup"><span data-stu-id="08e5c-113">In this way, you help guarantee that the soft launch remains restricted to the limited audience that you want to reach.</span></span>

## <a name="a-site-that-is-in-production"></a><span data-ttu-id="08e5c-114">Um site que está em produção</span><span class="sxs-lookup"><span data-stu-id="08e5c-114">A site that is in production</span></span>

<span data-ttu-id="08e5c-115">Quando um site estiver em produção, certifique-se de que todas as páginas do site estão marcadas corretamente.</span><span class="sxs-lookup"><span data-stu-id="08e5c-115">When a site is in production, you should make sure that all site pages are correctly tagged.</span></span> <span data-ttu-id="08e5c-116">O Microsoft Dynamics 365 Commerce usa as informações inseridas em uma página para renderizar todas as informações de SEO nessa página.</span><span class="sxs-lookup"><span data-stu-id="08e5c-116">Microsoft Dynamics 365 Commerce uses the information that is entered for a page to render all the SEO information on that page.</span></span> <span data-ttu-id="08e5c-117">Os seguintes módulos fornecem essa funcionalidade: resumo da página da categoria, resumo da página da lista e resumo da página do produto.</span><span class="sxs-lookup"><span data-stu-id="08e5c-117">The following modules provide this functionality: category page summary, list page summary, and product page summary.</span></span>

<span data-ttu-id="08e5c-118">Para otimizar a indexação do mecanismo de pesquisa, a estrutura de renderização usa as informações das propriedades de SEO configuradas no Dynamics 365 Commerce e as informações específicas do módulo.</span><span class="sxs-lookup"><span data-stu-id="08e5c-118">To optimize search engine indexing, the rendering framework uses both information from the SEO properties that are configured in Dynamics 365 Commerce and module-specific information.</span></span> <span data-ttu-id="08e5c-119">Para um site em produção, verifique se o arquivo robots.txt permite a indexação de todo o site e se ele contém links para o documento do mapa do site publicado.</span><span class="sxs-lookup"><span data-stu-id="08e5c-119">For a site that is in production, you should make sure that the robots.txt file allows for indexing of your whole site, and that it contains links to your published site map document.</span></span> <span data-ttu-id="08e5c-120">Você deve ativar a funcionalidade de geração do mapa de site em **Configurações de Site\> Mapas de site habilitados**.</span><span class="sxs-lookup"><span data-stu-id="08e5c-120">You should turn on the site map generation functionality at **Site Settings \> Site maps enabled**.</span></span>

### <a name="page-seo-settings-for-internal-preview-limited-audiences-and-all-audiences"></a><span data-ttu-id="08e5c-121">Configurações de SEO da página para visualização interna, público limitado e todos os públicos.</span><span class="sxs-lookup"><span data-stu-id="08e5c-121">Page SEO settings for internal preview, limited audiences, and all audiences</span></span>

<span data-ttu-id="08e5c-122">Como o Dynamics 365 Commerce oferece suporte de visualizações autenticadas "você vê como vai aparecer" (WYSIWYG) no construtor de página visual, os autores podem preparar o conteúdo da página sem se preocupar com o fato de as informações ficarem visíveis para os visitantes do site.</span><span class="sxs-lookup"><span data-stu-id="08e5c-122">Because Dynamics 365 Commerce supports "what you see is what you get" (WYSIWYG) authenticated previews in visual page builder, authors can prepare their page content without having to worry that the information will become visible to site visitors.</span></span> <span data-ttu-id="08e5c-123">Se uma página deve ser publicada, mas sua exposição deve ser limitada, ela deve ter a marca meta **NOINDEX** , de forma que não será indexada pelos mecanismos de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="08e5c-123">If a page must be published, but its exposure must be limited, it should have the **NOINDEX** meta tag, so that it won't be indexed by search engines.</span></span> <span data-ttu-id="08e5c-124">Então, quando a página estiver pronta para todos os públicos, todos os metadados básicos de SEO deverão estar presentes, para maximizar a eficiência da indexação do mecanismo de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="08e5c-124">Then, when the page is ready for all audiences, all the basic SEO metadata should be present, to maximize the efficiency of search engine indexing.</span></span> <span data-ttu-id="08e5c-125">Além disso, a marca meta **NOLIMIT** deverá ser removida.</span><span class="sxs-lookup"><span data-stu-id="08e5c-125">Additionally, the **NOLIMIT** meta tag should be removed.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="08e5c-126">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="08e5c-126">Additional resources</span></span>

[<span data-ttu-id="08e5c-127">Gerenciar usuários e funções de comércio online</span><span class="sxs-lookup"><span data-stu-id="08e5c-127">Manage e-Commerce users and roles</span></span>](manage-ecommerce-users-roles.md)

[<span data-ttu-id="08e5c-128">Adicionar o código de script a páginas do site para oferecer suporte à telemetria</span><span class="sxs-lookup"><span data-stu-id="08e5c-128">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

[<span data-ttu-id="08e5c-129">Gerenciar a política de segurança de conteúdo (CSP)</span><span class="sxs-lookup"><span data-stu-id="08e5c-129">Manage Content Security Policy (CSP)</span></span>](manage-csp.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
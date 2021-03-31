---
title: Módulo de consentimento de cookie
description: Este tópico abrange os módulos de consentimento de cookies e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
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
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 57c8876f1faf08ce965ccd796551996a8651e2eb
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5213929"
---
# <a name="cookie-consent-module"></a><span data-ttu-id="a4b58-103">Módulo de consentimento de cookie</span><span class="sxs-lookup"><span data-stu-id="a4b58-103">Cookie consent module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a4b58-104">Este tópico abrange os módulos de consentimento de cookies e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a4b58-104">This topic covers cookie consent modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="a4b58-105">O módulo de consentimento de cookie solicita que os usuários do site forneçam explicitamente o consentimento para permitir cookies para qualquer recurso ou módulo que rastreie os cookies do navegador.</span><span class="sxs-lookup"><span data-stu-id="a4b58-105">The cookie consent module prompts site users to explicitly provide consent to allow cookies for any feature or module that tracks browser cookies.</span></span> <span data-ttu-id="a4b58-106">O consentimento é necessário na primeira vez que um usuário navega por um site em uma nova sessão do navegador.</span><span class="sxs-lookup"><span data-stu-id="a4b58-106">The consent is required the first time a site user browses a site in a new browser session.</span></span> <span data-ttu-id="a4b58-107">Quando o consentimento é recebido, ele é rastreado e não é solicitado novamente.</span><span class="sxs-lookup"><span data-stu-id="a4b58-107">When consent is received, it is tracked and the site user will not be prompted for consent again.</span></span> <span data-ttu-id="a4b58-108">Para obter mais informações, consulte [Conformidade do cookie](cookie-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="a4b58-108">For more information, see [Cookie compliance](cookie-compliance.md).</span></span>

<span data-ttu-id="a4b58-109">Se o consentimento de cookie do usuário do site não for recebido, os recursos ou módulos que exigirem esse consentimento não serão renderizados na página.</span><span class="sxs-lookup"><span data-stu-id="a4b58-109">If site user cookie consent is not received, any features or modules that require cookie consent will not be rendered on the page.</span></span> <span data-ttu-id="a4b58-110">Por exemplo, o módulo de finalização da compra, o módulo de compartilhamento social e o recurso de loja preferida exigem o consentimento de cookie e não serão renderizados se o consentimento do usuário do site não for recebido.</span><span class="sxs-lookup"><span data-stu-id="a4b58-110">For example, the checkout module, social share module, and preferred store feature all require cookie consent and will not be rendered if site user consent is not received.</span></span> 

<span data-ttu-id="a4b58-111">Um módulo de consentimento de cookie pode ser configurado no fragmento de cabeçalho de uma página para que possa ser imposto quando ela for carregada.</span><span class="sxs-lookup"><span data-stu-id="a4b58-111">A cookie consent module can be configured on a page's header fragment so that it can be enforced when the page loads.</span></span> <span data-ttu-id="a4b58-112">O módulo de consentimento de cookie deve ter uma mensagem clara informando o usuário sobre o uso de cookies no site e deve fornecer um link para a página de privacidade do site.</span><span class="sxs-lookup"><span data-stu-id="a4b58-112">The cookie consent module should have a clear message informing the site user about cookie usage on the site and should provide a link to the site's privacy page.</span></span>

<span data-ttu-id="a4b58-113">A ilustração a seguir destaca um exemplo de mensagem de consentimento de cookie com um link para a página de política de privacidade do site exibida no cabeçalho de uma página do site.</span><span class="sxs-lookup"><span data-stu-id="a4b58-113">The following illustration highlights an example of a cookie consent message with a link to the site's privacy policy page displayed on the header of a site page.</span></span>
<span data-ttu-id="a4b58-114">![Exemplo de um módulo de consentimento de cookie](./media/ecommerce-cookieconsent.png)</span><span class="sxs-lookup"><span data-stu-id="a4b58-114">![Example of a cookie consent module](./media/ecommerce-cookieconsent.png)</span></span>

## <a name="cookie-consent-module-properties"></a><span data-ttu-id="a4b58-115">Propriedades do módulo de consentimento de cookie</span><span class="sxs-lookup"><span data-stu-id="a4b58-115">Cookie consent module properties</span></span>

| <span data-ttu-id="a4b58-116">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="a4b58-116">Property name</span></span>             | <span data-ttu-id="a4b58-117">Alíquota</span><span class="sxs-lookup"><span data-stu-id="a4b58-117">Value</span></span>                 | <span data-ttu-id="a4b58-118">descrição</span><span class="sxs-lookup"><span data-stu-id="a4b58-118">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="a4b58-119">Rich Text</span><span class="sxs-lookup"><span data-stu-id="a4b58-119">Rich Text</span></span>                  | <span data-ttu-id="a4b58-120">Rich Text</span><span class="sxs-lookup"><span data-stu-id="a4b58-120">Rich Text</span></span> | <span data-ttu-id="a4b58-121">Especifica uma notificação de Rich Text para os usuários informando que o site usa cookies do navegador e que os usuários devem aceitar o uso de cookies para que o site seja totalmente funcional.</span><span class="sxs-lookup"><span data-stu-id="a4b58-121">Specifies a Rich Text notification to site users that the site uses browser cookies and that users should accept the use of cookies for the site to be fully functional.</span></span> |
| <span data-ttu-id="a4b58-122">Links</span><span class="sxs-lookup"><span data-stu-id="a4b58-122">Links</span></span> | <span data-ttu-id="a4b58-123">URL</span><span class="sxs-lookup"><span data-stu-id="a4b58-123">URL</span></span> | <span data-ttu-id="a4b58-124">Um ou mais links podem ser adicionados à página de privacidade de um site que descreve os tipos de cookies que são rastreados nele.</span><span class="sxs-lookup"><span data-stu-id="a4b58-124">One or more links can be added to a site's privacy page that describes the types of cookies that are tracked on the site.</span></span> |

## <a name="add-a-cookie-consent-module-to-site-pages"></a><span data-ttu-id="a4b58-125">Adicionar um módulo de consentimento de cookie a páginas do site</span><span class="sxs-lookup"><span data-stu-id="a4b58-125">Add a cookie consent module to site pages</span></span>

<span data-ttu-id="a4b58-126">Para adicionar com eficiência um módulo de consentimento de cookie a várias páginas do site, ele pode ser adicionado a um fragmento de cabeçalho de página compartilhado.</span><span class="sxs-lookup"><span data-stu-id="a4b58-126">To efficiently add a cookie consent module to multiple site pages, it can be added to a shared page header fragment.</span></span> <span data-ttu-id="a4b58-127">Depois que o fragmento de cabeçalho for adicionado a todas as páginas do site, uma notificação de consentimento de cookie será automaticamente renderizada na primeira vez em que o usuário navegar até qualquer página do site.</span><span class="sxs-lookup"><span data-stu-id="a4b58-127">After the header fragment is added to all site pages, a cookie consent notification will automatically be rendered the first time a site user navigates to any site page.</span></span>

<span data-ttu-id="a4b58-128">Para obter mais informações sobre fragmentos e módulos de cabeçalho, consulte [Módulo de cabeçalho](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="a4b58-128">For more information about header fragments and modules, see [Header module](author-header-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a4b58-129">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="a4b58-129">Additional resources</span></span>

[<span data-ttu-id="a4b58-130">Visão geral da biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="a4b58-130">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="a4b58-131">Módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="a4b58-131">Header module</span></span>](author-header-module.md) 

[<span data-ttu-id="a4b58-132">Compatível com cookies</span><span class="sxs-lookup"><span data-stu-id="a4b58-132">Cookie compliance</span></span>](cookie-compliance.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
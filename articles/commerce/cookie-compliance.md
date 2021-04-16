---
title: Compatível com cookies
description: Este tópico descreve considerações sobre conformidade de cookies e as políticas padrão incluídas no Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 08/31/2020
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
ms.openlocfilehash: 2cc2089bc3052c0c59cb0414f8301123a9a30df2
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796018"
---
# <a name="cookie-compliance"></a><span data-ttu-id="40ab7-103">Compatível com cookies</span><span class="sxs-lookup"><span data-stu-id="40ab7-103">Cookie compliance</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="40ab7-104">Este tópico descreve considerações sobre conformidade de cookies e as políticas padrão incluídas no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="40ab7-104">This topic describes considerations for cookie compliance and the default policies that are included in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="40ab7-105">A privacidade é um fator importante ao rastrear tecnologias que afetem clientes de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="40ab7-105">Privacy is an important factor when tracking technologies that affect e-Commerce customers.</span></span> <span data-ttu-id="40ab7-106">Por causa dos padrões de conformidade de privacidade, como a norma de proteção de dados gerais (GDPR) na União Europeia (UE), as diretrizes de privacidade eletrônica devem ser consideradas para qualquer site ativo hoje.</span><span class="sxs-lookup"><span data-stu-id="40ab7-106">Because of privacy compliance standards such as the General Data Protection Regulation (GDPR) in the European Union (EU), electronic privacy guidelines must be considered for any site that is active today.</span></span> <span data-ttu-id="40ab7-107">Como muitos sites de comércio eletrônico são globalmente acessíveis por padrão, é importante que você revise os padrões de conformidade para seu site de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="40ab7-107">Because many e-Commerce sites are globally accessible by default, it's important that you review the compliance standards for your e-Commerce site.</span></span>

<span data-ttu-id="40ab7-108">Para saber mais sobre os princípios básicos usados pela Microsoft para conformidade com cookies, visite o [Microsoft Trust Center](https://www.microsoft.com/trust-center).</span><span class="sxs-lookup"><span data-stu-id="40ab7-108">To learn more about the basic principles that Microsoft uses for cookie compliance, visit the [Microsoft Trust Center](https://www.microsoft.com/trust-center).</span></span> <span data-ttu-id="40ab7-109">Nesse site, você também pode obter mais informações sobre áreas de conformidade e privacidade.</span><span class="sxs-lookup"><span data-stu-id="40ab7-109">On that site, you can also get more information about areas of compliance and privacy.</span></span>

<span data-ttu-id="40ab7-110">A tabela a seguir mostra a lista de referência atual de cookies colocados por sites do Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="40ab7-110">The following table shows the current reference list of cookies placed by Dynamics 365 Commerce sites.</span></span>

| <span data-ttu-id="40ab7-111">Nome do cookie</span><span class="sxs-lookup"><span data-stu-id="40ab7-111">Cookie name</span></span>                               | <span data-ttu-id="40ab7-112">Uso</span><span class="sxs-lookup"><span data-stu-id="40ab7-112">Usage</span></span>                                                        |
| ------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="40ab7-113">.AspNet.Cookies</span><span class="sxs-lookup"><span data-stu-id="40ab7-113">.AspNet.Cookies</span></span>                             | <span data-ttu-id="40ab7-114">Armazene cookies de autenticação do Microsoft Azure Active Directory (Azure AD) para logon único (SSO).</span><span class="sxs-lookup"><span data-stu-id="40ab7-114">Store Microsoft Azure Active Directory (Azure AD) authentication cookies for single sign-on (SSO).</span></span> <span data-ttu-id="40ab7-115">Armazena informações de entidade de segurança do usuário criptografadas (nome, sobrenome, email).</span><span class="sxs-lookup"><span data-stu-id="40ab7-115">Stores encrypted user principal information (name, surname, email).</span></span> |
| <span data-ttu-id="40ab7-116">&#95;msdyn365___cart&#95;</span><span class="sxs-lookup"><span data-stu-id="40ab7-116">&#95;msdyn365___cart&#95;</span></span>                           | <span data-ttu-id="40ab7-117">ID do carrinho da loja para obter a lista de produtos adicionada à instância do carrinho.</span><span class="sxs-lookup"><span data-stu-id="40ab7-117">Store cart ID used to obtain list of products added to cart instance.</span></span> |
| <span data-ttu-id="40ab7-118">&#95;msdyn365___ucc&#95;</span><span class="sxs-lookup"><span data-stu-id="40ab7-118">&#95;msdyn365___ucc&#95;</span></span>                            | <span data-ttu-id="40ab7-119">Rastreamento de consentimento de conformidade com cookies.</span><span class="sxs-lookup"><span data-stu-id="40ab7-119">Cookie compliance consent tracking.</span></span>                          |
| <span data-ttu-id="40ab7-120">ai_session</span><span class="sxs-lookup"><span data-stu-id="40ab7-120">ai_session</span></span>                                  | <span data-ttu-id="40ab7-121">Detecta quantas sessões de atividade do usuário incluíram determinadas páginas e recursos do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="40ab7-121">Detects how many sessions of user activity have included certain pages and features of the app.</span></span> |
| <span data-ttu-id="40ab7-122">ai_user</span><span class="sxs-lookup"><span data-stu-id="40ab7-122">ai_user</span></span>                                     | <span data-ttu-id="40ab7-123">Detecta quantas pessoas usaram o aplicativo e seus recursos.</span><span class="sxs-lookup"><span data-stu-id="40ab7-123">Detects how many people used the app and its features.</span></span> <span data-ttu-id="40ab7-124">Os usuários são contados usando IDs anônimas.</span><span class="sxs-lookup"><span data-stu-id="40ab7-124">Users are counted using anonymous IDs.</span></span> |
| <span data-ttu-id="40ab7-125">b2cru</span><span class="sxs-lookup"><span data-stu-id="40ab7-125">b2cru</span></span>                                       | <span data-ttu-id="40ab7-126">Armazena a URL de redirecionamento de forma dinâmica.</span><span class="sxs-lookup"><span data-stu-id="40ab7-126">Stores redirect URL dynamically.</span></span>                              |
| <span data-ttu-id="40ab7-127">JSESSIONID</span><span class="sxs-lookup"><span data-stu-id="40ab7-127">JSESSIONID</span></span>                                  | <span data-ttu-id="40ab7-128">Usado pelo conector de pagamento Adyen para armazenar a sessão do usuário.</span><span class="sxs-lookup"><span data-stu-id="40ab7-128">Used by payment connector Adyen to store user session.</span></span>       |
| <span data-ttu-id="40ab7-129">OpenIdConnect.nonce.&#42;</span><span class="sxs-lookup"><span data-stu-id="40ab7-129">OpenIdConnect.nonce.&#42;</span></span>                       | <span data-ttu-id="40ab7-130">Autenticação</span><span class="sxs-lookup"><span data-stu-id="40ab7-130">Authentication</span></span>                                               |
| <span data-ttu-id="40ab7-131">x-ms-cpim-cache:.&#42;</span><span class="sxs-lookup"><span data-stu-id="40ab7-131">x-ms-cpim-cache:.&#42;</span></span>                          | <span data-ttu-id="40ab7-132">Usado para manter o estado da solicitação.</span><span class="sxs-lookup"><span data-stu-id="40ab7-132">Used for maintaining the request state.</span></span>                      |
| <span data-ttu-id="40ab7-133">x-ms-cpim-csrf</span><span class="sxs-lookup"><span data-stu-id="40ab7-133">x-ms-cpim-csrf</span></span>                              | <span data-ttu-id="40ab7-134">Token de solicitação intersite forjada (CRSF) usado para proteção contra CRSF.</span><span class="sxs-lookup"><span data-stu-id="40ab7-134">Cross-site request forgery (CRSF) token used for protection from CRSF.</span></span>     |
| <span data-ttu-id="40ab7-135">x-ms-cpim-dc</span><span class="sxs-lookup"><span data-stu-id="40ab7-135">x-ms-cpim-dc</span></span>                                | <span data-ttu-id="40ab7-136">Usado para rotear solicitações para a instância apropriada do servidor de autenticação de produção.</span><span class="sxs-lookup"><span data-stu-id="40ab7-136">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="40ab7-137">x-ms-cpim-rc.&#42;</span><span class="sxs-lookup"><span data-stu-id="40ab7-137">x-ms-cpim-rc.&#42;</span></span>                              | <span data-ttu-id="40ab7-138">Usado para rotear solicitações para a instância apropriada do servidor de autenticação de produção.</span><span class="sxs-lookup"><span data-stu-id="40ab7-138">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="40ab7-139">x-ms-cpim-slice</span><span class="sxs-lookup"><span data-stu-id="40ab7-139">x-ms-cpim-slice</span></span>                             | <span data-ttu-id="40ab7-140">Usado para rotear solicitações para a instância apropriada do servidor de autenticação de produção.</span><span class="sxs-lookup"><span data-stu-id="40ab7-140">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="40ab7-141">x-ms-cpim-sso:rushmoreb2c.onmicrosoft.com_0</span><span class="sxs-lookup"><span data-stu-id="40ab7-141">x-ms-cpim-sso:rushmoreb2c.onmicrosoft.com_0</span></span> | <span data-ttu-id="40ab7-142">Usado para manter a sessão SSO.</span><span class="sxs-lookup"><span data-stu-id="40ab7-142">Used for maintaining the SSO session.</span></span>                        |
| <span data-ttu-id="40ab7-143">x-ms-cpim-trans</span><span class="sxs-lookup"><span data-stu-id="40ab7-143">x-ms-cpim-trans</span></span>                             | <span data-ttu-id="40ab7-144">Usado para rastrear transações (o número de guias abertas na autenticação de um site business-to-consumer (B2C)), incluindo a transação atual.</span><span class="sxs-lookup"><span data-stu-id="40ab7-144">Used for tracking transactions (the number of open tabs authenticating against a business-to-consumer (B2C) site), including the current transaction.</span></span> |

## <a name="site-user-cookie-consent-on-an-e-commerce-site"></a><span data-ttu-id="40ab7-145">Consentimento de cookie de usuário de site em um site de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="40ab7-145">Site user cookie consent on an e-Commerce site</span></span> 

<span data-ttu-id="40ab7-146">Se um recurso ou módulo de site de comércio eletrônico usar um cookie não essencial, o consentimento do usuário do site deverá ser obtido antes que o cookie seja rastreado.</span><span class="sxs-lookup"><span data-stu-id="40ab7-146">If an e-Commerce site feature or module uses a non-essential cookie, a site user's consent must be obtained before the cookie is tracked.</span></span> <span data-ttu-id="40ab7-147">Para permitir que os usuários do site forneçam consentimento de cookie no site de comércio eletrônico, um autor do site deve adicionar e configurar um módulo de consentimento de cookie no módulo de cabeçalho da página para garantir que o consentimento seja solicitado e recebido.</span><span class="sxs-lookup"><span data-stu-id="40ab7-147">To allow site users to provide cookie consent on the e-Commerce site, a site author must add and configure a cookie consent module in the page's header module to ensure that the consent is prompted for and received.</span></span> <span data-ttu-id="40ab7-148">O consentimento do usuário do site deve ser fornecido antes que um recurso ou módulo que use um cookie não essencial possa ser renderizado em uma página do site.</span><span class="sxs-lookup"><span data-stu-id="40ab7-148">Site user consent must be given before a feature or module using a non-essential cookie can be rendered on a site page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="40ab7-149">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="40ab7-149">Additional resources</span></span>

[<span data-ttu-id="40ab7-150">Recursos e funcionalidades de acessibilidade</span><span class="sxs-lookup"><span data-stu-id="40ab7-150">Accessibility features and capabilities</span></span>](accessibility.md)

[<span data-ttu-id="40ab7-151">Visão geral de conformidade</span><span class="sxs-lookup"><span data-stu-id="40ab7-151">Compliance overview</span></span>](compliance-overview.md)

[<span data-ttu-id="40ab7-152">Adicionar página de política de privacidade</span><span class="sxs-lookup"><span data-stu-id="40ab7-152">Add a privacy policy page</span></span>](add-privacy-page.md)

[<span data-ttu-id="40ab7-153">Substituir IDs de usuário associadas a alterações de conteúdo acompanhados</span><span class="sxs-lookup"><span data-stu-id="40ab7-153">Replace user IDs associated with tracked content changes</span></span>](replace-IDs-tracked-changes.md)

[<span data-ttu-id="40ab7-154">Módulo de consentimento de cookie</span><span class="sxs-lookup"><span data-stu-id="40ab7-154">Cookie consent module</span></span>](cookie-consent-module.md) 
 
[<span data-ttu-id="40ab7-155">Módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="40ab7-155">Header module</span></span>](author-header-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

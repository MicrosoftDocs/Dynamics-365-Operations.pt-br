---
title: Compatível com cookies
description: Este tópico descreve considerações sobre conformidade de cookies e as diretivas padrão incluídas no Microsoft Dynamics 365 Commerce.
author: BrianShook
manager: annbe
ms.date: 06/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e1fa016dc9f46b048220f0f83e4b0783087de91e
ms.sourcegitcommit: c66c4c67a21e7d7d3a94a3fd766c3184b6e65c4e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/12/2020
ms.locfileid: "3446904"
---
# <a name="cookie-compliance"></a><span data-ttu-id="d8376-103">Compatível com cookies</span><span class="sxs-lookup"><span data-stu-id="d8376-103">Cookie compliance</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d8376-104">Este tópico descreve considerações sobre conformidade de cookies e as diretivas padrão incluídas no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d8376-104">This topic describes considerations for cookie compliance and the default policies that are included in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="d8376-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="d8376-105">Overview</span></span>

<span data-ttu-id="d8376-106">A privacidade é um fator importante ao rastrear tecnologias que afetem clientes de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="d8376-106">Privacy is an important factor when tracking technologies that affect e-Commerce customers.</span></span> <span data-ttu-id="d8376-107">Por causa dos padrões de conformidade de privacidade, como a norma de proteção de dados gerais (GDPR) na União Europeia (UE), as diretrizes de privacidade eletrônica devem ser consideradas para qualquer site ativo hoje.</span><span class="sxs-lookup"><span data-stu-id="d8376-107">Because of privacy compliance standards such as the General Data Protection Regulation (GDPR) in the European Union (EU), electronic privacy guidelines must be considered for any site that is active today.</span></span> <span data-ttu-id="d8376-108">Como muitos sites de comércio eletrônico são globalmente acessíveis por padrão, é importante que você revise os padrões de conformidade para seu site de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="d8376-108">Because many e-Commerce sites are globally accessible by default, it's important that you review the compliance standards for your e-Commerce site.</span></span>

<span data-ttu-id="d8376-109">Para saber mais sobre os princípios básicos usados pela Microsoft para conformidade com cookies, visite o [Microsoft Trust Center](https://www.microsoft.com/trust-center).</span><span class="sxs-lookup"><span data-stu-id="d8376-109">To learn more about the basic principles that Microsoft uses for cookie compliance, visit the [Microsoft Trust Center](https://www.microsoft.com/trust-center).</span></span> <span data-ttu-id="d8376-110">Nesse site, você também pode obter mais informações sobre áreas de conformidade e privacidade.</span><span class="sxs-lookup"><span data-stu-id="d8376-110">On that site, you can also get more information about areas of compliance and privacy.</span></span>

<span data-ttu-id="d8376-111">A tabela a seguir mostra a lista de referência atual de cookies colocados por sites do Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d8376-111">The following table shows the current reference list of cookies placed by Dynamics 365 Commerce sites.</span></span>

| <span data-ttu-id="d8376-112">Nome do cookie</span><span class="sxs-lookup"><span data-stu-id="d8376-112">Cookie name</span></span>                               | <span data-ttu-id="d8376-113">Uso</span><span class="sxs-lookup"><span data-stu-id="d8376-113">Usage</span></span>                                                        |
| ------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="d8376-114">.AspNet.Cookies</span><span class="sxs-lookup"><span data-stu-id="d8376-114">.AspNet.Cookies</span></span>                             | <span data-ttu-id="d8376-115">Armazene cookies de autenticação do Microsoft Azure Active Directory (Azure AD) para logon único (SSO).</span><span class="sxs-lookup"><span data-stu-id="d8376-115">Store Microsoft Azure Active Directory (Azure AD) authentication cookies for single sign-on (SSO).</span></span> <span data-ttu-id="d8376-116">Armazena informações de entidade de segurança do usuário criptografadas (nome, sobrenome, email).</span><span class="sxs-lookup"><span data-stu-id="d8376-116">Stores encrypted user principal information (name, surname, email).</span></span> |
| <span data-ttu-id="d8376-117">&#95;msdyn365___cart&#95;</span><span class="sxs-lookup"><span data-stu-id="d8376-117">&#95;msdyn365___cart&#95;</span></span>                           | <span data-ttu-id="d8376-118">ID do carrinho da loja para obter a lista de produtos adicionada à instância do carrinho.</span><span class="sxs-lookup"><span data-stu-id="d8376-118">Store cart ID used to obtain list of products added to cart instance.</span></span> |
| <span data-ttu-id="d8376-119">&#95;msdyn365___ucc&#95;</span><span class="sxs-lookup"><span data-stu-id="d8376-119">&#95;msdyn365___ucc&#95;</span></span>                            | <span data-ttu-id="d8376-120">Rastreamento de consentimento de conformidade com cookies.</span><span class="sxs-lookup"><span data-stu-id="d8376-120">Cookie compliance consent tracking.</span></span>                          |
| <span data-ttu-id="d8376-121">ai_session</span><span class="sxs-lookup"><span data-stu-id="d8376-121">ai_session</span></span>                                  | <span data-ttu-id="d8376-122">Detecta quantas sessões de atividade do usuário incluíram determinadas páginas e recursos do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="d8376-122">Detects how many sessions of user activity have included certain pages and features of the app.</span></span> |
| <span data-ttu-id="d8376-123">ai_user</span><span class="sxs-lookup"><span data-stu-id="d8376-123">ai_user</span></span>                                     | <span data-ttu-id="d8376-124">Detecta quantas pessoas usaram o aplicativo e seus recursos.</span><span class="sxs-lookup"><span data-stu-id="d8376-124">Detects how many people used the app and its features.</span></span> <span data-ttu-id="d8376-125">Os usuários são contados usando IDs anônimas.</span><span class="sxs-lookup"><span data-stu-id="d8376-125">Users are counted using anonymous IDs.</span></span> |
| <span data-ttu-id="d8376-126">b2cru</span><span class="sxs-lookup"><span data-stu-id="d8376-126">b2cru</span></span>                                       | <span data-ttu-id="d8376-127">Armazena a URL de redirecionamento de forma dinâmica.</span><span class="sxs-lookup"><span data-stu-id="d8376-127">Stores redirect URL dynamically.</span></span>                              |
| <span data-ttu-id="d8376-128">JSESSIONID</span><span class="sxs-lookup"><span data-stu-id="d8376-128">JSESSIONID</span></span>                                  | <span data-ttu-id="d8376-129">Usado pelo conector de pagamento Adyen para armazenar a sessão do usuário.</span><span class="sxs-lookup"><span data-stu-id="d8376-129">Used by payment connector Adyen to store user session.</span></span>       |
| <span data-ttu-id="d8376-130">OpenIdConnect.nonce.&#42;</span><span class="sxs-lookup"><span data-stu-id="d8376-130">OpenIdConnect.nonce.&#42;</span></span>                       | <span data-ttu-id="d8376-131">Autenticação</span><span class="sxs-lookup"><span data-stu-id="d8376-131">Authentication</span></span>                                               |
| <span data-ttu-id="d8376-132">x-ms-cpim-cache:.&#42;</span><span class="sxs-lookup"><span data-stu-id="d8376-132">x-ms-cpim-cache:.&#42;</span></span>                          | <span data-ttu-id="d8376-133">Usado para manter o estado da solicitação.</span><span class="sxs-lookup"><span data-stu-id="d8376-133">Used for maintaining the request state.</span></span>                      |
| <span data-ttu-id="d8376-134">x-ms-cpim-csrf</span><span class="sxs-lookup"><span data-stu-id="d8376-134">x-ms-cpim-csrf</span></span>                              | <span data-ttu-id="d8376-135">Token de solicitação intersite forjada (CRSF) usado para proteção contra CRSF.</span><span class="sxs-lookup"><span data-stu-id="d8376-135">Cross-site request forgery (CRSF) token used for protection from CRSF.</span></span>     |
| <span data-ttu-id="d8376-136">x-ms-cpim-dc</span><span class="sxs-lookup"><span data-stu-id="d8376-136">x-ms-cpim-dc</span></span>                                | <span data-ttu-id="d8376-137">Usado para rotear solicitações para a instância apropriada do servidor de autenticação de produção.</span><span class="sxs-lookup"><span data-stu-id="d8376-137">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="d8376-138">x-ms-cpim-rc.&#42;</span><span class="sxs-lookup"><span data-stu-id="d8376-138">x-ms-cpim-rc.&#42;</span></span>                              | <span data-ttu-id="d8376-139">Usado para rotear solicitações para a instância apropriada do servidor de autenticação de produção.</span><span class="sxs-lookup"><span data-stu-id="d8376-139">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="d8376-140">x-ms-cpim-slice</span><span class="sxs-lookup"><span data-stu-id="d8376-140">x-ms-cpim-slice</span></span>                             | <span data-ttu-id="d8376-141">Usado para rotear solicitações para a instância apropriada do servidor de autenticação de produção.</span><span class="sxs-lookup"><span data-stu-id="d8376-141">Used to route requests to the appropriate production authentication server instance.</span></span> |
| <span data-ttu-id="d8376-142">x-ms-cpim-sso:rushmoreb2c.onmicrosoft.com_0</span><span class="sxs-lookup"><span data-stu-id="d8376-142">x-ms-cpim-sso:rushmoreb2c.onmicrosoft.com_0</span></span> | <span data-ttu-id="d8376-143">Usado para manter a sessão SSO.</span><span class="sxs-lookup"><span data-stu-id="d8376-143">Used for maintaining the SSO session.</span></span>                        |
| <span data-ttu-id="d8376-144">x-ms-cpim-trans</span><span class="sxs-lookup"><span data-stu-id="d8376-144">x-ms-cpim-trans</span></span>                             | <span data-ttu-id="d8376-145">Usado para rastrear transações (o número de guias abertas na autenticação de um site business-to-consumer (B2C)), incluindo a transação atual.</span><span class="sxs-lookup"><span data-stu-id="d8376-145">Used for tracking transactions (the number of open tabs authenticating against a business-to-consumer (B2C) site), including the current transaction.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="d8376-146">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="d8376-146">Additional resources</span></span>

[<span data-ttu-id="d8376-147">Recursos e funcionalidades de acessibilidade</span><span class="sxs-lookup"><span data-stu-id="d8376-147">Accessibility features and capabilities</span></span>](accessibility.md)

[<span data-ttu-id="d8376-148">Visão geral de conformidade</span><span class="sxs-lookup"><span data-stu-id="d8376-148">Compliance overview</span></span>](compliance-overview.md)

[<span data-ttu-id="d8376-149">Adicionar página de política de privacidade</span><span class="sxs-lookup"><span data-stu-id="d8376-149">Add a privacy policy page</span></span>](add-privacy-page.md)

[<span data-ttu-id="d8376-150">Substitua os IDs de usuário associados às alterações de conteúdo controladas</span><span class="sxs-lookup"><span data-stu-id="d8376-150">Replace user IDs associated with tracked content changes</span></span>](replace-IDs-tracked-changes.md)

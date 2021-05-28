---
title: O link de entrada redireciona novamente para um site de comércio eletrônico
description: Este tópico fornece orientações de solução de problemas que podem ajudar quando um link de entrada redireciona novamente para o site de comércio eletrônico, em vez de ir para a página de entrada.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: a1d0ae4e487c391020947c607d5d7cb5d1ba6af4
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020594"
---
# <a name="sign-in-link-redirects-back-to-an-e-commerce-site"></a><span data-ttu-id="6ff6f-103">O link de entrada redireciona novamente para um site de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="6ff6f-103">Sign-in link redirects back to an e-commerce site</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6ff6f-104">Este tópico fornece orientações de solução de problemas que podem ajudar quando um link de entrada redireciona novamente para o site de comércio eletrônico, em vez de ir para a página de entrada.</span><span class="sxs-lookup"><span data-stu-id="6ff6f-104">This topic provides troubleshooting guidance that can help when a sign-in link redirects back to the e-commerce site instead of going to the sign-in page.</span></span>

## <a name="description"></a><span data-ttu-id="6ff6f-105">descrição</span><span class="sxs-lookup"><span data-stu-id="6ff6f-105">Description</span></span>

<span data-ttu-id="6ff6f-106">Depois de configurar um novo locatário de B2C do Microsoft Azure Active Directory (Microsoft B2C Azure AD) no construtor de sites do Commerce, os usuários que selecionam o link **Entrar** são redirecionados para a página inicial de comércio eletrônico principal sem ir para a página de entrada.</span><span class="sxs-lookup"><span data-stu-id="6ff6f-106">After you configure a new Microsoft Azure Active Directory B2C (Azure AD B2C) tenant in Commerce site builder, users who select the **Sign in** link are redirected back to the main e-commerce landing page without going to the sign-in page.</span></span>

## <a name="resolution"></a><span data-ttu-id="6ff6f-107">Resolução</span><span class="sxs-lookup"><span data-stu-id="6ff6f-107">Resolution</span></span>

### <a name="confirm-that-the-reply-url-is-correctly-configured-in-the-azure-ad-b2c-application"></a><span data-ttu-id="6ff6f-108">Confirmar se a URL de resposta está configurada corretamente no aplicativo Azure AD B2C</span><span class="sxs-lookup"><span data-stu-id="6ff6f-108">Confirm that the reply URL is correctly configured in the Azure AD B2C application</span></span>

<span data-ttu-id="6ff6f-109">Para confirmar se a URL de resposta está configurada corretamente no aplicativo Azure AD B2C, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="6ff6f-109">To confirm that the reply URL is correctly configured in the Azure AD B2C application, follow these steps.</span></span>

1. <span data-ttu-id="6ff6f-110">Vá para o [portal do Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="6ff6f-110">Go to the [Azure portal](https://portal.azure.com/).</span></span>
1. <span data-ttu-id="6ff6f-111">Selecione o aplicativo Azure AD B2C criado para acesso ao site.</span><span class="sxs-lookup"><span data-stu-id="6ff6f-111">Select the Azure AD B2C application that you created for your site access.</span></span>
1. <span data-ttu-id="6ff6f-112">Selecione o aplicativo criado durante a configuração do Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="6ff6f-112">Select the application that you created during the Azure AD B2C setup.</span></span>
1. <span data-ttu-id="6ff6f-113">Em **URL de Resposta**, certifique-se de que a lista inclui entradas para a URL do domínio do site e para a URL gerada pelo comércio eletrônico, conforme mostrado no exemplo da ilustração a seguir.</span><span class="sxs-lookup"><span data-stu-id="6ff6f-113">Under **Reply URL**, make sure that the list includes entries for both the site domain URL and the e-commerce-generated URL, as shown in the example in the following illustration.</span></span>

    ![Entradas da URL de resposta do Azure AD B2C](media/aad-b2c-reply-url.jpg)

> [!NOTE]
> <span data-ttu-id="6ff6f-115">A URL de domínio do site e a URL gerada por comércio eletrônico devem estar em um formato de URL válido que não inclua barras à esquerda ou à direita.</span><span class="sxs-lookup"><span data-stu-id="6ff6f-115">Both the site domain URL and the e-commerce-generated URL must be in a valid URL format that doesn't include leading or trailing slashes.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6ff6f-116">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="6ff6f-116">Additional resources</span></span>

[<span data-ttu-id="6ff6f-117">Registrar um aplicativo Web no Azure Active Directory B2C</span><span class="sxs-lookup"><span data-stu-id="6ff6f-117">Register a web application in Azure Active Directory B2C</span></span>](/azure/active-directory-b2c/tutorial-register-applications?tabs=app-reg-ga#register-a-web-application)

[<span data-ttu-id="6ff6f-118">Configurar um locatário de B2C no Commerce</span><span class="sxs-lookup"><span data-stu-id="6ff6f-118">Set up a B2C tenant in Commerce</span></span>](../set-up-b2c-tenant.md)
---
title: Restringir o acesso a uma vitrine durante o teste ou o desenvolvimento
description: Este tópico explica como restringir o acesso a uma vitrine do Microsoft Dynamics 365 Commerce enquanto ocorre o teste ou o desenvolvimento interno.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
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
ms.openlocfilehash: f5cba6b7ff3aa65441c932e72fa458bda0d0fc69
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801522"
---
# <a name="restrict-access-to-a-storefront-during-testing-or-development"></a><span data-ttu-id="e7085-103">Restringir o acesso a uma vitrine durante o teste ou o desenvolvimento</span><span class="sxs-lookup"><span data-stu-id="e7085-103">Restrict access to a storefront during testing or development</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e7085-104">Este tópico explica como restringir o acesso a uma vitrine do Microsoft Dynamics 365 Commerce enquanto ocorre o teste ou o desenvolvimento interno.</span><span class="sxs-lookup"><span data-stu-id="e7085-104">This topic explains how to restrict access to a Microsoft Dynamics 365 Commerce storefront while internal testing or development is occurring.</span></span>

## <a name="description"></a><span data-ttu-id="e7085-105">descrição</span><span class="sxs-lookup"><span data-stu-id="e7085-105">Description</span></span>

<span data-ttu-id="e7085-106">Durante o teste interno ou o desenvolvimento ativo, talvez você queira restringir o acesso ao seu site para impedir que usuários externos acessem as páginas da vitrine.</span><span class="sxs-lookup"><span data-stu-id="e7085-106">During internal testing or active development, you might want to restrict access to your site to prevent external users from accessing the published storefront pages.</span></span>

## <a name="resolution"></a><span data-ttu-id="e7085-107">Resolução</span><span class="sxs-lookup"><span data-stu-id="e7085-107">Resolution</span></span>

### <a name="set-up-azure-ad-b2c-by-using-standard-user-flows"></a><span data-ttu-id="e7085-108">Configurar o Azure AD B2C usando fluxos de usuário padrão</span><span class="sxs-lookup"><span data-stu-id="e7085-108">Set up Azure AD B2C by using standard user flows</span></span>

<span data-ttu-id="e7085-109">Para obter informações sobre como configurar o Azure Active Directory B2C (Azure AD B2C) para seu site de comércio eletrônico, consulte [Configurar um locatário de B2C no Commerce](../set-up-b2c-tenant.md).</span><span class="sxs-lookup"><span data-stu-id="e7085-109">For information about how to configure Azure Active Directory B2C (Azure AD B2C) for your e-commerce site, see [Set up a B2C tenant in Commerce](../set-up-b2c-tenant.md).</span></span>

### <a name="restrict-user-access-to-storefront-pages-and-block-the-creation-of-new-users"></a><span data-ttu-id="e7085-110">Restringir o acesso de usuários a páginas de vitrine e bloquear a criação de novos usuários</span><span class="sxs-lookup"><span data-stu-id="e7085-110">Restrict user access to storefront pages and block the creation of new users</span></span>

<span data-ttu-id="e7085-111">Para restringir o acesso de usuários a páginas da vitrine do criador de sites do eCommerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="e7085-111">To restrict user access to storefront pages in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="e7085-112">Vá para seu site.</span><span class="sxs-lookup"><span data-stu-id="e7085-112">Go to your site.</span></span>
1. <span data-ttu-id="e7085-113">Selecione **Página** e, em seguida, selecione a página para restringir o acesso de usuários.</span><span class="sxs-lookup"><span data-stu-id="e7085-113">Select **Pages**, and then select the page to restrict user access for.</span></span>
1. <span data-ttu-id="e7085-114">Selecione o módulo ou o slot do fragmento e, em seguida, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e7085-114">Select the module or fragment slot, and then select **Edit**.</span></span>
1. <span data-ttu-id="e7085-115">No painel Propriedades, selecione **Requer entrada?** e, em seguida, selecione **Concluir edição**.</span><span class="sxs-lookup"><span data-stu-id="e7085-115">In the properties pane, select **Requires sign-in?**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="e7085-116">Selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="e7085-116">Select **Publish**.</span></span>

<span data-ttu-id="e7085-117">Para bloquear a criação de novos usuários no Azure AD, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="e7085-117">To block the creation of new users in Azure AD, follow these steps.</span></span>

1. <span data-ttu-id="e7085-118">Vá para o [portal do Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="e7085-118">Go to the [Azure portal](https://portal.azure.com/).</span></span>
1. <span data-ttu-id="e7085-119">Selecione o aplicativo Azure AD B2C criado para acesso ao site.</span><span class="sxs-lookup"><span data-stu-id="e7085-119">Select the Azure AD B2C application that you created for your site access.</span></span>
1. <span data-ttu-id="e7085-120">No painel de navegação à esquerda, selecione **Fluxos do usuário**.</span><span class="sxs-lookup"><span data-stu-id="e7085-120">In the left navigation, select **User flows**.</span></span>
1. <span data-ttu-id="e7085-121">Na parte superior da página **Fluxos de Usuário**, selecione **Novo fluxo do usuário**.</span><span class="sxs-lookup"><span data-stu-id="e7085-121">At the top of the **User Flows** page, select **New user flow**.</span></span>
1. <span data-ttu-id="e7085-122">Na página **Selecionar um tipo de fluxo de usuário**, selecione **Visualizar**.</span><span class="sxs-lookup"><span data-stu-id="e7085-122">On the **Select a user flow type** page, select **Preview**.</span></span>
1. <span data-ttu-id="e7085-123">No meio da página, selecione **Entrar no v2**.</span><span class="sxs-lookup"><span data-stu-id="e7085-123">In the middle of the page, select **Sign in v2**.</span></span> <span data-ttu-id="e7085-124">Em seguida, siga as etapas em [Configurar um locatário de B2C no Commerce](../set-up-b2c-tenant.md) para configurar o fluxo como o fluxo de usuário padrão do site para Azure AD B2C durante o teste ou o desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="e7085-124">Then follow the steps in [Set up a B2C tenant in Commerce](../set-up-b2c-tenant.md) to configure the flow as your site's standard user flow for Azure AD B2C during testing or development.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e7085-125">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="e7085-125">Additional resources</span></span>

[<span data-ttu-id="e7085-126">Configurar um locatário de B2C no Commerce</span><span class="sxs-lookup"><span data-stu-id="e7085-126">Set up a B2C tenant in Commerce</span></span>](../set-up-b2c-tenant.md)

[<span data-ttu-id="e7085-127">Configurar páginas personalizadas para entradas dos usuários</span><span class="sxs-lookup"><span data-stu-id="e7085-127">Set up custom pages for user sign-ins</span></span>](../custom-pages-user-logins.md)

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
# <a name="restrict-access-to-a-storefront-during-testing-or-development"></a>Restringir o acesso a uma vitrine durante o teste ou o desenvolvimento

[!include [banner](../../includes/banner.md)]

Este tópico explica como restringir o acesso a uma vitrine do Microsoft Dynamics 365 Commerce enquanto ocorre o teste ou o desenvolvimento interno.

## <a name="description"></a>descrição

Durante o teste interno ou o desenvolvimento ativo, talvez você queira restringir o acesso ao seu site para impedir que usuários externos acessem as páginas da vitrine.

## <a name="resolution"></a>Resolução

### <a name="set-up-azure-ad-b2c-by-using-standard-user-flows"></a>Configurar o Azure AD B2C usando fluxos de usuário padrão

Para obter informações sobre como configurar o Azure Active Directory B2C (Azure AD B2C) para seu site de comércio eletrônico, consulte [Configurar um locatário de B2C no Commerce](../set-up-b2c-tenant.md).

### <a name="restrict-user-access-to-storefront-pages-and-block-the-creation-of-new-users"></a>Restringir o acesso de usuários a páginas de vitrine e bloquear a criação de novos usuários

Para restringir o acesso de usuários a páginas da vitrine do criador de sites do eCommerce, siga estas etapas.

1. Vá para seu site.
1. Selecione **Página** e, em seguida, selecione a página para restringir o acesso de usuários.
1. Selecione o módulo ou o slot do fragmento e, em seguida, clique em **Editar**.
1. No painel Propriedades, selecione **Requer entrada?** e, em seguida, selecione **Concluir edição**.
1. Selecione **Publicar**.

Para bloquear a criação de novos usuários no Azure AD, siga estas etapas.

1. Vá para o [portal do Azure](https://portal.azure.com/).
1. Selecione o aplicativo Azure AD B2C criado para acesso ao site.
1. No painel de navegação à esquerda, selecione **Fluxos do usuário**.
1. Na parte superior da página **Fluxos de Usuário**, selecione **Novo fluxo do usuário**.
1. Na página **Selecionar um tipo de fluxo de usuário**, selecione **Visualizar**.
1. No meio da página, selecione **Entrar no v2**. Em seguida, siga as etapas em [Configurar um locatário de B2C no Commerce](../set-up-b2c-tenant.md) para configurar o fluxo como o fluxo de usuário padrão do site para Azure AD B2C durante o teste ou o desenvolvimento.

## <a name="additional-resources"></a>Recursos adicionais

[Configurar um locatário de B2C no Commerce](../set-up-b2c-tenant.md)

[Configurar páginas personalizadas para entradas dos usuários](../custom-pages-user-logins.md)

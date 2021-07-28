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
ms.openlocfilehash: e83b381e73d28dce0a438a37d5f8ed23b4957adf
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6350369"
---
# <a name="sign-in-link-redirects-back-to-an-e-commerce-site"></a>O link de entrada redireciona novamente para um site de comércio eletrônico

[!include [banner](../../includes/banner.md)]

Este tópico fornece orientações de solução de problemas que podem ajudar quando um link de entrada redireciona novamente para o site de comércio eletrônico, em vez de ir para a página de entrada.

## <a name="description"></a>descrição

Depois de configurar um novo locatário de B2C do Microsoft Azure Active Directory (Microsoft B2C Azure AD) no construtor de sites do Commerce, os usuários que selecionam o link **Entrar** são redirecionados para a página inicial de comércio eletrônico principal sem ir para a página de entrada.

## <a name="resolution"></a>Resolução

### <a name="confirm-that-the-reply-url-is-correctly-configured-in-the-azure-ad-b2c-application"></a>Confirmar se a URL de resposta está configurada corretamente no aplicativo Azure AD B2C

Para confirmar se a URL de resposta está configurada corretamente no aplicativo Azure AD B2C, siga estas etapas.

1. Vá para o [portal do Azure](https://portal.azure.com/).
1. Selecione o aplicativo Azure AD B2C criado para acesso ao site.
1. Selecione o aplicativo criado durante a configuração do Azure AD B2C.
1. Em **URL de Resposta**, certifique-se de que a lista inclui entradas para a URL do domínio do site e para a URL gerada pelo comércio eletrônico, conforme mostrado no exemplo da ilustração a seguir.

    ![Entradas da URL de resposta do Azure AD B2C.](media/aad-b2c-reply-url.jpg)

> [!NOTE]
> A URL de domínio do site e a URL gerada por comércio eletrônico devem estar em um formato de URL válido que não inclua barras à esquerda ou à direita.

## <a name="additional-resources"></a>Recursos adicionais

[Registrar um aplicativo Web no Azure Active Directory B2C](/azure/active-directory-b2c/tutorial-register-applications?tabs=app-reg-ga#register-a-web-application)

[Configurar um locatário de B2C no Commerce](../set-up-b2c-tenant.md)
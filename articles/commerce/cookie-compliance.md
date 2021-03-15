---
title: Compatível com cookies
description: Este tópico descreve considerações sobre conformidade de cookies e as diretivas padrão incluídas no Microsoft Dynamics 365 Commerce.
author: BrianShook
manager: annbe
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 95c5801e69396b21a36c4ae12ce17801e6f7fd88
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993491"
---
# <a name="cookie-compliance"></a>Compatível com cookies

[!include [banner](includes/banner.md)]

Este tópico descreve considerações sobre conformidade de cookies e as diretivas padrão incluídas no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão Geral

A privacidade é um fator importante ao rastrear tecnologias que afetem clientes de comércio eletrônico. Por causa dos padrões de conformidade de privacidade, como a norma de proteção de dados gerais (GDPR) na União Europeia (UE), as diretrizes de privacidade eletrônica devem ser consideradas para qualquer site ativo hoje. Como muitos sites de comércio eletrônico são globalmente acessíveis por padrão, é importante que você revise os padrões de conformidade para seu site de comércio eletrônico.

Para saber mais sobre os princípios básicos usados pela Microsoft para conformidade com cookies, visite o [Microsoft Trust Center](https://www.microsoft.com/trust-center). Nesse site, você também pode obter mais informações sobre áreas de conformidade e privacidade.

A tabela a seguir mostra a lista de referência atual de cookies colocados por sites do Dynamics 365 Commerce.

| Nome do cookie                               | Uso                                                        |
| ------------------------------------------- | ------------------------------------------------------------ |
| .AspNet.Cookies                             | Armazene cookies de autenticação do Microsoft Azure Active Directory (Azure AD) para logon único (SSO). Armazena informações de entidade de segurança do usuário criptografadas (nome, sobrenome, email). |
| &#95;msdyn365___cart&#95;                           | ID do carrinho da loja para obter a lista de produtos adicionada à instância do carrinho. |
| &#95;msdyn365___ucc&#95;                            | Rastreamento de consentimento de conformidade com cookies.                          |
| ai_session                                  | Detecta quantas sessões de atividade do usuário incluíram determinadas páginas e recursos do aplicativo. |
| ai_user                                     | Detecta quantas pessoas usaram o aplicativo e seus recursos. Os usuários são contados usando IDs anônimas. |
| b2cru                                       | Armazena a URL de redirecionamento de forma dinâmica.                              |
| JSESSIONID                                  | Usado pelo conector de pagamento Adyen para armazenar a sessão do usuário.       |
| OpenIdConnect.nonce.&#42;                       | Autenticação                                               |
| x-ms-cpim-cache:.&#42;                          | Usado para manter o estado da solicitação.                      |
| x-ms-cpim-csrf                              | Token de solicitação intersite forjada (CRSF) usado para proteção contra CRSF.     |
| x-ms-cpim-dc                                | Usado para rotear solicitações para a instância apropriada do servidor de autenticação de produção. |
| x-ms-cpim-rc.&#42;                              | Usado para rotear solicitações para a instância apropriada do servidor de autenticação de produção. |
| x-ms-cpim-slice                             | Usado para rotear solicitações para a instância apropriada do servidor de autenticação de produção. |
| x-ms-cpim-sso:rushmoreb2c.onmicrosoft.com_0 | Usado para manter a sessão SSO.                        |
| x-ms-cpim-trans                             | Usado para rastrear transações (o número de guias abertas na autenticação de um site business-to-consumer (B2C)), incluindo a transação atual. |

## <a name="site-user-cookie-consent-on-an-e-commerce-site"></a>Consentimento de cookie de usuário de site em um site de comércio eletrônico 

Se um recurso ou módulo de site de comércio eletrônico usar um cookie não essencial, o consentimento do usuário do site deverá ser obtido antes que o cookie seja rastreado. Para permitir que os usuários do site forneçam consentimento de cookie no site de comércio eletrônico, um autor do site deve adicionar e configurar um módulo de consentimento de cookie no módulo de cabeçalho da página para garantir que o consentimento seja solicitado e recebido. O consentimento do usuário do site deve ser fornecido antes que um recurso ou módulo que use um cookie não essencial possa ser renderizado em uma página do site.

## <a name="additional-resources"></a>Recursos adicionais

[Recursos e funcionalidades de acessibilidade](accessibility.md)

[Visão geral de conformidade](compliance-overview.md)

[Adicionar página de política de privacidade](add-privacy-page.md)

[Substituir IDs de usuário associadas a alterações de conteúdo acompanhados](replace-IDs-tracked-changes.md)

[Módulo de consentimento de cookie](cookie-consent-module.md) 
 
[Módulo de cabeçalho](author-header-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
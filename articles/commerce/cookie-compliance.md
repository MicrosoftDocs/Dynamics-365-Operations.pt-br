---
title: Compatível com cookies
description: Este tópico descreve considerações sobre conformidade de cookies e as políticas padrão incluídas no Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 05/21/2021
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
ms.openlocfilehash: 8eb610eb819dee09a30368257e36dc88f855e985
ms.sourcegitcommit: 8c5b3e872825953853ad57fc67ba6e5ae92b9afe
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "6088378"
---
# <a name="cookie-compliance"></a>Compatível com cookies

[!include [banner](includes/banner.md)]

Este tópico descreve considerações sobre conformidade de cookies e as políticas padrão incluídas no Microsoft Dynamics 365 Commerce.

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
| \_msdyn365___muid_                            | Usado se a Experimentação estiver ativada para o ambiente, utilizado como userId para fins de experimentação. |
| \_msdyn365___exp_                             | Usado se a Experimentação estiver ativada para o ambiente; usado para medir o balanceamento de carga de desempenho.         |
| d365mkt                                       | Usado se a detecção baseada em local para rastrear o endereço IP de um usuário para sugestões de localização de armazenamento estiver habilitada no construtor de sites comerciais em **Configurações do Site > Geral > Habilitar detecção de lojas com base na localização**.      |

Se um usuário do site selecionar qualquer link de mídia social em um site, os cookies na seguinte tabela também serão rastreados no navegador.


| Domínio                      | Cookie               | descrição                                                  | Origem                                          |
| --------------------------- | ------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| .linkedin.com                | UserMatchHistory         | Sincronização de ID de Anúncios do LinkedIn                                      | Tag do Feed e Insight do LinkedIn                                |
| .linkedin.com               | li_sugr                  | Identificador do navegador                                           | Tag de Insight do LinkedIn se o endereço IP não estiver em um país designado |
| .linkedin.com               | BizographicsOptOut       | Determina o status de recusa do acompanhamento de terceiros.              | Controles de convidados do LinkedIn e páginas de recusa do setor           |
| .linkedin.com               | \_guid                    | Identificador do navegador do Google Ads.                            | Feed do LinkedIn                                                |
| .linkedin.com               | li_oatml                 | Identificador indireto do membro para acompanhamento de conversões, redirecionamento e análise. | Tags de Anúncios e Insight do LinkedIn                                |
| Vários domínios primários | li_fat_id                | Identificador indireto do membro para acompanhamento de conversões, redirecionamento e análise. | Tags de Anúncios e Insight do LinkedIn                                |
| .adsymptotic.com            | U                        | Identificador do navegador                                           | Tag de Insight do LinkedIn se o endereço IP não estiver em um País Designado |
| .linkedin.com                | bcookie                  | Cookie da ID do navegador                                            | Solicitações para o LinkedIn                                         |
| .linkedin.com                | bscookie                 | Cookie de navegador seguro                                        | Solicitações para o LinkedIn                                         |
| .linkedin.com               | lang                     | Define a localização e o idioma padrão.                                 | Solicitações para o LinkedIn                                         |
| .linkedin.com                | lidc                     | Usado para roteamento.                                             | Solicitações para o LinkedIn                                         |
| .linkedin.com               | aam_uuid                 | Cookie do gerenciador de público-alvo da Adobe                                                     | Definir para sincronização de ID                                              |
| .linkedin.com               | \_ga                      | Cookie do Google Analytics                                            | Google Analytics                                             |
| .linkedin.com               | \_gat                     | Cookie do Google Analytics                                             | Google Analytics                                             |
| .linkedin.com               | liap                     | Cookie do Google Analytics                                             | Google Analytics                                             |
| .linkedin.com               | lissc                    |                                                              |                                                              |
| .facebook.com               | c_user                   | O cookie contém a ID de usuário do usuário conectado no momento.  |   Facebook                                                           |
| .facebook.com               | datr                     | Usado para identificar o navegador da Web usado para se conectar ao Facebook independentemente do usuário conectado. | Facebook                                                             |
| .facebook.com               | wd                       | Armazena as dimensões da janela do navegador e é usado pelo Facebook para otimizar a renderização da página. | Facebook                                                             |
| .facebook.com               | xs                       | Número de dois dígitos que representa o número da sessão. A segunda parte do valor é um segredo da sessão. |  Facebook                                                            |
| .facebook.com               | fr                       | Contém um navegador e uma ID de usuário exclusivos, usados para publicidade direcionada. |  Facebook                                                            |
| .facebook.com               | sb                       | Usado para aprimorar as sugestões de amigos do Facebook.                                |  Facebook                                                            |
| .facebook.com               | spin                     |                                                              |  Facebook                                                            |
| .twitter.com                | guest_id                 |                                                              |  Twitter                                                            |
| .twitter.com                | kdt                      |                                                              |  Twitter                                                             |
| .twitter.com                | personalization_id       | O cookie contém a ID de usuário do usuário conectado no momento.  |  Twitter                                                             |
| .twitter.com                | remember_checked_on      |                                                              | Twitter                                                              |
| .twitter.com                | twid                     |                                                              |  Twitter                                                             |
| .pinterest.com              | \_auth                    | O cookie contém a ID de usuário do usuário conectado no momento.  |   Pinterest                                                           |
| .pinterest.com              | \_b                       |                                                              |   Pinterest                                                           |
| .pinterest.com              | \_pinterest_pfob          |                                                              |  Pinterest                                                            |
| .pinterest.com              | \_pinterest_referrer      | O cookie contém páginas quando o usuário seleciona o botão Pinterest.      |  Pinterest                                                            |
| .pinterest.com              | \_pinterest_sess          | O cookie contém páginas quando o usuário seleciona o botão Pinterest.      |  Pinterest                                                            |
| .pinterest.com              | \_routing_id              |                                                              |  Pinterest                                                            |
| .pinterest.com              | bei                      |                                                              |  Pinterest                                                            |
| .pinterest.com              | cm_sub                   | Contém uma ID de usuário e o carimbo de data/hora em que o cookie foi criado. |  Pinterest                                                            |
| .pinterest.com              | csrftoken                | O cookie contém páginas quando o usuário seleciona o botão Pinterest.      | Pinterest                                                             |
| .pinterest.com              | sessionFunnelEventLogged | O cookie contém páginas quando o usuário seleciona o botão Pinterest.      | Pinterest                                                             |
| .pinterest.com              | Armazenamento local            |                                                              |  Pinterest                                                            |
| .pinterest.com              | Trabalhadores de Serviço          |                                                              |  Pinterest                                                            |


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

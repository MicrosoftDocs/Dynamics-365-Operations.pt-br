---
title: Atualizar o Commerce headquarters com as novas informações do B2C do Azure AD
description: Este artigo descreve como atualizar o Microsoft Dynamics 365 Commerce headquarters com novas informações de empresa para consumidor (B2C) do Azure Active Directory (Azure AD).
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: c65949ff97182d2692319ac2af00e3ef35a79580
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785217"
---
# <a name="update-commerce-headquarters-with-the-new-azure-ad-b2c-information"></a>Atualizar o Commerce headquarters com as novas informações do B2C do Azure AD

[!include [banner](includes/banner.md)]

Este artigo descreve como atualizar o Microsoft Dynamics 365 Commerce headquarters com novas informações de empresa para consumidor (B2C) do Azure Active Directory (Azure AD).

Depois que as etapas de provisionamento do B2C do Azure AD estiverem concluídas, o aplicativo B2C do Azure AD devem ser registrados no ambiente do Dynamics 365 Commerce.

Para atualizar o headquarters com as novas informações do B2C do Azure AD, siga estas etapas.

1. No Commerce, Acesse **Parâmetros Compartilhados do Commerce** e selecione **Provedores de Identidade** no menu esquerdo.
1. Em **Provedores de Identidade**, faça o seguinte:
    1. Na caixa **Emissor**, insira a cadeia de caracteres do emissor do provedor de identidade. Para encontrar a cadeia de caracteres do seu emissor, consulte [Obter cadeia de caracteres do emissor para a configuração do headquarters](#obtain-issuer-string-for-headquarters-setup) abaixo.
    1. Na caixa **Nome**, insira um nome para o registro do emissor.
    1. Na caixa **Tipo**, insira **B2C do Azure AD (id_token)**.
1. Em **Partes Confiáveis**, com o item do provedor de identidade do B2C acima selecionado, faça o seguinte:
    1. Na caixa **ClientID**, insira o ID do aplicativo B2C, que pode ser encontrado na caixa **ID do aplicativo** da página de propriedades do aplicativo B2C.
    1. Na caixa **Tipo**, insira **Público**.
    1. Na caixa **Tipo de Usuário**, insira **Cliente**.
1. No painel de ação, selecione **Salvar**.
1. Na caixa de pesquisa do Commerce, procure **Agenda de distribuição**
1. No menu de navegação à esquerda da página **Agendas de distribuição**, selecione o trabalho **1110 Configuração global**.
1. No painel de ação, selecione **Executar Agora**.

### <a name="obtain-issuer-string-for-headquarters-setup"></a>Obter cadeia de caracteres do emissor para a configuração do headquarters

Para obter a cadeia de caracteres do emissor do provedor de identidade, siga estas etapas.

1. Na página do Azure AD B2C do portal do Azure, navegue até o fluxo de usuário **Inscrever-se e entrar**.
1. Selecione **Layouts de página** no menu de navegação esquerdo, em **Nome do layout**, selecione **Página de inscrição ou entrada unificada** e selecione **Executar fluxo do usuário**.
1. Certifique-se de que o aplicativo esteja definido para seu aplicativo pretendido do Azure AD B2C criado acima e selecione o link do fluxo do usuário exibido no cabeçalho **Executar fluxo do usuário**, que inclui ``.../.well-known/openid-configuration?p=<B2CSIGN-INPOLICY>``. (Não selecione **Executar fluxo de usuário**.) Uma nova guia será aberta com a exibição de metadados da política para coletar a cadeia de caracteres do emissor.
1. Na página metadados exibida na guia do seu navegador, copie a cadeia de caracteres do emissor do provedor de identidade (o valor do **emissor** que começa com "https://" e termina com "/v2.0/") que é semelhante ao exemplo a seguir.
   - ``https://login.fabrikam.com/011115c3-0113-4f43-b5e2-df01266e24ae/v2.0/``.
 
**OU**: para construir a mesma URL de metadados manualmente, execute as etapas a seguir.

1. Crie um URL do endereço de metadados no seguinte formato usando o locatário e a política B2C: ``https://<B2CTENANTNAME>.b2clogin.com/<B2CTENANTNAME>.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=<B2CSIGN-INPOLICY>``
    - Exemplo: ``https://d365plc.b2clogin.com/d365plc.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=B2C_1_signinup``.
1. Insira o URL do endereço de metadados na barra de endereço no navegador.
1. Nos metadados, copie o URL do emissor do provedor de identidade (valor para **"emissor"**).
    - Exemplo: ``https://login.fabrikam.com/011115c3-0113-4f43-b5e2-df01266e24ae/v2.0/``.

## <a name="next-steps"></a>Próximas etapas

Para continuar o processo de configuração de um locatário B2C no Commerce, prossiga para [Configurar seu locatário B2C no construtor de sites Commerce](config-b2c-tenant-site-builder.md).

## <a name="additional-resources"></a>Recursos adicionais

[Configurar um locatário B2C do Commerce](set-up-b2c-tenant.md)

[Criar ou vincular a um locatário existente do Azure AD B2C no portal do Azure](create-link-aad-b2c-tenant.md)

[Criar o aplicativo B2C](create-b2c-app.md)

[Criar políticas de fluxo de usuário](create-user-flow-policies.md)

[Adicionar provedores de identidade social (Opcional)](add-social-identity-providers.md)

[Configurar o locatário B2C no construtor de sites do Commerce](config-b2c-tenant-site-builder.md)

[Informações adicionais do B2C](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

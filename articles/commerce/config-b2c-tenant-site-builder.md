---
title: Configurar o locatário B2C no construtor de sites do Commerce
description: Este artigo descreve como configurar o locatário business-to-consumer (B2C) no criador de sites do Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: 181edf1570f1a9d071a7fae38ff9d73ff3c068fa
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785216"
---
# <a name="configure-your-b2c-tenant-in-commerce-site-builder"></a>Configurar o locatário B2C no construtor de sites do Commerce

[!include [banner](includes/banner.md)]

Este artigo descreve como configurar o locatário business-to-consumer (B2C) no criador de sites do Microsoft Dynamics 365 Commerce.

Após configurar o locatário B2C do Azure AD, será necessário configurar o locatário B2C no construtor de sites do Commerce. As etapas de configuração incluem coletar informações do aplicativo B2C do portal do Azure, inserir as informações do aplicativo B2C no construtor de sites e associar o aplicativo B2C ao site e ao canal.

### <a name="collect-the-required-application-information"></a>Coletar as informações necessárias do aplicativo

Para coletar as informações necessárias do aplicativo, siga estas etapas.

1. No portal do Azure, acesse **Página Inicial \> B2C do Azure AD – Registros de aplicativos**,
1. Selecione o aplicativo e, no painel de navegação à esquerda, selecione **Visão geral** para obter os detalhes do aplicativo.
1. Na referência **ID do Aplicativo (cliente)**, colete a ID do aplicativo do B2C criada no seu locatário do B2C. Posteriormente, ela será inserida como **GUID do Cliente** no construtor de sites.
1. Selecione **Redirecionar URIs** e colete a URL de resposta mostrada para seu site (a URL de resposta inserida na instalação).
1. Acesse **Página Inicial \> B2C do Azure AD – Fluxos de usuário** e colete os nomes completos de cada política de fluxo de usuário.

A imagem a seguir mostra um exemplo da página de visão geral do **B2C do Azure AD - Registros de aplicativo**.

![B2C do Azure AD - página de visão geral de Registros de aplicativos com a ID do aplicativo (cliente) realçada](./media/ClientGUID_Application_AzurePortal.png)

A imagem a seguir mostra um exemplo de políticas de fluxo de usuário na página **B2C do Azure AD – Fluxos de usuário (políticas)**.

![Coletar os nomes de cada fluxo de política de B2C.](./media/B2CImage_22.png)

### <a name="enter-your-azure-ad-b2c-tenant-application-information-into-commerce"></a>Insira as informações do aplicativo do locatário do Azure AD B2C no Commerce

Insira os detalhes do locatário B2C do Azure AD no construtor de sites do Commerce antes de associar o locatário B2C aos sites.

Para adicionar as informações do aplicativo do locatário do Azure AD B2C ao Commerce, siga estas etapas.

1. Faça login como administrador no construtor de sites do Commerce no seu ambiente.
1. No painel de navegação esquerdo, selecione **Configurações de Locatário** para expandi-lo.
1. Em **Configurações de Locatário**, selecione **Configuração de autenticação do site**. 
1. Na janela principal ao lado de **Perfis de autenticação no site**, selecione **Gerenciar**. (Se o locatário aparecer na lista de perfis de autenticação no site, ele já foi adicionado por um administrador. Verifique se os itens na etapa 6 abaixo correspondem aos da sua configuração B2C pretendida. Também é possível criar um novo perfil usando os locatários ou aplicativos do Azure AD B2C semelhantes para contabilizar diferenças mínimas, como diferentes IDs de política de usuário).
1. Selecione **Adicionar perfil de autenticação de site**.
1. Insira os seguintes itens obrigatórios no formulário exibido usando valores do locatário e aplicativo B2C. Os campos que não são obrigatórios (sem um asterisco) podem ser deixados em branco.

    - **Nome do Aplicativo**: O nome do Aplicativo B2C, por exemplo, "Fabrikam B2C".
    - **Nome do locatário**: O nome de seu locatário B2C (por exemple, use "fabrikam" se o domínio aparecer como "fabrikam.onmicrosoft.com" para o locatário B2C). 
    - **ID da Política de Esquecer Senha**: A ID da política de fluxo de usuário de esquecer senha, por exemplo, "B2C_1_PasswordReset".
    - **ID da Política de Inscrição e Entrada**: a ID da política do fluxo de usuário de inscrição e entrada, por exemplo "B2C_1_signup_signin".
    - **GUID do Cliente**: A ID do aplicativo B2C, por exemplo "22290eb2-c52e-42e9-8b35-a2b0a3bcb9e6".
    - **ID da Política de Editar Perfil**: A ID da política do fluxo de usuário de edição de perfil, por exemplo "B2C_1A_ProfileEdit".

1. Selecione **OK**. Agora você verá o nome do aplicativo B2C aparecer na lista.
1. Selecione **Salvar** para salvar as alterações.

O campo **Domínio personalizado de logon** opcional só deverá ser usado se você estiver configurando um domínio personalizado para o locatário do Azure AD B2C. Para obter detalhes adicionais e considerações sobre o uso do campo **Domínio personalizado de logon**, consulte as [Informações adicionais sobre B2C](additional-b2c-info.md).

### <a name="associate-the-b2c-application-to-your-site-and-channel"></a>Associar o aplicativo B2C ao site e ao canal

> [!WARNING]
> - Se o site já estiver associado a um aplicativo B2C, alterar para outro aplicativo B2C removerá as referências atuais estabelecidas para usuários já inscritos neste ambiente. Se for alterado, todas as credenciais associadas ao aplicativo B2C atualmente atribuído não estarão disponíveis para os usuários. 
> - Somente atualize o aplicativo B2C se estiver configurando o aplicativo B2C do canal pela primeira vez ou se quiser que os usuários se inscrevam novamente com novas credenciais neste canal com o novo aplicativo B2C. Tenha cautela ao associar canais aos aplicativos B2C e nomeie os aplicativos de forma clara. Se um canal não estiver associado a um aplicativo B2C nas etapas abaixo, os usuários que fizerem logon nesse canal para o seu site serão inseridos no aplicativo B2C exibido como **padrão** na lista **Configurações do Locatário \> Configurações do B2C** de aplicativos B2C.

Para associar o aplicativo B2C ao site e ao canal, siga estas etapas.

1. Navegue até o seu site no construtor de sites do Commerce.
1. No painel de navegação esquerdo, selecione **Configurações de Site** para expandi-lo.
1. Abaixo de **Configurações do Site**, selecione **Canais**.
1. Na janela principal em **Canais**, selecione o seu canal.
1. No painel de propriedades do canal à direita, selecione o nome do aplicativo B2C no menu suspenso **Selecionar Aplicativo B2C**.
1. Selecione **Fechar** e, depois, selecione **Salvar e Publicar**.

## <a name="next-steps"></a>Próximas etapas

Para continuar o processo de configuração de um locatário de B2 no Commerce, acesse [Informações adicionais de B2C](additional-b2c-info.md).

## <a name="additional-resources"></a>Recursos adicionais

[Configurar um locatário B2C do Commerce](set-up-b2c-tenant.md)

[Criar ou vincular a um locatário existente do Azure AD B2C no portal do Azure](create-link-aad-b2c-tenant.md)

[Criar o aplicativo B2C](create-b2c-app.md)

[Criar políticas de fluxo de usuário](create-user-flow-policies.md)

[Adicionar provedores de identidade social (Opcional)](add-social-identity-providers.md)

[Atualizar o Commerce headquarters com as novas informações de B2C do Azure AD](update-hq-aad-b2c-info.md)

[Informações adicionais do B2C](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

---
title: Adicionar provedores de identidade social
description: Este artigo descreve como adicionar provedores de identidade social no portal do Microsoft Azure.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: 5596097a5484acafda54adcfffa68fb59c8fbc65
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785212"
---
# <a name="add-social-identity-providers"></a>Adicionar provedores de identidade social

[!include [banner](includes/banner.md)]

Este artigo descreve como adicionar provedores de identidade social no portal do Microsoft Azure.

Os provedores de identidade social permitem que os usuários usem suas contas sociais para autenticação. Incluir a autenticação de provedor de identidade social é opcional no Dynamics 365 Commerce. 

Se a autenticação de provedor de identidade social não for adicionada, os perfis padrão do B2C do Azure Active Directory (Azure AD) serão os perfis principais da sua base de usuários. Os usuários selecionarão o próprio nome de usuário (endereço de email preferencial) e definirão uma senha. O B2C do Azure AD autenticará os usuários diretamente. 

Se a autenticação do provedor de identidade social for adicionada e um usuário escolher um dos provedores de identidade social fornecidos, uma entidade ainda será criada no locatário B2C do Azure AD. O B2C do Azure AD autenticará as credenciais do usuário com o provedor de identidade social.

> [!NOTE]
> O logon do provedor de identidade cria um registro no locatário do B2C, mas em um formato diferente das contas locais, pois chamará a referência externa do provedor de identidade social para a autenticação. O usuário pode usar o mesmo endereço de email em todos os provedores de identidade social, indicando que o nome de usuário do email usado para a autenticação pode não ser exclusivo para o locatário. O B2C do Azure AD apenas irá impor que os usuários tenham um endereço de email exclusivo nas contas locais do B2C.

Antes de adicionar um provedor de identidade social para autenticação, Acesse o portal do provedor de identidade e configure um aplicativo de provedor de identidade conforme as orientações na documentação do B2C do Azure AD. Uma lista de links para a documentação é fornecida a seguir.

- [Amazon](/azure/active-directory-b2c/active-directory-b2c-setup-amzn-app)
- [Azure AD (Único Locatário)](/azure/active-directory-b2c/active-directory-b2c-setup-oidc-azure-active-directory)
- [Conta da Microsoft](/azure/active-directory-b2c/active-directory-b2c-setup-msa-app)
- [Facebook](/azure/active-directory-b2c/active-directory-b2c-setup-fb-app)
- [GitHub](/azure/active-directory-b2c/active-directory-b2c-setup-github-app)
- [Google](/azure/active-directory-b2c/active-directory-b2c-setup-goog-app)
- [LinkedIn](/azure/active-directory-b2c/active-directory-b2c-setup-li-app)
- [OpenID Connect](/azure/active-directory-b2c/active-directory-b2c-setup-oidc-idp)
- [Twitter](/azure/active-directory-b2c/active-directory-b2c-setup-twitter-app)

### <a name="add-and-set-up-a-social-identity-provider"></a>Adicionar e configurar um provedor de identidade social

> [!NOTE]
> Adicionar provedores de identidade social é uma etapa opcional quando você configura o locatário business-to-consumer (B2C) no Microsoft Dynamics 365 Commerce.

Para adicionar e configurar um provedor de identidade social, siga estas etapas.  

1. No portal do Azure, navegue até **Provedores de Identidade**.
1. Selecione **Adicionar**. A tela **Adicionar provedor de identidade** será exibida.
1. Em **Nome**, insira o nome a ser exibido para os usuários na tela de entrada.
1. Em **Tipo de provedor de identidade**, selecione um provedor de identidade na lista.
1. Selecione **OK**.
1. Selecione **Configurar este provedor de identidade** para acessar a tela **Configurar provedor de identidade social**.
1. Em **ID do Cliente**, insira o ID do cliente obtido na configuração do aplicativo do provedor de identidade.
1. Em **Segredo do cliente**, insira o segredo do cliente obtido na configuração do aplicativo do provedor de identidade.
1. Anexe o fluxo de usuário para as políticas de inscrição/entrada:
1. Acesse **B2C do Azure AD – Fluxos de usuário (políticas) \> {sua política de inscrição e logon} \> Provedores de identidade**.
1. Para anexar a política de fluxo de usuário de inscrição/entrada, selecione os provedores de identidade configurados para a sua conta. Para testar os fluxos, selecione **Executar fluxo de usuário** para cada provedor de identidade. Uma nova guia exibe a página de entrada com a caixa de seleção do novo provedor de identidade.

A imagem a seguir mostra exemplos das telas **Adicionar provedor de identidade** e **Configurar o provedor de identidade social** no B2C do Azure AD.

![Adicionar um Provedor de Identidade Social ao aplicativo.](./media/B2CImage_14.png)

A imagem a seguir mostra um exemplo de como selecionar provedores de identidade na página **Provedores de Identidade** do B2C do Azure AD.

![Selecione cada Provedor de Identidade Social que será habilitado para a sua política.](./media/B2CImage_16.png)

A imagem a seguir mostra um exemplo de uma tela de logon padrão com um botão de logon do provedor de identidade social exibido.

> [!NOTE]
> Se você estiver usando as páginas personalizadas criadas no Commerce para os fluxos de usuário, os botões para provedores de identidade social precisarão ser adicionados usando os recursos de extensibilidade da biblioteca de módulos do Commerce. Além disso, ao configurar seus aplicativos com um provedor de identidade social específica, em alguns casos, as cadeias de caracteres de configuração ou de URL podem diferenciar maiúsculas de minúsculas. Consulte as instruções de conexão do seu provedor de identidade social para obter mais informações.
 
![Exemplo de tela de logon padrão com o botão de logon do Provedor de Identidade Social exibido.](./media/B2CImage_17.png)

## <a name="next-steps"></a>Próximas etapas

Para continuar o processo de configuração de um locatário de B2 no Commerce, acesse [Atualizar Commerce headquarters com as novas informações de B2C do Azure AD](update-hq-aad-b2c-info.md).

## <a name="additional-resources"></a>Recursos adicionais

[Configurar um locatário B2C do Commerce](set-up-b2c-tenant.md)

[Criar ou vincular a um locatário existente do Azure AD B2C no portal do Azure](create-link-aad-b2c-tenant.md)

[Criar o aplicativo B2C](create-b2c-app.md)

[Criar políticas de fluxo de usuário](create-user-flow-policies.md)

[Atualizar o Commerce headquarters com as novas informações de B2C do Azure AD](update-hq-aad-b2c-info.md)

[Configurar o locatário B2C no construtor de sites do Commerce](config-b2c-tenant-site-builder.md)

[Informações adicionais do B2C](additional-b2c-info.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]

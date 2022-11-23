---
title: Criar políticas de fluxo de usuário
description: Este artigo descreve como criar políticas de fluxo de usuário no portal do Microsoft Azure.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: 91b9d99dfd8c3d100ca197aa499ca86799bbffc8
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785215"
---
# <a name="create-user-flow-policies"></a>Criar políticas de fluxo de usuário

[!include [banner](includes/banner.md)]

Este artigo descreve como criar políticas de fluxo de usuário no portal do Microsoft Azure.

Os fluxos de usuário são as políticas que o B2C do Azure Active Directory (Azure AD) usa para fornecer experiências seguras de logon, inscrição, edição de perfil e esquecer senha. O Dynamics 365 Commerce usa esses fluxos para realizar ações de políticas para interagir com o locatário B2C do Azure AD. Quando um usuário interage com essas políticas, ele é redirecionado para o locatário do B2C do Azure AD para realizar as ações.

O B2C do Azure AD fornece três tipos de fluxo de usuário básicos:
- Inscrever-se e fazer logon
- Edição de perfil
- Senha redefinida

Você pode optar por usar os fluxos de usuário padrão fornecidos pelo Azure AD, que exibirão uma página hospedada pelo Azure AD B2C. Como alternativa, é possível criar uma página HTML para controlar a aparência e a experiência desses fluxos de usuário. 

Para personalizar as páginas de política de usuário com as páginas criadas no Dynamics 365 Commerce, consulte [Configurar páginas personalizadas para logons de usuário](custom-pages-user-logins.md). Para obter mais informações, consulte [Personalizar a interface de experiências de usuário no B2C do Azure Active Directory](/azure/active-directory-b2c/tutorial-customize-ui).

### <a name="create-a-sign-up-and-sign-in-user-flow-policy"></a>Criar uma política fluxo de usuário de inscrição e entrada

Para criar uma política de fluxo de usuário de inscrição e entrada, siga estas etapas.

1. No portal do Azure, selecione **Fluxos de usuário (políticas)** no painel de navegação esquerdo.
1. Na página do **B2C do Azure AD – Fluxos de usuário (políticas)**, selecione **Novo Fluxo de Usuário**.
1. Selecione a política **Inscrever-se e entrar** e, sem seguida, selecione a versão **Recomendada**.
1. Em **Nome**, insira um nome da política. Esse nome será exibido após um prefixo atribuído pelo portal (por exemplo, "B2C_1_").
1. Em **Provedores de identidade**, na seção **Contas locais**, selecione **Inscrição por e-mail**. A autenticação de email é usada nos cenários mais comuns do Commerce. Se você também estiver usando a autenticação de provedor de identidade social, também poderá selecioná-las neste momento.
1. Em **Autenticação Multifator**, selecione a escolha apropriada para a sua empresa. 
1. Em **Atributos e declarações de usuário**, selecione as opções para coletar atributos ou retornar reivindicações, conforme apropriado. Selecione **Mostrar mais...** para obter a lista completa de atributos e opções de declarações. O Commerce requer as seguintes opções padrão:

    | **Coletar atributo** | **Retornar reivindicação** |
    | ---------------------- | ----------------- |
    | Endereço de Email          | Endereços de Email   |
    | Nome Fornecido             | Nome Fornecido        |
    |                        | Provedor de Identidade |
    | Sobrenome                | Sobrenome           |
    |                        | ID do Objeto do Usuário  |

1. Selecione **Criar**.

A imagem a seguir é um exemplo do fluxo de usuário de inscrição e entrada do Azure AD B2C.

![Configurações da política de Inscrição e Logon.](./media/B2CImage_11.png)

   
### <a name="create-a-profile-editing-user-flow-policy"></a>Criar uma política de fluxo de usuário de edição de perfil

Para criar uma política de fluxo de usuário de edição de perfil, siga estas etapas.

1. No portal do Azure, selecione **Fluxos de usuário (políticas)** no painel de navegação esquerdo.
1. Na página do **B2C do Azure AD – Fluxos de usuário (políticas)**, selecione **Novo Fluxo de Usuário**.
1. Selecione **Edição de perfil** e selecione a versão **Recomendada**.
1. Em **Nome**, insira o fluxo de usuário de edição de perfil. Esse nome será exibido após um prefixo atribuído pelo portal (por exemplo, "B2C_1_").
1. Em **Provedores de identidade**, na seção **Contas locais**, selecione **Entrada no Email**.
1. Em **Atributos do usuário**, marque as seguintes caixas de seleção:
    
    | **Coletar atributo** | **Retornar reivindicação** |
    | ---------------------- | ----------------- |
    |                        | Endereços de Email   |
    | Nome Fornecido             | Nome Fornecido        |
    |                        | Provedor de Identidade |
    | Sobrenome                | Sobrenome           |
    |                        | ID do Objeto do Usuário  |
    
1. Selecione **Criar**.

A imagem a seguir mostra um exemplo do fluxo de usuário de edição do perfil do B2C do Azure AD.

![Exemplo de fluxo do usuário de edição de perfil do Azure AD B2C](./media/B2CImage_12.png)

### <a name="create-a-password-reset-user-flow-policy"></a>Criar uma política de fluxo de usuário de redefinição de senha

Para criar uma política de fluxo de usuário de redefinição de senha, siga estas etapas.

1. No portal do Azure, selecione **Fluxos de usuário (políticas)** no painel de navegação esquerdo.
1. Na página do **B2C do Azure AD – Fluxos de usuário (políticas)**, selecione **Novo Fluxo de Usuário**.
1. Selecione **Redefinição de Senha** e selecione a versão **Recomendada**.
1. Em **Nome**, insira um nome para o fluxo de usuário de redefinição de senha.
1. Em **Provedores de identidade**, selecione **Redefinir senha usando endereço de email**.
1. Selecione **Criar**.
1. Em **Declarações do aplicativo**, marque as seguintes caixas de seleção:
    - **Endereços de email**
    - **Nome Fornecido**
    - **Sobrenome**
    - **ID do Objeto do Usuário**
1. Selecione **Criar**.

A imagem a seguir mostra onde definir **Redefinir Senha usando endereço de email** no fluxo de usuário de redefinição de senha do B2C do Azure AD.

![Configure "Redefinir Senha usando endereço de email" na política de Redefinição de Senha](./media/B2CImage_13.png)

## <a name="next-steps"></a>Próximas etapas

Para continuar o processo de configuração de um locatário de B2 no Commerce, acesse [Adicionar provedores de identidade social](add-social-identity-providers.md).

## <a name="additional-resources"></a>Recursos adicionais

[Configurar um locatário B2C do Commerce](set-up-b2c-tenant.md)

[Criar ou vincular a um locatário existente do Azure AD B2C no portal do Azure](create-link-aad-b2c-tenant.md)

[Criar o aplicativo B2C](create-b2c-app.md)

[Adicionar provedores de identidade social (Opcional)](add-social-identity-providers.md)

[Atualizar o Commerce headquarters com as novas informações de B2C do Azure AD](update-hq-aad-b2c-info.md)

[Configurar o locatário B2C no construtor de sites do Commerce](config-b2c-tenant-site-builder.md)

[Informações adicionais do B2C](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

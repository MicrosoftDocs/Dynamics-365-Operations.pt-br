---
title: Configurar páginas personalizadas para entradas dos usuários
description: Este tópico descreve como criar páginas personalizadas no Microsoft Dynamics 365 Commerce que manipula inscrições personalizadas para usuários nos locatários de business-to-consumer (B2C) do Azure Active Directory (Azure AD).
author: brianshook
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 0b54bf6234dcb87c84b21259c30ca5c321869adf
ms.sourcegitcommit: 8028fbc5b9585e87d3331ea02577ff82ede090af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/16/2020
ms.locfileid: "3817297"
---
# <a name="set-up-custom-pages-for-user-sign-ins"></a>Configurar páginas personalizadas para entradas dos usuários


[!include [banner](includes/banner.md)]

Este tópico descreve como criar páginas personalizadas no Microsoft Dynamics 365 Commerce que manipula inscrições personalizadas para usuários nos locatários de business-to-consumer (B2C) do Azure Active Directory (Azure AD).

## <a name="overview"></a>Visão geral

Para usar as páginas personalizadas criadas no Dynamics 365 Commerce para manipular fluxos de inscrições de usuário, você deve configurar as políticas do Azure AD que serão referenciadas no ambiente de comércio. Você pode configurar as políticas B2C "Se inscrever e entrar," "Edição de perfil," e "Redefinição de senha" Azure AD usando o aplicativo B2C do Azure AD. O locatário B2C do Azure AD e nomes de política podem ser referenciados durante o processo de provisionamento feito para o ambiente de comércio usando Microsoft Dynamics Lifecycle Services (LCS).

As páginas personalizadas Comércio podem ser criadas usando se inscrever, entrar, edição de perfil da conta ou módulo para redefinição de senha. As URLs da página publicadas para essas páginas personalizadas devem ser referenciadas nas configurações de política do Azure AD B2C no portal do Azure.

## <a name="set-up-b2c-policies"></a>Configurar políticas B2C

Depois de ter configurado seu locatário B2C Azure AD e associá-lo com seu ambiente de comércio, vá para a página **Azure AD B2C** no portal do Azure e depois, no menu, em **Políticas**, selecione **Fluxos de usuário (políticas)**.

![Comando fluxos de usuário (políticas) no menu](./media/B2C_CustomPage_PoliciesMenu.png)

Agora você pode configurar fluxos de entrada de usuário de "Se inscrever e entrar," "Edição de perfil," e "Redefinição de senha".

### <a name="configure-the-sign-up-and-sign-in-policy"></a>Configurar a política "Se inscrever e entrar"

Para configurar a política ""Se inscrever e entrar", siga estas etapas.

1. Selecione **Novo fluxo de usuário**, e depois na guia **Recomendado**, selecione a política **"Se inscrever e entrar**.
1. Insira um nome para a política (por exemplo, **B2C\_1\_SignInSignUp**).
1. Na seção **Provedores de Identidade**, selecione os provedores de identidade para usar a política. Ao mínimo, **Inscrição por e-mail** deve estar selecionado.
1. Na coluna **Coletar atributo**, marque as caixas de seleção **Endereço de e-mail**, **Nome fornecido** e **Sobrenome**.
1. Na coluna **Retornar reivindicação**, marque as caixas de seleção **Endereços de e-mail**, **Nome fornecido**, **Provedor de identidade**, **Sobrenome** e **ID do objeto de usuário**.

    ![Atributos e reivindicações selecionados](./media/B2C_SignInSignUp_Attributes.png)

1. Selecione **OK** para criar a política.
1. Clique duas vezes no nome da política, e depois no painel de navegação, selecione **Propriedades**.
1. Defina a opção **Habilitar layout de página garantindo JavaScript (visualização)** como **Ligado**.

    ![As páginas de propriedade da nova política](./media/B2C_SignInSignUp_EnableJavascript.png)

> [!NOTE]
> O nome da política será referenciado por completo no ambiente de comércio. (O prefixo **B2C\_1\_** será incluído na referência.) Políticas não podem ser renomeadas após serem criadas. Se você está substituindo uma política existente para seu ambiente de comércio, você pode excluir a política original e criar uma nova política que tem o mesmo nome. Alternativamente, se o ambiente já foi provisionado, você pode enviar o novo nome de política por meio de solicitação de serviço.

Você retornará a esta política para concluir a configuração depois de criar páginas personalizadas. Por hora, feche a política para retornar à página **Fluxos de usuário (políticas)** no portal do Azure.

### <a name="configure-the-profile-editing-policy"></a>Configurar a política "Edição de perfil"

Para configurar a política "Edição de perfil", siga as etapas a seguir.

1. Selecione **Novo fluxo de usuário**, e depois na guia **Recomendado**, selecione a política **Edição de perfil**.
1. Insira um nome para a política (por exemplo, **B2C\_1\_EditProfile**).
1. Na seção **Provedores de Identidade**, selecione os provedores de identidade para usar a política. Ao mínimo, **Inscrição de conta local** deve estar selecionado.
1. Na coluna **Coletar atributo**, marque as caixas de seleção **Endereços de e-mail** e **Sobrenome**.
1. Na coluna **Retornar reivindicação**, marque as caixas de seleção **Endereços de e-mail**, **Nome fornecido**, **Provedor de identidade**, **Sobrenome** e **ID do objeto de usuário**.
1. Selecione **OK** para criar a política.
1. Clique duas vezes no nome da política, e depois no painel de navegação, selecione **Propriedades**.
1. Defina a opção **Habilitar layout de página garantindo JavaScript (visualização)** como **Ligado**.

Você retornará a esta política para concluir a configuração depois de criar páginas personalizadas. Por hora, feche a política para retornar à página **Fluxos de usuário (políticas)** no portal do Azure.

### <a name="configure-the-password-reset-policy"></a>Configurar a política "Redefinir senha"

Para configurar a política "Redefinir senha", siga as etapas a seguir.

1. Selecione **Novo fluxo de usuário**, e depois na guia **Visualização**, selecione a política **Redefinir senha v1.1**.

    ![Política Redefinir senha v1.1 selecionada na guia Visualização](./media/B2C_ForgetPassword_Menu.png)

1. Insira um nome para a política (por exemplo, **B2C\_1\_ForgetPassword**).
1. Na seção **Provedores de Identidade**, selecione **Redefinir senha usando endereço de e-mail**.
1. Na coluna **Retornar reivindicação**, marque as caixas de seleção **Endereços de e-mail**, **Nome fornecido**, **Sobrenome** e **ID do objeto de usuário**.

    ![Reclamações selecionadas](./media/B2C_ForgetPassword_Attributes.png)

1. Selecione **OK** para criar a política.
1. Clique duas vezes no nome da política, e depois no painel de navegação, selecione **Propriedades**.
1. Defina a opção **Habilitar layout de página garantindo JavaScript (visualização)** como **Ligado**.

Você retornará a esta política para concluir a configuração depois de criar páginas personalizadas. Por hora, feche a política para retornar à página **Fluxos de usuário (políticas)** no portal do Azure.

## <a name="build-the-custom-pages"></a>Criar as páginas personalizadas

Para criar as páginas personalizadas para lidar com inscrições de usuários, siga estas etapas.

1. Nas ferramentas de comércio, vá para nosso site.
1. Criar os seguintes cinco modelos e cinco páginas:

    - Um modelo de **Entrada** e página que usa o módulo de entrada.
    - Um modelo de **Se inscrever** e página que usa o módulo de inscrição.
    - Um modelo e a página para **Redefinir senha** que usa o módulo para redefinir senha.
    - Um modelo e a página para **Verificação para redefinir senha** que usa o módulo de verificação para redefinir senha.
    - Um modelo e página **Edição de perfil** que usa o módulo de edição do perfil da conta

Quando você cria páginas, siga estas diretrizes:

- Para cada página ou módulo, use o layout e estilo que melhor atende aos seus requisitos de empresa.
- Publicar todas as páginas e URLs que devem ser usadas na configuração do Azure AD B2C.
- Após as páginas e URLs serem publicadas, colete as URLs que devem ser usadas para configurações da política Azure AD B2C. Um sufixo **?preloadscripts=true** será adicionado a cada URL quando é usado.

> [!IMPORTANT]
> Não reutilize cabeçalhos e rodapés universais com links relacionados. Como essas páginas estão hospedadas no domínio Azure AD B2C quando são usadas, apenas URLs absolutas devem ser usadas para todos os links.

## <a name="configure-azure-ad-b2c-policies-with-custom-page-information"></a>Configurar políticas Azure AD B2C com informações de página personalizadas 

No portal do Azure, volte à página do **Azure AD B2C** e depois no menu, em **Políticas**, selecione **Fluxos de usuário (políticas)**.

### <a name="update-the-sign-up-and-sign-in-policy-with-custom-page-information"></a>Atualizar a política "Se inscrever e entrar" com informações de página personalizadas

Para atualizar a política "Se inscrever e entrar" com informações de página personalizadas, siga estas etapas.

1. Na política **Se inscrever e entrar** que você configurou anteriormente, no painel de navegação, selecione **Layouts de página**.
1. Selecione o layout **Unificar entrada ou inscrição na página**.
1. Defina a opção **Usar conteúdo de página personalizado** como **Sim**.
1. No campo **URL de página personalizada**, insira a URL de entrada completa. Inclua o sufixo **?preloadscripts=true**. Por exemplo, insira ``www.<my domain>.com/sign-in?preloadscripts=true``.
1. No campo **Versão de layout de página (visualização)**, selecione **1.2.0**.
1. Selecione o layout **Página de inscrição de conta local**.
1. Defina a opção **Usar conteúdo de página personalizado** como **Sim**.
1. No campo **URL de página personalizada**, insira a URL de entrada completa. Inclua o sufixo **?preloadscripts=true**. Por exemplo, insira ``www.<my domain>.com/sign-up?preloadscripts=true``.
1. No campo **Versão de layout de página (visualização)**, selecione **1.2.0**.
1. Na seção **Atributos de usuário**, siga estas etapas:

    1. Para os atributos **Endereço de e-mail**, **Nome** e **Sobrenome**, selecione **Não** no campo **Requer verificação**.
    1. Para os atributos **Nome** e **Sobrenome**, selecione **Não** no campo **Opcional**.

    ![Configuração da política de página de inscrição de conta local](./media/B2C_SignUp_PageURLConfig.png)

### <a name="update-the-profile-editing-policy-with-custom-page-information"></a>Atualizar a política "Edição de perfil" com informações de página personalizadas

Para atualizar a política "Edição de perfil" com informações de página personalizadas, siga estas etapas.

1. Na política **Edição de perfil** que você configurou anteriormente, no painel de navegação, selecione **Layouts de página**.
1. Selecione o layout **Página de edição de perfil**.
1. Defina a opção **Usar conteúdo de página personalizado** como **Sim**.
1. No campo **URL de página personalizada**, insira a URL de edição de perfil completa. Inclua o sufixo **?preloadscripts=true**. Por exemplo, insira ``www.<my domain>.com/profile-edit?preloadscripts=true``.
1. No campo **Versão de layout de página (visualização)**, selecione **1.2.0**.
1. Na seção **Atributos de usuário**, siga estas etapas:

    1. Para os atributos **Endereço de e-mail**, **Nome**, selecione **Não** no campo **Requer verificação**.
    1. Para os atributos **Nome** e **Sobrenome**, selecione **Não** no campo **Opcional**.

### <a name="update-the-password-reset-policy-with-custom-page-information"></a>Atualizar a política "Redefinir senha" com informações de página personalizadas

Para atualizar a política "Redefinir senha" com informações de página personalizadas, siga estas etapas.

1. Na política **Redefinir senha** que você configurou anteriormente, no painel de navegação, selecione **Layouts de página**.
1. Selecione o layout **Nova página de senha**.
1. Defina a opção **Usar conteúdo de página personalizado** como **Sim**.
1. No campo **URL de página personalizada**, insira a URL de redefinição de senha completa. Inclua o sufixo **?preloadscripts=true**. Por exemplo, insira ``www.<my domain>.com/passwordreset?preloadscripts=true``.
1. No campo **Versão de layout de página (visualização)**, selecione **1.2.0**.
1. Selecione o layout **Página de verificação de conta**.
1. Defina a opção **Usar conteúdo de página personalizado** como **Sim**.
1. No campo **URL de página personalizada**, insira a URL de verificação redefinição de senha completa. Inclua o sufixo **?preloadscripts=true**. Por exemplo, insira ``www.<my domain>.com/passwordreset-verification?preloadscripts=true``.
1. No campo **Versão de layout de página (visualização)**, selecione **1.2.0**.



## <a name="customize-default-text-strings-for-labels-and-descriptions"></a>Personalizar caracteres de texto padrão e rótulos para descrições

Na biblioteca de módulos, os módulos de entrada são previamente preenchidos com caracteres de texto padrão para os rótulos e descrições. Você pode personalizar esses caracteres no kit de desenvolvimento de software (SDK) atualizando os valores no arquivo global.json para entrar no módulo.

Por exemplo, o texto padrão para o link de senha esquecida é **Esqueceu a senha?**. A seguir veja um texto padrão na página de entrada.

![Texto padrão para o link de senha esquecida na página de entrada](./media/B2C_SignUp_ModuleFace.png)

No entanto, no arquivo global.json para o módulo de entrada da biblioteca de módulos, você pode editar o texto para **Esqueceu a senha?**, conforme mostrado na ilustração a seguir.

![Texto de link atualizado no arquivo global.json do módulo de entrada](./media/B2C_CustomizingStringsForModule.png)

Depois de atualizar o arquivo global.json e publicar suas alterações, o novo texto de link será exibido no módulo de entrada no Commerce e na página de entrada ativa.

## <a name="additional-resources"></a>Recursos adicionais

[Configure seu nome de domínio](configure-your-domain-name.md)

[Implantar um novo site de comércio eletrônico](deploy-ecommerce-site.md)

[Criar um site de comércio eletrônico](create-ecommerce-site.md)

[Associar um site online a um canal](associate-site-online-store.md)

[Gerenciar arquivos robots.txt](manage-robots-txt-files.md)

[Carregar redirecionamentos de URL em massa](upload-bulk-redirects.md)

[Configurar um locatário B2C do Commerce](set-up-B2C-tenant.md)

[Configurar múltiplos locatários B2C em um ambiente do Commerce](configure-multi-B2C-tenants.md)

[Adicionar suporte para uma rede de entrega de conteúdo (CDN)](add-cdn-support.md)

[Habilitar detecção de lojas com base na localização](enable-store-detection.md)

---
title: Configurar um locatário B2C do Commerce
description: Este tópico descreve como configurar os locatários business-to-consumer (B2C) do Azure Active Directory (Azure AD) para a autenticação do site de usuário no Dynamics 365 Commerce.
author: BrianShook
ms.date: 03/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.dyn365.ops.version: ''
ms.openlocfilehash: 1351b9f22416e8ce6d90022997f0a15e9eb4042a
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6344362"
---
# <a name="set-up-a-b2c-tenant-in-commerce"></a>Configurar um locatário B2C do Commerce

[!include [banner](includes/banner.md)]

Este tópico descreve como configurar os locatários business-to-consumer (B2C) do Azure Active Directory (Azure AD) para a autenticação do site de usuário no Dynamics 365 Commerce.

O Dynamics 365 Commerce usa o B2C do Azure AD para oferecer suporte aos fluxos de credenciais e autenticação de usuário. Um usuário pode se inscrever, acessar e redefinir a senha por meio desses fluxos. O B2C do Azure AD armazena informações confidenciais de autenticação do usuário, como nome de usuário e senha. O registro de usuário no locatário B2C armazenará um registro de conta local B2C ou um registro de provedor de identidade social B2C. Esses registros de B2C serão vinculados ao registro do cliente no ambiente do Commerce.

> [!WARNING] 
> O Azure AD B2C removerá os fluxos de usuário antigos (herdados) em 1º de agosto de 2021. Portanto, você deve planejar a migração dos fluxos de usuário para a nova versão recomendada. A nova versão oferece paridade de recursos e novos recursos. A biblioteca de módulos do Commerce versão 10.0.15 ou superior deve ser usada com os fluxos de usuário de B2C recomendados. Para obter mais informações, consulte [Fluxos de usuário no Azure Active Directory B2C](/azure/active-directory-b2c/user-flow-overview).
 
 > [!NOTE]
 > Os ambientes de avaliação do Commerce vêm com um locatário do Azure AD B2C pré-carregado para fins de demonstração. Carregar seu próprio locatário do Azure AD B2C usando as etapas abaixo não será necessário para ambientes de avaliação.

## <a name="create-or-link-to-an-existing-aad-b2c-tenant-in-the-azure-portal"></a>Criar ou vincular a um locatário B2C do AAD no portal do Azure

1. Entre no [portal do Azure](https://portal.azure.com/).
1. No menu do portal do Azure, selecione **Criar um recurso**. Certifique-se de usar a assinatura e o diretório que será conectado ao ambiente do Commerce.

    ![Criar um Recurso no Portal do Azure.](./media/B2CImage_1.png)

1. Vá para **Identidade \> B2C do Azure Active Directory**.
1. Na página **Criar Locatário B2C ou Vincular a um Locatário existente**, use uma das opções abaixo que melhor atende às necessidades da sua empresa:

    - **Criar Locatário B2C do Azure AD**: Use esta opção para criar um locatário B2C do AAD.
        1. Selecione **Criar Locatário B2C do Azure AD**.
        1. Em **Nome da organização**, insira o nome da organização.
        1. Em **Nome do domínio inicial**, insira o nome do domínio inicial.
        1. Em **País ou região**, selecione o país ou a região.
        1. Selecione **Criar** para criar o locatário.

     ![Criar um Locatário do Azure AD.](./media/B2CImage_2.png)

     - **Vincular um Locatário B2C do Azure AD à minha assinatura do Azure**: Use esta opção se já tiver um locatário B2C do Azure AD ao qual deseja vincular.
        1. Selecione **Vincular um Locatário B2C do Azure AD existente à minha assinatura do Azure**.
        1. Em **Locatário B2C do Azure AD**, selecione o locatário B2C apropriado. Se a mensagem "Nenhum locatário B2C elegível encontrado" aparecer na caixa de seleção, você não tem um locatário B2C elegível existente e precisará criar um.
        1. Em **Grupo de recursos**, selecione **Criar**. Insira um **Nome** para o grupo de recursos que conterá o locatário, selecione **Local o grupo de recursos** e selecione **Criar**.

    ![Vincule um Locatário B2C do Azure AD existente à Assinatura do Azure.](./media/B2CImage_3.png)

1. Após criar diretório B2C do Azure AD (pode demorar alguns instantes), será exibido um link para o novo diretório no painel. Este link direcionará você para a página "Bem-vinco ao B2C do Azure Active Directory".

    ![Link para o novo Diretório do AAD.](./media/B2CImage_4.png)

> [!NOTE]
> Se você tiver várias assinaturas na conta do Azure ou tiver configurado o locatário B2C sem vincular a uma assinatura ativa, um banner de **Solução de problemas** orientará você a vincular o locatário a uma assinatura. Selecione a mensagem de solução de problemas e siga as instruções para resolver o problema da assinatura.

A imagem a seguir mostra um exemplo de um banner de **Solução de problemas** do B2C do Azure AD.

![Aviso mostrando que o diretório não tem uma Assinatura Ativa.](./media/B2CImage_5.png)

## <a name="create-the-b2c-application"></a>Criar o aplicativo B2C

Depois que o locatário B2C tiver sido criado, você criará um aplicativo B2C dentro do novo locatário do Azure AD B2C para interagir com o Commerce.

Para criar o aplicativo B2C, siga estas etapas.

1. No portal do Azure, selecione **Registros de aplicativo** e, em seguida, selecione **Novo registro**.
1. Em **Nome**, insira o nome a ser dado a este aplicativo do Azure AD B2C.
1. Em **Tipos de conta com suporte**, selecione **Contas em qualquer provedor de identidade ou diretório organizacional (para autenticar usuários com fluxos de usuário)**.
1. Para **URI de Redirecionamento**, insira suas URLs de resposta dedicadas como o tipo **Web**. Para obter informações sobre URLs de resposta e como formatá-las, consulte [URLs de resposta](#reply-urls) abaixo.
1. Para **Permissões**, selecione **Conceder consentimento do administrador para permissões OpenID e offline_access**.
1. Selecione **Registrar**.
1. Selecione o aplicativo recém-criado e navegue até o menu **Autenticação**. Aqui, é possível inserir **URIs de redirecionamento** adicionais, se necessário (agora ou posteriormente). Prossiga para a próxima etapa se isso não for necessário no momento.
1. Em **Concessão implícita**, selecione **Tokens de acesso** e **Tokens de ID** para habilitá-los para o aplicativo. Selecione **Salvar**.
1. Vá para o menu **Visão geral** do portal do Azure e copie a **ID do aplicativo (cliente)**. Anote essa ID para as etapas de configuração posteriores (mencionadas posteriormente como a **GUID do Cliente**).

Para obter referência adicional sobre os Registros de Aplicativo no Azure AD B2C, consulte [A nova experiência de Registros de aplicativos para o Azure Active Directory B2C](/azure/active-directory-b2c/app-registrations-training-guide)

### <a name="reply-urls"></a>URLs de resposta

As URLs de resposta são importantes, pois permitem uma lista de domínios de retorno quando o seu site chamar o B2C do Azure AD para autenticar um usuário. Isto permite o retorno do usuário autenticado para o domínio a partir do qual estão tentando fazer o logon (domínio do seu site). 

Na caixa **URL de resposta** na tela **B2C do Azure AD – Aplicativos \> Novo aplicativo**, será necessário adicionar linhas separadas ao domínio do site e (após o ambiente ser provisionado) à URL gerada pelo Commerce. Essas URLs devem sempre usar um formato de URL válido e devem ser somente URLs base (sem barras ou caminhos à direita). A string ``/_msdyn365/authresp`` precisará ser inserida às URLs base, como nos seguintes exemplos.

- ``https://www.fabrikam.com/_msdyn365/authresp`` (O domínio deve corresponder completamente ao domínio de comércio eletrônico. Se você tiver vários domínios, precisará adicionar esta URL para cada um deles.)
- ``https://fabrikam-prod.commerce.dynamics.com/_msdyn365/authresp``

## <a name="create-user-flow-policies"></a>Criar políticas de fluxo de usuário

Os fluxos de usuário são as políticas que o B2C do Azure AD usa para fornecer experiências seguras de logon, inscrição, edição de perfil e esquecer senha. O Dynamics 365 Commerce usa esses fluxos para realizar ações de políticas para interagir com o locatário B2C do Azure AD. Quando um usuário interage com essas políticas, ele é redirecionado para o locatário do B2C do Azure AD para realizar as ações.

O B2C do Azure AD fornece três tipos de fluxo de usuário básicos:
- Inscrever-se e fazer logon
- Edição de perfil
- Senha redefinida

Você pode optar por usar os fluxos de usuário padrão fornecidos pelo Azure AD, que exibirão uma página hospedada pelo B2C do AAD. Como alternativa, é possível criar uma página HTML para controlar a aparência e a experiência desses fluxos de usuário. 

Para personalizar as páginas de política de usuário com as páginas criadas no Dynamics 365 Commerce, consulte [Configurar páginas personalizadas para logons de usuário](custom-pages-user-logins.md). Para obter informações adicionais, consulte [Personalizar a interface de experiências de usuário no B2C do Azure Active Directory](/azure/active-directory-b2c/tutorial-customize-ui).

### <a name="create-a-sign-up-and-sign-in-user-flow-policy"></a>Criar uma política fluxo de usuário de inscrição e logon

Para criar uma política de fluxo de usuário de inscrição e logon, siga estas etapas.

1. No portal do Azure, selecione **Fluxos de usuário (políticas)** no painel de navegação esquerdo.
1. Na página do **B2C do Azure AD – Fluxos de usuário (políticas)**, selecione **Novo Fluxo de Usuário**.
1. Selecione a política **Inscrever-se e entrar** e, sem seguida, selecione a versão **Recomendada**.
1. Em **Nome**, insira um nome da política. Esse nome será exibido após um prefixo atribuído pelo portal (por exemplo, "B2C_1_").
1. Em **Provedores de identidade**, marque a caixa de seleção apropriada.
1. Em **Autenticação Multifator**, selecione a escolha apropriada para a sua empresa. 
1. Em **Atributos e declarações de usuário**, selecione as opções para coletar atributos ou retornar reivindicações, conforme apropriado. O Commerce requer as seguintes opções padrão:

    | **Coletar atributo** | **Retornar reivindicação** |
    | ---------------------- | ----------------- |
    | Endereço de Email          | Endereços de Email   |
    | Nome Fornecido             | Nome Fornecido        |
    |                        | Provedor de Identidade |
    | Sobrenome                | Sobrenome           |
    |                        | ID do Objeto do Usuário  |

1. Selecione **Criar**.

A imagem a seguir é um exemplo do fluxo de usuário de inscrição e logon do B2C do Azure AD.

![Configurações da política de Inscrição e Logon.](./media/B2CImage_11.png)

A imagem a seguir mostra a opção **Executar fluxo de usuário** no fluxo de usuário de inscrição e logon do B2C do Azure AD.

![Executar a opção do fluxo de usuário no fluxo da política.](./media/B2CImage_23.png)
   
### <a name="create-a-profile-editing-user-flow-policy"></a>Criar uma política de fluxo de usuário de edição de perfil

Para criar uma política de fluxo de usuário de edição de perfil, siga estas etapas.

1. No portal do Azure, selecione **Fluxos de usuário (políticas)** no painel de navegação esquerdo.
1. Na página do **B2C do Azure AD – Fluxos de usuário (políticas)**, selecione **Novo Fluxo de Usuário**.
1. Selecione **Edição de perfil** e selecione a versão **Recomendada**.
1. Em **Nome**, insira o fluxo de usuário de edição de perfil. Esse nome será exibido após um prefixo atribuído pelo portal (por exemplo, "B2C_1_").
1. Em **Provedores de identidade**, selecione **Entrada no Email**.
1. Em **Atributos do usuário**, marque as seguintes caixas de seleção:
    - **Endereços de Email** (somente **Retornar reivindicação**)
    - **Nome Fornecido** (**Coletar atributo** e **Retornar reivindicação**)
    - **Provedor de Identidade** (somente **Retornar reivindicação**)
    - **Sobrenome** (**Coletar atributo** e **Retornar reivindicação**)
    - **ID de Objeto do Usuário** (somente **Retornar reivindicação**)
1. Selecione **Criar**.

A imagem a seguir mostra um exemplo do fluxo de usuário de edição do perfil do B2C do Azure AD.

![Criar o fluxo de usuário de Edição de Perfil.](./media/B2CImage_12.png)

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

## <a name="add-social-identity-providers-optional"></a>Adicionar provedores de identidade social (Opcional)

Os provedores de identidade social permitem que os usuários usem suas contas sociais para autenticação. Incluir a autenticação de provedor de identidade social é opcional no Dynamics 365 Commerce. 

Se a autenticação de provedor de identidade social não for adicionada, os perfis padrão do B2C do Azure AD serão os perfis principais da sua base de usuários. Os usuários selecionarão o próprio nome de usuário (endereço de email preferencial) e definirão uma senha. O B2C do Azure AD autenticará os usuários diretamente. 

Se a autenticação do provedor de identidade social for adicionada e um usuário escolher um dos provedores de identidade social fornecidos, uma entidade ainda será criada no locatário B2C do Azure AD. O B2C do Azure AD autenticará as credenciais do usuário com o provedor de identidade social.

> [!NOTE]
> O logon do provedor de identidade cria um registro no locatário do B2C, mas em um formato diferente das contas locais, pois chamará a referência externa do provedor de identidade social para a autenticação. O usuário pode usar o mesmo endereço de email em todos os provedores de identidade social, indicando que o nome de usuário do email usado para a autenticação pode não ser exclusivo para o locatário. O B2C do Azure AD apenas irá impor que os usuários tenham um endereço de email exclusivo nas contas locais do B2C.

Antes de adicionar um provedor de identidade social para autenticação, vá para o portal do provedor de identidade e configure um aplicativo de provedor de identidade conforme as orientações na documentação do B2C do Azure AD. Uma lista de links para a documentação é fornecida a seguir.

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

Para adicionar e configurar um provedor de identidade social, siga estas etapas.  

1. No portal do Azure, navegue até **Provedores de Identidade**.
1. Selecione **Adicionar**. A tela **Adicionar provedor de identidade** será exibida.
1. Em **Nome**, insira o nome a ser exibido para os usuários na tela de logon.
1. Em **Tipo de provedor de identidade**, selecione um provedor de identidade na lista.
1. Selecione **OK**.
1. Selecione **Configurar este provedor de identidade** para acessar a tela **Configurar provedor de identidade social**.
1. Em **ID do Cliente**, insira o ID do cliente obtido na configuração do aplicativo do provedor de identidade.
1. Em **Segredo do cliente**, insira o segredo do cliente obtido na configuração do aplicativo do provedor de identidade.
1. Anexe o fluxo de usuário para as políticas de inscrição e logon:
1. Vá para **B2C do Azure AD – Fluxos de usuário (políticas) \> {sua política de inscrição e logon} \> Provedores de identidade**.
1. Para anexar a política de fluxo de usuário de inscrição/logon, selecione os provedores de identidade configurados para a sua conta. Para testá-los, selecione **Executar fluxo de usuário** para cada provedor de identidade. Uma nova guia será exibida na página de logon mostrando a caixa de seleção do novo provedor de identidade.

A imagem a seguir mostra exemplos das telas **Adicionar provedor de identidade** e **Configurar o provedor de identidade social** no B2C do Azure AD.

![Adicionar um Provedor de Identidade Social ao aplicativo.](./media/B2CImage_14.png)

A imagem a seguir mostra um exemplo de como selecionar provedores de identidade na página **Provedores de Identidade** do B2C do Azure AD.

![Selecione cada Provedor de Identidade Social que será habilitado para a sua política.](./media/B2CImage_16.png)

A imagem a seguir mostra um exemplo de uma tela de logon padrão com um botão de logon do provedor de identidade social exibido.

> [!NOTE]
> Se você estiver usando as páginas personalizadas criadas no Commerce para os fluxos de usuário, os botões para provedores de identidade social precisarão ser adicionados usando os recursos de extensibilidade da biblioteca de módulos do Commerce. Além disso, ao configurar seus aplicativos com um provedor de identidade social específica, em alguns casos, as cadeias de caracteres de configuração ou de URL podem diferenciar maiúsculas de minúsculas. Consulte as instruções de conexão do seu provedor de identidade social para obter mais informações.
 
![Exemplo de tela de logon padrão com o botão de logon do Provedor de Identidade Social exibido.](./media/B2CImage_17.png)

## <a name="update-commerce-headquarters-with-the-new-azure-ad-b2c-information"></a>Atualizar o Commerce headquarters com as novas informações do B2C do Azure AD

Depois que as etapas de provisionamento do B2C do Azure AD estiverem concluídas, o aplicativo B2C do Azure AD devem ser registrados no ambiente do Dynamics 365 Commerce.

Para atualizar o headquarters com as novas informações do B2C do Azure AD, siga estas etapas.

1. No Commerce, vá para **Parâmetros Compartilhados do Commerce** e selecione **Provedores de Identidade** no menu esquerdo.
1. Em **Provedores de Identidade**, faça o seguinte:
    1. Na caixa **Emissor**, insira o URL do emissor do provedor de identidade. Para encontrar o URL do emissor, consulte [Obter URL do emissor](#obtain-issuer-url) abaixo.
    1. Na caixa **Nome**, insira um nome para o registro do emissor.
    1. Na caixa **Tipo**, insira **B2C do Azure AD (id_token)**.
1. Em **Partes Confiáveis**, com o item do provedor de identidade do B2C acima selecionado, faça o seguinte:
    1. Na caixa **ClientID**, insira a ID do aplicativo B2C. Isso pode ser encontrado na caixa **ID do Aplicativo** na página de propriedades do aplicativo B2C.
    1. Na caixa **Tipo**, insira **Público**.
    1. Na caixa **Tipo de Usuário**, insira **Cliente**.
1. No painel de ação, selecione **Salvar**.
1. Na caixa de pesquisa do Commerce, procure **Agenda de distribuição**
1. No menu de navegação à esquerda da página **Agendas de distribuição**, selecione o trabalho **1110 Configuração global**.
1. No painel de ação, selecione **Executar Agora**.

### <a name="obtain-issuer-url"></a>Obter URL do emissor

Para obter o URL do emissor do provedor de identidade, siga estas etapas.
1. Na página do Azure AD B2C do portal do Azure, navegue até o fluxo de usuário **Inscrever-se e entrar**.
1. Selecione **Layouts de página** no menu de navegação esquerdo, em **Nome do layout**, selecione **Página de inscrição ou entrada unificada** e selecione **Executar fluxo do usuário**.
1. Certifique-se de que o aplicativo esteja definido para seu aplicativo pretendido do Azure AD B2C criado acima e selecione o link no cabeçalho **Executar fluxo do usuário**, que inclui ``.../.well-known/openid-configuration?p=<B2CSIGN-INPOLICY>``.
1. Uma página de metadados é exibida na guia do seu navegador. Copie a URL do emissor do provedor de identidade (o valor para **"emissor"**).
   - Exemplo: ``https://login.fabrikam.com/011115c3-0113-4f43-b5e2-df01266e24ae/v2.0/``.
 
**OU**: para construir a mesma URL de metadados manualmente, execute as etapas a seguir.

1. Crie um URL do endereço de metadados no seguinte formato usando o locatário e a política B2C: ``https://<B2CTENANTNAME>.b2clogin.com/<B2CTENANTNAME>.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=<B2CSIGN-INPOLICY>``
    - Exemplo: ``https://d365plc.b2clogin.com/d365plc.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=B2C_1_signinup``.
1. Insira o URL do endereço de metadados na barra de endereço no navegador.
1. Nos metadados, copie o URL do emissor do provedor de identidade (valor para **"emissor"**).
    - Exemplo: ``https://login.fabrikam.com/011115c3-0113-4f43-b5e2-df01266e24ae/v2.0/``.

## <a name="configure-your-b2c-tenant-in-commerce-site-builder"></a>Configurar o locatário B2C no construtor de sites do Commerce

Após configurar o locatário B2C do Azure AD, será necessário configurar o locatário B2C no construtor de sites do Commerce. As etapas de configuração incluem coletar informações do aplicativo B2C do portal do Azure, inserir as informações do aplicativo B2C no construtor de sites e associar o aplicativo B2C ao site e ao canal.

### <a name="collect-the-required-application-information"></a>Coletar as informações necessárias do aplicativo

Para coletar as informações necessárias do aplicativo, siga estas etapas.

1. No portal do Azure, vá para **Página Inicial \> B2C do Azure AD – Aplicativos**,
1. Selecione o aplicativo e, no painel de navegação à esquerda, selecione **Propriedades** para obter os detalhes do aplicativo.
1. Na caixa **ID do Aplicativo**, colete a ID do aplicativo B2C criado no seu locatário B2C. Posteriormente, ela será inserida como **GUID do Cliente** no construtor de sites.
1. Em **URL de resposta**, colete o URL de resposta.
1. Vá para **Página Inicial \> B2C do Azure AD – Fluxos de usuário (políticas)** e colete os nomes de cada política de fluxo de usuário.

A imagem a seguir mostra um exemplo da página **B2C do Azure AD – Aplicativos**.

![Navegue até o Aplicativo B2C no locatário.](./media/B2CImage_19.png)

A imagem a seguir mostra um exemplo da página **Propriedades** de um aplicativo no B2C do Azure AD. 

![Copiar a ID do Aplicativo nas Propriedades do Aplicativo B2C.](./media/B2CImage_21.png)

A imagem a seguir mostra um exemplo de políticas de fluxo de usuário na página **B2C do Azure AD – Fluxos de usuário (políticas)**.

![Coletar os nomes de cada fluxo de política de B2C.](./media/B2CImage_22.png)

### <a name="enter-your-aad-b2c-tenant-application-information-into-commerce"></a>Insira as informações do aplicativo locatário B2C do AAD no Commerce

Insira os detalhes do locatário B2C do Azure AD no construtor de sites do Commerce antes de associar o locatário B2C aos sites.

Para adicionar as informações do aplicativo locatário B2C do AAD ao Commerce, siga estas etapas.

1. Faça login como administrador no construtor de sites do Commerce no seu ambiente.
1. No painel de navegação esquerdo, selecione **Configurações de Locatário** para expandi-lo.
1. Em **Configurações do Locatário**, selecione **Configurações do B2C**. 
1. Na janela principal ao lado de **Aplicativos B2C**, selecione **Gerenciar**. (Se o locatário aparecer na lista de Aplicativos B2C, ele já foi adicionado por um administrador. Verifique se os itens na etapa 6 abaixo correspondem ao Aplicativo B2C.)
1. Selecione **Adicionar Aplicativo B2C**.
1. Insira os seguintes itens obrigatórios no formulário exibido usando valores do locatário e aplicativo B2C. Os campos que não são obrigatórios (sem um asterisco) podem ser deixados em branco.

    - **Nome do Aplicativo**: O nome do Aplicativo B2C, por exemplo, "Fabrikam B2C".
    - **Nome do locatário**: O nome de seu locatário B2C (por exemple, use "fabrikam" se o domínio aparecer como "fabrikam.onmicrosoft.com" para o locatário B2C). 
    - **ID da Política de Esquecer Senha**: A ID da política de fluxo de usuário de esquecer senha, por exemplo, "B2C_1_PasswordReset".
    - **ID da Política de Inscrição e Logon**: A ID da política do fluxo de usuário de inscrição e logon, por exemplo "B2C_1_signup_signin".
    - **GUID do Cliente**: A ID do aplicativo B2C, por exemplo "22290eb2-c52e-42e9-8b35-a2b0a3bcb9e6".
    - **ID da Política de Editar Perfil**: A ID da política do fluxo de usuário de edição de perfil, por exemplo "B2C_1A_ProfileEdit".

1. Selecione **OK**. Agora você verá o nome do aplicativo B2C aparecer na lista.
1. Selecione **Salvar** para salvar as alterações.

### <a name="associate-the-b2c-application-to-your-site-and-channel"></a>Associar o aplicativo B2C ao site e ao canal

> [!WARNING]
> Se o site já estiver associado a um aplicativo B2C, alterar para outro aplicativo B2C removerá as referências atuais estabelecidas para usuários já inscritos neste ambiente. Se for alterado, todas as credenciais associadas ao aplicativo B2C atualmente atribuído não estarão disponíveis para os usuários. 
> 
> Somente atualize o aplicativo B2C se estiver configurando o aplicativo B2C do canal pela primeira vez ou se quiser que os usuários se inscrevam novamente com novas credenciais neste canal com o novo aplicativo do B2C. Tenha cautela ao associar canais aos aplicativos B2C e nomeie os aplicativos de forma clara. Se um canal não estiver associado a um aplicativo B2C nas etapas abaixo, os usuários que fizerem logon nesse canal para o seu site serão inseridos no aplicativo B2C exibido como **padrão** na lista **Configurações do Locatário \> Configurações do B2C** de aplicativos B2C.

Para associar o aplicativo B2C ao site e ao canal, siga estas etapas.

1. Navegue até o seu site no construtor de sites do Commerce.
1. No painel de navegação esquerdo, selecione **Configurações de Site** para expandi-lo.
1. Abaixo de **Configurações do Site**, selecione **Canais**.
1. Na janela principal em **Canais**, selecione o seu canal.
1. No painel de propriedades do canal à direita, selecione o nome do aplicativo B2C no menu suspenso **Selecionar Aplicativo B2C**.
1. Selecione **Fechar** e, depois, selecione **Salvar e Publicar**.

## <a name="additional-b2c-information"></a>Informações adicionais do B2C

### <a name="customer-migration"></a>Migração de clientes

Se você estiver considerando migrar registros de clientes de uma plataforma de provedor de identidade anterior, trabalhe em conjunto com a equipe do Dynamics 365 Commerce para revisar as suas necessidades de migração de clientes.

Para obter documentação adicional do B2C do Azure AD sobre migração de clientes, consulte [Migrar usuários para o B2C do Azure Active Directory](/azure/active-directory-b2c/active-directory-b2c-user-migration).

### <a name="custom-policies"></a>Políticas personalizadas

Para obter informações adicionais sobre como personalizar fluxos de interações e políticas do B2C do Azure AD fora do escopo oferecido por políticas padrão do B2C, consulte [Políticas personalizadas no B2C do Azure Active Directory](/azure/active-directory-b2c/active-directory-b2c-overview-custom). 

### <a name="secondary-admin"></a>Administrador secundário

Uma conta de administrador ideal secundária pode ser adicionada à seção **Usuários** do locatário B2C. Pode ser uma conta direta ou uma conta geral. Caso precise compartilhar uma conta entre os recursos da equipe, uma conta comum também poderá ser criada. Devido à confidencialidade dos dados armazenados no B2C do Azure AD, uma conta comum deverá ser monitorada rigorosamente de acordo com as práticas de segurança da empresa.

## <a name="additional-resources"></a>Recursos adicionais

[Configurar seu nome de domínio](configure-your-domain-name.md)

[Implantar um novo locatário de comércio eletrônico](deploy-ecommerce-site.md)

[Criar um site de comércio eletrônico](create-ecommerce-site.md)

[Associar um site do Dynamics 365 Commerce a um canal online](associate-site-online-store.md)

[Gerenciar arquivos robots.txt](manage-robots-txt-files.md)

[Carregar redirecionamentos de URL em massa](upload-bulk-redirects.md)

[Configurar páginas personalizadas para logons dos usuários](custom-pages-user-logins.md)

[Configurar múltiplos locatários B2C em um ambiente do Commerce](configure-multi-B2C-tenants.md)

[Adicionar suporte para uma rede de entrega de conteúdo (CDN)](add-cdn-support.md)

[Habilitar detecção de lojas com base na localização](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
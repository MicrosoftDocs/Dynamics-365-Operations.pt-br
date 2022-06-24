---
title: Configurar páginas personalizadas para entradas dos usuários
description: Este artigo descreve como criar páginas personalizadas no Microsoft Dynamics 365 Commerce que lidem com entradas personalizadas para usuários nos locatários de B2C do Azure Active Directory (Azure AD).
author: brianshook
ms.date: 03/17/2021
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
ms.openlocfilehash: 2c610866b896ef7648d2596e17b51d1935a78dee
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8880331"
---
# <a name="set-up-custom-pages-for-user-sign-ins"></a>Configurar páginas personalizadas para entradas dos usuários

[!include [banner](includes/banner.md)]

Este artigo descreve como criar páginas personalizadas no Microsoft Dynamics 365 Commerce que lidem com entradas personalizadas para usuários nos locatários de B2C do Azure Active Directory (Azure AD).

Para usar as páginas personalizadas criadas no Dynamics 365 Commerce para manipular fluxos de inscrições de usuário, você deve configurar as políticas do Azure AD que serão referenciadas no ambiente de comércio. Você pode configurar as políticas B2C "Se inscrever e entrar," "Edição de perfil," e "Redefinição de senha" Azure AD usando o aplicativo B2C do Azure AD. O locatário B2C do Azure AD e nomes de política podem ser referenciados durante o processo de provisionamento feito para o ambiente de comércio usando Microsoft Dynamics Lifecycle Services (LCS).

As páginas personalizadas do Commerce podem ser criadas usando conectar, inscrever, edição de perfil da conta, redefinição de senha ou módulos AAD genéricos. As URLs da página publicadas para essas páginas personalizadas devem ser referenciadas nas configurações de política do Azure AD B2C no portal do Azure.

> [!WARNING] 
> O Azure AD B2C removerá os fluxos de usuário antigos (herdados) em 1º de agosto de 2021. Portanto, você deve planejar a migração dos fluxos de usuário para a nova versão recomendada. A nova versão oferece paridade de recursos e novos recursos. Para obter mais informações, consulte [Fluxos de usuário no Azure Active Directory B2C](/azure/active-directory-b2c/user-flow-overview).

>A biblioteca de módulos do Commerce versão 10.0.15 ou superior deve ser usada com os fluxos de usuário de B2C recomendados. As páginas da política de usuário padrão oferecidas no Azure AD B2C também podem ser usadas e permitem alterações de imagem de plano de fundo, logotipo e cor de plano de fundo relacionadas à identidade visual da empresa. Embora seja mais limitado em recursos de design, as páginas de política de usuário padrão fornecem a funcionalidade de política do Azure AD B2C, sem criar e configurar páginas personalizadas dedicadas. 

## <a name="set-up-b2c-policies"></a>Configurar políticas B2C

Depois de ter configurado seu locatário B2C Azure AD e associá-lo com seu ambiente de comércio, Acesse a página **Azure AD B2C** no portal do Azure e depois, no menu, em **Políticas**, selecione **Fluxos de usuário (políticas)**.

![Comando fluxos de usuário (políticas) no menu.](./media/B2C_CustomPage_PoliciesMenu.png)

Agora você pode configurar fluxos de entrada de usuário de "Se inscrever e entrar," "Edição de perfil," e "Redefinição de senha".

### <a name="configure-the-sign-up-and-sign-in-policy"></a>Configurar a política "Se inscrever e entrar"

Para configurar a política ""Se inscrever e entrar", siga estas etapas.

1. Selecione **Novo fluxo do usuário**, selecione **Inscrever-se e entrar**, selecione a guia **Recomendado** e selecione **Criar**.
1. Insira um nome para a política (por exemplo, **B2C\_1\_SignInSignUp**).
1. Na seção **Provedores de Identidade**, selecione os provedores de identidade para usar a política. Ao mínimo, **Inscrição por e-mail** deve estar selecionado.
1. Na coluna **Coletar atributo**, marque as caixas de seleção **Endereço de e-mail**, **Nome fornecido** e **Sobrenome**.
1. Na coluna **Retornar reivindicação**, marque as caixas de seleção **Endereços de e-mail**, **Nome fornecido**, **Provedor de identidade**, **Sobrenome** e **ID do objeto de usuário**.

    ![Atributos e reivindicações selecionados.](./media/B2C_SignInSignUp_Attributes.png)

1. Selecione **OK** para criar a política.
1. Clique duas vezes no nome da política, e depois no painel de navegação, selecione **Propriedades**.
1. Defina a opção **Habilitar layout de página garantindo JavaScript (visualização)** como **Ligado**.

    ![As páginas de propriedade da nova política.](./media/B2C_SignInSignUp_EnableJavascript.png)

> [!NOTE]
> O nome da política será referenciado por completo no ambiente de comércio. (O prefixo **B2C\_1\_** será incluído na referência.) Políticas não podem ser renomeadas após serem criadas. Se você está substituindo uma política existente para seu ambiente de comércio, você pode excluir a política original e criar uma nova política que tem o mesmo nome. Alternativamente, se o ambiente já foi provisionado, você pode enviar o novo nome de política por meio de solicitação de serviço.

Você retornará a esta política para concluir a configuração depois de criar páginas personalizadas. Por hora, feche a política para retornar à página **Fluxos de usuário (políticas)** no portal do Azure.

### <a name="configure-the-profile-editing-policy"></a>Configurar a política "Edição de perfil"

Para configurar a política "Edição de perfil", siga as etapas a seguir.

1. Selecione **Novo fluxo do usuário**, selecione **Edição de perfil**, selecione a guia **Recomendado** e selecione **Criar**.
1. Insira um nome para a política (por exemplo, **B2C\_1\_EditProfile**).
1. Na seção **Provedores de Identidade**, selecione os provedores de identidade para usar a política. Ao mínimo, **Inscrição de conta local** deve estar selecionado.
1. Na coluna **Coletar atributo**, marque as caixas de seleção **Nome Fornecido** e **Sobrenome**.
1. Na coluna **Retornar reivindicação**, marque as caixas de seleção **Endereços de e-mail**, **Nome fornecido**, **Provedor de identidade**, **Sobrenome** e **ID do objeto de usuário**.
1. Selecione **OK** para criar a política.
1. Clique duas vezes no nome da política, e depois no painel de navegação, selecione **Propriedades**.
1. Defina a opção **Habilitar layout de página garantindo JavaScript (visualização)** como **Ligado**.

Você retornará a esta política para concluir a configuração depois de criar páginas personalizadas. Por hora, feche a política para retornar à página **Fluxos de usuário (políticas)** no portal do Azure.

### <a name="configure-the-password-reset-policy"></a>Configurar a política "Redefinir senha"

Para configurar a política "Redefinir senha", siga as etapas a seguir.

1. Selecione **Novo fluxo de usuário** e selecione a opção **Redefinição de senha**, escolha a guia **Recomendado** e clique em **Criar**.
1. Insira um nome para a política (por exemplo, **B2C\_1\_ForgetPassword**).
1. Na seção **Provedores de Identidade**, selecione **Redefinir senha usando endereço de e-mail**.
1. Na coluna **Retornar reivindicação**, marque as caixas de seleção **Endereços de e-mail**, **Nome fornecido**, **Sobrenome** e **ID do objeto de usuário**.
1. Selecione **OK** para criar a política.
1. Clique duas vezes no nome da política, e depois no painel de navegação, selecione **Propriedades**.
1. Defina a opção **Habilitar layout de página garantindo JavaScript (visualização)** como **Ligado**.

Você retornará a esta política para concluir a configuração depois de criar páginas personalizadas. Por hora, feche a política para retornar à página **Fluxos de usuário (políticas)** no portal do Azure.

## <a name="build-the-custom-pages"></a>Criar as páginas personalizadas

Os módulos Azure AD dedicados são incluídos no Commerce para criar páginas personalizadas para políticas do usuário do Azure AD B2C. As páginas podem ser criadas especificamente para o layout de cada página da política do usuário usando os principais módulos do Azure AD B2C detalhados a seguir. Como alternativa, o módulo **AAD Genéricos** pode ser usado para todos os layouts e políticas de página no Azure AD B2C (mesmo para as opções de layout de página em políticas não listadas abaixo). 

- Os módulos específicos da página do Azure AD são vinculados a itens de entrada de dados processados pelo Azure AD B2C. Esses módulos fornecem mais controle sobre o posicionamento dos elementos em suas páginas. No entanto, mais páginas e extensões de módulo talvez precisem ser criadas para conta para variações além das configurações padrão descritas abaixo.
- O módulo **Genérico AAD** cria o elemento "div" para que Azure AD B2C processe todos os elementos no layout de página de política de usuário, proporcionando mais flexibilidade às funções B2C da página, mas menos controle do posicionamento e do estilo (embora CSS possa ser usado para corresponder à aparência do seu site).

Você pode criar uma única página com o módulo **Genérico AAD** e usá-la para todas as páginas de política de usuário ou pode criar páginas específicas usando os módulos individuais Azure AD para entrada, inscrição, edição de perfil, redefinição de senha e verificação de redefinição de senha. Você também pode usar uma combinação de ambos, usando as Azure AD páginas específicas dos layouts de página indicados abaixo e a página módulo de AAD genérico dos layouts de página restantes nessas páginas ou em outras políticas de usuário.

Para saber mais sobre os Módulos do Azure AD fornecidos com a biblioteca de módulos, leia mais em [Páginas e módulos de gerenciamento de identidades](identity-mgmt-modules.md).

Para criar as páginas personalizadas com módulos de identidade específicos para lidar com credenciais de usuários, siga estas etapas.

1. No construtor de sites do Commerce, navegue até o seu site.
1. Crie os cinco modelos e páginas a seguir (caso ainda não estejam presentes no site):
    - Um modelo de **Entrada** e página que usa o módulo de entrada.
    - Um modelo de **Inscrição** e página que usa o módulo de inscrição.
    - Um modelo e a página para **Redefinir senha** que usa o módulo para redefinir senha.
    - Um modelo e a página para **Verificação para redefinir senha** que usa o módulo de verificação para redefinir senha.
    - Um modelo e página **Edição de Perfil** que usa o módulo de edição do perfil da conta.

Quando você cria páginas, siga estas diretrizes:

- Para cada página ou módulo, use o layout e estilo que melhor atende aos seus requisitos de empresa.
- Publicar todas as páginas e URLs que devem ser usadas na configuração do Azure AD B2C.
- Após as páginas e URLs serem publicadas, colete as URLs que devem ser usadas para configurações da política Azure AD B2C. Um sufixo **?preloadscripts=true** será adicionado a cada URL quando é usado.

> [!IMPORTANT]
> As páginas criadas para serem referenciadas no Azure AD B2C são servidas diretamente do domínio do locatário do Azure AD B2C. Não reutilize cabeçalhos e rodapés universais com links relacionados. Como essas páginas estão hospedadas no domínio Azure AD B2C quando são usadas, apenas URLs absolutas devem ser usadas para todos os links. É recomendável criar um cabeçalho e um rodapé específicos com URLs absolutas para suas páginas personalizadas relacionadas do Azure AD, com todos os módulos específicos do Commerce que exigem conexão com o Retail Service removido. Por exemplo, os módulos favoritos, barra de pesquisa, link de entrada e carrinho não devem ser incluídos em páginas que serão usadas nos fluxos de usuário do Azure AD B2C.

## <a name="configure-azure-ad-b2c-policies-with-custom-page-information"></a>Configurar políticas Azure AD B2C com informações de página personalizadas 

No portal do Azure, volte à página do **Azure AD B2C** e depois no menu, em **Políticas**, selecione **Fluxos de usuário (políticas)**.

### <a name="update-the-sign-up-and-sign-in-policy-with-custom-page-information"></a>Atualizar a política "Se inscrever e entrar" com informações de página personalizadas

Para atualizar a política "Se inscrever e entrar" com informações de página personalizadas, siga estas etapas.

1. Na política **Se inscrever e entrar** que você configurou anteriormente, no painel de navegação, selecione **Layouts de página**.
1. Selecione o layout **Unificar entrada ou inscrição na página**.
1. Defina a opção **Usar conteúdo de página personalizado** como **Sim**.
1. No campo **URL de página personalizada**, insira a URL de entrada completa. Inclua o sufixo **?preloadscripts=true**. Por exemplo, insira ``www.<my domain>.com/sign-in?preloadscripts=true``.
1. No campo **Versão de Layout de Página**, selecione versão **2.1.0** ou posterior (requer biblioteca de módulos para versão 10.0.15 ou superior do Commerce).
1. Selecione **Salvar**.
1. Selecione o layout **Página de inscrição de conta local**.
1. Defina a opção **Usar conteúdo de página personalizado** como **Sim**.
1. No campo **URL de página personalizada**, insira a URL de entrada completa. Inclua o sufixo **?preloadscripts=true**. Por exemplo, insira ``www.<my domain>.com/sign-up?preloadscripts=true``.
1. No campo **Versão de Layout de Página**, selecione versão **2.1.0** ou posterior (requer biblioteca de módulos para versão 10.0.15 ou superior do Commerce).
1. Na seção **Atributos de usuário**, siga estas etapas:
    1. Para os atributos **Nome Fornecido** e **Sobrenome**, selecione **Não** na coluna **Requer Verificação**.
    1. Para o atributo **Endereço de Email**, é recomendável deixar o valor padrão **Sim** selecionado na coluna **Requer Verificação**. Esta opção garante que os usuários que se inscrevem em um determinado endereço de email verifique se eles possuem o endereço de email.
    1. Para os atributos **Endereço de Email**, **Nome Fornecido** e **Sobrenome**, selecione **Não** na coluna **Opcional**.
1. Selecione **Salvar**.

    ![Configuração da política de página de inscrição de conta local.](./media/B2C_SignInSignUp_Recommended_PageLayoutExample.png)

### <a name="update-the-profile-editing-policy-with-custom-page-information"></a>Atualizar a política "Edição de perfil" com informações de página personalizadas

Para atualizar a política "Edição de perfil" com informações de página personalizadas, siga estas etapas.

1. Na política **Edição de perfil** que você configurou anteriormente, no painel de navegação, selecione **Layouts de página**.
1. Selecione o layout **Página de edição do perfil** (pode exigir a rolagem para baixo além das outras opções de layout, dependendo da tela).
1. Defina a opção **Usar conteúdo de página personalizado** como **Sim**.
1. No campo **URL de página personalizada**, insira a URL de edição de perfil completa. Inclua o sufixo **?preloadscripts=true**. Por exemplo, insira ``www.<my domain>.com/profile-edit?preloadscripts=true``.
1. Para **Versão de Layout de Página**, selecione versão **2.1.0** ou posterior (requer biblioteca de módulos para versão 10.0.15 ou superior do Commerce).
1. Na seção **Atributos de usuário**, siga estas etapas:
    1. Para os atributos **Nome** e **Sobrenome**, selecione **Não** na coluna **Opcional**.
    1. Para os atributos **Nome Fornecido** e **Sobrenome**, selecione **Não** na coluna **Requer verificação**.
1. Selecione **Salvar**.

### <a name="update-the-password-reset-policy-with-custom-page-information"></a>Atualizar a política "Redefinir senha" com informações de página personalizadas

Para atualizar a política "Redefinir senha" com informações de página personalizadas, siga estas etapas.

1. Na política **Redefinir senha** que você configurou anteriormente, no painel de navegação, selecione **Layouts de página**.
1. Selecione o layout da **página Esqueceu senha**.
1. Defina a opção **Usar conteúdo de página personalizado** como **Sim**.
1. No campo **URL de página personalizada**, insira a URL de verificação redefinição de senha completa. Inclua o sufixo **?preloadscripts=true**. Por exemplo, insira ``www.<my domain>.com/password-reset-verification?preloadscripts=true``.
1. No campo **Versão de Layout de Página**, selecione versão **2.1.0** ou posterior (requer biblioteca de módulos para versão 10.0.15 ou superior do Commerce).
2. Selecione **Salvar**.
3. Selecione o layout da **página Alterar senha**.
4. Defina a opção **Usar conteúdo de página personalizado** como **Sim**.
5. No campo **URL de página personalizada**, insira a URL de redefinição de senha completa. Inclua o sufixo **?preloadscripts=true**. Por exemplo, insira ``www.<my domain>.com/password-reset?preloadscripts=true``.
6. No campo **Versão de Layout de Página**, selecione versão **2.1.0** ou posterior (requer biblioteca de módulos para versão 10.0.15 ou superior do Commerce).
7. Selecione **Salvar**.

## <a name="customize-default-text-strings-for-labels-and-descriptions"></a>Personalizar caracteres de texto padrão e rótulos para descrições

Na biblioteca de módulos, os módulos de entrada são previamente preenchidos com caracteres de texto padrão para os rótulos e descrições. Você pode personalizar as cadeias de caracteres no painel de propriedades do módulo no qual está trabalhando. As cadeias de caracteres adicionais na página (como o link de **Esqueceu a senha?** ou o texto de chamada à ação **Criar uma conta**) exigirão o uso do kit de desenvolvimento de software (SDK) do Commerce e a atualização dos valores no arquivo global.json para o módulo de entrada.

Por exemplo, o texto padrão para o link de senha esquecida é **Esqueceu a senha?**. A seguir veja um texto padrão na página de entrada.

![Texto padrão para o link de senha esquecida na página de entrada.](./media/B2C_SignUp_ModuleFace.png)

No entanto, no arquivo global.json para o módulo de entrada da biblioteca de módulos, você pode editar o texto para **Esqueceu a senha?**, conforme mostrado na ilustração a seguir.

![Texto de link atualizado no arquivo global.json do módulo de entrada.](./media/B2C_CustomizingStringsForModule.png)

Depois de atualizar o arquivo global.json e publicar suas alterações, o novo texto de link será exibido no módulo de entrada no Commerce e na página de entrada ativa.

## <a name="additional-resources"></a>Recursos adicionais

[Configurar seu nome de domínio](configure-your-domain-name.md)

[Implantar um novo locatário de comércio eletrônico](deploy-ecommerce-site.md)

[Criar um site de comércio eletrônico](create-ecommerce-site.md)

[Associar um site do Dynamics 365 Commerce a um canal online](associate-site-online-store.md)

[Gerenciar arquivos robots.txt](manage-robots-txt-files.md)

[Carregar redirecionamentos de URL em massa](upload-bulk-redirects.md)

[Configurar um locatário B2C do Commerce](set-up-B2C-tenant.md)

[Configurar múltiplos locatários B2C em um ambiente do Commerce](configure-multi-B2C-tenants.md)

[Adicionar suporte para uma rede de entrega de conteúdo (CDN)](add-cdn-support.md)

[Habilitar detecção de lojas com base na localização](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
---
title: Configurar CPOS para usar um aplicativo Azure AD personalizado
description: Este artigo explica como configurar o PDV em Nuvem (CPOS) para usar um aplicativo Azure Active Directory (Azure AD) personalizado.
author: boycez
ms.date: 11/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: global
ms.author: boycez
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 5e4ff797410e1e94869cc37684e7622ec0d97842
ms.sourcegitcommit: 9e2e54ff7d15aa51e58309da3eb52366328e199d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2022
ms.locfileid: "9746251"
---
# <a name="configure-cpos-to-use-a-custom-azure-ad-app"></a>Configurar CPOS para usar um aplicativo Azure AD personalizado

[!include [banner](includes/banner.md)]

Por padrão, o PDV em Nuvem (CPOS) no Microsoft Dynamics 365 Commerce aponta para um aplicativo de terceiros da Microsoft registrado no Azure Active Directory (Azure AD). Portanto, você pode usar o CPOS sem precisar fazer alterações no Azure AD. No entanto, talvez você deseje apontar sua instância do CPOS para um aplicativo Azure AD personalizado que você controla. Este artigo explica como configurar o CPOS para usar um aplicativo Azure AD personalizado.

## <a name="set-up-a-custom-retail-server-app-in-azure-ad"></a>Configurar um aplicativo Retail Server personalizado no Azure AD

Para criar e configurar um aplicativo Retail Server personalizado no Azure AD, siga estas etapas.

1. Entre no [centro de administração do Azure Active Directory](https://aad.portal.azure.com) usando qualquer conta de usuário do Azure AD. A conta de usuário não precisa ter permissões de administrador.
1. Selecione **Azure Active Directory**.
1. Selecione **Registros de aplicativos** e, depois, selecione **Novo registro** para abrir a caixa de diálogo **Registrar um aplicativo**.
1. Defina os seguintes campos:

    - **Nome**: insira um nome personalizado para o aplicativo. Por exemplo, insira **Servidor de Varejo Personalizado**.
    - **Tipos de conta com suporte**: selecione a opção padrão, **Contas neste diretório organizacional somente (apenas a Microsoft - único locatário)**.
    - **URL de redirecionamento**: esse campo é opcional. Deixe-o em branco.
    - **ID da Árvore de Serviço**: esse campo é opcional. Deixe-o em branco.
    
1. Selecione **Registrar**. A página de configuração do aplicativo recém-registrado é exibida.
1. Na seção **Visão geral \> Fundamentos**, selecione **Adicionar um URI de ID do Aplicativo** e, depois, selecione **Definir** ao lado de **URI de ID do Aplicativo**. Anote o valor sugerido e selecione **Save** para aceitar esse valor. 
1. Selecione **Adicionar um escopo** e, depois, defina os seguintes campos:

    - **Nome do escopo**: insira um nome personalizado para o escopo. Por exemplo, insira **Legacy.Access.Full**.
    - **Quem pode consentir**: especifique se administradores e usuários ou somente administradores podem dar consentimento, com base nas políticas de segurança de sua organização.
    - **Nome de exibição do consentimento do administrador**: digite um nome de exibição. Por exemplo, insira **Acessar Servidor de Varejo**.
    - **Descrição de consentimento do administrador**: insira uma descrição. Por exemplo, insira **Dá acesso a APIs do Retail Server**.

1. Selecione **Adicionar escopo** para concluir o processo de criação de escopo.

## <a name="set-up-a-custom-cpos-app-in-azure-ad"></a>Configurar um aplicativo CPOS personalizado no Azure AD

> [!IMPORTANT]
> Se você estiver atualizando um aplicativo CPOS personalizado do Azure AD criado antes da versão 10.0.21 do Commerce, siga as etapas em [Atualizar um aplicativo CPOS personalizado do Azure AD existente criado antes da versão 10.0.21 do Commerce](#upgrade-an-existing-custom-cpos-azure-ad-app-created-before-commerce-version-10021).

Para criar e configurar um aplicativo CPOS personalizado no Azure AD, siga estas etapas.

1. Entre no [centro de administração do Azure Active Directory](https://aad.portal.azure.com) usando qualquer conta de usuário do Azure AD. A conta de usuário não precisa ter permissões de administrador.
1. Selecione **Azure Active Directory**.
1. Selecione **Registros de aplicativos** e, depois, selecione **Novo registro** para abrir a caixa de diálogo **Registrar um aplicativo**.
1. Defina os seguintes campos:

    - **Nome**: insira um nome do aplicativo. Por exemplo, insira **PDV em Nuvem Personalizado**.
    - **Tipos de conta com suporte**: selecione a opção padrão, **Contas neste diretório organizacional somente (apenas a Microsoft - único locatário)**.
    - **URI de redirecionamento**: selecione **Aplicativo de página única (SPA)** na lista suspensa e insira seu URI de CPOS.
    - **ID da Árvore de Serviço**: esse campo é opcional. Deixe-o em branco.

1. Selecione **Registrar**. A página de configuração do aplicativo recém-registrado é exibida.
1. Na seção **Manifesto**, defina os parâmetros **oauth2AllowIdTokenImplicitFlow** e **oauth2AllowImplicitFlow** como **verdadeiro** e selecione **Salvar**.
1. Na seção **Configuração do token**, siga estas etapas para adicionar duas declarações:

    1. Selecione **Adicionar declaração opcional**. Defina o campo **Tipo de token** como **ID** e selecione a declaração **sid**. Selecione **Adicionar**.
    1. Selecione **Adicionar declaração opcional**. Defina o campo **Tipo de token** como **Acesso** e selecione a declaração **sid**. Selecione **Adicionar**.

1. Na seção **Permissões de API**, selecione **Adicionar uma permissão**.
1. Na guia **APIs que minha organização utiliza**, procure o aplicativo Retail Server que você criou na seção [Configurar um aplicativo Retail Server personalizado no Azure AD](#set-up-a-custom-retail-server-app-in-azure-ad). Depois, selecione **Adicionar permissões**.
1. Na seção **Visão geral**, anote o valor no campo **ID do aplicativo (cliente)**.

### <a name="upgrade-an-existing-custom-cpos-azure-ad-app-created-before-commerce-version-10021"></a>Atualizar um aplicativo CPOS personalizado do Azure AD existente criado antes da versão 10.0.21 do Commerce

Para atualizar um aplicativo CPOS personalizado do Azure AD existente criado antes da versão 10.0.21 do Commerce, siga estas etapas. 

1. Abra seu aplicativo CPOS personalizado do Azure AD no portal do Azure.
1. Selecione a guia **Autenticação**.
1. Copie e salve o URI de redirecionamento original do tipo **Web** para uso posterior e, em seguida, exclua-o.
1. Selecione **Adicionar uma plataforma** e escolha **Aplicativo de página única (SPA)**.
1. Adicione o URI de redirecionamento Web original, copiado acima da plataforma SPA.
1. Na seção **Configuração do token**, siga estas etapas para adicionar duas declarações:
    1. Selecione **Adicionar declaração opcional**. Defina o campo **Tipo de token** como **ID** e selecione a declaração **sid**. Selecione **Adicionar**.
    1. Selecione **Adicionar declaração opcional**. Defina o campo **Tipo de token** como **Acesso** e selecione a declaração **sid**. Selecione **Adicionar**.

## <a name="update-the-cpos-configuration-file"></a>Atualize o arquivo de configuração CPOS

Abra o arquivo config.json do CPOS e faça as atualizações a seguir nele.

1. Substitua o valor de chave **AADClientId** pelo valor **ID do aplicativo (cliente)** do aplicativo CPOS personalizado que você criou na seção [Configurar um aplicativo CPOS personalizado no Azure AD](#set-up-a-custom-cpos-app-in-azure-ad).
1. Substitua o valor de chave **AADRetailServerResourceId** pelo valor **URI de ID do Aplicativo** do aplicativo Retail Server personalizado que você criou na seção [Configurar um aplicativo Retail Server personalizado no Azure AD](#set-up-a-custom-retail-server-app-in-azure-ad).

O CPOS usará os dois parâmetros quando enviar solicitações ao Azure AD para adquirir um token de segurança.

## <a name="update-identity-providers-settings-in-commerce-headquarters"></a>Atualizar configurações de provedores de identidade no Commerce headquarters

Depois, você deve atualizar configurações de provedores de identidade no Commerce headquarters.

1. No Commerce headquarters, abra a página **Parâmetros compartilhados com o Commerce**.
1. Na guia **Provedores de Identidade**, na seção **Provedores de identidade**, selecione a linha em que o campo **Tipo** está definido como **Azure Active Directory** e o campo **Emissor** aponta para o locatário do Azure AD. Esta configuração declara que você trabalhará com grades filhas que contêm os dados relacionados ao provedor de identidade que corresponde ao locatário do Azure AD.
1. Na seção **Participantes confiáveis**, selecione **Adicionar** para adicionar uma linha.
1. Defina os seguintes campos:

    - **ClientId**: insira o valor **ID do aplicativo (cliente)** do aplicativo CPOS personalizado que você criou na seção [Configurar um aplicativo CPOS personalizado no Azure AD](#set-up-a-custom-cpos-app-in-azure-ad).
    - **Tipo**: selecione **Público**.
    - **UserType**: selecione **Trabalhador**.

1. Selecione a linha que você adicionou. A seção **IDs do Recurso de Servidor** abaixo da seção **Participantes Confiáveis** mostra as IDs do aplicativo Retail Server que podem ser acessadas pelo aplicativo que você selecionou na grade **Participantes Confiáveis**.
1. Na seção **IDs do Recurso de Servidor**, selecione **Adicionar** para adicionar uma linha.
1. No campo **Id do Recurso de Servidor**, insira o valor **URI de ID do Aplicativo** do aplicativo Retail Server personalizado que você criou na seção [Configurar um aplicativo Retail Server personalizado no Azure AD](#set-up-a-custom-retail-server-app-in-azure-ad).

    > [!IMPORTANT]
    > Todos os campos citados nas etapas anteriores diferenciam maiúsculas de minúsculas. Os valores inseridos devem coincidir exatamente com os valores configurados na central de administração do Azure AD.

1. Acesse **TI de Varejo e Comércio \> Agenda de distribuição** e execute o trabalho **1110** (**Configuração global**).

Agora você pode ativar os dispositivos CPOS usando seu próprio aplicativo Azure AD.

## <a name="additional-resources"></a>Recursos adicionais

[Ativação do dispositivo de ponto de venda (PDV)](dev-itpro/retail-device-activation.md)

[Gerenciar contas de ativação e dispositivos de validação](set-up-activation-accounts-validate-devices-hq.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]

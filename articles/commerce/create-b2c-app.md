---
title: Criar um aplicativo de B2C
description: Este artigo descreve como criar um aplicativo de business-to-consumer (B2C) no portal do Microsoft Azure.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: d8956d51bac7bf2a162a370ae5ef1c7e7cdc1e2f
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785213"
---
# <a name="create-a-b2c-application"></a>Criar um aplicativo de B2C

[!include [banner](includes/banner.md)]

Este artigo descreve como criar um aplicativo de business-to-consumer (B2C) no portal do Microsoft Azure.

Depois que seu locatário B2C tiver sido criado, você criará um aplicativo B2C dentro do novo locatário do Azure Active Directory (Azure AD) para interagir com o Commerce.

Para criar o aplicativo B2C, siga estas etapas.

1. No portal do Azure, selecione **Registros de aplicativo** e, em seguida, selecione **Novo registro**.
1. Em **Nome**, insira o nome a ser dado a este aplicativo do Azure AD B2C.
1. Em **Tipos de conta com suporte**, selecione **Contas em qualquer provedor de identidade ou diretório organizacional (para autenticar usuários com fluxos de usuário)**.
1. Para **URI de Redirecionamento**, insira suas URLs de resposta dedicadas como o tipo **Web**. Para obter informações sobre URLs de resposta e como formatá-las, consulte [URLs de resposta](#reply-urls) abaixo. Um URI de redirecionamento/URL de resposta deve ser inserido para habilitar redirecionamentos do Azure AD B2C de volta ao seu site quando um usuário é autenticado. A URL de resposta pode ser adicionada durante o processo de registro ou pode ser adicionada posteriormente selecionando o link **Adicionar uma URI de Redirecionamento** no menu **Visão geral** na seção **Visão Geral** do aplicativo B2C.
1. Para **Permissões**, selecione **Conceder consentimento do administrador para permissões OpenID e offline_access**.
1. Selecione **Registrar**.
1. Selecione o aplicativo recém-criado e navegue até o menu **Autenticação**. 
1. Se for inserida uma URL de resposta, em **Concessão implícita e fluxos híbridos** selecione as opções de **Tokens de acesso** e **Tokens de ID** para habilitá-los para o aplicativo e selecione **Salvar**. Se uma URL de resposta não foi inserida durante o registro, ela também pode ser adicionada à página, selecionando **Adicionar uma plataforma**, selecionando **Web** e inserindo o URI de redirecionamento do aplicativo. A seção **Concessão implícita e fluxos híbridos** estará disponível para selecionar as opções **Tokens de acesso** e **Tokens de ID**.
1. Acesse o menu **Visão geral** do portal do Azure e copie a **ID do aplicativo (cliente)**. Anote essa ID para as etapas de configuração posteriores (mencionadas posteriormente como a **GUID do Cliente**).

Para obter referência adicional sobre os Registros de Aplicativo no Azure AD B2C, consulte [A nova experiência de Registros de aplicativos para o Azure Active Directory B2C](/azure/active-directory-b2c/app-registrations-training-guide)

### <a name="reply-urls"></a>URLs de resposta

As URLs de resposta são importantes, pois permitem uma lista de domínios de retorno quando o seu site chamar o B2C do Azure AD para autenticar um usuário. Isto permite o retorno do usuário autenticado para o domínio a partir do qual estão tentando fazer o logon (domínio do seu site). 

Na caixa **URL de resposta** na tela **B2C do Azure AD – Aplicativos \> Novo aplicativo**, será necessário adicionar linhas separadas ao domínio do site e (após o ambiente ser provisionado) à URL gerada pelo Commerce. Essas URLs devem sempre usar um formato de URL válido e devem ser somente URLs base (sem barras ou caminhos à direita). A string ``/_msdyn365/authresp`` precisará ser inserida às URLs base, como nos seguintes exemplos.

- ``https://www.fabrikam.com/_msdyn365/authresp`` (O domínio deve corresponder completamente ao domínio de comércio eletrônico. Se você tiver vários domínios, precisará adicionar esta URL para cada um deles.)
- ``https://fabrikam-prod.commerce.dynamics.com/_msdyn365/authresp``

## <a name="next-steps"></a>Próximas etapas

Para continuar o processo de configuração de um locatário de B2 no Commerce, acesse [Criar políticas de fluxo de usuário](create-user-flow-policies.md).

## <a name="additional-resources"></a>Recursos adicionais

[Configurar um locatário B2C do Commerce](set-up-b2c-tenant.md)

[Criar ou vincular a um locatário existente do Azure AD B2C no portal do Azure](create-link-aad-b2c-tenant.md)

[Criar políticas de fluxo de usuário](create-user-flow-policies.md)

[Adicionar provedores de identidade social (Opcional)](add-social-identity-providers.md)

[Atualizar o Commerce headquarters com as novas informações de B2C do Azure AD](update-hq-aad-b2c-info.md)

[Configurar o locatário B2C no construtor de sites do Commerce](config-b2c-tenant-site-builder.md)

[Informações adicionais do B2C](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

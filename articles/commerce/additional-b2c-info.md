---
title: Informações adicionais do B2C
description: Este artigo mostra mais informações sobre como configurar o locatário business-to-consumer (B2C) no Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 11/14/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: b60ef15544cd30c44968ee7a588a8a9fb08e8223
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785211"
---
# <a name="additional-b2c-information"></a>Informações adicionais do B2C

[!include [banner](includes/banner.md)]

Este artigo mostra mais informações sobre como configurar o locatário business-to-consumer (B2C) no Microsoft Dynamics 365 Commerce.

### <a name="customer-migration"></a>Migração de clientes

Se você estiver considerando migrar registros de clientes de uma plataforma de provedor de identidade anterior, trabalhe em conjunto com a equipe do Dynamics 365 Commerce para revisar as suas necessidades de migração de clientes.

Para obter documentação adicional do B2C do Azure AD sobre migração de clientes, consulte [Migrar usuários para o B2C do Azure Active Directory](/azure/active-directory-b2c/active-directory-b2c-user-migration).

### <a name="custom-policies"></a>Políticas personalizadas

Para obter informações adicionais sobre como personalizar fluxos de interações e políticas do B2C do Azure AD fora do escopo oferecido por políticas padrão do B2C, consulte [Políticas personalizadas no B2C do Azure Active Directory](/azure/active-directory-b2c/active-directory-b2c-overview-custom). 

### <a name="secondary-admin"></a>Administrador secundário

Uma conta de administrador ideal secundária pode ser adicionada à seção **Usuários** do locatário B2C. Pode ser uma conta direta ou uma conta geral. Caso precise compartilhar uma conta entre os recursos da equipe, uma conta comum também poderá ser criada. Devido à confidencialidade dos dados armazenados no B2C do Azure AD, uma conta comum deverá ser monitorada rigorosamente de acordo com as práticas de segurança da empresa.

### <a name="set-up-a-custom-sign-in-domain"></a>Configurar um domínio de entrada personalizado

O Azure AD B2C permite configurar um domínio de entrada personalizado para o locatário do Azure AD B2C. Para obter instruções, consulte [Habilitar domínios personalizados para o Azure Active Directory B2C](/azure/active-directory-b2c/custom-domain). 

Se você usar um domínio de entrada personalizado, o domínio deverá ser inserido no construtor de sites do Commerce.

Para inserir um domínio de entrada personalizado no construtor de sites, siga estas etapas.

1. No canto superior direito do construtor de sites, selecione o seletor de sites e, em seguida, selecione **Gerenciar sites**.
1. No painel de navegação esquerdo, selecione **Configurações de locatário \> Configuração de autenticação no site**.
1. Na seção **Perfis de autenticação no site**, selecione **Gerenciar**.
1. No submenu à direita, selecione o botão **Editar** (símbolo de lápis) próximo ao perfil de autenticação no site para o qual você deseja inserir um domínio personalizado.
1. Na caixa de diálogo **Editar perfil de autenticação no site**, em **Domínio personalizado de entrada**, insira o seu domínio de entrada personalizado (por exemplo, "login.fabrikam.com").

> [!WARNING]
> Quando você atualiza para um domínio personalizado para o locatário do Azure AD B2C, a alteração afeta os detalhes do emissor do locatário para o token gerado. Os detalhes do emissor incluirão então o domínio personalizado em vez do domínio padrão fornecido pelo Azure AD B2C. Uma configuração de **Emissor** diferente no Commerce headquarters (**Varejo e Comércio \> Configuração do headquarters \> Parâmetros \> Parâmetros compartilhados do Commerce \> Provedores de Identidade**) altera a interação do sistema com os usuários do site, potencialmente criando um novo registro de cliente se um usuário estiver autenticando no novo emissor. Todas as alterações de domínio personalizadas devem ser testadas completamente antes de passarem para o domínio personalizado em um ambiente ativo do Azure AD B2C.

## <a name="additional-resources"></a>Recursos adicionais

[Configurar um locatário B2C do Commerce](set-up-b2c-tenant.md)

[Criar ou vincular a um locatário existente do Azure AD B2C no portal do Azure](create-link-aad-b2c-tenant.md)

[Criar o aplicativo B2C](create-b2c-app.md)

[Criar políticas de fluxo de usuário](create-user-flow-policies.md)

[Adicionar provedores de identidade social (Opcional)](add-social-identity-providers.md)

[Atualizar o Commerce headquarters com as novas informações de B2C do Azure AD](update-hq-aad-b2c-info.md)

[Configurar o locatário B2C no construtor de sites do Commerce](config-b2c-tenant-site-builder.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

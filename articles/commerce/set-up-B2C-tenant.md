---
title: Configurar um locatário B2C do Commerce
description: Este artigo descreve como configurar os locatários business-to-consumer (B2C) do Azure Active Directory (Azure AD) para a autenticação do site de usuário no Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: 3421dd3d67198a99ac236a56cbb4f300cb591a03
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785118"
---
# <a name="set-up-a-b2c-tenant-in-commerce"></a>Configurar um locatário B2C do Commerce

[!include [banner](includes/banner.md)]

Este artigo descreve como configurar os locatários business-to-consumer (B2C) do Azure Active Directory (Azure AD) para a autenticação do site de usuário no Dynamics 365 Commerce.

O Dynamics 365 Commerce usa o B2C do Azure AD para oferecer suporte aos fluxos de credenciais e autenticação de usuário. Um usuário pode se inscrever, acessar e redefinir a senha por meio desses fluxos. O B2C do Azure AD armazena informações confidenciais de autenticação do usuário, como nome de usuário e senha. O registro de usuário no locatário B2C armazenará um registro de conta local B2C ou um registro de provedor de identidade social B2C. Esses registros de B2C serão vinculados ao registro do cliente no ambiente do Commerce.

> [!WARNING] 
> O Azure AD B2C removerá os fluxos de usuário antigos (herdados) em 1º de agosto de 2021. Portanto, você deve planejar a migração dos fluxos de usuário para a nova versão recomendada. A nova versão oferece paridade de recursos e novos recursos. A biblioteca de módulos do Commerce versão 10.0.15 ou superior deve ser usada com os fluxos de usuário de B2C recomendados. Para obter mais informações, consulte [Fluxos de usuário no Azure Active Directory B2C](/azure/active-directory-b2c/user-flow-overview).
 
 > [!NOTE]
 > Os ambientes de avaliação do Commerce vêm com um locatário do Azure AD B2C pré-carregado para fins de demonstração. Carregar seu próprio locatário do Azure AD B2C usando as etapas abaixo não será necessário para ambientes de avaliação.

> [!TIP]
> Você pode proteger ainda mais os usuários do site e aumentar a segurança dos locatários do Azure AD B2C com a Proteção de Identidade e o Acesso Condicional do Azure AD. Para examinar os recursos disponíveis para locatários do Azure AD B2C Premium P1 e Premium P2, consulte [Proteção de Identidade e Acesso Condicional para o Azure AD B2C](/azure/active-directory-b2c/conditional-access-identity-protection-overview).

## <a name="dynamics-environment-prerequisites"></a>Pré-requisitos do ambiente do Dynamics

Antes de começar, verifique se o seu ambiente do Dynamics 365 Commerce e o canal de comércio eletrônico estão configurados adequadamente ao atender aos pré-requisitos a seguir.

- Defina o valor de **AllowAnonymousAccess** de operações POS como "1" no Commerce headquarters:
    1. Acesse **Operações de PDV**.
    1. Na grade de operações, clique com o botão direito do mouse e selecione **Personalizar**.
    1. Selecione **Adicionar um campo**.
    1. Na lista de colunas disponíveis, selecione a coluna **AllowAnonymousAccess** para adicioná-la.
    1. Selecione **Atualizar**.
    1. Para a operação de "adição de Cliente" **612**, altere **AllowAnonymousAccess** para "1."
    1. Execute o trabalho **1090 (Registradoras)**.
- Defina o atributo **Manual** da conta de cliente de sequência numérica como **Não** no Commerce headquarters:
    1. Acesse **Retail e Commerce \> Configuração do headquarters \> Parâmetros \> Parâmetros de Contas a receber**.
    1. Selecione **Sequências numéricas**.
    1. Na linha **Conta do cliente**, clique duas vezes no valor de **Código de sequência numérica**.
    1. Na Guia Rápida **Geral** da sequência numérica, defina **Manual** como **Não**.

Após a implantação do seu ambiente do Dynamics 365 Commerce, também será recomendável [Inicializar os dados de propagação](enable-configure-retail-functionality.md) no ambiente.

## <a name="next-steps"></a>Próximas etapas

Para continuar o processo de configuração de um locatário B2C no Commerce, prossiga para [Configurar seu locatário B2C existente do Azure AD no portal do Azure](create-link-aad-b2c-tenant.md).

## <a name="additional-resources"></a>Recursos adicionais

[Criar ou vincular a um locatário existente do Azure AD B2C no portal do Azure](create-link-aad-b2c-tenant.md)

[Criar o aplicativo B2C](create-b2c-app.md)

[Criar políticas de fluxo de usuário](create-user-flow-policies.md)

[Adicionar provedores de identidade social (Opcional)](add-social-identity-providers.md)

[Atualizar o Commerce headquarters com as novas informações de B2C do Azure AD](update-hq-aad-b2c-info.md)

[Configurar o locatário B2C no construtor de sites do Commerce](config-b2c-tenant-site-builder.md)

[Informações adicionais do B2C](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

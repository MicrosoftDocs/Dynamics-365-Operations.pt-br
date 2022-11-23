---
title: Criar ou vincular a um locatário do Azure AD B2C no portal do Azure
description: Este artigo descreve como criar ou vincular um locatário existente de business-to-consumer (B2C) do Azure Active Directory (Azure AD) no portal do Microsoft Azure.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: 0aa12387f00ffc3dd10688c6385c7952f089ab12
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785214"
---
# <a name="create-or-link-to-an-existing-azure-ad-b2c-tenant-in-the-azure-portal"></a>Criar ou vincular a um locatário do Azure AD B2C no portal do Azure

[!include [banner](includes/banner.md)]

Este artigo descreve como criar ou vincular um locatário de business-to-consumer (B2C) do Azure Active Directory (Azure AD) no portal do Microsoft Azure. Para obter mais informações, consulte [Tutorial: Criar um locatário do Azure Active Directory B2C](/azure/active-directory-b2c/tutorial-create-tenant).

Para criar ou vincular um locatário existente de B2C do Azure AD no portal do Azure, siga estas etapas.

1. Entre no [portal do Azure](https://portal.azure.com/).
1. No menu do portal do Azure, selecione **Criar um recurso**. Certifique-se de usar a assinatura e o diretório que será conectado ao ambiente do Commerce.

    ![Criar um Recurso no Portal do Azure.](./media/B2CImage_1.png)

1. Acesse **Identidade \> B2C do Azure Active Directory**.
1. Na página **Criar Locatário B2C ou Vincular a um Locatário existente**, use uma das opções abaixo que melhor atende às necessidades da sua empresa:

    - **Criar um novo Locatário do Azure AD B2C**: use esta opção para criar um novo locatário do Azure AD B2C.
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

    ![Link para o novo Diretório do Azure AD](./media/B2CImage_4.png)

> [!NOTE]
> Se você tiver várias assinaturas na conta do Azure ou tiver configurado o locatário B2C sem vincular a uma assinatura ativa, um banner de **Solução de problemas** orientará você a vincular o locatário a uma assinatura. Selecione a mensagem de solução de problemas e siga as instruções para resolver o problema da assinatura.

A imagem a seguir mostra um exemplo de um banner de **Solução de problemas** do B2C do Azure AD.

![Aviso mostrando que o diretório não tem uma Assinatura Ativa.](./media/B2CImage_5.png)

## <a name="next-steps"></a>Próximas etapas

Para continuar o processo de configuração de um locatário de B2 no Commerce, acesse [Criar o aplicativo de B2C](create-b2c-app.md).

## <a name="additional-resources"></a>Recursos adicionais

[Configurar um locatário B2C do Commerce](set-up-b2c-tenant.md)

[Criar o aplicativo B2C](create-b2c-app.md)

[Criar políticas de fluxo de usuário](create-user-flow-policies.md)

[Adicionar provedores de identidade social (Opcional)](add-social-identity-providers.md)

[Atualizar o Commerce headquarters com as novas informações de B2C do Azure AD](update-hq-aad-b2c-info.md)

[Configurar o locatário B2C no construtor de sites do Commerce](config-b2c-tenant-site-builder.md)

[Informações adicionais do B2C](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

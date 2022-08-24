---
title: Habilitar a integração do Dynamics 365 Commerce e do Microsoft Teams
description: Este artigo descreve como habilitar a integração do Microsoft Dynamics 365 Commerce e do Microsoft Teams.
author: gvrmohanreddy
ms.date: 02/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f8b84938c2047ab1102864cc203e0ec853160bb1
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274304"
---
# <a name="enable-dynamics-365-commerce-and-microsoft-teams-integration"></a>Habilitar a integração do Dynamics 365 Commerce e do Microsoft Teams

[!include [banner](includes/banner.md)]

Este artigo descreve como habilitar a integração do Microsoft Dynamics 365 Commerce e do Microsoft Teams.

Para provisionar o Teams com informações do Dynamics 365 Commerce e sincronizar os recursos de gerenciamento de tarefas entre o Teams e o aplicativo PDV (ponto de venda), você deve habilitar os recursos de integração no Commerce headquarters.

> [!NOTE]
> Ao habilitar a integração do Teams, você concorda em compartilhar seus dados com o Teams. Os dados compartilhados com o Teams podem residir em um país diferente do que os dados do Commerce e podem estar sujeitos a padrões de conformidade diferentes. Para obter mais informações, consulte o [Microsoft Trust Center](https://www.microsoft.com/trust-center). Para obter informações sobre as diretivas de privacidade da Microsoft, consulte a [Política de Privacidade da Microsoft](https://aka.ms/privacy).

## <a name="enable-teams-integration"></a>Habilitar a integração do Teams

Antes de habilitar a integração do Microsoft Teams com o Commerce, você deve registrar o aplicativo Teams com seu locatário no portal do Azure.

Para registrar o aplicativo Teams no seu locatário no portal do Azure, siga estas etapas.

1. Siga as etapas no [Início rápido: registre um aplicativo com a plataforma de identidade da Microsoft](/azure/active-directory/develop/quickstart-register-app) para registrar o aplicativo Teams com seu locatário no portal do Azure.
1. Na guia **Registro de aplicativo**, selecione o aplicativo que você criou na etapa anterior. Em seguida, na guia **Autenticação**, selecione **Adicionar uma plataforma**.
1. Na caixa de diálogo , selecione **Web**. Em seguida, no campo **URLs de redirecionamento**, insira uma URL no formato **\<HQUrl\>/oauth**. Substitua **\<HQUrl\>** pela URL do Commerce headquarters (por exemplo, `https://hxennugbjtweufmdeo385f47fadb6aa9a0aos.cloudax.int.dynamics.com/oauth`).
1. Na página **Visão Geral** do aplicativo registrado, copie o valor de **ID do aplicativo (cliente)**. Você deverá fornecer esse valor para habilitar a integração do Teams no Commerce headquarters na próxima seção.
1. Siga as instruções em [Adicionar um segredo de cliente](/azure/active-directory/develop/quickstart-register-app#add-a-client-secret) para adicionar um segredo de cliente. Em seguida, copie o valor de **Valor do segredo** do cliente. Você deverá fornecer esse valor para habilitar a integração do Teams no Commerce headquarters na próxima seção.
1. Selecione **Permissões de API** e, depois, **Adicionar uma permissão**.
1. Na caixa de diálogo **Solicitar permissões de API**, selecione **Microsoft Graph**, selecione **Permissões delegadas**, expanda **Grupo**, selecione **Group.ReadWrite.All** e, em seguida, selecione **Adicionar permissões**.
1. Na caixa de diálogo **Solicitar permissões de API**, selecione **Adicionar uma permissão**, **Microsoft Graph** e **Permissões de aplicativo**, expanda **Grupo**, selecione **Group.ReadWrite.All** e, em seguida, selecione **Adicionar permissões**.
1. Na caixa de diálogo **Solicitar permissões de API**, selecione **Adicionar uma permissão**. Na guia **APIs que minha organização utiliza**, procure e selecione **Serviço de Varejo do Microsoft Teams**.
1. Selecione **Permissões delegadas**, expanda **TaskPublishing**, selecione **TaskPublising.ReadWrite.All** e, depois, selecione **Adicionar permissões**. Para obter mais informações, consulte [Configurar um aplicativo cliente para acessar uma API Web](/azure/active-directory/develop/quickstart-configure-app-access-web-apis).

Para habilitar a integração do Teams no Commerce headquarters, siga estas etapas.

1. Acesse **Varejo e Comércio \> Configuração do canal \> Configuração de integração do Microsoft Teams**.
1. No Painel de Ações, selecione **Editar**.
1. Defina a opção **Habilitar integração do Microsoft Teams** como **Sim**.
1. No campo **ID do aplicativo**, insira o valor de **ID do aplicativo (cliente)** obtido ao registrar o aplicativo Teams no portal do Azure.
1. No campo **Chave do aplicativo**, insira o valor de **Valor do segredo** obtido ao adicionar um segredo de cliente no portal do Azure.
1. No Painel de ações, selecione **Salvar**.

A ilustração a seguir mostra um exemplo da configuração de integração do Teams no Commerce headquarters.

![Configuração de integração do Teams no Commerce headquarters.](media/D365-Commerce-Microsoft-Teams-Configuration_with_disclaimer.png)

## <a name="disable-teams-integration"></a>Desabilitar a integração do Teams

Para desabilitar a integração do Microsoft Teams no Commerce headquarters, siga estas etapas.

1. Acesse **Varejo e Comércio \> Configuração do canal \> Configuração de integração do Microsoft Teams**.
1. No Painel de Ações, selecione **Editar**.
3. Defina a opção **Habilitar integração do Microsoft Teams** como **Não**.
4. Limpe os valores dos campos **ID do Aplicativo** e **Chave do Aplicativo**.
1. No Painel de ações, selecione **Salvar**.

> [!NOTE]
> Depois de desabilitar a integração o Teams com o Commerce, os terminais de POS não mostrarão mais as tarefas publicadas a partir do aplicativo Teams.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de integração do Dynamics 365 Commerce e do Microsoft Teams](commerce-teams-integration.md)

[Provisionar o Microsoft Teams a partir do Dynamics 365 Commerce](provision-teams-from-commerce.md)

[Sincronizar o gerenciamento de tarefas entre o PDV do Microsoft Teams e do Dynamics 365 Commerce](synchronize-tasks-teams-pos.md)

[Gerenciar funções do usuário no Microsoft Teams](manage-user-roles-teams.md)

[Mapear lojas e equipes, se houver equipes pré-existentes no Microsoft Teams](map-stores-existing-teams.md)

[Perguntas frequentes sobre a integração do Dynamics 365 Commerce e do Microsoft Teams](teams-integration-faq.md)

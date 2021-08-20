---
title: Habilitar a integração do Dynamics 365 Commerce e do Microsoft Teams
description: Este tópico descreve como habilitar a integração do Microsoft Dynamics 365 Commerce e do Microsoft Teams.
author: gvrmohanreddy
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 9910ee48a0792c89a4e04ec8685fd02484e45575d70b06454dea56a89ee8c914
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6775329"
---
# <a name="enable-dynamics-365-commerce-and-microsoft-teams-integration"></a>Habilitar a integração do Dynamics 365 Commerce e do Microsoft Teams

[!include [banner](includes/banner.md)]

Este tópico descreve como habilitar a integração do Microsoft Dynamics 365 Commerce e do Microsoft Teams.

Para provisionar o Teams com informações do Dynamics 365 Commerce e sincronizar os recursos de gerenciamento de tarefas entre o Teams e o aplicativo PDV (ponto de venda), você deve habilitar os recursos de integração no Commerce Headquarters.

> [!NOTE]
> Ao habilitar a integração do Teams, você concorda em compartilhar seus dados com o Teams. Os dados compartilhados com o Teams podem residir em um país diferente do que os dados do Commerce e podem estar sujeitos a padrões de conformidade diferentes. Para obter mais informações, consulte o [Microsoft Trust Center](https://www.microsoft.com/trust-center). Para obter informações sobre as diretivas de privacidade da Microsoft, consulte a [Política de Privacidade da Microsoft](https://aka.ms/privacy).

## <a name="enable-teams-integration"></a>Habilitar a integração do Teams

Antes de habilitar a integração do Microsoft Teams com o Commerce, você deve registrar o aplicativo Teams com seu locatário no portal do Azure.

Para registrar o aplicativo Teams no seu locatário no portal do Azure, siga estas etapas.

1. Siga as etapas no [Início rápido: registre um aplicativo com a plataforma de identidade da Microsoft](/azure/active-directory/develop/quickstart-register-app) para registrar o aplicativo Teams com seu locatário no portal do Azure.
1. Copie o valor do **ID do aplicativo (cliente)** da página **Visão Geral** do aplicativo registrado. Você usará esse valor para habilitar a integração do Teams no Commerce Headquarters.
1. Copie o valor de certificado que foi inserido quando você [adicionou um certificado](/azure/active-directory/develop/quickstart-register-app#add-a-certificate) na etapa 1. O certificado também é conhecido como chave pública ou chave de aplicativo. Você usará esse valor para habilitar a integração do Teams no Commerce Headquarters.

Para habilitar a integração do Teams no Commerce headquarters, siga estas etapas.

1. Acesse **Varejo e Comércio \> Configuração do canal \> Configuração de integração do Microsoft Teams**.
1. No Painel de Ações, selecione **Editar**.
1. Defina a opção **Habilitar integração do Microsoft Teams** como **Sim**.
1. Nos campos **ID do aplicativo** e **Chave do aplicativo**, insira os valores obtidos ao registrar o aplicativo Teams no portal do Azure.
1. No Painel de ações, selecione **Salvar**.

A ilustração a seguir mostra um exemplo da configuração de integração do Teams no Commerce Headquarters.

![Configuração de integração do Teams na matriz do Commerce.](media/D365-Commerce-Microsoft-Teams-Configuration_with_disclaimer.png)

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
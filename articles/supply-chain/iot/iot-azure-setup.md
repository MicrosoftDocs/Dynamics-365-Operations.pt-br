---
title: Configurar recursos do Azure para Inteligência de IoT
description: Este tópico explica como criar e configurar os recursos do Microsoft Azure necessários para a Inteligência de IOT.
author: robinarh
manager: tfehr
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1277d2ab8bb1f2925874f7469250e164f6bde62d
ms.sourcegitcommit: 092ef6a45f515b38be2a4481abdbe7518a636f85
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4422497"
---
# <a name="set-up-azure-resources-for-iot-intelligence"></a>Configurar recursos do Azure para Inteligência de IoT

[!include [banner](../../includes/banner.md)]

Este tópico explica como criar e configurar os recursos do Microsoft Azure necessários para a Inteligência de IOT.

## <a name="create-azure-resources"></a>Criar recursos do Azure

Siga estas etapas para criar um Hub IoT, um cache de Redis e um cofre de chaves que podem ser acessados pelo Microsoft Dynamics 365 Supply Chain Management.

### <a name="verify-that-the-microsoft-dynamics-erp-microservices-first-party-app-id-is-in-your-tenant"></a>Verifique se a ID do aplicativo interno de microsserviços do Microsoft Dynamics ERP está em seu locatário

Para verificar se a ID do aplicativo para o aplicativo interno de microsserviços do Microsoft Dynamics ERP está em seu locatário, siga estas etapas.

1. Entre no portal do Azure em <https://portal.azure.com>.
2. Acesse **Azure Active Directory**.
3. Vá para **Aplicativos corporativos**.
4. No campo **Tipo de aplicativo**, selecione **Aplicativos da Microsoft**.
5. No campo de pesquisa, insira os **microsserviços do Microsoft Dynamics ERP**.
6. Verifique se **microsserviços do Microsoft Dynamics ERP** estão na lista. Outros aplicativos têm nomes semelhantes. Portanto, certifique se você encontrou a aplicação correta. A ID do aplicativo é **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.

    Se o aplicativo não estiver na lista, você deve adicioná-lo ao seu locatário:

    1. No portal do Azure, na barra de ferramentas, selecione o botão para abrir o Azure Cloud Shell.
    2. Execute o comando **Install-Module AzureAD**. Insira **S** para instalar o módulo.
    3. Execute o comando **Get-InstalledModule -Name "AzureAD"** para verificar se o módulo está instalado.
    4. Execute o comando **Connect-AzureAD -Confirm** para executar a autenticação.
    5. Execute o comando **New-AzureADServicePrincipal -AppId 0cdb527f-a8d1-4bf8-9436-b352c68682b2**.

    Agora você pode repetir as etapas 1 a 6 para verificar se a ID do aplicativo está no seu locatário.

### <a name="create-a-key-vault-resource"></a>Criar um recurso de cofre de chaves

Para criar um recurso de cofre de chaves, siga estas etapas.

1. No portal do Azure, crie ou acesse um grupo de recursos.
2. Selecione **Adicionar**.
3. Na página **Novo**, no campo de pesquisa, insira o **Cofre de chaves**. Depois, selecione **Criar**.
4. Na página **Criar cofre de chaves**, no campo **Nome do cofre de chaves**, insira um nome.
5. Revise os valores padrão e selecione **Revisar + Criar**.
6. Selecione **Criar**.

O cofre de chaves é criado em segundo plano.

### <a name="create-an-iot-hub-resource"></a>Criar um recurso de Hub IoT

Para criar um recurso de Hub IoT, siga estas etapas.

1. Crie ou vá para um grupo de recursos.
2. Selecione **Adicionar**.
3. Na página **Novo**, no campo de pesquisa, insira o **Hub Iot**. Depois, selecione **Criar**.
4. No campo **Nome de Hub IoT**, insira um nome.
5. Revise os valores padrão e selecione **Revisar + Criar**.
6. Selecione **Criar**.

O Hub IoT é criado em segundo plano.

> [!NOTE]
> Recomendamos que você crie apenas um recurso de Hub IoT por ambiente.

### <a name="create-a-redis-cache-resource"></a>Criar um recurso de cache Redis

Para criar um recurso de cache Redis, siga estas etapas.

1. Crie ou vá para um grupo de recursos.
2. Selecione **Adicionar**.
3. Na página **Novo**, no campo de pesquisa, insira **Cache do Azure para Redis**. Depois, selecione **Criar**.
4. No campo **Nome do DNS**, insira um nome.
5. Revise os valores padrão e selecione **Criar**.

O cache Redis é criado em segundo plano.

> [!NOTE]
> Recomendamos que você crie apenas um cache Redis por ambiente.

Todos os recursos foram criados agora.

## <a name="configure-the-azure-resources"></a>Configurar os recursos do Azure

### <a name="configure-the-iot-hub"></a>Configurar o Hub IoT

Para configurar o Hub IoT, siga estas etapas.

1. Em seus recursos, selecione o recurso de Hub IoT.
2. No painel de navegação esquerdo, selecione **Empresas internas**.
3. Em **Grupos de consumidores**, cole os seguintes grupos de consumidores. Esses grupos de consumidores correspondem aos cenários de retirada da caixa.

    + microsoft.dynamics.iotintelligence-1
    + microsoft.dynamics.iotintelligence-2
    + microsoft.dynamics.iotintelligence-3

### <a name="configure-the-key-vault"></a>Configurar o cofre de chaves

Para configurar o cofre de chaves, siga estas etapas.

1. Em seus recursos, selecione o recurso de cofre de chaves.
2. No painel de navegação esquerdo, selecione **Políticas de acesso**.
3. Selecione **Adicionar uma política de acesso**.
4. Na página **Adicionar política de acesso**, no campo **Permissões secretas**, selecione **Obter** e **Lista**.
5. Clique em **Selecionar principal**.
6. Na caixa de diálogo **Principal**, busque por e selecione **Microsserviços do Microsoft Dynamics ERP**. Depois selecione **Selecionar**.
7. Selecione **Adicionar**.
8. Selecione **Salvar**.

O aplicativo agora tem acesso aos segredos no cofre de chaves.

### <a name="save-the-iot-hub-connection-string-secret"></a>Salvar o segredo da cadeia de conexão do Hub IoT

Para salvar o segredo da cadeia de conexão do Hub IoT, siga estas etapas.

1. Em seus recursos, selecione o recurso de Hub IoT.
2. No painel de navegação esquerdo, selecione **Empresas internas**.
3. Copie o valor no campo **Ponto de extremidade compatível com Hub de eventos**.
4. Vá para o recurso de cofre de chaves.
5. No painel de navegação à esquerda, selecione **Segredos**.
6. Selecione **Gerar/Importar**.
7. No campo **Nome**, insira um nome.
8. No campo **Valor**, cole o valor da empresa que você copiou anteriormente.
9. Selecione **Criar**.

### <a name="save-the-redis-cache-connection-string-secret"></a>Salvar o segredo da cadeia de conexão do cache Redis

Para salvar o segredo da cadeia de conexão do cache Redis, siga estas etapas.

1. Em seus recursos, selecione o recurso de cache Redis.
2. Selecione **Chaves de acesso**.
3. Copie o valor no campo **Sequência de conexão primária**.
4. Vá para o recurso de cofre de chaves.
5. No painel de navegação à esquerda, selecione **Segredos**.
6. Selecione **Gerar/Importar**.
7. No campo **Nome**, insira um nome.
8. No campo **Valor**, cole a cadeia de conexão que você copiou anteriormente.
9. Selecione **Criar**.

> [!NOTE]
> Sempre que você atualizar uma das cadeias de conexão, deverá atualizar também os valores secretos.

Você concluiu o provisionamento dos recursos necessários do Azure. A próxima etapa é [instalar o suplemento de Inteligência de IOT Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
---
title: Instale o suplemento de Inteligência de IoT no LCS
description: Este tópico explica como instalar o suplemento de Inteligência de IoT no Microsoft Dynamics Lifecycle Services (LCS).
author: robinarh
manager: tfehr
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ad8b33633646f27bc368dc4bbedc1eb64c150a9f
ms.sourcegitcommit: 092ef6a45f515b38be2a4481abdbe7518a636f85
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4422495"
---
# <a name="install-the-iot-intelligence-add-in-in-lcs"></a>Instale o suplemento de Inteligência de IoT no LCS

[!include [banner](../../includes/banner.md)]

Este tópico explica como instalar o suplemento de Inteligência de IoT no Microsoft Dynamics Lifecycle Services (LCS). Observe que não é possível instalar suplementos em um ambiente de demonstração/avaliação. Para poder instalar o suplemento, você deve [criar os recursos do Azure](iot-azure-setup.md).

## <a name="set-up-the-lcs-environment"></a>Configurar o ambiente LCS

1. Abra o LCS e vá para o seu ambiente do Microsoft Dynamics 365 Supply Chain Management.
2. Role até a seção **Suplementos de ambiente**.
3. Selecione **Instalar um novo suplemento** para mostrar a lista de suplementos que foram habilitados para o ambiente.
4. Na caixa de diálogo **Selecionar um suplemento para instalar**, selecione a **Inteligência de IoT**.
5. Na caixa de diálogo **Configuração do suplemento**, forneça os detalhes do seu Hub IoT e do cache de Redis. Você pode encontrar os valores necessários no cofre de chaves criado em [Criar recursos do Azure](iot-azure-setup.md).

    + **ID do locatário** – No portal do Azure, acesse o cofre de chaves, e no painel à esquerda, selecione **Visão geral** e copie o valor **ID do diretório**. Cole esse valor na **Suplemento de configuração**.
    + **URI do cofre de chaves de ponto de extremidade compatível com Hub de eventos IoT** – Vá para o cofre de chaves e, no painel de navegação à esquerda, selecione **Visão geral** e copie o valor **Nome DNS**. Cole esse valor na **Suplemento de configuração**.
    + **Nome do segredo da empresa compatível com Hub de eventos IoT** – Vá para o cofre de chaves e, no painel de navegação à esquerda, selecione **Segredos** e copie o nome do segredo no qual a sequência de conexão do Hub de eventos do Hub IoT é armazenada. Cole esse valor na **Suplemento de configuração**.
    + **URI do cofre de chaves de cache Redis** – Vá para o cofre de chaves e, no painel de navegação à esquerda, selecione **Visão geral** e copie o valor **Nome DNS**. Cole esse valor na **Suplemento de configuração**.
    + **Nome do segredo do cache Redis** – Vá para o cofre de chaves e, no painel de navegação à esquerda, selecione **Segredos** e copie o nome do segredo no qual a sequência de conexão do cache Redis do Hub IoT é armazenada. Cole esse valor na **Suplemento de configuração**.

6. Marque a caixa de seleção para aceitar os termos e condições.
7. Selecione **Instalar**.
8. Uma caixa de mensagem é exibida dizendo que "Suplemento foi disparado com êxito para a instalação". Selecione **OK**.

A configuração do LCS está concluída. A próxima etapa é [configurar os cenários](iot-scenario-setup.md).

## <a name="uninstall-the-add-in"></a><a id="uninstall-addin"></a>Desinstalar o suplemento

1. Em Supply Chain Management, [desative os cenários](iot-scenario-setup.md#disable-a-scenario).
2. Em LCS, navegue até os detalhes do ambiente Supply Chain Management.
3. Role até a seção **Suplementos de ambiente**.
4. Selecione **Desinstalar** para o suplemento de inteligência IOT.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
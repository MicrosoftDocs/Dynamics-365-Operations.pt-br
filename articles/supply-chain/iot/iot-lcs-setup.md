---
title: Instale o suplemento de Inteligência de IoT no LCS
description: Este artigo explica como instalar o suplemento de Inteligência de IoT no Microsoft Dynamics Lifecycle Services (LCS).
author: johanhoffmann
ms.date: 08/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e18b05be1f2ba78c71515e4e76f180355d044b98
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2022
ms.locfileid: "9227823"
---
# <a name="install-the-iot-intelligence-add-in-in-lcs"></a>Instale o suplemento de Inteligência de IoT no LCS

[!include [banner](../../includes/banner.md)]
[!INCLUDE [iot-sdi-announcement](../../includes/iot-sdi-announcement.md)]

Este artigo explica como instalar o suplemento de Inteligência de IoT no Microsoft Dynamics Lifecycle Services (LCS). Observe que não é possível instalar suplementos em um ambiente de demonstração/avaliação. Para poder instalar o suplemento, você deve [criar os recursos do Azure](iot-azure-setup.md).

Você pode configurar a Inteligência da IoT sem escrever nenhum código. Estas são as etapas básicas.

1. [Configurar recursos do Azure](iot-azure-setup.md) – crie um hub IoT, um cache Redis e um cofre de chaves que possam ser acessados no Supply Chain Management.
2. [Formatos de esquema de mensagens para o Hub IoT](iot-schema-format.md) – configure seus dispositivos para enviar mensagens ao Hub IoT e defina o formato de mensagem JSON (JavaScript Object Notation).
3. Em Gerenciamento de Recursos, habilite o sinalizador de recurso de Inteligência da IoT.
4. Instalar o suplemento Inteligência da IoT no Microsoft Dynamics Lifecycle Services (LCs) – instale o suplemento no LCS e configure os segredos do Azure (conforme descrito neste artigo).
5. [Configurar métricas](iot-metrics-setup.md) – configure métricas no Supply Chain Management.
6. [Configuração do cenário](iot-scenario-setup.md) – configure os cenários no Supply Chain Management.

## <a name="set-up-the-lcs-environment"></a>Configurar o ambiente LCS

1. Abra o LCS e Acesse o seu ambiente do Microsoft Dynamics 365 Supply Chain Management.
2. Role até a seção **Suplementos de ambiente**.
3. Selecione **Instalar um novo suplemento** para mostrar a lista de suplementos que foram habilitados para o ambiente.
4. Na caixa de diálogo **Selecionar um suplemento para instalar**, selecione a **Inteligência de IoT**.
5. Na caixa de diálogo **Configuração do suplemento**, forneça os detalhes do seu Hub IoT e do cache de Redis. Você pode encontrar os valores necessários no cofre de chaves criado em [Criar recursos do Azure](iot-azure-setup.md).

    + **ID do locatário** – No portal do Azure, acesse o cofre de chaves, e no painel à esquerda, selecione **Visão geral** e copie o valor **ID do diretório**. Cole esse valor na **Suplemento de configuração**.
    + **URI do cofre de chaves de ponto de extremidade compatível com Hub de eventos IoT** – Acesse o cofre de chaves e, no painel de navegação à esquerda, selecione **Visão geral** e copie o valor **Nome DNS**. Cole esse valor na **Suplemento de configuração**.
    + **Nome do segredo da empresa compatível com Hub de eventos IoT** – Acesse o cofre de chaves e, no painel de navegação à esquerda, selecione **Segredos** e copie o nome do segredo no qual a sequência de conexão do Hub de eventos do Hub IoT é armazenada. Cole esse valor na **Suplemento de configuração**.
    + **URI do cofre de chaves de cache Redis** – Acesse o cofre de chaves e, no painel de navegação à esquerda, selecione **Visão geral** e copie o valor **Nome DNS**. Cole esse valor na **Suplemento de configuração**.
    + **Nome do segredo do cache Redis** – Acesse o cofre de chaves e, no painel de navegação à esquerda, selecione **Segredos** e copie o nome do segredo no qual a sequência de conexão do cache Redis do Hub IoT é armazenada. Cole esse valor na **Suplemento de configuração**.

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
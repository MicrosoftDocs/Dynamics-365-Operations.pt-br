---
title: Monitorar e gerenciar a inteligência IoT
description: Este tópico explica como monitorar e gerenciar a Inteligência de IoT.
author: robinarh
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: rhaertle
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 86e20b9e60e890833c0eb8573e92c0fbb27f8c9a
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908410"
---
# <a name="monitor-and-manage-iot-intelligence"></a>Monitorar e gerenciar a inteligência IoT

[!include [banner](../../includes/banner.md)]

Este tópico explica como monitorar e gerenciar a Inteligência de IoT.

## <a name="monitor-scenarios-in-microsoft-dynamics-365-supply-chain-management"></a><a id="monitor-scenarios"></a>Monitorar cenários no Microsoft Dynamics 365 Supply Chain Management

Você pode monitorar o processamento de Inteligência de IoT a partir de vários locais:

+ **Módulos \> Controle de produção \> Consultas e relatórios \> Inteligência de IoT \> Notificações** – Exibir a lista de notificações não resolvidas.
+ **Módulos \> Controle de produção \> Consultas e relatórios \> Inteligência de IoT \> Notificações fechadas** – Exibir a lista de notificações que foram solucionadas ou descartadas.
+ **Módulos \> Controle de produção \> Consultas e relatórios \> Inteligência de IoT \> Chaves de métrica** – Exibir as chaves de métrica para os gráficos de série **Status de recurso**.
+ **Módulos \> Controle de produção \> Execução de fabricação \> Status de recurso** – Rastrear métricas específicas usando a caixa de diálogo **Configurar**. Se um cenário detecta uma exceção, uma notificação mostra os detalhes da exceção.
+ **Espaços de trabalho \> Gerenciamento do chão de fábrica \> Notificações** – Exibir a lista de notificações não resolvidas.

## <a name="modify-a-running-iot-intelligence-scenario"></a>Modificar um cenário de Inteligência IoT em execução

Quando um cenário está em execução, você pode fazer as seguintes alterações:

+ Adicionar novas definições de esquema de sensor.
+ Selecione novos valores de dados de sinal.
+ Cancela a seleção de valores de dados de sinal existentes.
+ Adicione e mapeie novos valores de dados de sinal.
+ Atualize os valores de limite.

Quando um cenário está em execução, essas alterações são proibidas:

+ Exclua ou modifique qualquer definição de esquema consumida no momento por um cenário habilitado.
+ Altera os caminhos de esquema selecionados do cenário habilitado.

## <a name="simulation-options"></a>Opções de simulação

Você pode simular os sinais da máquina de fábrica. Para obter mais informações, consulte esses tópicos:

+ [Conectar IoT DevKit AZ3166 ao Hub IoT do Azure](/azure/iot-hub/iot-hub-arduino-iot-devkit-az3166-get-started)
+ [Conectar simulador online Raspberry Pi ao Hub IoT do Azure (Node.js)](/azure/iot-hub/iot-hub-raspberry-pi-web-simulator-get-started)
+ [Visão geral do acelerador de soluções de simulação de dispositivo](/azure/iot-accelerators/iot-accelerators-device-simulation-overview)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
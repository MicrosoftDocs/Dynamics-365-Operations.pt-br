---
title: Página inicial de Inteligência da IoT
description: Este tópico fornece links para informações sobre inteligência IoT.
author: tonyafehr
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: tfehr
ms.custom: intro-internal
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2020-04-25
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5c587f4e6a1dd58a7b8c238fc5afb16774828b2a
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8644376"
---
# <a name="iot-intelligence-home-page"></a>Página inicial de Inteligência da IoT

[!include [banner](../../includes/banner.md)]

> [!IMPORTANT]
> Esse recurso está disponível atualmente somente nos seguintes países/regiões:
>
> - EUA (Estados Unidos da América)
> - UE (União Europeia)
> - AU (Austrália)
> - CA (Canadá)
> - UK (Reino Unido)

A Inteligência da IoT é um suplemento para o Microsoft Dynamics 365 Supply Chain Management. Ela integra sinais da Internet das Coisas (IoT) a dados no Supply Chain Management para produzir ideias práticas.

A Inteligência da IoT dá suporte para os seguintes cenários:

- **Atrasos de produção** – esse cenário compara o tempo de ciclo real com o tempo de ciclo planejado. O Supply Chain Management notifica quando a produção não está na agenda, para que você possa intervir para maximizar a eficiência operacional e evitar atrasos na ordem.
- **Tempo de inatividade do equipamento** – esse cenário compara o tempo de atividade medido com os parâmetros definidos pelo usuário. O Supply Chain Management avisa quando um limite de interrupção é excedido, para que você possa tomar providências, como reagendar uma ordem de serviço de produção ou criar uma ordem de serviço de manutenção.
- **Qualidade do produto** – esse cenário compara as leituras do sensor, como umidade e temperatura, com as métricas de qualidade definidas pelo usuário. O Supply Chain Management avisa quando ocorre um desvio, para que você possa intervir para manter os padrões de qualidade e minimizar o desperdício.

A ilustração a seguir mostra a interação entre do Hub IoT do Azure, a Inteligência da IoT e o Supply Chain Management.

![Hub IoT, Inteligência da IoT e Supply Chain Management.](media/iot_intelligence.png)

<!-- KFM: hide setup info for now

## Setup

You can set up and configure IoT Intelligence without writing any code. Here are the basic steps.

1. [Set up Azure resources](iot-azure-setup.md) – Create an IoT hub, a Redis cache, and a key vault that can be accessed from Supply Chain Management.
2. [Message schema formats for IoT Hub](iot-schema-format.md) – Configure your devices to send messages to IoT Hub, and define the JavaScript Object Notation (JSON) message format.
3. In Feature Management, enable the IoT Intelligence feature flag. 
4. [Install the IoT Intelligence add-in in Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md) – Install the add-in in LCS, and configure the Azure secrets.
5. [Set up metrics](iot-metrics-setup.md) – Set up metrics in Supply Chain Management.
6. [Scenario setup](iot-scenario-setup.md) – Set up the scenarios in Supply Chain Management.

-->

## <a name="tracking-and-maintenance"></a>Acompanhamento e manutenção

- [Monitorar cenários no Dynamics 365 Supply Chain Management](iot-management.md#monitor-scenarios)
- [Desabilitar um cenário](iot-scenario-setup.md#disable-a-scenario)
- [Modificar um cenário de Inteligência IoT em execução](iot-management.md#modify-a-running-iot-intelligence-scenario)
- [Opções de simulação](iot-management.md#simulation-options)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
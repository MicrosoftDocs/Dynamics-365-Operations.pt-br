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
ms.openlocfilehash: 6b6c179052cdb9d1ca808d9cba089163bde0d5d5
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2021
ms.locfileid: "7782672"
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

+ **Atrasos de produção** – esse cenário compara o tempo de ciclo real com o tempo de ciclo planejado. O Supply Chain Management notifica quando a produção não está na agenda, para que você possa intervir para maximizar a eficiência operacional e evitar atrasos na ordem.
+ **Tempo de inatividade do equipamento** – esse cenário compara o tempo de atividade medido com os parâmetros definidos pelo usuário. O Supply Chain Management avisa quando um limite de interrupção é excedido, para que você possa tomar providências, como reagendar uma ordem de serviço de produção ou criar uma ordem de serviço de manutenção.
+ **Qualidade do produto** – esse cenário compara as leituras do sensor, como umidade e temperatura, com as métricas de qualidade definidas pelo usuário. O Supply Chain Management avisa quando ocorre um desvio, para que você possa intervir para manter os padrões de qualidade e minimizar o desperdício.

A ilustração a seguir mostra a interação entre do Hub IoT do Azure, a Inteligência da IoT e o Supply Chain Management.

![Hub IoT, Inteligência da IoT e Supply Chain Management.](media/iot_intelligence.png)

## <a name="setup"></a>Configuração

Você pode configurar a Inteligência da IoT sem escrever nenhum código. Estas são as etapas básicas.

1. [Configurar recursos do Azure](iot-azure-setup.md) – crie um hub IoT, um cache Redis e um cofre de chaves que possam ser acessados no Supply Chain Management.
2. [Formatos de esquema de mensagens para o Hub IoT](iot-schema-format.md) – configure seus dispositivos para enviar mensagens ao Hub IoT e defina o formato de mensagem JSON (JavaScript Object Notation).
3. Em Gerenciamento de Recursos, habilite o sinalizador de recurso de Inteligência da IoT. 
4. [Instalar o suplemento Inteligência da IoT no Microsoft Dynamics Lifecycle Services (LCs)](iot-lcs-setup.md) – instale o suplemento no LCS e configure os segredos do Azure.
5. [Configurar métricas](iot-metrics-setup.md) – configure métricas no Supply Chain Management.
6. [Configuração do cenário](iot-scenario-setup.md) – configure os cenários no Supply Chain Management.

## <a name="tracking-and-maintenance"></a>Acompanhamento e manutenção

+ [Monitorar cenários no Dynamics 365 Supply Chain Management](iot-management.md#monitor-scenarios)
+ [Desabilitar um cenário](iot-scenario-setup.md#disable-a-scenario)
+ [Desinstalar o suplemento](iot-lcs-setup.md#uninstall-addin)
+ [Modificar um cenário de Inteligência IoT em execução](iot-management.md#modify-a-running-iot-intelligence-scenario)
+ [Opções de simulação](iot-management.md#simulation-options)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
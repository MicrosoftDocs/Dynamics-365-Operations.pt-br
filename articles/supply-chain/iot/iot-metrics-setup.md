---
title: Configurar métricas para Inteligência da IoT
description: Este tópico explica como configurar métricas para a Inteligência da IoT.
author: johanhoffmann
ms.date: 04/25/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-04-25
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b67292e45746ee45460141b4be32f2f8f14076ad
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8674327"
---
# <a name="set-up-metrics-for-iot-intelligence"></a>Configurar métricas para Inteligência da IoT

[!include [banner](../../includes/banner.md)]

## <a name="configure-metrics"></a>Configurar métricas

Se você quiser ver os gráficos de série temporal de suas mensagens no Microsoft Dynamics 365 Supply Chain Management, configure as métricas seguindo estas etapas.

1. Copie a cadeia de conexão para o cache Redis:

    1. No portal do Azure, vá para o cache Redis.
    2. Vá para **Configurações** \> **Chaves de acesso**.
    3. Copie o valor no campo **Sequência de conexão primária**.

2. No Supply Chain Management, acesse **Controle de produção \> Configuração \> Inteligência da IoT \> Parâmetros de cenário**.
3. Na página **Parâmetros de cenário**, na guia **Série Temporal**, no campo **Cadeia de conexão do repositório de métricas Redis**, cole a cadeia de conexão que você copiou anteriormente. Esta etapa permite que as métricas do Hub IoT do Azure sejam visualizadas no Supply Chain Management. Quando você cola o valor no campo, ele é mostrado como **\*\*\*\*\*\***.

    > [!NOTE]
    > Sempre que você atualizar a cadeia de conexão do cache Redis, deverá atualizar também esse campo.

4. Vá para **Controle de produção \> Consultas e relatórios \> Inteligência da IoT \> Chaves de métricas**.
5. Na página **Chaves de métricas**, selecione **Atualizar**.
6. Na caixa de diálogo **Atualizar chaves métricas**, observe que **Executar em segundo plano** está selecionado no campo. Selecione **OK**.

Todas as chaves de métricas no cache Redis são recuperadas e adicionadas à lista **Chaves de métricas**. Os valores das métricas não aparecerão até que você [habilite os cenários](iot-scenario-setup.md).

## <a name="configure-the-resource-status-time-series"></a>Configurar a série temporal de Status do Recurso

Para configurar a série temporal **Status do Recurso**, siga estas etapas.

1. No Supply Chain Management, vá para **Controle de produção \> Execução de fabricação \> Status do Recurso**.
2. Na página **Status do recurso**, selecione **Configurar**.
2. Na caixa de diálogo **Configurar**, na lista **Recursos**, selecione um item para monitorar.
3. Selecione o botão **Editar** para a **Série temporal 1**.
4. Na caixa de diálogo **Selecionar série temporal**, selecione uma métrica na grade. (Você também pode usar o link **Atualizar chaves de métricas** para atualizar as chaves de métricas nessa caixa de diálogo.)
5. Selecione **OK** para retornar à caixa de diálogo **Configurar**.
6. Insira um nome de exibição.
7. No campo **Mostrar dados de**, selecione um período.
8. Selecione **OK**.

O gráfico é mostrado.

## <a name="delete-a-metric-key"></a>Excluir uma chave de métrica

1. No Supply Chain Management, vá para **Controle de produção \> Consultas e relatórios \> Inteligência da IoT \> Chaves de métricas**.
2. Na página **Chaves de métricas**, selecione a chave de métrica a ser excluída.
3. Selecione **Excluir**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
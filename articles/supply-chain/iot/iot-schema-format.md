---
title: Formatos de esquema para mensagens do Hub IoT
description: Este tópico explica como criar um esquema de mensagens que possa ser usado na Inteligência da IoT.
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
ms.openlocfilehash: 60d5bc4eacdd7e7d713490998bd1d20c9271ad02
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8673932"
---
# <a name="schema-formats-for-iot-hub-messages"></a>Formatos de esquema para mensagens do Hub IoT

[!include [banner](../../includes/banner.md)]

Este tópico explica como criar um esquema de mensagens que possa ser usado na Inteligência da IoT.

## <a name="message-requirements"></a>Requisitos de mensagem

As seguintes regras se aplicam ao monitoramento de mensagens na Inteligência da IoT:

+ Os esquemas de mensagens devem estar no formato JSON (JavaScript Object Notation).
+ Uma propriedade **carimbo de data/hora** do UNIX, em que o valor é expresso em milissegundos (ms), deve estar presente na mensagem do Hub IoT do Microsoft Azure.
+ Uma mensagem é rastreada somente se contiver todas as propriedades definidas na configuração do cenário. Por exemplo, se você definir as propriedades **id**, **carimbo de data/hora** e **valor**, a mensagem a seguir será monitorada.

    ```json
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
        "value": True
    }
    ```

    Esta mensagem não é monitorada, pois a propriedade **valor** está ausente.

    ```json
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
    }
    ```

+ A Inteligência da IoT ignora as propriedades na mensagem que não estão definidas na configuração do cenário. Por exemplo, se você definir as propriedades **id**, **carimbo de data/hora** e **valor**, a Inteligência da IoT vai monitorar todas as mensagens a seguir.

    ```json
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
        "value": True
    },
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
        "value": True,
        "machine" : "Machine1225",
    },
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
        "value": True,
         "activity": "PartOut"
    },
    ```

+ A Inteligência da IoT ignora silenciosamente as mensagens que não correspondem aos critérios de configuração do cenário.
+ Você pode definir e usar vários tipos de esquemas de mensagens.
+ Nem todo o tipo de esquema de mensagens deve ser definido. Somente os esquemas que serão usados para os cenários de Inteligência da IoT devem ser definidos.

## <a name="id-value-pair-schema"></a>Esquema do par ID-valor

Um par ID-valor é um padrão comum para esquemas de mensagens de Inteligência da IoT. Ao usar um par ID-valor, você garante que o seu esquema de mensagens é o mesmo em todos os cenários. Por exemplo, esta é uma mensagem para o cenário **Tempo de inatividade do equipamento** ou **Atrasos de produção**.

```json
{
    "id": "IoTInt.Machine1225.PartOut",
    "timestamp": 1576016821614,
    "value": True
}
```

Esta é uma mensagem para o cenário **Qualidade do produto**.

```json
{
    "id": "IoTInt.Machine1225.Temperature",
    "timestamp": 1576016821614,
    "value": 105
}
```

As duas mensagens anteriores contêm as propriedades **id** e **valor**. Os valores de **id** podem ser mapeados na tabela **Valores de Dados de Sinal** durante a configuração do cenário. Para o cenário **Tempo de inatividade do equipamento**, você mapeará o valor **IoTInt.Machine1225.PartOut**. Para o cenário **Qualidade do produto**, você mapeará o valor **IoTInt.Machine1225.Temperature**.

Para obter mais informações, consulte o [Documentação do Hub IoT do Azure](/azure/iot-hub/).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
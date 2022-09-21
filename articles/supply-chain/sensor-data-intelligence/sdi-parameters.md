---
title: Parâmetros do Sensor Data Intelligence
description: Este artigo fornece informações sobre as configurações disponíveis na página parâmetros do Sensor Data Intelligence.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreServiceParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 4a6665cc078e54da4ebb7920ec8826352ab7a816
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428292"
---
# <a name="sensor-data-intelligence-parameters"></a>Parâmetros do Sensor Data Intelligence

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

A página de **parâmetros do Sensor Data Intelligence** fornece algumas configurações que podem ser usadas para configurar o recurso. Essas configurações incluem os parâmetros de conexão do Azure e um parâmetro para o tempo de vida útil das mensagens de alerta que são enviadas aos usuários em resposta a medições de sensor.

## <a name="read-and-change-connection-details-for-your-azure-iot-solution"></a>Ler e alterar detalhes de conexão para sua solução Azure IoT

Normalmente, você configurará a solução Azure IoT e a conectará ao Microsoft Dynamics 365 Supply Chain Management na página **Implantar e conectar recursos do Azure**, que orientará você pelos dois procedimentos. (Para obter mais informações, consulte [Implantar uma solução IoT no Azure](sdi-deploy-iot-solution-on-azure.md).) Você também pode exibir e editar os detalhes da conexão a qualquer momento no Supply Chain Management seguindo essas etapas.

1. Vá para **Administração do sistema \> Configuração \> Sensor Data Intelligence \> Parâmetros do Sensor Data Intelligence**.
1. Na guia **Série temporal**, no campo **Cadeia de conexão de armazenamento de métrica de Redis**, insira o valor de **Cadeia de conexão principal (StackExchange.Redis)** a para a solução Azure IoT à qual você deseja se conectar. Para obter mais informações sobre como encontrar esse valor, consulte [Implantar uma solução IoT no Azure](sdi-deploy-iot-solution-on-azure.md).
1. Na guia **Integrações**, no campo **ID do cliente do aplicativo Azure AD**, insira o valor de **ID do cliente** para a solução Azure IoT à qual você deseja se conectar. Para obter mais informações sobre como encontrar esse valor, consulte [Implantar uma solução IoT no Azure](sdi-deploy-iot-solution-on-azure.md).

## <a name="set-the-lifetime-of-alert-messages"></a>Definir o tempo de vida útil das mensagens de alerta

Toda vez que o Sensor Data Intelligence detecta uma situação que exige atenção do usuário, ele envia uma notificação ao usuário relevante. Para evitar que essas notificações permaneçam no sistema, você deve defini-las para expirar após alguns dias.

1. Vá para **Administração do sistema \> Configuração \> Sensor Data Intelligence \> Parâmetros do Sensor Data Intelligence**.
1. Na guia **Notificações**, no campo **Dias até a notificação**, insira o número de dias para manter uma notificação. Após a quantidade de tempo especificada, a notificação será excluída.

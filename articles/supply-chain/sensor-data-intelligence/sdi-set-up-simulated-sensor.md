---
title: Configurar um sensor simulado para teste
description: Este artigo descreve como configurar um simulador que pode ser usado para testar o Sensor Data Intelligence sem instalar sensores físicos.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: dc8bd020a53214abab28ec51ffc6d6be74979932
ms.sourcegitcommit: c5f2cba3c2b0758e536eeaaa40506659a53085e1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2022
ms.locfileid: "9643967"
---
# <a name="set-up-a-simulated-sensor-for-testing"></a>Configurar um sensor simulado para teste

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Se você deseja testar o Sensor Data Intelligence sem instalar sensores físicos, é possível usar o serviço *Raspberry PI Azure IoT Online Simulator* para emular os sinais de sensor e enviá-los para a solução de Internet das Coisas (IoT) no Microsoft Azure. Para obter mais informações sobre o simulador, consulte [Conectar Raspberry Pi online Simulator ao Hub IoT do Azure (Node.js)](/azure/iot-hub/iot-hub-raspberry-pi-web-simulator-get-started).

## <a name="video-instructions"></a>Instruções de vídeo

O vídeo a seguir mostra como configurar um sensor simulado para teste. As seções restantes neste artigo fornecem as mesmas instruções em um formato baseado em texto.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE588g6]

## <a name="create-a-device-in-azure-iot-hub"></a>Criar um dispositivo no Hub IoT do Azure

Primeiro, você deve configurar um dispositivo para autenticar os sinais do sensor no Hub IoT do Azure.

1. No Azure, vá para a lista de recursos do grupo de recursos que você criou para uso com o Sensor Data Intelligence. (Para obter mais informações, consulte [Implantar uma solução IoT no Azure](sdi-deploy-iot-solution-on-azure.md).)
1. Na lista de recursos, localize o registro no qual o campo **Tipo** está definido como *Hub IoT*. Na coluna **Nome**, selecione o nome para abrir a página de detalhes do recurso.
1. No painel de navegação à esquerda, selecione **Dispositivos**.
1. Na página **Dispositivos**, selecione **Adicionar dispositivo**.
1. Na página **Criar um dispositivo**, defina os seguintes campos:

    - **ID do dispositivo** – Insira um nome para o novo dispositivo (por exemplo, *My-IoT-Device*).
    - **Tipo de autenticação** – Selecione *Chaves simétricas*.
    - **Gerar chaves automaticamente** – Marque esta caixa de seleção.
    - **Conectar este dispositivo a um hub IoT** – Selecione *Habilitar*.

1. Selecione **Salvar** para retornar à página **Dispositivos**.
1. Localize o novo dispositivo na lista. Na coluna **ID do dispositivo**, selecione o nome para abrir a página de detalhes do dispositivo. Se você não vir o novo dispositivo na lista, atualize a página.
1. Copie o valor de **Cadeia de conexão principal** (por exemplo, selecionando o botão **Copiar para a área de transferência**). Esse valor será necessário posteriormente, quando você configurar o Raspberry Pi IoT Simulator para emular os sinais do sensor. Portanto, considere colá-lo em um arquivo de texto por enquanto.

## <a name="add-the-azure-connection-string-to-the-raspberry-pi-iot-simulator"></a>Adicionar a cadeia de conexão do Azure ao Raspberry Pi IoT Simulator

Siga estas etapas para adicionar a cadeia de conexão do dispositivo no Hub IoT do Azure ao script no serviço Raspberry.

1. Abra o [Raspberry Pi IoT Simulator](https://azure-samples.github.io/raspberry-pi-web-simulator/).
1. No painel do editor de códigos, localize a linha que contém o comando a seguir.

    `const connectionString = '[Your IoT hub device connection string]';`

1. Substitua o texto de ajuda, incluindo os colchetes, pelo valor da **Cadeia de conexão principal** que você copiou na seção anterior. O resultado deve se assemelhar ao seguinte exemplo.

    `const connectionString = 'HostName=XXX;DeviceId=YYY;SharedAccessKey=ZZZ';`

## <a name="add-sensor-ids-and-values-to-the-payload-in-the-raspberry-pi-iot-simulator"></a>Adicionar IDs e valores de sensor à carga no Raspberry Pi IoT Simulator

Agora você deve configurar o Raspberry Pi IoT Simulator com sensores simulados e os valores que serão enviados como cargas.

- No editor de códigos do Raspberry Pi IoT Simulator, localize a função `getMessage` e edite-a para que corresponda ao código a seguir. (Os sensores são configurados nas linhas `cb()`.)

    ```cpp
    function getMessage(cb) {
        messageId++;
        sensor.readSensorData()
        .then(function (data) {
            cb(JSON.stringify({ value: 1, sensorId: 'MachineStatus' }), false);
            cb(JSON.stringify({ value: 70, sensorId: 'Quality' }), false);
            cb(JSON.stringify({ value: 1, sensorId: 'AssetMaintenance' }), false);
            cb(JSON.stringify({ value: 1, sensorId: 'ProductionDelay' }), false);
            cb(JSON.stringify({ value: 20, sensorId: 'AssetDowntime' }), false);
        })
        .catch(function (err) {
            console.error('Failed to read out sensor data: ' + err);
        });
    }
    ```

    > [!IMPORTANT]
    > Os IDs de sensores definidos no editor de códigos para o Raspberry Pi IoT Simulator devem ser idênticos aos IDs de sensor que você especificará posteriormente para os cenários no Supply Chain Management. O código de exemplo anterior usa IDs do sensor legíveis por pessoas. No entanto, em um cenário real, os IDs de sensor serão valores de identificador global exclusivo (GUID) fornecidos pelo fabricante do sensor. Os IDs do sensor legíveis por humanos usados neste exemplo de código também são usados nos exemplos de [O cenário de qualidade do produto](sdi-scenario-product-quality.md), [O cenário de manutenção de ativos](sdi-scenario-asset-maintenance.md), [O cenário de atrasos de produção](sdi-scenario-production-delays.md) e [O cenário de status da máquina](sdi-scenario-equipment-downtime.md). Portanto, use este código se você for trabalhar por meio desses cenários.

## <a name="edit-the-interval-for-sending-sensor-signals"></a>Editar o intervalo para enviar sinais de sensor

Agora você deve definir o intervalo no qual o Raspberry Pi IoT Simulator deve enviar os sinais do sensor emulado.

1. No editor de códigos do Raspberry Pi IoT Simulator, localize a seguinte chamada de função.

    `setInterval(sendMessage, 2000);`

2. Por padrão, o Raspberry Pi IoT Simulator envia um sinal de sensor a cada 2.000 milissegundos (dois segundos). Você pode ajustar o valor conforme desejado.

## <a name="run-the-raspberry-pi-iot-simulator"></a>Execute o Raspberry Pi IoT Simulator

- Selecione **Executar** para iniciar o simulador e começar a enviar dados de sensores simulados.

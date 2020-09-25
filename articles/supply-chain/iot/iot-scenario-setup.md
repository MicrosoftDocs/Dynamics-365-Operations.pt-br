---
title: Configuração do cenário de Inteligência de IoT
description: Este tópico explica como configurar cenários de Inteligência da IoT no Microsoft Dynamics 365 Supply Chain Management.
author: robinarh
manager: tfehr
ms.date: 08/16/2019
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
ms.openlocfilehash: d1deaa2130b63272da39a42315c6a1bc4b7ccb8a
ms.sourcegitcommit: 8adc65e26d78e229271eb427659a87ee5f371319
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2020
ms.locfileid: "3814050"
---
# <a name="scenario-setup-for-iot-intelligence"></a>Configuração do cenário de Inteligência de IoT

[!include [banner](../../includes/banner.md)]

Este tópico explica como configurar cenários de Inteligência da IoT no Microsoft Dynamics 365 Supply Chain Management. Antes de configurar os cenários, é necessário [configurar o Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md).

Neste tópico, você configurará o cenário de **Tempo de inatividade do equipamento** para que uma notificação seja gerada no Supply Chain Management quando uma máquina for desativada. O tópico também mostra como configurar o cenário de **Qualidade do produto** para que uma notificação seja gerada se um atributo de um item estiver fora de um intervalo especificado e como configurar o cenário de **Atrasos na produção** para que uma notificação seja gerada se a taxa de transferência da produção ficar abaixo de um valor limite.

## <a name="configure-the-equipment-downtime-scenario-in-supply-chain-management"></a>Configurar o cenário de Tempo de inatividade do equipamento no Supply Chain Management

O cenário de **Tempo de inatividade do equipamento** mapeia um sinal **PartOut** para um limite de alerta de máquina. A máquina é monitorada somente quando ela é selecionada para o cenário e quando é definida como **Em Execução** no Supply Chain Management. Se o tempo desde um último sinal **PartOut** recebido da máquina exceder o limite de alerta, uma notificação **Máquina desligada** será disparada. Se a máquina ainda estiver em execução, será disparada uma notificação **Máquina ativa** quando o próximo sinal **PartOut** for recebido. Se uma máquina permanecer inoperante por 30 minutos, uma nova notificação de **Máquina desativada** será disparada.

O cenário **Tempo de inatividade do equipamento** tem as seguintes dependências:

+ Um alerta só poderá ser disparado se uma ordem de produção estiver em execução em uma máquina mapeada.
+ Um sinal que representa o sinal **PartOut** de uma máquina mapeada deve ser enviado ao Hub IoT e um nome de propriedade exclusivo deve ser incluído.
+ Uma propriedade **carimbo de data/hora** do UNIX, em que o valor é expresso em milissegundos (ms), deve estar presente na mensagem do Hub IoT do Azure.

Para configurar o cenário, siga estas etapas.

1. Entre no Supply Chain Management.
2. Habilite o sinalizador de recurso de Inteligência de IoT. Para obter mais informações, consulte [Visão geral do Gerenciamento de recursos](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).
3. Configurar as métricas. Para obter mais informações, consulte [Como configurar métricas](iot-metrics-setup.md#configure-metrics).
4. Vá para **Controle de produção \> Configuração \> Inteligência da IoT \> Gerenciamento de cenário** .
6. No bloco **Tempo de inatividade do equipamento** , selecione **Configurar** para abrir o assistente de configuração.

   A primeira página no assistente é a página **Definição do esquema do sensor de equipamento**. Nesta página, sua meta é configurar o esquema no Supply Chain Management para que ele corresponda ao formato JSON (JavaScript Object Notation) das mensagens do Hub IoT. Vários esquemas de mensagens podem ser definidos. Para obter mais informações, consulte [Formatos de esquema de mensagens do Hub IoT](iot-schema-format.md). Neste exemplo, o conteúdo da mensagem inclui um lote de mensagens com o formato a seguir.

    ```json
    {
        "timestamp": 1576016821614,
        "payload": [
            {
                "id": "IoTInt.Machine1225.PartOut",
                "timestamp": 1576016821614,
                "value": True
            },
            {
                "id": "IoTInt.Machine1226.PartOut",
                "timestamp": 1576016991616,
                "value": True
            }
        ]
    }
    ```

7. Adicione uma linha à tabela e defina os seguintes valores:

    1. Defina o campo **Nome do esquema** como **ID**.
    2. Defina o campo **Caminho do esquema** como **/payload\[\*\]/id**.
    3. Defina o campo **Descrição** como **ID da mensagem**.

8. Adicione outra linha à tabela e defina os seguintes valores:

    1. Defina o campo **Nome do esquema** como **Carimbo de data/hora**.
    2. Defina o campo **Caminho do esquema** como **/payload\[\*\]/timestamp**.
    3. Defina o campo **Descrição** como **Carimbo de data/hora da mensagem**.

9. Adicione outra linha à tabela e defina os seguintes valores:

    1. Defina o campo **Nome do esquema** como **Valor**.
    2. Defina o campo **Caminho do esquema** como **/payload\[\*\]/value**.
    3. Defina o campo **Descrição** como **Valor da mensagem**.

    > [!NOTE]
    > Você não precisa definir todas as propriedades da mensagem. Defina somente as propriedades necessárias. Nas etapas anteriores, você não criou uma linha para o **Carimbo de data/hora raiz** . O caminho de **Carimbo de data/hora** seria **/timestamp**.

10. Selecione **Avançar** para ir para a página **Mapa de esquema do sensor de equipamento**.
11. Na linha de **ID de recurso do equipamento**, no campo **Nome do esquema**, selecione **ID**.
12. Na linha de **Hora UTC**, no campo **Nome do esquema**, selecione **Carimbo de data/hora**.
13. Na linha de **Sinal produzido da peça**, no campo **Nome do esquema**, selecione **Valor**.
14. Selecione **Avançar** para acessar a página **Configuração da ID do recurso do equipamento**.
15. Siga estas etapas para mapear os valores de mensagem do Hub IoT para os recursos do Supply Chain Management:

    1. Na tabela **Valores de Dados de Sinal**, adicione uma nova linha. No campo **Valor**, insira **IoTInt.Machine1225.PartOut** . Este valor vem da propriedade **id** de JSON na mensagem de Hub IoT.
    2. Selecione **Salvar**.
    3. Na tabela **Mapeamento de Registros Comerciais**, selecione **Novo**. Um valor padrão do campo **Tipo de registro comercial** é preenchido automaticamente e você não precisa alterá-lo.
    4. No campo **Registro comercial**, selecione o recurso de máquina Supply Chain Management do qual esse valor de sinal está sendo enviado.
    5. Selecione **Salvar**.
    6. Repita essas etapas para adicionar um novo mapeamento de registro de negócios para **Machine1226**. Você pode mapear vários valores de dados de sinal em um único registro no Supply Chain Management.

16. Use a coluna **Selecionado** para selecionar as máquinas que você deseja processar. Não é necessário definir todos os valores de sinal, nem selecionar todas as máquinas.
17. Selecione **Avançar** para acessar a página **Configuração de sinal de produzido parcial**.
18. Na tabela **Valores de Dados de Sinal**, adicione uma linha e defina o campo **Valor** como **Verdadeiro**. Este valor vem da propriedade **value** de JSON na mensagem de Hub IoT. Você pode adicionar quantos valores forem necessários para o seu cenário.
19. Selecione **Salvar**.
20. Selecione **Avançar** para acessar a página **Limite de tempo de inatividade do equipamento**. As máquinas listadas são as máquinas que foram previamente mapeadas para valores de sinal. Nesta etapa, você definirá um limite para determinar se uma máquina está inoperante. Por exemplo, se você definir o limite como **10**, o Supply Chain Management gerará uma notificação se uma máquina não receber sinal **PartOut** por 10 minutos.
21. Selecione **Avançar** para acessar a página **Habilitar cenário**. Defina a opção para habilitar o cenário.
22. Selecione **Concluir**.

A configuração do cenário agora está concluída. A Inteligência de IoT começará automaticamente a processar as mensagens de Hub IoT.

## <a name="configure-the-product-quality-scenario-in-supply-chain-management"></a>Configurar o cenário de Qualidade de produto em Supply Chain Management

O cenário **Qualidade do produto** gera uma notificação se um atributo de um item estiver fora de um intervalo especificado. Por exemplo, um sensor envia o peso de cada item ao Hub IoT. Se um item for pesado ou leve demais, uma notificação será gerada no Supply Chain Management.

O cenário **Qualidade do produto** tem as seguintes dependências:

+ Um alerta poderá ser disparado apenas se uma ordem de produção estiver em execução em uma máquina mapeada e gerar um produto com um atributo de lote mapeado.
+ Um sinal que representa o atributo de lote deve ser enviado ao Hub IoT e um nome de propriedade exclusivo deve ser incluído.
+ Uma propriedade **carimbo de data/hora** do UNIX, em que o valor é expresso em ms, deve estar presente na mensagem do Hub IoT.

## <a name="configure-the-production-delays-scenario-in-supply-chain-management"></a>Configurar o cenário de Atrasos de produção no Supply Chain Management

O cenário **Atrasos de produção** gera uma notificação se a taxa de transferência da produção ficar abaixo de um valor limite. Neste cenário, um sinal **PartOut** é enviado ao Hub IOT para cada item produzido. No Supply Chain Management, o atraso da ordem é calculado com base em: o tempo que a ordem de produção está agendada para ser executada, o número de itens que devem ser gerados, o período de tempo em que o trabalho está em execução e o número de sinais **PartOut** recebidos. Uma notificação de atraso será gerada se o número de sinais **PartOut** do trabalho ficar abaixo do valor limite.

O cenário **Atrasos de produção** tem as seguintes dependências:

+ Um alerta só poderá ser disparado se uma ordem de produção estiver em execução em uma máquina mapeada.
+ Um sinal que representa o sinal **PartOut** de uma máquina mapeada deve ser enviado ao Hub IoT do Azure e um nome de propriedade exclusivo deve ser incluído.
+ Uma propriedade **carimbo de data/hora** do UNIX, em que o valor é expresso em ms, deve estar presente na mensagem do Hub IoT.

## <a name="disable-a-scenario"></a>Desabilitar um cenário

Para desabilitar um cenário, siga estas etapas.

1. No Supply Chain Management, acesse **Controle de produção \> Configuração \> Inteligência de IoT \> Gerenciamento de cenário**.
2. No bloco do cenário, selecione **Configurar** .
3. Selecione **Avançar** para acessar a página do último assistente.
4. Defina a opção para desabilitar o cenário.

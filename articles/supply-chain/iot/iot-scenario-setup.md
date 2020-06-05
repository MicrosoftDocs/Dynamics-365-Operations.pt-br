---
title: Configuração do cenário de Inteligência de IoT
description: Este tópico descreve como configurar um cenário no Supply Chain Management para a Inteligência de IoT.
author: robinarh
manager: AnnBe
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: ''
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b87a9b73f49e73fe13b98fb11da939c9b30e0f6e
ms.sourcegitcommit: 261b70ea358b2c231e20f320ed8bd6adc1e7d715
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "3386486"
---
# <a name="scenario-setup-for-iot-intelligence"></a>Configuração do cenário de Inteligência de IoT

[!include [banner](../../includes/banner.md)]

Este tópico descreve como configurar um cenário no Supply Chain Management para a Inteligência de IoT. Antes de configurar os cenários, você deve [configurar LCS](iot-lcs-setup.md).

Neste tópico, você irá configurar o cenário de **Tempo de inatividade do equipamento** para gerar uma notificação no Supply Chain Management quando uma máquina for desativada.

## <a name="configure-the-equipment-downtime-scenario-in-supply-chain-management"></a>Configurar o cenário de **Tempo de inatividade do equipamento** no Supply Chain Management

O cenário de **Tempo de inatividade do equipamento** mapeia um sinal de saída parcial para um limite de alerta de máquina. A máquina é monitorada somente quando a máquina é selecionada para o cenário e é definida para ser executada no Supply Chain Management. Se o tempo desde o último sinal de parte recebido do computador for maior do que o limite de alerta, uma notificação **Máquina desligada** será disparada. Se a máquina ainda estiver sendo executada, quando o próximo sinal **PartOut** for recebido, a notificação **Máquina ativa** será disparada. Se uma máquina permanecer inoperante por 30 minutos, uma nova notificação de **Máquina desativada** será disparada.

O cenário **Tempo de inatividade do equipamento** tem estas dependências:

+ Uma ordem de produção deve estar sendo executada em uma máquina mapeada para que um alerta seja disparado.
+ Um sinal representando o sinal de saída de uma máquina mapeada deve ser enviado ao Hub IoT com um nome de propriedade exclusivo.
+ Uma propriedade de carimbo de data/hora UNIX em milissegundos deve estar presente na mensagem do Hub IoT.

Para configurar o cenário, siga estas etapas:

1. Entre no Supply Chain Management.
2. Habilite o sinalizador de recurso de Inteligência de IoT. Para obter mais informações, consulte [Visão geral do Gerenciamento de recursos](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
3. Configurar as métricas. Para obter mais informações, consulte [Como configurar métricas](iot-metrics-setup.md#configure-metrics).
4. Navegue até **Controle de produção**.
5. Navegue até **Configurações \> Inteligência de IoT \> Gerenciamento de cenário**.
6. Clique em **Configurar** no bloco **Tempo de inatividade do equipamento**. O assistente de configuração inicia com a página **Definição do esquema do sensor de equipamento**. A meta aqui é configurar o esquema no Supply Chain Management para coincidir com o formato JSON das mensagens IoT. Vários esquemas de mensagens podem ser definidos. Para obter mais informações, consulte [Formatos de esquema de mensagens para o Hub IoT](iot-schema-format.md). Neste exemplo, a carga da mensagem contém um lote de mensagens com este formato:

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

7. Adicione uma linha à tabela.

    1. Defina o **Nome do esquema** como **ID**.
    2. Defina o **Caminho do esquema** como **/payload[\*]/id**.
    3. Defina a **Descrição** como **ID da mensagem**.

8. Adicione uma linha à tabela.

    1. Defina o **Nome do esquema** como **Data/hora**.
    2. Defina o **Caminho do esquema** como **/payload[\*]/timestamp**.
    3. Defina a **Descrição** como **Data/hora da mensagem**.

9. Adicione uma linha à tabela.

    1. Defina o **Nome do esquema** como **Valor**.
    2. Defina o **Caminho do esquema** como **/payload[\*]/value**.
    3. Defina a **Descrição** como **Valor da mensagem**.

    Não é necessário definir todas as propriedades na mensagem, somente aquelas que você precisa. Neste exemplo, você não criou uma linha para o **Carimbo de data/hora**. O caminho para **Carimbo de data/hora** seria **/timestamp**.
  
10. Clique em **Avançar** para ir para a página **Mapa de esquema do sensor de equipamento**.
11. Na linha para **ID de recurso do equipamento** defina o **Nome do esquema** como **ID**. Os valores válidos são exibidos em uma tabela suspensa.
12. Na linha para **Hora UTC**, defina o **Nome do esquema** como **Data/hora**. Os valores válidos são exibidos em uma tabela suspensa.
13. Na linha para **Sinal produzido da peça** defina o **Nome do esquema** como **Valor**. Os valores válidos são exibidos em uma tabela suspensa.
14. Clique em **Avançar** para a página **Configuração da ID do recurso do equipamento**.
15. Nesta etapa, mapeie os valores de mensagem do Hub IoT para os recursos de Supply Chain Management.

    1. Na tabela **Valores de dados do sinal**, adicione uma nova linha e insira **IoTInt.Machine1225.PartOut** na coluna **Valor**. O valor **IoTInt.Machine1225.PartOut** vem da propriedade **id** de JSON na mensagem de Hub IoT.
    2. Clique em **Salvar**.
    3. Na tabela **Mapeamento de registros comerciais**, clique em **Novo**. O valor padrão para o **Tipo de registro comercial** é preenchido por completo e você não precisa alterá-lo.
    4. Na coluna **Registro comercial**, selecione o recurso de máquina Supply Chain Management do qual esse valor de sinal está sendo enviado.
    5. Clique em **Salvar**.
    6. Repita essas etapas, adicionando um novo mapeamento de registro de negócios para **Machine1226**. Você pode mapear vários valores de dados de sinal em um único registro no Supply Chain Management.

16. Use a coluna **Selecionado** para escolher as máquinas que deseja processar. Não é necessário definir todos os valores de sinal e não é necessário selecionar todos os computadores.
17. Clique em **Avançar** para ir para a página **Configuração de sinal de produzido parcial**.
18. Na tabela **Valores de dados de sinal**, adicione uma linha e defina **Valor** como **Verdade**. O valor **Verdadeiro** vem da propriedade **valor** de JSON na mensagem de Hub IoT. Você pode adicionar quantos valores forem necessários para o seu cenário.
19. Clique em **Salvar**.
20. Clique em **Avançar** para ir para a página **Limite de tempo de inatividade do equipamento**. As máquinas listadas são as máquinas previamente mapeadas para valores de sinal. Nesta etapa, você define um limite para determinar se um computador está inoperante. Por exemplo, se você definir o limite como 10, o Supply Chain Management gerará uma notificação se não houver nenhuma mensagem de parte de um computador por 10 minutos.
21. Clique em **Avançar** para ir para a página **Habilitar cenário**. Ative o controle deslizante para habilitar o cenário.
22. Clique em **Finish** (Concluir).

A configuração do cenário foi concluída. A Inteligência de IoT iniciará automaticamente o processamento das mensagens de Hub IoT.

## <a name="configure-the-product-quality-scenario-in-supply-chain-management"></a>Configurar o cenário de **Qualidade de produto** em Supply Chain Management

O cenário **Qualidade do produto** gera uma notificação se um atributo de um item estiver fora de um intervalo especificado. Por exemplo, um sensor pode enviar o peso de cada item ao Hub IoT. No Supply Chain Management, uma notificação seria gerada se o item era muito pesado ou muito claro.

O cenário tem estas dependências:

+ Uma Ordem de Produção deve ser executada em uma máquina mapeada e produzir um produto com um atributo de lote mapeado para que um alerta seja disparado.
+ Um sinal representando o atributo de lote deve ser enviado ao Hub IoT com um nome de propriedade exclusivo.
+ Uma propriedade de carimbo de data/hora UNIX em milissegundos deve estar presente na mensagem do Hub IoT.

## <a name="configure-the-production-delays-scenario-in-supply-chain-management"></a>Configurar o cenário de **Atrasos de produção** no Supply Chain Management

O cenário **Atrasos de produção** gera uma notificação se a taxa de transferência da produção ficar abaixo de um valor limite. Neste cenário, um sinal **PartOut** é enviado ao Hub IOT para cada item produzido. Em Supply Chain Management, o atraso da ordem é calculado com base no tempo agendado para a execução da ordem de produção, quantos itens devem ser produzidos, quanto tempo o trabalho está em execução e quantos sinais **PartOut** são recebidos. Uma notificação de atraso será gerada se o número de sinais **PartOut** do trabalho ficar abaixo do valor limite do valor esperado.

O cenário tem estas dependências:

+ Uma Ordem de Produção deve estar sendo executada em uma máquina mapeada para que um alerta seja disparado.
+ Um sinal representando o sinal de saída de uma máquina mapeada deve ser enviado ao Hub IoT com um nome de propriedade exclusivo.
+ Uma propriedade de carimbo de data/hora UNIX em milissegundos deve estar presente na mensagem do Hub IoT.

## <a name="how-to-disable-a-scenario"></a>Como desabilitar um cenário

Para desativar um cenário, siga estas etapas:

1. Em Supply Chain Management, navegue até **Controle de produção \> Configuração \> Inteligência de IoT \> Gerenciamento de cenário**.
2. Clique em **Configurar** no cenário.
3. Clique em **Avançar** para ir para a última guia do assistente.
4. Ative o controle deslizante para desabilitar o cenário.

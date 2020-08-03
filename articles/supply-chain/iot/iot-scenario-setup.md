---
title: Configuração do cenário de Inteligência de IoT
description: Este tópico descreve como configurar um cenário no Supply Chain Management para a Inteligência de IoT.
author: robinarh
manager: tfehr
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
ms.openlocfilehash: 5633741fcd9c04b68e5b174447d7ead3c521ccd7
ms.sourcegitcommit: f64fce03ec52f844b05a9e8cac286cb201385002
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/16/2020
ms.locfileid: "3597159"
---
# <a name="scenario-setup-for-iot-intelligence"></a><span data-ttu-id="de74f-103">Configuração do cenário de Inteligência de IoT</span><span class="sxs-lookup"><span data-stu-id="de74f-103">Scenario setup for IoT Intelligence</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="de74f-104">Este tópico descreve como configurar um cenário no Supply Chain Management para a Inteligência de IoT.</span><span class="sxs-lookup"><span data-stu-id="de74f-104">This topic describes how to configure a scenario in Supply Chain Management for IoT Intelligence.</span></span> <span data-ttu-id="de74f-105">Antes de configurar os cenários, você deve [configurar LCS](iot-lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="de74f-105">Before you can setup the scenarios, you must [setup LCS](iot-lcs-setup.md).</span></span>

<span data-ttu-id="de74f-106">Neste tópico, você irá configurar o cenário de **Tempo de inatividade do equipamento** para gerar uma notificação no Supply Chain Management quando uma máquina for desativada.</span><span class="sxs-lookup"><span data-stu-id="de74f-106">In this topic, you will configure the **Equipment downtime** scenario to generate a notification in Supply Chain Management when a machine goes down.</span></span>

## <a name="configure-the-equipment-downtime-scenario-in-supply-chain-management"></a><span data-ttu-id="de74f-107">Configurar o cenário de **Tempo de inatividade do equipamento** no Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="de74f-107">Configure the **Equipment downtime** scenario in Supply Chain Management</span></span>

<span data-ttu-id="de74f-108">O cenário de **Tempo de inatividade do equipamento** mapeia um sinal de saída parcial para um limite de alerta de máquina.</span><span class="sxs-lookup"><span data-stu-id="de74f-108">The **Equipment downtime** scenario maps a part out signal to a machine alert threshold.</span></span> <span data-ttu-id="de74f-109">A máquina é monitorada somente quando a máquina é selecionada para o cenário e é definida para ser executada no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="de74f-109">The machine is monitored only when the machine is selected for the scenario and is set to running in Supply Chain Management.</span></span> <span data-ttu-id="de74f-110">Se o tempo desde o último sinal de parte recebido do computador for maior do que o limite de alerta, uma notificação **Máquina desligada** será disparada.</span><span class="sxs-lookup"><span data-stu-id="de74f-110">If the time since the machine’s last received Part Out signal is greater than the alert threshold, then a **Machine down** notification is triggered.</span></span> <span data-ttu-id="de74f-111">Se a máquina ainda estiver sendo executada, quando o próximo sinal **PartOut** for recebido, a notificação **Máquina ativa** será disparada.</span><span class="sxs-lookup"><span data-stu-id="de74f-111">If the machine is still running, when the next **PartOut** signal is received a **Machine up** notification is triggered.</span></span> <span data-ttu-id="de74f-112">Se uma máquina permanecer inoperante por 30 minutos, uma nova notificação de **Máquina desativada** será disparada.</span><span class="sxs-lookup"><span data-stu-id="de74f-112">If a machine stays down for 30 mins a new **Machine down** notification is triggered.</span></span>

<span data-ttu-id="de74f-113">O cenário **Tempo de inatividade do equipamento** tem estas dependências:</span><span class="sxs-lookup"><span data-stu-id="de74f-113">The **Equipment downtime** scenario has these dependencies:</span></span>

+ <span data-ttu-id="de74f-114">Uma ordem de produção deve estar sendo executada em uma máquina mapeada para que um alerta seja disparado.</span><span class="sxs-lookup"><span data-stu-id="de74f-114">A production order must be running on a mapped machine for an alert to be triggered.</span></span>
+ <span data-ttu-id="de74f-115">Um sinal representando o sinal de saída de uma máquina mapeada deve ser enviado ao Hub IoT com um nome de propriedade exclusivo.</span><span class="sxs-lookup"><span data-stu-id="de74f-115">A signal representing a mapped machine's part out signal must be sent to the IoT Hub with a unique property name.</span></span>
+ <span data-ttu-id="de74f-116">Uma propriedade de carimbo de data/hora UNIX em milissegundos deve estar presente na mensagem do Hub IoT.</span><span class="sxs-lookup"><span data-stu-id="de74f-116">A Unix milliseconds timestamp property must be present in the IoT hub message.</span></span>

<span data-ttu-id="de74f-117">Para configurar o cenário, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="de74f-117">To configure the scenario, follow these steps:</span></span>

1. <span data-ttu-id="de74f-118">Entre no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="de74f-118">Log into Supply Chain Management.</span></span>
2. <span data-ttu-id="de74f-119">Habilite o sinalizador de recurso de Inteligência de IoT.</span><span class="sxs-lookup"><span data-stu-id="de74f-119">Enable the IoT Intelligence feature flag.</span></span> <span data-ttu-id="de74f-120">Para obter mais informações, consulte [Visão geral do Gerenciamento de recursos](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="de74f-120">For more information, see [Feature management overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>
3. <span data-ttu-id="de74f-121">Configurar as métricas.</span><span class="sxs-lookup"><span data-stu-id="de74f-121">Configure the metrics.</span></span> <span data-ttu-id="de74f-122">Para obter mais informações, consulte [Como configurar métricas](iot-metrics-setup.md#configure-metrics).</span><span class="sxs-lookup"><span data-stu-id="de74f-122">For more information, see [How to configure metrics](iot-metrics-setup.md#configure-metrics).</span></span>
4. <span data-ttu-id="de74f-123">Navegue até **Controle de produção**.</span><span class="sxs-lookup"><span data-stu-id="de74f-123">Navigate to **Production control**.</span></span>
5. <span data-ttu-id="de74f-124">Navegue até **Configurações \> Inteligência de IoT \> Gerenciamento de cenário**.</span><span class="sxs-lookup"><span data-stu-id="de74f-124">Navigate to **Setup \> IoT Intelligence \> Scenario management**.</span></span>
6. <span data-ttu-id="de74f-125">Clique em **Configurar** no bloco **Tempo de inatividade do equipamento**.</span><span class="sxs-lookup"><span data-stu-id="de74f-125">Click **Configure** on the **Equipment downtime** tile.</span></span> <span data-ttu-id="de74f-126">O assistente de configuração inicia com a página **Definição do esquema do sensor de equipamento**.</span><span class="sxs-lookup"><span data-stu-id="de74f-126">The configuration wizard starts with the **Equipment sensor schema definition** page.</span></span> <span data-ttu-id="de74f-127">A meta aqui é configurar o esquema no Supply Chain Management para coincidir com o formato JSON das mensagens IoT.</span><span class="sxs-lookup"><span data-stu-id="de74f-127">The goal here is to setup the schema in Supply Chain Management to match the JSON format of the IoT messages.</span></span> <span data-ttu-id="de74f-128">Vários esquemas de mensagens podem ser definidos.</span><span class="sxs-lookup"><span data-stu-id="de74f-128">Multiple message schemas can be defined.</span></span> <span data-ttu-id="de74f-129">Para obter mais informações, consulte [Formatos de esquema de mensagens para o Hub IoT](iot-schema-format.md).</span><span class="sxs-lookup"><span data-stu-id="de74f-129">For more information, see [Message schema formats for IoT Hub](iot-schema-format.md).</span></span> <span data-ttu-id="de74f-130">Neste exemplo, a carga da mensagem contém um lote de mensagens com este formato:</span><span class="sxs-lookup"><span data-stu-id="de74f-130">In this example, the message payload contains a batch of messages with this format:</span></span>

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

7. <span data-ttu-id="de74f-131">Adicione uma linha à tabela.</span><span class="sxs-lookup"><span data-stu-id="de74f-131">Add a row to the table.</span></span>

    1. <span data-ttu-id="de74f-132">Defina o **Nome do esquema** como **ID**.</span><span class="sxs-lookup"><span data-stu-id="de74f-132">Set the **Schema name** to **ID**.</span></span>
    2. <span data-ttu-id="de74f-133">Defina o **Caminho do esquema** como **/payload[\*]/id**.</span><span class="sxs-lookup"><span data-stu-id="de74f-133">Set the **Schema path** to **/payload[\*]/id**.</span></span>
    3. <span data-ttu-id="de74f-134">Defina a **Descrição** como **ID da mensagem**.</span><span class="sxs-lookup"><span data-stu-id="de74f-134">Set the **Description** to **Message ID**.</span></span>

8. <span data-ttu-id="de74f-135">Adicione uma linha à tabela.</span><span class="sxs-lookup"><span data-stu-id="de74f-135">Add a row to the table.</span></span>

    1. <span data-ttu-id="de74f-136">Defina o **Nome do esquema** como **Data/hora**.</span><span class="sxs-lookup"><span data-stu-id="de74f-136">Set the **Schema name** to **Timestamp**.</span></span>
    2. <span data-ttu-id="de74f-137">Defina o **Caminho do esquema** como **/payload[\*]/timestamp**.</span><span class="sxs-lookup"><span data-stu-id="de74f-137">Set the **Schema path** to **/payload[\*]/timestamp**.</span></span>
    3. <span data-ttu-id="de74f-138">Defina a **Descrição** como **Data/hora da mensagem**.</span><span class="sxs-lookup"><span data-stu-id="de74f-138">Set the **Description** to **Message timestamp**.</span></span>

9. <span data-ttu-id="de74f-139">Adicione uma linha à tabela.</span><span class="sxs-lookup"><span data-stu-id="de74f-139">Add a row to the table.</span></span>

    1. <span data-ttu-id="de74f-140">Defina o **Nome do esquema** como **Valor**.</span><span class="sxs-lookup"><span data-stu-id="de74f-140">Set the **Schema name** to **Value**.</span></span>
    2. <span data-ttu-id="de74f-141">Defina o **Caminho do esquema** como **/payload[\*]/value**.</span><span class="sxs-lookup"><span data-stu-id="de74f-141">Set the **Schema path** to **/payload[\*]/value**.</span></span>
    3. <span data-ttu-id="de74f-142">Defina a **Descrição** como **Valor da mensagem**.</span><span class="sxs-lookup"><span data-stu-id="de74f-142">Set the **Description** to **Message value**.</span></span>

    <span data-ttu-id="de74f-143">Não é necessário definir todas as propriedades na mensagem, somente aquelas que você precisa.</span><span class="sxs-lookup"><span data-stu-id="de74f-143">You don't need to define all the properties in the message, only the ones that you need.</span></span> <span data-ttu-id="de74f-144">Neste exemplo, você não criou uma linha para o **Carimbo de data/hora**.</span><span class="sxs-lookup"><span data-stu-id="de74f-144">In this example, you did not create a row for **Root timestamp**.</span></span> <span data-ttu-id="de74f-145">O caminho para **Carimbo de data/hora** seria **/timestamp**.</span><span class="sxs-lookup"><span data-stu-id="de74f-145">The path for **Root timestamp** would be **/timestamp**.</span></span>
  
10. <span data-ttu-id="de74f-146">Clique em **Avançar** para ir para a página **Mapa de esquema do sensor de equipamento**.</span><span class="sxs-lookup"><span data-stu-id="de74f-146">Click **Next** to go to the **Equipment sensor schema map** page.</span></span>
11. <span data-ttu-id="de74f-147">Na linha para **ID de recurso do equipamento** defina o **Nome do esquema** como **ID**.</span><span class="sxs-lookup"><span data-stu-id="de74f-147">In the row for **Equipment resource ID** set the **Schema name** to **ID**.</span></span> <span data-ttu-id="de74f-148">Os valores válidos são exibidos em uma tabela suspensa.</span><span class="sxs-lookup"><span data-stu-id="de74f-148">The valid values are displayed in a dropdown table.</span></span>
12. <span data-ttu-id="de74f-149">Na linha para **Hora UTC**, defina o **Nome do esquema** como **Data/hora**.</span><span class="sxs-lookup"><span data-stu-id="de74f-149">In the row for **UTC time** set the **Schema name** to **Timestamp**.</span></span> <span data-ttu-id="de74f-150">Os valores válidos são exibidos em uma tabela suspensa.</span><span class="sxs-lookup"><span data-stu-id="de74f-150">The valid values are displayed in a dropdown table.</span></span>
13. <span data-ttu-id="de74f-151">Na linha para **Sinal produzido da peça** defina o **Nome do esquema** como **Valor**.</span><span class="sxs-lookup"><span data-stu-id="de74f-151">In the row for **Part produced signal** set the **Schema name** to **Value**.</span></span> <span data-ttu-id="de74f-152">Os valores válidos são exibidos em uma tabela suspensa.</span><span class="sxs-lookup"><span data-stu-id="de74f-152">The valid values are displayed in a dropdown table.</span></span>
14. <span data-ttu-id="de74f-153">Clique em **Avançar** para a página **Configuração da ID do recurso do equipamento**.</span><span class="sxs-lookup"><span data-stu-id="de74f-153">Click **Next** for the **Equipment resource ID configuration** page.</span></span>
15. <span data-ttu-id="de74f-154">Nesta etapa, mapeie os valores de mensagem do Hub IoT para os recursos de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="de74f-154">In this step, you map the IoT Hub message values to the Supply Chain Management resources.</span></span>

    1. <span data-ttu-id="de74f-155">Na tabela **Valores de dados do sinal**, adicione uma nova linha e insira **IoTInt.Machine1225.PartOut** na coluna **Valor**.</span><span class="sxs-lookup"><span data-stu-id="de74f-155">In the **Signal Data Values** table, add a new row, and enter **IoTInt.Machine1225.PartOut** in the **Value** column.</span></span> <span data-ttu-id="de74f-156">O valor **IoTInt.Machine1225.PartOut** vem da propriedade **id** de JSON na mensagem de Hub IoT.</span><span class="sxs-lookup"><span data-stu-id="de74f-156">The value **IoTInt.Machine1225.PartOut** comes from the JSON **id** property in the IoT hub message.</span></span>
    2. <span data-ttu-id="de74f-157">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="de74f-157">Click **Save**.</span></span>
    3. <span data-ttu-id="de74f-158">Na tabela **Mapeamento de registros comerciais**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="de74f-158">In the **Business Record Mapping** table, click **New**.</span></span> <span data-ttu-id="de74f-159">O valor padrão para o **Tipo de registro comercial** é preenchido por completo e você não precisa alterá-lo.</span><span class="sxs-lookup"><span data-stu-id="de74f-159">The default value for the **Business record type** is autopopulated, and you don't need to change it.</span></span>
    4. <span data-ttu-id="de74f-160">Na coluna **Registro comercial**, selecione o recurso de máquina Supply Chain Management do qual esse valor de sinal está sendo enviado.</span><span class="sxs-lookup"><span data-stu-id="de74f-160">In the **Business record** column, select the Supple Chain Management machine resource this signal value is being sent from.</span></span>
    5. <span data-ttu-id="de74f-161">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="de74f-161">Click **Save**.</span></span>
    6. <span data-ttu-id="de74f-162">Repita essas etapas, adicionando um novo mapeamento de registro de negócios para **Machine1226**.</span><span class="sxs-lookup"><span data-stu-id="de74f-162">Repeat these steps, adding a new business record mapping for **Machine1226**.</span></span> <span data-ttu-id="de74f-163">Você pode mapear vários valores de dados de sinal em um único registro no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="de74f-163">You can map multiple signal data values to a single record in Supply Chain Management.</span></span>

16. <span data-ttu-id="de74f-164">Use a coluna **Selecionado** para escolher as máquinas que deseja processar.</span><span class="sxs-lookup"><span data-stu-id="de74f-164">Use the **Selected** column to choose which machines you want to process.</span></span> <span data-ttu-id="de74f-165">Não é necessário definir todos os valores de sinal e não é necessário selecionar todos os computadores.</span><span class="sxs-lookup"><span data-stu-id="de74f-165">You do not have to define all signal values and you do not have to select all machines.</span></span>
17. <span data-ttu-id="de74f-166">Clique em **Avançar** para ir para a página **Configuração de sinal de produzido parcial**.</span><span class="sxs-lookup"><span data-stu-id="de74f-166">Click **Next** to go to the **Part produced signal configuration** page.</span></span>
18. <span data-ttu-id="de74f-167">Na tabela **Valores de dados de sinal**, adicione uma linha e defina **Valor** como **Verdade**.</span><span class="sxs-lookup"><span data-stu-id="de74f-167">In the **Signal Data Values** table, add a row, and set **Value** to **True**.</span></span> <span data-ttu-id="de74f-168">O valor **Verdadeiro** vem da propriedade **valor** de JSON na mensagem de Hub IoT.</span><span class="sxs-lookup"><span data-stu-id="de74f-168">The value **True** comes from the JSON **value** property in the IoT hub message.</span></span> <span data-ttu-id="de74f-169">Você pode adicionar quantos valores forem necessários para o seu cenário.</span><span class="sxs-lookup"><span data-stu-id="de74f-169">You can add as many values as you need for your scenario.</span></span>
19. <span data-ttu-id="de74f-170">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="de74f-170">Click **Save**.</span></span>
20. <span data-ttu-id="de74f-171">Clique em **Avançar** para ir para a página **Limite de tempo de inatividade do equipamento**.</span><span class="sxs-lookup"><span data-stu-id="de74f-171">Click **Next** to go to the **Equipment downtime threshold** page.</span></span> <span data-ttu-id="de74f-172">As máquinas listadas são as máquinas previamente mapeadas para valores de sinal.</span><span class="sxs-lookup"><span data-stu-id="de74f-172">The machines listed are the machines previously mapped to signal values.</span></span> <span data-ttu-id="de74f-173">Nesta etapa, você define um limite para determinar se um computador está inoperante.</span><span class="sxs-lookup"><span data-stu-id="de74f-173">In this step, you define a threshold to determine if a machine is down.</span></span> <span data-ttu-id="de74f-174">Por exemplo, se você definir o limite como 10, o Supply Chain Management gerará uma notificação se não houver nenhuma mensagem de parte de um computador por 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="de74f-174">For example, if you set the threshold to 10, Supply Chain Management generates a notification if there is no part out message from a machine for 10 minutes.</span></span>
21. <span data-ttu-id="de74f-175">Clique em **Avançar** para ir para a página **Habilitar cenário**.</span><span class="sxs-lookup"><span data-stu-id="de74f-175">Click **Next** to go to the **Enable scenario** page.</span></span> <span data-ttu-id="de74f-176">Ative o controle deslizante para habilitar o cenário.</span><span class="sxs-lookup"><span data-stu-id="de74f-176">Toggle the slider to enable the scenario.</span></span>
22. <span data-ttu-id="de74f-177">Clique em **Finish** (Concluir).</span><span class="sxs-lookup"><span data-stu-id="de74f-177">Click **Finish**.</span></span>

<span data-ttu-id="de74f-178">A configuração do cenário foi concluída.</span><span class="sxs-lookup"><span data-stu-id="de74f-178">The scenario setup is complete.</span></span> <span data-ttu-id="de74f-179">A Inteligência de IoT iniciará automaticamente o processamento das mensagens de Hub IoT.</span><span class="sxs-lookup"><span data-stu-id="de74f-179">IoT Intelligence will automatically start processing the IoT Hub messages.</span></span>

## <a name="configure-the-product-quality-scenario-in-supply-chain-management"></a><span data-ttu-id="de74f-180">Configurar o cenário de **Qualidade de produto** em Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="de74f-180">Configure the **Product quality** scenario in Supply Chain Management</span></span>

<span data-ttu-id="de74f-181">O cenário **Qualidade do produto** gera uma notificação se um atributo de um item estiver fora de um intervalo especificado.</span><span class="sxs-lookup"><span data-stu-id="de74f-181">The **Product quality** scenario generates a notification if an attribute of an item is outside a specified range.</span></span> <span data-ttu-id="de74f-182">Por exemplo, um sensor pode enviar o peso de cada item ao Hub IoT.</span><span class="sxs-lookup"><span data-stu-id="de74f-182">For example, a sensor could send the weight of each item to IoT Hub.</span></span> <span data-ttu-id="de74f-183">No Supply Chain Management, uma notificação seria gerada se o item era muito pesado ou muito claro.</span><span class="sxs-lookup"><span data-stu-id="de74f-183">In Supply Chain Management, a notification would be generated if the item was too heavy or too light.</span></span>

<span data-ttu-id="de74f-184">O cenário tem estas dependências:</span><span class="sxs-lookup"><span data-stu-id="de74f-184">The scenario has these dependencies:</span></span>

+ <span data-ttu-id="de74f-185">Uma Ordem de Produção deve ser executada em uma máquina mapeada e produzir um produto com um atributo de lote mapeado para que um alerta seja disparado.</span><span class="sxs-lookup"><span data-stu-id="de74f-185">A Production Order must be running on a mapped machine and producing a product with a mapped batch attribute for an alert to be triggered.</span></span>
+ <span data-ttu-id="de74f-186">Um sinal representando o atributo de lote deve ser enviado ao Hub IoT com um nome de propriedade exclusivo.</span><span class="sxs-lookup"><span data-stu-id="de74f-186">A signal representing the batch attribute must be sent to the IoT Hub with a unique property name.</span></span>
+ <span data-ttu-id="de74f-187">Uma propriedade de carimbo de data/hora UNIX em milissegundos deve estar presente na mensagem do Hub IoT.</span><span class="sxs-lookup"><span data-stu-id="de74f-187">A Unix milliseconds timestamp property must be present in the IoT Hub message.</span></span>

## <a name="configure-the-production-delays-scenario-in-supply-chain-management"></a><span data-ttu-id="de74f-188">Configurar o cenário de **Atrasos de produção** no Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="de74f-188">Configure the **Production delays** scenario in Supply Chain Management</span></span>

<span data-ttu-id="de74f-189">O cenário **Atrasos de produção** gera uma notificação se a taxa de transferência da produção ficar abaixo de um valor limite.</span><span class="sxs-lookup"><span data-stu-id="de74f-189">The **Production delays** scenario generates a notification if the production throughput falls below a threshold value.</span></span> <span data-ttu-id="de74f-190">Neste cenário, um sinal **PartOut** é enviado ao Hub IOT para cada item produzido.</span><span class="sxs-lookup"><span data-stu-id="de74f-190">In this scenario, a **PartOut** signal is sent to IoT Hub for each item produced.</span></span> <span data-ttu-id="de74f-191">Em Supply Chain Management, o atraso da ordem é calculado com base no tempo agendado para a execução da ordem de produção, quantos itens devem ser produzidos, quanto tempo o trabalho está em execução e quantos sinais **PartOut** são recebidos.</span><span class="sxs-lookup"><span data-stu-id="de74f-191">In Supply Chain Management, the order delay is calculated based on how long the production order is scheduled to run, how many items should be produced, how long the job has been running, and how many **PartOut** signals are received.</span></span> <span data-ttu-id="de74f-192">Uma notificação de atraso será gerada se o número de sinais **PartOut** do trabalho ficar abaixo do valor limite do valor esperado.</span><span class="sxs-lookup"><span data-stu-id="de74f-192">A delay notification would be generated if the number of the **PartOut** signals for the job falls below the threshold value of the expected value.</span></span>

<span data-ttu-id="de74f-193">O cenário tem estas dependências:</span><span class="sxs-lookup"><span data-stu-id="de74f-193">The scenario has these dependencies:</span></span>

+ <span data-ttu-id="de74f-194">Uma Ordem de Produção deve estar sendo executada em uma máquina mapeada para que um alerta seja disparado.</span><span class="sxs-lookup"><span data-stu-id="de74f-194">A Production Order must be running on a mapped machine for an alert to be triggered.</span></span>
+ <span data-ttu-id="de74f-195">Um sinal representando o sinal de saída de uma máquina mapeada deve ser enviado ao Hub IoT com um nome de propriedade exclusivo.</span><span class="sxs-lookup"><span data-stu-id="de74f-195">A signal representing a mapped machine's part out signal must be sent to the IoT Hub with a unique property name.</span></span>
+ <span data-ttu-id="de74f-196">Uma propriedade de carimbo de data/hora UNIX em milissegundos deve estar presente na mensagem do Hub IoT.</span><span class="sxs-lookup"><span data-stu-id="de74f-196">A Unix milliseconds timestamp property must be present in the IoT Hub message.</span></span>

## <a name="how-to-disable-a-scenario"></a><span data-ttu-id="de74f-197">Como desabilitar um cenário</span><span class="sxs-lookup"><span data-stu-id="de74f-197">How to disable a scenario</span></span>

<span data-ttu-id="de74f-198">Para desativar um cenário, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="de74f-198">To disable a scenario, follow these steps:</span></span>

1. <span data-ttu-id="de74f-199">Em Supply Chain Management, navegue até **Controle de produção \> Configuração \> Inteligência de IoT \> Gerenciamento de cenário**.</span><span class="sxs-lookup"><span data-stu-id="de74f-199">In Supply Chain Management, navigate to **Production control \> Setup \> IoT Intelligence \> Scenario management**.</span></span>
2. <span data-ttu-id="de74f-200">Clique em **Configurar** no cenário.</span><span class="sxs-lookup"><span data-stu-id="de74f-200">Click **Configure** on the scenario.</span></span>
3. <span data-ttu-id="de74f-201">Clique em **Avançar** para ir para a última guia do assistente.</span><span class="sxs-lookup"><span data-stu-id="de74f-201">Click **Next** to get to the last wizard tab.</span></span>
4. <span data-ttu-id="de74f-202">Ative o controle deslizante para desabilitar o cenário.</span><span class="sxs-lookup"><span data-stu-id="de74f-202">Toggle the slider to disable the scenario.</span></span>

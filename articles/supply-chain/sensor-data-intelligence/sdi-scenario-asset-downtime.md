---
title: O cenário de tempo de inatividade do ativo
description: Este artigo descreve o cenário de tempo de inatividade do ativo, que permite usar os dados do sensor para monitorar a disponibilidade de seus ativos.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreScenarioManagement, IoTIntCoreScenarioConfigurationWizardV2, EntAssetObjectProductionStop
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 944818557deebed06c02c00fd69de6e8f08bda83
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428296"
---
# <a name="the-asset-downtime-scenario"></a>O cenário de tempo de inatividade do ativo

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

O cenário do tempo de inatividade do ativo vai gerar um registro de tempo de inatividade de manutenção se nenhum sinal for recebido de uma máquina dentro de um limite de tempo definido desde que o último sinal foi recebido. O cenário requer que você equipe sua máquina com um sensor que envia periodicamente um sinal ao seu Hub IoT do Azure enquanto o computador está operando, mas não envia um sinal quando a máquina não está operando.

## <a name="set-up-the-asset-downtime-scenario"></a>Configurar o cenário de tempo de inatividade do ativo

Siga estas etapas para configurar o cenário de *tempo de inatividade do ativo* no Supply Chain Management.

1. Vá até **Gerenciamento de ativos \> Configuração \> Sensor Data Intelligence \> Cenários** para abrir a página **Cenários**.
2. Na caixa de cenário **Tempo de inatividade do ativo**, selecione **Configurar** para abrir o assistente para configuração desse cenário.
3. Na página **Sensores**, selecione **Novo** para adicionar um sensor à grade. Em seguida, defina os seguintes campos:

    - **ID do sensor** – Insira o ID do sensor que você está usando. (Se estiver usando o Raspberry PI Azure IoT Online Simulator e o tiver configurado como descrito em [Configurar um sensor simulado para teste](sdi-set-up-simulated-sensor.md), digite *AssetDownTime*.)
    - **Descrição do sensor** – Insira uma descrição do sensor.

4. Repita a etapa anterior para cada sensor adicional que deseja adicionar agora. Você pode voltar e adicionar mais sensores a qualquer momento.
5. Selecione **Avançar**.
6. Na página **Mapeamento de registros comerciais**, na seção **Sensores**, selecione o registro de um dos sensores que você acabou de adicionar.
7. Na seção **Mapeamento de registros comerciais**, selecione **Novo** para adicionar uma linha à grade.
8. Na nova linha, defina o campo **Registro comercial** como o recurso que você está usando para monitorar o sensor selecionado. (Se estiver usando os dados de demonstração, selecione *AK-101, faca aérea para linha 1*.)
9. Selecione **Avançar**.
10. Na página **Limite de tempo de inatividade do ativo**, defina por quanto tempo o sistema deverá esperar antes de enviar uma notificação de tempo de inatividade do ativo. Há duas maneiras de definir o limite:

    - **Limite padrão (minutos)** – Defina este campo para definir o limite padrão. Esse valor se aplica a todos os recursos nos quais o campo **Limite de notificação (minutos)** está definido como dois minutos ou menos. O valor mínimo é *2* (minutos).
    - **Limite para determinar se a máquina não está respondendo (minutos)** – Para cada recurso na grade em que não deseja usar o limite padrão, insira um valor de substituição neste campo. Os recursos definidos para usar um limite de dois minutos ou menos usarão a configuração **Limite padrão (minutos)**.
11. Selecione **Avançar**.
12. Na página **Ativar sensores**, na grade, selecione o sensor configurado e selecione **Ativar**. Para cada sensor ativado na grade, uma marca de seleção aparece na coluna **Ativa**.
13. Selecione **Concluir**.

## <a name="work-with-the-asset-downtime-scenario"></a>Trabalhar com o cenário de tempo de inatividade do ativo

Se nenhum sinal de sensor for recebido de um ativo dentro do limite definido na configuração do cenário, o sistema criará um registro de tempo de inatividade de manutenção para o ativo. Os gerentes devem rever periodicamente os registros de tempo de inatividade (por exemplo, uma vez em cada turno de trabalho) e aplicar os códigos de motivo e horários adequados para cada registro de tempo de inatividade. Siga estas etapas para exibir os registros de tempo de inatividade de manutenção de um ativo:

1. Acesse **Gerenciamento de ativos > Ativos > Todos os ativos**.
2. Encontre e selecione o ativo que você deseja inspecionar. (Se estiver usando os dados de demonstração, selecione *AK-101*.)
3. No Painel de ações, abra a guia **Ativo** e, no grupo **Ordem de serviço**, selecione **Tempo de inatividade de manutenção** para abrir a página de registros de tempo de inatividade de manutenção para o ativo selecionado.

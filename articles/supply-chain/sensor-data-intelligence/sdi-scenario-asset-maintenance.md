---
title: O cenário de manutenção do ativo
description: Este artigo descreve o cenário de manutenção de ativos, que permite usar os dados do sensor para criar registros de contador que rastreiam o uso de um ativo de máquina.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreScenarioManagement, IoTIntCoreScenarioConfigurationWizardV2, EntAssetCounter
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: ff3944b987314a688a5829b05f8627479e3e79ed
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428277"
---
# <a name="the-asset-maintenance-scenario"></a>O cenário de manutenção do ativo

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

O cenário de *manutenção de ativos* permite usar os dados do sensor para criar registros de contador. Os registros de contador rastreiam o uso de um ativo de máquina e são usados como entrada para gerar o agendamento de manutenção dos ativos de máquina.

## <a name="prepare-demo-data-for-the-asset-maintenance-scenario"></a>Preparar dados de demonstração para o cenário de manutenção de ativos

Se você deseja usar um sistema de demonstração para testar o cenário de *manutenção de ativos*, use um sistema no qual os [dados de demonstração](../../fin-ops-core/fin-ops/get-started/demo-data.md) estão instalados, selecione a entidade legal *USMF* (empresa) e prepare os dados de demonstração adicionais, conforme descrito nesta seção. Se você estiver usando seus próprios sensores e dados, poderá ignorar esta seção.

Nesta seção, você configurará o ativo *AK-101, Faca aérea* nos dados de demonstração como um exemplo. Em seguida, você verá como o trabalho de manutenção futuro pode ser previsto com base nos sinais de sensor que medem o número de horas que a faca aérea está sendo executada. Você também pode configurar um plano de manutenção em que a faca aérea deve ser inspecionada a cada 10.000 horas.

### <a name="set-up-a-sensor-simulator"></a>Configurar um simulador de sensor

Se desejar tentar esse cenário sem usar um sensor físico, você poderá configurar um simulador para gerar os sinais necessários. Para obter mais informações, consulte [Configurar um sensor simulado para teste](sdi-set-up-simulated-sensor.md).

### <a name="create-an-asset-counter-to-track-production-hours"></a>Criar um contador de ativos para rastrear horas de produção

Siga estas etapas para criar um contador de ativos para rastrear horas de produção.

1. Acesse **Gerenciamento de ativos \> Configuração \> Tipos de ativo \> Contadores**.
1. No Painel de ação, selecione **Novo** para criar um contador.
1. No cabeçalho, defina os seguintes valores:

    - **Contador:** *ProductionHr*
    - **Nome:** *Horas de produção*

1. Na FastTab **Geral**, defina os seguintes valores:

    - **Unidade:** *hr*
    - **Atualização:** *Manual*
    - **Agregado total** *Soma*

1. Na Guia Rápida **Tipos de ativo**, selecione **Adicionar linha**.
1. Na linha nova, defina o campo **Tipo de ativo** como *Faca aérea*.

### <a name="create-a-maintenance-plan-for-the-asset"></a>Criar um plano de manutenção para o ativo

Siga estas etapas para criar um plano de manutenção para o ativo.

1. Acesse **Gerenciamento de ativos \> Configuração \> Manutenção preventiva \> Plano de manutenção**.
1. No Painel de ação, selecione **Novo** para criar um plano de manutenção.
1. No cabeçalho, defina os seguintes valores:

    - **Plano de manutenção:** *AirKnife*
    - **Nome:** *plano para facas aéreas*

1. Na FastTab **Detalhes**, defina os seguintes valores:

    - **Data do plano**: insira a data de hoje.
    - **Ativo:** *Sim*

1. Na Guia Rápida **Linhas**, selecione **Adicionar linha do contador de ativos** para adicionar uma linha à grade. Depois, defina os seguintes valores para ele:

    - **Descrição da ordem de serviço:** *manutenção para faca aérea*
    - **Tipo de trabalho de manutenção:** *preventivo*
    - **Tipo de intervalo:** *Repetido a partir da última ordem de serviço*
    - **Frequência do período:** *10000*
    - **Contador:** *ProductionHr*

## <a name="set-up-the-asset-maintenance-scenario"></a>Configurar o cenário de manutenção do ativo

Siga estas etapas para configurar o cenário de *manutenção do ativo* no Supply Chain Management.

1. Vá até **Gerenciamento de ativos \> Configuração \> Sensor Data Intelligence \> Cenários**.
1. Na caixa de cenário **Manutenção do ativo**, selecione **Configurar** para abrir o assistente para configuração desse cenário.
1. Na página **Sensores**, selecione **Novo** para adicionar um sensor à grade. Em seguida, defina os seguintes campos:

    - **ID do sensor** – Insira o ID do sensor que você está usando. (Se estiver usando o Raspberry PI Azure IoT Online Simulator e o tiver configurado como descrito em [Configurar um sensor simulado para teste](sdi-set-up-simulated-sensor.md), digite *AssetMaintenance*.)
    - **Descrição do sensor** – Insira uma descrição do sensor.

1. Repita a etapa anterior para cada sensor adicional que deseja adicionar agora. Você pode voltar e adicionar mais sensores a qualquer momento.
1. Selecione **Avançar**.
1. Na página **Mapeamento de registros comerciais**, na seção **Sensores**, selecione o registro de um dos sensores que você acabou de adicionar.
1. Na seção **Mapeamento de registros comerciais**, selecione **Novo** para adicionar uma linha à grade.
1. Na nova linha, o campo **Tipo de registro comercial** deve ser automaticamente definido como *Assets(EntAssetObjectTable)*. Defina o campo **Registro comercial** como o recurso que você está usando para monitorar o sensor selecionado. (Se estiver usando os dados de demonstração criados anteriormente neste artigo, defina-o como *AK-101, AK-101 faca aérea para a linha 1*.)
1. Imediatamente depois de selecionar um tipo de registro comercial para a linha que você adicionou na etapa anterior, uma segunda linha é adicionada automaticamente à grade. Nessa linha, o campo **Tipo de registro comercial** deve ser definido como *Counters(EntAssetCounterType)*. Defina o campo **Registro comercial** como o contador de ativos que está sendo atualizado com base nos sinais do sensor selecionado. (Se estiver usando os dados de demonstração criados anteriormente neste artigo, defina-o como *ProductionHr, Horas de produção*.)
1. Selecione **Avançar**.
1. Na página **Ativar sensores**, na grade, selecione o sensor adicionado e selecione **Ativar**. Para cada sensor ativado na grade, uma marca de seleção aparece na coluna **Ativa**.
1. Selecione **Concluir**.

## <a name="work-with-the-asset-maintenance-scenario"></a>Trabalhar com o cenário de manutenção do ativo

### <a name="view-counter-values"></a>Exibir valores do contador

Depois que os dados são preparados e o cenário de *manutenção de ativos* é configurado e ativado, você pode ver como os registros de um contador de ativos são inseridos com base nos dados do sensor.

1. Acesse **Gerenciamento de ativos \> Ativos \> Todos os ativos**.
1. Encontre e selecione o ativo que você deseja inspecionar. (Se estiver usando os dados de demonstração criados anteriormente neste artigo, selecione *AK-101*.)
1. No Painel de ação, na guia **Ativo**, no grupo **Preventivo**, selecione **Contadores** para abrir a página para registros de contador para o ativo *AK-101*.

### <a name="generate-maintenance-work-orders"></a>Gerar ordens de serviço de manutenção

Depois de habilitar o cenário de *manutenção de ativos* e configurar o plano de manutenção, você pode executar o agendamento de manutenção para gerar ordens de serviço de manutenção. Para obter mais informações sobre como trabalhar com manutenção preventiva, consulte [Visão geral da manutenção preventiva](../asset-management/preventive-and-reactive-maintenance/preventive-maintenance-overview.md).

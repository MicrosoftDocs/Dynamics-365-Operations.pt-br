---
title: O cenário de status da máquina
description: Este artigo descreve o cenário de status da máquina, que permite usar os dados do sensor para monitorar a disponibilidade de seu equipamento.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreScenarioManagement, IoTIntCoreNotification, IoTIntMfgResourceStatusConfiguration, IoTIntMfgResourceStatus
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 1f2b424dccf1963a7917059d412b5df7937496ee
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428278"
---
# <a name="the-machine-status-scenario"></a>O cenário de status da máquina

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

O cenário de *status da máquina* permite usar os dados do sensor para monitorar a disponibilidade de seu equipamento. Se você configurar um sensor que envie um sinal quando um trabalho de produção em um recurso de máquina produz saída, mas nenhum sinal de sensor é recebido em um intervalo especificado, uma notificação será exibida no painel do supervisor.

## <a name="scenario-dependencies"></a>Dependências de cenário

O cenário de *status da máquina* tem as seguintes dependências:

- Uma notificação só poderá ser disparada se um trabalho de produção estiver em andamento em uma máquina mapeada.
- Um sinal que representa uma *peça produzida* deve ser enviada ao hub IoT.

## <a name="prepare-demo-data-for-the-machine-status-scenario"></a>Preparar dados de demonstração para o cenário de status da máquina

Se você deseja usar um sistema de demonstração para testar o cenário de *status da máquina*, use um sistema no qual os [dados de demonstração](../../fin-ops-core/fin-ops/get-started/demo-data.md) estão instalados, selecione a entidade legal *USMF* (empresa) e prepare os dados de demonstração adicionais, conforme descrito nesta seção. Se você estiver usando seus próprios sensores e dados, poderá ignorar esta seção.

### <a name="set-up-a-sensor-simulator"></a>Configurar um simulador de sensor

Se desejar tentar esse cenário sem usar um sensor físico, você poderá configurar um simulador para gerar os sinais necessários. Para obter mais informações, consulte [Configurar um sensor simulado para teste](sdi-set-up-simulated-sensor.md).

### <a name="verify-that-resource-3118-is-used-for-product-p0111"></a>Verifique se o recurso 3118 é usado para o produto P0111

Uma ordem de produção será programada e liberada. Portanto, um trabalho de produção é liberado para o recurso *3118* (*Máquina de corte de espuma*). Siga estas etapas para verificar se o recurso *3118* é usado para o produto *P0111* nos seus dados de demonstração.

1. Acesse **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
1. Encontre e selecione o produto no qual o campo **Número do item** esteja definido como *P0111*.
1. No Painel de ação, na guia **Engenharia**, no grupo **Exibir**, selecione **Rota**.
1. Na página **Rota**, na guia **Visão geral** na parte inferior da página, selecione a linha na qual o campo **Nº** Oper. esteja definido como *30*.
1. Na guia **Requisitos de recursos**, na parte inferior da página, verifique se o recurso *3118* (*Máquina de corte de espuma*) está associado à operação.

### <a name="create-and-release-a-production-order-for-product-p0111"></a>Crie e libere uma ordem de produção para o produto P0111

Siga estas etapas para criar e liberar uma ordem de produção para o produto *P0111*.

1. Acesse **Controle de produção \> Ordens de produção \> Todas ordens de produção**.
1. Na página **Todas as ordens de produção**, no Painel de ação, selecione **Nova ordem de lote**.
1. Na caixa de diálogo **Criar lote**, defina os seguintes valores:

    - **Número de item:** *P0111*
    - **Quantidade:** *10*

1. Selecione **Criar** para criar a ordem e retornar à página **Todas as ordens de produção**.
1. Use o campo **Filtro** para procurar ordens de produção nas quais o campo **Número do item** esteja definido como *P0111*. Depois, encontre e selecione a ordem de produção que você criou.
1. No Painel de Ações, na guia **Ordem de produção**, no grupo **Processo**, selecione **Estimar**.
1. Na caixa de diálogo **Estimativa**, selecione **OK** para executar a estimativa.
1. No Painel de ações, na guia **Ordem de produção**, no grupo **Processo**, selecione **Liberar**.
1. Na caixa de diálogo **Liberar**, anote o número da ordem de lote que acabou de criar.
1. Selecione **OK** para liberar a ordem.

### <a name="configure-the-production-floor-execution-interface"></a><a name="config-pfe"></a>Configurar a interface de execução de piso de produção

Você usará a interface de execução de chão de produção para iniciar o trabalho que foi programado e liberado para o número de item *P0111* na seção anterior. Siga estas etapas para configurar a interface de execução de chão de produção.

1. Acesse **Controle de produção \> Execução de fabricação \> Execução de piso de produção**.
1. Se você não tiver configurado anteriormente a interface, será exibida uma página de entrada. Insira suas credenciais.
1. Na página de boas-vindas, selecione **Configurar** para abrir o assistente para **Configurar dispositivo**.
1. Na página **Configurar dispositivo - Etapa 1 - Selecionar configuração**, selecione a configuração *Padrão*.
1. Selecione **Avançar**.
1. Na página **Configurar dispositivo - Etapa 2 - Definir a área de chão de produção**, defina o campo **Recurso** como *3118*.
1. Selecione **OK**.

### <a name="enable-the-search-option-in-the-production-floor-execution-interface"></a><a name="enable-pfe-search"></a>Habilitar a opção de pesquisa na interface de execução de chão de produção

Para facilitar a localização do trabalho de produção para a ordem de produção que foi liberada anteriormente, siga estas etapas para habilitar a opção de pesquisa na interface de execução de chão de produção.

1. Acesse **Controle de produção \> Configuração \> Execução de fabricação \> Configurar execução de piso de produção**.
1. Selecione a configuração *Padrão*.
1. No Painel de Ações, selecione **Editar**.
1. Na Guia Rápida **Geral**, defina a opção **Habilitar pesquisa** como *Sim*.
1. Feche a página.

### <a name="start-the-first-job-in-the-batch-order"></a>Iniciar o primeiro trabalho na ordem de lote

Siga estas etapas para iniciar o trabalho programado no recurso *3118*.

1. Acesse **Controle de produção \> Execução de fabricação \> Execução de piso de produção**.
1. No campo **ID da notificação**, insira *123*. Em seguida, selecione **Entrar**.
1. Se um motivo de ausência for solicitado, selecione um dos cartões para ausência e selecione **OK**.
1. No campo **Pesquisa**, insira o número da ordem de lote para o qual você fez uma observação anteriormente. Em seguida, selecione a chave de **Devolução**.
1. Selecione a ordem e **Iniciar trabalho**.
1. Na caixa de diálogo **Iniciar trabalho**, selecione **Iniciar**.

## <a name="set-up-the-machine-status-scenario"></a>Configurar o cenário de status da máquina

Siga estas etapas para configurar o cenário de *status da máquina* no Supply Chain Management.

1. Acesse **Controle de produção \> Configuração \> Sensor Data Intelligence \> Cenários**.
1. Na caixa de cenário **Status da máquina**, selecione **Configurar** para abrir o assistente para configuração desse cenário.
1. Na página **Sensores**, selecione **Novo** para adicionar um sensor à grade. Em seguida, defina os seguintes campos:

    - **ID do sensor** – Insira o ID do sensor que você está usando. (Se estiver usando o Raspberry PI Azure IoT Online Simulator e o tiver configurado como descrito em [Configurar um sensor simulado para teste](sdi-set-up-simulated-sensor.md), digite *MachineStatus*.)
    - **Descrição do sensor** – Insira uma descrição do sensor.

1. Repita a etapa anterior para cada sensor adicional que deseja adicionar agora. Você pode voltar e adicionar mais sensores a qualquer momento.
1. Selecione **Avançar**.
1. Na página **Mapeamento de registros comerciais**, na seção **Sensores**, selecione o registro de um dos sensores que você acabou de adicionar.
1. Na seção **Mapeamento de registros comerciais**, selecione **Novo** para adicionar uma linha à grade.
1. Na nova linha, defina o campo **Registro comercial** como o recurso que você está usando para monitorar o sensor selecionado. (Se estiver usando os dados de demonstração criados anteriormente neste artigo, defina o campo como *3118, Máquina de corte de espuma*.)
1. Selecione **Avançar**.
1. Na página **Limite de status da máquina**, defina por quanto tempo o sistema deverá enviar uma notificação de status da máquina depois do último sinal de *peça produzida*. Há duas maneiras de definir o limite:

    - **Limite padrão (minutos)** – Defina este campo para definir o limite padrão. O valor será aplicado a todos os recursos em que o campo **Limite para determinar que a máquina não responde (minutos)** está definido como dois minutos ou menos. O valor mínimo é *2* (minutos).
    - **Limite para determinar se a máquina não está respondendo (minutos)** – Para cada recurso na grade em que não deseja usar o limite padrão, insira um valor de substituição neste campo. Os recursos definidos para usar um limite de dois minutos ou menos usarão a configuração **Limite padrão (minutos)**.

    > [!NOTE]
    > Normalmente, você usará um sinal de *peça produzida* para monitorar o status da máquina. Portanto, você deve verificar se o limite de cada recurso da máquina é maior do que a máquina requer para a produção de cada peça.

1. Selecione **Avançar**.
1. Na página **Ativar sensores**, na grade, selecione o sensor adicionado e selecione **Ativar**. Para cada sensor ativado na grade, uma marca de seleção aparece na coluna **Ativa**.
1. Selecione **Concluir**.

## <a name="work-with-the-machine-status-scenario"></a>Trabalhar com o cenário de status da máquina

Depois de instalar os sensores e configurar o cenário, você pode exibir os eventos de status da máquina no Supply Chain Management. Esta seção descreve onde e como exibir essas informações.

### <a name="view-machine-status-data-on-the-resource-status-page"></a>Exibir dados de status da máquina na página Status do recurso

Na página **Status do recurso**, os supervisores podem monitorar uma linha do tempo do sinal de *peça produzida* recebido dos sensores mapeados para cada recurso da máquina. Siga essas etapas para configurar a linha do tempo.

1. Vá para **Controle de produção \> Execução de fabricação \> Status do recurso**.
1. Na caixa de diálogo **Configurar**, defina os campos a seguir:

    - **Recurso** – Selecione os recursos que deseja monitorar. (Se estiver trabalhando com os dados de demonstração, selecione *3118*.)
    - **Série temporal 1** – Selecione o registro (chave métrica) que tem o seguinte formato para o nome: *MachineReportingStatus:&lt;Sensor&gt;*
    - **Nome de exibição** – Insira o *sinal de peça produzida*.

A ilustração a seguir mostra um exemplo de dados de status da máquina na página **Status do recurso** durante a operação padrão.

![Dados de status da máquina na página Status do recurso durante a operação padrão.](media/sdi-resource-status-downtime-up.png "Dados de status da máquina na página Status do recurso durante a operação padrão")

A ilustração a seguir mostra um exemplo de dados de status da máquina quando um tempo de inatividade é detectado.

![Dados de status da máquina na página Status do recurso quando o tempo de inatividade for detectado.](media/sdi-resource-status-downtime-down.png "Dados de status da máquina na página Status do recurso quando o tempo de inatividade for detectado")

### <a name="view-machine-status-on-the-notifications-page"></a>Exibir o status da máquina na página Notificações

Na página **Notificações**, os supervisores podem exibir as notificações geradas quando se passa muito tempo desde o último sensor ter fornecido um sinal de *peça produzida*. Cada notificação fornece uma visão geral do trabalho de produção afetado pela interrupção e concede a opção de reatribuir o trabalho afetado a outro recurso.

Para abrir a página **Notificação**, vá para **Controle de produção \> Consultas e relatórios \> Sensor Data Intelligence \> Notificações**.

A ilustração a seguir mostra um exemplo de uma notificação de status da máquina.

![Exemplo de uma notificação de status da máquina.](media/sdi-resource-status-downtime-notification.png "Exemplo de uma notificação de status da máquina")

---
title: O cenário de atrasos de produção
description: Este artigo descreve o cenário de atrasos de produção, que vai gerar uma notificação se a taxa de transferência da produção ficar abaixo de um valor limite específico.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreScenarioManagement, IoTIntCoreScenarioConfigurationWizardV2, IoTIntMfgResourceStatusConfiguration, IoTIntMfgResourceStatus
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 25ccbda1628544f14dc32d9bea3f2162ad47d79e
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690012"
---
# <a name="the-production-delays-scenario"></a>O cenário de atrasos de produção

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

O cenário de *atrasos de produção* vai gerar uma notificação se a taxa de transferência da produção ficar abaixo de um valor limite específico. Neste cenário, um sinal de *peça produzida* é enviado ao Hub IoT Microsoft Azure para cada item produzido. No Dynamics 365 Supply Chain Management, o atraso da ordem é calculado com base em: o tempo que a ordem de produção está agendada para ser executada, o número de itens que devem ser gerados, o período em que o trabalho está em execução e o número de sinais de *peça produzida* recebidos. Uma notificação de atraso será gerada se o número de sinais de *peça produzida* do trabalho ficar abaixo do valor limite.

## <a name="scenario-dependencies"></a>Dependências de cenário

O cenário de *atrasos de produção* tem as seguintes dependências:

- Um alerta só poderá ser disparado se uma ordem de produção estiver em execução em uma máquina mapeada.
- Um sinal que representa o sinal de *peça produzida* de uma máquina mapeada deve ser enviado ao Hub IoT e um nome de propriedade exclusivo deve ser incluído.
- Uma propriedade carimbo de data/hora do UNIX, em que o valor é expresso em milissegundos (ms), deve estar presente na mensagem do Hub IoT do Azure.

## <a name="prepare-demo-data-for-the-product-delays-scenario"></a>Preparar dados de demonstração para o cenário de atrasos de produção

Se você deseja usar um sistema de demonstração para testar o cenário de *atrasos de produção*, use um sistema no qual os [dados de demonstração](../../fin-ops-core/fin-ops/get-started/demo-data.md) estão instalados, selecione a entidade legal *USMF* (empresa) e prepare os dados de demonstração adicionais, conforme descrito nesta seção. Se você estiver usando seus próprios sensores e dados, poderá ignorar esta seção.

### <a name="set-up-sensor-simulator"></a>Configurar simulador de sensor

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

### <a name="configure-the-production-floor-execution-interface"></a>Configurar a interface de execução de piso de produção

Se ainda não tiver feito isso, configure a interface de execução de chão de produção para mostrar os trabalhos atribuídos ao recurso *3118* (*Máquina de corte de espuma*). Para obter instruções, consulte estas seções:

- [Configurar a interface de execução de piso de produção](sdi-scenario-equipment-downtime.md#config-pfe)
- [Habilitar a opção de pesquisa na interface de execução de chão de produção](sdi-scenario-equipment-downtime.md#enable-pfe-search)

### <a name="start-the-first-job-in-the-batch-order"></a>Iniciar o primeiro trabalho na ordem de lote

Siga estas etapas para iniciar o primeiro trabalho na ordem de lotes.

1. Acesse **Controle de produção \> Execução de fabricação \> Execução de piso de produção**.
1. No campo **ID da notificação**, insira *123*. Em seguida, selecione **Entrar**.
1. Se um motivo de ausência for solicitado, selecione um dos cartões para ausência e selecione **OK**.
1. No campo **Pesquisa**, insira o número da ordem de lote para o qual você fez uma observação anteriormente. Em seguida, selecione a chave de **Devolução**.
1. Selecione a ordem e **Iniciar trabalho**.
1. Na caixa de diálogo **Iniciar trabalho**, selecione **Iniciar**.

## <a name="set-up-the-production-delays-scenario"></a>Configurar o cenário de atrasos de produção

Siga estas etapas para configurar o cenário de *atrasos de produção* no Supply Chain Management.

1. Acesse **Controle de produção \> Configuração \> Sensor Data Intelligence \> Cenários**.
1. Na caixa de cenário **Atrasos de produção**, selecione **Configurar** para abrir o assistente para configuração desse cenário.
1. Na página **Sensores**, selecione **Novo** para adicionar um sensor à grade. Em seguida, defina os seguintes campos:

    - **ID do sensor** – Insira o ID do sensor que você está usando. (Se estiver usando o Raspberry PI Azure IoT Online Simulator e o tiver configurado como descrito em [Configurar um sensor simulado para teste](sdi-set-up-simulated-sensor.md), digite *ProductionDelay*.)
    - **Descrição do sensor** – Insira uma descrição do sensor.

1. Repita a etapa anterior para cada sensor adicional que deseja adicionar agora. Você pode voltar e adicionar mais sensores a qualquer momento.
1. Selecione **Avançar**.
1. Na página **Mapeamento de registros comerciais**, na seção **Sensores**, selecione o registro de um dos sensores que você acabou de adicionar.
1. Na seção **Mapeamento de registros comerciais**, selecione **Novo** para adicionar uma linha à grade.
1. Na nova linha, defina **Registro comercial** como o recurso que você está usando para monitorar o sensor selecionado. (Se estiver usando os dados de demonstração criados anteriormente neste artigo, defina-o como *3118, Máquina de corte de espuma*.)
1. Selecione **Avançar**.
1. Na página **Limite do desvio do atraso de produção**, se você estiver usando os dados de demonstração criados anteriormente neste artigo, siga estas etapas:

    1. Selecione o título da coluna **Relação de itens** para abrir uma caixa de diálogo suspensa que inclua filtros de pesquisa para a coluna. Digite *P0111* na caixa de pesquisa e selecione **Aplicar**.
    2. Selecione a linha na qual o campo **Operação** está definido como *Aparar/Cortar*. Defina o campo **Limite de notificação para o atraso (%)** como o limite (como uma porcentagem) em que uma notificação deve ser enviada.

1. Selecione **Avançar**.
1. Na página **Ativar sensores**, na grade, selecione o sensor adicionado e selecione **Ativar**. Para cada sensor ativado na grade, uma marca de seleção aparece na coluna **Ativa**.
1. Selecione **Concluir**.

## <a name="work-with-the-production-delays-scenario"></a>Trabalhar com o cenário de atrasos de produção

### <a name="view-production-delay-data-on-the-resource-status-page"></a>Exibir dados de atraso de produção na página Status do recurso

Na página **Status do recurso**, os supervisores podem monitorar uma linha dos sinais recebidos dos sensores mapeados para cada recurso da máquina. Siga essas etapas para configurar a linha do tempo.

1. Vá para **Controle de produção \> Execução de fabricação \> Status do recurso**.
1. Na caixa de diálogo **Configurar**, defina os campos a seguir:

    - **Recurso** – Selecione os recursos que deseja monitorar. (Se estiver trabalhando com os dados de demonstração, selecione *3118*.)
    - **Série temporal 1** – Selecione o registro (chave métrica) que tem o seguinte formato para o nome: *ProductionJobDelayed:ActualQuantity:&lt;JobId&gt;*
    - **Nome de exibição** – Insira o *sinal de peça produzida*.

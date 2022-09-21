---
title: O cenário de qualidade do produto
description: Este artigo fornece informações sobre o cenário de qualidade do produto. Esse cenário usa um sensor para medir a qualidade de um lote de produtos e gerará um alerta se uma medida estiver fora de um limite definido.
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
ms.openlocfilehash: 8c4808ea3a0389c2a8699f0e11ea154705a6916d
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428289"
---
# <a name="the-product-quality-scenario"></a>O cenário de qualidade do produto

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

No cenário de *qualidade do produto*, um sensor é configurado para medir a qualidade de um lote de produtos no chão de fábrica. Se uma medida ficar fora de um limite definido para o produto, uma notificação será mostrada no painel do supervisor. Por exemplo, um sensor está medindo a umidade de um produto alimentício que sai da linha de produção. Se a medição estiver fora do valor mínimo ou máximo permitido para a umidade do produto, uma notificação será gerada.

## <a name="scenario-dependencies"></a>Dependências de cenário

O cenário de *qualidade do produto* tem as seguintes dependências:

- Um alerta poderá ser disparado apenas se uma ordem de produção estiver em execução em uma máquina mapeada e se essa máquina estiver gerando um produto com um atributo de lote mapeado.
- Um sinal que representa o atributo de lote deve ser enviado ao Hub IoT e um nome de propriedade exclusivo deve ser incluído.

## <a name="prepare-demo-data-for-the-product-quality-scenario"></a>Preparar dados de demonstração para o cenário de qualidade do produto

Se você deseja usar um sistema de demonstração para testar o cenário de *qualidade do produto*, use um sistema no qual os [dados de demonstração](../../fin-ops-core/fin-ops/get-started/demo-data.md) estão instalados, selecione a entidade legal *USMF* (empresa) e prepare os dados de demonstração adicionais, conforme descrito nesta seção. Se você estiver usando seus próprios sensores e dados, poderá ignorar esta seção.

Nesta seção, você configurará os dados de demonstração para que possa usar o produto liberado *P0111* (*Caso composto*) com o cenário de *qualidade do produto*. Neste cenário, o sistema controla se um valor de atributo de lote que é medido por um sensor está fora do limite definido para um atributo de lote associado ao produto.

### <a name="set-up-a-sensor-simulator"></a>Configurar um simulador de sensor

Se desejar tentar esse cenário sem usar um sensor físico, você poderá configurar um simulador para gerar os sinais necessários. Para obter mais informações, consulte [Configurar um sensor simulado para teste](sdi-set-up-simulated-sensor.md).

### <a name="associate-a-batch-attribute-and-resource-with-product-p0111"></a>Associar um atributo de lote e um recurso ao produto P0111

Siga estas etapas para associar um atributo de lote ao produto *P0111* (*Caso composto*) e verifique se o recurso *3118* (*Máquina de corte de espuma*) é usado para ele.

1. Acesse **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
1. Encontre e selecione o produto no qual o campo **Número do item** esteja definido como *P0111*.
1. No Painel de ação, na guia **Gerenciar estoque**, no grupo **Atributos de lotes**, selecione **Específico do produto**.
1. Na página **Específico do produto**, selecione **Novo** para criar um atributo de lote específico do produto.
1. No cabeçalho, defina os seguintes campos:

    - **Código do atributo** – Selecione o escopo dos atributos que serão monitorados (*Tabela*, *Grupo* ou *Tudo*). Neste cenário, selecione *Tabela*, porque você sempre monitorará um único atributo.
    - **Relação de atributos** – Selecione o atributo para o qual você usará o cenário de *qualidade do produto* para monitorar o valor. Para este exemplo, selecione *Concentração*, que é um atributo incluído nos dados de demonstração padrão.

1. Na Guia Rápida **Valores**, nos campos **Mínimo** e **Máximo**, defina o intervalo de valores aceitáveis que o atributo deve relatar para passar na verificação de qualidade. Se o sensor relatar um valor fora desse intervalo, o sistema o identificará como uma violação de qualidade. Os outros campos dessa Guia Rápida não são relevantes para o cenário de *qualidade do produto*. Os valores padrão que você vê no momento são provenientes dos dados de demonstração. Portanto, deixe-os como estão e feche a página **Específico do produto** para retornar à página **Detalhes do produto liberado** para o item *P0111*.
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

## <a name="set-up-the-product-quality-scenario"></a>Configurar o cenário de qualidade do produto

Siga estas etapas para configurar o cenário de *qualidade do produto* no Supply Chain Management.

1. Acesse **Controle de produção \> Configuração \> Sensor Data Intelligence \> Cenários**.
1. Na caixa de cenário **Qualidade do produto**, selecione **Configurar** para abrir o assistente para configuração desse cenário.
1. Na página **Sensores**, selecione **Novo** para adicionar um sensor à grade. Em seguida, defina os seguintes campos:

    - **ID do sensor** – Insira o ID do sensor que você está usando. (Se estiver usando o Raspberry PI Azure IoT Online Simulator e o tiver configurado como descrito em [Configurar um sensor simulado para teste](sdi-set-up-simulated-sensor.md), digite *Quality*.)
    - **Descrição do sensor** – Insira uma descrição do sensor.

1. Repita a etapa anterior para cada sensor adicional que deseja adicionar agora. Você pode voltar e adicionar mais sensores a qualquer momento.
1. Selecione **Avançar**.
1. Na página **Mapeamento de registros comerciais**, na seção **Sensores**, selecione o registro de um dos sensores que você acabou de adicionar.
1. Na seção **Mapeamento de registros comerciais**, selecione **Novo** para adicionar uma linha à grade.
1. Na nova linha, o campo **Tipo de registro comercial** deve ser automaticamente definido como *Resources(WrkCtrTable)*. Defina o campo **Registro comercial** como o recurso que você está usando para monitorar o sensor selecionado. (Se estiver usando os dados de demonstração criados anteriormente neste artigo, defina-o como *3118, Máquina de corte de espuma*.)
1. Imediatamente depois de selecionar um tipo de registro comercial para a linha que você adicionou na etapa anterior, uma segunda linha é adicionada automaticamente à grade. Nessa linha, o campo **Tipo de registro comercial** deve ser definido como *Batch attributes(PdsBatchAttrib)*. Defina o campo **Registro comercial** como o atributo de lote que você está usando para monitorar o sensor selecionado. (Se estiver usando os dados de demonstração criados anteriormente neste artigo, defina-o como *Concentração, porcentagem de concentração*.)
1. Selecione **Avançar**.
1. Na página **Ativar sensores**, na grade, selecione o sensor adicionado e selecione **Ativar**. Para cada sensor ativado na grade, uma marca de seleção aparece na coluna **Ativa**.
1. Selecione **Concluir**.

## <a name="work-with-the-product-quality-scenario"></a>Trabalhar com o cenário de qualidade do produto

### <a name="view-product-quality-data-on-the-resource-status-page"></a>Exibir dados de qualidade do produto na página Status do recurso

Na página **Status do recurso**, os supervisores podem monitorar uma linha do tempo do sinal de qualidade do produto recebido dos sensores mapeados para cada recurso da máquina. Siga essas etapas para configurar a linha do tempo.

1. Vá para **Controle de produção \> Execução de fabricação \> Status do recurso**.
1. Na caixa de diálogo **Configurar**, defina os campos a seguir:

    - **Recurso** – Selecione os recursos que deseja monitorar. (Se estiver trabalhando com os dados de demonstração, selecione *3118*.)
    - **Série temporal 1** – Selecione o registro (chave métrica) que tem o seguinte formato para o nome: *ProductQuality:&lt;JobId&gt;:&lt;AttributeName&gt;*
    - **Nome de exibição** – Insira os *Valores de atributo de lote*.

A ilustração a seguir mostra um exemplo de dados de qualidade do produto na página **Status do recurso** quando o valor está no intervalo de valores aceitáveis.

![Dados de qualidade do produto na página Status do recurso quando o valor estiver no intervalo.](media/sdi-product-quality-in-range.png "Dados de qualidade do produto na página Status do recurso quando o valor estiver no intervalo")

A ilustração a seguir mostra um exemplo de dados de qualidade do produto quando um valor fora do intervalo é detectado.

![Dados de qualidade do produto na página Status do recurso quando um valor fora do intervalo é detectado.](media/sdi-product-quality-out-of-range.png "Dados de qualidade do produto na página Status do recurso quando um valor fora do intervalo é detectado")

### <a name="view-product-quality-data-on-the-notifications-page"></a>Exibir dados de qualidade do produto na página Notificações

Na página **Notificações**, os supervisores podem exibir as notificações geradas quando o sensor mede um valor de atributo de lote que está fora do limite definido para o atributo de lote. Cada notificação fornece uma visão geral do trabalho de produção afetado pela interrupção e concede a opção de reatribuir o trabalho afetado a outro recurso.

Para abrir a página **Notificação**, vá para **Controle de produção \> Consultas e relatórios \> Sensor Data Intelligence \> Notificações**.

A ilustração a seguir mostra um exemplo de uma notificação de qualidade do produto.

![Exemplo de uma notificação de qualidade do produto.](media/sdi-product-quality-notification.png "Exemplo de uma notificação de qualidade do produto")

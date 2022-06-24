---
title: Configuração da previsão de demanda
description: Este artigo descreve as tarefas de configuração que devem ser executadas para preparar a previsão de demanda.
author: t-benebo
ms.date: 11/23/2021
ms.topic: article
ms.search.form: ReqDemPlanDefaultAlgorithmParameters, ReqDemPlanForecastParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 10a211e0e20f22dfbfdb4923841808750b6ed71b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8900992"
---
# <a name="demand-forecasting-setup"></a>Configuração da previsão de demanda

[!include [banner](../includes/banner.md)]

Este artigo descreve como configurar a previsão de demanda.  

## <a name="item-allocation-keys"></a>Chaves de alocação de itens

As chaves de alocação de itens estabelecem grupos de itens. Uma previsão de demanda será calculada para um item e suas dimensões somente se o item fizer parte de uma chave de alocação de item. A regra é imposta agrupar grandes números de itens, para que as previsões de demanda possam ser criadas mais rapidamente. As previsões são criadas com base em dados históricos apenas.

Um item e suas dimensões devem ser parte de apenas uma chave de alocação de item, caso a chave de alocação de item seja usada durante a criação da previsão.

Para criar chaves de alocação de itens e adicionar uma unidade de manutenção de estoque (SKU) a elas, siga estas etapas.

1. Acesse **Planejamento mestre \> Configuração \> Previsão de demanda \> Chaves de alocação de itens**.
1. Selecione uma chave de alocação de item no painel de lista ou selecione **Novo** no Painel de Ações para criar uma nova. No cabeçalho para a chave nova ou selecionada, defina os seguintes campos:

    - **Chave de alocação de item** – Insira um nome exclusivo para a chave.
    - **Nome** – Insira um nome descritivo para a chave.

1. Siga uma destas etapas para adicionar itens à chave de alocação de itens selecionada ou remover itens:

    - Na guia rápida **Alocação de itens**, use os botões **Novo** e **Excluir** na barra de ferramentas para adicionar ou remover itens conforme necessário. Para cada linha, selecione o número do item e, em seguida, atribua os valores de dimensão nas outras colunas, conforme necessário. Selecione **Exibir dimensões** na barra de ferramentas para alterar o conjunto de colunas de dimensão mostrado na grade. (O valor na coluna **Porcentagem** é ignorado quando as previsões de demanda são geradas.)
    - Se desejar adicionar um grande número de itens à chave, selecione **Atribuir itens** no Painel de Ações para abrir uma página na qual você pode encontrar e atribuir vários itens à chave selecionada.

> [!IMPORTANT]
> Tome cuidado para incluir somente os itens relevantes em cada chave de alocação de itens. Itens desnecessários podem ocasionar o aumento dos custos quando você usa o Aprendizado de Máquina do Microsoft Azure.

## <a name="intercompany-planning-groups"></a>Grupos de planejamento intercompanhia

A previsão de demanda pode gerar previsões intercompanhia. No Dynamics 365 Supply Chain Management, as empresas que são planejadas juntas são colocadas no mesmo grupo de planejamento intercompanhia. Para especificar, por empresa, quais chaves de alocação de itens devem ser consideradas para a previsão de demanda, associe uma chave de alocação de itens ao membro do grupo de planejamento intercompanhia.

> [!IMPORTANT]
> No momento, a Otimização do Planejamento não oferece suporte a grupos de planejamento intercompanhia. Para fazer um planejamento intercompanhia que use a Otimização de Planejamento, configure trabalhos em lote do planejamento mestre que incluem planejamentos principais para todas as empresas relevantes.

Para configurar seus grupos de planejamento intercompanhia, siga estas etapas.

1. Acesse **Planejamento mestre \> Configuração \> Grupos de planejamento intercompanhia**.
1. Selecione um grupo de planejamento no painel de lista ou selecione **Novo** no Painel de Ações para criar um novo. No cabeçalho para o grupo novo ou selecionado, defina os seguintes campos:

    - **Nome** – Digite um nome exclusivo para grupo de planejamento.
    - **Descrição** – Insira uma breve descrição do grupo de planejamento.

1. Na guia rápida **Membros do grupo de planejamento intercompanhia**, use os botões na barra de ferramentas para adicionar uma linha para cada empresa (entidade legal) que deve fazer parte do grupo. Para cada linha, defina os seguintes campos:

    - **Entidade legal** – Selecione o nome de uma empresa (entidade legal) que seja membro do grupo selecionado.
    - **Sequência de planejamento** – Atribua a ordem em que a empresa deve ser processada em relação a outras empresas. Os valores baixos são processados primeiro. Essa ordem pode ser importante quando a demanda para uma empresa afeta outras empresas. Nesses casos, a empresa que fornece a demanda deve ser processada por último.
    - **Plano principal** – Selecione o plano principal a ser disparado para a empresa atual.
    - **Cópia automática para plano estático** – Marque esta caixa de seleção para copiar o resultado do plano para o plano estático.
    - **Cópia automática para plano dinâmico** – Marque esta caixa de seleção para copiar o resultado do plano para o plano dinâmico.

1. Por padrão, se nenhuma chave de alocação de item for atribuída aos membros do grupo de planejamento intercompanhia, uma previsão de demanda será calculada para todos os itens atribuídos a todas as chaves de alocação de item de todas as empresas. Opções de filtragem adicionais para empresas e chaves de alocação de itens estão disponíveis na caixa de diálogo **Gerar previsão estatística** (**Planejamento mestre \> Previsão \> Previsão de demanda \> Gerar previsão de linha de base estatística**). Para atribuir chaves de alocação de itens a uma empresa no grupo de planejamento intercompanhia selecionado, selecione a empresa e, em seguida, na guia rápida **Membros do grupo de planejamento intercompanhia**, selecione **Chaves de alocação de itens** na barra de ferramentas.

> [!IMPORTANT]
> Tome cuidado para incluir somente chaves de alocação de itens relevantes em cada grupo de planejamento intercompanhia. Itens desnecessários podem ocasionar o aumento dos custos quando você usa o Azure Machine Learning.

## <a name="set-up-demand-forecasting-parameters"></a><a name="parameters"></a>Configurar Parâmetros de previsão de demanda

Use a página **Parâmetros de previsão de demanda** para configurar várias opções que controlam como a previsão de demanda funcionará no seu sistema.

### <a name="open-the-demand-forecasting-parameters-page"></a>Abra a página Parâmetros de previsão de demanda

Para configurar os parâmetros de previsão de demanda, acesse **Planejamento mestre \> Configuração \> Previsão de demanda \> Parâmetros de previsão de demanda**. Como a previsão de demanda é realizada entre empresas, a configuração é global. Em outras palavras, ela se aplica a todas as entidades legais (empresas).

### <a name="general-settings"></a>Configurações gerais

Use a guia **Geral** da página **Parâmetros de previsão de demanda** para definir as configurações gerais para a previsão de demanda.

#### <a name="demand-forecast-unit"></a>Unidade de previsão de demanda

A previsão de demanda gera a previsão de quantidades. Portanto, a unidade de medida em que a quantidade deve ser expressa deve ser especificada no campo **Unidade de previsão de demanda**. Este campo define a unidade que será usada para todas as previsões de demanda, independentemente das unidades de estoque comuns para cada produto. Usando uma unidade de previsão consistente, você ajuda a garantir que a agregação e a distribuição percentual faça sentido. Para obter mais informações sobre agregação e distribuição percentual, consulte [Ajustes manuais na previsão estatística](manual-adjustments-baseline-forecast.md).

Para cada unidade de medida usada nas SKUs incluídas na previsão de demanda, verifique se há uma regra de conversão para a unidade de medida e a unidade de medida de previsão gera que você seleciona aqui. Ao gerar uma previsão, a lista de itens que não têm uma conversão de unidade de medida é registrada. Portanto, você pode corrigir a configuração com facilidade. Para obter mais informações sobre como unidades de medida e como convertê-las entre si, consulte [Gerenciar unidades de medida](../pim/tasks/manage-unit-measure.md).

#### <a name="transaction-types"></a>Tipos de transação

Use os campos da guia rápida **Tipos de transação** para selecionar os tipos de transação que são usados quando a previsão estatística é gerada.

A previsão de demanda pode ser usada para prever a demanda dependente e independente. Por exemplo, se apenas a opção **Ordem de venda** estiver definida como *Sim* e se todos os itens considerados na previsão de demanda forem itens vendidos, o sistema calculará a demanda independente. No entanto, os subcomponentes críticos podem ser adicionados às chaves de alocação de itens e incluídos na previsão de demanda. Nesse caso, se a opção **Linha de produção** estiver definida como *Sim*, uma previsão de dependente será calculada.

Você pode substituir tipos de transação por uma ou mais chaves de alocação de itens específicas usando a guia **Chaves de alocação de itens**. Essa guia fornece campos semelhantes.

#### <a name="choose-how-to-create-the-baseline-forecast"></a>Escolher como criar a previsão de linha de base

O campo **Estratégia de geração de previsão** permite selecionar o método usado para criar uma previsão de linha de base. Três métodos estão disponíveis:

- *Copiar histórico de demanda* – Crie previsões copiando dados históricos.
- *Serviço do Azure Machine Learning* – Use um modelo de previsão que use o Serviço do Azure Machine Learning. O Serviço do Azure Machine Learning é a atual solução de machine learning para o Azure. Portanto, é recomendável usá-lo se você desejar usar um modelo de previsão.
- *Azure Machine Learning* – Use um modelo de previsão que use o Estúdio do Azure Machine Learning (clássico). O Estúdio do Azure Machine Learning (clássico) foi preterido e será removido do Azure em breve. Portanto, recomendamos selecionar *Serviço do Azure Machine Learning* se você estiver configurando a previsão de demanda pela primeira vez. Se estiver usando o Estúdio do Azure Machine Learning (clássico) no momento, você deverá planejar mudar para o Serviço do Azure Machine Learning assim que possível.

Você pode substituir o método de geração de previsão por uma ou mais chaves de alocação de itens específicas usando a guia **Chaves de alocação de itens**. Essa guia fornece campos semelhantes.

#### <a name="override-default-forecast-algorithm-parameters-globally"></a>Substitua parâmetros do algoritmo de previsão padrão globalmente

Os valores e parâmetros do algoritmo de previsão padrão são atribuídos na página **Parâmetros de previsão de demanda** (**Planejamento mestre \> Configuração \> Geração de demanda \> Parâmetros de previsão de demanda**). No entanto, você pode substituí-los globalmente usando a guia rápida **Parâmetros do algoritmo de previsão** na guia **Geral** da página **Parâmetros de previsão de demanda**. (Você também pode substituí-los por chaves de alocação específicas usando a guia **Chaves de alocação de itens** na página **Parâmetros de previsão de demanda**.)

Usar os botões **Adicionar** e **Remover** na barra de ferramentas para estabelecer a coleta necessária de substituições de parâmetros. Para cada parâmetro na lista, selecione um valor no campo **Nome** e insira um valor apropriado no campo **Valor**. Todos os parâmetros não listados aqui levarão os valores das configurações na página **Parâmetros de previsão de demanda**. Para obter mais informações sobre como usar o conjunto padrão de parâmetros e selecionar valores para eles, consulte a seção [Parâmetros e valores padrão para modelos de previsão de demanda](#model-parameters).

### <a name="set-forecast-dimensions"></a>Definir dimensões de previsão

Uma dimensão de previsão indica o nível de detalhes em que a previsão será definida. A empresa, o site e a chave de alocação de itens são dimensões de previsão necessárias. Você também pode gerar previsões no depósito, no status do estoque, no grupo de clientes, na conta de cliente, no país/região, no estado e/ou no nível de item e em todos os níveis de dimensão de item. Use a guia **Dimensões de previsão** na página **Parâmetros de previsão de demanda**, para selecionar o conjunto de dimensões de previsão que é usado quando a previsão de demanda for gerada.

A qualquer momento, você pode adicionar dimensões de previsão à lista de dimensões usadas na previsão de demanda. É possível também remover as dimensões de previsão da lista. No entanto, os ajustes manuais serão perdidos se você adicionar ou remover uma dimensão de previsão.

### <a name="set-up-overrides-for-specific-item-allocation-keys"></a>Configurar substituições para chaves de alocação de itens específicas

Nem todos os itens funcionam da mesma forma sob uma perspectiva de previsão de demanda. Portanto, você pode estabelecer substituições de chaves de alocação específicas para a maioria das configurações definidas na guia **Geral**. A exceção é a unidade de previsão de demanda. Para configurar substituições para uma chave de alocação de itens específica, siga estas etapas.

1. Na página **Parâmetros de previsão de demanda**, na guia **Chaves de alocação de itens**, use os botões da barra de ferramentas para adicionar chaves de alocação de itens à grade à esquerda ou removê-las, conforme necessário. Em seguida, selecione a chave de alocação para a qual deseja configurar substituições.
1. Na guia rápida **Tipos de transação**, habilite os tipos de transações que você deseja usar para gerar a previsão estatística de produtos que pertencem à chave de alocação selecionada. As configurações funcionam exatamente como na guia **Geral**, mas se aplicam somente à chave de alocação de itens selecionada. Todas as configurações aqui (valores *Sim* e *Não*) substituem todas as configurações de **Tipos de transação** na guia **Geral**.
1. Na guia rápida **Parâmetros do algoritmo de previsão**, selecione a estratégia de geração de previsão e os parâmetros do algoritmo de previsão para produtos que pertencem à chave de alocação selecionada. Essas configurações funcionam exatamente como na guia **Geral**, mas se aplicam somente à chave de alocação de itens selecionada. Usar os botões **Adicionar** e **Remover** na barra de ferramentas para definir a coleta necessária de substituições de parâmetros. Para cada parâmetro na lista, selecione um valor no campo **Nome** e insira um valor apropriado no campo **Valor**. Para obter mais informações sobre como usar o conjunto padrão de parâmetros e selecionar valores para eles, consulte a seção [Parâmetros e valores padrão para modelos de previsão de demanda](#model-parameters).

### <a name="set-up-the-connection-to-the-azure-machine-learning-service"></a>Configurar a conexão com o Serviço do Azure Machine Learning

Use a guia **Serviço do Azure Machine Learning** para configurar a conexão com o Serviço do Azure Machine Learning. Esta solução é uma das opções para a criação da previsão de linha de base. Essas configurações nessa guia têm efeito somente quando o campo **Estratégia de geração de previsão** é definido como *Serviço do Azure Machine Learning*.

Para obter mais informações sobre como configurar o Serviço do Azure Machine Learning e usar as configurações aqui para se conectar a ele, consulte a seção [Configurar o Serviço do Azure Machine Learning](#setup-amls).

### <a name="set-up-the-connection-to-azure-machine-learning-studio-classic"></a>Configurar a conexão com o Estúdio do Azure Machine Learning (clássico)

> [!IMPORTANT]
> O Estúdio do Azure Machine Learning (clássico) foi preterido. Portanto, não será mais possível criar novos espaços de trabalho para ele no Azure. Ele foi substituído pelo Serviço do Azure Machine Learning, que fornece funcionalidade semelhante e muito mais. Se você ainda não estiver usando o Azure Machine Learning, comece a usar o Serviço do Azure Machine Learning. Se você já tiver um workspace criado para o Estúdio do Azure Machine Learning (clássico), poderá continuar a usá-lo até que o recurso seja completamente removido do Azure. No entanto, recomendamos atualizar o Serviço do Azure Machine Learning o mais rápido possível. Embora o aplicativo continue avisando que o Estúdio do Azure Machine Learning (clássico) foi preterido, o resultado previsto não será afetado. Para obter mais informações sobre o novo Serviço do Azure Machine Learning e como configurá-lo, consulte a seção [Configurar o Serviço do Azure Machine Learning](#setup-amls).
>
> Você pode alternar à vontade entre o uso das novas e antigas soluções de machine learning com o Supply Chain Management enquanto o seu antigo workspace do Estúdio do Azure Machine Learning (clássico) continuar disponível.

Se você já tiver um workspace do Estúdio do Azure Machine Learning (clássico) disponível, poderá usá-lo para gerar previsões, conectando-o ao Supply Chain Management. Você pode estabelecer essa conexão usando a guia **Azure Machine Learning** na página **Parâmetros de previsão de demanda**. (As configurações nesta guia têm efeito somente quando o campo **Estratégia de geração de previsão** é definido como *Azure Machine Learning*.) Insira os seguintes detalhes para seu workspace do Estúdio do Azure Machine Learning (clássico):

- Chave da API (interface de programação de aplicativos) do serviço Web
- URL do ponto de extremidade do serviço Web
- Nome da conta de armazenamento do Azure
- Chave da conta de armazenamento do Azure

> [!NOTE]
> O nome e a chave da conta de armazenamento do Azure serão necessários apenas se você usar uma conta de armazenamento personalizada. Se você implantar a versão local, deverá ter uma conta de armazenamento personalizada no Azure, para que o Machine Learning acesse os dados históricos.

## <a name="default-parameters-and-values-for-demand-forecasting-models"></a><a name="model-parameters"></a>Parâmetros e valores padrão para modelos de previsão de demanda

Ao usar o machine learning para gerar os modelos de planejamento de previsão, você controla as opções do machine learning definindo valores para os *Parâmetros do algoritmo de previsão*. Esses valores são enviados do Supply Chain Management para o Azure Machine Learning. Use a página **Parâmetros do algoritmo de previsão** para controlar os tipos de valores que devem ser fornecidos e quais valores devem ter.

Para configurar os valores e os parâmetros padrão usados para os modelos de previsão de demanda, acesse **Planejamento Mestre \> Configuração \> Previsão de demanda \> Parâmetros do algoritmo de previsão**. Um conjunto padrão de parâmetros é fornecido. Cada parâmetro tem os seguintes campos:

- **Nome** – O nome do parâmetro, conforme usado pelo Azure. Normalmente, você não deve alterar esse nome, a menos que tenha personalizado o experimento no Azure Machine Learning.
- **Descrição** – Um nome comum para o parâmetro. Esse nome é usado para identificar o parâmetro em outros locais no sistema (por exemplo, na página **Parâmetros de previsão de demanda**).
- **Valor** – O valor padrão do parâmetro. O valor que você deve inserir depende do parâmetro que está sendo editado. 
- **Explicação** – Uma breve descrição do parâmetro e como usá-lo. A descrição normalmente inclui sugestões sobre valores válidos para o campo **Valor**.

Os seguintes parâmetros são fornecidos por padrão. (Se você precisar reverter para essa lista padrão, selecione **Restaurar** no Painel de Ações.)

- **Porcentagem do nível de confiança** – um intervalo de confiança consiste em um intervalo de valores que representam boas estimativas para a previsão de demanda. Um nível de confiança de 95% indica que há um risco de 5% de que a demanda futura fique fora do intervalo de confiança.
- **Forçar sazonalidade** – Especifica se deseja forçar o modelo a usar um tipo de sazonalidade específico. Esse parâmetro aplica-se somente a ARIMA e ETS. Opções: *AUTO (padrão)*, *NENHUM*, *ADITIVO*, *MULTIPLICATIVO*.
- **Modelo de previsão** – Especifica o modelo de previsão a ser usado. Opções: *ARIMA*, *ETS*, *STL*, *ETS+ARIMA*, *ETS+STL*, *TUDO*. Para selecionar o melhor modelo, use *TUDO*.
- **Valor máximo previsto** – especifica o valor máximo a ser usado para previsões. Formato: +1E[n] ou constante numérica.
- **Valor mínimo previsto** – especifica o valor mínimo a ser usado para previsões. Formato: -1E[n] ou constante numérica.
- **Substituição de valor ausente** – especifica como as lacunas em dados históricos são preenchidas. Opções: *(valor numérico)*, *MÉDIA*, *ANTERIOR*, *INTERPOLAÇÃO LINEAR*, *INTERPOLAÇÃO POLINOMIAL*.
- **Escopo de substituição de valor ausente** – especifica se a substituição de valor se aplica apenas ao intervalo de datas de cada atributo de granularidade individual ou ao conjunto inteiro de dados. As seguintes opções estão disponíveis para estabelecer o intervalo de datas que o sistema usa ao preencher lacunas em dados históricos:

    - *GLOBAL* – O sistema usa todo o intervalo de datas de todos os atributos de granularidade.
    - *HISTORY_DATE_RANGE* – O sistema usa um intervalo de datas específico que é definido pelos campos **Data inicial** e **Data final** na seção **Horizonte histórico** na caixa de diálogo **Gerar previsão estatística**.
    - *GRANULARITY_ATTRIBUTE* – O sistema usa o intervalo de datas do atributo de granularidade processado no momento.

    > [!NOTE]
    > Um atributo de granularidade é uma combinação de dimensões de previsão em relação à qual a previsão é feita. Você pode definir dimensões de previsão na página **Parâmetros de previsão de demanda**.

- **Dica de sazonalidade** – para dados sazonais, forneça uma dica para o modelo de previsão para melhorar a precisão da previsão. Formato: Número inteiro que representa o número de classificações que um padrão de demanda se repete. Por exemplo, insira *6* para dados que se repetem a cada 6 meses.
- **Porcentagem de tamanho de conjunto de teste** – porcentagem de dados históricos que devem ser usados como conjunto de teste para o cálculo de precisão da previsão.

Você pode substituir os valores por esses parâmetros acessando **Planejamento Mestre \> Configuração \> Previsão de demanda \> Parâmetros de previsão de demanda**. Na página **Parâmetros de previsão de demanda**, você pode substituir os parâmetros das seguintes maneiras:

- Usar a guia **Geral** para substituir os parâmetros globalmente.
- Usar a guia **Chaves de alocação de itens** para substituir os parâmetros por chaves de alocação de itens específicas. Os parâmetros que são substituídos por uma chave de alocação de item específica afetam apenas a previsão dos itens associados a essa chave de alocação de item.

> [!NOTE]
> Na página **Parâmetros do algoritmo de previsão**, você pode usar os botões no Painel de Ações para adicionar ou remover parâmetros da lista. No entanto, normalmente, você não deve usar essa abordagem, a menos que tenha personalizado o experimento no Azure Machine Learning.

## <a name="set-up-the-azure-machine-learning-service"></a><a name="setup-amls"></a>Configurar o Serviço do Azure Machine Learning

O Supply Chain Management calcula as previsões de demanda usando o Serviço do Azure Machine Learning, que você deve configurar e executar em sua própria assinatura do Azure. Esta seção descreve como configurar o Serviço do Azure Machine Learning no Azure e, em seguida, conectá-lo ao seu ambiente do Supply Chain Management.

### <a name="enable-the-azure-machine-learning-service-in-feature-management"></a>Habilitar o Serviço do Azure Machine Learning no Gerenciamento de recursos

Antes de usar o Serviço do Azure Machine Learning para previsões de demanda, você deve ativar um recurso do Supply Chain Management para habilitar a integração. Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo. No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:

- **Módulo:** *Planejamento mestre*
- **Nome do recurso:** *Serviço do Azure Machine Learning para previsão de demanda*

### <a name="set-up-machine-learning-in-azure"></a><a name="ml-workspace"></a>Configurar o machine learning no Azure

Para habilitar o Azure a usar o machine learning para processar suas previsões, você deve configurar um workspace do Azure Machine Learning para essa finalidade. Você tem duas opções:

- Para configurar o workspace executando um script fornecido pela Microsoft, siga as instruções na seção [Opção 1: Executar um script para configurar automaticamente o workspace do Machine Learning](#ml-workspace-script) e, em seguida, avance para a seção [Configurar parâmetros de conexão do Serviço do Azure Machine Learning no Supply Chain Management](#demand-forecast-parameters).
- Para configurar manualmente o workspace, siga as instruções na seção [Opção 2: Configurar manualmente o Workspace do Machine Learning](#ml-workspace-manual) e, em seguida, avance para a seção [Configurar parâmetros de conexão do Serviço do Azure Machine Learning no Supply Chain Management](#demand-forecast-parameters). Esta opção demora mais, mas oferece mais controle.

#### <a name="option-1-run-a-script-to-automatically-set-up-your-machine-learning-workspace"></a><a name="ml-workspace-script"></a>Opção 1: Executar um script para configurar automaticamente o workspace do Machine Learning

Esta seção descreve como configurar o workspace do Machine Learning usando um script automatizado fornecido pela Microsoft. Se preferir, você pode configurar manualmente todos os recursos seguindo as instruções na seção [Opção 2: Configurar manualmente o Workspace do Machine Learning](#ml-workspace-manual). Não é necessário concluir as duas opções.

1. No GitHub, abra o repositório [Modelos para a previsão de demanda do Dynamics 365 Supply Chain Management com o Azure Machine Learning](https://github.com/microsoft/Dynamics-365-Supply-Chain-Management-Demand-Forecasting-With-Azure-Machine-Learning-Service) e baixe os seguintes arquivos:

    - quick_setup.ps1
    - sampleInput.csv
    - src/parameters.py
    - src/api_trigger.py
    - src/run.py
    - src/REntryScript/forecast.r

1. Abra uma janela do PowerShell e execute o script **quick_setup.ps1** baixado na etapa anterior. Siga as instruções na tela. O script configurará os recursos de workspace, armazenamento, armazenamento de dados padrão e computação necessários. No entanto, você ainda deve criar os pipelines necessários seguindo as etapas restantes deste procedimento. (Os pipelines fornecem uma forma de iniciar a previsão de scripts do Supply Chain Management.)
1. No Estúdio do Azure Machine Learning, carregue o arquivo **sampleInput.csv** que você baixou na etapa 1 para o contêiner chamado *demplan-azureml*. (O script quick_setup.ps1 criou este contêiner.) Esse arquivo é necessário para publicar o pipeline e gerar uma previsão de teste. Para obter instruções, consulte [Carregar um blob de blocos](/azure/storage/blobs/storage-quickstart-blobs-portal#upload-a-block-blob).
1. No Estúdio do Azure Machine Learning, selecione **Notebooks** no navegador.
1. Encontre o seguinte local na estrutura de **Arquivos**: **Users/\[current user\]/src**.
1. Carregue os quatro arquivos restantes que você baixou na etapa 1 para o local encontrado na etapa anterior.
1. Selecione o arquivo **api_trigger.py** que você acabou de carregar e execute-o. Ele criará um pipeline que pode ser disparado por meio da API.
1. Agora, seu workspace está configurado. Avance para a seção [Configurar parâmetros de conexão do Serviço do Azure Machine Learning no Supply Chain Management](#demand-forecast-parameters).

#### <a name="option-2-manually-set-up-your-machine-learning-workspace"></a><a name="ml-workspace-manual"></a>Opção 2: Configurar manualmente o workspace do Machine Learning

Esta seção descreve como configurar manualmente o workspace do Machine Learning. Você deve concluir os procedimentos nesta seção somente se decidiu não executar o script de configuração automatizado, conforme descrito na seção [Opção 1: Executar um script para configurar o workspace do Machine Learning](#ml-workspace-script).

##### <a name="step-1-create-a-new-workspace"></a><a name="create-workspace"></a>Etapa 1: Criar um novo workspace

Use o procedimento a seguir para criar um novo workspace do Machine Learning.

1. Entre no portal do Azure.
1. Abra o serviço do **Machine Learning**.
1. Selecione **Criar** na barra de ferramentas para abrir assistente de **Criação**.
1. Conclua o assistente seguindo as instruções na tela. Tenha as seguintes considerações em mente ao trabalhar:

    - Use as configurações padrão, a menos que outras considerações nesta lista recomendem configurações diferentes.
    - Selecione a região geográfica que corresponde à região em que a instância do Supply Chain Management é implantada. Caso contrário, alguns dados podem passar por limites de região. Para obter mais informações, consulte [aviso de privacidade](#privacy) posteriormente neste artigo.
    - Use recursos dedicados, como grupos de recursos, contas de armazenamento, registros de contêiner, Azure Key Vaults e recursos de rede.
    - Na página **Configurar parâmetros de conexão do Serviço do Azure Machine Learning** do assistente, você deve fornecer um nome de conta de armazenamento. Use uma conta dedicada à previsão de demanda. Os dados de entrada e saída de previsão de demanda serão armazenados nessa conta de armazenamento.

Para obter mais informações, consulte [Criar o workspace](/azure/machine-learning/quickstart-create-resources#create-the-workspace).

##### <a name="step-2-configure-storage"></a><a name="config-storage"></a>Etapa 2: Configurar armazenamento

Use o procedimento a seguir para configurar o armazenamento.

1. No GitHub, abra o repositório [Modelos para a previsão de demanda do Dynamics 365 Supply Chain Management com o Azure Machine Learning](https://github.com/microsoft/Dynamics-365-Supply-Chain-Management-Demand-Forecasting-With-Azure-Machine-Learning-Service) e baixe o arquivo **sampleInput.csv**.
1. Abra a conta de armazenamento que você criou na seção [Etapa 1: Criar um novo workspace](#create-workspace).
1. Siga as instruções em [Criar um contêiner](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) para criar um contêiner chamado *demplan-azureml*.
1. Carregue o arquivo **sampleInput.csv** baixado na etapa 1 para o contêiner que você acabou de criar. Esse arquivo é necessário para publicar o pipeline e gerar uma previsão de teste. Para obter instruções, consulte [Carregar um blob de blocos](/azure/storage/blobs/storage-quickstart-blobs-portal#upload-a-block-blob).

##### <a name="step-3-configure-a-default-datastore"></a>Etapa 3: Configurar um armazenamento de dados padrão

Use o procedimento a seguir para configurar o armazenamento de dados padrão.

1. No Estúdio do Azure Machine Learning, selecione **Armazenamentos de dados** no navegador.
1. Crie um novo armazenamento de dados do tipo *Armazenamento de Blobs do Azure* que aponte para o contêiner de armazenamento de blobs *demplan-azureml* criado na seção [Etapa 2: Configurar armazenamento](#config-storage). (Se o tipo de autenticação do novo armazenamento de dados for *Chave de conta*, forneça uma chave de conta para a conta de armazenamento criada. Para obter instruções, consulte [Gerenciar chaves de acesso da conta de armazenamento](/azure/storage/common/storage-account-keys-manage?tabs=azure-portal).)
1. Torne seu novo armazenamento de dados o padrão abrindo os detalhes e selecionando **Definir como armazenamento de dados padrão**.

##### <a name="step-4-configure-compute-resources"></a><a name="config-compute-resources"></a>Etapa 4: Configurar recursos de computação

Use o procedimento a seguir para configurar um recurso de computação no Estúdio do Azure Machine Learning para executar seus scripts de geração de previsão.

1. Abra a página detalhes para o workspace do Machine Learning que você criou na seção [Etapa 1: Criar um novo workspace](#create-workspace). Localize o valor da **URL da Web do Estúdio** e selecione o link para abri-lo.
1. Selecione **Computação** no painel de navegação.
1. Na guia **Instâncias de computação**, selecione **Novo** para abrir um assistente que ajudará a criar uma nova instância de computação. Siga as instruções na tela. A instância de computação será usada para criar o pipeline de previsão de demanda (pode ser excluída depois que o pipeline for publicado). Use as configurações padrão.
1. Na guia **Clusters de cálculo**, selecione **Novo** para abrir um assistente que ajudará a criar um novo cluster de cálculo. Siga as instruções na tela. O cluster de cálculo será usado para gerar previsões de demanda. Suas configurações afetam o desempenho e o nível máximo de paralelização da execução. Defina os campos a seguir, mas use as configurações padrão para todos os outros campos:

    - **Nome** – Insira *e2ecpucluster*.
    - **Tamanho da máquina virtual** – Ajuste essa configuração de acordo com o volume de dados que você espera usar como entrada para a previsão de demanda. A quantidade de nós não deve exceder 11, porque um nó é necessário para disparar a geração de previsão de demanda, e o número máximo de nós que podem ser usados para gerar uma previsão é 10. (Também será possível definir a quantidade de nós no arquivo parameters.py na seção [Etapa 5: Criar pipelines](#create-pipelines).) Em cada nó, haverá vários processos de trabalho que executam previsões de scripts em paralelo. O número total de processos de trabalho no seu trabalho será o *Número de núcleos que um nó tem* × *Quantidade de nós*. Por exemplo, se o seu cluster de cálculo tiver um tipo de *Standard\_D4* (oito núcleos) um máximo de 11 nós, e se o valor `nodes_count` for definido como *10* no arquivo parameters.py, o nível efetivo de paralelismo será 80.

##### <a name="step-5-create-pipelines"></a><a name="create-pipelines"></a>Etapa 5: Criar pipelines

Os pipelines fornecem uma forma de iniciar a previsão de scripts do Supply Chain Management. Use o seguinte procedimento para criar os pipelines necessários.

1. No GitHub, abra o repositório [Modelos para a previsão de demanda do Dynamics 365 Supply Chain Management com o Azure Machine Learning](https://github.com/microsoft/Dynamics-365-Supply-Chain-Management-Demand-Forecasting-With-Azure-Machine-Learning-Service) e baixe os seguintes arquivos:

    - src/parameters.py
    - src/api_trigger.py
    - src/run.py
    - src/REntryScript/forecast.r

1. No Estúdio do Azure Machine Learning, selecione **Notebooks** no navegador.
1. Encontre o seguinte local na estrutura de **Arquivos**: **Users/\[current user\]/src**.
1. Carregue os quatro arquivos que você baixou na etapa 1 para o local encontrado na etapa anterior.
1. No Azure, abra e revise o arquivo **parameters.py** que você acabou de carregar. Verifique se o valor `nodes_count` é um menor do que o valor configurado para o cluster de cálculo na seção [Etapa 4: Configurar recursos de computação](#config-compute-resources). Se o valor `nodes_count` for maior ou igual ao número de nós no cluster de cálculo, a execução do pipeline poderá ser iniciada. No entanto, ele para de responder enquanto aguarda os recursos necessários. Para obter mais informações sobre a quantidade de nós, consulte a seção [Etapa 4: Configurar recursos de computação](#config-compute-resources).
1. Selecione o arquivo **api_trigger.py** que você acabou de carregar e execute-o. Ele criará um pipeline que pode ser disparado por meio da API.

### <a name="set-up-a-new-active-directory-application"></a><a name="aad-app"></a>Configurar um novo aplicativo do Active Directory

É necessário que um aplicativo do Active Directory seja autenticado com os recursos dedicados à previsão de demanda usando uma entidade de serviço. Portanto, o aplicativo deve ter o menor nível de privilégio necessário para gerar a previsão.

1. Entre no portal do Azure.
1. Registre um novo aplicativo no Azure Active Directory (Azure AD) do locatário. Para obter instruções, consulte [Usar o portal para criar um aplicativo do Azure AD e uma entidade de serviço que possa acessar recursos](/azure/active-directory/develop/howto-create-service-principal-portal).
1. Siga as instruções na tela à medida que você conclui o assistente. Use as configurações padrão.
1. Forneça ao seu novo aplicativo do Active Directory acesso aos seguintes recursos que você criou na seção [Configurar o machine learning no Azure](#ml-workspace). Para obter instruções, consulte [Atribuir funções do Azure usando o portal do Azure](/azure/role-based-access-control/role-assignments-portal?tabs=current). Esta etapa permitirá que o sistema importe e exporte os dados de previsão e disparar execuções do pipeline de machine learning no Supply Chain Management.

    - Função de colaborador no workspace do Machine Learning
    - Função de colaborador à conta de armazenamento dedicada
    - Dados Blob de Armazenamento Função de colaborador à conta de armazenamento dedicada

1. Na seção **Certificados e segredos** do aplicativo que você criou, crie um segredo para o aplicativo. Para obter instruções, consulte [Adicionar um segredo do cliente](/azure/active-directory/develop/quickstart-register-app#add-a-client-secret).
1. Anote a ID do aplicativo e seu segredo. Você precisará dos detalhes desse aplicativo posteriormente, quando configurar a página **Parâmetros de previsão de demanda** no Supply Chain Management.

### <a name="set-up-azure-machine-learning-service-connection-parameters-in-supply-chain-management"></a><a name="demand-forecast-parameters"></a>Configurar parâmetros de conexão do Serviço do Azure Machine Learning no Supply Chain Management

Use o seguinte procedimento para conectar seu ambiente do Supply Chain Management ao serviço do Machine Learning que você acabou de configurar no Azure.

1. Entre no Supply Chain Management.
1. Acesse **Planejamento mestre \> Configuração \> Previsão de demanda \> Parâmetros de previsão de demanda**.
1. Na guia **Geral**, verifique se o campo **Estratégia de geração de previsão** está definido como *Serviço do Azure Machine Learning*.
1. Na guia **Chaves de alocação de itens**, verifique se o campo **Estratégia de geração de previsão** está definido como *Serviço do Azure Machine Learning* para cada chave de alocação que deve usar o Serviço do Azure Machine Learning para a previsão de demanda.
1. Na guia **Serviço do Azure Machine Learning**, defina os seguintes campos:

    - **ID de Locatário** – Insira a ID do seu locatário do Azure. O Supply Chain Management usará essa ID para autenticar o Serviço do Azure Machine Learning. Você pode encontrar sua ID de locatário na página **Visão geral** para o Azure AD no portal do Azure.
    - **ID do aplicativo da entidade de serviço** – Insira a ID do aplicativo que você criou na seção [Aplicativo do Active Directory](#aad-app). Esse valor é usado para autorizar solicitações de API ao Serviço do Azure Machine Learning.
    - **Segredo da entidade de serviço** – Insira o segredo do aplicativo da entidade de serviço que você criou na seção [Aplicativo do Active Directory](#aad-app). Esse valor é usado para adquirir o token de acesso da entidade de segurança que você criou para executar operações autorizadas em relação ao Armazenamento do Azure e ao workspace do Azure Machine Learning.
    - **Nome da conta de armazenamento** – Insira o nome da conta de armazenamento do Azure que você especificou ao executar o assistente de instalação no seu workspace do Azure. (Para obter mais informações, consulte a seção [Configurar o machine learning no Azure](#ml-workspace).)
    - **Endereço do ponto de extremidade do pipeline** – Insira a URL do ponto de extremidade REST do pipeline para o Serviço do Azure Machine Learning. Você criou esse pipeline como a última etapa ao [configurar o machine learning no Azure](#ml-workspace). Para obter a URL do pipeline, entre no portal do Azure, selecione **Pipelines** na navegação. Na guia **Pipeline**, selecione o ponto de extremidade do pipeline chamado **TriggerDemandForecastGeneration**. Em seguida, copie o ponto de extremidade REST exibido.

    ![Parâmetros na guia Serviço do Azure Machine Learning da página Parâmetros de previsão de demanda.](media/azure-ml-service-parameters.png "Parâmetros na guia Serviço do Azure Machine Learning da página Parâmetros de previsão de demanda")

## <a name="privacy-notice"></a><a name="privacy"></a>Aviso de privacidade

Ao selecionar o *Serviço do Azure Machine Learning* como sua estratégia de geração de previsão, o Supply Chain Management envia automaticamente os dados do cliente para a demanda histórica, como quantidades agregadas, nomes de produtos e suas dimensões de produto, os locais de remessa e recebimento, os identificadores de clientes e também os parâmetros de previsão, para a região geográfica na qual o workspace do Machine Learning e sua conta estão localizados, para fins de previsão de demandas futuras. O Serviço do Azure Machine Learning pode estar em uma região geográfica diferente da região geográfica em que o Supply Chain Management está implantado. Alguns usuários podem controlar se essa funcionalidade é habilitada, selecionando a estratégia de geração de previsão na página **Parâmetros de previsão de demanda**.

## <a name="additional-resources"></a>Recursos adicionais

- [Visão geral da previsão de demanda](introduction-demand-forecasting.md)
- [​Gerar uma previsão estatística​](generate-statistical-baseline-forecast.md)
- [Faça ajustes manuais para a previsão estatística](manual-adjustments-baseline-forecast.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

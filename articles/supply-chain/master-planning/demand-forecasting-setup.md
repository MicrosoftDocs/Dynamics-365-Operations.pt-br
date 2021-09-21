---
title: Configuração da previsão de demanda
description: Este tópico descreve as tarefas de configuração que devem ser executadas para preparar a previsão de demanda.
author: roxanadiaconu
ms.date: 08/09/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanDefaultAlgorithmParameters, ReqDemPlanForecastParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72653
ms.assetid: c5fa4b09-512d-4349-ac51-cc13da69a160
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 81fec20130a1621d4cb55394db75a7ac0a16fdf3
ms.sourcegitcommit: 4fbf031319109660c0462a800f85848571eb040d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2021
ms.locfileid: "7471326"
---
# <a name="demand-forecasting-setup"></a>Configuração da previsão de demanda

[!include [banner](../includes/banner.md)]

Este tópico descreve as tarefas de configuração que devem ser executadas para preparar a previsão de demanda.  

As tarefas de configuração incluem a configuração dos dados e parâmetros a seguir.

## <a name="item-allocation-keys"></a>Chaves de alocação de itens

Uma previsão de demanda será calculada para um item e suas dimensões somente se o item fizer parte de uma chave de alocação de item. A regra é imposta agrupar grandes números de itens, para que as previsões de demanda possam ser criadas mais rapidamente. O percentual da chave de alocação de item é ignorado quando as previsões de demanda são geradas. As previsões são criadas com base em dados históricos apenas.

Um item e suas dimensões devem ser parte de apenas uma chave de alocação de item, caso a chave de alocação de item seja usada durante a criação da previsão.

Para adicionar uma SKU (unidade de manutenção de estoque) a uma chave de alocação de item, acesse **Planejamento mestre \> Configuração \> Previsão de demanda \> Chaves de alocação de itens**. Use a página **Atribuir itens** para atribuir um item a uma chave de alocação.

## <a name="intercompany-planning-groups"></a>Grupos de planejamento intercompanhia

A previsão de demanda gera previsões interempresariais. No Dynamics 365 Supply Chain Management, as empresas que são planejadas juntas são colocadas em um grupo de planejamento intercompanhia. Para especificar, por empresa, quais chaves de alocação de item devem ser consideradas para previsão de demanda, associe uma chave de alocação de item ao membro do grupo de planejamento intercompanhia, acessando **Planejamento mestre \> Configuração \> Grupos de planejamento intercompanhia**.

Por padrão, se nenhuma chave de alocação de item for atribuída aos membros do grupo de planejamento intercompanhia, uma previsão de demanda será calculada para todos os itens atribuídos a todas as chaves de alocação de item de todas as empresas. Outras opções de filtragem para empresas e chaves de alocação de itens estão disponíveis na página **Gerar previsão estatística**.

Analise o número de itens previstos. Itens desnecessários podem ocasionar o aumento dos custos quando você usa o Aprendizado de Máquina do Microsoft Azure.

## <a name="demand-forecasting-parameters"></a>Parâmetros de previsão de demanda

Para configurar os parâmetros de previsão de demanda, acesse **Planejamento mestre \> Configuração \> \> Previsão de demanda \> Parâmetros de previsão de demanda**. Como a previsão de demanda é realizada entre empresas, a configuração é global. Isso significa que a configuração se aplica a todas as empresas.

A previsão de demanda gera a previsão de quantidades. Portanto, a unidade de medida em que a quantidade deve ser expressa deve ser especificada no campo **Unidade de previsão de demanda**. A unidade de medida deve ser exclusiva para garantir que a agregação e a distribuição percentual faça sentido. Para obter mais informações sobre agregação e distribuição percentual, consulte [Ajustes manuais na previsão estatística](manual-adjustments-baseline-forecast.md). Para cada unidade de medida usada nas SKUs incluídas na previsão de demanda, verifique se há uma regra de conversão para a unidade de medida e a unidade de medida de previsão geral. Quando a geração de previsão é executada, a lista de itens que não têm uma conversão de unidade de medida é registrada, para que você possa corrigir facilmente a configuração.

A previsão de demanda pode ser usada para prever a demanda dependente e independente. Por exemplo, se apenas a caixa de seleção **Ordem de venda** estiver marcada e se todos os itens considerados na previsão de demanda forem itens vendidos, o sistema calculará a demanda independente. No entanto, os subcomponentes críticos podem ser adicionados às chaves de alocação de itens e incluídos na previsão de demanda. Nesse caso, se a caixa de seleção **Linha de produção** estiver marcada, uma previsão de dependente será calculada.

Há dois métodos para criar uma previsão de linha de base. Você pode usar modelos de previsão sobre os dados históricos ou apenas copiar sobre os dados históricos na previsão. O campo **Estratégia de geração de previsão** permite que você selecione entre esses dois métodos. Para usar modelos de previsão, selecione **Aprendizado de Máquina do Azure**.

Ao selecionar **Dimensões de previsão** no painel esquerdo da página **Parâmetros de previsão de demanda**, você também pode selecionar o conjunto de dimensões de previsão a ser usado quando a previsão de demanda for gerada. Uma dimensão de previsão indica o nível de detalhes em que a previsão será definida. A empresa, o site e a chave de alocação de item são dimensões de previsão obrigatórias, mas você também pode gerar previsões no depósito, no status do estoque, no grupo de clientes, na conta de cliente, no país/região, no estado e no item e em todos os níveis de dimensão de item.

A qualquer momento, você pode adicionar dimensões de previsão à lista de dimensões usadas na previsão de demanda. É possível também remover as dimensões de previsão da lista. No entanto, os ajustes manuais serão perdidos se você adicionar ou remover uma dimensão de previsão.

Nem todos os itens funcionam da mesma forma sob uma perspectiva de previsão de demanda. Os itens semelhantes podem ser agrupados em uma única chave de alocação de item, e os parâmetros, como os tipos de transação e as configurações de método de previsão, podem ser definidos por chave de alocação de item. Selecione **Chaves de alocação de itens** no painel esquerdo da página **Parâmetros de previsão de demanda**.

Para gerar a previsão, o Supply Chain Management usa um serviço Web do Machine Learning. Para se conectar ao serviço, você deve fornecer as seguintes informações se entrar no Microsoft Azure Machine Learning Studio (clássico):

- Chave da API (interface de programação de aplicativos) do serviço Web
- URL do ponto de extremidade do serviço Web
- Nome da conta de armazenamento do Azure
- Chave da conta de armazenamento do Azure

> [!NOTE]
> O nome e a chave da conta de armazenamento do Azure serão necessários apenas se você usar uma conta de armazenamento personalizada. Se você implantar a versão local, deverá ter uma conta de armazenamento personalizada no Azure, para que o Aprendizado de Máquina acesse os dados históricos.

Para criar previsões de demanda, você pode implantar seu próprio serviço usando os experimentos de previsão de demanda do Estúdio de Aprendizado de Máquina ou do Supply Chain Management. As instruções para implantar os experimentos de previsão de demanda como um serviço Web estão disponíveis no Supply Chain Management. Na página **Parâmetros de previsão de demanda**, abra a guia **Azure Machine Learning**.

## <a name="settings-for-the-demand-forecasting-machine-learning-service"></a>Configurações do serviço de Aprendizado de Máquina da previsão de demanda.

Para exibir os parâmetros que podem ser configurados para o serviço de previsão de demanda, acesse **Planejamento Mestre \> Configuração \> Previsão de demanda \> Prevendo parâmetros de algoritmo**. A pagina **Prevendo parâmetros padrão de algoritmo** mostra os valores padrão dos parâmetros. Você pode substituir esses parâmetros acessando **Planejamento Mestre \> Configuração \> Previsão de demanda \> Parâmetros de previsão de demanda**, onde pode:

- Usar a guia **Geral** para substituir os parâmetros globalmente.
- Usar a guia **Chaves de alocação de itens** para substituir os parâmetros por chave de alocação de itens. Os parâmetros que são substituídos em uma chave de alocação de item afetam apenas a previsão dos itens associados a essa chave de alocação de item.

### <a name="forecast-algorithm-parameters"></a>Prever parâmetros de algoritmo

Na guia **Chaves de alocação de itens** da página **Parâmetros de previsão de demanda**, você pode usar a FastTab **Prever parâmetros de algoritmo** para atribuir parâmetros de algoritmo de previsão à chave de alocação de itens selecionada no momento na grade à esquerda. Usar os botões **Adicionar** e **Remover** na barra de ferramentas para estabelecer a coleta necessária de parâmetros. Para cada parâmetro na lista, selecione um dos seguintes valores no campo **Nome** e insira um valor apropriado no campo **Valor**:

- **Porcentagem do nível de confiança** – um intervalo de confiança consiste em um intervalo de valores que representam boas estimativas para a previsão de demanda. Um nível de confiança de 95% indica que há um risco de 5% de que a demanda futura fique fora do intervalo de confiança.
- **Forçar sazonalidade** – especifica se deseja forçar o modelo a usar um determinado tipo de sazonalidade. Aplica-se somente a ARIMA e ETS. Opções: AUTO (padrão), NENHUM, ADITIVO, MULTIPLICATIVO.
- **Modelo de previsão** – opções: ARIMA, ETS, STL, ETS+ARIMA, ETS+STL, TUDO. Para selecionar o melhor modelo, use **TUDO**.
- **Valor máximo previsto** – especifica o valor máximo a ser usado para previsões. Formato: +1E[n] ou constante numérica.
- **Valor mínimo previsto** – especifica o valor mínimo a ser usado para previsões. Formato: -1E[n] ou constante numérica.
- **Substituição de valor ausente** – especifica como as lacunas em dados históricos são preenchidas. Opções: valor numérico, MÉDIA, ANTERIOR, INTERPOLAÇÃO LINEAR, INTERPOLAÇÃO POLINOMIAL.
- **Escopo de substituição de valor ausente** – especifica se a substituição de valor se aplica apenas ao intervalo de datas de cada atributo de granularidade individual ou ao conjunto inteiro de dados. As seguintes opções estão disponíveis para estabelecer o intervalo de datas que o sistema usa ao preencher lacunas em dados históricos:

  - GLOBAL – o sistema usa todo o intervalo de datas de todos os atributos de granularidade.
  - HISTORY_DATE_RANGE – o sistema usa um intervalo de datas específico definido pelos campos **Data inicial** e **Data final** no grupo de campos **Horizonte histórico** na caixa de diálogo **Gerar previsão estatística**.
  - GRANULARITY_ATTRIBUTE – o sistema usa o intervalo de datas do atributo de granularidade processado no momento.

  > [!NOTE]
  > Um atributo de granularidade é uma combinação de dimensões de previsão em relação à qual a previsão é feita. Você pode definir dimensões de previsão na página **Parâmetros de previsão de demanda**.

- **Dica de sazonalidade** – para dados sazonais, forneça uma dica para o modelo de previsão para melhorar a precisão da previsão. Formato: número inteiro que representa o número de classificações que um padrão de demanda se repete. Por exemplo, insira "6" para dados que se repetem a cada 6 meses.
- **Porcentagem de tamanho de conjunto de teste** – porcentagem de dados históricos que devem ser usados como conjunto de teste para o cálculo de precisão da previsão.

## <a name="additional-resources"></a>Recursos adicionais

- [Visão geral da previsão de demanda](introduction-demand-forecasting.md)
- [​Gerar uma previsão estatística​](generate-statistical-baseline-forecast.md)
- [Faça ajustes manuais para a previsão estatística](manual-adjustments-baseline-forecast.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

---
title: "Configuração da previsão de demanda"
description: "Este tópico descreve as tarefas de configuração que devem ser executadas para preparar a previsão de demanda."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqDemPlanDefaultAlgorithmParameters, ReqDemPlanForecastParameters
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 72653
ms.assetid: c5fa4b09-512d-4349-ac51-cc13da69a160
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: f629329f4f50bd7c8edcfd70641bace01a1c53aa
ms.lasthandoff: 03/31/2017


---

# <a name="demand-forecasting-setup"></a>Configuração da previsão de demanda

Este tópico descreve as tarefas de configuração que devem ser executadas para preparar a previsão de demanda.  

As tarefas de configuração incluem a configuração dos dados e parâmetros a seguir.

## <a name="item-allocation-key"></a>Chave de alocação de itens
Uma previsão de demanda será calculada para um item e suas dimensões somente se o item fizer parte de uma chave de alocação de item. A regra é imposta agrupar grandes números de itens, para que as previsões de demanda possam ser criadas mais rapidamente. O percentual da chave de alocação de item é ignorado quando previsões de demanda são geradas. As previsões são criadas com base em dados históricos apenas. 

Um item e suas dimensões devem ser parte de apenas uma chave de alocação de item, caso a chave de alocação de item seja usada durante a criação da previsão. 

Para uma unidade de manutenção de estoque (SKU) a uma chave de alocação de item, vá ** planejamento mestre ** &gt; ** de instalação ** &gt; ** previsão de demanda ** &gt; ** chaves de alocação de item **. Use a página **Atribuir itens** para atribuir um item a uma chave de alocação.

## <a name="intercompany-planning-groups"></a>Grupos de planejamento intercompanhia
A previsão de demanda gera previsões interempresariais. No Microsoft Dynamics 365 para operações, as empresas que estão planejadas junto são agrupadas em um grupo de planejamento intercompanhia. Para especificar, pela empresa, que as chaves de alocação de item devem ser consideradas para previsão de demanda, associar uma chave de alocação de item ao membro do grupo de planejamento intercompanhia ** planejamento mestre prestes a ** &gt; ** de instalação ** &gt; ** grupos de planejamento intercompanhia **. 

Por padrão, se uma chave de alocação de item seja atribuída aos membros do grupo de planejamento intercompanhia, uma previsão de demanda é calculada para todos os itens atribuídos a todas as chaves de alocação de itens de qualquer dynamics 365 para empresas de operações. Outras opções de filtragem para empresas e chaves de alocação de itens estão disponíveis na página **Gerar previsão estatística**. 

Analise o número de itens previstos. Itens desnecessários podem ocasionar o aumento dos custos quando você usar o Aprendizado de Máquina do Microsoft Azure.

## <a name="demand-forecasting-parameters"></a>Parâmetros de previsão de demanda
Para configurar parâmetros de previsões de demanda, vá ** planejamento mestre ** &gt; ** de instalação ** &gt; ** parâmetros da previsão de demanda **. Como a previsão de demanda é realizada entre empresas, a configuração é global. Em outras palavras, a configuração se aplica a todas as empresas. 

A previsão de demanda gera a previsão de quantidades. Portanto, a unidade de medida em que a quantidade deve ser expressa deve ser especificada no campo **Unidade de previsão de demanda**. A unidade de medida deve ser exclusiva para garantir que a agregação e a distribuição percentual faça sentido. Para obter mais informações sobre agregação e distribuição percentual, consulte [Ajustes manuais na previsão estatística](manual-adjustments-baseline-forecast.md). Para cada unidade de medida usada nas SKUs incluídas na previsão de demanda, verifique se há uma regra de conversão para a unidade de medida e a unidade de medida de previsão geral. Quando a geração de previsão é executada, a lista de itens que não têm uma conversão de unidade de medida é registrada, para que você possa corrigir facilmente a configuração. 

A previsão de demanda pode ser usada para prever a demanda dependente e independente. Por exemplo, se apenas a caixa de seleção **Ordem de venda** estiver marcada e se todos os itens considerados na previsão de demanda forem itens vendidos, o sistema calculará a demanda independente. No entanto, os subcomponentes críticos podem ser adicionados às chaves de alocação de itens e incluídos na previsão de demanda. Nesse caso, se a caixa de seleção **Linha de produção** estiver marcada, uma previsão de dependente será calculada. 

Há dois métodos para criar uma linha de base de previsão em dynamics 365 para as operações. Você pode usar modelos de previsão sobre os dados históricos ou apenas copiar sobre os dados históricos na previsão. O campo **Estratégia de geração de previsão** permite que você selecione entre esses dois métodos. Para usar modelos de previsão, selecione **Aprendizado de Máquina do Azure**. 

Ao clicar em **Dimensões de previsão** no painel esquerdo da página **Parâmetros de previsão de demanda**, você também pode selecionar o conjunto de dimensões de previsão a ser usado quando a previsão de demanda for gerada. Uma dimensão de previsão indica o nível de detalhes em que a previsão será definida. A empresa, o site e a chave de alocação de item são dimensões de previsão obrigatórias, mas você também pode gerar previsões no depósito, no status do estoque, no grupo de clientes, na conta de cliente, no país/região, no estado e no item e em todos os níveis de dimensão de item. 

A qualquer momento, você pode adicionar dimensões de previsão à lista de dimensões usadas na previsão de demanda. É possível também remover as dimensões de previsão da lista. No entanto, os ajustes manuais serão perdidos se você adicionar ou remover uma dimensão de previsão. 

Nem todos os itens se comportam da mesma forma sob uma perspectiva de previsão de demanda. Os itens semelhantes podem ser agrupados em uma única chave de alocação de item, e os parâmetros, como os tipos de transação e as configurações de método de previsão, podem ser definidos por chave de alocação de item. Clique em **Chaves de alocação de itens** no painel esquerdo da página **Parâmetros de previsão de demanda**. 

Para gerar a previsão, o dynamics 365 usa operações para um computador que tenha certeza do serviço Web. Para se conectar ao serviço, você deve fornecer o dynamics 365 para operações as seguintes informações você se conecte ao Microsoft Azure o computador do: sabe studio

-   Chave da API (interface de programação de aplicativos) do serviço Web
-   URL do ponto de extremidade do serviço Web
-   Nome da conta de armazenamento do Azure
-   Chave da conta de armazenamento do Azure

**Observação:** o nome e a chave da conta de armazenamento do Azure serão necessários apenas se você usar uma conta de armazenamento personalizada. Se você implanta os locais a versão, é necessário ter uma conta personalizada de armazenamento em Azure, assim o computador que sabe o serviço pode acessar os dados históricos. 

Para criar previsões de demanda, você pode implementar seu próprio serviço usando o computador que sabe o studio o dynamics ou 365 em experiências de previsões de demanda de operações. Instruções para implantar o dynamics 365 para a previsão de demanda de operações experimentam como um serviço Web do dynamics disponível for 365 para as operações. Na página **Parâmetros de previsão de demanda**, clique na guia **Aprendizado de Máquina do Azure**.

## <a name="settings-for-the-dynamics-365-for-operations-demand-forecasting-machine-learning-service"></a>Configurações para dynamics 365 para o computador de previsões de demanda de operações que sabe o serviço
Para exibir os parâmetros que podem ser configurados para dynamics 365 para o serviço de previsões de demanda de operações, vá ** planejamento mestre ** &gt; ** de instalação ** &gt; ** previsão de demanda ** &gt; ** parâmetros de algoritmo ** de previsão. ** Parâmetros de algoritmo de previsão ** o página mostra os valores padrão dos parâmetros. Você pode substituir os parâmetros ** parâmetros da previsão de demanda ** na página. Use a guia **Geral** para substituir os parâmetros globalmente ou use a guia **Chaves de alocação de itens** para substituir os parâmetros por chave de alocação de item. Os parâmetros que são substituídos em uma chave de alocação de item afetam apenas a previsão dos itens associados a essa chave de alocação de item.

<a name="see-also"></a>Consulte também
--------

[Introduction to demand forecasting](introduction-demand-forecasting.md)

[Generating a statistical baseline forecast](generate-statistical-baseline-forecast.md)

[Making manual adjustments to the baseline forecast](manual-adjustments-baseline-forecast.md)



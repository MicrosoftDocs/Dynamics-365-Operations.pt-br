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
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 5074f3ded26f55c6244feba9fcf0199c81cad468
ms.contentlocale: pt-br
ms.lasthandoff: 04/25/2017


---

# <a name="demand-forecasting-setup"></a>Configuração da previsão de demanda

[!include[banner](../includes/banner.md)]


Este tópico descreve as tarefas de configuração que devem ser executadas para preparar a previsão de demanda.  

As tarefas de configuração incluem a configuração dos dados e parâmetros a seguir.

## <a name="item-allocation-key"></a>Chave de alocação de itens
Uma previsão de demanda será calculada para um item e suas dimensões somente se o item fizer parte de uma chave de alocação de item. A regra é imposta agrupar grandes números de itens, para que as previsões de demanda possam ser criadas mais rapidamente. O percentual da chave de alocação de item é ignorado quando as previsões de demanda são geradas. As previsões são criadas com base em dados históricos apenas. 

Um item e suas dimensões devem ser parte de apenas uma chave de alocação de item, caso a chave de alocação de item seja usada durante a criação da previsão. 

Para adicionar uma SKU (unidade de manutenção de estoque) a uma chave de alocação de item, vá para **Planejamento mestre** &gt; **Configuração** &gt; **Previsão de demanda** &gt; **Chaves de alocação de itens**. Use a página **Atribuir itens** para atribuir um item a uma chave de alocação.

## <a name="intercompany-planning-groups"></a>Grupos de planejamento intercompanhia
A previsão de demanda gera previsões interempresariais. No Microsoft Dynamics 365 for Operations, as empresas que são planejadas juntas são mantidas em um grupo de planejamento intercompanhia. Para especificar, por empresa, quais chaves de alocação de item devem ser consideradas para previsão de demanda, associe uma chave de alocação de item ao membro do grupo de planejamento intercompanhia, acessando **Planejamento mestre** &gt; **Configuração** &gt; **Grupos de planejamento intercompanhia**. 

Por padrão, se nenhuma chave de alocação de item for atribuída aos membros do grupo de planejamento intercompanhia, uma previsão de demanda será calculada para todos os itens atribuídos a todas as chaves de alocação de itens de todas as empresas do Dynamics 365 for Operations. Outras opções de filtragem para empresas e chaves de alocação de itens estão disponíveis na página **Gerar previsão estatística**. 

Analise o número de itens previstos. Itens desnecessários podem ocasionar o aumento dos custos quando você usar o Aprendizado de Máquina do Microsoft Azure.

## <a name="demand-forecasting-parameters"></a>Parâmetros de previsão de demanda
Para configurar os parâmetros de previsão de demanda, vá para **Planejamento mestre** &gt; **Configuração** &gt; **Parâmetros de previsão de demanda**. Como a previsão de demanda é realizada entre empresas, a configuração é global. Em outras palavras, a configuração se aplica a todas as empresas. 

A previsão de demanda gera a previsão de quantidades. Portanto, a unidade de medida em que a quantidade deve ser expressa deve ser especificada no campo **Unidade de previsão de demanda**. A unidade de medida deve ser exclusiva para garantir que a agregação e a distribuição percentual faça sentido. Para obter mais informações sobre agregação e distribuição percentual, consulte [Ajustes manuais na previsão estatística](manual-adjustments-baseline-forecast.md). Para cada unidade de medida usada nas SKUs incluídas na previsão de demanda, verifique se há uma regra de conversão para a unidade de medida e a unidade de medida de previsão geral. Quando a geração de previsão é executada, a lista de itens que não têm uma conversão de unidade de medida é registrada, para que você possa corrigir facilmente a configuração. 

A previsão de demanda pode ser usada para prever a demanda dependente e independente. Por exemplo, se apenas a caixa de seleção **Ordem de venda** estiver marcada e se todos os itens considerados na previsão de demanda forem itens vendidos, o sistema calculará a demanda independente. No entanto, os subcomponentes críticos podem ser adicionados às chaves de alocação de itens e incluídos na previsão de demanda. Nesse caso, se a caixa de seleção **Linha de produção** estiver marcada, uma previsão de dependente será calculada. 

Há dois métodos para criar uma previsão estatística no Dynamics 365 for Operations. Você pode usar modelos de previsão sobre os dados históricos ou apenas copiar sobre os dados históricos na previsão. O campo **Estratégia de geração de previsão** permite que você selecione entre esses dois métodos. Para usar modelos de previsão, selecione **Aprendizado de Máquina do Azure**. 

Ao clicar em **Dimensões de previsão** no painel esquerdo da página **Parâmetros de previsão de demanda**, você também pode selecionar o conjunto de dimensões de previsão a ser usado quando a previsão de demanda for gerada. Uma dimensão de previsão indica o nível de detalhes em que a previsão será definida. A empresa, o site e a chave de alocação de item são dimensões de previsão obrigatórias, mas você também pode gerar previsões no depósito, no status do estoque, no grupo de clientes, na conta de cliente, no país/região, no estado e no item e em todos os níveis de dimensão de item. 

A qualquer momento, você pode adicionar dimensões de previsão à lista de dimensões usadas na previsão de demanda. É possível também remover as dimensões de previsão da lista. No entanto, os ajustes manuais serão perdidos se você adicionar ou remover uma dimensão de previsão. 

Nem todos os itens se comportam da mesma forma sob uma perspectiva de previsão de demanda. Os itens semelhantes podem ser agrupados em uma única chave de alocação de item, e os parâmetros, como os tipos de transação e as configurações de método de previsão, podem ser definidos por chave de alocação de item. Clique em **Chaves de alocação de itens** no painel esquerdo da página **Parâmetros de previsão de demanda**. 

Para gerar a previsão, o Dynamics 365 for Operations usa um serviço Web de Aprendizado de Máquina. Para se conectar ao serviço, você deve fornecer ao Dynamics 365 for Operations as seguintes informações se entrar no Estúdio de Aprendizado de Máquina do Microsoft Azure:

-   Chave da API (interface de programação de aplicativos) do serviço Web
-   URL do ponto de extremidade do serviço Web
-   Nome da conta de armazenamento do Azure
-   Chave da conta de armazenamento do Azure

**Observação:** o nome e a chave da conta de armazenamento do Azure serão necessários apenas se você usar uma conta de armazenamento personalizada. Se você implantar a versão local, deverá ter uma conta de armazenamento personalizada no Azure, para que o serviço de Aprendizado de Máquina acesse os dados históricos. 

Para criar previsões de demanda, você pode implantar seu próprio serviço usando os experimentos de previsão de demanda do Estúdio de Aprendizado de Máquina ou do Dynamics 365 for Operations. As instruções para implantar os experimentos de previsão de demanda do Dynamics 365 for Operations como um serviço Web estão disponíveis no Dynamics 365 for Operations. Na página **Parâmetros de previsão de demanda**, clique na guia **Aprendizado de Máquina do Azure**.

## <a name="settings-for-the-dynamics-365-for-operations-demand-forecasting-machine-learning-service"></a>Configurações do serviço de aprendizado de máquina da previsão de demanda do Dynamics 365 for Operations.
Para exibir os parâmetros que podem ser configurados para o serviço de previsão de demanda do Dynamics 365 for Operations, vá para **Planejamento Mestre** &gt; **Configuração** &gt; **Previsão de demanda** &gt; **Parâmetros do algoritmo de previsão**. A pagina **Parâmetros do algoritmo de previsão** mostra os valores padrão dos parâmetros. Você pode substituir os parâmetros na página **Parâmetros de previsão de demanda**. Use a guia **Geral** para substituir os parâmetros globalmente ou use a guia **Chaves de alocação de itens** para substituir os parâmetros por chave de alocação de item. Os parâmetros que são substituídos em uma chave de alocação de item afetam apenas a previsão dos itens associados a essa chave de alocação de item.

<a name="see-also"></a>Consulte também
--------

[Introdução à previsão de demanda](introduction-demand-forecasting.md)

[Gerando uma previsão estatística](generate-statistical-baseline-forecast.md)

[Ajustes manuais na previsão estatística](manual-adjustments-baseline-forecast.md)





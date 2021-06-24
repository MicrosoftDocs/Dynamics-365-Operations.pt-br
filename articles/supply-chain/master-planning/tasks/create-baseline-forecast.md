---
title: 'Guia: criar uma previsão de linha de base'
description: Um planejador de produção pode criar uma linha de base de previsão usando modelos de previsão das séries temporais ou copiando as demandas históricas.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqIntercompanyPlanningGroupSetup, ReqIntercompanyPlanningGroupAllocKeys, ReqDemPlanForecastParameters, ReqDemPlanCreateForecastDialog, SysQueryForm, ReqDemPlanForecastViewer
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 95a20b30827c9096dd8d8f67d149305cf594ff05
ms.sourcegitcommit: 15aacd0e109b05c7281407b5bba4e6cd99116c28
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "6223953"
---
# <a name="guide-create-a-baseline-forecast"></a>Guia: criar uma previsão de linha de base

[!include [banner](../../includes/banner.md)]

Um planejador de produção pode criar uma linha de base de previsão usando modelos de previsão das séries temporais ou copiando as demandas históricas. Este procedimento mostra como criar uma previsão da linha de base para todos os produtos com uma chave de alocação de itens ao copiar a demanda de histórico.

## <a name="set-up-an-item-allocation-key"></a>Configurar uma chave de alocação de item

1. Vá para **Planejamento principal > Configuração > Grupos de planejamento entre empresas**.
2. Use o Filtro Rápido para localizar registros. Por exemplo, filtre no campo *Nome* com um valor de *10*.
    * A previsão de demanda executa por meio da pessoa jurídica. Por isso é necessário configurar todas as empresas para o qual você deseja gerar previsões em um grupo de planejamento intercompanhia.  
3. Na lista, localize e selecione o registro desejado.
4. Selecione **Chaves de alocação de itens**.
    * Selecione todas as chaves de alocação de item para o qual você deseja criar previsões.  
5. Na lista, marque a linha selecionada.
    * Selecione a chave de alocação de item de D_Aloc.  
6. Selecione **>**.
7. Feche a página.
8. Feche a página.

## <a name="set-up-the-demand-forecasting-parameters"></a>Configurar os parâmetros de previsão de demanda

1. Vá para **Planejamento principal > Configuração > Previsão de demanda > Parâmetros de previsão de demanda**.
2. Expanda a seção **Parâmetros do algoritmo de previsão**.
3. No campo **Estratégia de geração de previsão**, selecione **Copiar histórico de demanda**.
4. Selecione **Salvar**.

## <a name="create-a-baseline-forecast"></a>Criar uma previsão de linha de base

1. Vá para **Planejamento principal > Previsão > Previsão de demanda > Gerar previsão de linha de base estatística**.
2. No campo **Data inicial**, insira uma data.
    * Se você tem ordens de venda que começam desde 1º de janeiro de 2015, insira esta data. Caso contrário, insira a data mais anterior das ordens de venda.  
3. No campo **Data final**, insira uma data.
    * Insira a última data de suas ordens de venda, por exemplo *2015-31-03*.  
4. No campo **Data inicial**, insira uma data.
    * Digite *2015-01-04*. Essa data será calculada automaticamente como a data de início da próxima da previsão.  
5. Expanda a seção **Registros a serem incluídos**.
6. Selecione **Filtro**.
7. Na lista, marque a linha selecionada.
    * Marque a linha em que **Campo** = *Grupo de planejamento entre empresas*.  
8. No campo **Critérios**, digite um valor.
    * Digite o grupo de planejamento entre empresas (por exemplo, *10*) que você usou na primeira tarefa.  
9. Na lista, localize e selecione o registro desejado.
    * Selecione a linha em que **Campo** = *Chave de alocação de item*.  
10. No campo **Critérios**, digite um valor.
11. Selecione **OK**.
12. Expanda a seção **Parâmetros avançados**.
13. No campo **Bucket de previsão**, selecione *Mês*.
14. No campo **Horizonte de previsão**, insira *3*.
15. No campo **Congelar limite de tempo**, insira *1*.
16. Selecione **OK**.

## <a name="visualize-the-demand-forecast"></a>Visualize a previsão de demanda

1. Vá para **Planejamento principal > Previsão > Previsão de demanda > Previsão de demanda ajustada**.
2. Na tabela de exibição agregada, selecione a célula na linha 1, coluna 2. Este é o segundo mês para o qual você criou uma previsão.
3. Defina **QtyCell** como *400*.
    * Na célula, insira um número diferente de aquele que foi previsto, por exemplo, 400.  
4. Você tiver feito um ajuste manual para a previsão. Observe a indicação gráfica na próxima etapa.
5. Selecione **Detalhes da linha de previsão**.
    * Nessa página, você pode ver os valores de precisão, a demanda histórica e a previsão. Você pode fazer alterações para a previsão também.  

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
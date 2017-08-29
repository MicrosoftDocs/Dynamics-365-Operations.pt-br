--- 
title: "Criar uma previsão de linha de base"
description: "Um planejador de produção pode criar uma linha de base de previsão usando modelos de previsão das séries temporais ou copiando as demandas históricas."
author: YuyuScheller
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: c94a9766319531bd8285cca04003225709ce2113
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-baseline-forecast"></a>Criar uma previsão de linha de base

[!include[task guide banner](../../includes/task-guide-banner.md)]

Um planejador de produção pode criar uma linha de base de previsão usando modelos de previsão das séries temporais ou copiando as demandas históricas. Este procedimento mostra como criar uma previsão da linha de base para todos os produtos com uma chave de alocação de itens ao copiar a demanda de histórico. 


## <a name="set-up-an-item-allocation-key"></a>Configurar uma chave de alocação de item
1. Vá para Planejamento mestre > Configuração > Grupos de planejamento intercompanhia.
2. Use o Filtro Rápido para localizar registros. Por exemplo, filtre o campo Nome com um valor de '10'.
    * A previsão de demanda executa por meio da pessoa jurídica. Por isso é necessário configurar todas as empresas para o qual você deseja gerar previsões em um grupo de planejamento intercompanhia.  
3. Na lista, localize e selecione o PDV desejado.
4. Clique em Chaves de alocação de item.
    * Selecione todas as chaves de alocação de item para o qual você deseja criar previsões.  
5. Na lista, marque a linha selecionada.
    * Selecione a chave de alocação de item de D_Aloc.  
6. Clique em >.
7. Feche a página.
8. Feche a página.

## <a name="set-up-the-demand-forecasting-paramters"></a>Configurar os parâmetros para previsão de demanda
1. Vá para Planejamento mestre > Configuração > Previsão de demanda > Parâmetros de previsão de demanda.
2. Expanda a seção de parâmetros de algoritmo de previsão.
3. No campo da estratégia de geração de previsão, selecione 'Copiar sobre demanda histórica'.
4. Clique em Salvar.

## <a name="create-a-baseline-forecast"></a>Criar uma previsão de linha de base
1. Vá para Planejamento mestre > Previsão > Previsão de demanda > Previsão estatística.
2. No campo De data, insira uma data.
    * Se você tem ordens de venda que começam desde 1º de janeiro de 2015, insira esta data. Caso contrário, insira a data mais anterior das ordens de venda.  
3. No campo Até, insira uma data.
    * Insira a última data das ordens de venda, por exemplo, "31-03-2015".  
4. No campo De data, insira uma data.
    * Insira "01-04-2015" Essa data será calculada automaticamente como a data de início da próxima da previsão.  
5. Expanda os Registros para incluir a seção.
6. Clique em Filtro.
7. Na lista, marque a linha selecionada.
    * Marque a linha no campo = grupo de planejamento intercompanhia.  
8. No campo Critérios, digite um valor.
    * Digite o grupo de planejamento intercompanhia, por exemplo, 10, que é usado na primeira tarefa.  
9. Na lista, localize e selecione o PDV desejado.
    * Selecione a linha em que o campo = chave de alocação de item.  
10. No campo Critérios, digite um valor.
11. Clique em OK.
12. Expanda a seção Parâmetros avançados.
13. No campo Classificação por Previsão, selecione 'Mês'.
14. No campo Horizonte de previsão, insira '3'.
15. No Tempo limite de congelamento, insira '1'.
16. Clique em OK.

## <a name="visualize-the-demand-forecast"></a>Visualize a previsão de demanda
1. Vá para Planejamento mestre > Previsão > Previsão de demanda > Previsão de demanda ajustada.
2. Na tabela de exibição agregada, selecione a célula na linha 1, coluna 2. Este é o segundo mês para o qual você criou uma previsão.
3. Definir QtyCell a '400'.
    * Na célula, insira um número diferente de aquele que foi previsto, por exemplo, 400.  
4. Você tiver feito um ajuste manual para a previsão. Observe a indicação gráfica na próxima etapa.
5. Clique em Detalhes da linha de previsão.
    * Nessa página, você pode ver os valores de precisão, a demanda histórica e a previsão. Você pode fazer alterações para a previsão também.  



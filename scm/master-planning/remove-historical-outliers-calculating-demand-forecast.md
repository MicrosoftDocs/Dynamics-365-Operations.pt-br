---
title: "Remover exceções de dados históricos de transação ao calcular uma previsão de demanda"
description: "Este artigo descreve como excluir exceções dos dados históricos que são usados para calcular uma previsão de demanda. Ao excluir as exceções, você pode aumentar a precisão de previsão."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqDemPlanForecastParameters, ReqDemPlanOutlierQuerySetup
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 72621
ms.assetid: 88a964af-14eb-4c5c-945b-388e5908362c
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 6f44e1ce566781f1586203528d55b13b28001a2c
ms.lasthandoff: 03/31/2017


---

# <a name="remove-outliers-from-historical-transaction-data-when-calculating-a-demand-forecast"></a>Remover exceções de dados históricos de transação ao calcular uma previsão de demanda

[!include[banner](../includes/banner.md)]


Este artigo descreve como excluir exceções dos dados históricos que são usados para calcular uma previsão de demanda. Ao excluir as exceções, você pode aumentar a precisão de previsão.

Você pode excluir exceções para melhorar a precisão de previsão. Esta é uma tarefa opcional. Veja uma visão geral do processo:

1.  Clique em **Planejamento mestre** &gt; **Configuração** &gt; **Previsão de demanda** &gt; **Remoção de exceção** para abrir a página **Remoção de exceção** na qual você pode usar uma consulta para selecionar as transações a serem excluídas.
2.  Selecione a empresa à qual a consulta se aplica. Insira um nome e uma descrição. O campo **Data da consulta** é automaticamente definido como a data atual.
3.  Marque a caixa de seleção **Ativa** para excluir as transações que foram localizadas pela consulta nos dados históricos. Essa configuração entrará em vigor quando você criar uma previsão estatística.
4.  Na página **Consulta de remoção de exceção**, você pode adicionar, remover e selecionar os critérios que definem quais transações serão excluídas quando a previsão estatística for calculada. Por exemplo, selecione um item ou uma transação de ordem específica a ser excluída.
5.  Clique em **Exibir transações**. A página **Transações de exceção** lista as transações que atendem aos critérios definidos na consulta e que serão excluídos dos dados históricos quando a previsão de demanda for calculada.

**Observação:** você também pode criar uma consulta com base em uma consulta existente. Selecione a consulta a ser copiada e então clique em **Duplicar**. O campo **Data da consulta** identifica a versão. Você pode usar a consulta como está ou pode clicar em **Editar consulta** para modificar os critérios. Opcionalmente, você pode modificar o nome e a descrição da nova consulta.

<a name="see-also"></a>Consulte também
--------

[Introdução à previsão de demanda](introduction-demand-forecasting.md)

[Monitorando a precisão da previsão](monitor-forecast-accuracy.md)




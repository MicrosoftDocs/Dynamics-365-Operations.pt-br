---
title: Remover exceções de dados históricos de transação ao calcular uma previsão de demanda
description: Este artigo descreve como excluir exceções dos dados históricos que são usados para calcular uma previsão de demanda. Ao excluir as exceções, você pode aumentar a precisão de previsão.
author: roxanadiaconu
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanForecastParameters, ReqDemPlanOutlierQuerySetup, ReqDemPlanOutlierQueryPreview
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72621
ms.assetid: 88a964af-14eb-4c5c-945b-388e5908362c
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2825aad67c4f61fb45ac56f07c8e677f6df3597bbe1cc01aad59182461414ba1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6774792"
---
# <a name="remove-outliers-from-historical-transaction-data-when-calculating-a-demand-forecast"></a>Remover exceções de dados históricos de transação ao calcular uma previsão de demanda

[!include [banner](../includes/banner.md)]

Este artigo descreve como excluir exceções dos dados históricos que são usados para calcular uma previsão de demanda. Ao excluir as exceções, você pode aumentar a precisão de previsão.

Você pode excluir exceções para melhorar a precisão de previsão. Esta é uma tarefa opcional. Veja uma visão geral do processo:

1.  Clique em **Planejamento mestre** &gt; **Configuração** &gt; **Previsão de demanda** &gt; **Remoção de exceção** para abrir a página **Remoção de exceção** na qual você pode usar uma consulta para selecionar as transações a serem excluídas.
2.  Selecione a empresa à qual a consulta se aplica. Insira um nome e uma descrição. O campo **Data da consulta** é automaticamente definido como a data atual.
3.  Marque a caixa de seleção **Ativa** para excluir as transações que foram localizadas pela consulta nos dados históricos. Essa configuração entrará em vigor quando você criar uma previsão estatística.
4.  Na página **Consulta de remoção de exceção**, você pode adicionar, remover e selecionar os critérios que definem quais transações serão excluídas quando a previsão estatística for calculada. Por exemplo, selecione um item ou uma transação de ordem específica a ser excluída.
5.  Clique em **Exibir transações**. A página **Transações de exceção** lista as transações que atendem aos critérios definidos na consulta e que serão excluídos dos dados históricos quando a previsão de demanda for calculada.

**Observação:** você também pode criar uma consulta com base em uma consulta existente. Selecione a consulta a ser copiada e então clique em **Duplicar**. O campo **Data da consulta** identifica a versão. Você pode usar a consulta como está ou pode clicar em **Editar consulta** para modificar os critérios. Opcionalmente, você pode modificar o nome e a descrição da nova consulta.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da previsão de demanda](introduction-demand-forecasting.md)

[​Monitorar precisão da previsão​](monitor-forecast-accuracy.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
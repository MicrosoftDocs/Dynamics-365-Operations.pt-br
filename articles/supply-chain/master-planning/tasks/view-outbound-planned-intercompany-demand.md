---
title: Exibir planejamento de demanda intercompanhia de saída
description: Este artigo fornece um procedimento que mostra como exibir o planejamento de demanda intercompanhia de saída.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqOutboundIntercompanyDemand
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dcdea0af5cb522646bc63c7e5ef1d4e54e0a3547
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8895631"
---
# <a name="view-outbound-planned-intercompany-demand"></a>Exibir planejamento de demanda intercompanhia de saída

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como exibir todas as ordens planejadas que serão cumpridas por um fornecedor intercompanhia. A empresa de dados demonstrativos utilizada para criar esse procedimento é a DEMF.

1. Selecione **Planejamento mestre**.
2. No campo **Plano**, insira ou selecione um valor.
    * No campo **Plano**, selecione o plano *10*.  
3. Selecione *Executar*.
4. No campo **Número de threads**, insira um número.
    * Isso representa o número de threads paralelos a serem usados no planejamento mestre.  
5. Selecione **OK**.
    * Isso pode levar algum tempo.  
6. Selecione **Planejamento de demanda intercompanhia**.
7. Selecione **Planejamento de demanda intercompanhia de saída**.
    * Esta página fornece uma visão geral de todas as demandas planejadas que serão cumpridas por um fornecedor interno da cadeia de fornecimento.  
8. Expanda a seção **Detalhes da demanda upstream**.
    * Nesta seção, você poderá ver os detalhes sobre como a solicitação será cumprida. É possível que você tenha que aguardar o planejamento mestre ser executado na empresa de fornecimento antes que possa ver informações adicionais aqui.  

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

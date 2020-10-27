---
title: Exibir planejamento de demanda intercompanhia de saída
description: Este procedimento mostra como exibir todas as ordens planejadas que serão cumpridas por um fornecedor intercompanhia.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqOutboundIntercompanyDemand
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 259ce229c18466b7d29fd231dc3f0be8a6906c6b
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3978095"
---
# <a name="view-outbound-planned-intercompany-demand"></a>Exibir planejamento de demanda intercompanhia de saída

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como exibir todas as ordens planejadas que serão cumpridas por um fornecedor intercompanhia. A empresa de dados demonstrativos utilizada para criar esse procedimento é a DEMF.

1. Clique em Planejamento mestre.
2. No campo Plano, insira ou selecione um valor.
    * No campo Plano, selecione o plano 10.  
3. Clique em Executar.
4. No campo Número de threads, insira um número.
    * Isso representa o número de threads paralelos a serem usados no planejamento mestre.  
5. Clique em OK.
    * Isso pode levar algum tempo.  
6. Clique em Planejamento de demanda intercompanhia.
7. Clique em Planejamento de demanda intercompanhia de saída.
    * Esta página fornece uma visão geral de todas as demandas planejadas que serão cumpridas por um fornecedor interno da cadeia de fornecimento.  
8. Expanda a seção Detalhes da demanda upstream.
    * Nesta seção, você poderá ver os detalhes sobre como a solicitação será cumprida. É possível que você tenha que aguardar o planejamento mestre ser executado na empresa de fornecimento antes que possa ver informações adicionais aqui.  


---
title: Finalizar uma ordem de produção
description: Este procedimento mostra como finalizar uma ordem de produção.
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cb84d3b1908d6be889a49f7386de876cb52141ab
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3149035"
---
# <a name="end-a-production-order"></a>Finalizar uma ordem de produção

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como finalizar uma ordem de produção. A empresa de dados demo usada para criar este procedimento é USMF. Este é o último procedimento de sete que explica o ciclo de vida da ordem de produção.


## <a name="end-a-production-order"></a>Finalizar uma ordem de produção
1. Vá para Controle de produção > Ordens de produção > Todas as ordens de produção.
    * Selecione uma ordem de produção com o status Relatada como concluída.  
2. No Painel de Ação, clique em Ordem de produção.
3. Clique em Finalizar.
    * Nesta página, você pode confirmar que deseja finalizar a ordem de produção.  
4. Clique na guia Geral.
5. No campo Data, insira uma data.
6. No campo Método de sucata, selecione 'Alocação'.
    * Ao selecionar o método Alocação, os custos dos materiais sucateados são adicionados às mercadorias finalizadas.  
7. Clique em OK.

## <a name="validate-calculation-results"></a>Validar resultados do cálculo
1. No Painel de Ação, clique em Gerenciar custos.
2. Clique em Visualizar comparação de custo.
    * Após a finalização da ordem de produção, é possível comparar o preço de custo estimado com o preço de custo realizado para obter uma visão geral das variações de produção.  

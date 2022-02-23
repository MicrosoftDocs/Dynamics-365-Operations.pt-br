---
title: Número de registros por diário
description: Este tópico descreve o relacionamento entre diários e registros de ativos quando você cria uma aquisição de ativo fixo ou proposta de depreciação por meio de um trabalho em lotes. Você pode definir o número máximo de registros incluídos para cada aquisição e para depreciação.
author: moaamer
manager: Ann Beebe
ms.date: 11/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-11-19
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: d4ba98cefdc0b555eedfaa56b6a3ca4870b5de93
ms.sourcegitcommit: 65f9e2584c0530b1a71655aae09101691726b47f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "4650646"
---
# <a name="number-of-books-per-journal"></a>Número de registros por diário

[!include [banner](../includes/banner.md)]

Este tópico descreve o relacionamento entre diários e registros de ativos quando você cria uma aquisição de ativo fixo ou proposta de depreciação por meio de um trabalho em lotes. Você pode definir o número máximo de registros incluídos para cada aquisição e para depreciação usando os campos da seção **Número de registros por diário** na guia **Geral** da página **Parâmetros de ativos fixos** (**Ativos fixos \> Configuração \> Parâmetros de ativos fixos**). Esses campos permitem que você distribua o número de registros de ativos por diário de aquisição e diário de depreciação.

Para uma proposta de aquisição, o valor padrão é de pelo menos 10.000 registros. Para uma proposta de depreciação, o valor padrão é de pelo menos 2.000 registros.

Por exemplo, se houver 4.000 ativos fixos e dois registros estiverem associados a cada ativo, um registro será lançado na camada atual e o outro será lançado na camada de imposto. Se você adquirir 4.000 ativos fixos por meio do processamento em lotes, o trabalho em lotes que cria um diário de aquisição de ativo fixo conterá 4.000 registros de ativos.

> [!NOTE]
> O diário criado continuará a ser usado até que o trabalho em lotes seja concluído.
>
> Os registros derivados não são incluídos no número máximo de registros por diário.

Você pode usar o processamento em lotes para executar a depreciação para o mesmo conjunto de ativos adquiridos. Por exemplo, um trabalho em lotes cria dois diários de depreciação, cada um com 2.000 registros de ativos. O primeiro diário conterá registros associados aos ativos fixos numerados de 1 a 2.000. O segundo diário conterá então os registros associados aos ativos fixos numerados de 2.001 a 4.000.

O trabalho de processamento em lotes exclui os registros fechados. Por exemplo, em um trabalho em lotes para depreciação, 10 dos 2.000 primeiros registros estão fechados. Nesse caso, o primeiro diário conterá registros associados aos ativos fixos numerados de 1 a 2.011. O segundo diário conterá então os registros associados aos ativos fixos numerados de 2.012 a 4.000.

O limite no número de registros será aplicado se as IDs de ativo duplicadas não existirem no mesmo diário. No entanto, se a ID do ativo for igual à ID do registro, o número de registros por diário poderá ser excedido para manter a ID do ativo no mesmo diário.

Por exemplo, há 5.001 IDs de ativo fixo, três registros estão associados a cada ID de ativo fixo e cada registro de ativo é lançado no mesmo nível de lançamento. A depreciação é executada por três meses consecutivos, sem recapitulação. O diário de depreciação será criado por meio de um trabalho em lotes, e o sistema criará sete diários com 667 IDs de ativo fixo e três registros para cada ID de ativo fixo. O resultado será 2.001 registros. Portanto, em três meses, haverá 6.003 linhas do diário para manter as mesmas IDs de ativo no mesmo diário. O sistema também criará um diário com 332 IDs de ativo fixo e três registros para cada ID de ativo fixo. Em três meses, haverá 2.988 linhas.

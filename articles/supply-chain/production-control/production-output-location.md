---
title: Local de saída de produção
description: Este tópico descreve a hierarquia usada para identificar o local de saída de produção.
author: johanhoffmann
manager: tfehr
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: e4002bf7dddb196edf306268ecc16e1bfa5d6d1e
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3211298"
---
# <a name="production-output-location"></a>Local de saída de produção

[!include [banner](../includes/banner.md)]

Este tópico descreve a hierarquia usada para identificar o local de saída de produção.

O local de saída de produção é o primeiro local onde uma mercadoria concluída é armazenada depois de produzida. Geralmente, esse local é próximo ao processo de produção que gera a mercadoria concluída. O local de saída de produção é usado como armazenamento intermediário do material antes que ele seja movido para a área de remessa, um local de armazenamento, um local de entrada de produção para um processo de produção downstream e assim por diante. 

Um local de saída de produção padrão é definido quando as mercadorias concluídas são relatadas em uma ordem de produção ou em uma ordem de lote. A hierarquia a seguir é usada para identificar este local de saída:

1. Use o local de saída definido no cabeçalho da ordem de produção ou da ordem de lote.
2. Se não houver um local ali, use o local de saída definido no recurso usado pela última operação definida no roteiro de produção.
3. Se não houver um local ali, use o local de saída definido no grupo de recursos usado pelo recurso na última operação definida no roteiro de produção.
4. Se não houver uma localização ali, use o local de saída definido no depósito definido na ordem de produção.

Um local de saída de produção padrão é definido apenas para os produtos configurados usando os processos avançados de depósito. Quando esse tipo de item for relatado como concluída, será criado o trabalho de depósito do tipo **Mercadorias concluídas armazenadas** ou **Co-produto e subproduto armazenados**. Esse tipo de trabalho usa o local de saída de produção como o local de separação. O local de armazenamento é determinado pelas diretivas de local.

---
title: "Definições de lançamento"
description: "Este artigo fornece informações sobre definições de lançamento, e como definir e vinculá-las. Para tipos de lançamento e documentos com suporte, você pode usar definições de lançamento em vez de perfis de lançamento para classificar as contas principais e as dimensões financeiras em entradas contábeis."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: JournalizingDefinition, JournalizingDefinitionTrans, LedgerParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 15741
ms.assetid: 1495e7e0-2e39-464c-8da9-f55b1ca1c6bb
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 513d3e20e0c89eb0064e3c1bc11a3a8dea43cfe4
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="posting-definitions"></a>Definições de lançamento

[!INCLUDE [banner](../includes/banner.md)]

Este artigo fornece informações sobre definições de lançamento, e como definir e vinculá-las. Para tipos de lançamento e documentos com suporte, você pode usar definições de lançamento em vez de perfis de lançamento para classificar as contas principais e as dimensões financeiras em entradas contábeis.

Para tipos de lançamento e documentos com suporte, você pode usar definições de lançamento em vez de perfis de lançamento para classificar as contas principais e as dimensões financeiras em entradas contábeis. Você pode exibir os documentos e os tipos de lançamento com suporte na página **Definições de lançamento de transação**. 

Para começar a usar definições de lançamento, selecione a opção**Usar definições de lançamento** na página **Parâmetros de contabilidade**. Mesmo quando você usa definições de lançamento, ainda deve definir perfis de lançamento para as entradas de origem e os tipos de lançamento e os documentos sem suporte. 

Você deve usar definições de lançamento para habilitar a contabilidade de ônus para ordens de compra e a contabilidade de pré-ônus para requisições de compra.

## <a name="defining-posting-definitions"></a>Definições de lançamento
Use a página **Definições de lançamento** para especificar os critérios de correspondência e para definir as entradas que devem ser geradas quando ocorre uma correspondência. Os critérios de correspondência são avaliados para as entradas de origem como distribuições contábeis. 

Na página **Definições de lançamento**, você também pode atribuir números de prioridade a linhas de entrada para controlar a ordem em que as linhas são avaliadas. As linhas com o número de menor prioridade são avaliadas primeiro. Por exemplo, todas as linhas com uma prioridade 1 são avaliadas, depois as linhas com uma prioridade 2 e assim por diante. Quando uma correspondência for encontrada, os outros critérios de correspondência serão ignorados. Além disso, apenas os critérios no grupo que correspondem à transação de origem criarão entradas geradas. 

Você pode validar suas definições de lançamento usando o assistente **Testar definição de lançamento**. Depois de definir uma entrada de origem de exemplo para uma definição de lançamento, você verá as entradas geradas. 

Você pode usar versões da definição de lançamento junto com datas efetivas. Por exemplo, você pode criar uma versão futura de uma definição de lançamento para lançar em uma conta contábil diferente em um novo ano fiscal. 

Use a página **Definições de lançamento de transação** para atribuir definições de lançamento aos tipos de transação.

## <a name="linking-posting-definitions"></a>Vinculação de definições de lançamento
Você pode vincular de uma definição de lançamento para outra quando cria definições de lançamento. Os critérios para a definição à qual você vinculou são então considerados, além dos critérios para a definição de lançamento atual. Esse recurso ajuda a economizar seu tempo, já que você não precisa reinserir os critérios na Guia Rápida **Entradas** na página **Definições de lançamento** para a definição atual caso você já tenha inserido essas linhas para outra definição. 

Nos diagramas ou nas tabelas, inclua todos os links que talvez sejam usados. Para evitar conflitos com a definição de lançamento atual, verifique se as linhas em qualquer definição de lançamento às quais você esteja vinculando sejam exclusivas. 

As seguintes limitações se aplicam quando você cria links em definições de lançamento:

-   Uma determinada definição de lançamento pode vincular a outra definição de lançamento ou ser vinculada de outra definição de lançamento, mas não ambos. No entanto, uma definição de lançamento pode ser vinculada a várias definições de lançamento.
-   Você só pode configurar links entre definições de lançamento que estejam no mesmo módulo.
-   Você pode atribuir uma definição de lançamento a qualquer tipo de transação, mas o tipo de transação deve estar no mesmo módulo que a definição de lançamento. Use a página **Definições de lançamento de transação** para ver em qual módulo está um tipo de transação.


Para obter mais informações, consulte [Exemplos de definição de lançamento](example-posting-definitions.md). 




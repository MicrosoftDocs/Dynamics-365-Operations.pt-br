---
title: Configurar alertas de fraude
description: "Este tópico explica como configurar regras para alertar representantes de atendimento ao cliente sobre informações potencialmente fraudulentas quando as ordens são processadas. Você também pode especificar códigos a serem usados para colocar ordens suspeitas manualmente ou manualmente em espera."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 79103
ms.assetid: e342af8d-7498-4d20-8483-ab368429c578
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail Version
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 7255f2b7e49f56a731d0e3745b4752091013668b
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="set-up-fraud-alerts"></a>Configurar alertas de fraude

[!include[banner](includes/banner.md)]


Este tópico explica como configurar regras para alertar representantes de atendimento ao cliente sobre informações potencialmente fraudulentas quando as ordens são processadas. Você também pode especificar códigos a serem usados para colocar ordens suspeitas manualmente ou manualmente em espera. 

Antes de configurar e usar as regras de verificação de fraude, você deve habilitar a verificação de fraude e definir os valores básicos de verificação de fraude nos parâmetros do call center. Há dois tipos de regras de fraude:

-   **Regras estáticas** - usam um valor específico; por exemplo, um número de telefone inserido em uma lista de bloqueio.
-   **Regras dinâmicas** - podem ser compostas por variáveis e condições.

Antes de criar uma regra dinâmica, você deve criar as variáveis e as condições que definem a quem a regra se aplica e quando a regra deve ser aplicada. Por exemplo, você deseja criar uma regra para exigir que qualquer ordem de venda criada pelo cliente 1202 com valor de 1.000,00 ou mais seja colocada em espera até que o pagamento do cliente seja verificado. Nesse caso, as variáveis são o cliente 1202 e um valor total de 1.000,00 da ordem. A condição especifica que, se o cliente 1202 fizer um pedido, e o valor total da ordem for igual ou superior a 1.000,00, a ordem de venda deverá ser colocada em espera até que o pagamento do cliente seja verificado.





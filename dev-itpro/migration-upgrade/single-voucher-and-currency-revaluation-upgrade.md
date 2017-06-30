---
title: "Atualização de reavaliação de único comprovante e de moeda"
description: "Algumas organizações inserem diários que contêm um único comprovante que possui mais de um cliente ou fornecedor e também executam o processo de reavaliação de Contas a Receber ou Contas a Pagar. Este tópico descreve as etapas que essas organizações devem seguir ao atualizar para o Microsoft Dynamics 365 for Operations versão 1611."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: d3c6d817424be79b09ccdd89deb7f31599fe9bf5
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="single-voucher-and-currency-revaluation-upgrade"></a>Atualização de reavaliação de único comprovante e de moeda

[!include[banner](../includes/banner.md)]


Algumas organizações inserem diários que contêm um único comprovante que possui mais de um cliente ou fornecedor e também executam o processo de reavaliação de Contas a Receber ou Contas a Pagar. Este tópico descreve as etapas que essas organizações devem seguir ao atualizar para o Microsoft Dynamics 365 for Operations versão 1611.

Siga estas etapas quando você atualizar para Microsoft Dynamics 365 for Operations versão 1611.

1.  Antes de atualizar para o Dynamics 365 for Operations, execute os processos de reavaliação de moeda estrangeira para Contas a receber e Contas a pagar. Defina o campo **Método** para **Data da fatura**. É criada uma transação de reavaliação que reverte a última reavaliação de moeda estrangeira. Portanto, as transações em aberto são avaliadas em sua moeda de contabilização original.
2.  Atualize para o Dynamics 365 for Operations versão 1611.
3.  Execute novamente os processos de reavaliação de contas a receber e contas a pagar. Agora, defina o campo **Método** para **Padrão**. É criada uma nova transação de reavaliação baseada nas taxas de câmbio atuais. Essa transação registra o ganho/perda não realizado e a conta de razão contábil correta.






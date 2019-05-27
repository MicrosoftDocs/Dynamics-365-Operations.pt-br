---
title: Atualizar diários de comprovante único e reavaliações de moeda
description: Algumas organizações inserem diários que contêm um único comprovante que possui mais de um cliente ou fornecedor e também executam o processo de reavaliação de Contas a Receber ou Contas a Pagar. Este tópico descreve as etapas que essas organizações devem seguir ao atualizar para o Microsoft Dynamics 365 for Operations versão 1611.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 343fa226e1cf9072696082e9ebf0a1629e553ae9
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1554511"
---
# <a name="upgrade-single-voucher-journals-and-currency-revaluations"></a>​Atualizar diários de comprovante único e reavaliações de moeda

[!include [banner](../includes/banner.md)]

Algumas organizações inserem diários que contêm um único comprovante que possui mais de um cliente ou fornecedor e também executam o processo de reavaliação de Contas a Receber ou Contas a Pagar. Este tópico descreve as etapas que essas organizações devem seguir ao atualizar para o Microsoft Dynamics 365 for Operations versão 1611.

Siga estas etapas quando fizer o upgrade para o Microsoft Dynamics 365 for Operations versão 1611.

1.  Antes de atualizar para o Dynamics 365 for Operations, execute os processos de reavaliação de moeda estrangeira para Contas a receber e Contas a pagar. Defina o campo **Método** para **Data da fatura**. É criada uma transação de reavaliação que reverte a última reavaliação de moeda estrangeira. Portanto, as transações em aberto são avaliadas em sua moeda de contabilização original.
2.  Atualize para o Dynamics 365 for Operations versão 1611.
3.  Execute novamente os processos de reavaliação de contas a receber e contas a pagar. Agora, defina o campo **Método** para **Padrão**. É criada uma nova transação de reavaliação baseada nas taxas de câmbio atuais. Essa transação registra o ganho/perda não realizado e a conta de razão contábil correta.





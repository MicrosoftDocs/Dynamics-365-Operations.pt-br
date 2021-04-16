---
title: ​Atualizar diários de comprovante único e reavaliações de moeda
description: Este tópico descreve como atualizar diários de comprovante único e reavaliações de moeda.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 6b66b969d13cff7f1f39fb644f459aa92bea198f
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5743912"
---
# <a name="upgrade-single-voucher-journals-and-currency-revaluations"></a>​Atualizar diários de comprovante único e reavaliações de moeda

[!include [banner](../includes/banner.md)]

Algumas organizações inserem diários que contêm um único comprovante que possui mais de um cliente ou fornecedor e também executam o processo de reavaliação de Contas a Receber ou Contas a Pagar. Este tópico descreve as etapas que essas organizações devem seguir ao atualizar para o Microsoft Dynamics 365 for Operations versão 1611.

Siga estas etapas quando fizer o upgrade para o Microsoft Dynamics 365 for Operations versão 1611.

1.  Antes de atualizar para o Finance and Operations, execute os processos de reavaliação de moeda estrangeira para Contas a receber e Contas a pagar. Defina o campo **Método** para **Data da fatura**. É criada uma transação de reavaliação que reverte a última reavaliação de moeda estrangeira. Portanto, as transações em aberto são avaliadas em sua moeda de contabilização original.
2.  Atualize para a versão 1611.
3.  Execute novamente os processos de reavaliação de contas a receber e contas a pagar. Agora, defina o campo **Método** para **Padrão**. É criada uma nova transação de reavaliação baseada nas taxas de câmbio atuais. Essa transação registra o ganho/perda não realizado e a conta de razão contábil correta.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
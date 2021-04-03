---
title: ​Atualizar diários de comprovante único e reavaliações de moeda
description: Este tópico descreve como atualizar diários de comprovante único e reavaliações de moeda.
author: ShylaThompson
manager: AnnBe
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
ms.openlocfilehash: fb4eca4933716105789d3bbc21dd374395211d1d
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559512"
---
# <a name="upgrade-single-voucher-journals-and-currency-revaluations"></a>​Atualizar diários de comprovante único e reavaliações de moeda

[!include [banner](../includes/banner.md)]

Algumas organizações inserem diários que contêm um único comprovante que possui mais de um cliente ou fornecedor e também executam o processo de reavaliação de Contas a Receber ou Contas a Pagar. Este tópico descreve as etapas que essas organizações devem seguir ao atualizar para o Microsoft Dynamics 365 for Operations versão 1611.

Siga estas etapas quando fizer o upgrade para o Microsoft Dynamics 365 for Operations versão 1611.

1.  Antes de atualizar para o Finance and Operations, execute os processos de reavaliação de moeda estrangeira para Contas a receber e Contas a pagar. Defina o campo **Método** para **Data da fatura**. É criada uma transação de reavaliação que reverte a última reavaliação de moeda estrangeira. Portanto, as transações em aberto são avaliadas em sua moeda de contabilização original.
2.  Atualize para a versão 1611.
3.  Execute novamente os processos de reavaliação de contas a receber e contas a pagar. Agora, defina o campo **Método** para **Padrão**. É criada uma nova transação de reavaliação baseada nas taxas de câmbio atuais. Essa transação registra o ganho/perda não realizado e a conta de razão contábil correta.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
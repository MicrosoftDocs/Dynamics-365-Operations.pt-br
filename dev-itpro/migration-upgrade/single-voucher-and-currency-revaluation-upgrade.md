---
title: "Atualização de revalorização de vouchers e moedas para Microsoft Dynamics 365 for Operations versão 1611"
description: "Algumas organizações inserem diários que contêm um único comprovante que possui mais de um cliente ou fornecedor e também executam o processo de reavaliação de Contas a Receber ou Contas a Pagar. Este tópico descreve as etapas que essas organizações devem seguir ao atualizar para o Microsoft Dynamics 365 for Operations versão 1611."
author: twheeloc
manager: AnnBe
ms.date: 2016-12-28 16 - 04 - 17
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: d42c753d0dc8b8efc2a0d2a26da32a4951d85503
ms.lasthandoff: 03/31/2017


---

# <a name="single-voucher-and-currency-revaluation-upgrade-for-microsoft-dynamics-365-for-operations-version-1611"></a>Atualização de revalorização de vouchers e moedas para Microsoft Dynamics 365 for Operations versão 1611

Algumas organizações inserem diários que contêm um único comprovante que possui mais de um cliente ou fornecedor e também executam o processo de reavaliação de Contas a Receber ou Contas a Pagar. Este tópico descreve as etapas que essas organizações devem seguir ao atualizar para o Microsoft Dynamics 365 for Operations versão 1611.

Siga estas etapas quando você atualizar para Microsoft Dynamics 365 for Operations versão 1611.

1.  Antes de atualizar para o Dynamics 365 for Operations, execute os processos de reavaliação de moeda estrangeira para Contas a receber e Contas a pagar. Defina o campo **Método** para **Data da fatura**. É criada uma transação de reavaliação que reverte a última reavaliação de moeda estrangeira. Portanto, as transações em aberto são avaliadas em sua moeda de contabilização original.
2.  Atualize para o Dynamics 365 for Operations versão 1611.
3.  Execute novamente os processos de reavaliação de contas a receber e contas a pagar. Agora, defina o campo **Método** para **Padrão**. É criada uma nova transação de reavaliação baseada nas taxas de câmbio atuais. Essa transação registra o ganho/perda não realizado e a conta de razão contábil correta.




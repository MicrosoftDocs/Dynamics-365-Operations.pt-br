---
title: "Atualização de reavaliação de única comprovante e do Microsoft Dynamics 365 para a versão 1611 de operações"
description: "Algumas organizações enter em diários que contenham uma única comprovante com mais de um cliente ou fornecedor, e também desempenham contas a receber ou de reavaliação de moeda estrangeira contas a pagar processo. Este tópico descreve as etapas que as organizações deve controlar quando aberto ao Microsoft Dynamics 365 para a versão 1611 de operações."
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

# <a name="single-voucher-and-currency-revaluation-upgrade-for-microsoft-dynamics-365-for-operations-version-1611"></a>Atualização de reavaliação de única comprovante e do Microsoft Dynamics 365 para a versão 1611 de operações

Algumas organizações enter em diários que contenham uma única comprovante com mais de um cliente ou fornecedor, e também desempenham contas a receber ou de reavaliação de moeda estrangeira contas a pagar processo. Este tópico descreve as etapas que as organizações deve controlar quando aberto ao Microsoft Dynamics 365 para a versão 1611 de operações.

Rastrear estas etapas na atualização ao Microsoft Dynamics 365 para a versão 1611 de operações.

1.  Antes de atualizar o dynamics 365 para operações, execute os processos de reavaliação de moeda estrangeira para contas a receber e contas a pagar. ** Definir o campo método ** ** ** data de nota fiscal. Uma transação de reavaliação é criada inverta reavaliação de moeda estrangeira a última vez. Portanto, as transações abertas serão avaliadas contábil na moeda original.
2.  Atualizar o dynamics 365 para a versão 1611 de operações.
3.  Executar contas a receber e a reavaliação de moeda estrangeira contas a pagar processos novamente. Esse horário, definem ** ** o campo método ** ** padrão. Uma nova transação de reavaliação criado é baseada nas taxas de câmbio atuais. Esta transação registra o lucro não realizado/perdas e a conta resumo correta.




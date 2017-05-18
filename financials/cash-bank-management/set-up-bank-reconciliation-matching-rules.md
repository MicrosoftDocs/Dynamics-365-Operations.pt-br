---
title: "Configurar regras de correspondência de reconciliação bancária"
description: "Este artigo explica como configurar regras de correspondência de reconciliação e a regra de correspondência de reconciliação para ajudar no processo de reconciliação bancária. As regras correspondência de reconciliação são um conjunto de critérios usados para filtrar as linhas de extrato bancário e as linhas de documento bancário durante o processo de reconciliação."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BankReconciliationMatchRule, BankReconciliationMatchRuleSet
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 12971
ms.assetid: b5073f83-31dc-404f-af42-3fd84a02a7c6
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: fc3b12d05d6acb54a3868b67e1168188fcb12a6f
ms.contentlocale: pt-br
ms.lasthandoff: 04/25/2017


---

# <a name="set-up-bank-reconciliation-matching-rules"></a>Configurar regras de correspondência de reconciliação bancária

[!include[banner](../includes/banner.md)]


Este artigo explica como configurar regras de correspondência de reconciliação e a regra de correspondência de reconciliação para ajudar no processo de reconciliação bancária. As regras correspondência de reconciliação são um conjunto de critérios usados para filtrar as linhas de extrato bancário e as linhas de documento bancário durante o processo de reconciliação.

É possível configurar regras de correspondência de reconciliação e a regra de correspondência de reconciliação para ajudar no processo de reconciliação bancária. Uma regra de correspondência de reconciliação é um conjunto de critérios usados para filtrar as linhas do extrato bancário e as linhas de transação bancária no Microsoft Dynamics 365 for Operations durante o processo de reconciliação. Use a página **Regras de correspondência da reconciliação** para configurar as regras de correspondência da reconciliação. Você pode configurar mais de uma regra de correspondência e depois criar um conjunto de regras de correspondência da reconciliação na página **Conjuntos de regras da correspondência da reconciliação**. 

> [!NOTE] 
> As regras de correspondência da reconciliação bancária são usadas se você reconciliar um extrato bancário eletrônico ao usar a reconciliação bancária avançada. 

Na página **Regras de correspondência de reconciliação**, é possível selecionar quais critérios de ação e de seleção são usados quando a regra de correspondência é executada. No grupo de campo **Ações**, selecione a ação que será executada quando a regra de correspondência for executada durante o processo de reconciliação.  

> [!NOTE] 
> A opção que você seleciona determina os campos que aparecem.

|                                    |                                                                                                                                                                                                                                                                                                               |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Ação**                         |                                                                                                                                                                                                                                                                                                               | **Critérios de seleção disponíveis quando a ação for selecionada**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Fazer a correspondência com o documento bancário**       | Criar critérios para especificar como fazer a correspondência dos documentos bancários e das linhas de extrato bancário quando a regra de correspondência é executada na página **Planilha de reconciliação bancária**. As linhas de transação são selecionadas de acordo com os critérios adicionais configurados nas Guias Rápidas.                                | **Etapa 1: Define a regra de correspondência** – Selecione critérios para especificar quais extratos bancários devem ser correspondidos com as transações bancárias do Dynamics 365 for Operations. **Etapa 2 (opcional): Selecione as linhas do demonstrativo para executar regras de correspondência:**  Aplicar um filtro na linha do demonstrativo para executar as regras.                                                                                                                                                                                                                                                                                                               |
| **Limpar linhas de demonstrativo de estorno** | Crie critérios para especificar como as linhas do demonstrativo de estorno deve ser removido da página **Planilha da reconciliação bancária** quando a correspondência for executada. Esta opção é usada quando um erro bancário faz com que duas linhas do extrato bancário sejam listadas no extrato bancário importado e as linhas devem ser reconciliadas. | **Etapa 1**:**Localizar linhas do demonstrativo de estorno**– Adicionar critérios de seleção para selecionar linhas do extrato bancário do estorno. Por exemplo, para selecionar somente cheques, selecione o campo **Código de transação bancária**, selecione o sinal de (+) no campo **Operador**, e insira **Cheques** no campo Valor. **Etapa 2: Localizar linhas do demonstrativo original** – Você pode adicionar critérios de seleção para fazer a correspondência das linhas de documento bancário com as linhas de extrato bancário. **Etapa 3: Encontrar as transações bancárias do Dynamics 365 for Operations **– Você pode adicionar critérios de seleção para corresponder às transações bancárias do Dynamics 365 for Operations para linhas de extrato bancário. |
| **Marcar novas transações**          | Crie critérios para especificar como as novas transações devem ser marcadas na página **Planilha da reconciliação bancári**a quando a correspondência for executada.                                                                                                                                                                 | **Etapa 1: Localizar linhas do demonstrativo**– Adicionar campos de seleção para especificar quais linhas do extrato bancário devem ser selecionadas na página **Planilha de reconciliação bancária**. **Etapa 2: Encontrar as transações bancárias do Dynamics 365 for Operations **– Você pode adicionar critérios de seleção para pesquisar linhas de documento bancário. Se nenhum documento bancário for localizado, uma linha do demonstrativo será marcada como uma nova transação.                                                                                                                                                                                                                                             |

 








---
title: Configurar regras de correspondência de reconciliação bancária
description: Este tópico explica como configurar regras de correspondência de reconciliação e a regra de correspondência de reconciliação para ajudar no processo de reconciliação bancária. As regras correspondência de reconciliação são um conjunto de critérios usados para filtrar as linhas de extrato bancário e as linhas de documento bancário durante o processo de reconciliação.
author: panolte
manager: AnnBe
ms.date: 08/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankReconciliationMatchRule, BankReconciliationMatchRuleSet
audience: Application User
ms.reviewer: roschlom
ms.custom: 12971
ms.assetid: b5073f83-31dc-404f-af42-3fd84a02a7c6
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 39b03bd0834b5142d21a4ab17a7d7ad18c4a574b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5231509"
---
# <a name="set-up-bank-reconciliation-matching-rules"></a>Configurar regras de correspondência de reconciliação bancária

[!include [banner](../includes/banner.md)]

Este tópico explica como configurar regras de correspondência de reconciliação e a regra de correspondência de reconciliação para ajudar no processo de reconciliação bancária. As regras correspondência de reconciliação são um conjunto de critérios usados para filtrar as linhas de extrato bancário e as linhas de documento bancário durante o processo de reconciliação.

É possível configurar regras de correspondência de reconciliação e a regra de correspondência de reconciliação para ajudar no processo de reconciliação bancária. Uma regra de correspondência de reconciliação é um conjunto de critérios usados para filtrar as linhas do extrato bancário e as linhas de transação bancária no Dynamics 365 Finance durante o processo de reconciliação. Use a página **Regras de correspondência da reconciliação** para configurar as regras de correspondência da reconciliação. Você pode configurar mais de uma regra de correspondência e depois criar um conjunto de regras de correspondência da reconciliação na página **Conjuntos de regras da correspondência da reconciliação**. 

> [!NOTE] 
> As regras de correspondência da reconciliação bancária são usadas se você reconciliar um extrato bancário eletrônico ao usar a reconciliação bancária avançada. 

Na página **Regras de correspondência de reconciliação**, é possível selecionar quais critérios de ação e de seleção são usados quando a regra de correspondência é executada. No grupo de campo **Ações**, selecione a ação que será executada quando a regra de correspondência for executada durante o processo de reconciliação.  

Por padrão, as regras de correspondência coincidirão com o primeiro documento bancário que atende aos critérios da regra de correspondência. Se vários documentos bancários atenderem aos critérios da regra, o parâmetro para exigir a correspondência manual poderá ser ativado, indo para o **Gerenciamento de caixa e de bancos > Configuração > Parâmetros de gerenciamento de caixa e de bancos > Reconciliação bancária > Exigir a correspondência manual quando as regras de correspondência de reconciliação bancária avançada localizarem vários documentos que correspondam ao valor**.

> [!NOTE] 
> A opção que você seleciona determina os campos que aparecem.

|                                    |                                                                                                                                                                                                                                                                                                               |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Ação**                         |                                                                                                                                                                                                                                                                                                               | **Critérios de seleção disponíveis quando a ação for selecionada**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Fazer a correspondência com o documento bancário**       | Criar critérios para especificar como fazer a correspondência dos documentos bancários e das linhas de extrato bancário quando a regra de correspondência é executada na página **Planilha de reconciliação bancária**. As linhas de transação são selecionadas de acordo com os critérios adicionais configurados nas Guias Rápidas.                                | **Etapa 1: Definir a regra de correspondência** – Selecione os critérios para especificar para quais extratos bancários deve ser feita uma correspondência com transações bancárias do Finance. **Etapa 2 (opcional): Selecione as linhas do demonstrativo para executar regras de correspondência:**  Aplicar um filtro na linha do demonstrativo para executar as regras.                                                                                                                                                                                                                                                                                                               |
| **Limpar linhas de demonstrativo de estorno** | Crie critérios para especificar como as linhas do demonstrativo de estorno deve ser removido da página **Planilha da reconciliação bancária** quando a correspondência for executada. Esta opção é usada quando um erro bancário faz com que duas linhas do extrato bancário sejam listadas no extrato bancário importado e as linhas devem ser reconciliadas. | **Etapa 1**:**Localizar linhas do demonstrativo de estorno**– Adicionar critérios de seleção para selecionar linhas do extrato bancário do estorno. Por exemplo, para selecionar somente cheques, selecione o campo **Código de transação bancária**, selecione o sinal de (+) no campo **Operador**, e insira **Cheques** no campo Valor. **Etapa 2: Localizar linhas do demonstrativo original** – Você pode adicionar critérios de seleção para fazer a correspondência das linhas de documento bancário com as linhas de extrato bancário. **Etapa 3: Localizar transações bancárias do Finance** – É possível adicionar critérios de seleção para fazer a correspondências das transações bancárias do Finance com as linhas do extrato bancário. |
| **Marcar novas transações**          | Crie critérios para especificar como as novas transações devem ser marcadas na página **Planilha da reconciliação bancária** quando a correspondência é executada.                                                                                                                                                                 | **Etapa 1: Localizar linhas do demonstrativo**– Adicionar campos de seleção para especificar quais linhas do extrato bancário devem ser selecionadas na página **Planilha de reconciliação bancária**. **Etapa 2: Localizar Finance and Operations** – É possível adicionar critérios de seleção para pesquisar linhas do documento bancário. Se nenhum documento bancário for localizado, uma linha do demonstrativo será marcada como uma nova transação.                                                                                                                                                                                                                                             |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
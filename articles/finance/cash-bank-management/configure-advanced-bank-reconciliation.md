---
title: Processo de configuração de reconciliação bancária avançada
description: A reconciliação bancária avançada permite importar extratos bancários eletrônicos e reconciliá-los automaticamente com transações bancárias no Microsoft Dynamics 365 Finance. Este artigo explicará o processo de configuração da reconciliação.
author: panolte
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankReconciliationMatchRule, BankReconciliationMatchRuleSet
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 98303
ms.assetid: ae071f04-f038-4b17-812d-0a241ed15521
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7103cb93ad0d9ea0f1b92e317bee7454eb08d1f2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440491"
---
# <a name="advanced-bank-reconciliation-setup-process"></a>Processo de configuração de reconciliação bancária avançada

[!include [banner](../includes/banner.md)]

A reconciliação bancária avançada permite importar extratos bancários eletrônicos e reconciliá-los automaticamente com transações bancárias no Microsoft Dynamics 365 Finance. Este artigo irá explicar o processo de configuração da reconciliação.  

Existem diversas partes que devem ser configuradas antes que a funcionalidade de reconciliação bancária avançada seja utilizada. Para obter mais informações sobre como configurar a importação de extrato bancário, consulte [Configurar o processo de importação de reconciliação bancária avançada](set-up-advanced-bank-reconciliation-import-process.md).  Os requisitos para configurar o processo de reconciliação estão detalhados abaixo.

## <a name="transaction-codes"></a>Códigos de transação
Os códigos de transação podem ser usados como parte das regras de correspondência de reconciliação bancária. Os códigos de transação ajudarão na correspondência apenas dos mesmos tipos de transações entre o Finance and Operations e o seu extrato bancário. Para realizar esse tipo de correspondência, primeiro você deve definir os tipos de transação usados em transações bancárias no Finance e depois mapear esses tipos com os códigos de transação do extrato usados por seu banco. Os tipos de transação das transações bancárias são definidos na página **Tipo de transação bancária**. Também é aqui em que você define a conta principal a ser usada para postagens associadas a esse tipo de transação. 

Após a definição dos seus códigos de transação bancária, mapeie-os para os códigos de transação usados nos seus extratos bancários eletrônicos. Esse processo de mapeamento é realizado por meio da página **Mapeamento de códigos de transação**. O mapeamento de códigos de transação é concluído separadamente para cada conta bancária.

## <a name="matching-rules-and-matching-rule-sets"></a>Regras de correspondência e conjuntos de regras de correspondência
As regras de correspondência permitem definir critérios para a reconciliação automática entre as transações bancárias do Finance e as transações do extrato bancário. A configuração das regras de correspondência é realizada na página **Regras de correspondência de reconciliação**. Para obter mais informações, consulte [Configurar regras de correspondência de reconciliação bancária](set-up-bank-reconciliation-matching-rules.md). 

Os conjuntos de regras de correspondência são utilizados para definir um grupo de regras de correspondência que são executadas em sequência durante o processo de reconciliação bancária.  Conjuntos de regras de correspondência são configurados na página **Conjuntos de regras de correspondência de reconciliação**.

## <a name="cash-and-bank-management-parameters"></a>Parâmetros de gerenciamento de caixa e bancos
Existem diversos parâmetros específicos para o processo de reconciliação bancária avançada na página **Parâmetros de gerenciamento de caixa e bancos**.  O **Mostrar valor da linha do extrato em débito/crédito** altera a exibição dos valores na página **Extrato bancário**. Se essa opção estiver selecionada, os valores das transações do extrato bancário serão exibidos em colunas separadas de débito e crédito. Caso não esteja selecionada, os valores de transações do extrato bancário serão exibidos em uma única coluna com os sinais apropriados. 

As opções de validação definidas na página de parâmetros substituirão as seleções definidas nas regras de correspondência. Por exemplo, não é possível combinar documentos manual ou automaticamente após a diferença de datas definida na página de parâmetros. Além disso, se a opção **Validar mapeamento de tipos de transação** estiver selecionada, os tipos de transação deverão ser mapeados entre a transação bancária do Finance e a transação do extrato bancário para que as transações sejam correlacionadas manual ou automaticamente. 

Você também deve configurar as sequências numéricas necessárias na página **Parâmetros de gerenciamento de banco e caixa**.  Na guia **Sequências numéricas**, defina códigos de sequência numérica para as referências de **ID, ID do extrato, ID de reconciliação e Reconciliação bancária** do Download.

## <a name="bank-account-reconciliation-options"></a>Opções de reconciliação de conta bancária
Primeiramente, é necessário habilitar a Reconciliação bancária avançada para a conta bancária. Uma série de opções adicionais estão disponíveis na página **Conta bancária** assim que a funcionalidade Reconciliação bancária avançada é ativada. 

A funcionalidade **Utilize extratos bancários como confirmação de pagamentos eletrônicos** integra a funcionalidade de reconciliação bancária com os status de pagamentos eletrônicos. Quando essa opção estiver habilitada, um documento bancário será criado automaticamente para o status do pagamento eletrônico definido como **Enviado**. Além disso, o status de um pagamento eletrônico será atualizado de **Enviado** para **Recebido** assim que o pagamento for combinado, reconciliado e lançado. 

O campo **Nome da conta bancária em extratos** é o nome usado para a conta bancária em seus extratos bancários eletrônicos. Esse nome é usado ao determinar quais transações importar, para uma conta bancária, de um extrato que pode conter informação de múltiplas contas bancárias. 

A opção de **Reconciliar após a importação** validará automaticamente o extrato bancário, criará uma nova reconciliação bancária e planilha e executará o conjunto de regras de correspondência padrão. Essa funcionalidade automatiza o processo até o ponto em que as transações precisam ser combinadas manualmente. A configuração da conta bancária será padrão durante a importação.




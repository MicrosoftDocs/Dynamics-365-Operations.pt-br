---
title: "Visão geral da reconciliação bancária avançada"
description: "A reconciliação bancária avançado permite que você importe extratos bancários e automaticamente o reconciliar eletrônicos com transações bancárias no Microsoft Dynamics 365 para as operações.  Este artigo irá explicar o processo de configuração da reconciliação."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 98303
ms.assetid: ae071f04-f038-4b17-812d-0a241ed15521
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3b16ef53f9fb57a6663db0be1f7e0a57471db2fb
ms.openlocfilehash: c2fc9e858f61d7d0122393bbf306ba64ac3659b8
ms.lasthandoff: 03/31/2017


---

# <a name="advanced-bank-reconciliation-overview"></a>Visão geral da reconciliação bancária avançada

A reconciliação bancária avançado permite que você importe extratos bancários e automaticamente o reconciliar eletrônicos com transações bancárias no Microsoft Dynamics 365 para as operações.  Este artigo irá explicar o processo de configuração da reconciliação.  

Há um número de unidades que devem ser definidas antes de usar a funcionalidade avançada de reconciliação bancária. Para obter mais informações sobre a importação de demonstrativos a configuração, consulte configurar o processo [] de extrato bancário (setup-advanced-bank-reconciliation-import-process.md).  Os requisitos para a configuração de processo de reconciliação são detalhados abaixo.

## <a name="transaction-codes"></a>Códigos de transação
Os códigos de transações podem ser usados como parte de regras correspondente de reconciliação bancária.  Os códigos de transação ajudarão a corresponder somente os mesmos tipos de transações entre o dynamics 365 para operações e o extrato bancário.  Para fazer esse tipo de correspondência, primeiro será necessário definir os tipos de transação usados para as transações bancárias do 365 para operações, então é mapeado os tipos de códigos de transação do extrato usados pelo banco.  Os tipos de transação para dynamics 365 para transações bancárias operações são definidos ** tipo de transação bancária ** na página.  Isso também é o local onde será definida a conta principal a ser usada para as postagens associadas a esse tipo de transação. 

Depois que sua dynamics 365 para códigos de transação bancária de operações é definida, mapear os nos códigos de transação usados nos extratos bancários eletrônicos.  Esse processo de mapeamento é feito usando ** mapeamento de transação ** a página.  Mapeamento de transação é concluído separadamente para cada conta bancária.

## <a name="matching-rules-and-matching-rule-sets"></a>Regras de correspondência e conjuntos de regras de correspondência
As regras permitem correspondentes que você defina critérios para a reconciliação automática entre o dynamics de 365 transações bancárias de operações e transações do extrato bancário.  A configuração de regras for compatíveis ** regras correspondente de reconciliação ** página cima feito.  Para obter mais informações, consulte as regras configuradas compatíveis [] de reconciliação bancária (setup-bank-reconciliation-matching-rules.md). 

Conjuntos correspondentes da regra são usados para definir um grupo de regras compatíveis executadas na ordem durante o processo de reconciliação bancária.  Conjuntos correspondentes da regra são configurados ** conjuntos de regra de correspondência de reconciliação ** na página.

## <a name="cash-and-bank-management-parameters"></a>Parâmetros de gerenciamento de caixa e bancos
Há vários parâmetros específicos do processo de reconciliação avançado bancárias ** desconto e os parâmetros de gerenciamento de banco ** na página.  ** Linha do demonstrativo mostram o valor de débito/crédito ** alterações a exibição de valores ** ** extrato bancário na página.  Se esta opção estiver selecionada, os valores de transação do extrato bancário serão mostrados em colunas separadas de débito e de crédito.  Se não selecionado, os valores de transação do extrato bancário serão mostrados em uma única coluna de valor com o sinal apropriado. 

Opções de página validação definidos em parâmetros substituem as seleções em regras definidas compatíveis.  Por exemplo, você não pode excluí-la manualmente ou automaticamente documentos de correspondência além da diferença da data definida na página de parâmetros.  Além disso, se a opção ** validar mapeamento do tipo de transação ** estiver marcada, os tipos de transação devem ser mapeados entre o dynamics 365 para a transação bancária de operações e a transação do extrato bancário de transações correspondam manualmente ou automaticamente. 

Você também deve configurar as sequências numéricas necessárias ** desconto e parâmetros de gerenciamento de banco ** na página.  ** ** Sequências numéricas na guia, definir códigos de sequência numérica para o download ** ID, ID da instrução, ID de reconciliação e, reconciliação bancária ** referências.

## <a name="bank-account-reconciliation-options"></a>Opções de reconciliação de conta bancária
É preciso habilitar a reconciliação bancária avançado para a conta bancária.  Várias opções adicionais disponíveis ** ** conta bancária na página depois que a funcionalidade avançada de reconciliação bancária estiver habilitada. 

** Use extratos bancários como confirmação de pagamento eletrônico ** a funcionalidade da funcionalidade de reconciliação bancária com status de pagamento eletrônico.  Quando isso for habilitado, um documento de bancos será criado automaticamente para o status de pagamento estiver definido como eletrônico ** ** enviado.  Além, o status de um pagamento eletrônico será atualizado da enviada ** ** ** recebido ** depois que o pagamento é reconciliado, correspondente, e lançado. 

** Nome da conta bancária em demonstrativos ** o campo é o nome usado para a conta bancária nos extratos bancários eletrônicos.  Este nome é usado para determinar quais transações para importar para uma conta bancária de uma instrução que possa conter informações para diversas contas bancárias. 

** Reconciliar padrão após a importação ** automaticamente validará o extrato bancário, cria uma nova planilha de reconciliação e banco, e executar o conjunto de regras padrão de correspondência.  Esta funcionalidade automatiza o processo o ponto de transações que devem ser manualmente correspondidas.  A configuração na conta bancária padrão para importação.



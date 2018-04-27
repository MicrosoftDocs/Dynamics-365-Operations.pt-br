---
title: "Definições de lançamento"
description: "Este artigo oferece exemplos que mostram como as definições de lançamento são usadas para ônus de ordem de compra e apropriações de orçamento."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: JournalizingDefinition, JournalizingDefinitionTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 15772
ms.assetid: 3864e4da-853f-403d-b906-79631d80b363
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 10015952773ce0ae6ab36912df636919b572704d
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---

# <a name="posting-definition-examples"></a>Exemplos de definições de lançamento

[!INCLUDE [banner](../includes/banner.md)]

Este artigo oferece exemplos que mostram como as definições de lançamento são usadas para ônus de ordem de compra e apropriações de orçamento.

Antes que você leu este tópico, você deve estar familiarizado com as definições de lançamento e as definições de lançamento da transação. Para obter informações, consulte [Definições de lançamento](posting-definitions.md). Os exemplos a seguir podem ser configurados na página **Definições de lançamento**. Cada exemplo contém estas seções:

-   Definição dos critérios de correspondência lançamento –
-   definição de lançamento – entradas gerados
-   transações com as contas, os valores de dimensão, e os valores
-   Entrada do razão geradas na definição de lançamento

Quando ocorre uma correspondência entre as contas e os valores de dimensão no painel de **Fazer a correspondência de critérios** para a definição de lançamento e as contas e os valores de dimensão na transação, as entradas do razão são geradas com base no painel **Entradas geradas** para a definição de lançamento. 
> [!NOTE]
> Para associar uma definição de lançamento a um tipo de transação específico, use a página **Definições de lançamento da transação**. Depois de associar uma definição de lançamento a um tipo de transação e selecionar **Usar definições de lançamento** na página **Parâmetros da contabilidade**, todas as transações do tipo de transação selecionado devem usar as definições de lançamento.

## <a name="example-purchase-order-encumbrances"></a>exemplo: Ônus da ordem de compra
Ao habilitar o processamento de ônus selecionando **Habilitar processo de ônus** na página **Parâmetros da contabilidade** as definições de lançamento devem ser usadas para registrar ônus na contabilidade para todas as contas que devem ser reservadas. Na maioria dos casos, todas as contas de despesas estão reservados no balanço. 

As definições de lançamento para ônus são configuradas para o módulo **Compras** na página **Definições de lançamento**. Em seguida, na área de **Compras** da página **Definições de lançamento de transação**, é possível selecionar o tipo de transação **Ordem de compra** para associar a definição de lançamento às ordens de compra. 

Todas as transações de comprovante para ônus da ordem de compra devem conferir (isto é, débitos devem ser iguais aos créditos), em cada dimensão exclusiva em um comprovante.

### <a name="posting-definition--match-criteria"></a>Definição dos critérios de correspondência lançamento –

| Estrutura da conta       | Fazer a correspondência de número de conta | Prioridade |
|-------------------------|----------------------|----------|
| Estrutura de conta -  | \*                   | 1        |

<em>Um valor em branco no campo **Fazer a correspondência de número de conta</em>* significa que todas as contas correspondentes na estrutura de conta definida fazem parte da regra correspondente.

### <a name="posting-definition--generated-entries"></a>definição de lançamento – entradas gerados

| Estrutura de conta | Número de conta gerado                    | Débito/crédito gerado |
|-------------------|---------------------------------------------|------------------------|
| Saldo           | 300143 - -(Conta de ônus)             | Igual                   |
| Saldo           | 300144 - -(Reserva para a conta de ônus) | Balancear              |

### <a name="transactions-with-the-accounts-dimension-values-and-amounts"></a>transações com as contas, os valores de dimensão, e os valores

As contas e os valores de dimensão são originários de distribuições contábeis que você insere para uma linha da ordem de compra, ou vêm de contas e dimensões que são geradas automaticamente com base nas configurações padrão para fornecedores, itens, categorias e modelos de dimensão.

| Conta + dimensões           | Débito  | Crédito | Comentário |
|--------------------------------|--------|--------|---------|
| 606400-OU\_1-OU\_3566-Training | 250,00 |        |         |

### <a name="ledger-entries-generated-from-the-posting-definition"></a>Entrada do razão geradas na definição de lançamento

As entradas do razão geradas são criadas para registrar os ônus.

| Conta + dimensões           | Débito  | Crédito | Comentário |
|--------------------------------|--------|--------|---------|
| 300143-OU\_1-OU\_3566-Training | 250,00 |        |         |
| 300144-OU\_1-OU\_3566-Training |        | 250,00 |         |

Neste exemplo, qualquer conta que está parte da estrutura de conta - L&P coincidir com os critérios de definição de lançamento. Portanto, quando 606500-OU\_1-OU\_3566-Training é avaliado, as entradas geradas são criadas para as contas que são definidas no painel de **Entradas geradas** para a definição de lançamento.

## <a name="example-budget-appropriations"></a>habilitar apropriações do orçamento
Quando você habilita a apropriação do orçamento selecionando **Habilitar apropriação do orçamento** na página **Parâmetros da contabilidade**, as definições de lançamento devem ser usadas para registrar entradas de registro de orçamento na contabilidade. Quando uma configuração de controle de orçamento estiver ativa e habilitada, as definições de lançamento e as definições de lançamento da transação poderão ser usadas para oferecer suporte à gravação de entradas de apropriações, revisões, transferências, projetos, ativos fixos e previsão de suprimento e demanda para a contabilidade. 

Para configurar uma definição de lançamento para entradas de registro de orçamento que possuam **Orçamento original** e que tenha as apropriações ativadas, selecione o módulo **Orçamento** na página **Definições de lançamento**. Em seguida, na área **Orçamento** da página **Definições de lançamento de transação**, você pode usar os códigos de orçamento para associar a definição de lançamento às entradas de registro de orçamento que têm um tipo de orçamento de **Orçamento original**. 

Quando apropriações de orçamento e as definições de lançamento são habilitadas, as entradas de registro de orçamento são registradas para controle de orçamento e na contabilidade.

### <a name="posting-definition--match-criteria"></a>Definição dos critérios de correspondência lançamento –

| Estrutura da conta       | Fazer a correspondência de número de conta | Prioridade |
|-------------------------|----------------------|----------|
| Estrutura de conta -  | \*                   | 1        |

<em>Um valor em branco no campo **Fazer a correspondência de número de conta</em>* significa que todas as contas correspondentes na estrutura de conta definida fazem parte da regra correspondente.

### <a name="posting-definition--generated-entries"></a>definição de lançamento – entradas gerados

| Estrutura de conta | Número de conta gerado              | Débito/crédito gerado |
|-------------------|---------------------------------------|------------------------|
| Estrutura de conta | 300145 - -(Conta de receita prevista) | Igual                   |
| Estrutura de conta | 300146 - -(Conta de apropriação)     | Balancear              |

### <a name="transactions-with-the-accounts-dimension-values-and-amounts"></a>transações com as contas, os valores de dimensão, e os valores

Você insere as contas, valores de dimensão e valores para a entrada da conta de orçamento na página **Entrada de registro de orçamento**.

| Conta + dimensões           | Débito | Crédito | Comentário |
|--------------------------------|-------|--------|---------|
| 606400-OU\_1-OU\_3566-Training |       | 250,00 |         |

### <a name="ledger-entries-generated-from-the-posting-definition"></a>Entrada do razão geradas na definição de lançamento

As entradas do razão geradas são criadas para registrar o orçamento original em cada dimensão.

| Conta + dimensões           | Débito  | Crédito | Comentário |
|--------------------------------|--------|--------|---------|
| 300145-OU\_1-OU\_3566-Training |        | 250,00 |         |
| 300146-OU\_1-OU\_3566-Training | 250,00 |        |         |

Neste exemplo, qualquer conta que está parte da estrutura de conta - L&P coincidir com os critérios de definição de lançamento. Portanto, quando 606400-OU\_1-OU\_3566-Training é avaliado, as entradas do razão geradas são criadas.







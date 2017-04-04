---
title: "Liquidação automática e priorização"
description: "Este artigo descreve como as transações serão liquidadas se você selecionar a Liquidação automática na página de parâmetro de Contas a receber. Também explica como a liquidação automática pode ser usada em combinação com a prioridade de pagamento."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CustOpenTrans, CustParameters, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14531
ms.assetid: e7837cf6-ec69-44b4-8d47-eba38d5c7b1f
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: a751973b49febd6925267d00fb1d2c72114f86b0
ms.lasthandoff: 03/31/2017


---

# <a name="automatic-settlement-and-prioritization"></a>Liquidação automática e priorização

Este artigo descreve como as transações serão liquidadas se você selecionar a Liquidação automática na página de parâmetro de Contas a receber. Também explica como a liquidação automática pode ser usada em combinação com a prioridade de pagamento.

Você tem duas opções quando liquida pagamentos com faturas e outras transações. Você pode selecionar manualmente as transações para liquidar, ou Microsoft Dynamics 365 para operações pode selecionar as transações automaticamente usando a funcionalidade liquidação automática. Você também pode personalizar como as liquidações automáticas são processadas usando a opção **Priorizar liquidação**. Todas essas opções são parte parâmetros de pagamento definidas ** parâmetros de contas a receber ** na página. O modo como as transações são liquidadas automaticamente pode ser diferente, dependendo do método usado para a liquidação automática. Os seguintes métodos estão disponíveis:

-   Prioridade de liquidação definida pelo usuário
-   Liquidação automática padrão

As seções a seguir descrevem como as transações são liquidadas para cada método.

## <a name="example-transactions"></a>Transações de exemplo
Os exemplos de liquidações posteriormente neste artigo se baseiam nas transações a seguir. Todas as transações são para o cliente 2050.

| Transação   | Data        | Valor | Condições de desconto à vista | Data do desconto à vista | Comentários                                                                                                                                                                                      |
|---------------|-------------|--------|---------------------|--------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Fatura 1     | 15 de agosto   | 100,00 | 2%14, Líquido 30        | 29 de agosto          |                                                                                                                                                                                               |
| Fatura 2     | 1 de setembro | 250,00 | 2%14, Líquido 30        | 15 de setembro       |                                                                                                                                                                                               |
| Fatura 3     | 15 de outubro  | 500,00 | 2% 14/Líquido 30        | 29 de outubro         |                                                                                                                                                                                               |
| Nota de juros | 15 de outubro  | 7:00   |                     |                    | A nota de juros para a nota fiscal é 1 e a fatura. 2. O valor é calculado como juros 2 dos valores que são 30 ou mais dias atrasado. Por exemplo, 0,02 × (100,00 + 250,00) = 7,00. |

## <a name="userdefined-settlement-priority"></a>Prioridade definida pelo usuário de pagamento
Se você definir **Usar prioridade para liquidações automáticas** como **Sim** na página **Parâmetros de contas a receber**, a prioridade de liquidação que você definir na página **Prioridade de liquidação** é usada quando as transações forem selecionadas para liquidação automática. Para este exemplo, a seguinte prioridade de liquidação é definida:

1.  Tipo de transação
    -   Taxas de pagamento
    -   Cartas de cobrança
    -   Notas de juros
    -   Faturas

2.  Data da transação, ordem crescente
3.  Comprovante

Se você lançar um pagamento de 700,00 em 25 de outubro, o pagamento é liquidado para transações na seguinte ordem.

| Comprovante       | Data       | Fatura | Valor na moeda da transação | Valor para liquidar | Saldo | Moeda |
|---------------|------------|---------|--------------------------------|------------------|---------|----------|
| Nota de juros | 15/10/2015 |         | 7:00                           | 7:00             | 0,00    | USD      |
| Fatura 1     | 15/08/2015  | 10001   | 100,00                         | 100,00           | 0,00    | USD      |
| Fatura 2     | 01/09/2015   | 10002   | 250,00                         | 250,00           | 0,00    | USD      |
| Fatura 3     | 15/10/2015 |         | 500,00                         | 343,00           | 157,00  | USD      |

## <a name="default-automatic-settlement"></a>Liquidação automática padrão
Se não houver nenhuma prioridade de liquidação definida pelo usuário, as transações serão automaticamente selecionadas para liquidação com base na data de vencimento. As transações liquidadas devem ter a mesma moeda do que a transação com que serão liquidadas. Se você lançar um pagamento de 700,00 em 25 de outubro, as transações a seguir serão selecionadas para liquidação.

| Comprovante       | Data       | Fatura | Valor na moeda da transação | Valor para liquidar | Saldo | Moeda |
|---------------|------------|---------|--------------------------------|------------------|---------|----------|
| Fatura 1     | 15/08/2015  | 10001   | 100,00                         | 100,00           | 0,00    | USD      |
| Fatura 2     | 01/09/2015   | 10002   | 250,00                         | 250,00           | 0,00    | USD      |
| Fatura 3     | 15/10/2015 |         | 500,00                         | 350,00           | 150.00  | USD      |
| Nota de juros | 15/10/2015 |         | 7:00                           | 0,00             | 0,00    | USD      |





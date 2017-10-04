---
title: "Liquidação e priorização automáticas"
description: "Este artigo descreve como as transações serão liquidadas se você selecionar a Liquidação automática na página de parâmetro de Contas a receber. Também explica como a liquidação automática pode ser usada em combinação com a prioridade de pagamento."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustOpenTrans, CustParameters, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14531
ms.assetid: e7837cf6-ec69-44b4-8d47-eba38d5c7b1f
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 298ac47e2253f8add1aa3938dda15afe186afbeb
ms.openlocfilehash: 3e2ca11eef4246d5abfd77351325ac2b4440b446
ms.contentlocale: pt-br
ms.lasthandoff: 06/20/2017

---

# <a name="automatic-settlement-and-prioritization"></a>Liquidação e priorização automáticas

[!include[banner](../includes/banner.md)]


Este artigo descreve como as transações serão liquidadas se você selecionar a Liquidação automática na página de parâmetro de Contas a receber. Também explica como a liquidação automática pode ser usada em combinação com a prioridade de pagamento.

Você tem duas opções quando liquida pagamentos com faturas e outras transações. Você pode selecionar manualmente as transações a serem liquidadas ou o Microsoft Dynamics 365 for Finance and Operations pode selecionar as transações automaticamente usando a funcionalidade de liquidação automática. Você também pode personalizar como as liquidações automáticas são processadas usando a opção **Priorizar liquidação**. Todas essas opções são parte dos parâmetros de liquidação que são definidos na página **Parâmetros de contas a receber**. O modo como as transações são liquidadas automaticamente pode ser diferente, dependendo do método usado para a liquidação automática. Os seguintes métodos estão disponíveis:

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
| Nota de juros | 15 de outubro  | 7:00   |                     |                    | Esta nota de juros destina-se à fatura 1 e à fatura 2. O valor é calculado como 2% de juros em valores devidos com 30 ou mais dias de atraso. Por exemplo, 0,02 × (100,00 + 250,00) = 7,00. |

## <a name="userdefined-settlement-priority"></a>Prioridade de liquidação definida pelo usuário
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






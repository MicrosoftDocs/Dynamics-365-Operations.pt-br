---
title: Relatórios financeiros de balancete
description: Este artigo descreve os relatórios padrão para saldos de teste. Ele também descreve os blocos de construção que estão associados a esses relatórios e como você pode modificar os relatórios para atender às suas necessidades de negócios.
author: jinniew
ms.date: 05/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: kfend
ms.custom: 12314
ms.assetid: 3b77d6f3-fd07-41a7-9ddb-1b22d1ae33fc
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b26d2ec261720499fc309a5fb850de2cb796bd8b
ms.sourcegitcommit: d27fef61593c6d1e9e26d5c9fad21411bc52fabc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/23/2022
ms.locfileid: "9802598"
---
# <a name="trial-balance-financial-reports"></a>Relatórios financeiros de balancete

[!include [banner](../includes/banner.md)]

Este artigo descreve os relatórios padrão para saldos de teste. Ele também descreve os blocos de construção que estão associados a esses relatórios e como você pode modificar os relatórios para atender às suas necessidades de negócios. 

## <a name="default-trial-balance-reports"></a>Relatórios do balancete padrão

Três relatórios do balancete estão disponíveis no relatório financeiro.

| Relatório padrão                                 | O que ele faz                                                                            |
|------------------------------------------------|--------------------------------------------------------------------------------------|
| Balancete Detalhado - Padrão               | Fornece informações de saldo para todas as contas e inclui saldos de débito e crédito e suas redes com a data de transação, comprovante e descrição do diário.                  |
| Resumo do Balancete – Padrão                | Fornece informações de saldo de todas as contas e inclui saldos de abertura e de fechamento e os saldos de débito e de crédito, com a diferença líquida.                                        |
| Resumo do Balancete Ano a Ano – Padrão | Fornece informações sobre saldo para todas as contas e inclui saldos de abertura e de fechamento e saldos de débito e crédito com a diferença líquida para o ano atual e o ano passado. |

## <a name="building-blocks"></a>Bloco de construção
Os relatórios financeiros de balancete usam os seguintes blocos de construção.

| Relatório padrão                                 | Definição de linha          | Definição de coluna                              |
|------------------------------------------------|-------------------------|------------------------------------------------|
| Balancete Detalhado - Padrão               | Balancete - Padrão | Balancete Detalhado - Padrão               |
| Resumo do Balancete – Padrão                | Balancete - Padrão | Balancete do resumo - Padrão                |
| Resumo do Balancete Ano a Ano – Padrão | Balancete - Padrão | Resumo do balancete ano a ano - Padrão |

> [!NOTE] 
> Ao executar o relatório **Balancete** nos relatórios financeiros, marque as caixas de seleção para **Exibir linhas sem valores** e **Exibe relatórios sem linhas ativas** nas guias **Configurações**.

### <a name="row-definition"></a>Definição de linha

A definição de linha, balancete - padrão, contém uma única linha que puxa todas as contas principais. Consequentemente, qualquer pessoa pode gerar o relatório sem fazer modificações. Ao visualizar o relatório, você navega na linha única para ver os detalhes sobre cada conta. É possível modificar a definição da linha para que inclua mais detalhes. Para modificar a definição da linha Balancete – Padrão para que inclua linhas para todas as contas, siga as etapas.

1.  Clique em **Editar** e, depois, em **Inserir linhas de dimensões**. O comando **Inserir linhas de dimensões** permite escolher as dimensões desejadas em sua definição de linha. Para esta definição da linha, você utilizará **Conta principal**.
2.  Verifique se **Conta principal** contém todos os E comerciais (&) e clique em **OK**.

Agora, a definição da linha contém todas as contas principais para sua entidade legal padrão.

### <a name="column-definition"></a>Definição de coluna

Cada relatório do balancete usa uma definição da coluna diferente. Essas definições da coluna contêm diferentes tipos de colunas para fornecer níveis diferentes de detalhes e dados financeiros.

-   **Balancete detalhado – Tipos de coluna padrão:**
    -   **DESC** – A descrição da definição da linha
    -   **ACCT** – Códigos de conta
    -   **ATTR (3)** – Atributos:
        -   Data da Transação
        -   Comprovante
        -   Descrição do diário
    -   **DF** – Dados financeiros que contém somente débitos
    -   **DF** – Dados financeiros que contenham somente créditos
    -   **CALC** – A diferença líquida
-   **Resumo do balancete – Tipos de coluna padrão:**
    -   **ACCT** – Códigos de conta
    -   **DESC** – A descrição da definição da linha
    -   **ATTR** – Atributo:
        -   Comprovante
    -   **DF** – Dados financeiros do saldo
    -   **DF** – Dados financeiros que contêm somente débitos
    -   **DF** – Dados financeiros que contenham somente créditos
    -   **CALC** – Diferença líquida
    -   **CALC** – Saldo do fechamento
-   **Resumo do balancete ano a ano – Padrão:**
    -   **ACCT** – Códigos de conta
    -   **DESC** – A descrição da definição da linha
    -   **ATTR** – Atributo
        -   Comprovante
    -   **DF** – Dados financeiros do saldo inicial para o ano atual
    -   **DF** – Dados financeiros que contém somente os débitos para o ano atual
    -   **DF** – Dados financeiros que contêm somente os créditos para o ano atual
    -   **CALC** – Diferença líquida
    -   **CALC** – Saldo do fechamento
    -   **DF** – Dados financeiros que contêm somente os débitos para o ano anterior
    -   **DF** – Dados financeiros que contêm somente os créditos do ano anterior

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de relatórios financeiros](financial-reporting-getting-started.md)

[Exibir relatórios financeiros](view-financial-reports.md)

[Blog de Relatório Financeiro do Dynamics](https://blogs.msdn.com/b/dynamics_financial_reporting/)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]

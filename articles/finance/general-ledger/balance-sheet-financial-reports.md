---
title: Relatórios financeiros de balanço
description: Este artigo descreve os relatórios padrão para balanços. Também mostra os blocos de construção associados a esses relatórios.
author: jinniew
ms.date: 10/10/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinanicalReports
audience: Application User
ms.reviewer: twheeloc
ms.custom: 12274
ms.assetid: 52f78229-f531-4d16-b337-e2628994acb6
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4aad297f401143388d682da175a6b14727a8f2f0
ms.sourcegitcommit: c5f2cba3c2b0758e536eeaaa40506659a53085e1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2022
ms.locfileid: "9643814"
---
# <a name="balance-sheet-financial-reports"></a>Relatórios financeiros de balanço

[!include [banner](../includes/banner.md)]

Este artigo descreve os relatórios padrão para balanços. Também mostra os blocos de construção associados a esses relatórios. 

## <a name="default-balance-sheet-reports"></a>Relatórios do balanço padrão

Há dois relatórios do balanço padrão. Em um relatório, as seções são empilhadas. No outro relatório, as seções estão lado a lado.

| Relatório padrão                       | O que ele faz                                                                                                                           |
|--------------------------------------|--------------------------------------------------------------------------------------|
| Balanço - Padrão              | Fornece uma exibição do cargo financeiro da organização para o ano.                    |
| Balanço e Demonstrativo de Renda Lado a Lado – Padrão | Fornece uma exibição lado a lado do cargo financeiro da organização para o ano. |

## <a name="building-blocks"></a>Blocos de construção
Os relatórios financeiros de balanço usam os seguintes blocos de construção.

| Relatório padrão                       | Definição de linha                       | Definição de coluna             |
|--------------------------------------|--------------------------------------|-------------------------------|
| Balanço - Padrão              | Balanço - Padrão              | Desde o início do ano e Variação - Padrão    |
| Balanço e Demonstrativo de Renda Lado a Lado – Padrão | Balanço e Demonstrativo de Renda Lado a Lado – Padrão | Coluna Desde o início do ano - Padrão |

### <a name="row-definition"></a>Definição de linha

As definições de linha para os relatórios do balanço contêm as seções para cada parte de um balanço tradicional. O relatório inclui lado a lado inclui uma quebra de coluna, de modo que o e o capital próprio do proprietário são exibidos aos ativos. A dimensão da Categoria de conta principal é usada para criar as definições da linha. Consequentemente, qualquer pessoa pode gerar os relatórios sem fazer modificações.

### <a name="column-definition"></a>Definição de coluna

As definições da coluna contêm diferentes tipos de colunas para fornecer níveis diferentes de detalhes e dados financeiros.

-   **Desde o início do ano e variação – Tipos da coluna padrão:**
    -   **DESC** – A descrição da definição da linha
    -   **FD** – Dados financeiros acumulados do ano para o ano atual
    -   **FD** – Dados financeiros acumulados do último ano
    -   **CALC** – A variação ao subtrair o último ano deste ano

<!-- -->

-   **Coluna desde o início do ano – Padrão:**
    -   **DESC** – A descrição da definição da linha
    -   **FD** – Dados financeiros acumulados do ano para o ano atual



## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de relatórios financeiros](financial-reporting-getting-started.md)

[Exibir relatórios financeiros](view-financial-reports.md)

[Blog de Relatório Financeiro do Dynamics](https://blogs.msdn.com/b/dynamics_financial_reporting/)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]

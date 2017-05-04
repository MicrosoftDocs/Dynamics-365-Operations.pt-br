---
title: "Relatórios financeiros de balanço"
description: "Este artigo descreve os relatórios padrão para balanços. Também mostra os blocos de construção associados a esses relatórios."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 12274
ms.assetid: 52f78229-f531-4d16-b337-e2628994acb6
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 664d32c2bfecb50e24fd48a66ab5b34cef6c09a3
ms.lasthandoff: 03/31/2017


---

# <a name="balance-sheet-financial-reports"></a>Relatórios financeiros de balanço

[!include[banner](../includes/banner.md)]


Este artigo descreve os relatórios padrão para balanços. Também mostra os blocos de construção associados a esses relatórios. 

<a name="default-balance-sheet-reports"></a>Relatórios do balanço padrão
-----------------------------

Há dois relatórios do balanço padrão. Em um relatório, as seções são empilhadas. No outro relatório, as seções estão lado a lado.

| Relatório padrão                       | O que ele faz                                                                                                                           |
|--------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| Balanço - Padrão              | Fornece uma exibição do cargo financeiro da organização para o ano.                                                                 |
| Balanço Lado a Lado – Padrão | Fornece uma exibição do cargo financeiro da organização para o ano. Os ativos e passivos e o capital próprio do acionista estão lado a lado. |

## <a name="building-blocks"></a>Bloco de construção
Os relatórios financeiros de balanço usam os seguintes blocos de construção.

| Relatório padrão                       | Definição de linha                       | Definição de coluna             |
|--------------------------------------|--------------------------------------|-------------------------------|
| Balanço - Padrão              | Balanço - Padrão              | Desde o início do ano e Variação - Padrão    |
| Balanço Lado a Lado – Padrão | Balanço Lado a Lado – Padrão | Coluna Desde o início do ano - Padrão |

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

 

<a name="see-also"></a>Consulte também
--------

[Relatórios financeiros](financial-reporting-getting-started.md)

[Exibir relatórios financeiros](view-financial-reports.md)

[Blog de Relatório Financeiro do Dynamics](http://blogs.msdn.com/b/dynamics_financial_reporting/)





---
title: Relatórios financeiros de balanço
description: Este artigo descreve os relatórios padrão para balanços. Também mostra os blocos de construção associados a esses relatórios.
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FinanicalReports
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 12274
ms.assetid: 52f78229-f531-4d16-b337-e2628994acb6
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e96552447182f3692a19d4cfd962afbcb28e5508
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440420"
---
# <a name="balance-sheet-financial-reports"></a>Relatórios financeiros de balanço

[!include [banner](../includes/banner.md)]

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



<a name="additional-resources"></a>Recursos adicionais
--------

[Visão geral de relatórios financeiros](financial-reporting-getting-started.md)

[Exibir relatórios financeiros](view-financial-reports.md)

[Blog de Relatório Financeiro do Dynamics](https://blogs.msdn.com/b/dynamics_financial_reporting/)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
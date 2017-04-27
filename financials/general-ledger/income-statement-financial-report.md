---
title: "Relatório financeiro do demonstrativo de renda"
description: "Este artigo descreve o relatório padrão para declarações de imposto. Também mostra os blocos de construção associados a este relatório."
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
ms.custom: 12294
ms.assetid: 30820be0-d943-4f8b-8c25-6414ec393b3d
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 8dd289c1943afb55373ba682afcc3cd107cb67a7
ms.lasthandoff: 03/31/2017


---

# <a name="income-statement-financial-report"></a>Relatório financeiro do demonstrativo de renda

[!include[banner](../includes/banner.md)]


Este artigo descreve o relatório padrão para declarações de imposto. Também mostra os blocos de construção associados a este relatório. 

<a name="default-income-statement-report"></a>Relatório do demonstrativo de renda padrão
-------------------------------

| Relatório padrão             | O que ele faz                                                                                              |
|----------------------------|-----------------------------------------------------------------------------------------------------------|
| Demonstrativo de renda – Padrão | Fornece uma visualização da lucratividade da organização para o período atual e para o acumulado do ano. |

## <a name="building-blocks"></a>Bloco de construção
O relatório financeiro do demonstrativo de renda usa os seguintes blocos de construção.

| Relatório padrão             | Definição de linha                     | Definição de coluna          |
|----------------------------|------------------------------------|----------------------------|
| Demonstrativo de renda – Padrão | Resumo do demonstrativo de renda - Padrão | Periódico e acumulado do ano - Padrão |

### <a name="row-definition"></a>Definição de linha

A definição da linha Resumo do demonstrativo de renda - Padrão contém uma seção para cada parte de um demonstrativo de renda tradicional. A dimensão Categoria de conta principal é usada para criar esta definição da linha. Consequentemente, qualquer pessoa pode gerar o relatório sem fazer modificações.

### <a name="column-definition"></a>Definição da coluna

As definições da coluna contêm diferentes tipos de colunas para fornecer níveis diferentes de detalhes e dados financeiros.

-   **Periódico e acumulado do ano - Tipos de coluna padrão:**
    -   **DESC** – A descrição da definição da linha
    -   **DF** – Dados financeiros para o período atual
    -   **DF** – Dados financeiros acumulados do ano

 

<a name="see-also"></a>Consulte também
--------

[Relatórios financeiros](financial-reporting-getting-started.md)

[Exibir relatórios financeiros](view-financial-reports.md)

[Blog de Relatório Financeiro do Dynamics](http://blogs.msdn.com/b/dynamics_financial_reporting/)





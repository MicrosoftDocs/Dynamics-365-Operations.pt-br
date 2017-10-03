---
title: Planejar seu plano de contas
description: "Este artigo fornece informações as quais o ajudarão a planejar o gráfico para sua organização."
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DimensionConfigureAccountStructure, LedgerChartOfAccounts
audience: Application User
ms.reviewer: robinr
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14051
ms.assetid: 10edb129-33f0-4cf9-b2a7-4b7ffa09b229
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: c4f5dae90c5fcaaa52a7087d7c20b2de343b7da0
ms.openlocfilehash: 424ea5ce12d51d384c86878b7d2199bcd52c40f8
ms.contentlocale: pt-br
ms.lasthandoff: 08/01/2017

---

# <a name="plan-your-chart-of-accounts"></a>Planejar seu plano de contas

[!include[banner](../includes/banner.md)]


Este artigo fornece informações as quais o ajudarão a planejar o gráfico para sua organização.

Para rastrear e manter as informações financeiras em uma organização, você pode configurar um plano de contas. Um plano de contas é um conjunto de contas que definem uma estrutura financeira. Para rastrear outras transações nessas contas, você pode adicionar segmentos, que são conhecidos como dimensões financeiras. Por exemplo, uma conta de despesas pode incluir as dimensões financeiras denominadas Departamento, Centro de custos e Finalidade. As regras definidas pelo usuário, conhecidas como estruturas de conta e regras avançadas, determinam como essas dimensões financeiras são anexadas às contas principais e outras dimensões financeiras, e também como as transações podem ser inseridas. 

O plano de contas é uma lista estruturada das contas da contabilidade de uma entidade legal. A lista é utilizada para preparar relatórios financeiros para autoridades e proprietários. As contas são agrupadas em tipos de contas e então agregadas em categorias maiores. No nível mais amplo, as contas são agrupadas como receitas e custos (contas operacionais), ativos e passivos (contas de saldo). 

Um plano de contas pode ser compartilhado e usado por todas as entidades legais em uma organização. O plano de contas usado por uma entidade legal é definido na página **Razão**. 

Veja alguns dos fatores que você deve considerar ao planejar a estrutura do plano de contas para sua organização:

-   Os requisitos de relatório do país/região no qual sua organização está sediada
-   Os requisitos de relatórios da entidade legal
-   O grau de especificação é necessário para as duas organizações externas e a sua organização

Crie o plano de contas na página **Plano de contas**. As contas principais podem ser criadas na página **Plano de contas** ou na página **Contas principais**. Sus contas principais não devem usar caracteres especiais utilizados como delimitadores de plano de contas. Se você tiver um caractere especial igual ao delimitador do seu plano de contas, talvez experimente instabilidade ou precise sempre usar pesquisas ou o submenu ao inserir combinações de contas e de dimensões. Para saber mais, consulte [Criar uma conta principal](tasks/create-account-structures.md).


É recomendável vincular as contas principais a categorias de conta principal, de forma que você possa aproveitar as vantagens dos relatórios financeiros padrão sem ter que fazer modificações. Consequentemente, você poderá projetar e manter relatórios de forma mais rápida e fácil. 

Use a página **Configurar estruturas de conta** para criar estruturas de conta. As estruturas de conta definem as combinações válidas. As combinações, juntamente com as contas principais, formam um plano de contas.  Para saber mais, consulte [Criar estruturas de conta](tasks/create-main-account.md).

**Substituições de entidade legal** 

Nem todas as contas principais são válidas para todas as entidades legais e algumas podem ser relevantes apenas por um período específico. Neste cenário, a seção Substituições da entidade legal pode ser usada para identificar para quais empresas a conta principal deve ser suspensa, quem é o proprietário e há quanto tempo a dimensão está ativa. As substituições no nível compartilhado não podem ser mais restritivas do que as substituições no nível da entidade legal.

Para saber mais, consulte os seguintes tópicos: [Dimensões financeiras](financial-dimensions.md)
[Criar e atribuir estruturas de regra avançadas](tasks/create-assign-advanced-rule-structures.md)





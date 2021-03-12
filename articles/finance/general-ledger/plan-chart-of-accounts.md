---
title: Planejar seu plano de contas
description: Este tópico fornece informações que o ajudarão a planejar o plano de contas para sua organização.
author: aprilolson
manager: AnnBe
ms.date: 04/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure, LedgerChartOfAccounts
audience: Application User
ms.reviewer: roschlom
ms.custom: 14051
ms.assetid: 10edb129-33f0-4cf9-b2a7-4b7ffa09b229
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6e568fca70ea2048d881681ff7ab8ebc6fad6450
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990355"
---
# <a name="plan-your-chart-of-accounts"></a>Planejar seu plano de contas

[!include [banner](../includes/banner.md)]

Este tópico fornece informações que o ajudarão a planejar o plano de contas para sua organização.

Para rastrear e manter as informações financeiras em uma organização, você pode configurar um plano de contas. Um plano de contas é um conjunto de contas que definem uma estrutura financeira. Para rastrear outras transações nessas contas, você pode adicionar segmentos. Esses segmentos são conhecidos como dimensões financeiras. Por exemplo, uma conta de despesas pode incluir as dimensões financeiras denominadas Departamento, Centro de custos e Finalidade. As regras definidas pelo usuário determinam como as dimensões financeiras são anexadas às contas principais e às outras dimensões financeiras, e também como as transações podem ser inseridas. Essas regras definidas pelo usuário são conhecidas como estruturas de conta e regras avançadas.

O plano de contas é uma lista estruturada das contas da contabilidade de uma entidade legal. A lista é utilizada para preparar relatórios financeiros para autoridades e proprietários. As contas primeiro são agrupadas em tipos de contas e depois são agregadas em categorias maiores. No nível mais amplo, as contas são agrupadas como receitas e custos (contas operacionais), ativos e passivos (contas de saldo).

Um plano de contas pode ser compartilhado e usado por todas as entidades legais em uma organização. O plano de contas usado por uma entidade legal é definido na página **Razão**.

Veja alguns dos fatores que você deve considerar ao planejar a estrutura do plano de contas para sua organização:

- Os requisitos de relatório do país ou da região em que sua organização está sediada
- Os requisitos de relatórios da entidade legal
- O grau de especificação é necessário para as duas organizações externas e a sua organização

Você cria o plano de contas na página **Plano de contas**. Você pode criar as contas principais na página **Plano de contas** ou na página **Contas principais**. Suas contas principais não devem usar caracteres especiais que são utilizados como delimitadores do plano de contas. Caso contrário, você pode se deparar com instabilidade, ou pode ser necessário sempre usar pesquisas ou a caixa de diálogo, ao inserir combinações de contas e dimensões. Para saber mais, consulte [Criar uma conta principal](tasks/create-main-account.md).

> [!NOTE]
> No Dynamics 365 for Finance and Operations versão 8.0 (Abril 2018), você pode modificar o delimitador de plano de contas da página **Parâmetros de contabilidade**.

É recomendável vincular as contas principais a categorias de conta principal, de forma que você possa aproveitar as vantagens dos relatórios financeiros padrão sem ter que fazer modificações. Consequentemente, você poderá projetar e manter relatórios de forma mais rápida e fácil.

Você criar estruturas de conta na página **Configurar estruturas de conta**. As estruturas de conta definem as combinações válidas. Essas combinações, juntamente com as contas principais, formam um plano de contas. Para saber mais, consulte [Criar estruturas de conta](tasks/create-account-structures.md).

**Substituições de entidade legal**

Nem todas as contas principais são válidas para todas as entidades legais, e algumas podem ser relevantes apenas por um período específico. Neste cenário, você pode usar a seção **Substituições da entidade legal** para identificar as empresas para a qual a conta principal deve ser suspensa, o proprietário, e o período no qual a dimensão está ativa. As substituições no nível compartilhado não podem ser mais restritivas do que as substituições no nível da entidade legal.

Para obter mais informações, consulte os seguintes tópicos:

- [Dimensões financeiras](financial-dimensions.md)
- [Criar e atribuir estruturas de regras avançadas](tasks/create-assign-advanced-rule-structures.md)

---
title: Armazenamento de relatório de classificação por vencimento do estoque
description: Este tópico descreve a funcionalidade que permite executar um Relatório de classificação por vencimento de estoque e disponibiliza a saída como um formulário e um gráfico.
author: AndersGirke
manager: tfehr
ms.date: 11/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2019-01-10
ms.dyn365.ops.version: ''
ms.openlocfilehash: 1e68833cc2b4430f66419a67b1cba5f6c8c209f4
ms.sourcegitcommit: 68092ed283bfbb7b6f611cce1b62c791f9b6a208
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2020
ms.locfileid: "3323614"
---
# <a name="inventory-aging-report-storage"></a>Armazenamento de relatório de classificação por vencimento do estoque

[!include [banner](../includes/banner.md)]

No Microsoft Dynamics 365 Supply Chain Management, você pode executar um relatório **Armazenamento de relatório de classificação por vencimento do estoque** e disponibilizar a saída como um formulário e um gráfico. No formulário, as colunas e os saldos agregação são ajustados dinamicamente, dependendo do layout configurado. O gráfico oferece uma visão geral visual que dá suporte à filtragem e permite que você faça uma busca detalhada. Adicionalmente, uma entidade de dados chamada **Relatório de classificação por vencimento de estoque** permite exportar os resultados de uma execução de um relatório **Armazenamento de relatório de classificação por vencimento do estoque** para um formato como um arquivo do Microsoft Excel ou um arquivo PDF.

Esse método de execução de um relatório **Armazenamento de relatório de classificação por vencimento do estoque** é útil quando as saídas contêm várias linhas. Por exemplo, a saída conterá várias linhas se você tiver 50.000 itens e 300 repositórios criados, como depósitos, e solicitar a classificação por vencimento de estoque por item, local e depósito.

## <a name="enable-the-inventory-value-storage-report-feature"></a>Habilitar o recurso de relatório de armazenamento de valor de estoque

Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema. Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo, se necessário. Aqui o recurso está listado como:

- **Módulo** - Gerenciamento de custos
- **Nome do recurso** - Armazenamento de relatório de classificação por vencimento do estoque

## <a name="run-an-inventory-aging-report-storage"></a>Executar um armazenamento de classificação por vencimento de estoque

1. Vá para **Gerenciamento de custos \> Consultas e relatórios \> Armazenamento do relatório de classificação por vencimento de estoque**.
1. Selecione **Novo**.
1. No campo **Identificador do Processo – Nome**, insira um nome exclusivo para o relatório.
1. Selecione o relatório **Identificação – ID** e filtre-o como necessário.

    A execução do relatório sempre é feita em um trabalho em lotes.

1. Depois que o trabalho em lotes for concluído, as saídas serão mostradas na página **Armazenamento do relatório de classificação por vencimento de estoque**.
1. Para exibir a saída como um formulário com um layout tradicional de grade, selecione **Exibir detalhes**. Para exibir a saída como um gráfico agregado, selecione **Exibir gráfico**.

    > [!NOTE]
    > O formulário não incluirá os subtotais definidos no layout de relatório.

A entidade de dados **Relatório de classificação por vencimento de estoque** permite exportar as saídas de um relatório **Armazenamento de relatório de classificação por vencimento do estoque** por meio da aplicação de um filtro para o campo **Identificador do processo – Nome** a qualquer formato que dê suporte ao Gerenciamento de dados.

---
title: Relatório de classificação por vencimento do estoque
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
ms.openlocfilehash: 790c8fe3a52bce652227f1cef97eff6496476100
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3201608"
---
# <a name="inventory-aging-report"></a>Relatório de classificação por vencimento do estoque


[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

No Microsoft Dynamics 365 Supply Chain Management, você pode executar um relatório **Classificação por vencimento de estoque** e disponibilizar a saída como um formulário e um gráfico. No formulário, as colunas e os saldos agregação são ajustados dinamicamente, dependendo do layout configurado. O gráfico oferece uma visão geral visual que dá suporte à filtragem e permite que você faça uma busca detalhada. Adicionalmente, uma entidade de dados chamada **Relatório de classificação por vencimento de estoque** permite exportar os resultados de uma execução do relatório **Classificação por vencimento de estoque** para um formato como um arquivo do Microsoft Excel ou um arquivo PDF.

Esse método de execução de um relatório **Classificação por vencimento de estoque** é útil quando as saídas contêm várias linhas. Por exemplo, a saída conterá várias linhas se você tiver 50.000 itens e 300 repositórios criados, como depósitos, e solicitar a classificação por vencimento de estoque por item, local e depósito.

## <a name="run-an-inventory-aging-report"></a>Executar um Relatório de classificação por vencimento de estoque

1. Vá para **Gerenciamento de custos \> Consultas e relatórios \> Armazenamento do relatório de classificação por vencimento de estoque**.
1. Selecione **Novo**.
1. No campo **Identificador do Processo – Nome**, insira um nome exclusivo para o relatório.
1. Selecione o relatório **Identificação – ID** e filtre-o como necessário.

    A execução do relatório sempre é feita em um trabalho em lotes.

1. Depois que o trabalho em lotes for concluído, as saídas serão mostradas na página **Armazenamento do relatório de classificação por vencimento de estoque**.
1. Para exibir a saída como um formulário com um layout tradicional de grade, selecione **Exibir detalhes**. Para exibir a saída como um gráfico agregado, selecione **Exibir gráfico**.

    > [!NOTE]
    > O formulário não incluirá os subtotais definidos no layout de relatório.

A entidade de dados **Relatório de classificação por vencimento de estoque** permite exportar as saídas de um relatório **Classificação por vencimento de estoque** por meio da aplicação de um filtro para o campo **Identificador do processo – Nome** a qualquer formato que dê suporte ao Gerenciamento de dados.

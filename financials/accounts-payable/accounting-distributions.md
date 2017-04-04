---
title: "Distribuições contábeis"
description: "Este artigo fornece informações sobre distribuições contábeis e descreve as opções disponíveis para o processamento. As distribuições contábeis são usadas para alocar valores monetários para um documento de origem em contas contábeis específicas."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AccountingDistribution
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 17231
ms.assetid: 9030355d-8e6e-408b-9e7d-7b346eaa652c
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: a98ce08dc115bc96cec07c2d6ced10d774785fe9
ms.openlocfilehash: b1057caae6f47e5a17e194834fbbcb9d7d731605
ms.lasthandoff: 03/31/2017


---

# <a name="accounting-distributions"></a>Distribuições contábeis

Este artigo fornece informações sobre distribuições contábeis e descreve as opções disponíveis para o processamento. As distribuições contábeis são usadas para alocar valores monetários para um documento de origem em contas contábeis específicas. 

As distribuições contábeis são um recurso do programa que é usado e estendido por cada documento de origem, como uma ordem de compra, uma fatura de fornecedor, um relatório de despesas e uma fatura de texto livre. Por padrão, uma distribuição contábil padrão é gerada para cada linha do documento de origem e o valor monetário é habilitada condicionalmente para a alteração. 

> [!Note] 
> Alguns documentos também são compatíveis valores monetários de documento do cabeçalho, como encargos para ordens e notas fiscais. 

Os recursos de distribuição contábil genéricos fornecem as seguintes opções para processar distribuições contábeis:

-   **Distribuir valores** – Exibir e modificar as distribuições contábeis para o cabeçalho, linha ou linhas filho de um documento individual, como impostos e encargos.
    -   Para as principais distribuições de valores monetários (distribuições pai), a conta principal e as dimensões financeiras devem ser editáveis diretamente no controle segmentado de entrada na grade. O preço bruto é um exemplo típico de uma distribuição pai.
    -   Os valores das distribuições são baseados na moeda da condição do documento. Geralmente, esta moeda é a moeda da transação. Os valores da contabilidade e da moeda de relatório são gerados como parte da contabilidade de sub-razão.
    -   As distribuições exibem a data e o evento contábeis. Normalmente, o evento contábil está definido como **Nenhum** até que o documento seja lançado/lançado. Naquele ponto, o evento contábil é definido como **Original**. Depois que as distribuições foram lançadas, não é possível alterá-las.
    -   O botão **Dividir** pode ser habilitado para distribuições pai. **Dividir** gera novas distribuições contábeis e a divisão pode ser baseada em porcentagem, no valor ou na quantidade.
    -   O botão** Distribuir igualmente** pode ser usado de forma combinada com **Dividir** para alocar o valor igualmente em todas as distribuições.
    -   O botão **Redefinir** pode ser habilitado para distribuições pai quando há mais de uma distribuição. **Redefinir** reverte qualquer alteração manual na distribuição excluindo as distribuições existentes e regenerando as distribuições padrão.
    -   Qualquer distribuição filho, como desconto, encargo e imposto está de acordo com a a distribuição pai. Você pode exibir parceiro pai/filho ** referência ** &gt; ** em informações ** pai.
    -   A conta principal e a dimensão financeira também podem ser editáveis para filho.
    -   As dimensões financeiras nas distribuições contábeis seguem um padrão de que o documento pode ser estendido. Para obter mais detalhes, consulte os artigos relacionados.
    -   As distribuições de variação podem ser geradas em cenários correspondentes, como a correspondência entre uma fatura e a ordem de compra. Você pode exibir as relações entre compatíveis distribuição contábil ** referência ** &gt; ** em informações de documentos. **
    -   O botão **Corrigir** é exibido para documentos que suportam correções. ** Correto ** criar distribuições novos. Primeiro, as distribuições são criadas que invertem distribuições originais. As distribuições não podem ser alteradas. Em seguida, novas distribuições contábeis corretas é criado. Essas distribuições podem ser alteradas se as distribuições originais puderem ser alteradas.
    -   O botão** Detalhes do projeto** é habilitado como uma extensão quando uma linha estiver relacionada a um projeto. As distribuições contábeis do projeto permitem alterar detalhes como a fonte de financiamento e a propriedade da linha.
    -   Você pode exibir o status de contabilidade de documentos atual dentro ** ** referência. O status é do documento inteiro, e se o documento estará em processo ou concluído.
-   ** Distribuições de exibição ** – exibem distribuições contábeis para todas as linhas e valores monetários no documento. Você não pode alterar as distribuições contábeis nesse modo de exibição.


Para obter mais informações, consulte e distribuições [contábeis entrada no diário-razão auxiliar] para notas fiscais de texto livre (accounting-distributions-subledger-journal-entries-vendor-invoices.md).


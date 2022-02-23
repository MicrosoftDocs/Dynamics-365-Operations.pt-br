---
title: Distribuições contábeis
description: Este tópico fornece informações sobre distribuições contábeis e descreve as opções disponíveis para o processamento.
author: ShylaThompson
manager: AnnBe
ms.date: 09/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AccountingDistribution
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 17231
ms.assetid: 9030355d-8e6e-408b-9e7d-7b346eaa652c
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c9a627ba33065086d21c758a1b8d8f2fa2f6ef02
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440506"
---
# <a name="accounting-distributions"></a>Distribuições contábeis

[!include [banner](../includes/banner.md)]

Este tópico fornece informações sobre distribuições contábeis e descreve as opções disponíveis para o processamento. As distribuições contábeis são usadas para alocar valores monetários para um documento de origem em contas contábeis específicas. 

As distribuições contábeis são um recurso do programa que é usado e estendido por cada documento de origem, como uma ordem de compra, uma fatura de fornecedor, um relatório de despesas e uma fatura de texto livre. Por padrão, uma distribuição contábil padrão é gerada para cada linha do documento de origem e o valor monetário é habilitada condicionalmente para a alteração. 

> [!NOTE] 
> Alguns documentos também oferecem suporte de valores monetários para documentos de cabeçalho, como encargos diversos para ordens e faturas. 

Os recursos de distribuição contábil genéricos fornecem as seguintes opções para processar distribuições contábeis:

-   **Distribuir valores** – Exibir e modificar as distribuições contábeis para o cabeçalho, linha ou linhas filho de um documento individual, como impostos e encargos.
    -   Para as principais distribuições de valores monetários (distribuições pai), a conta principal e as dimensões financeiras devem ser editáveis diretamente no controle segmentado de entrada na grade. O preço bruto é um exemplo típico de uma distribuição pai.
    -   Os valores das distribuições são baseados na moeda da condição do documento. Geralmente, esta moeda é a moeda da transação. Os valores da contabilidade e da moeda de relatório são gerados como parte da contabilidade de sub-razão.
    -   As distribuições exibem a data e o evento contábeis. Normalmente, o evento contábil está definido como **Nenhum** até que o documento seja lançado/lançado. Naquele ponto, o evento contábil é definido como **Original**. Depois que as distribuições foram lançadas, não é possível alterá-las.
    -   O botão **Dividir** pode ser habilitado para distribuições pai. **Dividir** gera novas distribuições contábeis e a divisão pode ser baseada em porcentagem, no valor ou na quantidade.
    -   O botão **Distribuir igualmente** pode ser usado de forma combinada com **Dividir** para alocar o valor igualmente em todas as distribuições.
    -   O botão **Redefinir** pode ser habilitado para distribuições pai quando há mais de uma distribuição. **Redefinir** reverte qualquer alteração manual na distribuição excluindo as distribuições existentes e regenerando as distribuições padrão.
    -   Qualquer distribuição filho, como desconto, encargo e imposto está de acordo com a a distribuição pai. É possível visualizar a relação pai/filho em **Referência** &gt; **Informações sobre pai**.
    -   A conta principal e a dimensão financeira também podem ser editáveis para filho.
    -   As dimensões financeiras nas distribuições contábeis seguem um padrão de que o documento pode ser estendido.
    -   As distribuições de variação podem ser geradas em cenários correspondentes, como a correspondência entre uma fatura e a ordem de compra. É possível visualizar as relações de conciliação entre a distribuição contábil em **Referência** &gt; **Informações do documento**.
    -   O botão **Corrigir** é exibido para documentos que suportam correções. **Corrigir** cria novas distribuições. Primeiro, as distribuições criadas que invertem as distribuições originais. Essas distribuições não podem ser alteradas. Em seguida, as novas distribuições contábeis corretas são criadas. Essas distribuições podem ser alteradas se as distribuições originais puderem ser alteradas.
    -   O botão **Detalhes do projeto** é habilitado como uma extensão quando uma linha estiver relacionada a um projeto. As distribuições contábeis do projeto permitem alterar detalhes como a fonte de financiamento e a propriedade da linha.
    -   É possível visualizar o status atual da contabilidade do documento em **Referência**. O status se refere a todo o documento e indica se ele está sendo processado ou se ele foi concluído.
-   **Exibir distribuições** – Exiba as distribuições contábeis para todas as linhas e valores monetários no documento. Você não pode alterar as distribuições contábeis nesse modo de exibição.

Na versão 10.0.13, um recurso adicionado que valida a tabela de distribuição contábil para garantir que os novos campos estejam configurados corretamente. Esse recurso é chamado **Habilitar a validação adicional de dados para documentos usando a estrutura contábil do documento de origem**. Para usar o recurso, você deve habilitá-lo usando o espaço de trabalho **Gerenciamento de recursos**. Para habilitar o recurso, procure o nome do recurso no campo **Pesquisar** na página **Gerenciamento de recursos** e selecione **Habilitar agora**.

Para obter mais informações, consulte [Distribuições contábeis e entradas no diário-razão auxiliar para faturas de fornecedor](accounting-distributions-subledger-journal-entries-vendor-invoices.md).

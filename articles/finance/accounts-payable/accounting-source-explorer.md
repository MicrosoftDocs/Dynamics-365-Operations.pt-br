---
title: Gerenciador de fontes contábeis
description: Este artigo fornece informações sobre o explorador de origem da contabilidade, que pode ser usado para análise detalhada das informações de origem, além das entradas contábeis da contabilidade.
author: rcarlson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AccountingSourceExplorer
audience: Application User
ms.reviewer: roschlom
ms.custom: 15391
ms.assetid: 57b95899-7298-43c0-8034-45b5d993cbf2
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f1ab7cb7f8f9a42d5f311f8760ff2463055dc178
ms.sourcegitcommit: f2dfec2f4c427e37a574e6acdfaaf150bc92ebb6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2021
ms.locfileid: "6661028"
---
# <a name="accounting-source-explorer"></a>Gerenciador de fontes contábeis

[!include [banner](../includes/banner.md)]

Este artigo fornece informações sobre o explorador de origem da contabilidade, que pode ser usado para análise detalhada das informações de origem, além das entradas contábeis da contabilidade.

O explorador de origem contábil é uma nova página que mostra informações de origem. Você pode usar o explorador de origem contábil como uma ferramenta independente ou analisar os detalhes das entradas de contas contábeis. Por exemplo, você pode usar o explorador de origem contábil para obter as informações mais detalhadas da origem para um saldo no rastreamento de saldos ou para uma transação do voucher. Você pode usar o recurso Exportar para MS Excel para dividir ainda mais as informações no Microsoft Excel (por exemplo, em uma Tabela Dinâmica ou em um relatório de Tabela Dinâmica).

O explorador de origem contábil sempre exibe o valor total por conta contábil como é exibido pela contabilidade (por exemplo, no balancete). Como no Balancete, é possível exibir segmentos nas colunas separadas. Selecione o conjunto de dimensões financeiras apropriado. 

É possível usar os parâmetros para definir um intervalo de datas para análise. Esta funcionalidade também se assemelha à funcionalidade no Balancete.

Para todos os documentos que usam estrutura do documento de origem, o explorador da origem contábil exibe informações adicionais, com base nas distribuições contábeis e, se aplicável, em distribuições contábeis do projeto Essas informações incluem o tipo de valor monetário, projeto, atividade, categoria e a linha de propriedade. Veja alguns exemplos da análise que você pode fazer:

-   Variações entre ordens de compra e faturas de fornecedor, pois cada variação é representada por um tipo de valor monetário, como a variação de encargo
-   Horas faturáveis versus horas não faturáveis e despesas por projeto, unidade de negócios e conta principal

Para documentos de origem que usam o conceito das identidades de referência do documento de origem, o explorador de origem contábil exibe ainda mais detalhes, como o cliente, o fornecedor, o trabalhador, o produto, a quantidade, o texto de unidade e as descrições. Veja alguns exemplos da análise que você pode fazer:

-   Despesas com hotéis por unidade de negócios e nome do hotel para um período fiscal, com base nos relatórios de despesas
-   Descontos por fornecedor, produtos, departamento

Para esses documentos, também é possível navegar no documento de origem real do explorador de origem contábil.

> [!NOTE]
> A partir da versão 10.0.20, o botão **Atualizar** oferece mais dois intervalos para restringir a consulta inicial executada para inserir dados na página. Esses intervalos adicionais também estão disponíveis na versão 10.0.19 como uma atualização de serviço. Estes campos foram incluídos:
>
> - De Comprovante, Para Comprovante
> - De Conta principal, Para Conta principal

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

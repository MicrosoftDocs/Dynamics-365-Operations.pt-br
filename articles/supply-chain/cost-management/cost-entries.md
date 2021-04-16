---
title: Entradas de custo
description: Este artigo fornece informações sobre entradas de custo previsto e quando foram criadas. Uma entrada de custo estimada é um registro que marca a quantidade e os custos de um determinado evento.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19131
ms.assetid: dd2663d8-bcc0-47b1-b36d-57433143487c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 48c37e4355bc3448930a7cfa73ce08ac8e439b97
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5839406"
---
# <a name="cost-entries"></a>Entradas de custo

[!include [banner](../includes/banner.md)]

Este artigo fornece informações sobre entradas de custo previsto e quando foram criadas. Uma entrada de custo estimada é um registro que marca a quantidade e os custos de um determinado evento.

As entradas de custo são agregações de transações de estoque que são registradas nas dimensões de estoque financeiras ativas.

## <a name="examples"></a>Exemplos
### <a name="example-1-no-cost-entries-are-created"></a>Exemplo 1: Nenhuma entrada de custo é criada

Um evento do diário de transferência é registrado. O evento transfere uma parte do item A da localização A para a localização B. A dimensão de estoque do local não será considerada parte do objeto de custo. Sendo assim, o evento cria duas transações de estoque e nenhuma entrada de custo.

### <a name="example-2-cost-entries-are-created"></a>Exemplo 2: Entradas de custo são criadas

Um evento do diário de transferência é registrado. O evento transfere uma parte do item A da localização 1 para a localização 2 A dimensão de estoque do local é considerada parte do objeto de custo. Sendo assim, o evento cria duas transações de estoque e duas entradas de custo.

### <a name="example-3-one-cost-entry-is-created"></a>Exemplo 3: Uma entrada de custo é criada

Um evento de recebimento de produto é registrado para uma ordem de compra. O evento registra 100 peças do item A a um custo unitário de 10,00 reais (BRL). Como o item A usa um número de série para rastrear a finalidade do gerenciamento de estoque, um número de série exclusivo é criado para cada item recebido. Sendo assim, o evento cria 100 transações de estoque e uma entrada de custo.

## <a name="cost-entries-page"></a>Página de entradas de custo
A nova página de **Entradas de custo** permite exibir e controlar os registros de custos e de quantidades. Essa página complementa as páginas **Transação de estoque** e **Liquidações de estoque**. Os registros são registrados em ordem cronológica para um evento. Consequentemente, você pode encontrar e controlar rapidamente os custos acumulados de um evento específico ou todos os eventos relacionados a um documento. Veja a seguir um exemplo:

-   Um evento de recebimento de produto é registrado para o item A. Cem peças são recebidas a um custo unitário de BRL 10,00.
-   Alguns dias após o evento de fatura ser registrado, o custo aumenta para BRL 11,00. Portanto, o valor total é de BRL 1.100,00. Um segundo comprovante é criado para esclarecer a diferença de 100 reais.
-   Alguns dias depois, um encargo diverso de 15,00 reais para cobrir o custo de transporte é registrado na ordem de compra.

| Comprovante | Data       | Demonstrativo      | Número | ID do lote  | Quantidade | Valor  |
|---------|------------|----------------|--------|---------|---------------|----|
| 00001   | 01/01/2015 | Ordem de Compra | 100001 | 0000101 | 100,00   | 1.000,00 |
| 00002   | 20/01/2015 | Ordem de Compra | 100001 | 0000101 |          | 100,00  |
| 00003   | 31/01/2015 | Ajuste     | 100001 | 0000101 |          | 15,00   |

A página **Entradas de custo** permite a filtragem por ID de documento e data de documento. 

> [!NOTE]
> As entradas de custo estão disponíveis somente para [objetos de custo](cost-object.md) ou produtos liberados.

<a name="additional-resources"></a>Recursos adicionais
--------

[Objetos de custo](cost-object.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
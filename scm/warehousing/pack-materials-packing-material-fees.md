---
title: Taxas e materiais de embalagem
description: "As taxas de material de embalagem são pagas a uma empresa de reciclagem em determinados intervalos. Um valor é pago por unidade de peso para cada material com o qual a unidade de embalagem é feita. As taxas de material de embalagem são calculadas e relatadas, mas nenhuma transação do razão é lançada, pois essas taxas não são consideradas como taxas que devam ser pagas a uma autoridade."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventPackagingGroup, InventPackagingMaterialCode, InventPackagingMaterialFee, InventPackagingMaterialTrans, InventPackagingMaterialTransPurch, InventPackagingUnit
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2194
ms.assetid: 040b65dc-43c9-4256-b69f-b2d6e736fbe9
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: e07ed8d8344576f96d2439051255d0e58555c30f
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017

---

# <a name="packing-materials-and-fees"></a>Taxas e materiais de embalagem

[!include[banner](../includes/banner.md)]


As taxas de material de embalagem são pagas a uma empresa de reciclagem em determinados intervalos. Um valor é pago por unidade de peso para cada material com o qual a unidade de embalagem é feita. As taxas de material de embalagem são calculadas e relatadas, mas nenhuma transação do razão é lançada, pois essas taxas não são consideradas como taxas que devam ser pagas a uma autoridade.

Os pesos e as taxas dos materiais de embalagem são calculados para as linhas de ordem de venda e compra.

Você pode definir uma ou mais unidades de embalagem para um item, um grupo de itens de embalagem ou para todos os itens. Uma unidade de embalagem consiste em materiais de embalagem, seus pesos, além do número de itens incluídos na unidade de embalagem. Um código de material de embalagem é atribuído a cada tipo de material de embalagem definido. Com base no código de material de embalagem, você pode especificar um preço para um período específico. A taxa de material de embalagem é calculada com base nessas informações.

| **Nota**                                                                                                                                             |
|------------------------------------------------------------------------------------------------------------------------------------------------------|
| Mesmo que sua empresa não pague taxas de material de embalagem, você poderá usar a funcionalidade para calcular estatísticas de pesos dos materiais de embalagem. |

## <a name="setup-requirements-for-packing-material-fees"></a>Configurar requisitos para taxas de material de embalagem
Antes de calcular pesos ou taxas de materiais de embalagem, ou ambos, você deve criar os seguintes dados base:

-   Grupos de embalagem – Crie grupos de embalagem para atribuir a itens.
-   Códigos de material de embalagem – Crie códigos de material de embalagem para cada tipo de material de embalagem definido.
-   Unidades de embalagem – Especifique uma unidade de embalagem para um item, um grupo de embalagens ou todos os itens. Para cada unidade de embalagem, defina os materiais de embalagem a serem incluídos, atribua pesos e, no campo Fator de unidade de embalagem, insira o fator de conversão da unidade de estoque.
-   Taxas de material de embalagem – Especifique taxas de material de embalagem para cada código de material de embalagem Para cada tipo de material, defina o período de validade, o preço por material, a moeda e a unidade.

## <a name="packing-units-on-sales-order-lines"></a>Unidades de embalagem nas linhas da ordem de venda
Quando você cria uma linha de ordem de venda, o sistema verifica se as unidades de embalagem foram especificadas para o item. Se as unidades de embalagem estiverem especificadas, o sistema atualizará a linha de ordem de venda com a unidade de embalagem especificada e a quantidade de unidade de embalagem. Essa quantidade se baseia na quantidade solicitada e dividida pelo número de itens da unidade de embalagem selecionada. Se uma unidade de embalagem não tiver sido especificada, você poderá inserir manualmente uma unidade de embalagem e uma quantidade de unidade de embalagem na linha de ordem de venda. Também é possível alterar a unidade de embalagem e a quantidade ao lançar a linha de ordem de venda. Isso será relevante se a linha de ordem de venda for apenas parcialmente entregue ou parcialmente faturada. Quando você fatura a ordem de venda, as transações de material de embalagem são criadas. As transações de material de embalagem contêm os pesos dos materiais de embalagem para a linha de venda. Você também pode modificar as transações depois de faturá-las e, em seguida, criar novas transações.

## <a name="packing-units-on-purchase-order-lines"></a>Unidades de embalagem nas linhas da ordem de compra
As transações de material de embalagem para uma linha de ordem de compra não são criadas pelo sistema. Crie transações para as linhas da ordem de compra faturada manualmente na página **Transações de material de embalagem**.

## <a name="set-up-customer-packagingmaterialfee-license-numbers"></a>Configurar os números de licença das taxas de material de embalagem do cliente
Se as taxas de material de embalagem forem pagas pelos clientes, especifique os números de licença dessas taxas na página**Clientes**. Quando um número de licença é atribuído a um cliente, as taxas de material de embalagem são calculadas automaticamente quando as ordens de venda são faturadas. Após o faturamento, a caixa de seleção **Calcular taxa** é desmarcada na página **Transações de material de embalagem**, pois você não precisa calcular e imprimir um relatório. Você pode imprimir os pesos do material de embalagem na fatura e informar aos clientes que eles estão pagando as taxas. 

Se as taxas de material de embalagem forem pagas pela sua empresa, não especifique os números de licença dos clientes. Após o faturamento, a caixa de seleção **Calcular taxa** é marcada na página **Transações de material de embalagem**. Isso indica que as taxas são calculadas quando um relatório é criado. Você pode imprimir os pesos na fatura e indicar que sua empresa paga as taxas.

## <a name="print-packaging-material-weights-on-invoices"></a>Imprimir os pesos do material de embalagem nas notas fiscais
Você pode imprimir os pesos do material de embalagem na fatura e indicar quem está pagando as taxas de material de embalagem. Os pesos são resumidos por código de embalagem.
 






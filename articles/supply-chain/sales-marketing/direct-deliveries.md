---
title: Entregas diretas
description: "Este artigo fornece informações sobre entregas diretas. As entregas diretas são enviadas diretamente do fornecedor para o cliente."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchCreateFromSalesOrder, SalesTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 9704
ms.assetid: 64c51384-8a4e-45d0-83c1-12cea22902f9
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: a62c1c78ae66ffff7e36fe17757bb98d2e7fbc54
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="direct-deliveries"></a>Entregas diretas

[!include[banner](../includes/banner.md)]


Este artigo fornece informações sobre entregas diretas. As entregas diretas são enviadas diretamente do fornecedor para o cliente.

As entregas diretas economizam o tempo de entrega e reduzem os custos associados à manutenção de estoque porque você não retém os produtos no depósito antes de remetê-los ao cliente.  

Você pode criar entregas diretas da página **Ordem de venda**. Primeiro, crie uma ordem de venda e linhas de ordem. Em seguida, no Painel de Ação, na guia **Ordem de venda**, selecione **Entrega direta**. Por fim, especifique as linhas que devem ser tratadas como uma entrega direta. É criado um link entre as linhas da ordem de venda para a entrega direta e as linhas correspondentes na ordem de compra.  

**Observação:** se uma parte da quantidade encomendada já tiver sido entregue, você deverá dividir a quantidade restante. Crie uma nova linha para a quantidade que deve ser entregue diretamente e subtraia essa quantidade da quantidade na linha original. Por exemplo, se a quantidade original for 15 e cinco foram entregues, você deverá criar uma nova linha para a quantidade restante, 10, e então reduzir a quantidade original por esse valor.  

Depois de criar o link de entrega direta entre as linhas da ordem de venda e da ordem de compra, você pode atualizar a ordem de venda usando uma guia de remessa. Realize uma atualização de guia de remessa ou uma atualização da fatura da ordem de compra. Você deve atualizar a ordem de venda na fatura na página **Ordem de venda**. Uma atualização de fatura não pode fazer com que a quantidade na ordem de venda exceda a quantidade registrada como recebida. Por exemplo, uma linha da ordem de venda tem 10 peças, mas apenas cinco peças da linha da ordem de venda são atualizadas com uma guia de remessa. Se você selecionar **Todos** na lista **Quantidade** ao atualizar a ordem de venda na fatura, somente os itens recebidos fisicamente ou atualizados com uma guia de remessa serão atualizados na fatura. A linha de ordem de venda inteira não é atualizada.

## <a name="delivery-date"></a>Data de entrega
Quando você atualiza o campo **Data de recebimento solicitada** na linha da ordem de venda, o campo **Data de entrega** na linha da ordem de compra correspondente também é atualizado. De forma similar, quando você atualiza o campo **Confirmado** na linha de ordem de compra, os campos **Data de recebimento confirmada** e **Data de remessa confirmada** na linha da ordem de venda correspondente também são atualizados.

## <a name="delivery-address"></a>Endereço de entrega
Em geral, o endereço de entrega de uma ordem de compra é o endereço da empresa. No entanto, quando você cria uma entrega direta, insere o endereço do cliente é inserido como o endereço de entrega. Se você alterar o endereço de entrega em uma linha de ordem de compra que tenha o tipo de entrega **Entrega direta**, o endereço de entrega na linha de ordem da venda correspondente também será atualizado. De maneira similar, se você alterar o endereço de entrega na linha da ordem de venda, o endereço de entrega na linha da ordem de compra também será atualizado.

## <a name="deleting-order-lines"></a>Excluindo linhas da ordem
Se você tentar excluir uma linha de ordem de venda que tenha o tipo de entrega **Entrega direta**, uma caixa de mensagem indicará que as linhas da ordem de compra estão anexadas à linha. Se a linha da ordem de venda tiver sido parcialmente entregue, você não poderá excluir a linha da ordem de venda nem as linhas da ordem de compra anexadas a ela.

## <a name="warehouse"></a>Depósito
Quando você cria uma entrega direta, os itens vendidos nunca chegam fisicamente no depósito. No entanto, você ainda deve especificar um depósito na linha da ordem de venda. De forma similar, os requisitos de separação podem ser especificados no grupo de modelos de item para o item. No entanto, como os itens nunca chegam fisicamente no depósito, esses requisitos são ignorados quando a ordem de venda é uma entrega direta.





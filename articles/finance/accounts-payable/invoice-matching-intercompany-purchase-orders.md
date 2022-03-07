---
title: Conciliação de faturas e ordens de compra intercompanhia
description: A entidade legal da compra envolvida em uma transação de comércio intercompanhia pode ser configurada para usar a conciliação de faturas de contas a pagar. Nesse caso, os requisitos de lançamento para o comércio intercompanhia e a conciliação de faturas de contas a pagar devem ser atendidos para que as faturas de fornecedor intercompanhia sejam lançadas.
author: abruer
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchLineMatchingPolicy
audience: Application User
ms.reviewer: roschlom
ms.custom: 3101
ms.assetid: 9c7c2e44-45f8-4325-b6de-a09fe790f9cf
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4af4251580b66895d4dd284a2984d47fddc77066
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5221024"
---
# <a name="invoice-matching-and-intercompany-purchase-orders"></a>Conciliação de faturas e ordens de compra intercompanhia

[!include [banner](../includes/banner.md)]

A entidade legal da compra envolvida em uma transação de comércio intercompanhia pode ser configurada para usar a conciliação de faturas de contas a pagar. Quando o campo **Lançar fatura com discrepâncias** no formulário **Parâmetros de contas a pagar** estiver definido como **Exigir aprovação**, a validação de conciliação de faturas será executada. Nesse caso, os requisitos de lançamento para o comércio intercompanhia e a conciliação de faturas de contas a pagar devem ser atendidos para que as faturas de fornecedor intercompanhia sejam lançadas.

Os exemplos neste tópico usam a seguinte configuração de comércio intercompanhia:
-   Fabrikam Compras é a entidade legal de compra.
-   Fabrikam Vendas é a entidade legal de venda.
-   O cliente 4020 existe na Fabrikam Vendas.
-   O fornecedor 3024 existe na Fabrikam Compras.
-   Na Fabrikam Compras, informações intercompanhias são especificadas para o fornecedor 3024. A Fabrikam Vendas é especificada como empresa do cliente, e o cliente 4020 é especificado como conta do cliente que corresponde à entidade legal da Fabrikam Purchase.
-   Na Fabrikam Vendas, as informações intercompanhias são especificadas para o cliente 4020. A Fabrikam Compras é especificada como empresa do fornecedor, e o fornecedor 3024 é especificado como conta do fornecedor que corresponde à entidade legal da Fabrikam Vendas.

Os exemplos usam a seguinte configuração de conciliação de faturas de contas a pagar para a Fabrikam Compras:
-   Na página Parâmetros de contas a pagar, a opção Habilitar validação da conciliação de faturas está selecionada.
-   Na página Parâmetros de contas a pagar, o campo Lançar fatura com discrepâncias é definido como Exigir aprovação.
-   A porcentagem de tolerância de preços para a entidade legal é 2.

## <a name="example-price-matching-and-intercompany-trade"></a>Exemplo: Conciliação de preço e comércio intercompanhia
Os valores líquidos para a fatura de fornecedor intercompanhia e a fatura de cliente intercompanhia devem ser iguais. Esse requisito substitui as aprovações de conciliação de faturas ou os percentuais de tolerância de preços aplicáveis. Por exemplo, siga estas etapas.
1.  Na Fabrikam Compras, crie a ordem de venda SO888 para o cliente 4020. A ordem de compra intercompanhia ICPO222 é criada automaticamente para o fornecedor 3024 na Fabrikam Compras e a ordem de venda ICSO888 é criada automaticamente na Fabrikam Sales.
2.  Na Fabrikan Vendas, registre que os itens foram recebidos e lance uma guia de remessa. O status de OVIC888 muda para Entregue. O status de OCIC222 muda para Recebido.
3.  Na Fabrikan Vendas, realize uma atualização de fatura para OVIC888. O preço unitário é 0,45 e 100 itens são atualizados.
4.  Na Fabrikam Compras, crie uma fatura para OCIC222. Acidentalmente você altera o preço líquido de 45,00 para 54,00. Um ícone é exibido para indicar que o preço excede a tolerância de preço permitida de 2%.
5.  Na página Detalhes da conciliação de faturas, selecione a opção para aprovar o lançamento com discrepâncias de conciliação. Na página Fatura do fornecedor, clique em OK. Se a fatura do fornecedor não fosse uma fatura de fornecedor intercompanhia, o lançamento teria sido feito com êxito. No entanto, como você está trabalhando com uma fatura de fornecedor intercompanhia, o lançamento não foi feito com êxito. Para o comércio intercompanhia, os totais de fatura na ordem de venda intercompanhia devem ser iguais aos totais de fatura na ordem de compra intercompanhia correspondente. Para resolver esse problema, você deve corrigir o preço líquido da fatura alterando o preço líquido de volta para o valor padrão, 45,00.

## <a name="example-quantity-matching-with-intercompany-trade"></a>Exemplo: Conciliação de quantidade com comércio intercompanhia
As quantidades da ordem de compra intercompanhia e da ordem de venda intercompanhia devem ser iguais. Essa exigência substitui as aprovações de conciliação de faturas aplicáveis. Este exemplo usa a seguinte configuração de comércio intercompanhia adicional:
-   Na Fabrikam Compras, a política de ações da ordem de compra para o fornecedor 3024 é configurada para lançar automaticamente a fatura original de cliente e a fatura de fornecedor intercompanhia.

Este exemplo usa a seguinte configuração adicional de conciliação de faturas de contas a pagar para a Fabrikam Compras:
-   Na página Grupos de modelos de item para o grupo de modelos usado pelo item B-R14, a opção Requisitos de recebimento está selecionada.
-   A quantidade disponível do item B-R14 é 0 (zero).

Por exemplo, siga estas etapas.
1.  Na Fabrikam Compras, crie uma ordem de venda SO999 para o cliente 4020. A ordem contém um item de linha: 100 baterias (item B-R14) ao preço unitário de 1,00 cada. A ordem de compra intercompanhia OCIC333 é criada automaticamente na Fabrikam Compras para o fornecedor 3024, e a ordem de venda OVIC999 é criada automaticamente na Fabrikam Vendas.
2.  Na Fabrikam Vendas, realize uma atualização de fatura para OVIC999. O lançamento não foi feito com êxito, pois o item está esgotado e ainda não foi recebido. Portanto, as informações financeiras não podem ser atualizadas.
3.  Na Fabrikam Vendas, registre que os itens foram recebidos e lance uma guia de remessa para OVIC999. Um recebimento de produtos para a OCIC333 é lançado automaticamente na Fabrikam Compras. Na Fabrikam Compras, a quantidade recebida do item B-R14 muda para 100.
4.  Na Fabrikam Vendas, realize uma atualização de fatura para OVIC999. O lançamento foi feito com êxito nas duas entidades legais. Na Fabrikam Compras, a quantidade comprada do item B-R14 muda para 100.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
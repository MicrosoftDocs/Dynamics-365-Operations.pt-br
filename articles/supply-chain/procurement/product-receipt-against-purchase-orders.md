---
title: ​Recebimento de produtos contra ordens de compra​
description: Este tópico descreve as diversas opções para registrar produtos como recebido.
author: kamaybac
ms.date: 11/15/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, VendPackingSlipJournalListPage, VendPackingSlipJournal
audience: Application User
ms.reviewer: kamaybac
ms.custom: 93113
ms.assetid: d4ec3e86-fce2-4546-911b-e0acf64c8887
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ca52f4127b3ec80eab3ba5c3c239c36d01178c00
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5825461"
---
# <a name="product-receipt-against-purchase-orders"></a>​Recebimento de produtos contra ordens de compra​

[!include [banner](../includes/banner.md)]

Este tópico descreve as diversas opções para registrar produtos como recebido.

Recebimento de produtos é o processo de gravação que produtos foram pedidos foram recebidos, para que as linhas de pedido (PO) de compra podem ser processadas para faturamento. Em alguns casos, produtos passam por pré-registro, onde as informações adicionais do fornecedor são registradas antes que os produtos sejam recebidos. Quando os produtos chegam, primeiro são marcados como **Registrados**. Os produtos, em seguida, podem passar por outros processos, como gerenciamento de qualidade, antes de finalmente estarem marcados como **Recebido**.

## <a name="preregistration-asn"></a>Pré-Registro (ASN)
Fornecedores podem compartilhar informações sobre os produtos que serão enviados. Nesse caso, você pode pré-registrar os produtos para registrar essas informações antes que os produtos são recebidos. Ao pré-registrar os produtos, você reduz a quantidade de trabalho que é necessária durante o recebimento e o registro de item. Fornecedores podem fornecer informações sobre o produto eletronicamente por meio de um adiantamento remessa aviso (ASN) que é automaticamente registrado no sistema. As informações a ASN incluem a quantidade de produtos que serão enviados e a data em que serão enviados. A ASN também pode incluir informações como números de série ou de lote. Registro da ASN ocorre no módulo **Gerenciamento de transporte**.

## <a name="registration"></a>Registro
Registro de recebimento de produto ocorre com frequência em docas de entrada em um depósito. Ele é realizado por meio de um dispositivo de mão ou por meio de diários de entrada. Como alternativa, você pode registrar manualmente o recebimento de produtos usando a ação **Registro** sobre a página **Ordem de compra**. Em ambos os casos, os produtos são marcados como **Registrados**. Observe que os produtos ainda não estão marcados como **Recebido**.  

Produtos que são recebidos em um depósito podem passar por inspeção de qualidade antes de serem colocados fora do estoque. Ordens de qualidade ou ordens de quarentena podem ser usadas para executar a inspeção de qualidade. Se as ordens de qualidade forem usadas, você pode configurar o processo para bloquear temporariamente os produtos por meio de uma reserva enquanto eles são inspecionados. Se as ordens de quarentena são usadas, os produtos são movidos para outro depósito para inspeção. Esse depósito é conhecido como o depósito de quarentena. Em ambos os processos de inspeção de qualidade, alguns dos bens podem ser sucateados, porque eles não estão em conformidade com as expectativas de qualidade ou a inspeção de qualidade envolve testes destrutivos de uma amostra do produto.

## <a name="product-receipt"></a>Recebimento de produtos
Frequentemente, a ação **Recebimento de produtos** na página **Ordens de compra** é usada para marcar os produtos como **Recebido** da OC. A página **Lançamento de recebimento de produto** tem várias opções para a quantidade que é considerada como recebido. Por exemplo, você pode definir o campo **Quantidade** para **Quantidade solicitada** ou **Receber quantidade agora**. Como alternativa, se um processo de recebimento de depósito tiver sido usado, você irá geralmente definir este campo para **Quantidade registrada**. Você pode modificar as quantidades em cada linha da ordem que será marcada como **Recebido**, para levar em conta as discrepâncias, como entrega excedente e entrega insuficiente. Durante o recebimento de produtos, você deve especificar um identificador de recebimento de produtos, que normalmente é uma referência à guia de remessa do fornecedor. Esse identificador é necessário para a contabilidade, porque ele permite verificações ou auditorias de guias contra o que foi recebido e o estoque contabilizado ou despesas de remessa do fornecedor.  

POs podem ser criadas para produtos que não servem como estoque mas são considerados uma despesa. Esta categoria inclui linhas da ordem em que os produtos são marcados como **Não estocado** pelo grupo de modelos de estoque e também linhas de categorias de compras. Nesse caso, os itens não podem passar pelo registro de entrada e recebimento no depósito. Em vez disso, a ação **Remessa de produto** é usada para registrar o recebimento diretamente no pedido de compra e o recebimento é baseado na quantidade solicitada, e não uma quantidade registrada.  

Você pode criar linhas de ordem de compra onde a opção **Novo ativo fixo** está habilitada. Esta opção indica que a compra deve ser considerada um ativo fixo em vez de estoque. Nesse caso, as regras de determinação de ativo fixo que foram configuradas determinam se a compra do produto ou categoria excede limites específicos e, portanto, deve ser contabilizada como um ativo e passam por gerenciamento de ativo fixo. Compras também podem ser feitas em direção a um ativo fixo existente. Nesse caso, o valor é ajustado conforme apropriado.  

Você já pode selecionar várias ordens e recebimento de processo em todas as ordens. Essa abordagem não é usada com muita frequência, mas talvez você queira usá-la se um fornecedor consolidou remessas para você em uma única carga. Durante o recebimento de produtos na compra, há uma função para fazer atualizações de resumo. Resumo de atualizações permitem lançar uma guia de remessa única do fornecedor para mais de uma ordem de compra.  

POs podem ser criados a partir de uma ordem de venda onde a opção **Entrega direta** foi selecionada. Quando a entrega direta é usada, os produtos nunca chegam no depósito mas são entregues diretamente do fornecedor ao cliente. Nesse caso, o recebimento é geralmente registrado diretamente no pedido de compra. O recebimento pode ser feito automaticamente, tais como a integração da electronic data interchange (EDI) com o fornecedor. Como alternativa, se a ordem de compra for uma ordem de compra intercompanhia, o Supply Chain Management automatizará o recebimento de ordem de venda intercompanhia quando ocorrer a remessa. Quando a entrega direta é usada, produtos ainda são contabilizados como estoque, mesmo que eles não cheguem fisicamente no depósito. Portanto, o recebimento de produtos é registrado no pedido de compra, a ordem de venda é automaticamente atualizada com uma guia de remessa, para que a alteração geral no estoque seja 0 (zero). Em cenários de entrega direta, você não deve exigir pré-registro. Se você estiver usando os depósitos que estão habilitados para o gerenciamento de depósito, contorne a necessidade de registro de matrícula, especificando um depósito virtual em vez disso. Especificar este depósito no campo **Depósito de entrega direta** no produto. 

Após o recebimento do produto ser processado no pedido de compra, o status do pedido de compra é definido como **Recebido** para indicar que a fatura pode ser processada para a ordem. Você pode revisar os detalhes sobre os produtos que já foram recebidos usando a página **Diários de recebimento de produto**.  

Você pode acessar esta página a partir do grupo de ação **Recebimento** na página **Ordem de compra**. As informações nos diários incluem detalhes sobre as quantidades, datas e dimensões.

<a name="additional-resources"></a>Recursos adicionais
--------

[Visão geral de ordens de compra](purchase-order-overview.md)

[Criar ordens de compra](purchase-order-creation.md)

[Aprovar e confirmar ordens de compra](purchase-order-approval-confirmation.md)

[​Visão geral de faturas de fornecedor​](../../financials/accounts-payable/vendor-invoices-overview.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
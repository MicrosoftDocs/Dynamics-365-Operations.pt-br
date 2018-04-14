--- 
title: Criar uma ordem de compra com uma agenda de entrega
description: Este procedimento demonstra como criar uma agenda de entrega para ordem de compra.
author: FrankDahl
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 1e4a0204d74c8966cd90b52ae13c88e222ebc3ef
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-purchase-order-with-a-delivery-schedule"></a>Criar uma ordem de compra com uma agenda de entrega

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento demonstra como criar uma agenda de entrega para ordem de compra. Um plano de entrega é usado quando uma quantidade em uma ordem ou diário for exigido para ser entregue em várias remessas. O exemplo mostrado neste guia pode ser usado na empresa dos dados do programa demonstrativo de USMF. Esse procedimento seria feito normalmente por um agente de compras.


## <a name="create-a-delivery-schedule"></a>Criar uma agenda de entrega
1. Vá para Aquisição e fornecimento > Ordens de compra > Todas as ordens de compra.
2. Clique em Novo.
3. No campo Conta de fornecedor, digite US-101.
4. Clique em OK.
5. No campo Número do item, insira M0001.
6. No campo Quantidade, insira 10.
7. Clique na Linha de ordem de compra.
8. Clique em Agenda de entrega.
    * A página do plano de entrega permite especificar o número de remessas na qual a quantidade total da linha da ordem será enviado do fornecedor.  
    * Por padrão, o sistema copia a quantidade total e outros detalhes de entrega das compras originais de linha na primeira linha do plano de entrega. Neste exemplo, criaremos um plano para duas remessas, com a segunda data de remessa compensada em uma semana da remessa.  
9. No campo Quantidade, altere a quantidade para 4.
10. Clique em Novo.
11. No campo Quantidade, insira 6 como a quantidade restante.
    * No campo da data de entrega, selecione uma data que seja de uma semana após a data na primeira linha de entrega.  
    * Você pode controlar a quantidade total alocada para as linhas do plano de entrega olhando totais e os campos restantes. Quando a quantidade restante for zero, a quantidade total de linha original esteve alocada ao plano.  
12. Expanda a seção Conversão das cargas.
    * As opções aqui permitem que você controle como você quer que as cargas sejam distribuídas através das linhas da programação de entrega. Se você selecionar valores brutos de impressão, o valor de encargo na linha de ordem original será copiado na linha de remessa. A opção de alocação das linhas de entrega divide a linha carga original de acordo com a quantidade em cada linha de entrega.  
13. Diminua a seção Conversão das cargas.
14. Clique em OK.
    * O plano de entrega agora foi copiado nas linhas da ordem.  
    * A linha da ordem original, agora conhecida como uma linha comercial, foi convertida em uma linha da ordem com várias entregas. Ela está marcada com um ícone distinto e atua como um cabeçalho para as linhas de entrega.  
15. Selecione a segunda linha da ordem, que é a primeira das duas linhas de entrega.
    * As duas novas linhas, referidas como linhas de entrega, compõem um plano de entrega. A ordem será processada nessas linhas e não na linha original. Se os documentos como confirmações, diários de remessa de produtos ou notas fiscais forem impressos, apenas as linhas de entrega serão exibidas.  

## <a name="change-the-delivery-schedule"></a>Altere a entrega de compras
    * Você pode mudar a quantidade nas linhas de entrega. Se fizer isso, a linha comercial é atualizada automaticamente com a quantidade total nas linhas da entrega.  
1. No campo Quantidade da primeira linha de entrega, altera a quantidade de 4 para 5.
2. Selecione a linha de primeira ordem (a linha comercial).
    * A quantidade na linha comercial foi mudada para 11.  

## <a name="process-product-receipt-using-delivery-schedules"></a>Processe o recibo do produto usando programações de entrega
    * A ordem de compra deve ser confirmada antes que o recibo do produto possa ser processado. Nesse caso, o recebimento é geralmente registrado diretamente no pedido de compra. O recibo poderia igualmente ter sido gravado quando os bens chegaram no armazém.  
1. No Painel de Ação, clique em Compra.
2. Clique em Confirmar.
3. No Painel de Ação, clique em Receber.
4. Clique em Recebimento de produtos.
5. No campo Recebimento de produtos, digite qualquer valor.
    * Este campo é usado para inserir uma referência que seja usada como comprovante do diário de recebimentos de produtos.  
    * No campo Quantidade, selecione "Quantidade solicitada". Esta opção significa que o recibo processará a quantidade com que as linhas da ordem foram criadas.  
    * Certifique-se de que o campo do recibo do produto da cópia está ajustado para Não. A impressão não é necessária neste exemplo.  
6. Expandir a seção Linhas.
    * Observe como o recibo do produto é criado para as duas linhas de entrega e não para a linha original da ordem. Se o recibo foi gravado no armazém, ele também seria gravado nas linhas da programação de entrega.  
7. Recolha a seção Linhas.
8. Clique em OK para lançar o recebimento.



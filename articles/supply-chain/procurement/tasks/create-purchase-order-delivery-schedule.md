---
title: Criar uma ordem de compra com uma agenda de entrega
description: Este tópico demonstra como criar uma agenda de entrega para uma ordem de compra.
author: GalynaFedorova
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, InventItemIdLookupPurchase, PurchDeliverySchedule, PurchEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d1475115b5c1a475f9a56f0f3eb8bb47267d2b91
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8677440"
---
# <a name="create-a-purchase-order-with-a-delivery-schedule"></a>Criar uma ordem de compra com uma agenda de entrega

[!include [banner](../../includes/banner.md)]

Este tópico demonstra como criar uma agenda de entrega para uma ordem de compra. Um plano de entrega é usado quando uma quantidade em uma ordem ou diário for exigido para ser entregue em várias remessas. O exemplo mostrado neste guia pode ser usado na empresa dos dados do programa demonstrativo de USMF. Esse procedimento seria feito normalmente por um agente de compras.

## <a name="create-a-delivery-schedule"></a>Criar uma agenda de entrega
1. No painel de navegação, Acesse **Módulos > Compras e fornecimento > Ordens de compra > Todas as ordens de compra**.
2. No Painel de Ações, selecione **Novo**.
3. No campo **Conta de fornecedor**, insira `US-101`.
4. Selecione **OK**.
5. No campo **Número do item**, insira `M0001`.
6. No campo **Quantidade**, insira `10`.
7. Selecione uma **Linha de ordem de compra**.
8. Selecione **Agenda de entrega**.
- A página **Agenda de entrega** permite especificar o número de remessas na qual a quantidade total da linha da ordem será enviada do fornecedor.  
- Por padrão, o sistema copia a quantidade total e outros detalhes de entrega das compras originais de linha na primeira linha do plano de entrega. Neste exemplo, criaremos um plano para duas remessas, com a segunda data de remessa compensada em uma semana da remessa.  
9. No campo **Quantidade**, altere a quantidade para `4`.
10. Selecione **Novo**.
11. No campo **Quantidade**, insira `6` como a quantidade restante.
- No campo da data de entrega, selecione uma data que seja de uma semana após a data na primeira linha de entrega.  
- Você pode controlar a quantidade total alocada para as linhas do plano de entrega verificando os campos **Total** e **Restante**. Quando a quantidade restante for zero, a quantidade total de linha original esteve alocada ao plano.  
12. Expanda a seção **Conversão de encargos**.
- As opções aqui permitem que você controle como você quer que as cargas sejam distribuídas através das linhas da programação de entrega. Se você selecionar **Copiar valores brutos**, o valor de encargo na linha de ordem original será copiado em cada linha de remessa. A opção **Alocar em linhas de entrega** divide a carga da linha original de acordo com a quantidade em cada linha de entrega.  
13. Recolha a seção **Conversão de encargos**.
14. Selecione **OK**.
- O plano de entrega agora foi copiado nas linhas da ordem.  
- A linha da ordem original, agora conhecida como uma linha comercial, foi convertida em uma linha da ordem com várias entregas. Ela está marcada com um ícone distinto e atua como um cabeçalho para as linhas de entrega.  
15. Selecione a segunda linha da ordem, que é a primeira das duas linhas de entrega.
- As duas novas linhas, referidas como linhas de entrega, compõem um plano de entrega. A ordem será processada nessas linhas e não na linha original. Se os documentos como confirmações, diários de remessa de produtos ou notas fiscais forem impressos, apenas as linhas de entrega serão exibidas.  

## <a name="change-the-delivery-schedule"></a>Altere a entrega de compras
Você pode mudar a quantidade nas linhas de entrega. Se fizer isso, a linha comercial é atualizada automaticamente com a quantidade total nas linhas da entrega.  
1. No campo **Quantidade** da primeira linha de entrega, altere a quantidade de `4` para `5`.
2. Selecione a linha de primeira ordem (a linha comercial).  
- A quantidade na linha comercial foi mudada para 11.  

## <a name="process-product-receipt-using-delivery-schedules"></a>Processe o recibo do produto usando programações de entrega
A ordem de compra deve ser confirmada antes de o recibo do produto ser processado. Nesse caso, o recebimento é geralmente registrado diretamente no pedido de compra. O recibo também pode ter sido gravado quando as mercadorias chegaram no depósito.  
1. No Painel de Ação, selecione **Compra**.
2. Selecione **Confirmar**.
3. No Painel de Ação, selecione **Receber**.
4. Selecione **Recebimento de produtos**. No campo **Recebimento de produtos**, digite qualquer valor.
- Este campo é usado para inserir uma referência que seja usada como comprovante do diário de recebimentos de produtos.  
- No campo **Quantidade**, selecione **Quantidade solicitada**. Esta opção significa que o recibo processará a quantidade com que as linhas da ordem foram criadas.  
- Certifique-se de que o campo **Imprimir recebimento de produtos** da cópia está definido como **Não**. A impressão não é necessária neste exemplo.  
5. Expanda a seção **Linhas**.
- Observe como o recibo do produto é criado para as duas linhas de entrega e não para a linha original da ordem. Se o recibo tivesse sido gravado no depósito, ele também seria gravado nas linhas da agenda de entrega.  
6. Recolha a seção **Linhas**.
7. Selecione **OK** para lançar o recibo.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
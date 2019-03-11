---
title: ​Aprovar e confirmar ordens de compra​
description: Este tópico descreve os status pelos quais uma ordem de compra (OC) passa após ela ter sido criada e o efeito de habilitar o gerenciamento de alterações no PDV.
author: FrankDahl
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 93143
ms.assetid: cd12a944-c52c-4579-a301-7abe1d237c72
ms.search.region: Global
ms.search.industry: ''
ms.author: fdahl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e274f52484d3fe1884152f155b6b7f0714f8842e
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "336948"
---
# <a name="approve-and-confirm-purchase-orders"></a>​Aprovar e confirmar ordens de compra​

[!include [banner](../includes/banner.md)]

[!include [retail name](../includes/retail-name.md)]

Este tópico descreve os status pelos quais uma ordem de compra (OC) passa após ela ter sido criada e o efeito de habilitar o gerenciamento de alterações no PDV.

Depois de criar uma ordem de compra (OC), ela terá que passar por um processo de aprovação. Depois que o fornecedor tiver concordado com a ordem, a ordem de compra é definida como um status de **Confirmado**.

## <a name="approval-of-purchase-orders"></a>Aprovação de ordens de compra
POs que não usam o gerenciamento de alteração com um status de **Aprovado** assim que elas forem criadas, enquanto POs que usam o gerenciamento de alteração têm um status de **Rascunho** quando elas são criados pela primeira vez. Além de isso, as ordens de compra criadas para confirmação ordens planejadas do planejamento mestre são definidos sempre como **Aprovado**, independentemente das configurações de gerenciamento de alterações. Uma OC cria transações de estoque somente quando ela atinge o status **Aprovado**. Portanto, o estoque não aparece como disponível para reserva ou marcação até que o pedido seja aceito.  

Ativar o gerenciamento de alterações para POs definindo a opção **Ativar o gerenciamento de alterações** na página **Parâmetros de compras**. Quando o gerenciamento de alterações é habilitado, as POs devem passar por um fluxo de trabalho de aprovação depois que elas tiverem sido concluídas. O Microsoft Dynamics 365 for Finance and Operations tem um editor de processos de fluxo de trabalho, onde você pode definir um fluxo de trabalho para representar o processo de aprovação. Este fluxo de trabalho pode incluir regras de aprovação automática, as regras que determinam o que será atribuído ao aprovar POs específicos e regras para escalar um fluxo de trabalho que estavam esperando aprovação por um longo tempo. Você pode habilitar o processo de gerenciamento de alterações para todos os fornecedores ou fornecedores específicos. Você também pode configurar o processo de forma que pode ser substituído por PDVs individuais.  

Quando o gerenciamento de alterações é habilitado, POs percorrem os seis status de aprovação de **Rascunho** para **Finalizado**. Depois que um pedido for aprovado, os usuários que deseja modificá-lo devem usar a ação **Solicitar alteração**.

| Status de aprovação | Descrição                                                                      | Solicitação de alteração está ativada |
|-----------------|----------------------------------------------------------------------------------|---------------------------|
| Rascunho           | O pedido de compra é um rascunho e ainda não foi enviado para aprovação do fluxo de trabalho de OC.     | Não                        |
| Em revisão       | O pedido de compra foi enviado para aprovação do fluxo de trabalho de OC. Aguardando minha aprovação       | Não                        |
| Rejeitada        | A ordem de compra foi rejeitado durante o processo de aprovação.                                 | Não                        |
| Aprovado        | O pedido de compra foi aprovado.                                                             | Sim                       |
| Confirmada       | O pedido de compra foi confirmado. Uma ordem de compra não pode ser confirmado até a aprovação.        | Sim                       |
| Finalizado       | O pedido de compra está final. Financeiramente será fechado e não poderá mais ser alterado. | Não                        |

## <a name="confirming-purchase-orders"></a>Confirmar ordens de compra
POs que têm um status de aprovação **Aprovado** podem passar por etapas adicionais antes que elas sejam confirmadas. Por exemplo, você terá de enviar uma consulta de compra para o fornecedor para saber mais sobre preços, descontos ou datas de entrega. Nesse caso, você pode definir a ordem de compra para o status **Na análise externa** usando a ação **Consulta de compra**.  

Fornecedores que estão configurados para usar o portal do fornecedor podem rever pedidos no portal e aprovar ou rejeitá-los. Durante esse processo de revisão, o pedido de compra tem um status de **Na análise externa**. O portal do fornecedor pode ser configurado de modo que uma confirmação do fornecedor confirme automaticamente a ordem no Finanças e Operações. Como alternativa, você pode confirmar manualmente uma ordem de compra após receber a confirmação do fornecedor. Se um fornecedor rejeita um pedido de compra, a rejeição é recebida com o motivo para a rejeição e sugestões para alterações. Nesse caso, o status do pedido de compra permanece **Na análise externa**.  

Há também uma opção para gerar uma confirmação pró-forma para um pedido antes da confirmação real ser processada. Essa opção apenas cria um relatório que pode ser compartilhado com o fornecedor. Ela não cria quaisquer informações de diário.  

Depois que o fornecedor concordar com a ordem, a próxima etapa é registrar o pedido de compra como comprometido. Você pode concluir essa etapa, usando a ação **Confirmação** ou a ação **Confirmar**. Ambas essas ações definiram o status de aprovação da ordem para **Confirmado**. A confirmação de um pedido inicia dois processos adicionais:

-   Um diário é criado para armazenar uma cópia exata do que foi confirmado no sistema. Algumas vezes, pedidos exigem alterações e diários adicionais são criados após a confirmação do pedido atualizado. Esses diários permitem que você exiba o histórico das várias versões da ordem que foram confirmadas.
-   As distribuições contábeis são criadas e solicitar verificações e verificações de orçamento ocorrerem se essa funcionalidade tiver sido habilitada. Se qualquer verificação falhar, você receberá uma mensagem de erro afirmando que alterações devem ser feitas para o pedido de compra antes que ele possa ser confirmado novamente.

Um fornecedor pode solicitar algum tipo de garantia de pagamento será fornecido para uma compra. Há vários métodos para fornecer essa garantia em processos de contas a pagar. Por exemplo, a ação **Pagamento antecipado** reserva fundos para o pedido de compra e este pagamento antecipado é gravado no pedido de compra.

## <a name="changing-purchase-orders"></a>Alterar ordens de compra
Em algumas situações, talvez seja necessário alterar uma ordem de compra depois que ela tiver alcançado um status de aprovação **Aprovado** ou **Confirmado**.  

Se o pedido de compra foi criado usando um processo de gerenciamento de alterações, você pode fazer alterações por retornar a ordem ou, se já tiver sido aprovada a ordem usando a ação **Solicitar alteração**. Nesse caso, o status de aprovação é alterado para **Rascunho** e, em seguida, você pode modificar a ordem. Depois que você terminar de fazer alterações, você terá que enviar o pedido de compra para aprovação novamente. Você pode configurar os tipos de alterações que requerem reaprovação usando uma regra de política **Regra de reaprovação de ordens de compra** na página **Políticas de compra**.  

Se parte da quantidade encomendada para uma linha de ordem de compra foi entregue, você não pode alterar a quantidade solicitada. No entanto, você pode alterar a quantidade **Entrega pendente** na linha. Você pode usar a ação **Finalizar** para cancelar linhas e evitar o processamento adicional. 

Depois que um pedido foi confirmado, você não poderá excluí-lo. No entanto, você pode cancelar a quantidade total ou qualquer quantidade restante na ordem, desde que a quantidade ainda não seja recebida ou faturada.

<a name="additional-resources"></a>Recursos adicionais
--------

[Visão geral de ordem de compra](purchase-order-overview.md)

[Criação de ordem de compra](purchase-order-creation.md)

[Recebimento de produtos contra ordens de compra](product-receipt-against-purchase-orders.md)

[Visão geral de faturas de fornecedor](../../financials/accounts-payable/vendor-invoices-overview.md)




---
title: Aprovar e confirmar ordens de compra
description: Este tópico descreve os status pelos quais uma ordem de compra passa após ela ter sido criada e o efeito de habilitar o gerenciamento de alterações no PDV.
author: mkirknel
manager: tfehr
ms.date: 04/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Retail
ms.custom: 93143
ms.assetid: cd12a944-c52c-4579-a301-7abe1d237c72
ms.search.region: Global
ms.search.industry: ''
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6b331b7e7725b3dd284deb02e59fcf2d699822c4
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3207985"
---
# <a name="approve-and-confirm-purchase-orders"></a>​Aprovar e confirmar ordens de compra​

[!include [banner](../includes/banner.md)]

Este tópico descreve os status pelos quais uma ordem de compra (OC) passa após ela ter sido criada e o efeito de habilitar o gerenciamento de alterações no PDV.

Depois de criar uma ordem de compra (OC), ela terá que passar por um processo de aprovação. Depois que o fornecedor tiver concordado com a ordem, a ordem de compra é definida como um status de **Confirmado**.

## <a name="approval-of-purchase-orders"></a>Aprovação de ordens de compra
As OCs que não usam o gerenciamento de alteração têm um status de **Aprovado** assim que elas são criadas, enquanto as OCs que usam o gerenciamento de alteração têm um status de **Rascunho** quando elas são criadas pela primeira vez. Além de isso, as ordens de compra criadas para confirmação ordens planejadas do planejamento mestre são definidos sempre como **Aprovado**, independentemente das configurações de gerenciamento de alterações. Uma OC cria transações de estoque somente quando ela atinge o status **Aprovado**. Portanto, o estoque não aparece como disponível para reserva ou marcação até que o pedido seja aceito.

Ativar o gerenciamento de alterações para POs definindo a opção **Ativar o gerenciamento de alterações** na página **Parâmetros de compras**. Quando o gerenciamento de alterações é habilitado, as POs devem passar por um fluxo de trabalho de aprovação depois que elas tiverem sido concluídas. O Supply Chain Management tem um editor de processos de fluxo de trabalho, onde você pode definir um fluxo de trabalho para representar o processo de aprovação. Este fluxo de trabalho pode incluir regras de aprovação automática, as regras que determinam o que será atribuído ao aprovar POs específicos e regras para escalar um fluxo de trabalho que estavam esperando aprovação por um longo tempo. Você pode habilitar o processo de gerenciamento de alterações para todos os fornecedores ou fornecedores específicos. Você também pode configurar o processo de forma que pode ser substituído por PDVs individuais.

Quando o gerenciamento de alterações é habilitado, POs percorrem os seis status de aprovação de **Rascunho** para **Finalizado**. Depois que um pedido for aprovado, os usuários que deseja modificá-lo devem usar a ação **Solicitar alteração**.

| Status de aprovação | Descrição                                                                      | Solicitação de alteração está ativada |
|-----------------|----------------------------------------------------------------------------------|---------------------------|
| Preliminar           | A ordem de compra é um rascunho e ainda não foi enviada para aprovação do fluxo de trabalho de OC.     | Não                        |
| Em revisão       | O pedido de compra foi enviado para aprovação do fluxo de trabalho de OC. Aguardando minha aprovação       | Não                        |
| Rejeitada        | A ordem de compra foi rejeitado durante o processo de aprovação.                                 | Não                        |
| Aprovado        | O pedido de compra foi aprovado.                                                             | Sim                       |
| Confirmada       | O pedido de compra foi confirmado. Uma ordem de compra não pode ser confirmada até ser aprovada.        | Sim                       |
| Finalizado       | O pedido de compra está final. Financeiramente será fechada e não poderá mais ser alterada. | Não                        |

## <a name="confirming-purchase-orders"></a>Confirmar ordens de compra
POs que têm um status de aprovação **Aprovado** podem passar por etapas adicionais antes que elas sejam confirmadas. Por exemplo, você terá de enviar uma consulta de compra para o fornecedor para saber mais sobre preços, descontos ou datas de entrega. Nesse caso, você pode definir a ordem de compra para o status **Na análise externa** usando a ação **Consulta de compra**.

Fornecedores que estão configurados para usar o portal do fornecedor podem rever pedidos no portal e aprovar ou rejeitá-los. Durante esse processo de revisão, o pedido de compra tem um status de **Na análise externa**. O portal do fornecedor pode ser configurado para que uma confirmação do fornecedor confirme automaticamente a ordem no Supply Chain Management. Como alternativa, você pode confirmar manualmente uma ordem de compra após receber a confirmação do fornecedor. Se um fornecedor rejeita um pedido de compra, a rejeição é recebida com o motivo para a rejeição e sugestões para alterações. Nesse caso, o status do pedido de compra permanece **Na análise externa**.

Há também uma opção para gerar uma confirmação pró-forma para um pedido antes da confirmação real ser processada. Essa opção apenas cria um relatório que pode ser compartilhado com o fornecedor. Ela não cria quaisquer informações de diário.

Depois que o fornecedor concordar com a ordem, a próxima etapa é registrar o pedido de compra como comprometido. Você pode concluir essa etapa, usando a ação **Confirmação** ou a ação **Confirmar**. Ambas essas ações definiram o status de aprovação da ordem para **Confirmado**. A confirmação de um pedido inicia dois processos adicionais:

-   Um diário é criado para armazenar uma cópia exata do que foi confirmado no sistema. Algumas vezes, pedidos exigem alterações e diários adicionais são criados após a confirmação do pedido atualizado. Esses diários permitem que você exiba o histórico das várias versões da ordem que foram confirmadas.
-   As distribuições contábeis são criadas e solicitar verificações e verificações de orçamento ocorrerem se essa funcionalidade tiver sido habilitada. Se qualquer verificação falhar, você receberá uma mensagem de erro afirmando que alterações devem ser feitas para o pedido de compra antes que ele possa ser confirmado novamente.

Um fornecedor pode solicitar algum tipo de garantia de pagamento será fornecido para uma compra. Há vários métodos para fornecer essa garantia em processos de contas a pagar. Por exemplo, a ação **Pagamento antecipado** reserva fundos para o pedido de compra e este pagamento antecipado é gravado no pedido de compra.

## <a name="changing-purchase-orders"></a>Alterar ordens de compra
Em algumas situações, talvez seja necessário alterar uma ordem de compra depois que ela tiver alcançado um status de aprovação **Aprovado** ou **Confirmado**.

Se o pedido de compra foi criado usando um processo de gerenciamento de alterações, você pode fazer alterações por retornar a ordem ou, se já tiver sido aprovada a ordem usando a ação **Solicitar alteração**. Nesse caso, o status de aprovação é alterado para **Rascunho** e, em seguida, você pode modificar a ordem. Depois que você terminar de fazer as alterações, pode ser necessário enviar a ordem de compra para aprovação novamente. Você pode configurar os tipos de alterações que requerem reaprovação usando uma regra de política **Regra de reaprovação de ordens de compra** na página **Políticas de compra**.

Se parte da quantidade encomendada para uma linha de ordem de compra tiver sido entregue, você não poderá alterar a quantidade solicitada quando a ordem de compra estiver em status de **Rascunho**. No entanto, é possível alterar a quantidade de **Entrega pendente** na linha da ordem de compra que estiver em um status de **Rascunho**.

Depois que um pedido foi confirmado, você não poderá excluí-lo. No entanto, você pode cancelar a quantidade total ou qualquer quantidade restante na ordem, desde que a quantidade ainda não tenha sido recebida ou faturada. Você pode usar a ação **Finalizar** para evitar o processamento adicional. 


## <a name="canceling-purchase-orders"></a>Cancelar ordens de compra

Uma OC pode ser cancelada usando a ação **Cancelar** no cabeçalho.

Se a quantidade tiver sido registrada, recebida ou faturada parcialmente, você pode cancelar somente a quantidade restante que não foi registrada, recebida ou faturada. A quantidade da ordem será reduzida de acordo. Quando a quantidade na linha for atualizada, o status da linha também será atualizado. Por exemplo, a quantidade original na linha é 5 e a quantidade recebida é 3. Nesse caso, é possível cancelar apenas 2. A linha é atualizada para o status **Recebido**.

Se o restante da entrega for adicionado à linha da ordem e exceder a quantidade na linha da ordem, a ação **Cancelar** não cancelará a quantidade em excesso. Em vez disso, a linha permanecerá com status **Ordem em aberto**, pois tem uma quantidade pendente. Por exemplo, a quantidade original na linha é 5 e o restante da entrega é 7. Se a ordem for cancelada, 5 serão cancelados e 2 serão mantidos, conforme é possível ver nas transações de estoque.

Para cancelar a quantidade total em uma linha da ordem de compra, cancele a quantidade restante da entrega na linha. A linha será atualizada para o status **Cancelado**.

Se uma OC no gerenciamento de alterações, todas as mudanças, como o cancelamento da ordem ou da quantidade pendente, devem ser enviadas para o sistema do fluxo de trabalho e aprovadas antes do processo ser concluído e as transações do estoque podem ser atualizadas como canceladas.

<a name="additional-resources"></a>Recursos adicionais
--------

[Visão geral de ordens de compra](purchase-order-overview.md)

[Criar ordens de compra](purchase-order-creation.md)

[​Recebimento de produtos contra ordens de compra​](product-receipt-against-purchase-orders.md)

[Visão geral de faturas de fornecedor](../../finance/accounts-payable/vendor-invoices-overview.md)




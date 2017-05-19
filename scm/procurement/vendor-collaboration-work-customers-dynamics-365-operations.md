---
title: "Colaboração do fornecedor com clientes"
description: "Este tópico descreve como você pode usar a colaboração do fornecedor para trabalhar com OCs e para monitorar o estoque em consignação no Dynamics 365 for Operations."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ConsignmentProductReceiptLines, ConsignmentVendorPortalOnHand, PurchVendorPortalConfirmedOrders, PurchVendorPortalOriginalOrder, PurchVendorPortalResponsesHistoryList, PurchVendorPortalResponsesPart
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 221234
ms.assetid: 6e69fb8b-6d3a-46ef-88cf-6d01212aa7c3
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: d9dafdc211a866aa7d0b2ea139628ec530a2b6d4
ms.contentlocale: pt-br
ms.lasthandoff: 04/25/2017


---

# <a name="vendor-collaboration-with-customers"></a>Colaboração do fornecedor com clientes

[!include[banner](../includes/banner.md)]


Este tópico descreve como você pode usar a colaboração do fornecedor para trabalhar com OCs e para monitorar o estoque em consignação no Dynamics 365 for Operations.

Este tópico descreve como você pode usar a colaboração do fornecedor para trabalhar com clientes no Microsoft Dynamics 365 for Operations. Inclui informações sobre como monitorar e responder a ordens de compra e como monitorar inventário de remessa. Também é possível usar colaboração de fornecedores para trabalhar com faturas. Para obter mais informações, consulte [Espaço de trabalho de faturamento de colaboração do fornecedor](/dynamics365/operations/financials/accounts-payable/vendor-portal-invoicing-workspace).

## <a name="working-with-purchase-orders"></a>Trabalhando com ordens de compra
O espaço de trabalho **Confirmação de ordem de compra** permite que você responda a OCs enviadas para sua revisão. Ele também permite exibir informações sobre OCs que estão esperando uma ação do cliente e OCs que já foram confirmadas, mas ainda estão abertas. Há três listas no espaço de trabalho **Confirmação de ordem de compra**:

-   **Ordens de compra para revisão** – essa lista mostra as OCs que foram enviadas para sua resposta. Depois de responder, a PO desaparece da lista. Se o cliente enviar uma nova versão da OC antes de você responder à versão anterior, apenas a versão mais recente será exibida.
-   **Aguardando ação do cliente** – essa lista mostra as OCs que você respondeu, mas que ainda não foram confirmadas pelo cliente. Se você aceitou a OC, pode monitorá-la nessa lista até que o status mude para **Confirmada**. Se você rejeitou a OC ou aceitou-a com alterações, monitore a OC aqui até que o cliente envie uma nova versão.
-   **Ordens de compra confirmadas em aberto** – essa lista contém todas as OCs de sua conta com status de **Confirmada**. Quando produtos ou serviços são totalmente recebidos com relação à OC, ela desaparece da lista.

A lista a seguir mostra as quatro páginas que você pode usar para trabalhar com ordens de compra, duas das quais têm as mesmas informações que as listas no espaço de trabalho:

-   **Ordens de compra para revisão** (veja acima)
-   **Histórico de confirmações do fornecedor de ordens de compra** – essa página contém todas as OCs e todas as versões das OCs que foram enviadas ao fornecedor, e todas as respostas que foram recebidas do fornecedor.
-   **Ordens de compra confirmadas em aberto** (veja acima)
-   **Todas as ordens de compra confirmadas** – essa página contém todas as OCs que foram confirmadas, inclusive aquelas nas quais os produtos ou serviços foram recebidos. Use essa lista para monitorar OCs para as quais você pode enviar faturas.

### <a name="responding-to-purchase-orders"></a>Respondendo a ordens de compra

As ordens de compra que o cliente enviou para revisão estão visíveis no espaço de trabalho **Confirmação da ordem de compra** e na página **Ordens de compra para revisão**. Depois de abrir um pedido, pode optar por aceitá-lo, rejeitá-lo ou aceitá-lo com alterações. Podem haver anexos no cabeçalho da OC ou nas linhas individuais. Também é possível anexar informações sobre sua resposta no cabeçalho da OC ou nas linhas individuais. Por exemplo, você pode sugerir um item substituto para uma das linhas. Você pode visualizar e imprimir a OC como um arquivo PDF usando a opção **Visualizar/Imprimir**. Oculte ou mostre as seguintes colunas de dimensão usando a ação **Exibir dimensões**: Local, Depósito, Cor, Tamanho, Estilo, Configuração. Se você usar a opção **Aceitar com alterações**, você pode aceitar ou rejeitar linhas individuais. Você também pode fazer as seguintes alterações em linhas:

-   Alterar datas ou quantidades. Se você quiser atualizar a data de entrega confirmada em todas as linhas, use a opção **Atualizar data de entrega** no cabeçalho da OC.
-   Dividir linhas para datas de entrega ou quantidades diferentes.
-   Substituir um item. Para fazer isso, insira uma descrição do item e o número de item no campo **Externo** da seção **Detalhes da linha**.

Você não pode alterar informações de preço ou encargos, mas pode sugerir alterações a esses itens usando notas. Se o cliente enviar a você uma nova versão de uma OC, ela terá um sufixo de versão para indicar que é uma versão modificada de uma OC comunicada anteriormente. A página **Histórico de confirmações do fornecedor de ordens de compra** permite acompanhar o histórico de cada ordem.

## <a name="monitoring-consignment-inventory"></a>Monitorando o estoque em consignação
Se você estiver usando o estoque em consignação, poderá usar a interface de colaboração do fornecedor para exibir informações nas seguintes páginas:

-   **Ordens de compra que consomem o estoque de consignação** - As ordens de compra para inventário de remessa são geradas quando o cliente toma a propriedade do inventário. Essas ordens de compra de consignação são exibidas somente na página**Ordens de compra que consomem o estoque em consignação**. Elas não estão incluídas na página **Todas as ordens de compra confirmadas**.
-   **Produtos recebidos de estoque em consignação** – essa página lista todas as transações em que a propriedade dos produtos é transferida para a empresa que está consumindo o estoque. Use essas informações para faturar o cliente.
-   **Estoque em consignação disponível** – essa página mostra o estoque em consignação disponível de propriedade da sua empresa que está disponível no depósito do cliente.


<a name="see-also"></a>Consulte também
--------

[Gerenciar usuários de colaboração do fornecedor](manage-vendor-collaboration-users.md)





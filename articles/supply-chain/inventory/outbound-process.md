---
title: Visão geral do processo de saída
description: Este artigo fornece uma visão geral do processo de saída no gerenciamento de estoque.
author: yufeihuang
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: WMSOrder, WMSShipment, MCRPickingWorkbench, WMSPickingRegistration, CustomFilterGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "274363"
- intro-internal
ms.assetid: 375807b2-a426-4f1b-bc1f-2fe00fd48413
ms.search.region: global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: 4e3c97862858e219d98b4ef9a81b52c6ab1623ab
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8852466"
---
# <a name="outbound-process-overview"></a>Visão geral do processo de saída

[!include [banner](../includes/banner.md)]

Este artigo fornece uma visão geral do processo de saída no gerenciamento de estoque.

## <a name="output-orders"></a>Ordens de saída

As ordens de saída são usadas para vincular linhas de ordem de venda e linhas de ordem de transferência aos processos de separação de saída que usam as listas de separação.

Quando as listas de separação são geradas de ordens de venda ou de ordens de transferência, as ordens de saídas e remessas são criadas automaticamente. Uma lista de separação tem um relacionamento um para um com uma remessa. A remessa de ordem de transferência ou guia de remessa de ordem de venda pode ser processada da remessa. 

O diagrama a seguir exibe uma visão geral do processo de ordens de saída. 

[![Visão geral do processo da ordem de saída.](./media/outbound-order.png)](./media/outbound-order.png)

Você pode configurar regras de saída para definir como o programa deve tratar o processo de saída. Você pode usar essas regras para controlar o processo de remessa. Particularmente, você pode usar as regras para controlar em qual estágio do processo uma remessa pode ser enviada. As seguintes definições determinam como os processos de saída são tratados.

## <a name="picking-route-status-for-sales-and-transfer-orders"></a>Seleção do status do roteiro para vendas e ordens de transferência 

Acesse **Contas a receber** \> **Configuração** \> **Parâmetros de contas a receber** e, em seguida, na guia **Atualizações**, selecione um valor no campo **Status do roteiro de separação**.

[![Seleção do campo de status de roteiro para ordens de venda.](./media/picking-route-status-sales-order.png)](./media/picking-route-status-sales-order.png)

Se o campo **Status do roteiro de separação** for definido como **Concluído**, o processo de separação ocorre automaticamente como parte do processo de geração das listas de separação. Se o campo for definido como **Ativado**, as linhas da lista de separação devem ser atualizadas manualmente.

A mesma configuração se aplica a ordens de transferência. Acesse **Gerenciamento de estoque** \> **Configuração** \> **Parâmetros de gerenciamento de estoque e depósito** e, em seguida, na guia **Transporte**, selecione um valor no campo **Status do roteiro de separação**.

[![Seleção do campo de status de roteiro para ordens de transferência.](./media/picking-route-status-transfer-order.png)](./media/picking-route-status-transfer-order.png)

## <a name="end-output-inventory-orders"></a>Finalizar ordens de estoque de saída

Acesse **Gerenciamento de estoque** \> **Configuração** \> **Parâmetros de gerenciamento de estoque e depósito** e na guia **Geral**, defina a opção **Finalizar ordem de estoque de saída**.

[![Opção Finalizar ordem de estoque de saída.](./media//end-output-inventory-order.png)](./media//end-output-inventory-order.png)

Quando o trabalhador de depósito reduz as quantidades da lista de separação, as quantidades correspondentes da ordem de estoque são removidas de remessa. Quando a lista de separação for atualizada em dado momento, as quantidades restantes serão relatadas na ordem se a opção **Finalizar ordem de estoque de saída** estiver definida como **Sim**. Se a opção **Finalizar ordem de estoque de saída** estiver definida como **Não**, os valores restantes serão mantidos como uma quantidade de ordem de saída aberta e deverão ser adicionados a uma nova lista de separação como parte da funcionalidade **Abrir ordens de saída**. 

[![Comando Abrir ordens de saída no menu Funções.](./media/open-output-order.png)](./media/open-output-order.png)

[![Menu de funções na página Abrir ordens de saída.](./media/open-output-order-function.png)](./media/open-output-order-function.png)

## <a name="reduce-quantity"></a>Reduzir quantidade

O terceiro parâmetro que você pode usar como parte do processo de geração de listas de separação no parâmetro **Reduzir quantidade**. A configuração deste parâmetro trabalha junto com a configuração **Reserva** que aciona um processo de reserva como parte da liberação ao depósito.

[![Parâmetro Reduzir quantidade.](./media/reduce-quantity.png)](./media/reduce-quantity.png)

## <a name="example-of-an-outbound-process-for-a-sales-order"></a>Exemplo de um processo de saída para uma ordem de venda

Por exemplo, há uma ordem de venda para dois itens. Durante a geração de listas de separação, selecione o parâmetro **Reduzir quantidade**. Portanto, você libera e cria linhas de separação somente para estoque disponível. A separação deve ser reportada por meio de um processo de registro para listas de separação (**Status do roteiro de separação** = **Ativado**).

O estoque que ainda não foi reservado é reservado durante a geração da lista de separação. O estoque indisponível pode ser removido da ordem de venda ou liberado para o depósito para processamento de saída posteriormente, quando o estoque estiver disponível para separação.

[![Atualizar a lista de separação.](./media/update-picking-list.png)](./media/update-picking-list.png)

Assim que todas as linhas de separação forem separadas na página **Registro de lista de separação**, a remessa associada será concluída. O processo para guias de remessa de ordem de venda pode ser inicializado com base em estoque separado.

[![Atualizar remessas de saída.](./media/outbound-shipments.png)](./media/outbound-shipments.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
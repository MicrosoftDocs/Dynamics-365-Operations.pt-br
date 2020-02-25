---
title: Ordens de cliente no Modern POS (MPOS)
description: Este tópico fornece informações sobre ordens de cliente no Modern POS (MPOS). Ordens de cliente também são conhecidas como ordens especiais O tópico inclui uma discussão sobre parâmetros relacionados e fluxos de transação.
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 260594
ms.assetid: 6fc835ef-d62e-4f23-9d49-50299be642ca
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: b8ea8339c2ad25ceed2415eb5ccf5e2048c612fa
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3021569"
---
# <a name="customer-orders-in-modern-pos-mpos"></a>Ordens de cliente no Modern POS (MPOS)

[!include [banner](includes/banner.md)]

Este tópico fornece informações sobre ordens de cliente no Modern POS (MPOS). Ordens de cliente também são conhecidas como ordens especiais O tópico inclui uma discussão sobre parâmetros relacionados e fluxos de transação.

Em um mundo de canal omni de comércio, muitos varejistas oferecem a opção de ordens de cliente, ou ordens especiais, para cumprir vários requisitos de produto e atendimento. Estes são alguns dos cenários típicos:

- Um cliente deseja que produtos sejam entregues a um endereço específico em uma determinada data.
- Um cliente deseja retirar produtos de uma loja ou local que é diferente da loja ou local no qual ele comprou esses produtos.
- Um cliente deseja que outra pessoa retire o produto que ele comprou.

Varejistas também usam ordens de cliente para minimizar perdas de venda que, de outra forma, poderiam ser causadas por faltas de estoque, já que a mercadoria pode ser entregue ou retirada em um horário ou local diferentes.

## <a name="set-up-customer-orders"></a>Configurar ordens de cliente

Estes são alguns dos parâmetros que podem ser definidos na página **Parâmetros de comércio** para definir como as ordens de cliente são atendidas:

- **Percentual de depósito padrão** – Especifique o valor que o cliente deve pagar como depósito antes que uma ordem possa ser confirmada. O valor de depósito padrão é calculado como porcentagem do valor da ordem. Dependendo dos privilégios, um associado da loja talvez consiga substituir o valor usando **Substituição de depósito**.
- **Percentual de encargo de cancelamento** – Se um encargo for aplicado quando uma ordem de cliente é cancelada, especifique o valor desse encargo.
- **Código do encargo de cancelamento** – Se um encargo for aplicado quando uma ordem de cliente é cancelada, esse encargo será refletido em um código de encargo na ordem de venda. Use esse parâmetro para definir o código de encargo de cancelamento.
- **Código do encargo de remessa** – Varejistas podem cobrar uma taxa adicional por enviar mercadoria a um cliente. O valor desse encargo de remessa será refletido em código de encargo na ordem de venda. Use esse parâmetro para mapear o código de encargo de remessa com os encargos de remessa na ordem de cliente.
- **Reembolsar encargos de remessa** – Especifique se os encargos de remessa associados a uma ordem de cliente são reembolsáveis.
- **Valor máximo sem aprovação** – Se os encargos de remessa forem reembolsáveis, especifique o valor máximo dos reembolsos de encargo de envio em ordens de reembolso. Se esse valor for excedido, a substituição do gerente é necessária para continuar com o reembolso. Para acomodar os seguintes cenários, um reembolso de encargos de remessa pode exceder o valor originalmente pago:

    - Encargos são aplicados no nível do cabeçalho das ordens de venda e, quando alguma quantidade de uma linha de produto é devolvida, não é possível determinar o reembolso máximo de encargos de remessa permitido para os produtos e a quantidade de uma forma que funcione para todos os clientes.
    - Encargos de remessa são utilizados para todas as instâncias de remessa. Se um cliente devolver produtos várias vezes e a política do revendedor especificar que o revendedor arcará com o custo de reembolso de encargos de remessa, o reembolso de encargos de remessa será superior aos encargos reais de remessa.

## <a name="transaction-flow-for-customer-orders"></a>Fluxo de transações para ordens de cliente

### <a name="create-a-customer-order-in-modern-pos"></a>Criar uma ordem de cliente no Modern POS

1. Adicione um cliente à transação.
2. Adicione produtos ao carrinho.
3. Clique em **Criar ordem do cliente** e depois selecione o tipo de ordem. O tipo de ordem pode ser **Ordem de cliente** ou **Cotação**.
4. Clique em **Remeter selecionado** ou **Remeter tudo** para enviar os produtos a um endereço na conta do cliente, especifique a data de remessa solicitada e especifique os encargos de remessa.
5. Clique em **Retirar selecionado** ou **Retirar tudo** para selecionar produtos que serão retirados da loja atual ou de uma loja diferente em uma data específica.
6. Cobre o valor de depósito, se um depósito for necessário.

### <a name="edit-an-existing-customer-order"></a>Editar uma ordem de cliente existente

1. Na página inicial, clique em **Encontrar uma ordem**.
2. Encontre e selecione a ordem a ser editada. Na parte inferior da página, clique em **Editar**.

### <a name="pick-up-an-order"></a>Retirar uma ordem

1. Na página inicial, clique em **Encontrar uma ordem**.
2. Selecione a ordem a ser retirada. Na parte inferior da página, clique em **Separação e embalagem**.
3. Clique em **Retirar**.

### <a name="cancel-an-order"></a>Cancelar uma ordem

1. Na página inicial, clique em **Encontrar uma ordem**.
2. Selecione a ordem a ser cancelada. Na parte inferior da página, clique em **Cancelar**.

### <a name="create-a-return-order"></a>Criar uma ordem de devolução

1. Na página inicial, clique em **Encontrar uma ordem**.
2. Selecione a ordem a ser devolvida, selecione a fatura para a ordem e depois selecione uma linha de produto para a mercadoria a ser devolvida.
3. Na parte inferior da página, clique em **Ordem de devolução**.

## <a name="asynchronous-transaction-flow-for-customer-orders"></a>Fluxo de transações assíncronas para ordens de cliente

Ordens de cliente podem ser criadas do cliente do ponto de venda (PDV) em modo síncrono ou assíncrono.

### <a name="enable-customer-orders-to-be-created-in-asynchronous-mode"></a>Habilitar ordens de cliente para serem criadas em modo assíncrono

1. Clique em **Varejo e Comércio** &gt; **Configuração de canal** &gt; **Configuração do PDV** &gt; **Perfis de PDV** &gt; **Perfis de funcionalidade**.
2. Na Guia Rápida **Geral**, defina a opção **Criar ordem do cliente no modo assíncrono** como **Sim**.

Quando a opção **Criar ordem do cliente no modo assíncrono** é definida como **Sim**, as ordens de cliente sempre são criadas no modo assíncrono, mesmo se o Retail Transaction Service (RTS) está disponível. Se você definir essa opção como **Não**, as ordens de cliente sempre serão criadas em modo síncrono por meio de RTS. Quando ordens de cliente são criadas em modo assíncrono, elas são retiradas e inseridas no Commerce por trabalhos de pull (P). As ordens de venda correspondentes são criadas quando **Sincronizar ordens** é executado manualmente ou por meio de um processo em lote.

## <a name="additional-resources"></a>Recursos adicionais

[Ordens híbridas de cliente](hybrid-customer-orders.md)

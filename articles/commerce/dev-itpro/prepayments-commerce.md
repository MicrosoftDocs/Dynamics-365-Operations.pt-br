---
title: Pagamentos antecipados no Dynamics 365 Commerce
description: Este artigo apresenta uma visão geral sobre o processamento de transações com pagamento antecipado no Microsoft Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2021-06-28
ms.openlocfilehash: 8262470f83481ef8840857a52948c0833d8b278e
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780347"
---
# <a name="prepayments-in-dynamics-365-commerce"></a>Pagamentos antecipados no Dynamics 365 Commerce

[!include[banner](../includes/banner.md)]

Este artigo apresenta uma visão geral sobre o processamento de transações com pagamento antecipado no Microsoft Microsoft Dynamics 365 Commerce.

O Dynamics 365 Commerce processa transações de pré-pagamento para os seguintes tipos de pagamento usados ​​em Contas a receber ou Commerce:

- **Pagamento de depósito na conta do cliente** – Um cliente paga um depósito no ponto de venda (POS). O Commerce processa o pagamento do depósito como uma transação de pré-pagamento. Quando você lança a transação, um diário de pagamento é criado e publicado na página **Comprovante de diário** no Commerce headquarters. A caixa de seleção **Comprovante de diário de pré-pagamento** na guia **Pagamento** é selecionada automaticamente para o diário de pagamento. Para obter mais informações, incluindo pré-pagamento e informações específicas sobre impostos relevantes para a região de destino, consulte [Recursos de globalização - Conteúdo de ajuda específico do país/região](/dynamics365/fin-ops-core/dev-itpro/lcs-solutions/country-region?context=%2Fdynamics365%2Fcontext%2Ffinance#countryregion-specific-help-content).
- **Pedido de cliente que possui depósito** – Um cliente cria um pedido de cliente no PDV. O cliente pode pagar um depósito pelo pedido, com base na porcentagem de depósito padrão configurada na página **Ordens do cliente** no Commerce headquarters (**Parâmetros do comércio \> Ordens do cliente**). O Commerce processa o pagamento do depósito da ordem do cliente como uma transação de pré-pagamento. Quando você lança a transação, um diário de pagamento é criado e publicado na página **Comprovante de diário**. A caixa de seleção **Comprovante de diário de pré-pagamento** na guia **Pagamento** é selecionada automaticamente para o diário de pagamento. O pagamento é liquidado e a fatura do cliente é emitida automaticamente quando a ordem é retirada ou entregue.
- **Pedido de venda do call center** - Um representante do Serviço de Atendimento ao Consumidor do call center cria um pedido de venda em nome de um cliente e o atributo **pagamento antecipado** é definido como **Sim** durante a captura do pagamento.

O Commerce executa as seguintes tarefas para processar um pagamento antecipado:

- **Processar um pagamento de depósito na conta do cliente** – Um pagamento de depósito que um cliente faz é transferido para o Commerce usando um serviço que sincroniza os dados. O Commerce processa o pagamento do depósito como uma transação de pré-pagamento. Quando você posta a transação de varejo, um diário de caixa ou diário de pagamento do cliente é postado. A caixa de seleção **Comprovante de diário de pré-pagamento** na guia **Pagamento** da página **Comprovante de diário** no Commerce headquarters é selecionada automaticamente para o diário de pagamento. Pagamentos antecipados não podem ser processados ​​se o valor do pagamento for negativo.
- **Processar um pedido de cliente ou pedido de venda que tenha um depósito** – Um cliente paga um depósito obrigatório para um pedido de cliente usando o Commerce Data Exchange: Serviço em tempo real. O Commerce cria um diário de pagamento do cliente ou um diário de caixa, dependendo do método de pagamento usado pelo cliente. A caixa de seleção **Comprovante de diário de pré-pagamento** na guia **Pagamento** da página **Comprovante de diário** é selecionada automaticamente para o diário de pagamento no Commerce headquarters. Se um cliente usar vários métodos de pagamento para fazer pagamentos parciais, o Commerce processará cada pagamento parcial com base no método de pagamento usado.

Para cartões de crédito e para carteiras digitais que possuem métodos de pagamento com cartão de crédito subjacentes, o Commerce envia uma solicitação de "captura" após a autorização bem-sucedida. (Os fundos são captados antes que o pedido de venda seja faturado.)

Se você cancelar um pedido do cliente, o valor do pré-pagamento será reembolsado e um diário de pagamento de reembolso será lançado com o valor do depósito. O valor do reembolso é calculado e lançado com base no método de pagamento que você especificou quando lançou o pagamento do reembolso. O Commerce pode aplicar uma taxa de cancelamento com base na porcentagem definida na página **Parâmetros do Commerce** no Commerce headquarters.

Se você devolver um pedido de cliente, um pedido de devolução e um diário de pagamento de reembolso serão criados. Quando você lança a ordem de devolução, o Commerce cria um diário de pagamento do cliente ou um diário de caixa, dependendo do método de pagamento usado pelo cliente para a transação original.

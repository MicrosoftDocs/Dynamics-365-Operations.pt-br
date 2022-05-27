---
title: Posição de caixa
description: Este tópico descreve como o recurso de previsão de fluxo de caixa prevê a posição de pagamento à vista de uma organização para horários específicos. Também descreve as opções disponíveis para mostrar previsões para períodos diferentes.
author: ShivamPandey-msft
ms.date: 12/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2019-11-06
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 1c6d394cb192a88316beb2e8746b558eb8dd184b
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2022
ms.locfileid: "8711649"
---
# <a name="cash-position"></a>Posição de caixa

[!include [banner](../includes/banner.md)]

Posição de pagamento à vista é a projeção do fluxo de caixa que é a previsão para o próximo termo. Ele se baseia na projeção de recebimentos à vista de clientes que pagam faturas e ordens pendentes, e também na projeção de pagamentos à vista que são pagos para fornecedores para faturas e ordens de compra.

Quando o sistema prevê os pagamentos do cliente, ele usa as previsões de pagamento do recurso de previsão de pagamento do cliente. Sem previsões de pagamento, o tempo médio necessário para converter uma fatura de cliente para um pagamento para cada cliente é usado para calcular uma data de pagamento. Para ordens de cliente em aberto, o sistema calcula a data da fatura usando o número médio de dias para que as linhas de ordem por cliente sejam faturadas. Em seguida, ele usa a data da fatura como entrada para a funcionalidade de previsão de pagamento. A funcionalidade de previsão de pagamento do cliente calcula uma data de pagamento para cada linha da ordem. 

A data de pagamento para faturas pendentes é estimada a partir das previsões de pagamento, selecionando uma data que corresponda ao quinquagésimo percentil da função de distribuição cumulativa que é obtida das probabilidades do período previsto.

Uma abordagem semelhante é usada para prever pagamentos para fornecedores. Para cada fornecedor, o sistema calcula o tempo médio necessário para converter uma fatura de fornecedor para um pagamento. Esse número de dias é usado para calcular a data de pagamento. Para ordens de fornecedor abertas, o sistema calcula a data da fatura considerando o número médio de dias necessário para converter as linhas de ordem em uma fatura para cada fornecedor. O sistema calcula a data de pagamento usando o tempo médio necessário para converter uma fatura de fornecedor para um pagamento para cada fornecedor.

A seção superior da guia **Posição de pagamento à vista** inclui um gráfico de posição de pagamento à vista. Esse gráfico mostra fluxos de entrada e saída de caixa e seu impacto no saldo de liquidez total. Os detalhes no gráfico de posição de pagamento à vista podem ser exibidos em períodos diários, semanais, mensais ou trimestrais. Ao selecionar **Diariamente**, você pode exibir previsões para os próximos 21 dias. Ao selecionar **Semanalmente**, você pode exibir previsões para as próximas 20 semanas. Ao selecionar **Mensalmente**, você pode exibir previsões para os próximos 12 meses. Ao selecionar **Trimestralmente**, você pode exibir previsões para os próximos 12 trimestres. Você pode ocultar o gráfico se precisar de espaço adicional na tela para exibir o conteúdo na guia **Posição de pagamento à vista**.

A seção inferior da guia **Posição de pagamento à vista** mostra detalhes da posição, do fluxo de caixa, dos pagamentos projetados e da conta bancária.

- As informações na grade **Detalhes da posição** são apresentadas em três seções: uma lista de contas de liquidez, uma lista de documentos que compõem fluxos de entrada de caixa e uma lista de documentos que compõem saídas de caixa. A grade também mostra saldos de posição de pagamento à vista. Para o primeiro período que você está exibindo, o saldo das contas de liquidez é o saldo inicial. Para períodos subsequentes, os saldos para as contas de liquidez são calculados com base na adição de entrada de caixa e na subtração de saídas de caixa de períodos anteriores. Para exibir detalhes das transações que compõem o saldo, selecione o link **Saldo**.
- A grade **Fluxo de caixa** mostra entradas de caixa, saídas de caixa agregadas por período e seu impacto nos saldos de conta de liquidez. Para o primeiro período, o saldo das contas de liquidez é o saldo inicial. Para períodos subsequentes, os saldos para as contas de liquidez são calculados com base na adição de entrada de caixa e na subtração de saídas de caixa de períodos anteriores.
- A grade **Saldo bancário projetado** mostra saídas de caixa esperadas e seu impacto nas contas de liquidez.
- A grade **Conta bancária** mostra o impacto de entradas e saídas de caixa esperada no saldo do banco.

Para salvar e editar a posição de pagamento à vista, crie um instantâneo. FoPara obter mais informações sobre como trabalhar instantâneos, consulte [Visão geral de instantâneos](payment-snapshots.md).

## <a name="details-of-the-cash-position-capability"></a>Detalhes do recurso de posição de caixa 

O recurso de posição de caixa inclui a funcionalidade a seguir. 

- A posição de caixa mostra o fluxo de caixa com base em documentos existentes no sistema e nas linhas de entrada e saída importadas dos sistemas externos.
- Facilita a integração de dados de fluxo de caixa de sistemas externos para o Dynamics 365 Finance. A posição de caixa também podem usar a estrutura de importação-exportação de dados. Esta estrutura facilita a integração com o Excel/OData. Também é possível combinar dados de várias fontes para criar uma solução de posição de caixa abrangente.
- Introduz a posição de caixa à vista inteligente. A posição de caixa é criada com base no comportamento de pagamento do cliente para prever quando uma empresa pode esperar dinheiro chegar em suas contas.
- Para ordens e faturas do cliente, a funcionalidade de IA de previsão de pagamento do cliente é usada para determinar o comportamento histórico de pagamento do cliente quando uma ordem ou fatura for paga.
- Para ordens e faturas do fornecedor, usamos o tempo médio entre a remessa e a fatura e o pagamento de uma fatura por fornecedor para determinar quando uma ordem ou fatura do fornecedor será paga, fazendo com que as saídas de caixa sejam mais precisas.

Isso cria uma visão mais precisa do fluxo de caixa com base no comportamento do pagamento histórico do tesoureiro. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

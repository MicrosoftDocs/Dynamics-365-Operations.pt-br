---
title: Posição de pagamento à vista (Versão preliminar)
description: Este tópico descreve como o recurso de previsão de fluxo de caixa prevê a posição de pagamento à vista de uma organização para horários específicos. Também descreve as opções disponíveis para mostrar previsões para períodos diferentes.
author: ShivamPandey-msft
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2019-11-06
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 36eb939d2539653fdcde78a6044cf1a87e8e3280
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5811378"
---
# <a name="cash-position-preview"></a>Posição de pagamento à vista (versão preliminar)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Posição de pagamento à vista é a projeção do fluxo de caixa que é a previsão para o próximo termo. Ele se baseia na projeção de recebimentos à vista de clientes que pagam faturas e ordens pendentes, e também na projeção de pagamentos à vista que são pagos para fornecedores para faturas e ordens de compra.

Quando o sistema prevê os pagamentos do cliente, ele usa as previsões de pagamento do recurso de previsão de pagamento do cliente. Sem previsões de pagamento, o tempo médio necessário para converter uma fatura de cliente para um pagamento para cada cliente é usado para calcular uma data de pagamento. Para ordens de cliente em aberto, o sistema calcula a data da fatura usando o número médio de dias para que as linhas de ordem por cliente sejam faturadas. Em seguida, ele usa a data da fatura como entrada para a funcionalidade de previsão de pagamento. A funcionalidade de previsão de pagamento do cliente calcula uma data de pagamento para cada linha da ordem. 

<*Texto necessário de Jarek ou Dave sobre como as previsões de pagamento são convertidas em uma data*> a data de pagamento para faturas pendentes é aproximada [*estimada*] a partir das previsões de pagamento, selecionando uma data que corresponda ao quinquagésimo percentil da função de distribuição cumulativa que é obtida das probabilidades do período previsto.

Uma abordagem semelhante é usada para prever pagamentos para fornecedores. Para cada fornecedor, o sistema calcula o tempo médio necessário para converter uma fatura de fornecedor para um pagamento. Esse número de dias é usado para calcular a data de pagamento. Para ordens de fornecedor abertas, o sistema calcula a data da fatura considerando o número médio de dias necessário para converter as linhas de ordem em uma fatura para cada fornecedor. O sistema calcula a data de pagamento usando o tempo médio necessário para converter uma fatura de fornecedor para um pagamento para cada fornecedor.

A seção superior da guia **Posição de pagamento à vista** inclui um gráfico de posição de pagamento à vista. Esse gráfico mostra fluxos de entrada e saída de caixa e seu impacto no saldo de liquidez total. Os detalhes no gráfico de posição de pagamento à vista podem ser exibidos em períodos diários, semanais, mensais ou trimestrais. Ao selecionar **Diariamente**, você pode exibir previsões para os próximos 21 dias. Ao selecionar **Semanalmente**, você pode exibir previsões para as próximas 20 semanas. Ao selecionar **Mensalmente**, você pode exibir previsões para os próximos 12 meses. Ao selecionar **Trimestralmente**, você pode exibir previsões para os próximos 12 trimestres. Você pode ocultar o gráfico se precisar de espaço adicional na tela para exibir o conteúdo na guia **Posição de pagamento à vista**.

A seção inferior da guia **Posição de pagamento à vista** mostra detalhes da posição, do fluxo de caixa, dos pagamentos projetados e da conta bancária.

- As informações na grade **Detalhes da posição** são apresentadas em três seções: uma lista de contas de liquidez, uma lista de documentos que compõem fluxos de entrada de caixa e uma lista de documentos que compõem saídas de caixa. A grade também mostra saldos de posição de pagamento à vista. Para o primeiro período que você está exibindo, o saldo das contas de liquidez é o saldo inicial. Para períodos subsequentes, os saldos para as contas de liquidez são calculados com base na adição de entrada de caixa e na subtração de saídas de caixa de períodos anteriores. Para exibir detalhes das transações que compõem o saldo, selecione o link **Saldo**.
- A grade **Fluxo de caixa** mostra entradas de caixa, saídas de caixa agregadas por período e seu impacto nos saldos de conta de liquidez. Para o primeiro período, o saldo das contas de liquidez é o saldo inicial. Para períodos subsequentes, os saldos para as contas de liquidez são calculados com base na adição de entrada de caixa e na subtração de saídas de caixa de períodos anteriores.
- A grade **Saldo bancário projetado** mostra saídas de caixa esperadas e seu impacto nas contas de liquidez.
- A grade **Conta bancária** mostra o impacto de entradas e saídas de caixa esperada no saldo do banco.

Para salvar e editar a posição de pagamento à vista, crie um instantâneo. FoPara obter mais informações sobre como trabalhar instantâneos, consulte [Visão geral de instantâneos](payment-snapshots.md).

#### <a name="privacy-notice"></a>Aviso de privacidade
As versões prévias (1) podem utilizar menos medidas de privacidade e segurança que o serviço do Dynamics 365 Finance and Operations, (2) não estão incluídas no contrato de nível de serviço (SLA) desse serviço, (3) não devem ser usadas para processar dados pessoais ou outros dados sujeitos a requisitos de conformidade legais ou regulatórios e (4) têm suporte limitado.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
---
title: Visão geral de crédito e cobranças
description: Este tópico apresenta uma visão geral da funcionalidade de crédito e cobranças.
author: mikefalkner
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.custom: intro-internal
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 24df4ffe5b8af7535611bdf71472bc580ef594e94c96cdafc0e4ec52a5d07c13
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6763349"
---
# <a name="credit-and-collections-overview"></a>Visão geral de crédito e cobranças

[!include [banner](../includes/banner.md)]

Você pode gerenciar os limites de crédito de seus clientes e realizar atividades de cobrança quando forem necessárias.

## <a name="credit-management"></a>Gerenciamento de crédito

O gerenciamento de crédito de cliente permite gerenciar limites de crédito e controlar o fluxo de ordens de venda por meio do processo de lançamento, com base nas regras de crédito criadas.

O processo de gerenciamento de crédito pode incluir qualquer uma das seguintes etapas:

- Atualizar os atributos de crédito para que os clientes forneçam informações adicionais sobre confiabilidade de crédito.
- Criar limites de crédito para os clientes usando ajustes de limite de crédito.
- Criar limites de crédito temporários para os clientes usando ajustes de limite de crédito. Dessa forma, você pode aumentar ou diminuir temporariamente os limites de crédito dos clientes com base nas requisições de negócios.
- Adicionar informações que podem afetar o limite de crédito, como informações sobre seguro e garantias.
- Criar grupos de crédito de cliente que vinculem os clientes para que eles compartilhem um único limite de crédito.
- Atribuir pontuações de risco aos clientes e usar as pontuações para gerar automaticamente limites de crédito para esses clientes por meio de ajustes de limite de crédito.
- Criar regras de bloqueio que coloquem uma ordem em espera durante um ou mais processos de lançamento com base em fatores como risco, condições de pagamento, limites de crédito, valores vencidos e a porcentagem do limite de crédito que foi usado.
- Gerenciar uma lista de ordens de venda em espera, revisar os motivos do bloqueio e mitigar problemas.
- Liberar ordens de venda para dar andamento a elas no processo de lançamento.
- Configurar um fluxo de trabalho para gerenciar a aprovação de alterações no limite de crédito e liberações de ordens de venda.

## <a name="collections-management"></a>Gerenciamento de cobranças

A página **Cobranças** mostra uma exibição centralizada onde são gerenciadas as informações sobre cobranças de contas a receber. Os gerentes de cobranças podem usar essa exibição centralizada para gerenciar cobranças. Os agentes de cobranças podem iniciar o processo de cobranças em listas de clientes que são geradas com o uso de critérios de cobrança predefinidos ou na página **Clientes**.

Antes de começar a configurar ou trabalhar com cobranças, você deve entender os seguintes conceitos:

- Os instantâneos de classificação por vencimento de clientes contêm informações de saldo antigo em um determinado ponto no tempo.
- Os grupos de clientes de cobranças ajudam você a organizar seu trabalho.
- Os agentes de cobranças podem ter seus próprios grupos de clientes.
- As páginas de lista organizam clientes, atividades e casos de cobranças.
- Todas as informações de cobranças de um cliente estão em uma página e você pode agir com base nessa página.
- Juros e taxas podem ser cancelados, restabelecidos ou revertidos em uma única etapa.
- Transações de baixa podem ser criadas em uma única etapa.
- Pagamentos NSF (insuficiência de fundos) podem ser processados em uma única etapa.

Para obter descrições desses conceitos, consulte [Principais conceitos de gerenciamento de cobranças](./cm-collections-concepts.md).

## <a name="additional-resources"></a>Recursos adicionais

[Configuração de parâmetros de gerenciamento de crédito de cliente](./cm-credit-mgmt-setup.md)

[Informações de configuração de gerenciamento de crédito de cliente](./cm-setup-information.md)

[Adicionar informações de gerenciamento de crédito de um cliente](./cm-add-credit-mgmt-information-customer.md)

[Grupos de crédito de cliente](./cm-customer-credit-groups.md)

[Ajustes de limite de crédito de cliente](./cm-credit-limit-adjustments.md)

[Bloqueios de crédito para ordens de venda](./cm-sales-order-credit-holds.md)

[Tarefas periódicas de gerenciamento de crédito de cliente](./cm-periodic-tasks.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
---
title: Requisições de Compra
description: Este tópico descreve como as requisições de compra têm suporte na Otimização de Planejamento.
author: ChristianRytt
manager: tfehr
ms.date: 01/04/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2021-01-04
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 8075f8d7c3868c6d6012edbce17dbbb4749209ab
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992335"
---
# <a name="purchase-requisitions"></a>Requisições de Compra

O planejamento mestre pode reabastecer requisições de compra aprovadas. Portanto, ao cobrir requisições de compra, os usuários não precisam usar um fluxo de trabalho para criar ordens de compra. Em vez disso, as requisições de compra podem ser cobertas pelo planejamento mestre. Por causa dessa funcionalidade, uma requisição de compra pode produzir uma ordem de compra, uma ordem de transferência ou uma ordem de produção, dependendo do valor **Tipo de ordem planejada** definido para o produto relacionado.

## <a name="enable-master-plans-to-include-requisitions"></a>Habilitar planos mestres para incluir requisições

Para incluir requisições durante o cálculo de cobertura de um plano mestre, siga estas etapas.

1. Vá para **Planejamento mestre** \> **Configuração** \> **Planos** \> **Planos mestres**.
1. Crie ou selecione um plano mestre.
1. Na FastTab **Geral**, defina a opção **Incluir requisições** como *Sim*.
1. Repita as etapas 2 e 3 para cada plano mestre adicional no qual você deseja incluir requisições.

## <a name="approved-requisitions-time-fence"></a>Limite de tempo de requisições aprovadas

O *limite de tempo de requisições aprovadas* estabelece até quando (em dias) um plano mestre incluirá a demanda de requisições de reabastecimento aprovadas. Você pode definir um limite de tempo de requisições aprovadas no nível do grupo de cobertura e do plano mestre.

### <a name="set-the-approved-requisitions-time-fence-for-a-coverage-group"></a>Definir o limite de tempo de requisições aprovadas para um grupo de cobertura

1. Vá para **Planejamento mestre** \> **Configuração** \> **Cobertura** \> **Grupo de cobertura**.
1. Crie ou selecione um grupo de cobertura.
1. Na FastTab **Outro**, defina o campo **Limite de tempo de requisições aprovadas (dias)** como o número de dias a ser incluído no limite de tempo.
1. Repita as etapas 2 e 3 para cada grupo de cobertura adicional no qual você deseja definir um limite de tempo de requisições aprovadas.

### <a name="set-the-approved-requisitions-time-fence-for-individual-master-plans"></a>Definir o limite de tempo de requisições aprovadas para planos mestres individuais

Ao definir um limite de tempo de requisições aprovadas para um plano mestre individual, a configuração de limite de tempo é substituída para qualquer grupo de cobertura aplicável.

1. Vá para **Planejamento mestre** \> **Configuração** \> **Planos** \> **Planos mestres**.
1. Crie ou selecione um plano mestre.
1. Na FastTab **Limites de tempo em dias**, defina o campo **Limite de tempo de requisições aprovadas (dias)** como o número de dias a ser incluído no limite de tempo.
1. Repita as etapas 2 e 3 para cada plano mestre adicional no qual você deseja definir um limite de tempo de requisições aprovadas.

> [!IMPORTANT]
> **Em breve:** os limites de tempo de requisições aprovadas ainda não têm suporte para a Otimização de Planejamento. Até que tenham suporte, todos os valores inseridos no campo **Limite de tempo de requisições aprovadas (dias)** serão ignorados.

## <a name="independent-supply-regardless-of-coverage-code"></a>Fornecimento autônomo, independentemente do código de cobertura

As requisições de compra são sempre cobertas por ordens planejadas autônomas, independentemente do código de cobertura. Esse comportamento garante rastreabilidade e fluxos de trabalho claros entre requisições de compra e ordens de reabastecimento.

### <a name="example-1"></a>Exemplo 1

Um produto é configurado para ter um valor **Código de cobertura** de *Mín./Máx.*. Ele tem os seguintes status de estoque e requisição:

- Quantidade disponível de estoque = 10.
- Quantidade mínima de estoque = 15.
- Quantidade máxima de estoque = 20.
- Há uma requisição de compra para uma peça. Sua data de solicitação é hoje.

Quando o planejamento mestre é executado, duas ordens planejadas são criadas: uma para 10 peças a fim de reabastecer o estoque até a quantidade máxima e outra para uma peça a fim de reabastecer a requisição de compra.

### <a name="example-2"></a>Exemplo 2

Um produto é configurado para ter um valor **Código de cobertura** de *Mín./Máx.*. Ele tem os seguintes status de estoque e requisição:

- Quantidade disponível de estoque = 17.
- Quantidade mínima de estoque = 15.
- Quantidade máxima de estoque = 20.
- Há uma requisição de compra para uma peça. Sua data de solicitação é hoje.

Quando o planejamento mestre é executado, uma ordem planejada para uma peça é criada para reabastecer a requisição de compra.

### <a name="example-3"></a>Exemplo 3

Um produto é configurado para ter um valor **Código de cobertura** de *Período* e um período de sete dias. Ele tem os seguintes status de estoque, ordem de venda e requisição:

- Quantidade disponível de estoque = 0.
- Há uma ordem de venda para cinco peças. Sua data de remessa esperada é hoje mais um dia.
- Há uma requisição de compra para três peças. Sua data de solicitação é hoje mais três dias.

Quando o planejamento mestre é executado, duas ordens planejadas são criadas: uma para três peças a fim de reabastecer a requisição de compra e outra para cinco peças a fim de reabastecer a demanda da ordem de venda.

> [!NOTE]
> Depois que uma ordem planejada vinculada a uma requisição de compra é confirmada, o mecanismo de planejamento mantém a vinculação à requisição de compra. Se, posteriormente, na ordem confirmada, estiver faltando alguma quantidade necessária para atender à requisição de compra, o sistema criará uma nova ordem planejada para a diferença.

Para obter mais informações sobre requisições de compra, consulte [Visão geral de requisições de compra](../../procurement/purchase-requisitions-overview.md).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
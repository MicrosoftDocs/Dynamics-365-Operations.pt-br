---
title: Cenários de limite de crédito
description: Este artigo descreve como o limite de crédito do cliente é verificado quando o cliente pertence a um grupo de limite de crédito do cliente.
author: JodiChristiansen
ms.date: 06/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2022-06-28
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 60b17a6b7f57b468610974ae9bd05b7db3584cc1
ms.sourcegitcommit: 85141b21ac90f3db1b378c21f9c7f3d8f74e182f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2022
ms.locfileid: "9130248"
---
# <a name="credit-limit-scenarios"></a>Cenários de limite de crédito

No Gerenciamento de crédito, um limite de crédito pode ser atribuído aos clientes no nível do cliente. Cada cliente pode ser atribuído a um *grupo de limite de crédito do cliente* e cada grupo tem um limite de crédito. Portanto, um limite de crédito também pode ser atribuído aos clientes no nível do grupo. Todos os clientes atribuídos ao mesmo grupo de crédito do cliente têm o mesmo limite de crédito.

Em geral, os limites de crédito do grupo são verificados antes dos limites de crédito individuais. O limite de crédito individual nem sempre substitui o limite de crédito do grupo.

Este artigo descreve cinco cenários relacionados a grupos de crédito do cliente e limites de crédito individuais.

## <a name="the-customer-group-credit-limit-is-more-than-the-individual-credit-limit"></a>O limite de crédito de grupo do cliente é maior do que o limite de crédito individual

Por exemplo, o cliente tem um limite de crédito individual de US$ 10.000. O cliente é atribuído a um grupo de crédito do cliente e o limite de crédito do grupo é US$ 15.000. Neste caso, o "limite de crédito efetivo" do cliente é US$ 10.000, pois esse valor é menor do que o limite do grupo. As regras de bloqueio verificam primeiro o limite do grupo. Em seguida, elas verificam o limite individual. Qualquer ordem de venda acima de US$ 10.000 será bloqueada.

## <a name="the-individual-credit-limit-is-more-than-the-customer-group-credit-limit"></a>O limite de crédito individual é maior do que o limite de crédito de grupo do cliente

Por exemplo, o cliente tem um limite de crédito individual de US$ 20.000. O cliente é atribuído a um grupo de crédito do cliente e o limite de crédito do grupo é US$ 15.000. Nesse caso, o limite de crédito efetivo do cliente é de US$ 15.000, pois as regras de bloqueio sempre verificam primeiro o limite do grupo. Qualquer ordem de venda acima de US$ 15.000 será bloqueada.

## <a name="the-individual-credit-limit-is-set-to-000-and-mandatory-credit-limit-is-set-to-yes"></a>O limite de crédito individual é definido como 0,00 e o limite de crédito Obrigatório é definido como Sim

Se o cliente tiver um limite de crédito individual definido como **0,00**, e a opção **Limite de crédito obrigatório** for definida como **Sim**, o limite de crédito efetivo do cliente será US$ 0,00, mesmo se o cliente for atribuído a um grupo de crédito do cliente. Dessa forma, o cliente pode fazer parte de um grupo, mas todas as ordens vão para o Gerenciamento de crédito.

## <a name="the-individual-credit-limit-is-set-to-000-and-unlimited-credit-limit-is-set-to-yes"></a>O limite de crédito individual é definido como 0,00 e o limite de crédito Ilimitado é definido como Sim

Se o cliente tiver um limite de crédito individual definido como **0,00**, mas a opção **Limite de crédito ilimitado** for definida como **Sim**, o cliente terá crédito ilimitado, mesmo se ele estiver atribuído a um grupo de crédito do cliente.

## <a name="the-individual-credit-limit-is-set-to-000-and-the-customer-is-part-of-a-customer-credit-group"></a>O limite de crédito individual é definido como 0,00 e o cliente faz parte de um grupo de crédito do cliente

Por exemplo, o cliente tem um limite de crédito individual definido como **0,00**, a opção **Crédito ilimitado** está definida como **Não** e a opção **Limite de crédito obrigatório** está definida como **Não**. O cliente é atribuído a um grupo de crédito do cliente e o limite de crédito do grupo é US$ 15.000. Nesse caso, o limite de crédito efetivo do cliente é o limite do grupo, US$ 15.000. Portanto, qualquer ordem de venda acima desse valor será bloqueada. Esse comportamento permite que o limite de crédito seja gerenciado no nível do grupo de crédito do cliente, e não no nível do cliente individual. Todos os clientes atribuídos ao mesmo grupo têm o mesmo limite de crédito.

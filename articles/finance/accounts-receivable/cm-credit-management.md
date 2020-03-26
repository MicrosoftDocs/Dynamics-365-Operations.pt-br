---
title: Gerenciamento de crédito de cliente
description: O gerenciamento de crédito de cliente permite gerenciar limites de crédito e controlar o fluxo de ordens de venda por meio do processo de lançamento com base nas regras de crédito criadas.
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 1e7d3325587d7cfc876e8f8c7b9207d44046ccd4
ms.sourcegitcommit: 1d5a4f70a931e78b06811add97c1962e8d93689b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/13/2020
ms.locfileid: "3124268"
---
# <a name="customer-credit-management-overview"></a>Visão geral de gerenciamento de crédito de cliente

[!include [banner](../includes/banner.md)]

O gerenciamento de crédito de cliente permite gerenciar limites de crédito e controlar o fluxo de ordens de venda por meio do processo de lançamento com base nas regras de crédito criadas. 

O processo para usar o gerenciamento de crédito pode incluir algumas ou todas as seguintes etapas:
- Atualizar clientes com atributos de crédito que forneçam informações adicionais sobre confiabilidade de crédito 
- Criar limites de crédito para os clientes usando ajustes de limite de crédito
- Criar limites de crédito temporários para os clientes usando ajustes de limite de crédito quando você quiser aumentar ou diminuir temporariamente o limite de crédito deles com base nas necessidades comerciais
- Adicionar mais informações que podem afetar o limite de crédito, como seguro e garantias
- Criar grupos de crédito de cliente que vinculem os clientes para que eles possam compartilhar um único limite de crédito
- Atribuir pontuações de risco aos clientes e usar essas pontuações para gerar automaticamente limites de crédito para os clientes usando ajustes de limite de crédito
- Criar regras de bloqueio que colocarão uma ordem em espera durante um ou mais processos de lançamento com base em fatores como risco, condições de pagamento, limites de crédito, valores vencidos e a porcentagem do limite de crédito usado
- Gerenciar uma lista de ordens de venda em espera, revisar os motivos do bloqueio e mitigar os problemas
- Liberar ordens de venda e permitir que elas continuem no processo de lançamento
- Configurar um fluxo de trabalho para gerenciar a aprovação de alterações no limite de crédito e liberações de ordens de venda


<a name="additional-resources"></a>Recursos adicionais
--------
[Configuração de parâmetros de gerenciamento de crédito de cliente](./cm-credit-mgmt-setup.md)

[Informações de configuração de gerenciamento de crédito de cliente](./cm-setup-information.md)

[Adicionar informações de gerenciamento de crédito de um cliente](./cm-add-credit-mgmt-information-customer.md)

[Grupos de crédito de cliente](./cm-customer-credit-groups.md)

[Ajustes de limite de crédito de cliente](./cm-credit-limit-adjustments.md)

[Bloqueios de crédito para ordens de venda](./cm-sales-order-credit-holds.md)

[Tarefas periódicas de gerenciamento de crédito de cliente](./cm-periodic-tasks.md)



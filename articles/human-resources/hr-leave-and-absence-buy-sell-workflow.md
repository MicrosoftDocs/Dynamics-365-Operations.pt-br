---
title: Criar um fluxo de trabalho de solicitação de compra e venda de licenças
description: Cria um fluxo de trabalho de solicitação de compra e venda de licenças para gerenciar as solicitações de licença de compra e venda de forma consistente no Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-08-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3f200fec48dc6bff2702b962c47cbd6951c5921c
ms.sourcegitcommit: 67c4ed957e43d4d60bb609d93921a0be9619e675
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2022
ms.locfileid: "8509406"
---
# <a name="create-a-buy-and-sell-leave-request-workflow"></a>Criar um fluxo de trabalho de solicitação de compra e venda de licenças


>[!Important]
>A funcionalidade mencionada neste tópico está disponível atualmente para clientes individuais de Dynamics 365 Human Resources. Algumas ou todas as funcionalidades estarão disponíveis como parte de uma versão futura na infraestrutura do Finance após a versão Finance 10.0.26.


[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Você pode criar um fluxo de trabalho no Dynamics 365 Human Resources para gerenciar as solicitações de compra e venda de licença de forma consistente. Um fluxo de trabalho **Comprar e vender licença** permite:

- Definir tarefas
- Determinar quem deve concluir as tarefas
- Especificar quem pode aprovar ou rejeitar solicitações

## <a name="create-a-buy-and-sell-leave-request-workflow"></a>Criar um fluxo de trabalho de solicitação de compra e venda de licenças

1. Na página **Licença e ausência**, selecione a guia **Links**.

2. Em **Configuração**, selecione **Fluxos de trabalho de recursos humanos**.

3. Selecione **Novo** e **Solicitação de compra e venda de licença**. 

4. Quando aparecer a caixa de mensagem **Abrir este arquivo?**, selecione **Abrir** e faça login com as credenciais da sua empresa.

5. Use o editor de fluxo de trabalho para criar um fluxo de trabalho para suas solicitações de licença. Para obter mais informações sobre como trabalhar com fluxos de trabalho, consulte [Visão geral de criação de fluxos de trabalho](../fin-ops-core/fin-ops/organization-administration/create-workflow.md?toc=%2fdynamics365%2fcommerce%2ftoc.json.)

## <a name="leave-and-absence-request-workflow-data-elements"></a>Elementos de dados de fluxo de trabalho de solicitação de licenças e ausências

Você pode usar os elementos de dados a seguir para criar aprovações condicionais ou automáticas em fluxos de trabalho para solicitações de compra e venda de licença:

- **Valor**
- **Política de compra e venda de licenças**
- **Empresa**
- **Criado por**
- **Data e hora de criação**
- **Data de término**
- **Tipo de licença**
- **Modificação de**
- **Data e hora da modificação**
- **ID da Solicitação**
- **Data inicial:**
- **Status** 
- **Data de envio**
- **Envio feito por**
- **Enviado pelo Recursos Humanos**
- **Enviado pelo gerente**
- **Enviado em nome de**
- **Trabalhador**

## <a name="workflow-examples"></a>Exemplos de fluxo de trabalho

Esses exemplos mostram como é possível criar diferentes tipos de condições de fluxo de trabalho usando esses elementos de dados:

- Use **Enviado pelo Recursos Humanos** e **Enviado pelo gerente** em uma ação automática para aprovar automaticamente solicitações de compra e venda de licença que essas funções enviam em nome dos funcionários. Para obter mais informações sobre ações automáticas, consulte [Configurar processos de aprovação em um fluxo de trabalho](../fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow.md).

- Use o **Tipo de licença** em uma instrução condicional ou ação automática para controlar como o fluxo de trabalho encaminha solicitações com certos tipos de licença.

## <a name="see-also"></a>Consulte também

[Visão geral de licença e ausência](hr-leave-and-absence-overview.md)<br>
[Gerenciar políticas de compra e venda de licenças](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)<br>
[Comprar e vender licenças](hr-employee-self-service-buy-sell-leave.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]

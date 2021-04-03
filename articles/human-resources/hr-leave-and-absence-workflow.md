---
title: Criar um fluxo de trabalho de solicitação de licença
description: Crie um fluxo de trabalho de solicitação de licença e ausência para gerenciar as solicitações de licença consistentemente no Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 05/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c2c2020c68c4aca3594a2532d32f968ab76f6b7b
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5463301"
---
# <a name="create-a-leave-request-workflow"></a>Criar um fluxo de trabalho de solicitação de licença

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Você pode criar um fluxo de trabalho no Dynamics 365 Human Resources para gerenciar as solicitações de licença e ausência de forma consistente. Um fluxo de trabalho de **Licença e ausência** permite:

- Definir tarefas
- Determinar quem deve concluir as tarefas
- Especificar quem pode aprovar ou rejeitar solicitações

## <a name="create-a-leave-and-absence-request-workflow"></a>Criar um fluxo de trabalho de solicitação de licenças e ausências

1. Na página **Licença e ausência**, selecione a guia **Links**.

2. Em **Configuração**, selecione **Fluxos de trabalho de recursos humanos**.

3. Selecione **Novo** e **Solicitação de licença e ausência**. 

4. Quando aparecer a caixa de mensagem **Abrir este arquivo?**, selecione **Abrir** e faça login com as credenciais da sua empresa.

5. Use o editor de fluxo de trabalho para criar um fluxo de trabalho para suas solicitações de licença. Para obter mais informações sobre como trabalhar com fluxos de trabalho, consulte [Visão geral de criação de fluxos de trabalho](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/create-workflow?toc=/dynamics365/commerce/toc.json.)

## <a name="leave-and-absence-request-workflow-data-elements"></a>Elementos de dados de fluxo de trabalho de solicitação de licenças e ausências

Você pode usar os elementos de dados a seguir para criar aprovações condicionais ou automáticas em fluxos de trabalho para solicitações de licença e ausência:

- **Valor**
- **Comentário**
- **Empresa**
- **Criação de**
- **Data e hora de criação**
- **Data Final**
- **Tipo de licença**
- **Modificação de**
- **Data e hora da modificação**
- **Código do motivo**
- **ID da Solicitação**
- **Data inicial**
- **Status** 
- **Data de envio**
- **Envio feito por**
- **Enviado pelo Recursos Humanos**
- **Enviado pelo gerente**
- **Enviado em nome de**
- **Trabalhador**
- **Tipo de trabalhador**

Esses exemplos mostram como é possível criar diferentes tipos de condições de fluxo de trabalho usando esses elementos de dados:

- Use o **Código do motivo** em uma instrução condicional para rotear solicitações de licença de doença com o código de motivo **Cirurgia** para HR para aprovação, enquanto roteia todos os outros códigos de motivo para o gerente. Para obter mais informações sobre instruções condicionais, consulte [Configurar decisões condicionais em um fluxo de trabalho](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-conditional-decision-workflow). 

- Use **Enviado por Human resources** e **Enviado pelo gerente** em uma ação automática para aprovar automaticamente solicitações de licença que essas funções submetem em nome dos funcionários. Para obter mais informações sobre ações automáticas, consulte [Configurar processos de aprovação em um fluxo de trabalho](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow).

- Use o **Tipo de licença** em uma instrução condicional ou ação automática para controlar como o fluxo de trabalho encaminha solicitações com certos tipos de licença.

## <a name="see-also"></a>Consulte também

- [Visão geral de licença e ausência](hr-leave-and-absence-overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
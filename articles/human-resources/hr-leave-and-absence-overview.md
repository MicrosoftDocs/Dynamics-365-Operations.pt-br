---
title: Visão geral
description: ''
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9a36f6b6ba696fa926ab3d6298568dddfce43a57
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008132"
---
# <a name="overview"></a>Visão geral

O Dynamics 365 Human Resources ajuda a fornecer excelentes benefícios de licença para seus funcionários. O **espaço de trabalho** de licença e ausência fornece uma estrutura flexível para a criação de novos planos de licenças, de fluxos para gerenciar solicitações e uma página de auto-atendimento intuitiva para que os funcionários solicitem folga. Ajudar a organização a medir e monitorar os saldos de licenças e o uso de seus planos de licenças.

## <a name="set-up-leave-and-absence"></a>Configurar licenças e ausências

Antes de poder criar planos de licença para seus funcionários, você precisará executar algumas etapas de configuração:

- [Configurar parâmetros de licença e ausência](hr-leave-and-absence-parameters.md)
- [Criar um calendário de horas úteis](hr-leave-and-absence-working-time-calendar.md)
- [Criar um fluxo de trabalho de solicitação de licença](hr-leave-and-absence-workflow.md)

## <a name="create-and-manage-leave-plans"></a>Criar e gerenciar planos de licenças

Antes de criar planos de licença para seus trabalhadores, você precisará criar tipos de licença e ausência. Depois de criar um plano de licença, você pode inscrever trabalhadores no plano. Você também pode executar o processo de acúmulo, criar alertas e exibir análises para seus planos.

- [Configurar tipos de licença e ausência](hr-leave-and-absence-types.md)
- [Criar um plano de licença e ausência](hr-leave-and-absence-plans.md)
- [Atribuir trabalhadores a um plano de licença](hr-leave-and-absence-enroll.md)
- [Acumular planos de licença e ausência](hr-leave-and-absence-accrue.md)
- [Exibir análises de licenças e ausências](hr-leave-and-absence-analytics.md)

## <a name="request-time-off-and-manage-requests"></a>Solicitação de tempo e gerenciar solicitações

Seus funcionários podem enviar solicitações de folga e você pode gerenciá-los no espaço de trabalho **Autoatendimento para funcionários**.

- [Solicitar folga](hr-employee-self-service-request-time-off.md)
- [Gerenciar solicitações de licença e ausência](hr-employee-self-service-manage-requests.md)

## <a name="leave-and-absence-preview-features"></a>Recursos de visualização de licenças e ausências

Você pode experimentar novos recursos de licença e visualização de ausência em **um** ambiente de área restrita. Para obter mais informações sobre os recursos de visualização, consulte [Gerenciar recursos](hr-admin-manage-features.md). Os recursos de visualização incluem:

- **Calendário de licenças e ausências da empresa** - Os parâmetros de licença e ausência moverão de **Parâmetros de recursos humanos** a uma nova tela chamada **Parâmetros de licença e ausência**. A nova tela inclui uma nova guia **Calendário**. Esta visualização habilita apenas um subconjunto dos parâmetros. Você pode acessar a nova tela na guia **Links** do espaço de trabalho **Licença e ausência**. Os calendários incluem:
  - **Calendário da empresa** - mostra todas as solicitações de tempo limite do funcionário. As pessoas com a função **Human resources** podem acessar este calendário na guia **Links** da área de trabalho **Licença e ausência**.
  - **Calendário da equipe do gerente** - mostra todas as solicitações de tempo limite dos relatórios diretos. Os gerentes podem acessar o calendário da guia **Minha equipe** no auto-atendimento para funcionários em **Licença e ausência**. 

- **Calendários de férias e ausências** - Os tipos de licença incluem uma nova opção de **Feriado**, usada em conjunto com o calendário de horário de trabalho. Os dias definidos por feriados e recessos agora são designados como **Feriado** quando os dias de trabalho são gerados. Quando as competências são processadas, os ajustes são feitos aos funcionários atribuídos ao calendário para contabilizar os feriados que ocorrem em um dia útil.

- **Manter auditoria de acumulação** - Uma nova tela permite que você examine quando as competências foram processadas e excluídas, ambas por funcionários e funcionários individuais. Você pode acessar essa nova tela na guia **Links** do espaço de trabalho **Licença e ausência**.

- **Manter exclusão da competência** - Você pode excluir registros de competência para planos de licença específicos. Você pode acessar essa nova opção na guia **Links** do espaço de trabalho **Licença e ausência**. Para funcionários individuais, esta opção aparece no agrupamento de **Licenças e ausências** no perfil do funcionário. 

- **Arredondamento de acúmulos de licença** - Novas opções para **Tipo de licença** definem qual tipo de arredondamento de acúmulos deve ser usado, mais a precisão decimal do arredondamento durante o processo de acumulação. Quando as competências são processadas, o arredondamento e a precisão são aplicados aos registros de competência. 

- **Configurar vários tipos de licença em um único plano de licença** - Uma nova coluna no plano de acumulação de licença para tipos de licença permite definir vários tipos de licença em um planejamento de licença e ausência com diferentes agendas de competência. O campo **Tipo de licença** anterior é removido. Na inscrição do funcionário, os saldos para os tipos de licença agora são exibidos em uma tabela em vez de na parte superior da tela.

  > [!IMPORTANT]
  > Não é possível desativar esse recurso após ativá-lo.

- **Use a equivalência de horário integral de um funcionário (FTE) para acumular** - Uma nova coluna na agenda de acumulação de licença permite o uso de FTE para acumulação. Quando as competências são processadas, o aplicativo usa a posição principal do funcionário e a FTE definida para determinar o valor acumulado rateado.

  > [!NOTE]
  > Este recurso só estará disponível se você habilitar **Configurar vários tipos de licença por licença**. 

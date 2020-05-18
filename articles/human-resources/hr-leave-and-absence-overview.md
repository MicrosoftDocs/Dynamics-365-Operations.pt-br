---
title: Visão Geral
description: Em Dynamics 365 Human Resources, o espaço de trabalho de licença e ausência fornece uma estrutura flexível para a criação de novos planos de licenças, fluxos para gerenciar solicitações e uma página de auto-atendimento intuitiva para que os funcionários solicitem licença.
author: andreabichsel
manager: AnnBe
ms.date: 04/30/2020
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
ms.openlocfilehash: 2bb123b808615ff7d770c7c6b83338a32d922be3
ms.sourcegitcommit: de217452a85429675994e9cc0e06eb4821cab3e5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2020
ms.locfileid: "3325756"
---
# <a name="overview"></a>Visão Geral

O Dynamics 365 Human Resources ajuda a fornecer excelentes benefícios de licença para seus funcionários. O **espaço de trabalho** de licença e ausência fornece uma estrutura flexível para a criação de novos planos de licenças, de fluxos para gerenciar solicitações e uma página de auto-atendimento intuitiva para que os funcionários solicitem folga. Ajudar a organização a medir e monitorar os saldos de licenças e o uso de seus planos de licenças.

## <a name="set-up-leave-and-absence"></a>Configurar licenças e ausências

Antes de criar planos de licença para seus funcionários, você precisará executar algumas etapas de configuração:

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

## <a name="leave-and-absence-known-issues"></a>Problemas conhecidos de licença e ausência

### <a name="rounding-precision"></a>Precisão de arredondamento

Não é possível definir a **Precisão do arredondamento** ao definir o **Tipo de arredondamento**. Você só pode definir a **Precisão de arredondamento** usando a entidade **Tipo de licença e ausência**. 

1. Em **Tipos de licença e ausência**, selecione **Abrir no Excel** para abrir a entidade **Tipo de licença e ausência**.

2. Depois que o arquivo abrir e estiver habilitado, selecione **Design**.

3. Na tabela **Tipo de licença e ausência**, selecione a opção de lápis a ser editada.

4. Selecione **RoundingPrecision** e **RoundingType** e depois selecione **Adicionar** para adicionar à lista de campos.

5. Selecione **Atualizar** e, depois, **Concluído**.

6. Insira ou selecione o tipo **Tipo de arredondamento** para cada tipo de licença se ainda não tiver sido definido. 

7. Insira a **Precisão de arredondamento** para os tipos apropriados.

8. Selecione **Publicar** para forçar as alterações em Human Resources.

## <a name="leave-and-absence-preview-features"></a>Recursos de visualização de licenças e ausências

Você pode experimentar novos recursos de licença e visualização de ausência em **um** ambiente de área restrita. Para obter mais informações sobre os recursos de visualização, consulte [Gerenciar recursos](hr-admin-manage-features.md). 

[!include [banner](includes/preview-feature.md)]

Os recursos de visualização incluem:

- **Suspensão da licença** - Você pode suspender a licença e a ausência em Human Resources para um funcionário. Suspender licença interrompe a acumulação de licenças de licença para os tipos de licença selecionados. Se a suspensão ocorrer depois de um processo de acumulação, a suspensão da licença cria um ajuste rateado para o saldo de licença do funcionário. Você também pode incluir códigos de motivo ao suspender a licença de um funcionário. A experiência do usuário foi atualizada para indicar suspensão. 

- **Regras de postergação** - Você pode especificar um tipo de licença postergada para saldos postergados nos quais ajustes postergados são transferidos. Por exemplo, se um funcionário adianta 10 dias, você pode escolher um tipo de licença diferente para esses 10 dias. 

- **Incluir código de motivo e comentários para ajustes** - é possível incluir um código de motivo e um comentário ao fazer um ajuste ao saldo da licença de um funcionário. 

- **Transição para parâmetros de licença e de ausência** - é possível usar agora somente parâmetros de licença e ausência em vez de usar parâmetros de Human Resources. 

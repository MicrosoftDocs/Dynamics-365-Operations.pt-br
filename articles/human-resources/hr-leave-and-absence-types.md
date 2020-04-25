---
title: Configurar tipos de licença e ausência
description: Configurar tipos de licença que os funcionários podem executar no Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 04/01/2020
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
ms.openlocfilehash: df6e34fe6a23e6f0a8307a035752a35a15a3431c
ms.sourcegitcommit: 79f8aa2c0b166a423db9b8503da53e96e3fc43dc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2020
ms.locfileid: "3198041"
---
# <a name="configure-leave-and-absence-types"></a>Configurar tipos de licença e ausência

Os tipos de licenças no Dynamics 365 Human Resources definem os tipos de ausências que os funcionários podem relatar. Você pode personalizar os tipos de licença de acordo com as necessidades da sua organização. Exemplos de tipos de licença incluem:

- Folga remunerada (PTO)
- Licença não remunerada
- Férias remuneradas
- Ausência por motivo de doença
- Licença médica
- Licença de família
- Incapacidade temporária
- Licença óbito

## <a name="add-a-leave-type"></a>Adicionar um tipo de licença

1. Na página **Licença e ausência**, selecione a guia **Links**.

2. Em **Configuração**, selecione **Tipos de licença e ausência**.

3. Selecione **Novo**.

4. Digite um nome para o tipo de licença em **Tipo**, selecione um fluxo de trabalho em **ID do fluxo de trabalho** e digite uma descrição em **Descrição**.

5. Em **Geral**, selecione **Nenhum**, **Agendado** ou **Não agendado** no menu suspenso **Categoria**.

6. Selecione um código de ganhos no menu suspenso **Código de ganhos**.

7. Em **Código de motivo obrigatório**, escolha se deseja exigir um código de motivo. Se desejar exigir códigos de motivo, talvez seja necessário adicioná-los. Em **Códigos de motivo**, selecione **Adicionar**, selecione um código de motivo e marque a caixa de seleção **Habilitado** ao lado dele.

8. Em **Restringir acesso a funções selecionadas**, escolha se deseja restringir o acesso. Em seguida, selecione as funções de segurança em **Funções de segurança para este tipo de licença**. As funções de segurança são definidas no fluxo de trabalho selecionado em **ID do fluxo de trabalho**, que vimos antes neste procedimento.

9. Selecione **Salvar**.

## <a name="configure-leave-type-rules"></a>Configurar regras de tipo de licença

1. Defina as opções de arredondamento para o tipo de licença. As opções incluem **Nenhum**, **Para cima**, **Para baixo** e **Mais próximo**. Você também pode definir a precisão de arredondamento para o tipo de licença.

2. Defina a **Correção de feriado** para o tipo de licença. Quando você seleciona esta opção, o Human Resources usa o número de feriados que caem em um dia útil para determinar como acumular folgas para o tipo de licença. Por exemplo, se o dia de Natal cair na segunda-feira, o Human Resources subtrairá um dia do tipo de licença ao processar competências.

   Você pode definir feriados no calendário de horário de trabalho. Para obter mais informações, consulte [Criar um calendário de horário de trabalho](hr-leave-and-absence-working-time-calendar.md)
   
## <a name="configure-preview-features"></a>Configure recursos de visualização

Se tiver habilitado recursos de visualização para licença e ausência, você também precisará definir configurações para eles.

[!include [banner](includes/preview-feature-leave-absence.md)]

1. Escolha o tipo de licença para os saldos postergados a serem transferidos. Você também pode criar um novo tipo de licença para postergar. 

## <a name="see-also"></a>Consulte também

- [Visão geral de licença e ausência](hr-leave-and-absence-overview.md)
- [Criar um plano de licença e ausência](hr-leave-and-absence-plans.md)
- [Criar um calendário de horas úteis](hr-leave-and-absence-working-time-calendar.md)

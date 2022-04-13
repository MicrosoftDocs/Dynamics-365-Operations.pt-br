---
title: Criar um calendário de horário de trabalho
description: Defina um calendário de horário de trabalho, feriados e horário não comercial no Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/28/2021
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
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 163d7caf516d791fa54e2518d19798bdf3d58d3d
ms.sourcegitcommit: 67c4ed957e43d4d60bb609d93921a0be9619e675
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2022
ms.locfileid: "8509602"
---
# <a name="create-a-working-time-calendar"></a>Criar um calendário de horário de trabalho


> [!Important]
> A funcionalidade mencionada neste tópico está disponível atualmente para clientes individuais de Dynamics 365 Human Resources. Algumas ou todas as funcionalidades estarão disponíveis como parte de uma versão futura na infraestrutura do Finance após a versão Finance 10.0.26.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Um calendário de horário de trabalho no Dynamics 365 Human Resources mostra os dias e as horas em que os funcionários trabalham na sua organização. Quando um funcionário envia uma solicitação de folga, ele não precisa se preocupar com feriados e recessos.

Para simplificar as solicitações de folga, configure estes itens na organização:

- Calendário de horário de trabalho
- Feriados e recessos
- Horário não comercial

Você poderá adicionar os dois últimos itens enquanto estiver configurando um calendário de horário de trabalho. Você também pode configurá-los ou atualizá-los separadamente.

## <a name="set-up-a-working-time-calendar"></a>Configure um calendário de horário de trabalho

Configure pelo menos um calendário de horário de trabalho que mostre os dias e as horas de operação. Se você tiver locais em vários países e regiões, talvez queira configurar um calendário de produção para cada área.

1. Na página **Administração da organização**, selecione **Calendários**.

2. Selecione **Novo** e digite um nome e uma descrição para seu calendário.

3. Em **Opções de geração**, selecione os dias de trabalho da sua organização e insira os horários de trabalho. 
   - Para adicionar um feriado ou um recesso, selecione o botão **Adicionar** ao lado de **Feriados e recessos**.
   - Para adicionar um período não útil, como almoços ou pausas, selecione **Adicionar** em **HORÁRIO NÃO COMERCIAL** e insira o nome e o intervalo de tempo.

4. Em **Dias** , selecione **Gerar** para gerar os dias no calendário. Insira o intervalo de datas para o calendário e selecione **Gerar dias**.

5. Para adicionar agendas de trabalho, em **Agenda de trabalho**, selecione **Adicionar** e insira os horários de cada plano de trabalho.

## <a name="configure-holidays-and-closures"></a>Configurar feriados e recessos

Você pode adicionar ou alterar feriados e recessos separadamente de um calendário de horário de trabalho.

1. Na página **Administração da organização**, selecione **Feriados e recessos**.

2. Selecione **Novo** e digite um nome e uma data para o feriado ou recesso.

## <a name="configure-non-work-time"></a>Configurar horário não comercial

Você pode adicionar ou alterar horários não comerciais separadamente de um calendário de horário de trabalho.

1. Na página **Administração da organização**, selecione **HORÁRIO NÃO COMERCIAL**.

2. Selecione **Novo** e insira um nome e o intervalo de tempo para o horário não comercial.

Se você tiver habilitado o recurso de visualização de correções de feriados no banco de licenças e ausências, o Human Resources usará feriados e recessos para determinar o número de dias a serem ajustados para os funcionários inscritos no calendário.

## <a name="see-also"></a>Consulte também

- [Visão geral de licença e ausência](hr-leave-and-absence-overview.md)
- [Configurar tipos de licença e ausência](hr-leave-and-absence-types.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

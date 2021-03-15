---
title: Criar um calendário de horário de trabalho
description: Defina um calendário de horário de trabalho, feriados e horário não comercial no Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 04/01/2020
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
ms.openlocfilehash: ccf7901ebbea655b7f795a48944c6f03f9cf210a
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2021
ms.locfileid: "5115093"
---
# <a name="create-a-working-time-calendar"></a>Criar um calendário de horário de trabalho

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

1. Na página **Administração da organização**, selecione **Horário não comercial**.

2. Selecione **Novo** e insira um nome e o intervalo de tempo para o horário não comercial.

Se você tiver habilitado o recurso de visualização de correções de feriados no banco de licenças e ausências, o Human Resources usará feriados e recessos para determinar o número de dias a serem ajustados para os funcionários inscritos no calendário.

## <a name="see-also"></a>Consulte também

- [Visão geral de licença e ausência](hr-leave-and-absence-overview.md)
- [Configurar tipos de licença e ausência](hr-leave-and-absence-types.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
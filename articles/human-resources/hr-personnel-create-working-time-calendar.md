---
title: Criar calendários e gerar horários de trabalho
description: Os calendários descrevem a capacidade e os horários de trabalho dos recursos de operações. Este artigo explica como definir um calendário de trabalho com base no modelo de horário de trabalho.
author: andreabichsel
manager: tfehr
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OpResLifeCycleManagementWorkspace, WorkCalendarTable, WorkCalendarDate, HcmPersonnelManagementWorkspace, WrkCtrGroupDateCalendar, WrkCtrDateCalendar
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: af2675468dcc1f1891d24d988c32115ae57e1d2b
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465453"
---
# <a name="create-calendars-and-generate-working-times"></a>Criar calendários e gerar horários de trabalho

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Os calendários descrevem a capacidade e os horários de trabalho dos recursos de operações. Este artigo explica como definir um calendário de trabalho com base no modelo de horário de trabalho. Você pode ver todo esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.

1. Na home page, selecione **Gerenciamento do ciclo de vida de recurso**.
2. Selecione **Calendários**.
3. Selecione **Novo**.
4. No campo **Calendário**, classifique o seu calendário. Este é o ID do calendário, que é usado como uma referência ao atribuir calendários, como um recurso de operações ou um grupo de recursos.  
5. No campo **Nome**, nomeie seu calendário.
6. No campo **Dia de trabalho padrão em horas**, insira um número.
7. Verifique se a linha está selecionada e marque **Horários de trabalho** no painel de Ação.
8. Selecione **Compor horários de trabalho**. Gera horas de trabalho para cada dia no período que você quer agendar o trabalho. Conforme o tempo passa, você pode gerar horários de trabalho para períodos adicionais.  
9. No campo **Data inicial**, insira uma data. Esse é o primeiro dia que este calendário deve ficar aberto.  
10. No campo **Data final**, insira uma data. Esse é o último dia que este calendário deve está aberto.  
11. No campo **Modelo de horário de trabalho**, insira ou selecione um valor. O modelo de horário de trabalho define as horas de trabalho para cada dia da semana.  
12. Selecione **OK**.
13. Feche a página.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
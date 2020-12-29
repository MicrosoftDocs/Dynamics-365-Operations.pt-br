---
title: Calendários de horário de trabalho
description: Este tópico descreve os calendários de produção no Dynamics 365 Human Resources e como configurá-los.
author: andreabichsel
manager: AnnBe
ms.date: 09/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-07-01
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.openlocfilehash: e77cc8921f2a8cfa1a48fda589fd20aae00e0fd4
ms.sourcegitcommit: 53174ed4e7cc4e1ba07cdfc39207e7296ef87c1f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/07/2020
ms.locfileid: "4690067"
---
# <a name="working-time-calendars"></a>Calendários de horário de trabalho

O calendário de produção permite que você crie um calendário com as horas e os dias em que os funcionários trabalham na sua organização. Os calendários simplificam o processo de solicitação de folga por padrão em horas ou em dias. Quando um funcionário envia uma solicitação de folga, ele não precisa se preocupar com feriados e fechamentos, que são processados para eles pelo calendário de produção.

## <a name="setting-up-a-working-time-calendar"></a>Configuração de um calendário de produção

Os calendários incluem detalhes da geração, os dias e as horas que você deseja que sejam incluídos, os dias do calendário, os períodos de trabalho para esses dias e funcionários inscritos. 

Para configurar um calendário, siga essas etapas:

1. Na página **Administração da Organização**, clique em **Calendários**.

2. No Painel de Ações, selecione **Novo** e digite um nome e uma descrição.

3. Escolha os dias de trabalho para sua organização e insira o período de trabalho.

4. Adicione feriados e fechamentos usando o botão **Adicionar**.

5. Insira o nome e a descrição dos feriados e fechamentos, como feriados nacionais ou bancários. Insira as datas para os feriados e fechamentos. Salve a lista de feriados e fechamentos e feche a página.

6. Selecione os feriados e fechamentos no menu suspenso.

7. Se seus funcionários têm horários não comerciais, como almoços ou intervalos, adicione-os também. Selecione **Horário não comercial** e insira o nome e o intervalo de tempo. Feche a página. 

8. Clique em **Adicionar** para adicionar o horário não comercial ao calendário.

9. Na guia **Dias** , selecione **Gerar** para gerar os dias no calendário. Insira o intervalo de datas para o calendário. Os dias e os períodos de trabalho são gerados com base nos dias e períodos de trabalho definidos nas opções da geração em conjunto com as datas selecionadas.

10. Para atribuir um calendário a funcionários, selecione **Atribuir a funcionários** no Painel de Ações. Selecione os funcionários aos quais você deseja atribuir esse calendário e clique em **Atribuir**.

Não é necessário que os funcionários tenham calendários atribuídos. Se houver um calendário de produção definido, os dias de folga serão automaticamente excluídos da solicitação. A quantidade, em dias ou em horas, é definida como padrão para períodos de trabalho definidos no calendário. Caso um funcionário não tenha um calendário atribuído, todos os dias estão disponíveis para folga, e o período de folga não é o padrão da solicitação. 

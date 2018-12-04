---
title: "Calendários de horário de trabalho"
description: "Este tópico descreve os calendários de produção no Dynamics 365 for Talent - Core HR e como configurar calendários."
author: jcart1106
manager: AnnBe
ms.date: 09/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2018-07-01
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 1bf37d65cd8ce6a98fc2d2fb11ae9587cf6958a3
ms.openlocfilehash: 2465065d7db18a5468d7c979e0d6cb9c7e76f969
ms.contentlocale: pt-br
ms.lasthandoff: 09/27/2018

---

# <a name="working-time-calendars"></a>Calendários de horário de trabalho

[!include [banner](includes/banner.md)]

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


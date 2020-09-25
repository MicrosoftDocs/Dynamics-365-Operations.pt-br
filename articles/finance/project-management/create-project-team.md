---
title: Criar uma equipe de projeto
description: Este tópico fornece informações sobre como criar e gerenciar equipes de projeto.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 834a6c0a4fcc32a955c1feddf0a6cbbb1f16b869
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760474"
---
# <a name="create-a-project-team"></a>Criar uma equipe de projeto

[!include [banner](../includes/banner.md)]

Para usar as funções que foram configuradas previamente em um projeto, um gerente de projeto deve associar as funções ao projeto. As diversas funções podem ser atribuídas para um projeto. Para evitar confusão, essas funções são rotuladas automaticamente durante a reserva. Por exemplo, se o gerente de projeto quiser três engenheiros de software, três funções de engenheiro de software que têm **engenheiro de software 1**, **engenheiro de software 2** e **engenheiro de software 3** como rótulos, são gerados automaticamente. Se as características da função tiverem sido definidas anteriormente para a função, elas serão aplicadas como um filtro durante a pesquisa de recursos. Características adicionais podem ser adicionadas conforme necessário para refinar ainda mais a pesquisa.

As configurações de exibição também podem ser personalizadas para fornecer uma visão melhor de disponibilidade de capacidade. Há opções para mostrar a disponibilidade por hora, por dia, por semana, por mês, por trimestre e por ano. Há também uma opção para mostrar a capacidade disponível e restante dos recursos. Essa opção é útil para o gerenciamento de tempo, quando você estiver estimando as horas disponíveis para atividades ou a disponibilidade de capacidade.

O gerente de projeto pode selecionar uma função na página e, se houver um recurso disponível de acordo com a necessidade, selecionar para reservar um recurso para preencher a função. Observe que os recursos não precisam ser reservados nesse momento na fase de planejamento. Quando você cria um WBS, pode substituir funções pelos recursos recrutados do projeto. Se as funções forem substituídas pelos recursos recrutados no WBS, a configuração do recurso atualiza automaticamente a listagem e o agendamento da equipe do projeto.

[![Listagem da equipe de projeto que inclui as funções e os recursos reais](./media/projectresourcing03-1024x368.jpg)](./media/projectresourcing03.jpg) 

O gerente de projeto tem diversas opções para reservar um recurso para um projeto, como **Capacidade restante**, **Capacidade total**, **Porcentagem da capacidade** e **Especificar horas**. Essas opções de reserva poderão ser canceladas a qualquer momento se as atribuições de recursos forem alterados. Há dois tipos de reserva com suporte:

- **Reserva fixa** – A reserva de recursos foi aprovada e confirmada para trabalhar no compromisso pela duração especificada.
- **Reserva flexível** – As reservas de recursos foram definidas como uma tentativa para trabalhar no compromisso pela duração especificada.

O procedimento a seguir explica como criar uma equipe de projeto.

## <a name="create-a-project-team"></a>Criar uma equipe de projeto

1. Na página de lista **Todos os projetos**, selecione um projeto e selecione **Editar**.
2. Na guia **Equipe e agendamento de projeto**, no campo **Data final da agenda**, insira a data inicial da agenda mais um mês. Por exemplo, se a data de início da agenda for 24 de junho de 2017 (24/06/2017), insira **24/07/2017**.
3. Selecione **Adicionar**.
4. No painel **Adicionar funções ao projeto**, no campo **Função**, selecione **Gerente de projeto sênior**.
5. Selecione **Competências necessárias**.
6. Na página **Escolher características**, as características que você definiu anteriormente para a função Gerente de projeto sênior estarão selecionadas por padrão. Selecione **OK**.
7. Na página **Adicionar funções ao projeto**, no campo **Número de recursos**, insira **1**.
8. No campo **Recurso**, a consulta mostra todos os recursos que têm as competências necessárias. Selecione **Daniel Goldschmidt** e selecione **Criar**.
9. Na página **Projeto**, selecione **Adicionar**.
10. No painel **Adicionar funções ao projeto**, no campo **Função**, selecione **Membro de equipe**. No campo **Número de recursos**, insira **5**.
11. Selecione **Criar**.
12. Na página **Projetos**, selecione **Preencher recurso**.

## <a name="monitor-project-teams"></a>Monitorar equipes de projeto
1. Na página **Todos os projetos**, selecione o link **ID do projeto** para o projeto **Fase de atualização 2 de XYZ**.
2. Na Guia Rápida **Equipe de projeto e agendamento**, verifique se os recursos de projetos listados estão corretos.

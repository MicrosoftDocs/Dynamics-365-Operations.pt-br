---
title: Distribuir e planejar questionários
description: Este tópico explica como distribuir os questionários criados por você, de modo que sejam disponibilizados para a pessoa ou grupo de pessoas que os preencherão.
author: andreabichsel
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: KMConnectionType, KMKnowledgeCollectorPlanningTabel, SysEmailParameters
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 17424
ms.assetid: fd8d867a-2446-400a-b91f-ad4085427470
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1e0369be278519f39fc304b34ef3a270438f0bb1
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/24/2019
ms.locfileid: "2026247"
---
# <a name="distribute-and-schedule-questionnaires"></a>Distribuir e planejar questionários

[!include [banner](includes/banner.md)]

Este tópico explica como distribuir os questionários criados por você, de modo que sejam disponibilizados para a pessoa ou grupo de pessoas que os preencherão. 

Há várias formas de distribuir um questionário:

-   Marcar o questionário como ativo. O questionário é disponibilizado a todos os funcionários, a menos que um grupo de questionários esteja configurado para restringir o acesso ao questionário.
-   Atribuir direitos a um grupo de questionários. O questionário ficará disponível a todos os membros do grupo selecionado.
-   Criar sessões de resposta planejadas. O questionário está disponível a apenas uma pessoa em particular.
-   Criar uma agenda. O questionário poderá estar disponível para vários contatos.

## <a name="marking-a-questionnaire-as-active"></a>Marcar um questionário como ativo
Configurando o campo **Ativo** como **Sim** na página **Questionários**, você disponibiliza o questionário para todos os funcionários preencherem. Os respondentes poderão preencher o questionário várias vezes. Essa funcionalidade será útil se você quiser obter feedback contínuo durante todo o ano. Por exemplo, você pode fazer um questionário que os funcionários usam para fornecer feedback sobre o serviço de almoço no bar.

## <a name="questionnaire-groups"></a>Grupos de questionários
Você pode configurar grupos de questionário e incluir os participantes para os quais um questionário deve ser distribuído. 

Você pode criar grupos de questionário das seguintes páginas:

-   **Grupos de questionários**– Somente os indivíduos em um grupo de questionário podem preencher um questionário selecionado. Por exemplo, se o público-alvo é prestadores de serviço, você pode criar um grupo de questionário que é específico para esses entrevistados.
-   **Membros do grupo de questionário** – Você pode adicionar pessoas aos grupos de questionários.

Para atribuir um grupo de questionários a um questionário, na página **Questionário**, clique em **Direitos do usuário**. Depois que o questionário foi salvo como ativo, os membros do grupo de questionário podem preencher o questionário. Essa funcionalidade será útil se você quiser testar um questionário em um grupo seleto de pessoas antes de enviá-lo para um grupo maior, ou se você quiser direcionar um questionário para um público muito específico.

## <a name="planned-answer-sessions-in-a-questionnaire"></a>Sessões de respostas planejadas em um questionário
As sessões de respostas planejadas são os questionários para os quais você criou e selecionou os participantes. 

> **Observação** Antes de configurar as sessões de respostas planejadas, você deverá criar um questionário. 

N página **Sessão de respostas planejadas**, é possível criar uma sessão de resposta planejada para um funcionário individual. A lista na página exibe todos os questionários planejados. 

As sessões de respostas planejadas também são usadas na página **Agendas de questionário**, onde é possível planejar questionários para diversas pessoas:

-   Funcionários
-   Participantes do curso
-   Unidades organizacionais

Cada pessoa pode responder ao questionário apenas uma vez.

## <a name="scheduling-a-questionnaire"></a>Planejando um questionário
Como opção, você pode planejar um questionário para vários participantes.

### <a name="planning-types"></a>Tipos de planejamento

Os tipos de planejamento são necessários se você desejar agendar sessões de respostas planejadas para vários entrevistados. Os tipos de plano são usados para classificar planos de questionário. Por exemplo, você pode planejar questionários para as seguintes finalidades:

-   Avaliação
-   Pesquisa
-   Testando

Você pode especificar tipos de plano para um plano de questionário na página **Agendas de questionário**.

### <a name="reference-types-for-questionnaire"></a>Tipos de referência para o questionário

É possível usar tipos de referência para inserir critérios para os entrevistados que você pode selecionar ao planejar um questionário. 

Use a página **Tipos de referência** para configurar os tipos de referência para um questionário. Cada tipo de referência corresponde a uma tabela do Microsoft Dynamics 365 Finance. A o criar planos de questionários, você pode especificar os registros individuais na tabela ou um intervalo de registros ao qual o questionário será associado. 

Por exemplo, se você selecionar a tabela Cursos, poderá decidir qual curso específico para o qual será o questionário. Ao configurar uma referência para a tabela Cursos, alguns campos e botões na página **Cursos** se tornam disponíveis.

### <a name="questionnaire-schedules"></a>Agendas de questionários

Você pode usar agendas de questionário para gerar várias sessões de resposta planejadas para um grupo de usuários, com base em um tipo de referência. Criar uma agenda na página **Agendas de questionários**. Selecione o tipo de planejamento para categorizar a agenda e também selecione o tipo de referência que deve ser usado para consultar o sistema para usuários específicos. Por exemplo, se definir o tipo de referência para a tabela Cursos, você pode selecionar um curso específico no campo **Referência**. 

Clique em **Detalhes de instalação** para selecionar o questionário e outros critérios. Por exemplo, especifique o nome do instrutor como um critério, se o questionário for uma avaliação do instrutor. Depois que terminar de inserir os detalhes de instalação, o sistema gera sessões de respostas planejadas para os usuários incluídos na consulta. 

Clique em **Sessões de respostas planejadas** para exibir as sessões de respostas para a agenda. Você poderá criar manualmente sessões de respostas planejadas adicionais ou excluir as sessões de respostas planejadas que não foram atendidas. 

Clique em **Funções** &gt; **Início** para disponibilizar o questionário aos usuários em sessões de respostas planejadas relacionadas. Clique em **Respostas** para exibir as respostas concluídas do questionário. Como opção, você pode copiar as configurações de agenda do questionário, as sessões de respostas planejadas, e as respostas para uma nova agenda de questionário.

## <a name="notifying-respondents-about-questionnaires-that-are-available-to-them"></a>Notificando participantes sobre os questionários que estão disponíveis para eles
Quando você distribuir um questionário, será necessário notificar os entrevistados que há questionários disponíveis para eles. 

### <a name="notifying-respondents-about-a-planned-answer-session"></a>Notificando os participantes sobre uma sessão de respostas planejadas

Se você usar uma sessão de resposta planejadas, você deve notificar a pessoa diretamente, por telefone ou email.

### <a name="notifying-respondents-about-a-scheduling"></a>Notificando participantes sobre um planejamento

Use a página **Agendas de questionário** para preparar e enviar um email a todos os entrevistados atribuídos ao questionário. Insira o texto do email na guia **Email para o autoatendimento para funcionários**. Depois que a agenda for iniciada, clique em **Funções** &gt; **Enviar email** para gerar e enviar o email para os entrevistados. Os entrevistados poderão efetuar logon no site e preencher o questionário. 

> **Observação** Antes que você possa usar a funcionalidade de email, o administrador de TI deverá inserir as configurações de email na página **Parâmetros de email**.

## <a name="ending-a-scheduled-questionnaire"></a>Finalizando um questionário planejado
É possível encerrar um questionário planejado depois que todos os participantes concluírem as sessões de resposta atribuídas a eles. Depois que um questionário planejado for concluído, não será possível copiar as configurações para um novo agendamento. 

> **Observação** Caso um ou mais participantes não tenham preenchido o questionário e você ainda queira encerrar o agendamento, você deve primeiro excluir os participantes relevantes da lista na página **Sessão de respostas planejadas**. Em seguida, será possível encerrar a agenda.

## <a name="completing-questionnaires"></a>Preenchendo questionários
Após criar e distribuir um questionário, este poderá ser preenchido por entrevistados selecionados. Você pode preencher os questionários disponíveis para você em dois locais:

-   No painel de navegação, clique em **Questionários** &gt; **Distribuir** &gt; **Preencher um questionário**.
-   No autoatendimento do funcionário, clique em **Questionários a serem concluídos**.

Os questionários podem ficar disponíveis para usuários específicos, grupos de usuários ou todas as pessoas de uma rede.

<a name="additional-resources"></a>Recursos adicionais
--------

[Projetar questionários](design-questionnaires.md)

[Usando questionários](questionnaires.md)

[Exibindo e avaliando os resultados dos questionários](evaluate-questionnaire-results.md)



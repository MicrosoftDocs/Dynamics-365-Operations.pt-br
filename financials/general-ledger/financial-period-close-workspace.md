---
title: "Espaço de trabalho de fechamento do período financeiro"
description: "Este artigo fornece uma visão geral do espaço de trabalho financeiro final do período e a configuração associada."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerPeriodCloseProjectWorkspace
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13791
ms.assetid: 6ee51758-639b-448e-9cb2-56cf1d804273
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 114dee90b0fe525f0b3efabbf651d2804a22dd7d
ms.openlocfilehash: ba0d709d123f56edb2a5287376c06c1f41181b1c
ms.lasthandoff: 03/31/2017


---

# <a name="financial-period-close-workspace"></a>Espaço de trabalho de fechamento do período financeiro

Este artigo fornece uma visão geral do espaço de trabalho financeiro final do período e a configuração associada.

Espaço de trabalho de fechamento do período financeiro

** Fechamento de período financeiro ** o espaço de trabalho permite acompanhar os processos financeiros de fechamento nas empresas, as áreas, e os contatos. Dependendo de sua exibição ** fechamento de período financeiro ** o espaço de trabalho, verá de todas as tarefas e status de uma agenda de fechamento, ou apenas tarefas atribuídas. 

Você deve primeiro selecionar um plano de fechamento na parte superior do espaço de trabalho. Todos os dados mostrados no espaço de trabalho são filtrados na agenda de fechamento selecionada.

### <a name="summary-tiles"></a>Blocos do resumo

Os blocos **Resumo** oferecem uma visão geral do processo e os indicadores ajudam a manter o rastreamento do processo de fechamento. Você pode ver as tarefas que estão, outras tarefas já vencidas para hoje, as tarefas que hoje é devido mas está bloqueado por causa dependências, e todas as outras tarefas do processo. Essas informações são para todas as empresas incluídas na agenda de fechamento selecionada.

### <a name="tasks-and-status-section"></a>Seção de tarefas e status

** Tarefas e status ** na seção, o status do total de fechamento é dividido de várias maneiras: status a empresa, por status por área, por status e a pessoa responsável. Você pode exibir o status de todas as tarefas na agenda de fechamento, apenas tarefas que hoje é devido, ou tarefas que estão de atraso alterando o filtro na parte superior da lista do cartão. Você também pode selecionar o filtro de empresa para exibir o status de uma empresa específica. Cada guia status de uma pane por porcentagem que foi preenchido e número de tarefas restantes. Clique no cartão ou ** exiba detalhes ** a ação filtrar a lista de tarefas detalhada por cartão selecionado. 

Guia o mais recente é para a lista de tarefas detalhada. A lista mostra a lista de tarefas e total pode ser filtrada de forma que mostra apenas as tarefas de seu interesse. Você pode filtrar a lista de tarefas em várias formas. Por exemplo, você poderá filtrar por data de vencimento da tarefa associada, por empresa e, por área associado. Você também pode selecionar para exibir ou ocultar tarefas concluído na lista de tarefas. 

Dois indicadores são usados para tarefas:

-   Um ícone de ponto de exclamação indica que a tarefa está atrasado. Para as tarefas que estão de atraso, a data de vencimento também está realçada em vermelho.
-   Um ícone de cadeado indica se a tarefa depende de outras tarefas que não preencheram ainda. Uma tarefa que será bloqueado por dependências não pode ser marcada como concluídas. Você pode definir para uma tarefa dependências usando ** dependência ajustada ** a ação.

O nome da tarefa é um hiperlink a Microsoft Dynamics 365 para a página de operações ou outro página da Web que o usuário deve ir concluir o trabalho. Você pode definir esse hiperlink usando ** link de tarefa ** coloca ao editar ou uma tarefa. 

Você pode anexar arquivos, notas, imagens, a URL e uma tarefa usando ** anexos ** a ação. Por exemplo, você pode indicar os números de diário usado como parte de uma tarefa, a adição de comentários sobre uma tarefa específica, ou anexar um arquivo de relatório que é impresso para a tarefa. Um ícone será exibido ** anexo ** coluna para a tarefa se o anexo estiver presente. 

** Tarefa ** a opção total deve ser marcada manualmente depois que a tarefa foi concluída. Quando uma tarefa são marcadas como concluídas, ** data concluído ** o campo será atualizado automaticamente a data atual e em horas. Os indicadores de dependência também é atualizado conforme apropriado.

## <a name="all-financial-period-close-tasks-list-page"></a>Página da lista de todas as tarefas de fechamento do período financeiro
Você pode exibir todas a produção atual e anteriores tarefas de fechamento de período ** todas as tarefas e de fechamento de período ** página de listagem. Esta página de listagem é usada melhor para análise histórica do processo de fechamento, que inclui informações sobre a data de conclusão planejada, a data final real, e a pessoa que concluiu a tarefa. Facilite exportar informações nesta página de listagem para o Microsoft Excel para relatar e auditar fins.

## <a name="financial-period-close-configuration-page"></a>Página de configuração do fechamento do período financeiro
Para usar ** fechamento de período financeiro ** o espaço de trabalho, você deve configurar o processo no Microsoft Dynamics 365 para as operações usando ** financeiramente configuração de fechamento de período ** a página. (Clique ** contabilidade ** &gt; ** período próximo ** &gt; ** financeiramente configuração de fechamento de período **.)

### <a name="resources"></a>Recursos

** ** Recursos na guia, você define os contatos envolvidos em processos de fechamento. Qualquer funcionário responsável por uma tarefa de fechamento devem primeiro estar atribuído aqui. Especifique também a exibição do funcionário do espaço de trabalho. As opções a seguir estão disponíveis:

-   **Somente tarefas atribuídas** – O usuário verá apenas as tarefas atribuídas a você ou a ele.
-   **Todas as tarefas e status** – O usuário verá todas as tarefas de fechamento e o status do processo total.

Os usuários que têm permissão para exibir somente suas tarefas atribuídas tarefas não poderão adicionar à lista de tarefas, editar tarefas ou remover tarefas da lista de tarefas.

### <a name="task-areas"></a>Áreas de tarefa

Use áreas de tarefas para agrupar tarefas de fechamento em áreas lógicas de propriedade na sua organização. Por exemplo, contas a pagar, contas a receber, ou contabilidade podem ser usadas como áreas de tarefa.

### <a name="calendars"></a>Calendários

Crie e edite calendários financeiros de fechamento com o guia de calendários.  É aqui que você definirá os dias úteis para fechar processos, e será usado planejamento tarefas de fechamento.  Crie um novo calendário e, indique os dias úteis a ser usado para agendamento de tarefas.  É aconselhável criar um calendário ao longo período de tempo, como um ano ou um ano de varejo, pois pode ser editada depois da criação.  Após criar o calendário, clique em editar o botão para atualizar o calendário em determinados dias, como feriados.  As tarefas de fechamento serão programadas em dias em que o valor de controle será definido para abrir.  Fechar tarefas não teria planejamento em um dia específico, aquele dia deve ter o valor de controle definido como fechado.

### <a name="templates"></a>Modelos

Use um fechamento financeiro modelo para definir as tarefas que são parte de um processo. Uma tarefa de fechamento é um trabalho recorrente de trabalho atribuído a uma pessoa para concluir como parte de cada processo. No modelo, uma data de vencimento relativo deve ser definida para cada tarefa de fechamento. A data de vencimento é relativo o número de dias antes ou depois da data final de período definida que a tarefa será feito a cada período. Horários devidos também são atribuídos a cada tarefa. Os devidos hora serão definidas usando o contexto do fuso horário e serão convertidos o fuso horário para cada usuário. 

Você pode atribuir uma tarefa no modelo a uma ou mais empresas em que essa tarefa se aplica. Se uma pessoa atribuída diferente para concluir esse trabalho de trabalho em cada empresa, talvez você acredita que é útil criar múltiplas tarefas para o mesmo trabalho de trabalho. Crie uma tarefa para cada empresa. 

** Link de tarefa ** o item de menu associado ao trabalho de trabalho com tarefas e pode ser usado para ir diretamente para a página associada link de tarefa no espaço de trabalho. Por exemplo, uma tarefa de fechamento executar o processo de reavaliação de contas a pagar pode ser vinculada no associado ** reavaliação de moeda estrangeira ** pagina no Microsoft Dynamics 365 para as operações. É possível também vincular a um URL externo. 

> [! Hint] se deseja vincular um relatório específico do management reporter em uma tarefa financeira do período, você pode usar a URL de relatório. Para acessar a URL de relatório, abra o relatório no designer de relatórios, clique em Arquivo ** ** &gt; ** o exibir relatório ** para abrir o relatório em um navegador. É possível copiar a URL na barra de endereços do navegador e colá-la no campo **URL** do **Link da tarefa**. 

Você pode definir dependências de tarefa no modelo. Se uma tarefa foi configurada depender de uma ou mais tarefas, essa tarefa não pode ser marcada como concluída até que todas as dependências sejam concluídos. 

Você pode criar vários modelos próximos financeiros. Você pode usar os vários modelos para acompanhar os processos de fechamento para diferentes tipos de períodos, como a empresa ou de mês e anos, ou para acompanhar as empresas que usam diferentes processos de fechamento. Depois que um modelo for criada, você pode copie-o para um novo modelo e fazer as alterações necessárias. Você poderá atribuir apenas um modelo para cada plano de fechamento.

### <a name="closing-schedules"></a>Agendas de fechamento

Você usa uma agenda de fechamento para atribuir um modelo próximo financeiro o período financeiro específico que deve ser fechado. Tarefas do modelo são geradas automaticamente para o período especificado, e o novo plano de fechamento é adicionada ao espaço de trabalho. Quando você cria um novo plano de fechamento, ** data final do período ** o campo é usado para determinar as datas de vencimento real das tarefas de fechamento, com base na data de vencimento relativo atribuída em próximo modelo financeiro. 

Atribuir o calendário apropriado para a agenda de fechamento, para indicar os dias úteis a ser usado no planejamento de tarefa. Se você não definir um calendário específico, datas de vencimento de tarefa usará todos os dias da semana. 

Você também deve definir empresas a serem associadas à agenda de fechamento. Se a chave tarefas do modelo são atribuídas a várias empresas, as tarefas separadas serão criadas para cada empresa na agenda de fechamento e atribuídas à tarefa de modelo. 

Depois que um plano de fechamento for concluído, selecione ** fechado ** o padrão para ele. O histórico da tarefa ainda estará disponível ** todas as tarefas e de fechamento de período ** página de listagem, mas a agenda de fechamento será removida do espaço de trabalho. Depois que um plano de fechamento foi marcada como fechado ** **, você não poderá adicionar tarefas não editar, tarefas, nem remover as tarefas delas.



---
title: Espaço de trabalho de fechamento do período financeiro
description: Este artigo fornece uma visão geral do espaço de trabalho financeiro final do período e a configuração associada.
author: ShylaThompson
ms.date: 11/29/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerPeriodCloseProjectWorkspace
audience: Application User
ms.reviewer: roschlom
ms.custom: 13791
ms.assetid: 6ee51758-639b-448e-9cb2-56cf1d804273
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 157d7e7503a3153f74e705c20b4afac76a81229e807ae6f39b52fc05c733487b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6739945"
---
# <a name="financial-period-close-workspace"></a>Espaço de trabalho de fechamento do período financeiro

[!include [banner](../includes/banner.md)]

Este artigo fornece uma visão geral do espaço de trabalho financeiro final do período e a configuração associada.

Espaço de trabalho de fechamento do período financeiro

O espaço de trabalho **Fechamento do período financeiro** permite acompanhar os processos financeiros de fechamento nas empresas, áreas e contatos. Dependendo de sua exibição do espaço de trabalho **Fechamento do período financeiro**, você verá todas as tarefas e status de uma agenda de fechamento, ou apenas as tarefas atribuídas a você. 

Primeiro é necessário selecionar uma agenda de fechamento na parte superior do espaço de trabalho. Todos os dados mostrados no espaço de trabalho são filtrados na agenda de fechamento selecionada.

### <a name="summary-tiles"></a>Blocos do resumo

Os blocos de **Resumo** fornecem uma visão geral do processo os indicadores o ajudam a manter o processo de fechamento em andamento. Você pode ver as tarefas que estão vencidas, tarefas restantes de hoje, tarefas vencidas hoje, mas bloqueadas por causa de dependências e todas as outras tarefas do processo. Essas informações são para todas as empresas incluídas na agenda de fechamento selecionada.

### <a name="tasks-and-status-section"></a>Seção de tarefas e status

Na seção **Tarefas e status**, o status da agenda total de fechamento é dividido em várias maneiras: status pela empresa, status por área e status por pessoa responsável. Você pode exibir o status de todas as tarefas na agenda de fechamento, apenas de tarefas que vencem hoje, ou tarefas que estão vencidas alterando o filtro na parte superior da lista do cartão. Você também pode selecionar o filtro de empresa para exibir o status de uma empresa específica. Cada guia de status fornece uma divisão pela porcentagem que foi concluída e número de tarefas restantes. Clique no cartão ou na ação **Exibir detalhes** para filtrar a lista de tarefas detalhada pelo cartão selecionado. 

A última guia se refere à lista de tarefas detalhadas. Esta lista mostra a lista de tarefas completa e pode ser filtrada de modo que mostre somente as tarefas de seu interesse. Você pode filtrar a lista de tarefas de várias maneiras. Por exemplo, você pode filtrar por data de vencimento da tarefa, pela empresa associada e por área associada. Você também pode optar por mostrar ou ocultar tarefas concluídas na lista de tarefas. 

Dois indicadores são usados para tarefas:

-   Um ícone de ponto de exclamação indica que a tarefa está atrasada. Para as tarefas que estão atrasadas, a data de vencimento também está realçada em vermelho.
-   Um ícone de cadeado vermelho indica que a tarefa depende de outras tarefas que ainda não foram concluídas. Uma tarefa que será bloqueada por dependências não pode ser marcada como concluída. Você pode definir dependências de uma tarefa usando a ação **Definir dependência**.

O nome da tarefa é um hiperlink para a página que o usuário deve acessar para concluir o trabalho. Você pode definir o hiperlink usando o campo **Link de tarefa** ao editar ou criar uma tarefa. 

Você pode anexar arquivos, notas, imagens e URLs a uma tarefa ao usar a ação **Anexos**. Por exemplo, você pode indicar os números de diários usados como parte de uma tarefa, adicionar comentários sobre uma tarefa específica, ou anexar um arquivo de relatório que foi impresso para uma tarefa. Um ícone será exibido na coluna **Anexo** para a tarefa se um anexo estiver presente. 

A opção **Conclusão da tarefa** deve ser selecionada manualmente depois que a tarefa for concluída. Quando uma tarefa é marcada como concluída, o campo **Data de conclusão** é atualizado automaticamente para a data e hora atuais. Os indicadores de dependência também são atualizados conforme apropriado.

## <a name="all-financial-period-close-tasks-list-page"></a>Página da lista de todas as tarefas de fechamento do período financeiro
Você pode exibir todas as tarefas do fechamento do período anterior ou atual na página de listagem **Todas as tarefas de fechamento**. Esta página de listagem é usada para análise histórica de seu processo de fechamento, pois inclui informações sobre a data de vencimento programada, a data de conclusão real e a pessoa que concluiu a tarefa. Você pode exportar facilmente as informações nesta página de lista para o Microsoft Excel para fins de relatórios e auditoria.

## <a name="financial-period-close-configuration-page"></a>Página de configuração do fechamento do período financeiro
Para poder usar o espaço de trabalho **Fechamento do período financeiro**, você deve configurar o processo usando a página **Configuração de fechamento do período financeiro**. (Clique em **Contabilidade** &gt; **Fechamento do período** &gt; **Configuração do fechamento no período financeiro**.)

### <a name="resources"></a>Recursos

Na guia **Recursos** você define as pessoas que estão envolvidas nos processos de fechamento. Os funcionários responsáveis por uma tarefa de fechamento devem ser atribuídos aqui. Você também deve especificar a exibição do funcionário do espaço de trabalho. As opções a seguir estão disponíveis:

-   **Somente tarefas atribuídas** – o usuário verá apenas as tarefas atribuídas a ele.
-   **Todas as tarefas e status** – O usuário verá todas as tarefas de fechamento e o status do processo total.

Os usuários que têm permissão para exibir somente suas tarefas atribuídas tarefas não poderão adicionar à lista de tarefas, editar tarefas ou remover tarefas da lista de tarefas.

### <a name="task-areas"></a>Áreas de tarefa

Use áreas de tarefas para agrupar tarefas de fechamento em áreas lógicas de propriedade na sua organização. Por exemplo, contas a pagar, contas a receber, ou contabilidade podem ser usadas como áreas de tarefa.

### <a name="calendars"></a>Calendários

Criar e editar calendários financeiros de fechamento usando a guia Calendários. Nesta guia, você definirá os dias da semana para fechar processos, e também a usará para agendar tarefas de fechamento.  Crie um novo calendário e, indique os dias úteis que serão usados para a agenda de tarefas.  É aconselhável criar um calendário para longos períodos, como um ano ou vários anos, desde que pode ser editado depois da criação.  Depois de criar o calendário, clique no botão Editar para atualizar o calendário de dias específicos, como feriados.  As tarefas de fechamento serão programadas em dias em que o valor de controle for definido para Abrir.  Se as tarefas de fechamento não tiverem que ser agendadas em um dia especificado, o valor do controle desse dia deve ser definido como Fechado.

### <a name="templates"></a>Modelos

Use um modelo de fechamento financeiro para definir todas as tarefas que fazem parte de um processo de fechamento. Uma tarefa de fechamento é um esforço recorrente que é atribuído a um indivíduo para conclusão como parte de cada processo de fechamento. No modelo, uma data de vencimento relativo deve ser definida para cada tarefa de fechamento. A data de vencimento relativa é o número de dias antes ou depois do período definido final no qual a tarefa será encerrada em cada período A hora de vencimento também será atribuída a cada tarefa. A hora do vencimento é definida usando o contexto de seu fuso horário e será convertida para o fuso horário de cada usuário. 

Você pode atribuir uma tarefa no modelo a uma ou mais empresas às quais essa tarefa se aplica. Se uma pessoa diferente é atribuída para concluir o compromisso de trabalho em cada empresa, talvez seja útil criar várias tarefas para o mesmo compromisso de trabalho. Crie uma tarefa para cada empresa. 

O item de menu **Link da tarefa** é associado ao compromisso de trabalho da tarefa e pode ser usado para ir diretamente à página associada no link da tarefa no espaço de trabalho. Por exemplo, uma tarefa de fechamento para executar o processo de reavaliação da moeda para Contas a pagar pode ser vinculada à página **Reavaliação de moeda estrangeira** associada. É possível também vincular a um URL externo. 

> [!TIP]
> Se deseja vincular um relatório específico do Management Reporter a uma tarefa de fechamento do período financeiro, use a URL do relatório. Para acessar a URL do relatório, abra o relatório no criador de relatórios e clique em **Arquivo** &gt; **Relatório de exibição** para abrir o relatório em um navegador. É possível copiar a URL na barra de endereços do navegador e colá-la no campo **URL** do **Link da tarefa**. 

É possível definir dependências de tarefa no modelo. Se uma tarefa foi configurada para depender de uma ou mais tarefas, essa tarefa não pode ser marcada como concluída até que todas as dependências sejam concluídas. 

Você pode criar vários modelos de fechamento financeiro. Você pode usar os vários modelos para acompanhar os processos de fechamento para diferentes tipos de períodos, como a empresa ou de mês e anos, ou para acompanhar as empresas que usam diferentes processos de fechamento. Depois que um modelo é criado, é possível copiar para um novo modelo e fazer as alterações necessárias. É possível atribuir somente um modelo a cada agenda de fechamento.

### <a name="closing-schedules"></a>Agendas de fechamento

Use uma agenda de fechamento para atribuir um modelo de fechamento financeiro a um período financeiro específico que deve ser fechado As tarefas do modelo são geradas automaticamente para o período especificado, e a nova agenda de fechamento será adicionada ao espaço de trabalho. Quando uma nova agenda de fechamento é criada, o campo **Data final do período** é usado para determinar as datas de vencimento real das tarefas de fechamento, com base na data de vencimento relativa que é atribuída no modelo do fechamento financeiro. 

Atribua o calendário apropriado para a agenda de fechamento, para indicar os dias úteis a serem usados no agendamento de tarefas. Se você não definir um calendário específico, as datas de vencimento usarão todos os dias da semana. 

Você também deve definir as empresas que serão associadas à agenda de fechamento. Se as tarefas do modelo forem atribuídas a várias empresas, as tarefas separadas serão criadas para cada companhia que estiver na agenda de fechamento e estiverem atribuídas às tarefas do modelo. 

Depois que uma agenda de fechamento for concluída, selecione a opção **Fechada** para ela. O histórico da tarefa ainda estará disponível na página de listagem **Todas as tarefas de fechamento do período financeiro**, mas a agenda de fechamento será removida do espaço de trabalho. Depois que uma agenda de fechamento for marcada como **Fechada**, não será possível adicionar tarefas, editar tarefas, nem removê-las.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
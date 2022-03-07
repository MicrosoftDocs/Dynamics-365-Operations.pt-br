---
title: Gerenciamento de tarefas
description: Este tópico explica a funcionalidade de gerenciamento de tarefas disponível no Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 12/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-29-11
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 614f37236bbd0239925e37ebf29f59ac006d09cd
ms.sourcegitcommit: 4f84540e6121ca3d5ae52ee07e414116d423cefa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/03/2022
ms.locfileid: "7948786"
---
# <a name="task-management"></a>Gerenciamento de tarefas

O gerenciamento de tarefas permite criar tarefas que devem ser concluídas para contratar (integrar), demitir (desligar) e transferir (transição) funcionários. O gerenciamento de tarefas usa o conceito de listas de verificação. Uma lista de verificação é uma lista de tarefas de integração, desligamento ou transição. O gerenciamento de tarefas usa listas de verificação para agrupar tarefas e para atribuí-las a indivíduos ou a grupos. A funcionalidade da lista de verificação para integração, desligamento e transições é semelhante.

## <a name="checklist-overview"></a>Visão geral da lista de verificação

Uma lista de verificação é um grupo de tarefas. As listas de verificação fornecem uma maneira flexível de agrupar tarefas e elas podem ser reutilizadas (por exemplo, quando você contrata funcionários adicionais). É possível criar tantas listas de verificação quanto forem necessárias, e você pode atribuir as mesmas tarefas a várias listas de verificação.

### <a name="examples"></a>Exemplos

Os exemplos a seguir mostram como as listas de verificação podem ser usadas no processo de integração. No entanto, como a funcionalidade da lista de verificação para integração, desligamento e transições é semelhante, as informações também se aplicam aos processos de desligamento e transição.

Como parte do processo de integração, os profissionais de Recursos humanos (RH) podem criar tarefas que rastreiam o andamento da integração dos funcionários novos e recentemente contratados. Como o processo de integração pode variar, dependendo da posição do funcionário ou da localização geográfica, você pode criar várias listas de verificação de integração para acomodar diferentes situações de contratação.

**Exemplo 1**

Cada funcionário contratado nos Estados Unidos deve concluir tarefas, como preencher formulários de retenção de imposto. No entanto, tarefas como a atribuição de um carro da empresa podem ser aplicáveis somente à equipe executiva. Neste caso, duas listas de verificação integradas podem ser criadas: **Funcionários baseados nos EUA** e **Somente executivos**. Depois, quando um gerente de nível intermediário for contratado nos Estados Unidos, a lista de verificação **Funcionários com base nos EUA** é marcada. No entanto, quando um executivo é contratado nos Estados Unidos, ambas as listas de verificação são selecionadas para garantir que todas as tarefas de integração necessárias sejam concluídas.

**Exemplo 2**

Uma empresa tem funcionários sazonais e funcionários comuns em tempo integral. Embora algumas tarefas (como verificar a hora de entrada do novo funcionário) se apliquem a funcionários de ambos os tipos, algumas tarefas adicionais se aplicam somente a funcionários comuns em tempo integral. Neste caso, você pode criar duas listas de verificação. Ambas as listas de verificação incluem as tarefas que se aplicam a funcionários sazonais e comuns de tempo integral, mas somente uma lista de verificação inclui as tarefas que são específicas para funcionários regulares em tempo integral.

## <a name="task-management-workspace"></a>Espaço de trabalho de gerenciamento da tarefa

O espaço de trabalho **Gerenciamento de tarefas** lista todas as tarefas que foram atribuídas às pessoas nos processos de integração, desligamento e transição. Para exibir as tarefas de um processo, selecione a guia apropriada no canto superior esquerdo: **Integração**, **Desligamento** ou **Transições**. Por padrão, somente os profissionais de RH podem acessar o espaço de trabalho **Gerenciamento de tarefas**.

A guia **Integração** contém uma lista **Inicia em breve** que mostra os funcionários novos e uma lista **Contratações recentes** que mostra os funcionários contratados recentemente. Em ambas as listas, você pode selecionar somente um funcionário. Quando você seleciona um funcionário, todas as tarefas relacionadas à integração do funcionário são mostradas no lado direito da página. A guia **Integração** também contém uma lista de **Todas as tarefas** que mostra todas as tarefas de todos os funcionários novos ou recentemente contratados. Finalmente, ela contém uma lista de tarefas vencidas e uma lista de tarefas atribuídas ao usuário atual.

A guia **Desligamento** contém uma lista de funcionários que estão saindo da empresa e uma lista de funcionários que já saíram da empresa. Em ambas as listas, você pode selecionar somente um funcionário. Quando você seleciona um funcionário, todas as tarefas relacionadas ao desligamento do funcionário são mostradas. A guia **Desligamento** também contém uma lista de **Todas as tarefas** que mostra todas as tarefas de todos os funcionários que estão saindo ou que saíram da empresa. Finalmente, ela contém uma lista de tarefas vencidas e uma lista de tarefas atribuídas ao usuário atual.

A guia **Transições** contém uma lista de **Todas as tarefas** que mostra todas as tarefas de todos os funcionários que mudarão as posições ou que alteraram recentemente as posições. Há também uma lista de tarefas vencidas e uma lista de tarefas atribuídas ao usuário atual.

Em todas as três guias, os assistentes de RH e os gerentes podem concluir as seguintes atividades:

- Aplicar uma lista de verificação a um funcionário.
- Atualizar o status de uma tarefa.
- Reatribuir uma tarefa.
- Atualizar a data de vencimento de uma tarefa.

> [!NOTE]
> Por padrão, a guia **Integração** mostra os funcionários que foram contratados nos últimos sete dias. Para alterar essa configuração, na página **Parâmetros de recursos humanos**, na guia **Geral**, no campo **Contratações recentes**, digite um período. As informações na lista **Contratações recentes** podem ser mostradas para um número específico de dias, meses ou anos. Por exemplo, para exibir a lista de funcionários contratados nos últimos 14 dias, defina o campo **Período** como **14** e o campo **Unidade** como **Dias**.
>
> Na página **Parâmetros de recursos humanos**, você também pode atualizar o intervalo de datas das listas de funcionários que estão saindo e que saíram da empresa que são mostrados na guia **Desligamento**.
>
> Essas configurações também se aplicam ao espaço de trabalho **Gerenciamento de pessoal**.

## <a name="setting-up-tasks"></a>Configurando tarefas

Você pode criar tarefas individualmente e reutilizá-las em várias listas de verificação. Para criar uma tarefa, na página **Configuração de integração**, na guia **Tarefas**, selecione **Novo**.

Como alternativa, você pode adicionar tarefas diretamente a uma lista de verificação. Para adicionar uma tarefa a uma lista de verificação, na página **Configuração de integração**, na guia **Lista de verificação**, crie uma nova lista de verificação para adicionar a tarefa, ou adicione a tarefa a uma lista de verificação existente.

> [!NOTE]
> Se você adicionar uma tarefa diretamente a uma lista de verificação, não poderá reutilizá-la em outras listas de verificação.

A tabela a seguir descreve os campos disponíveis quando você cria uma tarefa por qualquer método.

| Campo           | Descrição |
|-----------------|-------------|
| Tarefa            | Insira o nome da tarefa. |
| Descrição     | Insira uma descrição da tarefa. |
| Opcional        | Especifique se a tarefa é opcional e é apenas informativa. |
| Link da tarefa       | Insira a URL de uma página da Web externa ou uma página específica no aplicativo em que o usuário deve concluir a tarefa. Para obter mais informações, consulte os [Links da tarefa](#task-links). |
| Tipo de atribuição | As tarefas podem ser atribuídas a um trabalhador, uma posição ou um grupo de posições específico, o gerente do funcionário afetado (ou seja, o funcionário que faz parte do processo de integração, desligamento ou transição) ou o funcionário afetado. Selecione o tipo de atribuição. Para obter mais informações, consulte os [Tipos de atribuição](#assignment-types). |
| Atribuído a     | Selecione o trabalhador, a posição ou o grupo de posições específico ao qual a tarefa deve ser atribuída. |
| Pessoa de contato  | Especifique a pessoa que deverá ser contatada, se houver dúvidas sobre a tarefa. |
| Diferença da data de vencimento | Especifique o número de dias antes ou depois da data de integração, desligamento ou transição em que a tarefa é devida. Para obter mais informações, consulte a seção [Datas de vencimento da tarefa e o campo Diferença da data de vencimento](#task-due-dates-and-the-due-date-offset-field). |
| Instruções    | Insira instruções para concluir a tarefa. Para obter mais informações, consulte a seção [Instruções](#instructions). |

### <a name="task-links"></a>Links da tarefa

Um link de tarefa fornece um link para uma página da Web externa ou para uma página no aplicativo Dynamics 365. Você pode especificar um link de tarefa se a pessoa atribuída a uma tarefa tiver que ir a uma página específica ou a uma página específica do aplicativo Dynamics 365 para concluir a tarefa. Ao criar um link de tarefa, você pode selecionar uma das seguintes opções:

- **Item de menu** – se você selecionar esta opção, será exibida uma lista de todas as páginas no aplicativo Dynamics 365. Selecione uma página na lista.
- **URL** – se você selecionar essa opção, insira a URL da página da Web para a qual deseja que a pessoa atribuída à tarefa acesse. A página especificada pode ser uma página que não faz parte do aplicativo Dynamics 365.
- **Detalhes do trabalhador** – se você escolher este item, selecione uma das seguintes opções:

    - **Ações de autoatendimento para funcionário** – esta opção mostra uma lista de páginas que estão disponíveis no **Autoatendimento para funcionários**. Use-a, se a tarefa que foi atribuída ao funcionário integrado tiver que ser concluída no **Autoatendimento para funcionário**. Por exemplo, se você deseja que o funcionário insira suas informações pessoais de contato, selecione **Ações de autoatendimento para funcionário** e selecione **Detalhes Pessoais&gt;Informações pessoais**.
    - **Ações de gerenciamento do trabalhador** – esta opção mostra uma lista de páginas relacionadas ao registro do trabalhador, mas que não estão acessíveis ao funcionário. Por exemplo, se você deseja que o proprietário da tarefa Insira informações específicas a um trabalhador integrado, como informações de remuneração, selecione **Ações de gerenciamento de trabalhador** e selecione **Remuneração&gt;Remuneração fixa**.

### <a name="assignment-types"></a>Tipos de atribuição

Quando um funcionário é contratado, desligado ou transferido, uma ou mais listas de verificação podem ser selecionadas. Depois que uma lista de verificação é selecionada e o processo de contratação, desligamento ou transferência é concluído, as tarefas são criadas e atribuídas aos usuários para rastrear o andamento.

Quando uma tarefa é criada, ela é atribuída a um usuário específico. O usuário ao qual uma tarefa é atribuída depende do tipo de atribuição selecionado para essa tarefa. Os seguintes valores estão disponíveis no campo **Tipo de atribuição**:

- **Trabalhador** – atribua a tarefa a um trabalhador específico. Depois de selecionar este valor, selecione o trabalhador no campo **Atribuído a**.
- **Posição** – atribua a tarefa a uma posição específica. Depois de selecionar este valor, selecione a posição no campo **Atribuído a**.

    Por exemplo, um engenheiro de TI sempre será responsável por preparar um laptop para um novo funcionário. Nesse caso, ao criar a tarefa de configuração do laptop, selecione **Posição** como o tipo de atribuição e, em seguida, selecione **Engenheiro de TI** como a posição. Em seguida, quando um funcionário é contratado e a lista de verificação é atribuída, a tarefa de configuração do laptop é atribuída a qualquer funcionário que esteja na posição de engenheiro de TI no momento em que a ação de contratação é inserida.

- **Grupo** – atribui a tarefa a um grupo de posições (grupo de atribuições). Depois de selecionar este valor, selecione o grupo no campo **Atribuído a**. Para obter mais informações, consulte a seção [Configurando grupos de atribuições (Opcional)](#setting-up-assignment-groups-optional).
- **Gerente** – atribui a tarefa ao gerente do funcionário que está sendo contratado, desligado ou transferido.

    > [!IMPORTANT]
    > Quando uma lista de verificação for aplicada, se nenhuma posição estiver atribuída no momento ao funcionário contratado, desligado ou transferido, o gerente não poderá ser determinado. Nesse caso, a tarefa é atribuída ao proprietário da lista de verificação. Para obter mais informações, consulte a seção [Configurando listas de verificação](#setting-up-checklists).

- **Funcionário** – atribua ao funcionário que está sendo contratado, desligado ou transferido.

### <a name="task-due-dates-and-the-due-date-offset-field"></a>Datas de vencimento da tarefa e o campo Diferença da data de vencimento

As datas de vencimento da tarefa são baseadas na data de início do emprego, na data de desligamento ou na data de transição. Algumas tarefas devem ser concluídas antes da data de início de um funcionário, enquanto outras tarefas podem ser concluídas depois. Ao definir uma tarefa, você define o campo **Diferença da data de vencimento** para especificar uma data de vencimento relativa à data de início, data de desligamento ou data de transição. Por exemplo, um engenheiro de TI deve preparar um laptop para um novo funcionário dois dias antes da data de início desse funcionário. Nesse caso, ao criar a tarefa de configuração do laptop, defina o campo **Diferença da data de vencimento** como **-2**. Em seguida, se a data de início de um funcionário for 5 de maio, a tarefa vencerá em 3 de maio.

> [!NOTE]
> As datas de vencimento podem ser ajustadas após a tarefa ser criada.

As datas de vencimento são calculadas com base no calendário associado à lista de verificação. Para obter mais informações, consulte a seção [Configurando listas de verificação](#setting-up-checklists).

### <a name="instructions"></a>Instruções

Tarefas complexas podem exigir várias etapas, ou a pessoa que está executando a tarefa talvez precise fornecer informações adicionais. No campo **Instruções**, você pode inserir instruções ou informações adicionais para ajudar a pessoa designada à tarefa a concluí-la.

## <a name="setting-up-checklists"></a>Configurando listas de verificação

Uma lista de verificação é um grupo de tarefas. É possível criar tantas listas de verificação quanto forem necessárias, e você pode atribuir as mesmas tarefas a várias listas de verificação. Ao criar uma lista de verificação, especifique um proprietário e um calendário.

Se o campo **Tipo de atribuição** de uma tarefa estiver definido como **Posição**, **Gerente** ou **Grupo**, mas nenhuma pessoa específica puder ser derivada do tipo de atribuição, a tarefa será atribuída ao proprietário da lista de verificação. Aqui estão alguns exemplos de situações nas quais as tarefas serão atribuídas ao proprietário da lista de verificação:

- Nenhuma posição é atribuída ao funcionário que está sendo contratado ou demitido. Como o funcionário não tem uma atribuição de posição, não é possível determinar seu gerente.
- O campo **Tipo de atribuição** é definido como **Posição**, mas nenhum funcionário é atribuído à posição no momento em que a tarefa é criada. Por exemplo, a tarefa **Laptop de configuração** é atribuída ao número de posição 000876 (**Especialista em Suporte Técnico**). No momento em que um funcionário é contratado, nenhum funcionário é atribuído à posição 000876. Portanto, uma tarefa será criada para o proprietário da lista de verificação.
- O campo **Tipo de atribuição** é definido como **Grupo**, mas nenhum funcionário é atribuído à posição no grupo no momento em que a tarefa é criada.

O calendário especificado para uma lista de verificação é usado para calcular a data de vencimento das tarefas que fazem parte dessa lista de verificação. Os dias úteis e não úteis são definidos na configuração do calendário. Os dias úteis são incluídos quando a data de vencimento das tarefas é calculada e os dias não úteis são excluídos. Os dias não úteis incluem fins de semana e feriados. 

Depois que um calendário é configurado, ele é associado a um modelo de lista de verificação. Dessa forma, a data de vencimento de cada tarefa na lista de verificação é calculada da mesma forma. Você pode configurar vários calendários, mas somente um calendário pode ser associado a cada lista de verificação.

## <a name="setting-up-assignment-groups-optional"></a>Configurando grupos de atribuições (Opcional)

Às vezes, um grupo de indivíduos é responsável por uma tarefa. Por exemplo, um grupo de operadores de TI pode ser responsável por preparar laptops para novos contratados.

Para configurar um grupo de atribuições, siga estas etapas.

1. Na página **Atribuição de Grupo**, selecione **Novo**.
1. Digite um nome (por exemplo, **Laptop de TI**) e uma descrição para o grupo.
1. Selecione **Salvar**.
1. Na Guia Rápida **Membros**, selecione **Adicionar**.
1. No campo **Posições**, selecione todas as posições responsáveis pela tarefa.

Depois que um grupo de atribuições é criado, ele fica disponível para seleção quando uma tarefa é criada. Para selecionar um grupo específico para uma tarefa, você deve selecionar **Grupo** no **Tipo de atribuição**. O grupo que você criou estará disponível para seleção no campo **Atribuído a**.

> [!IMPORTANT]
> Se uma tarefa for atribuída a um grupo, a tarefa será marcada como **Concluída** quando uma pessoa do grupo for concluída. As tarefas são criadas no momento da contratação, do desligamento ou da transição. Elas são criadas para os usuários atribuídos às posições que estão incluídos no grupo.

## <a name="setting-up-task-groups-optional"></a>Configurando grupos de tarefas (Opcional)

Um processo de integração, desligamento ou transição pode incluir várias tarefas. Para facilitar a atribuição de todas as tarefas necessárias a uma lista de verificação, você pode criar grupos de tarefas opcionais para categorizar as tarefas relacionadas. Por exemplo, os departamentos de RH, de TI e de Folha de Pagamento devem executar cada tarefa específica para contratar um novo funcionário. Portanto, você cria os seguintes grupos de tarefas: **RH**, **TI** e **Folha de Pagamento**. Em seguida, ao criar uma tarefa, você pode associar um desses grupos de tarefas a ela.

Quando quiser adicionar uma tarefa a uma lista de verificação, você poderá filtrar a lista de tarefas pelo grupo de tarefas ao qual a tarefa desejada está atribuída. Por exemplo, ao criar um modelo de lista de verificação, você pode filtrar a lista para que somente as tarefas de TI atribuídas ao grupo de **TI** sejam mostradas. Portanto, você pode garantir que somente as tarefas de TI relevantes sejam selecionadas.

## <a name="using-checklists"></a>Usando listas de verificação

Quando um colaborador é contratado, desligado ou transferido, uma ou mais listas de verificação podem ser selecionadas. As datas de vencimento da tarefa e as atribuições de trabalhador são criadas após a conclusão do processo de contratação, desligamento ou transição. Por exemplo, quando você seleciona o botão **Contratar** ou **Contratar e adicionar detalhes**, as tarefas são criadas para as pessoas, com base no tipo de atribuição.

Uma data de vencimento é atribuída a cada tarefa adicionando ou subtraindo a diferença da data de vencimento da data de início do funcionário. Para obter mais informações, consulte a seção [Datas de vencimento da tarefa e o campo Diferença da data de vencimento](#task-due-dates-and-the-due-date-offset-field).

Se você estiver usando ações de pessoal, as tarefas serão criadas quando o botão **Concluir** for selecionado ou a ação for aprovada.

No espaço de trabalho **Gerenciamento de tarefas**, você pode aplicar uma lista de verificação a um funcionário, selecionando o funcionário na página lista simples ou detalhes e selecionando **Aplicar lista de verificação**. O valor do campo **Data de destino** será usado para calcular a data de vencimento das tarefas. Normalmente, a data de destino deve ser igual à data de contratação, desligamento ou transição do funcionário.

Também é possível aplicar uma lista de verificação a um funcionário abrindo a página **Trabalhador** e selecionando **Listas de verificação** no menu.

## <a name="completing-tasks"></a>Concluindo tarefas

Na página **Autoatendimento para funcionários** um funcionário pode exibir todas as tarefas atribuídas a elas. Para cada tarefa atribuída, os valores de **Tarefa**, **Descrição**, **Instruções** e **Pessoa de contato** são mostrados. Além disso, para cada tarefa, o funcionário pode abrir a página da Web externa associada ou a página associada no aplicativo Dynamics 365.

As tarefas podem ser marcadas como **Em andamento**, **Canceladas** ou **Concluídas**. Se uma tarefa foi atribuída a um grupo, ela será marcada como **Concluída** quando uma pessoa do grupo concluí-la.

As tarefas também podem ser reatribuídas.

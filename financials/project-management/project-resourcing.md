---
title: Recursos do projeto
description: "Este tópico fornece informações sobre o resourcing de projeto."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: cmercado
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: c29c95fc6abd13e668c44d3ccf437bb0e879e46b
ms.lasthandoff: 03/31/2017


---

# <a name="project-resourcing"></a>Recursos do projeto

Este tópico fornece informações sobre o resourcing de projeto.

Um desafio de gerentes de projeto e gerentes de recursos no estágio de planejamento do projeto for uma atribuição recursos, determinar onde e devem reservar recurso correto trabalhar em um projeto. No Microsoft Dynamics 365 para operações, os recursos de projetos para resourcing permitem definir as funções que são tratadas como recursos temporários que podem ser reservados para um compromisso específico, ou parte de um compromisso. Esse tipo de recurso permite que os gerentes de projeto e gerentes de recursos concluam as seguintes tarefas:

-   Definir uma função que tenha as competências necessárias para facilitar a correspondência recursos.
-   Use funções para definir um plano inicial do compromisso baseada em recursos reservados.
-   Estimar os custos e determinar um orçamento inicial com base em funções e em vários recursos para um projeto.
-   Use funções para estimar o número reservas de recurso necessárias para cada compromisso.
-   Estimar o número de recursos necessários para todo o ciclo de vida de um projeto.
-   Criar um rascunho de WBS (estrutura de detalhamento de trabalho) usando as atribuições de recursos iniciais.

[ciclo de vida do projeto (![]. /media/projectresourcing02-1024x812.jpg)](. /media/projectresourcing02.jpg) 

Como os rendimentos de planejamento de recursos, projeto planejadas podem ser pors substituir proveram equipe de recursos. O gerente de projeto também pode voltar e atualizar o resourcing durante alguns estágios do projeto.

## <a name="set-up-project-resources"></a>Configurar recursos do projeto
Você deve configurar um calendário e associá-lo a um funcionário ou a um trabalhador. O calendário é usado para agendar o projeto e o tempo dos recursos que são reservados para o projeto. Durante a configuração de calendário, os gerentes de projeto podem realizar o nivelamento de recursos como parte da otimização de recursos. Com base na agenda de calendário, podem ser colocadas restrições em recursos. Você pode definir um calendário ** calendários ** na página. 

Quando você configurou um trabalhador como um recurso de projeto, você pode selecionar os funcionários que trabalham na empresa para a qual você está configurando ou recursos, você pode selecionar funcionários de outras de sua organização. Esses são recursos intercompanhia. Os procedimentos a seguir explicam como configurar um trabalhador como um recurso de projeto em sua empresa e como configurar o recurso intercompanhia de projeto.

### <a name="set-up-a-worker-as-a-project-resource"></a>Configurar um trabalhador como um recurso do projeto

1.  ** ** Trabalhadores na página em, ** trabalhadores ** lista, selecione o trabalhador que você está adicionando como um recurso de projeto, bem abrem o registro de trabalho.
2.  No painel de ações, clique ** projeto ** &gt; ** de instalação ** &gt; ** ** configuração de projeto.
3.  Selecione um calendário, e feche a página.

Você também pode especificar projetos padrão para um recurso como um tipo de atribuição prévia. As atribuições prévias podem ser usadas quando o gerente de recurso ou o gerente de projeto sabem com antecedência em quais projetos o recurso trabalhará. As atribuições prévias também podem ser baseadas na solicitação de um patrocinador ou de um cliente do projeto. Para atribuir um projeto previamente, na página **Atribuir projetos**, na guia **Projetos**, na lista **Projetos restantes**, selecione o projeto apropriado.

### <a name="set-up-an-intercompany-resource"></a>Configurar o recurso intercompanhia

Quando você configurou um trabalhador como um recurso intercompanhia, você deve concluir a instalação da empresa de empréstimo e na empresa de empréstimo. 

** De empréstimo a empresa: **

1.  Em dynamics 365 para operações, verifique se a empresa de empréstimo esteja selecionada, e conclua o procedimento acima, “um trabalhador configurado como um recurso de projeto”.
2.  Ir ** contabilidade **&gt; ** a configuração de postagem **&gt; ** ** contabilidade intercompanhia. Click **New**.
3.  ** O ID da entidade legal ** campo, selecione a empresa de empréstimo. Preencha os campos restantes como apropriado, e clique em salvar ** **.
4.  Ir ** gerenciamento e contabilidade de projeto **&gt; ** o de instalação **&gt; ** preços ** &gt; ** ** preço de transferência. ** **
5.  ** O preço de transferência ** formulário, clicar ** ** novo e, em ** solicitando a entidade legal ** campo, selecione a empresa apropriada.
6.  Se você deseja emprestar somente para a empresa de empréstimo o recurso que você criou no início desta seção, o recurso ** ** campo, selecione o nome do recurso que você criou. Se desejar tornar todos os recursos da empresa disponíveis na empresa de empréstimo, deixe ** recurso ** campo em branco.
7.  Ir ** gerenciamento e contabilidade de projeto **&gt; ** de instalação **&gt; ** parâmetros de gerenciamento do projeto e contabilidade **, ** ** intercompanhia e na guia, definir ** habilitar o recurso de planejamento intercompanhia e a folha de ponto ** o campo ** Sim **.

** De empréstimo a empresa: **

1.  Ir ** gerenciamento e contabilidade de projeto ** &gt; ** os recursos de projetos ** &gt; ** recursos listam **.
2.  Em filtros de pesquisa, insira o nome do recurso criado no procedimento anterior da empresa de empréstimo verifique o nome foi incluído na lista de recursos para a empresa de empréstimo.

## <a name="manage-resource-competencies"></a>Gerenciar competências do recurso
Competências do recurso são uma parte essencial de gerenciamento de recursos. As competências podem ser usadas como uma linha de base para determinar os recursos que tenham o equilíbrio correto de habilidades, de formação educacional, de certificação e da experiência de projeto. Você deve configurar essas informações para cada recurso e atualizá-las periodicamente. Dessa forma, você pode maximizar os recursos quando as competências específicas do recurso forem correspondidas durante a atribuição do recurso de projeto. [exemplos do![as habilidades, as certificações, a educação, e a experiência de projeto (]. /media/projectresourcing06-1024x383.jpg)](. /media/projectresourcing06.jpg) 

Os procedimentos a seguir explicam como configurar algumas das competências para um recurso. 

Para configurar as competências de um trabalhador, você pode usar a página de listagem **Trabalhadores** em Recursos humanos ou a página de listagem **Recursos** em Gerenciamento e contabilidade de projetos. Para os procedimentos, ** trabalhadores ** a página de listagem em recursos humanos for usada.

### <a name="set-up-competencies-certificates"></a>Configurar competências: certificados

1.  Na página de listagem **Trabalhadores**, selecione a linha do trabalhador para a qual você está adicionando as informações de certificado.
2.  No Painel de Ação, na guia **Trabalhador**, no grupo **Competências**, clique em **Certificados**.
3.  Clique em **Novo**.
4.  No campo **Tipo de certificado**, selecione **PMP**.
5.  No campo **Data inicial**, selecione **1/10/2015**.
6.  Clique em **Salvar** e feche a página.

### <a name="set-up-competencies-skills"></a>Configurar competências: habilidades

1.  Na página de listagem **Trabalhadores**, verifique se o trabalhador usado no procedimento anterior ainda está selecionado. Então, no Painel de Ação, na guia **Trabalhador**, no grupo **Competências**, clique em **Habilidades**.
2.  Clique em **Novo**.
3.  No campo **Habilidade**, selecione **Gerenciamento de projetos**.
4.  No campo **Nível**, selecione **5 Especialista**.
5.  No campo **Data do nível**, selecione **14/1/2014**.
6.  No campo **Anos de experiência**,insira **10**.
7.  Clique em **Salvar** e feche a página.

## <a name="create-a-new-project"></a>Criar um novo projeto
1.  ** Clique em gerenciamento e contabilidade de projeto ** &gt; ** espaços de trabalho de gerenciamento ** &gt; ** ** projeto.
2.  Clique em **Novo projeto** e insira os seguintes valores:
    -   ** ** Tipo de projeto - tempo e material
    -   ** Nome do projeto - 2 ** fase de atualização XYZ
    -   ** ** Grupo de projeto - WIP TM\_
    -   ** ID de contrato de projeto ** - 00000002
3.  Clique em **Criar projeto**.

### <a name="assign-a-resource-to-a-project"></a>Atribuir um recurso a um projeto

1.  Clique ** recursos humanos ** &gt; ** trabalhadores ** &gt; ** trabalhadores **.
2.  Na lista **Trabalhadores**, selecione o registro para o trabalhador para o qual você configurou competências e abra o registro do trabalhador.
3.  No Painel de Ação, na guia **Projeto**, no grupo **Configuração**, clique em **Atribuir projetos**.
4.  Na página **Atribuições de projeto de validação do recurso**, clique na guia **Projetos**.
5.  ** O adicionar o projeto para projetos selecionados **, em filtro, projeto 2 fase de atualização XYZ
6.  No painel **Projetos restantes**, selecione um projeto e clique na seta para adicioná-lo ao painel **Projetos selecionados**.
7.  Feche a página.

Se necessário, também é possível atribuir categorias para um recurso. O tipo de categoria será Custo ou Receita. Isso é determinado por sua organização. Se não houver nenhuma categoria atribuído para o recurso, o dynamics 365 para operações pesquisará a categoria padrão em horas para preços de custo e receita.

### <a name="set-up-project-resource-and-role-characteristics"></a>Configurar as características de recurso de projeto e de função

Um gerente de projeto pode usar a funcionalidade de recursos do projeto para criar as funções necessárias para um projeto. As funções podem ser usadas quando os recursos confirmados ainda desconhecidos quando para reservar recursos. As funções podem ser como recursos esperado temporariamente permitido, para que você possa continuar os estágios de planejamento do projeto. 

[exemplo![de uma função. (]/media/projectresourcing05.jpg)](. /media/projectresourcing05.jpg) 

**Cenário:** Exemplo de função Cenário: a Contoso foi contratado para concluir um projeto por Tempo e material com um estatuto de projeto aprovado. O gerente de projeto júnior ainda está concluindo o escopo do projeto. Gerente de recurso estará identificando atualmente recursos específicos que serão reservados para trabalhar no novo projeto. Uma das funções que o solicitou patrocinador de projeto, devido a natureza crítico de projeto, é a gerente de projeto superior. Gerente de recurso necessário adquirir o recurso novo e defina a função do sistema se o gerente de projeto júnior requer informações de recurso durante o planejamento do projeto. 

As etapas abaixo mostram como gerente de recurso pode configurar a função gerente de projeto superior e recurso de estoque associado a ele. Posteriormente, a função poderá ser usada para procurar os recursos disponíveis que correspondam às competências necessários de recurso.

1.  ** Clique em gerenciamento e contabilidade de projeto ** &gt; ** de instalação ** &gt; ** recursos ** &gt; ** funções ** de instalação.
2.  Clique em **Novo** e insira os seguintes valores:
    -   ** Função - ID ** superior gerente de projeto
    -   ** Descrição ** - superior gerente de projeto
3.  Clique em **Criar**.
4.  Selecione a função **Gerente de projeto sênior** e clique em **Configurar características**.
5.  No campo **Tipo de característica**, selecione **Habilidade**.
6.  No campo **Características disponíveis**, insira a habilidade que você está procurando.
7.  No campo **Tipo de característica**, selecione **Certificado**.
8.  No campo **Características disponíveis**, insira o tipo de certificado que você está procurando.
9.  Clique em **OK** e feche a página.

### <a name="assign-a-project-resource-to-a-project"></a>Atribuir um recurso de projeto a um projeto

1.  ** Clique em gerenciamento e contabilidade de projeto ** &gt; ** comum ** &gt; ** projetos ** &gt; ** ** todos os projetos, e abra ** a fase 2 de atualização XYZ ** o projeto.
2.  Na guia **Equipe de projeto e agendamento**, clique em **Adicionar**.
3.  No campo **Função**, selecione **Membro da equipe**.
4.  Clique em **Reservar do calendário**.
5.  Na página **Disponibilidade de recursos**, clique em **Configurações de exibição**.
6.  Na página **Ajustar configurações de exibição**, insira os seguintes valores:
    -   ** Formato da exibição do intervalo de data - ** dia
    -   ** Disponibilidade de descrições de exibição - Sim **
    -   ** Capacidade restante de exibição - Sim **
7.  Na lista de recursos, selecione um recurso.
8.  Clique ** registro rígido ** &gt; ** ** capacidade total.
9.  Feche a página.

### <a name="assign-a-resource-to-a-default-role"></a>Atribuir um recurso a uma função padrão

Para ajudar a gerentes de projeto ou recurso, você pode fazer busca detalhada nos recursos mais que podem ser reservados para um projeto. Você pode associar uma função padrão a um recurso existente ou a um recurso adquirido mais recentemente. Por exemplo, quando Daniel foi contratado, tinha a experiência e as habilidades preencha a função comercial de analista. Gerente de recurso tiver atribuído essa função como a função padrão de Daniel. Assim, o gerente de recurso Daniel adicionados a um grupo de analistas comerciais disponíveis para produção em projetos. 

Durante a reserva de recurso, os gerentes de projeto podem filtrar a função dos recursos disponíveis para produção em projetos. Eles podem usar essas informações como um critério ao executarem análises de decisão de vários critérios durante o preenchimento de recursos. Também podem adicionar outras características do recurso ao filtro para pesquisar recursos que tenha habilidades, formação educacional e experiência específicas para um determinado projeto. 

** Cenário: ** Aprovado um projeto foi iniciado, e a função gerente sênior de projeto foi definido como um recurso planejada durante o estágio de planejamento do projeto. O gerente de recurso adquiriu um recurso para preencher a função Gerente de projeto sênior.

1.  ** Clique em gerenciamento e contabilidade de projeto ** &gt; ** recursos de projetos ** &gt; ** recursos listam **.
2.  Na lista **Recurso**, selecione **Daniel Goldschmidt**.
3.  Clique ** recurso de projeto ** &gt; ** manter ** &gt; ** ** função de recurso.
4.  Clique em **Novo** e insira os seguintes valores:
    -   ** Efetivo ** - (a data atual)
    -   ** Vencimento ** - nunca
    -   ** ** - Função gerente de projeto superior
5.  Clique em **Salvar** e feche a página.
6.  Na guia **Competências**, adicione a habilidade **ProjectMgmt** e o certificado **PMP**.

## <a name="set-up-role-based-pricing"></a>Configurar preços baseados em função
Todos os preços de custo, de venda e de transferência podem ser configurados para funções.

1.  ** Clique em gerenciamento e contabilidade de projeto ** &gt; ** de instalação ** &gt; ** preços ** &gt; ** preço de venda (horas) **.
2.  Click **New**.
3.  Inserir uma data de efetivação.
4.  Na coluna **Função**, selecione uma função.
5.  Na coluna **Preços**, insira um preço para a função de recurso selecionada.

## <a name="form-a-project-team"></a>Formulário equipe de projeto
Para usar as funções configuradas previamente em um projeto, uma gerente de projeto deverá associar funções com o projeto. As diversas funções podem ser atribuídas para um projeto e, ao 365 para operações etiquetas automaticamente essas funções durante a reserva para evitar você evitará. Por exemplo, se o gerente de projeto requer três Engineers Software, três cargos de Software Engineer com o Software Engineer 1, a Engineer Software 2, e o Software Engineer 3 como os rótulos são gerados automaticamente. Se as características da função tiverem sido definidas anteriormente para a função, elas serão aplicadas como um filtro durante a pesquisa de recursos. Características adicionais podem ser adicionadas conforme necessário para refinar ainda mais a pesquisa. 

As configurações de exibição também podem ser personalizadas para fornecer uma visão melhor de disponibilidade de capacidade. Há opções para mostrar a disponibilidade por hora, por dia, por semana, por mês, por trimestre e por ano. Há também uma opção para mostrar a capacidade disponível e restante dos recursos. Essa opção é útil para o gerenciamento de tempo quando você está estimando as horas disponíveis para atividades ou a disponibilidade de capacidade. 

Gerente de projeto poderá selecionar uma função na página em seguida, se há um recurso disponível de acordo com a necessidade, selecione para permitir um recurso para preencher a função. Observe que os recursos não precisam ser reservados nesse ponto até o estágio de planejamento. Quando você cria um WBS, você pode substituir funções com os recursos providos de equipe para o projeto. Se as funções são pors substituir proveram equipe de recursos em WBS, o recurso atualizar automaticamente a listagem e plano de equipes de projeto. 

[lista de equipes do![que contém funções e recursos (reais]. /media/projectresourcing03-1024x368.jpg)](. /media/projectresourcing03.jpg) 

O gerente de projeto tem diversas opções para reservar um recurso para um projeto, como **Capacidade restante**, **Capacidade total**, **Porcentagem da capacidade** e **Especificar horas**. Essas opções de reserva poderão ser canceladas a qualquer momento se as atribuições de recursos forem alterados. Há dois tipos de reserva com suporte:

-   ** O livro rígido ** – reserva de recurso foi aprovado e confirmada para compromisso para trabalhar na duração específica.
-   ** O registro de ** – reservas de recurso foi definido para trabalhar em provisoriamente compromisso para a duração específica.

O procedimento a seguir explica como criar uma equipe de projeto.

### <a name="create-a-project-team"></a>Criar uma equipe de projeto

1.  Na página de listagem **Todos os projetos**, selecione um projeto e clique em **Editar**.
2.  ** Em equipe de projeto e plano ** guia, ** data final do plano ** no campo, insira a data inicial de plano mais um mês. Por exemplo, se a data de início do plano é 24 de junho de 2017 (24/06/2017), insira 24/07/2017 ** **.
3.  Click **Add**.
4.  No painel **Adicionar funções ao projeto**, no campo **Função **, selecione **Gerente de projeto sênior**.
5.  Clique em **Competências necessárias**.
6.  Na página **Escolher características**, as características que você definiu anteriormente para a função Gerente de projeto sênior estarão selecionadas por padrão. Clique em **OK**.
7.  Na página **Adicionar funções ao projeto**, no campo **Número de recursos**, insira **1**.
8.  No campo **Recurso**, a consulta mostra todos os recursos que têm as competências necessárias. Selecione **Daniel Goldschmidt** e clique em **Criar**.
9.  Na página **Projeto**, clique em **Adicionar**.
10. No painel **Adicionar funções ao projeto**, no campo **Função **, selecione **Membro de equipe**. No campo **Número de recursos**, insira **5**.
11. Clique em **Criar**.
12. Na página **Projetos**, clique em **Preencher recurso**.

## <a name="resource-capacity-synchronization"></a>Sincronização de capacidade do recurso
Os processos para ajudar a sincronização de recurso garantem que as informações do calendário e do calendário base escoem para o agendamento de recurso de projeto. Se o calendário for alterado, os processos farão as atualizações necessárias no agendamento dos recursos de projeto. Os processos também ajudam a melhorar o desempenho, pois as informações de recurso do calendário são previamente sincronizadas, de tal modo que as atualizações das informações de agendamento de recurso ocorram mais rápido. Recomendamos que você agende os processos em lotes em vez de um de cada vez. Caso contrário, há o risco de que alguém se esqueça das datas inclusivas quando as informações foram sincronizadas pela última vez. Se as datas inclusivas não forem usadas, poderão ocorrer lacunas durante a sincronização de datas.

### <a name="calendar-synchronizationmediaprojectresourcing04-1024x471jpg"></a>![Calendário a sincronização](./media/projectresourcing04-1024x471.jpg)

**Synchronize resource capacity roll-ups**

O processo de sincronização é projetado para sincronizar todas as informações do calendário do recurso. Essas informações incluem informações do calendário base sobre todas as alterações na tabela de capacidade do calendário do recurso do projeto. Se os recursos novos são adicionados no projeto, ajuda de sincronização garantir que as informações atualizadas sobre calendário está disponível. Essa sincronização pode ser feita a qualquer momento. 

É recomendável usar um lote. As opções estarão disponíveis nas reservas de capacidade de sincronização.

-   ** Clique em gerenciamento e contabilidade de projeto ** &gt; ** periódico ** &gt; ** sincronização de capacidade ** &gt; ** sincronizar a capacidade rolo- UPS recursos **.

| Opção | descrição                                                                                                                                                                                          |
|--------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Sim    | Sincronize todos os dados de recurso com as informações do calendário e do calendário base, e substitua todas as informações no calendário de capacidade de recurso do projeto.                                                  |
| Não     | Sincronize dados de recurso com base no código de intervalo de datas, e as datas inicial e final especificadas. Esta opção não remove os dados existentes e atualiza as informações somente para recursos recém-adicionados. |

[processo de sincronização do![(]. /media/projectresourcing09.jpg)](. /media/projectresourcing09.jpg)

## <a name="set-up-roles-on-wbs-templates"></a>Configurar funções em modelos WBS
Os gerentes de projeto podem configurar modelos de WBS que podem ser aplicados durante a criação de uma WBS para novos projetos. Os gerentes de projeto funções podem adicionar ao criar um modelo. Use o seguinte procedimento para atribuir uma função para um modelo de WBS. ** **

1.  ** Clique em gerenciamento e contabilidade de projeto ** &gt; ** de instalação ** &gt; ** projetos ** &gt; ** modelos da estrutura de detalhamento de trabalho **.
2.  Clique em **Detalhes** para um modelo de WBS selecionado.
3.  Selecione uma tarefa na lista e, no campo **Função**, selecione uma função para atribuir à tarefa.

### <a name="work-with-a-wbs"></a>Trabalhar com um WBS

Você pode criar um novo WBS ou pode copiar uma WBS de um modelo existente de WBS. Um gerente de projeto pode gerenciar os recursos ao atribuir funções às novas tarefas na WBS. As funções poderão ser substituídas depois que um recurso for adquirido ou depois que um recurso confirmado para trabalhar na tarefa for identificado. Essa flexibilidade permite que os gerentes de projeto executem as seguintes tarefas:

-   Identificar o número de recursos necessários para os pacotes de trabalho WBS.
-   Estimar custos de projeto.
-   Determinar um orçamento preliminar.
-   Estimar a duração da atividade com base em funções e em recursos.
-   Desenvolver alguns planos de gerenciamento de projetos com base nas informações disponíveis sobre o projeto.

Outras opções foram adicionadas à WBS para melhorar o uso da funcionalidade de recursos.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Opção</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Atribuições de recursos</td>
<td>Exiba os recursos atribuídos, as datas, o número de horas e o tipo de reserva para tarefas na WBS.</td>
</tr>
<tr class="even">
<td>Gerar equipe automaticamente</td>
<td>Adicione automaticamente recursos planejados usando as funções associadas a uma tarefa. O dynamics 365 para operações sugere automaticamente recursos planejados usando vários critérios de decisões de teste baseada em funções. Depois que as funções e o esforço (horas) tenham sido definidos para as tarefas em uma WBS, e depois de a estrutura ter sido liberada, clique em <strong>Gerar equipe automaticamente</strong>. O número necessário de recursos planejados é adicionado à WBS e à guia <strong>Agendamento de projeto e equipe</strong>.</td>
</tr>
<tr class="odd">
<td>Recurso (lista suspensa)</td>
<td>Na página <strong>Iniciar atribuição de recursos</strong>, você pode selecionar recursos para reserva fixa ou reserva flexível com base na duração especificada. Você pode ajustar as configurações de exibição para ver e definir a duração de atividades de recurso. Você pode selecionar e atribuir recursos no nível do pacote de trabalho usando as seguintes opções:
<ul>
<li><strong>Aceitar</strong> – confirme as alterações feitas no recurso atribuído a uma tarefa.</li>
<li><strong>Cancelar</strong> – cancele as alterações feitas no recurso atribuído a uma tarefa.</li>
<li><strong>Atribua automaticamente</strong> – Esta opção selecionar um recurso provido disponível da equipe com uma função da tarefa selecionada.</li>
</ul></td>
</tr>
</tbody>
</table>

1.  ** Clique em gerenciamento e contabilidade de projeto ** &gt; ** projetos ** &gt; ** ** todos os projetos.
2.  Na lista, selecione o projeto **Fase de Atualização 2 de XYZ**.
3.  Clique ** plano ** &gt; ** atividades ** &gt; ** estrutura de detalhamento de trabalho **.
4.  Clique em **Nova** para adicionar as seguintes atividades de um único nível à WBS:
    -   Início
    -   Planejamento
    -   Executando
    -   Monitoramento e controle
    -   Fechar

5.  Definir datas e trabalho (horas), conforme mostrado a seguir de captura de tela. [![que define as datas e trabalho (]. /media/projectresourcing10.jpg)](. /media/projectresourcing10.jpg)
6.  Selecione a linha de tarefa **Início** e, no campo **Função**, selecione **Gerente de Projeto Sênior**.
7.  Clique em **Publicar**.
8.  Na mesma linha, no campo **Recurso**, selecione **Daniel Goldschmidt**.
9.  Clique em **Aceitar**.
10. Selecione a linha de tarefas **Planejamento** e, no campo **Função**, selecione **Analista de negócios**.
11. Clique em **Publicar** e clique em **Gerar equipe automaticamente**.
12. Na caixa de diálogo exibida, clique em **Sim**.
13. No campo **Recurso**, verifique se o valor é **Analista de negócios 1**.
14. Para o recurso **Analista de negócios 1**, abra a pesquisa e clique em **Iniciar formulário de atribuições de recurso**.
15. Selecione um trabalhador para a tarefa.
16. Clique ** atribuir de ** &gt; ** ** capacidade total.
17. Clique em **Salvar** e feche a página. 

> [!NOTE] 
> Você não receberá um aviso que o recurso especificado agora é 2, como o número de recursos em falta 1.
18. Na página **Estrutura de detalhamento de trabalho **, valide a atribuição de recursos na WBS e clique em **Salvar**.

## <a name="resource-fulfillment-for-planned-resources"></a>Preenchimento de recurso para recursos planejados
Um gerente de projeto pode planejar as funções necessárias do recurso para um projeto. O gerente de recurso verá esses recursos planejados como solicitações na página **Preenchimento de recurso** e poderá atribuir recursos reais.

1.  ** Clique em gerenciamento e contabilidade de projeto ** &gt; ** projetos ** &gt; ** ** todos os projetos.
2.  Na lista, selecione o projeto **Fase de Atualização 2 de XYZ**.
3.  Clique em **Projeto**.
4.  Clique em **Editar**.
5.  ** Equipe de projeto e plano ** na guia, clique ** ** ** ** adicionar.
6.  Na caixa de diálogo **Adicionar funções**, selecione a função **Desenvolvedor de software**.
7.  Clique em **Criar**.
8.  Feche a página do projeto.
9.  ** Clique em gerenciamento e contabilidade de projeto ** &gt; ** recursos de projetos ** &gt; ** ** preenchimento de recurso.
10. Selecione **Desenvolvedor de software 1** para o projeto**Fase 2 Fase do projeto de Atualização de XYZ**.
11. Selecione um trabalhador e clique em **Atribuir**.
12. Verifique se a linha de **Desenvolvedor de software 1** foi removida para o projeto **Fase 2 do projeto de Atualização de XYZ**.
13. Na guia **Equipe de projeto e agendamento** do projeto **Fase de atualização 2 de XYZ**, verifique se o trabalhador selecionado na etapa 11 foi adicionado como **Desenvolvedor de software**.

## <a name="requests-for-project-resources"></a>Solicitações para recursos de projetos
Os gerentes de recursos de suporte a funcionalidade do planejamento de recursos de projetos a proveram distribuir somente da equipe em recursos acoplamentos ou projetos. Para habilitar essa funcionalidade, conclua as seguintes tarefas ou verificá-las, que é preenchido.

-   Configure as sequências numéricas.
-   Configurar fluxos de trabalho de gerenciamento do projeto e contabilidade.
-   Habilitar o fluxo de trabalho do de recurso.

Depois que você verificar ou concluir as tarefas acima, você pode completar estas tarefas quando necessário.

-   Criar uma solicitação de um recurso de recurso provido equipe de macio- registrado.
-   Monitorar solicitações de recurso.
-   Atenda solicitações de recurso.
-   Solicitar um recurso provido de pessoal de WBS.
-   Inscrever recursos em um projeto sem uma solicitação de um recurso provido de equipe.

## <a name="monitor-project-teams"></a>Monitorar times de projeto
1.  ** Clique em gerenciamento e contabilidade de projeto ** &gt; ** projetos ** &gt; ** ** todos os projetos.
2.  Na lista de projetos, clique no link **ID do projeto** para o projeto **Fase de Atualização 2 de XYZ**.
3.  Na Guia Rápida **Equipe de projeto e agendamento**, verifique se os recursos de projetos listados estão corretos.




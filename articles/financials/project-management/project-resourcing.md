---
title: Recursos do projeto
description: "Este tópico fornece informações sobre recursos de projeto."
author: KimANelson
manager: AnnBe
ms.date: 09/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 2d31a5dfd16a4404e19c6c9693dacecff6f2f064
ms.contentlocale: pt-br
ms.lasthandoff: 03/26/2018

---

# <a name="project-resourcing"></a>Recursos do projeto

[!include[banner](../includes/banner.md)]

Este tópico fornece informações sobre recursos de projeto.

Um desafio para gerentes de projeto e gerentes de recursos durante a fase de planejamento do projeto é a atribuição de recursos, onde eles devem determinar e reservar o recurso correto para o trabalho em um projeto. No Microsoft Dynamics 365 for Finance and Operations, os recursos para projetos permitem definir as funções tratadas como recursos temporários que podem ser reservados para um compromisso específico ou parte de um compromisso. Esse tipo de recurso permite que os gerentes de projeto e gerentes de recursos concluam as seguintes tarefas:

- Definir uma função que tenha as competências necessárias para facilitar a correspondência de recursos.
- Usar funções para definir uma agenda de compromisso inicial baseada em recursos reservados.
- Estimar os custos e determinar um orçamento inicial com base em funções e em vários recursos para um projeto.
- Usar funções para estimar o número das reservas de recursos necessários para cada solicitação.
- Estimar o número de recursos necessários para todo o ciclo de vida de um projeto.
- Criar um rascunho de WBS (estrutura de detalhamento de trabalho) usando as atribuições de recursos iniciais.

[![Ciclo de vida de projeto](./media/projectresourcing02-1024x812.jpg)](./media/projectresourcing02.jpg)

À medida que o planejamento de projeto prosseguir, os recursos planejados poderão ser substituídos por recursos recrutados. O gerente de projeto também pode voltar e atualizar as reservas de recursos durante algum estágio do projeto.

## <a name="set-up-project-resources"></a>Configurar recursos do projeto
Você deve configurar um calendário e associá-lo a um funcionário ou a um trabalhador. O calendário é usado para agendar o projeto e o horário de trabalho dos recursos reservados para o projeto. Durante a configuração de calendário, os gerentes de projeto podem fazer o nivelamento de recursos como parte da otimização de recursos. Com base na agenda de calendário, as restrições podem ser colocadas nos recursos. Você pode configurar um calendário na página **Calendários**.

Quando você configura um trabalhador como um recurso de projeto, você pode selecionar os trabalhadores que trabalham na empresa para a qual você está configurando recursos. Se preferir, você pode selecionar trabalhadores de outras empresas de sua organização. Esses trabalhadores são conhecidos como recursos intercompanhia.

Os procedimentos a seguir explicam como configurar um trabalhador como um recurso de projeto em sua empresa e como configurar um recurso intercompanhia do projeto.

### <a name="set-up-a-worker-as-a-project-resource"></a>Configurar um trabalhador como um recurso do projeto

1. Na página **Trabalhadores**, na lista **Trabalhadores**, selecione o trabalhador que você está adicionando como um recurso de projeto e abra o registro do trabalhador.
2. No Painel de Ação, selecione **Projeto** &gt; **Configuração** &gt; **Configuração do projeto**.
3. Selecione um calendário e feche a página.

Você também pode especificar projetos padrão para um recurso como um tipo de atribuição prévia. As atribuições prévias podem ser usadas quando o gerente de recurso ou o gerente de projeto sabem com antecedência em quais projetos o recurso trabalhará. As atribuições prévias também podem ser baseadas na solicitação de um patrocinador ou de um cliente do projeto. Para atribuir um projeto previamente, na página **Atribuir projetos**, na guia **Projetos**, na lista **Projetos restantes**, selecione o projeto apropriado.

### <a name="set-up-an-intercompany-resource"></a>Configurar um recurso intercompanhia

Quando configurar um trabalhador como um recurso intercompanhia, você deve concluir a instalação na empresa de crédito e na empresa de empréstimo.

**Na empresa de crédito**

1. No Finance and Operations, verifique se a empresa de crédito está selecionada e conclua o procedimento da seção anterior, "Configurar um trabalhador como um recurso de projeto."
2. Na página **Contabilização intercompanhia** , selecione **Novo**.
3. No campo **ID de entidade legal**, selecione a empresa de crédito. Preencha os campos restantes conforme apropriado e selecione **Salvar**.
4. Na página **Transferir preço** , selecione **Novo**.
5. No campo **Entidade legal que toma o empréstimo**, selecione a empresa apropriada.
6. Para emprestar à empresa de empréstimo somente o recurso que você criou no início desta seção , no campo **Recurso**, selecione o nome do recurso criado. Para tornar todos os recursos na empresa de crédito disponíveis para a empresa de empréstimo, deixe o campo **Recurso** em branco.
7. Na página **Parâmetros de gerenciamento e contabilidade de projetos.**, na guia **Intercompanhia**, defina a opção **Habilitar quadro de horários e agendamento de recursos intercompanhia** como **Sim**.

**Na empresa de empréstimo**

- Na página **Lista de recursos**, no filtro de pesquisas, insira o nome do recurso que você criou para a empresa de crédito para verificar se o nome está incluído na lista de recurso da empresa de empréstimo.

## <a name="manage-resource-competencies"></a>Gerenciar competências do recurso
Competências de recurso são uma parte essencial do gerenciamento de recursos. As competências podem ser usadas como uma linha de base para determinar os recursos que tenham o equilíbrio correto de habilidades, de formação educacional, de certificação e da experiência de projeto. Você deve configurar essas informações para cada recurso e atualizá-las periodicamente. Dessa forma, você pode maximizar os recursos quando as competências específicas do recurso forem correspondidas durante a atribuição do recurso de projeto.

[![Exemplos de habilidades, certificações, educação e experiência de projeto](./media/projectresourcing06-1024x383.jpg)](./media/projectresourcing06.jpg)

Os procedimentos a seguir explicam como configurar algumas das competências para um recurso.

Para configurar as competências de um trabalhador, você pode usar a página de listagem **Trabalhadores** em Recursos humanos ou a página de listagem **Recursos** em Gerenciamento e contabilidade de projetos. Para os procedimentos a seguir, usaremos a página de listagem **Trabalhadores** em Recursos humanos.

### <a name="set-up-competencies-certificates"></a>Configurar competências: certificados

1. Na página de lista **Trabalhadores**, selecione a linha do trabalhador para a qual você está adicionando as informações de certificado.
2. No Painel de Ação, na guia **Trabalhador**, no grupo **Competências**, selecione **Certificados**.
3. Selecione **Novo**e, depois, no campo **Tipo do certificado** , selecione **PMP**.
4. No campo **Data inicial** , selecione **10/1/2015**, e selecione **Salvar**.

### <a name="set-up-competencies-skills"></a>Configurar competências: habilidades

1. Na página de listagem **Trabalhadores**, verifique se o trabalhador usado no procedimento anterior ainda está selecionado. Em seguida, no Painel de Ação, na guia **Trabalhador**, no grupo **Competências**, selecione **Habilidades**.
2. Selecione **Novo**.
3. No campo **Habilidade**, selecione **Gerenciamento de projetos**.
4. No campo **Nível**, selecione **5 Especialista**.
5. No campo **Data do nível**, selecione **14/1/2014**.
6. No campo **Anos de experiência**,insira **10**.
7. Selecione **Salvar** e feche a página.

## <a name="create-a-new-project"></a>Criar um novo projeto
1. Na página **Gerenciamento de projetos** , selecione **Novo projeto**, e insira os seguintes valores:

    - **Tipo de projeto:** Tempo e material
    - **Nome do projeto:** Fase de atualização 2 de XYZ
    - **Grupo de projetos:** TM\_WIP
    - **ID do contrato do projeto:** 00000002

2. Selecione **Criar projeto**.

### <a name="assign-a-resource-to-a-project"></a>Atribuir um recurso a um projeto

1. Na página **Trabalhadores**, na lista **Trabalhadores**, selecione o registro para o trabalhador para o qual você configurou competências anteriormente e abra o registro do trabalhador.
2. No Painel de Ação, na guia **Projeto**, no grupo **Configuração**, selecione **Atribuir projetos**.
3. Na página **Atribuições de projetos de validação de recursos**, na guia **Projetos**, no campo **Adicionar o projeto aos projetos selecionados**, filtre o projeto **Fase de atualização 2 de XYZ**.
4. No painel **Projetos restantes**, selecione um projeto e selecione o botão de seta para adicioná-lo ao painel **Projetos selecionados**.

Você também pode atribuir categorias para um recurso, conforme necessário. O tipo de categoria é **Custo** ou **Receita**. O tipo de categoria é determinado pela sua organização. Se não houver categorias atribuídas a um recurso, o Finance and Operations pesquisará a categoria padrão em preços por hora para custo e receita.

### <a name="set-up-project-resource-and-role-characteristics"></a>Configurar as características de recurso de projeto e de função

Um gerente de projeto pode usar a funcionalidade de recursos do projeto para criar as funções necessárias para um projeto. As funções podem ser usadas se os recursos confirmados ainda forem desconhecidos quando forem reservados. As funções podem ser reservadas temporariamente como recursos planejados, de forma que você possa prosseguir com os estágios de planejamento do projeto.

[![Exemplo de uma função](./media/projectresourcing05.jpg)](./media/projectresourcing05.jpg) 

**Cenário:** Exemplo de função Cenário: a Contoso foi contratado para concluir um projeto por Tempo e material com um estatuto de projeto aprovado. O gerente de projeto júnior ainda está concluindo o escopo do projeto. O gerente de recurso está identificando atualmente recursos específicos que serão reservados ao trabalho no novo projeto. Uma das funções solicitadas pelo patrocinador do projeto, por causa da natureza crítica do projeto, é de gerente de projeto sênior. O gerente de recurso deve adquirir o novo recurso e definir a função no sistema, caso o gerente de projeto júnior exija informações as informações do recurso durante o planejamento do projeto.

As etapas a seguir mostram como o gerente de recurso pode configurar a função de gerente de projeto sênior e associar características de recurso a ela. Posteriormente, a função poderá ser usada para procurar os recursos disponíveis que correspondam às competências necessários de recurso.

1. Na página **Funções de configuração** , selecione **Novo**, e insira os seguintes valores:

    - **ID da Função:** Gerente de projeto sênior
    - **Descrição:** Gerente de projeto sênior

2. Selecione **Criar**.
3. Selecione a função **Gerente de projeto sênior** e depois selecione **Configurar características**.
4. No campo **Tipo de característica**, selecione **Habilidade**.
5. No campo **Características disponíveis**, insira a habilidade que você está procurando.
6. No campo **Tipo de característica**, selecione **Certificado**.
7. No campo **Características disponíveis**, insira o tipo de certificado que você está procurando.

### <a name="assign-a-project-resource-to-a-project"></a>Atribuir um recurso de projeto a um projeto

1. Na página **Todos os projetos** , selecione o projeto **Fase de atualização 2 de XYZ** .
2. Na guia **Equipe do projeto e agendamento**, selecione **Adicionar**.
3. No campo **Função**, selecione **Membro da equipe**.
4. Selecione **Reservar do calendário**.
5. Na página **Disponibilidade de recursos**, selecione **Configurações de exibição**.
6. Na página **Ajustar configurações de exibição**, insira os seguintes valores:

    - **Formato da exibição do intervalo de datas:** Dia
    - **Exibir descrições de disponibilidade:** Sim
    - **Exibir capacidade restante:** Sim

7. Na lista de recursos, selecione um recurso.
8. Selecione **Reserva fixa** e **Capacidade total**.


### <a name="assign-a-resource-to-a-default-role"></a>Atribuir um recurso a uma função padrão

Para ajudar os gerentes de projeto ou de recurso, você pode fazer uma busca detalhada nos recursos que podem ser reservados a um projeto. Você pode associar uma função padrão a um recurso existente ou a um recurso adquirido mais recentemente. Por exemplo, quando Daniel foi contratado, ele tinha a experiência e as habilidades para preencher a função de Analista comercial. O gerente de recurso atribuiu essa função como a função padrão de Daniel. Assim, o gerente de recurso adicionou Daniel a um grupo de analistas comerciais que estão disponíveis para trabalhar nos projetos.

Durante a reserva de recursos, os gerentes de projeto podem filtrar os recursos de função disponíveis para trabalhar em projetos. Eles podem usar essas informações como um critério ao executarem análises de decisão de vários critérios durante o preenchimento de recursos. Também podem adicionar outras características do recurso ao filtro para pesquisar recursos que tenha habilidades, formação educacional e experiência específicas para um determinado projeto.

**Cenário:** Um projeto aprovado foi iniciado, e a função de Gerente de projeto sênior foi reservada como um recurso planejado durante o estágio de planejamento do projeto. O gerente de recurso adquiriu um recurso para preencher a função Gerente de projeto sênior.

1. Na página **Lista de recursos**, selecione **Daniel Goldschmidt**.
2. Na página **Função do recurso**, selecione **Novo** e informe os seguintes valores:

    - **Efetivo:** Informe a data atual.
    - **Expiração:** Informe **Nunca**.
    - **Função:** Informe **Gerente de projeto sênior**.

3. Selecione **Salvar** e feche a página.
4. Na guia **Competências**, adicione a habilidade **ProjectMgmt** e o certificado **PMP**.

## <a name="set-up-role-based-pricing"></a>Configurar preços baseados em função
Todos os preços de custo, de venda e de transferência podem ser configurados para funções.

1. Na página **Preço de venda - Hora**, selecione **Novo** e informe uma data de efetivação.
2. Na coluna **Função**, selecione uma função.
3. Na coluna **Preços**, insira um preço para a função de recurso selecionada.

## <a name="form-a-project-team"></a>Formar uma equipe de projeto
Para usar as funções que foram configuradas previamente em um projeto, um gerente de projeto deve associar as funções ao projeto. As diversas funções podem ser atribuídas para um projeto. Para evitar confusão, o Finance and Operations rotula automaticamente essas funções durante a reserva. Por exemplo, se o gerente de projeto quiser três engenheiros de software, três funções de engenheiro de software que têm **engenheiro de software 1**, **engenheiro de software 2** e **engenheiro de software 3** como rótulos, são gerados automaticamente. Se as características da função tiverem sido definidas anteriormente para a função, elas serão aplicadas como um filtro durante a pesquisa de recursos. Características adicionais podem ser adicionadas conforme necessário para refinar ainda mais a pesquisa.

As configurações de exibição também podem ser personalizadas para fornecer uma visão melhor de disponibilidade de capacidade. Há opções para mostrar a disponibilidade por hora, por dia, por semana, por mês, por trimestre e por ano. Há também uma opção para mostrar a capacidade disponível e restante dos recursos. Essa opção é útil para o gerenciamento de tempo, quando você estiver estimando as horas disponíveis para atividades ou a disponibilidade de capacidade.

O gerente de projeto pode selecionar uma função na página e, se houver um recurso disponível de acordo com a necessidade, selecionar para reservar um recurso para preencher a função. Observe que os recursos não precisam ser reservados nesse momento na fase de planejamento. Quando você cria um WBS, pode substituir funções pelos recursos recrutados do projeto. Se as funções forem substituídas pelos recursos recrutados no WBS, a configuração do recurso atualiza automaticamente a listagem e o agendamento da equipe do projeto.

[![Listagem da equipe de projeto que inclui as funções e os recursos reais](./media/projectresourcing03-1024x368.jpg)](./media/projectresourcing03.jpg) 

O gerente de projeto tem diversas opções para reservar um recurso para um projeto, como **Capacidade restante**, **Capacidade total**, **Porcentagem da capacidade** e **Especificar horas**. Essas opções de reserva poderão ser canceladas a qualquer momento se as atribuições de recursos forem alterados. Há dois tipos de reserva com suporte:

- **Reserva fixa** – A reserva de recursos foi aprovada e confirmada para trabalhar no compromisso pela duração especificada.
- **Reserva flexível** – As reservas de recursos foram definidas como uma tentativa para trabalhar no compromisso pela duração especificada.

O procedimento a seguir explica como criar uma equipe de projeto.

### <a name="create-a-project-team"></a>Criar uma equipe de projeto

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

## <a name="resource-capacity-synchronization"></a>Sincronização de capacidade do recurso
Os processos para ajudar a sincronização de recurso ajudam a garantir que as informações do calendário e do calendário base passem para o agendamento de recurso de projeto. Se o calendário for alterado, os processos farão as atualizações necessárias no agendamento dos recursos de projeto. Os processos também ajudam a melhorar o desempenho, pois as informações de recurso de calendário são previamente sincronizadas. Portanto, as atualizações para informações de recurso ocorrem mais rapidamente. Recomendamos que você agende os processos em lotes em vez de um de cada vez. Caso contrário, há o risco de que alguém se esqueça das datas inclusivas quando as informações foram sincronizadas pela última vez. Se as datas inclusivas não forem usadas, poderão ocorrer lacunas durante a sincronização de datas.

![Sincronização de calendário](./media/projectresourcing04-1024x471.jpg)

### <a name="synchronize-resource-capacity-roll-ups"></a>Sincronizar acúmulos de capacidade de recurso

O processo de sincronização é projetado para sincronizar todas as informações do calendário do recurso. Essas informações incluem informações do calendário base sobre todas as alterações na tabela de capacidade do calendário do recurso do projeto. Se novos recursos forem adicionados ao projeto, a sincronização ajuda a garantir que as informações atualizadas de calendário estejam disponíveis. Essa sincronização pode ser feita a qualquer momento.

É recomendável usar um lote. As opções estarão disponíveis durante a sincronização de reservas de capacidade.

1. Selecione **Gerenciamento e contabilidade de projeto** &gt; **Atividades periódicas** &gt; **Sincronização de capacidade** &gt; **Sincronizar acúmulos de capacidade de recursos**.
2. Defina as opções na seguinte tabela.

    | Opção      | descrição |
    |-------------|-------------|
    | Código de período | Se preferir, selecione o código de intervalo de datas da contabilidade para definir as datas inicial e final para o processo de sincronização para acúmulos de capacidade de recurso. |
    | Data de início  | Insira a data inicial para o processo de sincronização para acúmulos de capacidade de recurso. |
    | Data de término    | Insira a data final para o processo de sincronização para acúmulos de capacidade de recurso. |

[![Processo de sincronização](./media/projectresourcing09.jpg)](./media/projectresourcing09.jpg)

## <a name="set-up-roles-on-wbs-templates"></a>Configurar funções em modelos WBS
Os gerentes de projeto podem configurar modelos de WBS que podem ser aplicados durante a criação de uma WBS para novos projetos. Os gerentes de projeto podem adicionar funções ao criar um modelo. Use o procedimento a seguir para atribuir uma função a um modelo de WBS. 

1. Selecione **Gerenciamento e contabilidade de projeto** &gt; **Configuração** &gt; **Projetos** &gt; **Modelos de estrutura de detalhamento de trabalho**.
2. Selecione **Detalhes** para um modelo de WBS selecionado.
3. Selecione uma tarefa na lista e, no campo **Função**, selecione uma função para atribuir à tarefa.

### <a name="work-with-a-wbs"></a>Trabalhar com um WBS

Você pode criar um novo WBS ou pode copiar uma WBS de um modelo existente de WBS. Um gerente de projeto pode gerenciar os recursos ao atribuir funções às novas tarefas na WBS. As funções poderão ser substituídas depois que um recurso for adquirido ou depois que um recurso confirmado para trabalhar na tarefa for identificado. Essa flexibilidade permite que os gerentes de projeto executem as seguintes tarefas:

- Identificar o número de recursos necessários para os pacotes de trabalho WBS.
- Estimar custos de projeto.
- Determinar um orçamento preliminar.
- Estimar a duração da atividade com base em funções e em recursos.
- Desenvolver alguns planos de gerenciamento de projetos com base nas informações disponíveis sobre o projeto.

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
<td>Adicione automaticamente recursos planejados usando as funções associadas a uma tarefa. O Finanças e Operações sugere automaticamente recursos planejados usando vários critérios de análise de decisão baseados em funções. Depois que as funções e o esforço (horas) forem definidos para as tarefas em uma WBS e depois de a estrutura ter sido liberada, selecione <strong>Gerar equipe automaticamente</strong>. O número necessário de recursos planejados é adicionado à WBS e à guia <strong>Agendamento de projeto e equipe</strong>.</td>
</tr>
<tr class="odd">
<td>Recurso (lista suspensa)</td>
<td>Na página <strong>Iniciar atribuição de recursos</strong>, você pode selecionar recursos para reserva fixa ou reserva flexível com base na duração especificada. Você pode ajustar as configurações de exibição para ver e definir a duração de atividades de recurso. Você pode selecionar e atribuir recursos no nível do pacote de trabalho usando as seguintes opções:
<ul>
<li><strong>Aceitar</strong> – confirme as alterações feitas no recurso atribuído a uma tarefa.</li>
<li><strong>Cancelar</strong> – cancele as alterações feitas no recurso atribuído a uma tarefa.</li>
<li><strong>Atribuir automaticamente</strong> – Um recurso recrutado disponível que tem uma função correspondente é selecionado e atribuído automaticamente à tarefa selecionada.</li>
</ul></td>
</tr>
</tbody>
</table>

1. Na página **Todos os projetos** , selecione o projeto **Fase de atualização 2 de XYZ** .
2. Selecione **Plano** &gt; **Atividades** &gt; **Estrutura de detalhamento de trabalho**.
3. Selecione **Nova** para adicionar as seguintes atividades de um único nível à WBS:

    - Início
    - Planejamento
    - Executando
    - Monitoramento e controle
    - Fechar

4. Definir datas e trabalho (horas), conforme mostrado na ilustração.

    [![Configuração de datas e esforço](./media/projectresourcing10.jpg)](./media/projectresourcing10.jpg)

5. Selecione a linha de tarefa **Início** e, no campo **Função**, selecione **Gerente de Projeto Sênior**.
6. Selecione **Publicar**.
7. Na mesma linha, no campo **Recurso**, selecione **Daniel Goldschmidt** e, em seguida, **Aceitar**.
8. Selecione a linha de tarefas **Planejamento** e, no campo **Função**, selecione **Analista de negócios**.
9. Selecione **Publicar** e selecione **Gerar equipe automaticamente**.
10. Na caixa de mensagem exibida, selecione **Sim**.
11. No campo **Recurso**, verifique se o valor é **Analista de negócios 1**.
12. Para o recurso **Analista de negócios 1**, abra a pesquisa e selecione **Iniciar atribuições de recurso**. Em seguida, selecione um trabalhador para a tarefa.
13. Selecione **Atribuição flexível** &gt; **Capacidade total**.

    > [!NOTE] 
    > Você não receberá um aviso de que o recurso especificado agora é 2 porque o número de recursos permanece em 1.

14. Na página **Estrutura de detalhamento de trabalho**, valide a atribuição de recursos na WBS e selecione **Salvar**.

## <a name="resource-fulfillment-for-planned-resources"></a>Preenchimento de recurso para recursos planejados
Um gerente de projeto pode planejar as funções necessárias do recurso para um projeto. O gerente de recurso verá esses recursos planejados como solicitações na página **Preenchimento de recurso** e poderá atribuir recursos reais.

1. Na página **Todos os projetos** , selecione o projeto **Fase de atualização 2 de XYZ** .
2. Selecione **Projeto**, e **Editar**.
3. Na guia **Equipe do projeto e agendamento**, selecione **Adicionar**.
4. Na caixa de diálogo **Adicionar funções**, selecione a função **Desenvolvedor de software**.
5. Selecione **Criar** e feche a página do projeto.
6. Na **Preenchimento de recurso** , selecione **Desenvolvedor de software 1** para o projeto **Fase 2 Fase do projeto de Atualização de XYZ** .
7. Selecione um trabalhador e **Atribuir**.
8. Verifique se a linha de **Desenvolvedor de software 1** foi removida para o projeto **Fase 2 do projeto de Atualização de XYZ**.
9. Na guia **Equipe de projeto e agendamento** do projeto **Fase de atualização 2 de XYZ**, verifique se o trabalhador selecionado na etapa anterior foi adicionado como **Desenvolvedor de software**.

## <a name="requests-for-project-resources"></a>Solicitações de recursos de projeto
A funcionalidade de agendamento do recurso de projeto permite apenas gerentes de recurso para distribuir recursos recrutados em compromissos ou projetos. Para habilitar essa funcionalidade, conclua as seguintes tarefas ou verifique se elas foram preenchidas:

- Configure as sequências numéricas.
- Configurar fluxos de trabalho para gerenciamento e contabilidade de projetos.
- Habilitar fluxos de trabalho de solicitação de recurso.

Depois que as tarefas precedentes forem concluídas, você pode completar estas tarefas quando necessário:

- Criar uma solicitação de um recurso recrutado de modo flexível
- Monitorar solicitações de recurso.
- Preencher solicitações de recurso.
- Solicitar um recurso recrutado de uma WBS.
- Inscrever recursos a um projeto sem ter uma solicitação de um recurso recrutado.

## <a name="monitor-project-teams"></a>Monitorar equipes de projeto
1. Na página **Todos os projetos**, selecione o link **ID do projeto** para o projeto **Fase de atualização 2 de XYZ**.
2. Na Guia Rápida **Equipe de projeto e agendamento**, verifique se os recursos de projetos listados estão corretos.


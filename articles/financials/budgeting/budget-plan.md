---
title: "Planejamento de orçamento"
description: "O objetivo deste laboratório é fornecer uma visualização guiada das atualizações de funcionalidade do Microsoft Dynamics 365 for Finance and Operations na Área de planejamento de orçamento. A intenção deste laboratório é ilustrar um exemplo rápido de configuração de módulo de planejamento de orçamento e exibir como o planejamento de orçamento pode ser alcançado usando esta configuração.  Este laboratório focará especificamente nos processos empresariais a seguir ou tarefas -    - Criar hierarquia organizacional para planejamento de orçamento e configuração de segurança do usuário   - Definir cenários de plano de orçamento, colunas de plano de orçamento, layouts e modelos do Excel   - Criar e ativar processo de planejamento de orçamento   - Criar documento de plano de orçamento extraindo os reais de Contabilidade   - Usar alocações para ajustar dados de documento de plano de orçamento   - Editar dados de documento de plano de orçamento no Excel"
author: twheeloc
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BudgetPlanningConfiguration
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 10763
ms.assetid: 0f2ba752-1f6d-4f28-b9e9-b2e97d10b6d1
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 59781da7681ece1c0c013f59e0d1a5d7efc51c3a
ms.contentlocale: pt-br
ms.lasthandoff: 03/26/2018

---

# <a name="budget-planning"></a>Planejamento de orçamento

[!include[banner](../includes/banner.md)]


O objetivo deste laboratório é fornecer uma visualização guiada das atualizações de funcionalidade do Microsoft Dynamics 365 for Finance and Operations na Área de planejamento de orçamento. A intenção deste laboratório é ilustrar um exemplo rápido de configuração de módulo de planejamento de orçamento e exibir como o planejamento de orçamento pode ser alcançado usando esta configuração.  Este laboratório focará especificamente nos processos empresariais a seguir ou tarefas -    - Criar hierarquia organizacional para planejamento de orçamento e configuração de segurança do usuário   - Definir cenários de plano de orçamento, colunas de plano de orçamento, layouts e modelos do Excel   - Criar e ativar processo de planejamento de orçamento   - Criar documento de plano de orçamento extraindo os reais de Contabilidade   - Usar alocações para ajustar dados de documento de plano de orçamento   - Editar dados de documento de plano de orçamento no Excel 

<a name="prerequisites"></a>Pré-requisitos 
------------------

Para este tutorial, você precisará acessar o ambiente Finance and Operations com dados de demonstração da Contoso e deve ser definido como administrador na instância. Não use no modo particular para este laboratório - se necessário, faça logoff de outra conta no navegador e faça logon com as credenciais de administrador do Finance and Operations. Para fazer logon no Finance and Operations, você **DEVE** marcar a caixa de seleção "Mantenha-me conectado". Isso cria um cookie persistente necessário para o Excel App. Se você fizer login no Finance and Operations usando um navegador diferente do IE, o sistema solicitará que você faça login no aplicativo Excel. Quando você clica em “Login” no App Excel, uma janela pop-up de IE é aberta e, ao fazer login, você **DEVE** marcar a caixa de seleção "Manter-me conectado”. Se, ao clicar em "Login" no Excel App, nada acontecer, você deverá limpar o cache de cookies no IE.

## <a name="scenario-overview"></a>**Visão geral do cenário**
Julia funciona como um gerente financeira na Contoso Entertainment Systems na Alemanha (DEMF). Como o FY2016 se aproxima, ela precisa trabalhar na configuração do orçamento da empresa para o próximo ano. Aspectos de preparação:

1.  Julia os valores reais do ano anterior como ponto de partida para criar o orçamento.
2.  Com base nos números reais do ano anterior, ela cria previsões para os 12 meses do próximo ano
3.  Julia examinar o orçamento com CFO. Depois de fazer isso, ela faz ajustes necessários para o plano do orçamento e finaliza a preparação do orçamento.

O esquema de configurações do planejamento do orçamento para o cenário tem a seguinte aparência:

![Esquema de configuração de planejamento de orçamento](./media/screenshot1-300x152.png)

Julia usa o seguinte modelo do Excel para preparar o orçamento:

[![Modelo do Excel](./media/screenshot2-1024x352.png)](./media/screenshot2.png)

## <a name="exercise-1-configuration"></a>Ano 1: Configuração

### <a name="task-1-create-organizational-hierarchy"></a>**Tarefa 1: Criar hierarquia organizacional**
Como todo o processo de orçamento ocorre no departamento financeiro, Julia precisa criar uma hierarquia organizacional muito simples – consistindo no departamento financeiro apenas. 1.1. Navegar para as hierarquias da organização (Administração da organização &gt; Organizações &gt; Hierarquias da organização) e clique no botão Novo

![Hierarquia da organização](./media/screenshot3.png) 

1.2. Digite o nome da hierarquia organizacional e clique no botão Atribuir finalidade

[![Nome](./media/screenshot4.png)](./media/screenshot4.png) 

1.3. Selecione a finalidade do planejamento do orçamento, clique no botão Adicionar e atribuir uma hierarquia organizacional recém-criada: 

[![Atribuir finalidade](./media/screenshot5.png)](./media/screenshot5.png)

1.4. Repita a etapa acima para a finalidade da Segurança organizacional. Feche o formulário quando terminar.

[![Organização de segurança](./media/screenshot6.png)](./media/screenshot6.png)

1.5. No formulário Hierarquias organizacionais, clique no botão Visualizar. Clique em Editar na criação da hierarquia e crie uma hierarquia ao clicar no botão Inserir.

[![Inserir](./media/screenshot7.png)](./media/screenshot7.png) 

1.6. Selecione Departamento financeiro para a hierarquia de orçamento. 

[![Finanças](./media/screenshot8.png)](./media/screenshot8.png)

1.7. Quando feito, clique no botão Publicar e Fechar. Selecione 1/1/2015 como a data efetiva para a publicação da hierarquia.

[![Data de efetivação](./media/screenshot9.png)](./media/screenshot9.png)

### <a name="task-2-configure-user-security"></a>Tarefa 2: Configurar segurança do usuário
O planejamento do orçamento usa políticas de segurança especiais para configurar o acesso aos dados de planejamento do orçamento. Julia precisa conceder a si mesma os planejamentos financeiros do orçamento. 

2.1. Alterne para o contexto da entidade legal do DEMF. 


2.2. Navegue até Orçamento &gt; Configuração &gt; Planejamento do orçamento &gt; Configuração do planejamento do orçamento. Na guia Parâmetros, defina o valor do modelo de segurança com base nas organizações de segurança 

[![Parâmetros](./media/screenshot11.png)](./media/screenshot11.png) 

2.3. Navegue até Administração do sistema &gt; Usuários &gt; Usuários. Dê ao usuário Admin (Julia Funderburk) a função de gerente de orçamentos. 

[![Gerente de orçamentos](./media/screenshot12.png)](./media/screenshot12.png) 

2.4. Escolha a função do usuário e clique em Atribuir organizações 

[![Atribuir organizações](./media/screenshot13.png)](./media/screenshot13.png)

2.5. Selecione "Conceder acesso a organizações específicas". Escolha a hierarquia organizacional criada na primeira etapa. Escolha o Nó de finanças e clique no botão Conceder com filhos 

***Importante!*** *Verifique se você está no contexto da entidade legal DEMF ao executar essa tarefa, já que a segurança da organização é aplicada por entidade legal* 

[![Conceder acesso](./media/screenshot14.png)](./media/screenshot14.png)

### <a name="task-3-create-scenarios"></a>Tarefa 3: Criar cenários
3.1. Navegue até Orçamento&gt;Configuração &gt; Planejamento do orçamento &gt; Configuração do planejamento do orçamento. Na página Cenários, anote os cenários que vamos usar posteriormente neste laboratório: Números reais e valores orçados do ano anterior. 

*Nota: É possível criar novos cenários para este ano, se desejado, e usar esses item.* 

[![Novos cenários](./media/screenshot15.png)](./media/screenshot15.png) 

*Observação: como Julia não está usando o processo de aprovação formal para a preparação do orçamento, ignoraremos a configuração das etapas Fluxos de trabalho, Estágios e Fluxo de trabalho neste laboratório e usaremos a configuração existente para o fluxo de trabalho Aprovar automaticamente. Consulte o apêndice desta configuração de fluxo de trabalho.*

### <a name="task-4-create-budget-plan-columns"></a>Tarefa 4: Criar colunas do plano de orçamento
As colunas do plano de orçamento são as colunas monetárias ou de quantidade que podem ser usadas no layout de documento do plano de orçamento. Nosso no exemplo é necessário criar uma coluna para os números reais do ano anterior e 12 colunas para representar cada mês no ano orçado. As colunas podem ser criadas ao clicar no botão Adicionar e preencher os valores ou com a ajuda de uma entidade de dados. Neste laboratório, usaremos a entidade de dados para preencher os valores. 

4.1. Em Orçamento&gt;Configuração &gt; Planejamento do orçamento &gt; Configuração do planejamento do orçamento, abra a página Colunas. Clique no botão Office, no canto superior direito do formulário e escolha Colunas (não filtrado) 

[![Colunas não filtradas](./media/screenshot16.png)](./media/screenshot16.png) 

4.2. O sistema abrirá a pasta de trabalho do Excel para ser usada ao preencher os valores. Se solicitado, clique em Habilitar Edição e Confiar neste aplicativo 

[![Habilitar edição](./media/screenshot18.png)](./media/screenshot18.png) 

[![Confiar neste aplicativo](./media/screenshot17.png)](./media/screenshot17.png)

4.3. Serão necessárias mais colunas para preencher os valores. Clique em Criar no painel direito para adicionar as colunas à grade: 

[![Criar](./media/screenshot19.png)](./media/screenshot19.png) 

4.4. Clique no botão de lápis ao lado de PlanColumns para ver as colunas disponíveis para adicionar à grade 

[![Editar](./media/screenshot20.png)](./media/screenshot20.png) 

4.5. Clique duas vezes em cada campo disponível para adicioná-las aos Campos selecionados e clique em Atualizar 

![Atualização](./media/screenshot21.png)](./media/screenshot21.png) 

4.6. Na tabela do Excel, adicione todas as colunas necessárias para serem criadas. Use o recurso de Preenchimento Automático no Excel para adicionar as linhas de maneira rápida. Verifique se as linhas são adicionadas como parte da tabela (ao usar rolagem vertical, você deve ver cabeçalhos das colunas na parte superior da grade) 

[![Preenchimento Automático](./media/screenshot22.png)](./media/screenshot22.png) 

4.7. Retorne ao Finance and Operations e atualize a página. Valores publicados aparecerão no Finance and Operations. 

[![Atualizar](./media/screenshot23.png)](./media/screenshot23.png)

### <a name="task-5-create-budget-plan-document-layouts-and-templates"></a>Tarefa 5: Criar um layouts e modelos para o documento do planejamento do orçamento
O layout define como as linhas grade de documento do plano de orçamento serão exibidas quando o usuário abrir o documento do plano de orçamento. Também é possível alternar o layout para o documento do plano de orçamento para ver os mesmos dados em ângulos diferentes. Agora, como há colunas definidas que podem ser usadas em seu documento do plano de orçamento, Julia deve criar um layout do documento do plano de orçamentos, que se assemelhe à tabela do Excel usada para criar dados do orçamento (consulte visão geral do Cenário na seção neste laboratório) 

5.1. Em Orçamento&gt;Configuração &gt; Planejamento do orçamento &gt; Configuração do planejamento do orçamento, abra a página Layouts. Crie um novo layout para a entrada de orçamento mensal:

-   Escolha o conjunto de dimensões de MA+BU para incluir contas principais e unidades de negócios no layout.
-   Liste todas as colunas do plano de orçamento criadas na etapa anterior na seção Elementos. Faça com que todos os dados, exceto os números do ano anterior, sejam editáveis.
-   Clique no botão Descrições para selecionar quais dimensões financeiras devem ser exibidas em Descrições na grade.

[![Descrições](./media/screenshot24.png)](./media/screenshot24.png) 

Com base na definição do layout do plano do orçamento, criamos um modelo do Excel que será usado como uma alternativa para editar dados do Orçamento. Como o modelo do Excel deve corresponder à definição do layout do plano de orçamento, você não poderá editar o layout do plano de orçamento depois de gerar o modelo do Excel, pois esta tarefa deve ser realizada depois que todos os componentes foram definidos. 

5.2. Para o layout criado na etapa 5.1 clique no botão Modelo &gt; Gerar. Confirme a mensagem de aviso. Para visualizar o modelo, clique em Modelo &gt; Visualizar. 

*Observação: não deixe de selecionar “Salvar como” e selecionar o lugar em que o modelo deve ser armazenado para a edição. Se o usuário selecionar "Abrir" na caixa de diálogo sem salvar, as alterações feitas no arquivo não serão retidas quando o arquivo for fechado.* 
[![Exibição do modelo](./media/screenshot25.png)](./media/screenshot25.png) 

5.3. &lt; Etapa opcional&gt; Modificar modelo do Excel para ter uma melhor aparência – adicionar fórmulas totais, campos do cabeçalho, formatações etc. Salvar as alterações e carregar o arquivo para o layout do plano do orçamento ao clicar em Layout &gt; Carregar [![Carregar](./media/screenshot26.png)](./media/screenshot26.png)

### <a name="task-6-create-a-budget-planning-process"></a>Tarefa 6: Criar um processo de planejamento do orçamento
Julia precisa criar e ativar um novo processo de planejamento de orçamento que combina a configuração acima para iniciar inserindo planos de orçamento. O processo de planejamento de orçamento define para que as organizações, o fluxo de trabalho, os layouts e os modelos de orçamento serão usados ao criar planos de orçamento. 

6.1. Navegue até Orçamento &gt; Configuração &gt; Planejamento do orçamento &gt; Processo de planejamento do orçamento e crie um novo registro.

-   Processo de planejamento do orçamento – FY2016 do orçamento DEMF
-   Ciclo do orçamento - FY2016
-   Ledger – DEMF
-   Estrutura da conta padrão – P&L de fabricação
-   Hierarquia organizacional – escolha a hierarquia criada no início do laboratório
-   Fluxo de trabalho do planejamento do orçamento - atribuir Automático - Aprovar fluxo de trabalho para o departamento financeiro
-   Nas regras e modelos do estágio de planejamento do orçamento, para cada escolha do estágio de planejamento do orçamento, se Adicionar linhas e Modificar linhas estiver permitido e qual Layout deve ser usado por padrão

*Observação: Você pode criar outros layouts de documento e atribuir disponibilidade no estágio do fluxo de trabalho do planejamento do orçamento ao clicar no botão Alternar layouts.* 

[![Layouts alternativos](./media/screenshot27.png)](./media/screenshot27.png) 

6.2. Selecione Ações &gt; Ativar para ativar este fluxo de trabalho do planejamento do orçamento 

[![Ativar](./media/screenshot28.png)](./media/screenshot28.png)

## <a name="exercise-2-process-simulation"></a>Ano 2: Simulação do processo

### <a name="task-7-generate-initial-data-for-budget-plan-from-general-ledger"></a>Tarefa 7: Gerar dados iniciais para o plano do orçamento na contabilidade
7.1. Navegue até Orçamento &gt; Periódico &gt; Gerar plano do orçamento na contabilidade. Preencha os parâmetros do processo do periódico e clique no botão Gerar. 

[![Gerar](./media/screenshot29.png)](./media/screenshot29.png) 

7.2. Navegue até Orçamento &gt; Planos do orçamento para localizar um plano do orçamento criado por Gerar processo. 

[![Plano de orçamento](./media/screenshot30.png)](./media/screenshot30.png) 

7.3. Abra os detalhes do documento ao clicar no hiperlink do número do documento. O plano de orçamento é exibido como definido no layout criado durante este laboratório 

[![Exibição de plano de orçamento](./media/screenshot31.png)](./media/screenshot31.png)

### <a name="task-8-create-current-year-budget-based-on-previous-year-actuals"></a>Tarefa 8: Crie o orçamento do ano atual com base nos números reais do ano anterior
Os métodos de alocação podem ser usados no plano de orçamento para copiar facilmente as informações para os planos do orçamento de um cenário para outro/ colá-las nos períodos/alocar para dimensões. Usaremos alocações para criar o orçamento do ano atual a partir de números reais do ano anterior. 

8.1. Selecione todas as linhas na grade do documento do plano do orçamento e clique no botão alocar orçamento 

[![Todas as linhas](./media/screenshot32.png)](./media/screenshot32.png) 

8.2. Selecione o método da alocação, a chave do período, os cenários de origem e destino e clique em Alocar 

[![Alocar](./media/screenshot33.png)](./media/screenshot33.png)

Os valores reais do ano anterior serão copiados no orçamento do ano atual e alocados em períodos por meio da chave do período da curva de vendas. 

[![Curva de vendas](./media/screenshot34.png)](./media/screenshot34.png)

### <a name="task-9-adjust-budget-plan-document-using-excel-and-finalize-the-document"></a>Tarefa 9: Ajustar o documento do plano do orçamento usando o Excel e finalizar o documento
9.1. Clique na planilha Botão para abrir o conteúdo do documento no Excel

[![Excel](./media/screenshot35.png)](./media/screenshot35.png)

9.2. Quando a pasta de trabalho do Excel for aberta, ajuste os número do documento do plano do orçamento e clique no botão Publicar.

[![Publicar](./media/screenshot36.png)](./media/screenshot36.png)

9.3. Voltar para o documento no plano do orçamento no Finance and Operations. Clique em Fluxo de trabalho &gt; Enviar para aprovar o documento automaticamente

[![Aprovar automaticamente](./media/screenshot37.png)](./media/screenshot37.png) 

Depois que o fluxo de trabalho é concluído, o estágio do documento do plano do orçamento é alterado para Aprovado. [![Aprovado](./media/screenshot38.png)](./media/screenshot38.png)

## <a name="appendix"></a>Anexo

### <a name="auto-approve-workflow-configuration"></a>Configuração do luxo de trabalho de aprovação automática

A. Orçamento &gt; Configuração &gt; Planejamento do orçamento &gt; Fluxos de trabalho do orçamento Crie um novo fluxo de trabalho usando os fluxos de trabalho do planejamento do orçamento:

[![Criar um novo fluxo de trabalho](./media/screenshot39.png)](./media/screenshot39.png)

Este fluxo de trabalho conterá somente uma tarefa – plano do orçamento de transição do estágio 

[![Plano de orçamento da transição de fases](./media/screenshot40.png)](./media/screenshot40.png) 

Salve e ative o fluxo de trabalho. 

B. Navegue até Orçamento &gt; Configuração &gt; Planejamento do orçamento &gt; Configuração do planejamento do orçamento. Na guia Estágios, crie 2 estágios - Inicial e Enviado 

[![Inicial e enviado](./media/screenshot41.png)](./media/screenshot41.png)

C. Navegue até Orçamento &gt; Configuração &gt; Planejamento do orçamento &gt; Configuração do planejamento do orçamento. Na guia Estágios do fluxo de trabalho, associe a aprovação automática do fluxo de trabalho criada na etapa A aos estágios Inicial e Enviado 

[![Orçamento e planejamento de orçamento](./media/screenshot42.png)](./media/screenshot42.png)  





---
title: "Planejamento de orçamento"
description: "O objetivo de laboratório este é fornecer uma exibição guiada Microsoft Dynamics 365 para atualizações da funcionalidade das operações na área de planejamento de orçamento. A intenção deste laboratório é ilustrar um exemplo rápido de configuração de módulo de planejamento de orçamento e exibir como o planejamento de orçamento pode ser alcançado usando esta configuração.  Este centrar-se-á laboratório especificamente sobre os seguintes processos comerciais ou de tarefas - - criando a hierarquia organizacional para o planejamento de orçamento que configuram e a segurança do usuário - cenários definição de planos de orçamento, colunas de orçamento, plano de layouts e modelos Excel - criar e ativar o processo de planejamento de orçamento - criar o documento de plano de orçamento recebendo em números reais da contabilidade - usando alocações para ajustar os dados do documento de plano de orçamento - dados do documento de plano de orçamento editar Excel"
author: twheeloc
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 10763
ms.assetid: 0f2ba752-1f6d-4f28-b9e9-b2e97d10b6d1
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: 81b44aa7af3a05ebc28963f406fab98bfbbb340d
ms.lasthandoff: 03/31/2017


---

# <a name="budget-planning"></a>Planejamento de orçamento

O objetivo de laboratório este é fornecer uma exibição guiada Microsoft Dynamics 365 para atualizações da funcionalidade das operações na área de planejamento de orçamento. A intenção deste laboratório é ilustrar um exemplo rápido de configuração de módulo de planejamento de orçamento e exibir como o planejamento de orçamento pode ser alcançado usando esta configuração.  Este centrar-se-á laboratório especificamente sobre os seguintes processos comerciais ou de tarefas - - criando a hierarquia organizacional para o planejamento de orçamento que configuram e a segurança do usuário - cenários definição de planos de orçamento, colunas de orçamento, plano de layouts e modelos Excel - criar e ativar o processo de planejamento de orçamento - criar o documento de plano de orçamento recebendo em números reais da contabilidade - usando alocações para ajustar os dados do documento de plano de orçamento - dados do documento de plano de orçamento editar Excel 

<a name="prerequisites"></a>Pré-requisitos 
------------------

Tutorial deste, precisará acessar o dynamics 365 do ambiente de operações com dados de demonstração de A Contoso, e seja provisionado como um administrador na instância. Não use em particular o modo de navegador para este laboratório - desconectar de qualquer outra conta no navegador se necessário conectar com 365 para dynamics credenciais do administrador de operações. Para assinar em dynamics 365 para operações, você DEVA ** ** verifica “” mante-me conectou a caixa de seleção. Isso cria um cookie persistente necessário para o Excel App. Quando você entra o dynamics 365 para as operações usando um navegador diferente o IE, você será solicitado a conectarem-se descritivo no Excel. Quando você clica em “Login” no App Excel, uma janela pop-up de IE é aberta e, ao fazer login, você **DEVE** marcar a caixa de seleção "Manter-me conectado”. Se, ao clicar em "Login" no Excel App, nada acontecer, você deverá limpar o cache de cookies no IE.

## <a name="scenario-overview"></a>**Scenario overview**
Julia funciona como um gerente financeira na Contoso Entertainment Systems na Alemanha (DEMF). Como o FY2016 se aproxima, ela precisa trabalhar na configuração do orçamento da empresa para o próximo ano. Aspectos de preparação:

1.  Julia os valores reais do ano anterior como ponto de partida para criar o orçamento.
2.  Com base nos números reais do ano anterior, ela cria previsões para os 12 meses do próximo ano
3.  Julia examinar o orçamento com CFO. Depois de fazer isso, ela faz ajustes necessários para o plano do orçamento e finaliza a preparação do orçamento.

De orçamento o esquema de configuração de planejamento para os aspectos do cenário a seguir:

![Captura de tela 1](./media/screenshot1-300x152.png)

Julia usa o seguinte modelo De O excel para preparar o orçamento:

[![](./media/screenshot2-1024x352.png)](./media/screenshot2.png)

<a name="exercise-1-configuration"></a>Ano 1: Configuração
=========================

## <a name="task-1-create-organizational-hierarchy"></a>** Tarefa 1: Crie a hierarquia organizacional **
Como todo o processo de orçamento ocorre no departamento financeiro, Julia precisa criar uma hierarquia organizacional muito simples – consistindo no departamento financeiro apenas. 1.1. Navegar as hierarquias organizacionais (hierarquias organizacionais de organizações &gt; administração &gt; organizacional e clique no botão

![Captura de tela 3](./media/screenshot3.png) 

1.2. Digite o nome da hierarquia organizacional e clique na finalidade de alocar de botões

[![(Screenshot4]. captura de 4.png]) /media/screen(. captura de 4.png /media/screen) 

1.3. A finalidade de planejamento dos orçados botão, clique em adicionar e atribuir uma nova hierarquia organizacional: 

[![(Screenshot5]. captura de 5.png]) /media/screen(. captura de 5.png /media/screen)

1.4. Repita a etapa acima para a finalidade da Segurança organizacional. Feche o formulário quando terminar.

[![(Screenshot6]. captura de 6.png]) /media/screen(. captura de 6.png /media/screen)

1.5. No formulário Hierarquias organizacionais, clique no botão Visualizar. Clique em Editar na criação da hierarquia e crie uma hierarquia ao clicar no botão Inserir.

[![(Screenshot7]. captura de 7.png]) /media/screen(. captura de 7.png /media/screen) 

1.6. Selecione Departamento financeiro para a hierarquia de orçamento. 

[![(Screenshot8]. captura de 8.png]) /media/screen(. captura de 8.png /media/screen)

1.7. Quando feito, clique no botão Publicar e Fechar. Selecione 1/1/2015 como a data efetiva para a publicação da hierarquia.

[![(Screenshot9]. captura de 9.png]) /media/screen(. captura de 9.png /media/screen)

## <a name="task-2-configure-user-security"></a>Tarefa 2: Configurar segurança do usuário
O planejamento do orçamento usa políticas de segurança especiais para configurar o acesso aos dados de planejamento do orçamento. Julia precisa conceder a si mesma os planejamentos financeiros do orçamento. 2.1. Alternar o contexto de entidade legal de DEMF: [![(Screenshot10]. captura de 10.png]) /media/screen(. captura 10.png /media/screen) de 2.2. Navegar na configuração &gt; do &gt; orçamento de previsão de &gt; orçamento de previsão de orçamento de configuração. Na guia parâmetros, defina o valor do modelo de segurança com base em organizações de segurança [![(Screenshot11]. captura de 11.png]) /media/screen(. captura 11.png /media/screen) de 2.3. Navegar para usuários &gt; de usuários &gt; de administração de sistema. Dê ao usuário Admin (Julia Funderburk) a função de gerente de orçamentos. [![(Screenshot12]. captura de 12.png]) /media/screen(. captura 12.png /media/screen) de 2.4. Organizações de atribuição de funções de usuário e clique em [de separação (![Screenshot13]. captura de 13.png]) /media/screen(. captura 13.png /media/screen) de 2.5. Selecione "Conceder acesso a organizações específicas". Escolha a hierarquia organizacional criada na primeira etapa. Escolha o nó de finanças e Conceda clique com o botão de *** filho importante! *** * – Verifique se você está no contexto de entidade legal de DEMF para executar esta tarefa, como a segurança organizacional for aplicado por entity* legal [![(Screenshot14]. captura de 14.png]) /media/screen(. captura de 14.png /media/screen)

## <a name="task-3-create-scenarios"></a>Tarefa 3: Criar cenários
3.1. Navegar na configuração&gt;&gt; de planejamento de &gt; orçamento de previsão de orçamento de BudgetingSetup. Na página Cenários, anote os cenários que vamos usar posteriormente neste laboratório: Números reais e valores orçados do ano anterior. *Nota: É possível criar novos cenários para este ano, se desejado, e usar esses item.* [![(Screenshot15]. captura de 15.png]) /media/screen(. *Note de captura de 15.png /media/screen): como Julia não estiver usando o processo de aprovação formal da preparação de orçamento, a configuração é ignoraremos fluxos de trabalho, os estágios e os estágios do fluxo de trabalho neste e laboratório usaremos de instalação existente para o automóvel – aprove o fluxo de trabalho. Consulte o apêndice para o fluxo de trabalho configuration.*

## <a name="task-4-create-budget-plan-columns"></a>Tarefa 4: Criar colunas do plano de orçamento
As colunas do plano de orçamento são as colunas monetárias ou de quantidade que podem ser usadas no layout de documento do plano de orçamento. Nosso no exemplo é necessário criar uma coluna para os números reais do ano anterior e 12 colunas para representar cada mês no ano orçado. As colunas podem ser criadas ao clicar no botão Adicionar e preencher os valores ou com a ajuda de uma entidade de dados. Neste laboratório, usaremos a entidade de dados para preencher os valores. 4.1. Na&gt;&gt; página colunas abertas &gt; de configuração de planejamento de orçamento de previsão de orçamento de BudgetingSetup. Botão de O Office clique em no canto superior direito colunas do formulário e de separação (não) [filtradas![(Screenshot16]. captura de 16.png]) /media/screen(. captura 16.png /media/screen) de 4.2. O sistema abrirá a pasta de trabalho do Excel para ser usada ao preencher os valores. Se solicitado, clique em editar e habilita confiar este descritivo [![(Screenshot18]. captura de 18.png]) /media/screen(. captura 18.png) [] do![Screenshot17 (/media/screen. captura de 17.png]) /media/screen(. captura 17.png /media/screen) de 4.3. Nós precisaremos mais colunas de preencher os valores. Clique no Design do painel do lado direito para adicionar colunas à grade: [![(Screenshot19]. captura de 19.png]) /media/screen(. captura 19.png /media/screen) de 4.4. Clique no botão de lápis ao lado de PlanColumns para ver disponíveis para adicionar colunas à grade [![(Screenshot20]. captura de 20.png]) /media/screen(. captura 20.png /media/screen) de 4.5. Clique duplo fazer em cada campo disponível para adiciona-los campos selecionados e a atualização do![Screenshot21 clique em []. (captura de 21.png]) /media/screen(. captura 21.png /media/screen) de 4.6. Na tabela do Excel, adicione todas as colunas necessárias para serem criadas. Use o recurso de Preenchimento Automático no Excel para adicionar as linhas de maneira rápida. Verifique se as linhas serão adicionados como parte da tabela (ao usar rola vertical, você deve ser capaz consulte cabeçalhos de coluna na parte superior da grade) [![(Screenshot22]. captura de 22.png]) /media/screen(. captura 22.png /media/screen) de 4.7. Retorne o dynamics 365 para operações e atualizar a página. Os valores não serão publicados dynamics 365 para as operações. [![(Screenshot23]. captura de 23.png]) /media/screen(. captura de 23.png /media/screen)

## <a name="task-5-create-budget-plan-document-layouts-and-templates"></a>Tarefa 5: Criar um layouts e modelos para o documento do planejamento do orçamento
O layout define como as linhas grade de documento do plano de orçamento serão exibidas quando o usuário abrir o documento do plano de orçamento. Também é possível alternar o layout para o documento do plano de orçamento para ver os mesmos dados em ângulos diferentes. Agora, como há colunas definidas que podem ser usadas em seu documento do plano de orçamento, Julia deve criar um layout do documento do plano de orçamentos, que se assemelhe à tabela do Excel usada para criar dados do orçamento (consulte visão geral do Cenário na seção neste laboratório) 5.1. Na&gt;&gt; página de layouts abertos &gt; de configuração de planejamento de orçamento de previsão de orçamento de BudgetingSetup. Crie um novo layout para a entrada de orçamento mensal:

-   Escolha o conjunto de dimensões de MA+BU para incluir contas principais e unidades de negócios no layout.
-   Liste todas as colunas do plano de orçamento criadas na etapa anterior na seção Elementos. Faça com que todos os dados, exceto os números do ano anterior, sejam editáveis.
-   Clique no botão Descrições para selecionar quais dimensões financeiras devem ser exibidas em Descrições na grade.

[![(Screenshot24]. captura de 24.png]) /media/screen(. /media/screen disparou em 24.png) com base na definição do layout de plano de orçamento poderemos criar um modelo De O excel a serem usado como uma alternativa de maneira editar dados de orçamento. Como o modelo do Excel deve corresponder à definição do layout do plano de orçamento, você não poderá editar o layout do plano de orçamento depois de gerar o modelo do Excel, pois esta tarefa deve ser realizada depois que todos os componentes foram definidos. 5.2. Para o layout criada em 5.1. a etapa de modelo, clique &gt; em botão gera. Confirme a mensagem de aviso. Para exibir o modelo, clique na opção &gt; de modelo. *Note: Certifique-se selecione salvar como “a” e selecione o local em que o modelo deve ser armazenado para a edição. Se o usuário selecionar “inicial” na caixa de diálogo, sem salvar as alterações feitas no arquivo não estarão retidas quando o arquivo é closed.* [![(Screenshot25]. captura de 25.png]) /media/screen(. captura 25.png /media/screen) de 5.3. &lt; A etapa opcional&gt; alterar o modelo De O excel para torná-lo mais olhar amigável – adicionar fórmulas totais, campos de cabeçalho, formatação, etc. salvar as alterações e encargos o arquivo para orçar o layout do plano clicando o carregamento &gt; de layout [![(Screenshot26]. captura de 26.png]) /media/screen(. captura de 26.png /media/screen)

## <a name="task-6-create-a-budget-planning-process"></a>Tarefa 6: Criar um processo de planejamento do orçamento
Julia precisa criar e ativar um novo processo de planejamento de orçamento que combina a configuração acima para iniciar inserindo planos de orçamento. O processo de planejamento de orçamento define para que as organizações, o fluxo de trabalho, os layouts e os modelos de orçamento serão usados ao criar planos de orçamento. 6.1. Navegar no processo &gt; de planejamento &gt; de orçamento de orçamento &gt; de previsão de orçamento de configuração e crie um novo registro.

-   Processo de planejamento do orçamento – FY2016 do orçamento DEMF
-   Ciclo do orçamento - FY2016
-   Ledger – DEMF
-   Estrutura da conta padrão – P&L de fabricação
-   Hierarquia organizacional – escolha a hierarquia criada no início do laboratório
-   Fluxo de trabalho do planejamento do orçamento - atribuir Automático - Aprovar fluxo de trabalho para o departamento financeiro
-   Nas regras e modelos do estágio de planejamento do orçamento, para cada escolha do estágio de planejamento do orçamento, se Adicionar linhas e Modificar linhas estiver permitido e qual Layout deve ser usado por padrão

*Observação: Você pode criar outros layouts de documento e atribuir disponibilidade no estágio do fluxo de trabalho do planejamento do orçamento ao clicar no botão Alternar layouts.* [![(Screenshot27]. captura de 27.png]) /media/screen(. captura 27.png /media/screen) de 6.2. As ações selecionadas &gt; ativam para ativar este fluxo de trabalho de planejamento de orçamento [![(Screenshot28]. captura de 28.png]) /media/screen(. captura de 28.png /media/screen)

<a name="exercise-2-process-simulation"></a>Ano 2: Simulação do processo
==============================

## <a name="task-7-generate-initial-data-for-budget-plan-from-general-ledger"></a>Tarefa 7: Gerar dados iniciais para o plano do orçamento na contabilidade
7.1. Vá até orçamento &gt; periódico &gt; geram o plano de orçamento contábil. Preencha os parâmetros do processo do periódico e clique no botão Gerar. [![(Screenshot29]. captura de 29.png]) /media/screen(. captura 29.png /media/screen) de 7.2. Navegar a planos &gt; de orçamento de orçamento para um plano de orçamento criado por Generate processo. [![(Screenshot30]. captura de 30.png]) /media/screen(. captura 30.png /media/screen) de 7.3. Abra os detalhes do documento ao clicar no hiperlink do número do documento. O plano de orçamento será exibida conforme definido em layout criado durante este laboratório [![(Screenshot31]. captura de 31.png]) /media/screen(. captura de 31.png /media/screen)

## <a name="task-8-create-current-year-budget-based-on-previous-year-actuals"></a>Tarefa 8: Crie o orçamento do ano atual com base nos números reais do ano anterior
Os métodos de alocação podem ser usados no plano de orçamento para copiar facilmente as informações para os planos do orçamento de um cenário para outro/ colá-las nos períodos/alocar para dimensões. Usaremos alocações para criar o orçamento do ano atual a partir de números reais do ano anterior. 8.1. Escolher as linhas da grade do documento de plano de orçamento do botão e clique em atribuir o orçamento [![(Screenshot32]. captura de 32.png]) /media/screen(. captura 32.png /media/screen) de 8.2. O método de alocação, a chave de período, a origem e os cenários e clique em selecionar atribuem de destino 

[![(Screenshot33]. captura de 33.png]) /media/screen(. captura de 33.png /media/screen)

Os valores reais do ano anterior serão copiados para o orçamento do ano atual e para atribui-los por períodos usando a chave de período da curva de vendas. 

[![(Screenshot34]. captura de 34.png]) /media/screen(. captura de 34.png /media/screen)

## <a name="task-9-adjust-budget-plan-document-using-excel-and-finalize-the-document"></a>Tarefa 9: Ajustar o documento do plano do orçamento usando o Excel e finalizar o documento
9.1. Clique na planilha de botões ao conteúdo de documentos inicial Excel

[![(Screenshot35]. captura de 35.png]) /media/screen(. captura de 35.png /media/screen)

9.2. Quando a pasta de trabalho do Excel for aberta, ajuste os número do documento do plano do orçamento e clique no botão Publicar.

[![(Screenshot36]. captura de 36.png]) /media/screen(. captura de 36.png /media/screen)

9.3. Devolução do documento de plano de orçamento em dynamics 365 para as operações. O fluxo de trabalho do &gt; retail transaction ao aprovar o documento

[![(Screenshot37]. captura de 37.png]) /media/screen(. captura de 37.png /media/screen) 

Depois que o fluxo de trabalho for concluído, o estágio do documento de plano de orçamento é alterado para aprovado. [![(Screenshot38]. captura de 38.png]) /media/screen(. captura de 38.png /media/screen)

<a name="appendix"></a>Anexo
========

### <a name="auto-approve-workflow-configuration"></a>Configuração do luxo de trabalho de aprovação automática

A. Os fluxos &gt; de trabalho de orçamento &gt; de orçamento de planejamento &gt; de configuração orçamento criar um novo fluxo de trabalho com fluxos de trabalho de planejamento de orçamento de planta:

[![(Screenshot39]. captura de 39.png]) /media/screen(. captura de 39.png /media/screen)

Este fluxo de trabalho só conterá uma tarefa – preparar o plano de orçamento da transição 

[![(Screenshot40]. captura de 40.png]) /media/screen(. captura de 40.png /media/screen) 

Salve e ativar o fluxo de trabalho. 

B. Navegar na configuração &gt; do &gt; orçamento de previsão de &gt; orçamento de previsão de orçamento de configuração. Na guia de estágios criar estágios 2 – iniciais e enviados 

[![(Screenshot41]. captura de 41.png]) /media/screen(. captura de 41.png /media/screen)

C. Navegar na configuração &gt; do &gt; orçamento de previsão de &gt; orçamento de previsão de orçamento de configuração. Associado da guia nos estágios do fluxo de trabalho o automóvel de fluxo de trabalho o aprovar criado na etapa de rubrica com os estágios e enviou 

[![(Screenshot42]. captura de 42.png]) /media/screen(. captura de 42.png /media/screen)  



---
title: Visão geral de planejamento de orçamento
description: Este tópico descreve o planejamento de orçamento. Ele também contém informações que podem ajudar você a configurar o planejamento de orçamento e a definir os processos de planejamento de orçamento.
author: panolte
ms.date: 01/11/2018
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetPlanningConfiguration
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "17251"
- intro-internal
ms.assetid: a2e06633-a800-4840-a962-88fed8462104
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 391f62f42e482f79420bbe1bbd4cec4930790229
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2022
ms.locfileid: "7982056"
---
# <a name="budget-planning-overview"></a>Visão geral de planejamento de orçamento

[!include [banner](../includes/banner.md)]

Este tópico descreve o planejamento de orçamento. Ele também contém informações que podem ajudar você a configurar o planejamento de orçamento e a definir os processos de planejamento de orçamento.

## <a name="overview-of-budget-planning"></a>Visão geral do planejamento de orçamento

Uma organização pode configurar o planejamento de orçamento e, em seguida, definir os processos de planejamento de orçamento para atender às políticas, procedimentos e aos requisitos para preparação do orçamento. Ao entender os conceitos e a terminologia usados no Microsoft Dynamics 365 Finance, você pode implementar de maneira mais fácil e eficaz o planejamento de orçamento na organização.

### <a name="key-terms"></a>Condições principais

- **Processos de planejamento do orçamento** – Os processos do planejamento de orçamento determinam como os planos de orçamento podem ser atualizados, encaminhados, examinados e aprovados na hierarquia da organização de orçamento. Um processo de planejamento de orçamento está vinculado a um ciclo orçamentário e a uma organização por meio de uma entidade legal.
- **Planos de orçamento** – Os planos de orçamento contêm os dados de orçamento para um ciclo orçamentário. Você pode ter vários planos de orçamento que são usados para várias finalidades. Por exemplo, você pode usar planos de orçamento para criar valores de orçamento para diferentes unidades organizacionais. Você também pode usá-los para fazer comparações e tomar decisões informadas.
- **Cenários do plano de orçamentos** – Os cenários do plano de orçamento definem categorias de dados para os planos de orçamento. Você define cenários do plano de orçamento para dar suporte a classes monetárias e outras classes de unidade de medida, como quantidades. São exemplos de cenários de plano de orçamento monetário o "ano anterior do departamento" e as "solicitações do departamento". São exemplos de cenários do plano do orçamento que usam quantidades as "chamadas de suporte do ano anterior" e a "contagem equivalente ao horário integral".
- **Estágios do plano de orçamento** – Os estágios de planejamento de orçamento definem as etapas que o plano de orçamento seguem desde o seu início até a aprovação. Os estágios do planejamento de orçamento são organizados em fluxos de trabalho do planejamento de orçamento.
- **Fluxos de trabalho do planejamento do orçamento** – Os fluxos de trabalho do planejamento de orçamento consiste em estágios do planejamento do orçamento e o define. Os fluxos de trabalho do planejamento de orçamento são associados aos fluxos de trabalho do orçamento. Os fluxos de trabalho de orçamento são os processos automatizados e manuais que movem os planos de orçamento nos estágios de planejamento do orçamento.

[![Terminologia do planejamento do orçamento.](./media/budgetplanning-terms-1024x504.png)](./media/budgetplanning-terms.png)

### <a name="typical-tasks"></a>Tarefas típicas

Você pode usar o planejamento de orçamento para realizar estas tarefas:

- Criar planos de orçamento para definir a receita e as despesas esperadas para um ciclo orçamentário.
- Analisar e atualizar os planos de orçamento usando para vários cenários.
- Em seguida, Encaminhe os planos do orçamento, com planilhas, documentos de justificativa e outros anexos, para revisão e aprovação.
- Consolide vários planos de orçamento de um nível mais baixo da organização em um único plano de orçamento pai em um nível mais alto. Também é possível desenvolver um único plano de orçamento em um nível mais alto da organização e alocar o orçamento para os níveis mais baixos.

O planejamento de orçamento é integrado a outros módulos. Consequentemente, você poderá incluir as informações de orçamento anteriores, despesa atuais, ativos fixos e recursos humanos. Como o planejamento de orçamento também é integrado ao Microsoft Excel e ao Microsoft Word, você pode usar esses programas para trabalhar com os dados pertinentes. Por exemplo, um gerente de orçamento pode importar a solicitação de orçamento de um cenário do plano de orçamento na planilha do Excel. Os dados podem ser analisados, atualizados e representados em gráfico na planilha e, em seguida, publicados de volta nas linhas do plano de orçamento.

## <a name="configuring-budget-planning"></a>Configurando o planejamento de orçamento

A funcionalidade introduzida no Dynamics 365 Finance versão 10.0.9 (abril de 2020) inclui um recurso que ajuda a melhorar o desempenho quando você usa o botão **Publicar** para atualizar registros existentes no Excel e depois publicá-los no cliente. Esse recurso acelera o processo de atualização e também ajuda a reduzir a probabilidade de uma atualização ser bloqueada quando você atualiza muitos registros ao mesmo tempo. Para disponibilizar essa funcionalidade, acesse o espaço de trabalho **Gerenciamento de recursos** e ative o recurso **Otimização de consulta de planejamento de orçamento para desempenho** em **Orçamento**. Recomendamos que você ative esse recurso.

A página **Configuração do planejamento do orçamento** contém a maioria das configurações necessárias para configurar o planejamento de orçamento. As seções a seguir descrevem alguns dos fatores que você deve considerar ao configurar o planejamento de orçamento. Depois de concluir a configuração, você pode configurar os processos do plano do orçamento.

### <a name="budget-planning-schema-optional"></a>Esquema de planejamento de orçamento (opcional)

A primeira etapa opcional, mas recomendada, é criar um esquema que mostra o procedimento da organização para formular um orçamento. Você pode usar o método que desejar para criar este esquema.

A ilustração a seguir mostra um exemplo genérico, em que os fluxos de trabalho do plano de orçamento separados são criados para níveis diferentes da organização. Os estágios são definidos em cada fluxo de trabalho e os cenários específicos são atribuídos a cada estágio para reter os dados do orçamento. As tarefas são concluídas para mover os dados de um estágio para o outro. Por exemplo, os valores podem ser alocados ou agregados em contas diferentes, aprovações diferentes ou outras revisões. Nesta ilustração, o texto em itálico indica um cenário que não pode ser editado durante o estágio, ou dados que são históricos ou foram aprovados em uma fase anterior e não devem ser alterados.

[![Esquema genérico do plano de orçamento.](./media/budgetplanninggenericschema-300x145.png)](./media/budgetplanninggenericschema.png) 

A ilustração a seguir mostra um exemplo em que a matriz corporativa estima os valores de linha de base para o orçamento inicial e os distribui aos departamentos de vendas. Os departamentos de vendas estimam e envia a previsão para a matriz, onde o gerente poderá agregá-la e ajustá-la. Além disso, o gerente de orçamento envia os valores de orçamento ajustados ao diretor financeiro (CFO) para revisão, ajustes finais e aprovação.

[![Exemplo do esquema do plano de orçamento.](./media/budgetplanningexampleschema-300x145.png)](./media/budgetplanningexampleschema.png)

### <a name="organization-hierarchy-for-budget-planning"></a>Hierarquia organizacional para o plano do orçamento

Na página **Hierarquia da organização**, você pode especificar uma hierarquia organizacional como uma hierarquia de planejamento de orçamento para cada processo de planejamento de orçamento. A hierarquia de planejamento de orçamento não precisa corresponder a hierarquia organizacional padrão que é usada para outras finalidades. Como essa hierarquia é usada para agregar e distribuir dados, pode ser necessário ter uma estrutura diferente. No esquema do exemplo, os departamentos de vendas estão no nível da matriz que inclui os departamentos do orçamento e de finanças. Provavelmente, esta estrutura difere da estrutura usada para gerenciar operações dos departamentos de vendas. Somente uma hierarquia da organização pode ser atribuída a cada processo do plano do orçamento.

Para obter mais informações, consulte [Organizações e hierarquias organizacionais](../../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md).

### <a name="user-security"></a>Segurança do usuário

O plano do orçamento pode seguir um dos dois modelos para definir permissões do usuário. Para especificar o modelo de segurança, você pode definir um parâmetro do planejamento na página **Configuração do planejamento de orçamento**.

### <a name="budget-planning-workflows-stages"></a>Estágios dos fluxos de trabalho do planejamento do orçamento

Os fluxos de trabalho do plano de orçamento são usados com fluxos de trabalho de orçamento para gerenciar a criação e a evolução dos planos de orçamento.

Um fluxo de trabalho do planejamento de orçamento consiste em um conjunto de estágios ordenados pelos quais um plano de orçamento se move. Cada fluxo de trabalho do plano do orçamento está associado ao fluxo de trabalho do orçamento. Os fluxos de trabalho de orçamento são um dos tipos do fluxo de trabalho que são usados em todo o Dynamics 365 Finance. Eles encaminham os planos de orçamento, com planilhas, justificações e anexos, por meio da sua organização para revisão e aprovação.

Você cria um fluxo de trabalho do planejamento na seção **Estágios do fluxo de trabalho** da página **Configuração do plano de orçamento**. Nele, é possível selecionar os estágios e o fluxo de trabalho do orçamento que será usado e definir configurações adicionais.

Uma boa prática é criar um fluxo de trabalho do planejamento de orçamento para cada nível da hierarquia do orçamento. Em seguida, atribua um fluxo de trabalho do orçamento que contém os elementos que correspondem aos estágios no fluxo de trabalho do orçamento. No esquema do exemplo que aparece neste tópico, um fluxo de trabalho do planejamento de orçamento será criado para os departamentos de venda e outro deve ser criado para a matriz. Um fluxo de trabalho de orçamento move os planos de orçamento pelos estágios.

Você cria um fluxo de trabalho do orçamento para o plano na página **Fluxos de trabalho do orçamento**. O processo se parece com o processo para criar outros fluxos de trabalho. A ilustração a seguir mostra um exemplo de um fluxo de trabalho da matriz.

[![Fluxo de trabalho do orçamento para o plano do orçamento.](./media/budgetingworkflowforbudgetplanning-300x300.png)](./media/budgetingworkflowforbudgetplanning.png) 

O fluxo de trabalho inclui os seguintes elementos:

- Alocação para os departamentos de venda e agregação de seus envios
- Análise do gerente de orçamento
- Aprovação de CFO
- Transições de preparação entre cada estágio do fluxo de trabalho de planejamento de orçamento

Atribua o fluxo de trabalho do orçamento a cada fluxo de trabalho do planejamento do orçamento na seção **Estágios do fluxo de trabalho** da página **Configuração do planejamento do orçamento**.

### <a name="parameters-scenarios-and-stages"></a>Parâmetros, cenários e estágios

As configurações iniciais na página **Configuração do plano do orçamento** permitem criar alguns blocos para as etapas de configuração posteriores:

- **Parâmetros** – Os parâmetros definem as regras de segurança que você deseja aplicar nos planos do orçamento e as dimensões financeiras padrão que devem ser usadas quando os usuários navegam nos valores dos cenários do plano de orçamentos.
- **Cenários** – Os cenários englobam as categorias de dados que você deseja para os planos de orçamento. Você define cenários do plano de orçamento para dar suporte a classes monetárias e outras classes de unidade de medida, como quantidade. Em um plano do orçamento, os cenários representam uma versão dos dados do planejamento de orçamentos. São exemplos de cenários de plano de orçamento monetário as "vendas do ano anterior" e os "contratos assinados". São exemplos dos cenários que usam quantidades os "números das chamadas de vendas" e a "contagem equivalente ao horário integral".
- **Estágios** – Os estágios definem as etapas seguidas por um plano de orçamento desde o início até a aprovação final. São exemplos de estágios do plano do orçamento "Acúmulo da matriz", "Revisão do chefe do departamento financeiro" e "Final".

### <a name="allocation-schedules"></a>Agendas de alocação

No plano do orçamento, você pode alocar os valores ou quantidades nas linhas do plano do orçamento de um cenário para outro ou no mesmo cenário. Por exemplo, você pode alocar valores ou quantidades para o mesmo cenário se você deseja aplicar alterações às dimensões financeiras ou às datas dos valores nesse cenário. Uma alocação pode ser feita em um plano de orçamento ou de um plano de orçamento para outro.

Os planos de agendamento alocam linhas do plano de orçamento durante o processamento do fluxo de trabalho. Você pode executar alocações ao usar um dos métodos a seguir na lista **Método de alocação**:

- **Alocar entre períodos** - É possível usar uma chave de alocação para alocar as linhas do plano de orçamento do cenário do plano orçamento de origem entre períodos no cenário de destino.

    > [!NOTE]
    > Antes que possa alocar nos períodos, você deve definir chaves de alocação de período na página **Categorias de alocação de período**.

- **Alocar para dimensões** – As linhas do plano de orçamento são alocadas desde o cenário do plano de orçamento de origem nas dimensões financeiras do cenário de destino.

    > [!NOTE]
    > Antes que você possa alocar para dimensões, é necessário configurar as condições de alocação de orçamento na página **Condições de alocação de orçamento**.

- **Agregar** – As linhas do plano do orçamento são agregadas a partir do cenário do plano de orçamento de origem são associadas aos planos de orçamento para o cenário de destino no plano de orçamento pai.
- **Distribuir** – As linhas do plano de orçamento são distribuídas desde o cenário do plano de orçamento de origem no plano de orçamento principal para o cenário de destino nos planos de orçamento associados.
- **Usar regras de alocação do razão** – As linhas do plano de orçamento são distribuídas a partir do cenário do plano de orçamento de origem para o cenário de destino, com base na regra de alocação do razão selecionada.
- **Cópia do plano de orçamento** – É possível selecionar outro plano do orçamento para usar como origem da alocação.

### <a name="stage-allocations"></a>Alocações de fase

As alocações do estágio são usadas para alocar automaticamente as linhas do plano de orçamento durante o processamento do fluxo de trabalho. Quando as alocações do estágio são usadas, as linhas do plano de orçamento no destino podem ser criadas e modificadas sem a intervenção da pessoa que preparou o plano orçamentário ou do revisor.

Ao configurar uma alocação de estágio, você associa o fluxo de trabalho e o estágio do planejamento de orçamento à agenda de alocação. O fluxo de trabalho do planejamento de orçamento deve estar associado a um fluxo de trabalho de orçamento que use a tarefa de fluxo de trabalho automatizada **Alocação de fase do planejamento de orçamento**. Quando o fluxo de trabalho atingir o estágio especificado, a alocação ocorrerá automaticamente. Essa tarefa automatizada pode ser usada para criar linhas do plano de orçamento em um novo cenário.

No esquema do exemplo anteriormente exibido neste tópico, uma alocação será executada para transferir valores de um plano de orçamento e os cenários no estágio da linha de "base" da matriz para outro plano de orçamento e os cenários no estágio "Estimativa" dos departamentos de vendas. A ilustração a seguir mostra a seção relevante do esquema de exemplo.

[![Alocação do estágio.](./media/stageallocation-204x300.png)](./media/stageallocation.png) 

Além disso, no esquema de exemplo, uma agregação é feita de planos e os cenários de orçamento no estágio "Enviado" para departamentos de vendas para um plano principal na fase "Acúmulo" da matriz. A ilustração a seguir mostra a seção relevante do esquema de exemplo.

[![Agregação.](./media/aggregation-109x300.png)](./media/aggregation.png)

### <a name="priorities"></a>Prioridades

Opcionalmente, você pode usar as prioridades do plano de orçamento para definir categorias e objetivos para planos do orçamento que você configurou. Você também pode usar prioridades para organizar, classificar e avaliar vários planos de orçamento. Por exemplo, você pode criar uma prioridade de planejamento de orçamento para saúde e segurança e então avaliar os planos de orçamento atribuídos a essa prioridade. Você também pode atribuir um número aos seus planos de orçamento para indicar uma classificação.

### <a name="columns-and-layouts"></a>Colunas e layouts

Em um plano de orçamento, os valores do orçamento aparecem em linhas e colunas. Após definir as colunas, é possível criar um layout para definir a apresentação dessas colunas.

Para definir uma coluna, selecione um cenário do plano de orçamento. Os valores da linha no cenário são exibidos no plano de orçamento. É possível selecionar um período para filtrar o valor ou aplicar filtros que se baseiam na conta do razão.

Quando você está definindo um layout, selecione uma dimensão contábil definida para criar linhas do plano de orçamento que você deseja exibir e selecione as colunas como os elementos do layout. Você pode criar vários layouts, de modo que um plano de orçamento mostre os dados desejados em diferentes estágios do processo de planejamento de orçamento.

Além das colunas para valores de orçamento, é possível definir colunas para os campos projeto, projeto proposto, ativo e ativo proposto no plano do orçamento. Também é possível definir uma coluna para as posições orçadas. Esta opção é útil quando você deve analisar orçamentos de pessoal.

No esquema de exemplo, você pode querer criar colunas para os cenários "Vendas de PY", "Contratos" e "Previsão". (A ilustração a seguir mostra a seção relevante do esquema). Em seguida, você poderá dividir um desses cenários em colunas separadas para cada trimestre do ano fiscal, de modo que o gerente do departamento de vendas possa inserir os valores de previsão de cada período de maneira precisa.

[![Ilustração de seções do esquema para adicionar colunas.](./media/columns.png)](./media/columns.png)

Você também pode especificar se cada elemento de layout (coluna) é editável e se está disponível no modelo que é criado para o layout. Para o esquema de exemplo, no layout usado para a fase "Estimativa", as colunas da "Previsão" são editáveis, mas as colunas de "Vendas de PY" e "Contratos" são somente leitura.

> [!NOTE]
> Por padrão, você será limitado a 36 colunas, a menos que estenda o planejamento de orçamento seguindo as etapas em [Estender o layout de planejamento de orçamento](./extending-budget-planning-layout.md).

### <a name="templates"></a>Modelos

Na seção **Layouts** da página **Configuração de planejamento de orçamento**, você pode gerar, visualizar ou carregar um modelo do Excel para cada layout. Esses modelos são Os modelos são as pastas de trabalho vinculadas a cada plano de orçamento, para fornecer análise adicional, gráficos e recursos de inserção de dados.

Quando um modelo é gerado, o layout está bloqueado e não pode ser editado. O bloqueio ajuda a garantir que o formato do modelo corresponde ao layout do plano de orçamento e inclui os mesmos dados. Depois que um modelo é gerado, pode ser exibido e editado. Por exemplo, você pode adicionar gráficos ao modelo ou personalizar sua aparência.

> [!NOTE]
> Um modelo deve ser salvo em um local ao qual o usuário tem acesso, de modo que possa ser carregado para o layout após a conclusão da edição. Dessa maneira, o modelo será usado com planos de orçamento que usam o layout.

### <a name="descriptions"></a>Descrições

Na seção **Layouts**, você pode atribuir descrições para mostrar o nome de uma dimensão financeira incluída em um layout. Por exemplo, uma organização pode querer mostrar o nome da conta principal ao lado do número da conta principal em um plano de orçamento. No entanto, talvez seja necessário omitir os nomes de outras dimensões financeiras, para evitar desordenar a exibição.

## <a name="setting-up-budget-planning-processes"></a>Configurando processos de planejamento de orçamento

Depois de concluir a configuração do plano do orçamento, é possível configurar os processos de planejamento do orçamento na página **Processo do planejamento do orçamento**. Processos de planejamento do orçamento são os conjuntos de regras que determinam como os planos de orçamento podem ser atualizados, encaminhados, revisados e aprovados na hierarquia da organização de orçamento.

Para cada processo de planejamento de orçamento, selecione primeiro um ciclo do orçamento e um razão. Cada processo de planejamento de orçamento está relacionado a um ciclo orçamentário e um razão. Em seguida, selecione a hierarquia da organização de orçamento na FastTab **Administração do processo do plano do orçamento**, e atribua um fluxo de trabalho do planejamento de orçamento a todos os centros de responsabilidade da organização que aparecem na grade.

Para atribuir ou alterar o fluxo de trabalho do planejamento de orçamento para centros de responsabilidade semelhantes, selecione **Atribuir fluxo de trabalho** e depois selecione o tipo de organização de destino e o fluxo de trabalho do plano de orçamento a ser usado. A ID de fluxo de trabalho do Orçamento associada a cada fluxo de trabalho do planejamento de orçamento é adicionada à grade automaticamente.

Quando você define as regras e os modelos do estágio na Guia Rápida **Regras e layouts do estágio do plano de orçamento**, pode definir um conjunto de regras e layouts padrão para cada estágio de planejamento de orçamento. Por exemplo, o estágio "Estimativa" do departamento de vendas permite que os usuários modifiquem as linhas em um plano de orçamento, mas os impede de adicionar linhas. O estágio "Enviado" permite que os usuários vejam as linhas, mas não as adicionem ou modifiquem, porque o trabalho no estágio foi concluído e os planos de orçamento devem ser evitados. Para selecionar os layouts que estão disponíveis para os planos de orçamento, selecione **Layouts alternativos**.

Opcionalmente, você pode selecionar as prioridades de planejamento do orçamento na Guia Rápida **Restrições da prioridade do plano de orçamento**. As prioridades podem ser selecionadas nos planos do orçamento.

A etapa final consiste em ativar o processo de planejamento do orçamento usando o menu **Ações**. Um processo de planejamento de orçamento não pode ser usado até que seja ativado.

Você também pode usar o menu **Ações** para criar um processo, copiando um processo existente. Este recurso é útil para organizações que acompanham o mesmo ciclo do orçamento e fazem poucas alterações ou nenhuma.

Outro comando útil no menu **Ações** é **Visualizar processo do orçamento**. Este comando exibe graficamente os planos de orçamento em um processo, junto com os dados relevantes, como o status do fluxo de trabalho dos planos, resumos pelo valor e por unidade, e navegação de único clique para os planos do orçamento.

[![Status de processo de planejamento de orçamento.](./media/budgetplanningprocessstatus-300x171.png)](./media/budgetplanningprocessstatus.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

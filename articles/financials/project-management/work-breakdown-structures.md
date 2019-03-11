---
title: Estruturas de detalhamento de trabalho
description: Uma estrutura de detalhamento de trabalho (WBS) é uma descrição do trabalho que será feito para um projeto. É uma hierarquia de tarefas que representa a compreensão da equipe do projeto da composição do trabalho, e do tamanho, custo, e duração de cada componente ou tarefa.
author: KimANelson
manager: AnnBe
ms.date: 06/05/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjWorkBreakdownStructure
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 23861
ms.assetid: 241a0464-0056-4a69-b468-0afbe2d5f3ae
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: df4bc39f8df80580261102941712622ed59262bd
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "358890"
---
# <a name="work-breakdown-structures"></a>Estruturas de detalhamento de trabalho

[!include [banner](../includes/banner.md)]

Uma estrutura de detalhamento de trabalho (WBS) é uma descrição do trabalho que será feito para um projeto. É uma hierarquia de tarefas que representa a compreensão da equipe do projeto da composição do trabalho, e do tamanho, custo, e duração de cada componente ou tarefa. Uma WBS tem três fins principais:

-   Descrever o detalhamento ou composição do trabalho em tarefas.
-   Planejar o trabalho do projeto.
-   Estimar os custos de cada tarefa.

O nível de detalhe em uma WBS depende do nível de precisão exigido em estimativas e do nível de acompanhamento obrigatório em relação às estimativas. Projetos que têm tolerância muito baixa para deslizes na agenda ou no custo geralmente exigem uma WBS mais detalhada, e acompanhamento assíduo do progresso do trabalho e dos custos em relação à WBS. Esse tipo de projeto é comum em setores de construção e engenharia. 

Por outro lado, os projetos em setores como mídia e propaganda, software, e infraestrutura de TI tendem a ser de um tipo único, e a produtividade é relativa à experiência e competência do indivíduo que está executando a tarefa. Consequentemente, essas indústrias utilizam uma WBS para obter uma aproximação do tamanho de um projeto, ao invés de acompanhar o progresso do projeto em detalhes. 

Construir uma WBS é um processo intensivo que geralmente é feito durante um longo período de tempo, e que requer colaborações e informações de diversas pessoas. Este tópico descreve como você pode usar aprimoramentos de WBS no Microsoft Dynamics 365 for Finance and Operations para atender os requisitos de estimativas e acompanhamento.

## <a name="prerequisites-for-creating-a-wbs"></a>Pré-requisitos para criação de uma WBS
Para criar uma WBS, você deve ser capaz de criar um plano de trabalho e estimar os custos de trabalho.

### <a name="prerequisites-for-creating-a-work-schedule"></a>Pré-requisitos para criação de um plano de trabalho

Para usar todas as funcionalidades de programação dos recursos da WBS, complete as etapas a seguir:

1.  Configurar um calendário padrão e um calendário do projeto:
    1.  Clique em **Gerenciamento e contabilidade de projetos** &gt; **Configurar** &gt; **Parâmetros de gerenciamento e contabilidade de projetos** &gt; **Agendamento**. No campo **Calendário de trabalho padrão**, especifique um calendário padrão. Esse será o calendário de trabalho padrão para qualquer projeto novo criado.
    2.  Você pode alterar o calendário padrão para um projeto específico. Clique na página detalhes do projeto e, na Guia Rápida **Equipe de projeto e planejamento**, atualize o campo **Calendário de planejamento** selecionando outro calendário.

2.  Configure dias úteis padrões e horas de trabalho. O calendário definido como calendário de trabalho para o projeto será usado na WBS para determinar as seguintes informações:

-   Dias úteis e feriados
-   O número de horas de trabalho em um dia

Para configurar os dias úteis e as horas de trabalho em um calendário, ou para criar um novo calendário **Administração da organização** &gt; **Comum** &gt; **Calendários**.

### <a name="prerequisites-for-estimating-the-cost-of-work"></a>Pré-requisitos para estimar os custos de trabalho

Para usar todas as funcionalidades da estimativa de custo da WBS, você deve configurar os preços de custo e venda para os funcionários, categorias de trabalho, despesas e taxas, e itens.

-   Para configurar as categorias de preços de custo e venda do trabalho, despesa, e taxa, clique em **Gerenciamento de projetos e contabilidade** &gt; **Configuração** &gt; **Preços**.
-   Para configurar os preços de custo e venda dos itens, utilize a página **Contratos comerciais** para cada item na página de listagem **Produtos liberados** em Gerenciamento de informações sobre produtos.

## <a name="creating-a-wbs"></a>Criando uma WBS
Criar uma WBS envolve três atividades:

1.  **Decomposição do trabalho** – Criar um fracionamento do trabalho em pedaços ou tarefas gerenciáveis.
2.  **Plano de trabalho** – Estimar o tempo necessário para completar uma tarefa, definir interdependências da tarefa, e selecionar as datas de início e fim das tarefas.
3.  **Previsão de custos** – Estimar custos para cada tarefa.

As seções a seguir discutem como as funcionalidades da WBS podem ajudar em cada uma dessas atividades.

### <a name="work-decomposition"></a>Decomposição do trabalho

Criar um fracionamento ou decomposição do trabalho é geralmente a primeira etapa do processo de criação de uma WBS. A funcionalidade da WBS suporta as seguintes construções básicas para fracionamento e decomposição do trabalho. 

**Tarefa raiz do projeto** A tarefa raiz do projeto é a tarefa de resumo de nível mais alto para um projeto. Todas as outras tarefas do projeto são criadas abaixo dela. O nome da tarefa raiz está sempre definida com o nome do projeto. O esforço, datas, e duração do nó raiz resumem os valores das tarefas abaixo da tarefa raiz. Você não pode alterar as propriedades do nó raiz ou excluí-lo.

**Tarefas de resumo ou acolhedoras** Uma tarefa de resumo é uma tarefa que contém subtarefas ou tarefas componentes abaixo dela. Uma tarefa de resumo não apresenta esforço de trabalho ou custo próprio. Em vez disso, o esforço de trabalho e o custo de uma tarefa de resumo são a soma dos esforços de trabalho e dos custos de suas tarefas componentes. A data de início mais próxima entre as tarefas componentes é usada como data de início da tarefa de resumo, e a data de término mais distante entre as tarefas componentes é usada como data de término. Você pode alterar o nome de uma tarefa de resumo, mas você não pode alterar as propriedades de planejamento para esforço, datas e duração. Se você excluir uma tarefa de resumo, todas suas tarefas componentes também serão deletadas. 

**Tarefas do nó folha** Uma tarefa do nó folha representa o pacote de trabalho mais granular do projeto. Um nó folha possui um esforço estimado, um número planejado de recursos, datas planejadas de início e término, e duração. 

Você pode completar as seguintes operações hierárquicas para habilitar a criação de uma hierarquia ou decomposição do trabalho em um projeto. 

**Nova tarefa** Qualquer nova tarefa criada é automaticamente adicionada sob o nó raiz, e um número WBS é automaticamente atribuído à tarefa. O número WBS representa o nível da tarefa na hierarquia. Para tarefas que estão no primeiro nível abaixo da tarefa raiz, um esquema de numeração do tipo 1, 2, 3, e assim por diante, é utilizado. Para tarefas que estão abaixo do primeiro nível, um esquema de numeração do tipo 1.1, 1.2, 1.3, e assim por diante, é utilizado. Para cada nível que é adicionado abaixo de um nível anterior, uma nova série de números pontuada é adicionada. 

No momento, você não pode personalizar o sistema de numeração da WBS. 

**Recuar tarefa** Quando você recua uma tarefa, ela se torna um filho da tarefa que a precede. O número WBS da nova tarefa filha é automaticamente recalculado com base no número WBS da sua nova tarefa mãe. A tarefa mãe é agora uma tarefa de resumo ou acolhedora, e portanto se torna uma acumuladora de suas tarefas componentes. 

> [!NOTE] 
> Quando você recua tarefas sob uma tarefa que era um nó folha antes da operação de recuo, a recém-criada tarefa de resumo perde suas próprias datas, esforço, e número de recursos. Ela usa agora um resumo dos valores das suas novas tarefas componentes. 

**Recuar tarefa à esquerda** Quando você recua uma tarefa à esquerda, ela deixa de ser uma tarefa componente da sua tarefa mãe. O número WBS dessa tarefa é recalculado automaticamente para refletir o novo nível da tarefa dentro da hierarquia. O esforço, o custo, e as datas da sua tarefa mãe anterior são recalculados para excluir aquela tarefa. 

**Mover para cima e Mover para baixo** Quando você clicar em **Mover para cima** e **Mova para baixo**, você altera a posição de uma tarefa dentro da hierarquia em que se encontra. A posição de uma tarefa não afeta o esforço, o custo, as datas, ou duração da tarefa. No entanto, o número WBS da tarefa é recalculado automaticamente para refletir a nova posição da tarefa.

### <a name="schedule-estimation"></a>Estimativa de planejamento

Estimativa de planejamento é, geralmente, a segunda etapa da criação de uma WBS. Como prática recomendada, você deve concluir a estimativa do planejamento depois de criar as tarefas. A página **Estrutura de detalhamento de trabalho** no Finance and Operations tem duas seções. O painel superior é destinado à estimativa de planejamento, e o painel inferior inclui uma aba **Custos e receitas estimados** que você pode utilizar na estimativa de custos. 
**Dependências da tarefa** Em uma WBS, você pode criar uma relação de antecessor entre tarefas. Ao atribuir tarefas de antecessor a uma tarefa, aquela tarefa só poderá ser iniciada depois que todas suas tarefas de antecessor forem completadas. A data planejada de início da tarefa é automaticamente definida como a data mais distante entre todas suas antecessores. 

**Planejamento de tarefa no Microsoft Dynamics 365 for Finance and Operations** Os seguintes fatores determinam o planejamento das tarefas do nó folha:

-   Predecessores
-   Esforço
-   O número de recursos
-   Datas inicial e final

A data de início de uma tarefa do nó folha que não tem antecessoras é automaticamente definida como a data de início do planejamento do projeto. A duração de uma tarefa do nó folha é sempre calculada como o número de dias úteis entre suas datas de início e término. 

*<strong><em>Regras de agendamento</em></strong>* Quando a assistência automática de agendamento é ativada, as seguintes regras se aplicam ao agendamento de tarefas do nó folha:

-   As datas de início e término de uma tarefa devem ser dias úteis, de acordo com o calendário de planejamento do projeto.
-   A data de início de uma tarefa que contém antecessoras é automaticamente definida como a data de término mais distante entre suas antecessoras.
-   O esforço para uma tarefa é calculado automaticamente da seguinte maneira:

Número de pessoas × Duração × Número de horas em um dia de trabalho padrão no calendário do projeto. 

Em alguns casos, você pode querer afastar-se essas regras. É possível desativar o planejamento automático para evitar que o Finance and Operations defina ou corrija automaticamente alguma propriedade das tarefas do nó folha. Quando você insere informações sobre uma tarefa que pode causar uma violação de alguma regra de planejamento, um ícone de erro de planejamento é exibido na tarefa. Se você não deseja que os erros de planejamento sejam exibidos, clique em **Erros de planejamento são exibidos** para desativar esse recurso. 

> [!NOTE] 
> Os valores de uma tarefa de resumo ou acolhedora continuam a ser calculados como a soma dos valores das tarefas componentes, independentemente da assistência automática de planejamento estar ativada ou desativada. 

**Corrigindo erros de planejamento** Quando a assistência automática de planejamento está ativada, é pouco provável que ocorram erros de planejamento. Entretanto, se você desativar a assistência automática de planejamento e então ativá-la novamente mais tarde, ícones de erro de planejamento podem aparecer no WBS. 

**Corrigindo erros de planejamento por tarefa** Quando você clica duas vezes no ícone de erro de planejamento de uma tarefa específica, uma caixa de diálogo exibe todos os erros de planejamento daquela tarefa. Você pode decidir quais erros de planejamento corrigir para a tarefa. 

**Corrigindo todos os erros de planejamento** Se você deseja que o Finance and Operations corrija todos os erros de planejamento na WBS, no Painel de Ação, clique em **Corrigir todas as discrepâncias de planejamento**. 

> [!NOTE] 
> Este recurso pode causar alterações significativas na WBS. Erros são corrigidos de acordo com a seguinte ordem:

1.  O esforço estimado em todas as tarefas é modificado para que seja igual à capacidade definida no calendário do projeto.
2.  A data de início de cada tarefa é modificada para que a tarefa inicie depois que todas suas tarefas antecessoras forem concluídas.
3.  A data de início de cada tarefa é modificada para remover intervalos entre as datas de início das tarefas antecessoras.

### <a name="cost-estimation"></a>Previsão de custo

Como mencionado anteriormente neste documento, você insere a estimativa de custo para cada tarefa do nó folha utilizando a aba **Custos e receitas estimados** no painel inferior da página **Estrutura de detalhamento de trabalho**. 

> [!NOTE] 
> Não é possível alterar a estimativa de custo de uma tarefa de resumo ou acolhedora. A estimativa de custo de uma tarefa de resumo é igual à soma das estimativas de custos de suas tarefas do nó folha. O custo total estimado para cada tarefa é calculado como a soma das quantias de custo estimado para os seguintes tipos de transação:

-   Trabalho
-   Item ou material
-   Despesas

Uma transação do tipo **Taxa** é utilizada para estimar a receita baseada em honorários. Esse tipo de transação não possui um componente de custo e portanto não será considerado quando os custos forem estimados. 

Uma transação do tipo **Por conta** é utilizada para registrar o valor de venda contratado em um projeto do tipo valor fixo. Esse tipo de transação também não será considerado quando os custos forem estimados. 

Quando você estimar os custos do trabalho, e as despesas de cada etapa, você deve atribuir uma categoria de projeto ao custo estimado. 

**Estimando custos de trabalho** Para cada tarefa do nó folha, você atribui um esforço de trabalho em horas e uma categoria padrão. Consequentemente, quando você configurar uma agenda para uma tarefa, os custos estimados de mão de obra serão automaticamente adicionados à categoria padrão para trabalho. Essa estimativa de custo é exibida na aba **Custos e receitas estimados** na grade **Detalhes da linha** para aquela tarefa. Se for necessário mais estimativas de custos de mão de obra, você pode adicioná-las nessa aba. Se você aumentar ou diminuir a quantidade de horas na estimativa de custos de mão de obra, a agenda da tarefa é recalculada automaticamente. 

**Estimando despesas e custo de materiais** A aba **Custos e receitas estimados** também permite que você estime as despesas e o custo dos materiais para uma tarefa, se necessário. 

O custo e o preço de venda de cada linha de estimativa de mão-de-obra ou despesa baseiam-se na configuração definida para cada categoria nas tabelas de preços em **Gerenciamento de projetos e contabilidade** &gt; **Configuração** &gt; **Definição de preços**. Para os itens, os preços de custo e venda são adicionados, por padrão, dos contratos comercial ou de item na página de listagem **Produtos lançados** em Gerenciamento de informações sobre produtos.

## <a name="tracking-progress-on-the-wbs"></a>Acompanhando progresso na WBS
Algumas indústrias acompanham o andamento de um projeto em relação a uma WBS a um nível muito granular, enquanto outras acompanham o progresso a um nível superior da WBS. Esta seção descreve como você pode utilizar o acompanhamento da WBS para os seus requisitos de projeto. 

Finance and Operations tem três exibições para a WBS de um projeto: a Exibição de planejamento, a Exibição do rastreamento do esforço, e a Exibição do rastreamento do custo.

### <a name="planning-view"></a>Exibição de Planejamento

A Exibição de planejamento exibe a estimativa planejada ou de referência da agenda e informações sobre custo. Embora não existam recursos para acompanhar a versão e a referência de uma WBS de projeto, os valores nessa exibição representam a versão de referência. As seções Estimativa da agenda e Estimativa de custo desse tópico descrevem essa exibição e como ela é utilizada para criar uma WBS.

### <a name="effort-tracking-view"></a>Exibição do rastreamento do esforço

A Exibição do rastreamento do esforço exibe o acompanhamento do progresso para tarefas na WBS. Compara as horas reais de esforço acumuladas de uma tarefa às horas de esforço planejadas. As seguintes fórmulas fornecem os valores na Exibição do rastreamento do esforço:

-   Porcentagem de progresso = Esforço real até o momento ÷ Esforço planejado para a tarefa
-   Esforço restante (também conhecido como Estimativa para conclusão \[ETC\]) = Esforço planejado – Esforço real até o momento
-   Estimativa quando concluído (EAC) = Esforço restante + Esforço real até o momento
-   Variação de esforço projetada = Esforço planejado – EAC

A Exibição do rastreamento do esforço exibe uma projeção da variação do esforço para a tarefa, levando em conta se a EAC é maior ou menor que o esforço planejado:

-   Se a EAC é maior que o esforço planejado, a tarefa será projetada para levar mais tempo do que o planejado originalmente e está atrasada.
-   Se a EAC é menor que o esforço planejado, a tarefa será projetada para levar menos tempo do que o planejado originalmente e está adiantada.

**Nova projeção de esforço do gerente de projeto** Ocasionalmente, o gerente de projeto ou outra pessoa que esteja acompanhando o progresso de um projeto terá que revisar as estimativas originais em uma tarefa. A tarefa pode estar progredindo mais rápido ou mais devagar do que aquilo que foi originalmente antecipado, por diversas razões. Por exemplo, o escopo foi reduzido, ou os funcionários têm menos experiência do que o originalmente planejado. Projeções são a percepção de estimativas do gerente de projeto, com base no status atual de um projeto. No geral, você não deve alterar os números de referência, pois a referência de um projeto representa um documento publicado sobre a agenda do projeto e a estimativa de custos com o qual todas as partes interessadas concordaram. 

Existem duas maneiras em que os gerentes de projetos podem modificar o esforço em tarefas:

-   Modificar o esforço restante que está automaticamente configurado para atualizar o esforço restante real na tarefa.
-   Modificar a porcentagem de progresso que está automaticamente configurada para atualizar o progresso verdadeiro na tarefa.

Ambas as abordagens geram um novo cálculo da ETC, da EAC e da porcentagem de progresso da tarefa, além da variação de esforço projetada na tarefa. A EAC, a ETC e a porcentagem de progresso nas tarefas de resumo também são recalculadas, e suas variações de esforço projetadas são atualizadas. 

**Esforço alterado em tarefas de resumo** Você pode alterar o esforço em tarefas de resumo ou acolhedoras. Independentemente de você alterar esses valores utilizando o esforço restante ou a porcentagem de progresso nas tarefas de resumo, os cálculos ocorrem automaticamente na seguinte ordem:

1.  A EAC, a ETC e a porcentagem de progresso da tarefa são calculadas.
2.  A nova EAC é distribuída às tarefas filhas com a mesma proporção do valor da EAC original.
3.  A nova EAC em cada tarefa do nó folha é calculada.
4.  O esforço restante e a porcentagem de progresso são recalculadas para todas as tarefas filhas afetadas, com base no novo valor da EAC. A variação de esforço das tarefas também é recalculada.
5.  A EAC das tarefas de resumo também são recalculadas pelos nós folha.

Clique em **Expandir ao nível** na Exibição do rastreamento do esforço para definir o nível sobre o qual acompanhar e manter sua WBS. A WBS é automaticamente expandida àquele nível na Exibição do rastreamento do esforço sempre que você abri-la.

### <a name="cost-tracking-view"></a>Exibição do rastreamento do custo

A Exibição do rastreamento do custo exibe o acompanhamento do consumo de custo em uma tarefa. Nesta exibição, os custos reais que foram gastos em uma tarefa até o momento são comparados ao custo planejado para a tarefa. As seguintes fórmulas fornecem os valores na Exibição do rastreamento do custo:

-   Porcentagem de custo consumido = Custo real até o momento ÷ Custo planejado para a tarefa
-   Custo para concluir (CTC) = Custo planejado – Custo real até o momento
-   Estimativa quando concluído (EAC) = CTC + Custo real até o momento
-   Variação de custo projetada = Custo planejado – EAC

A Exibição do rastreamento do custo exibe uma projeção da variação de custo para a tarefa, levando em conta se a EAC é maior ou menor que o custo planejado:

-   Se a EAC é maior que o custo planejado, a tarefa será projetada para gastar mais dinheiro do que o planejado originalmente e está fora do orçamento.
-   Se a EAC é menor que o custo planejado, a tarefa será projetada para gastar menos dinheiro do que o planejado originalmente e está dentro do orçamento.

**Nova projeção de custo do gerente de projeto** Gerentes de projeto devem usar o CTC para revisar a estimativa de custo original em uma tarefa. O gerente de projeto pode alterar o valor do CTC para o custo necessário para concluir a tarefa. Se você alterar o valor do CTC, o CTC, a EAC e a porcentagem de custo consumido da tarefa, além da variação de custo projetada para uma tarefa, são recalculados. A EAC, a ETC e a porcentagem de custo consumido nas tarefas de resumo também são recalculadas, e suas variações de custo projetadas são atualizadas. 

> [!NOTE] 
> Quando você revisa o esforço de uma tarefa da WBS na Exibição do rastreamento do esforço, o CTC, a EAC e a porcentagem de custo consumido da tarefa, assim como a variação de custo projetada, são todos recalculados na Exibição do rastreamento do custo. No entanto, as revisões de custo não afetam os valores na Exibição do rastreamento do esforço, pois o custo por tipo de transação (mão de obra, material ou despesa) ou categoria de projeto não são revisados. 

**Revisão de projeção para custos nas tarefas de resumo** Você pode revisar os custos nas tarefas de resumo, e os cálculos ocorrem automaticamente na seguinte ordem:

1.  A EAC, o CTC e a porcentagem de custo consumido da tarefa são recalculadas.
2.  A nova EAC é distribuída às tarefas filhas com a mesma proporção da EAC original nas tarefas.
3.  A nova EAC de cada tarefa é calculada.
4.  O CTS e a porcentagem de custo consumido são recalculados para as tarefas filhas afetadas, com base no valor da EAC. A variação de custo das tarefas também é recalculada.
5.  As EAC de todas as tarefas de resumo são recalculadas com base nessa alteração.

Clique em **Expandir ao nível** na Exibição do rastreamento do custo para definir o nível sobre o qual acompanhar e manter sua WBS. A WBS é expandida àquele nível na Exibição do rastreamento do custo sempre que você abri-la.

### <a name="earned-value-management"></a>Gerenciamento de valores obtidos

Você pode usar o método de valor obtido (EVM) para acompanhar o progresso de um projeto. Você pode visualizar métricas de valor obtido na Central de Funções do gerente de projeto. O componente gráfico do valor obtido mostra os valores cíclicos do valor planejado e do custo real. O valor obtido a partir da data atual é mostrado como um ponto. Os dados cíclicos para valor obtido não estão disponíveis no momento. 

A fase de tempo no gráfico de valor obtido é exibida por semana ou por mês. Esta seção descreve os três pilares do EVM: valor planejado, valor obtido e custo real. 

**Valor planejado** A teoria do EVM afirma que o gráfico do valor planejado representa a taxa com a qual a equipe de projeto planejou obter valor no projeto. 

O Finance and Operations usa a regra de ganho 0:100 quando traça o valor planejado. Sob essa regra, o valor da tarefa é lançado na tarefa a partir da sua data final. Nenhum valor é lançado até que a tarefa esteja 100 por cento completa. 

Em Gerenciamento de projetos e contabilidade, insira a data final dos nós folha e o custo planejado para eles. Quando o gráfico do valor planejado é exibido por semana, o valor planejado é resumido por semana em todas as tarefas do nó folha durante a duração do projeto. 

**Valor obtido** A teoria do EVM afirma que o gráfico do valor obtido representa a taxa em que a equipe de projeto está realmente obtendo valor no projeto. 

O Finance and Operations usa a regra de ganho 0:100 quando traça o valor obtido. Sob essa regra, o valor da tarefa é lançado na tarefa a partir da sua data final. Nenhum valor é lançado até que a tarefa esteja 100 por cento completa. 

Quando o valor obtido é calculado, a porcentagem do progresso de cada tarefa é considerada. Sob a regra de ganho 0:100, apenas as tarefas que são concluídas em um período especificado são consideradas no cálculo de valor obtido a partir do final daquele período. O valor obtido no projeto é calculado para todas as tarefas que foram concluídas quando o gráfico for criado. 

> [!NOTE] 
> Atualmente, o sistema de rastreamento da WBS não possui estrutura de dados para armazenar o histórico de porcentagens de progresso em cada tarefa. Consequentemente, o valor obtido pode ser informado somente a partir da hora em que o cubo é processado. Processe o cubo regularmente para atualizar os dados de valor obtido mostrados na Central de Funções. 

**Custo real** A teoria do EVM afirma que o gráfico do custo real representa a taxa em que o dinheiro está sendo gasto no projeto. 

As transações que foram lançadas em um projeto são usadas para plotar a linha de custo real. Os custos são resumidos por data. Esses dados são então usados para plotar os custos reais por semana e por mês no gráfico de valor obtido.

### <a name="how-to-use-the-concepts-of-planned-value-earned-value-and-actual-cost"></a>Como usar os conceitos de valor planejado, valor obtido, e custo real

**Variação da agenda** Durante o planejamento, você cria uma previsão de trabalho em um cronograma. Consequentemente, o valor planejado é a taxa em que os planejadores de projeto pensaram que o trabalho trabalho seria realizado no projeto. Depois que um projeto está em andamento, o trabalho é concluído, e o projeto ganha valor. Ao comparar o valor planejado com o valor obtido, você pode visualizar como o trabalho em um projeto está progredindo. O resultado dessa comparação é chamado de variação da agenda. 

Se o valor planejado para um período é maior que o valor obtido, a quantidade de trabalho realizado em um projeto é menor do que o planejado. Consequentemente, o projeto está atrasado. Como o valor planejado e o valor obtido são expressos em termos monetários, o tempo de atraso em um projeto também recebe um valor monetário. 

Se o valor planejado para um período é menor que o valor obtido, a quantidade de trabalho realizado em um projeto é maior do que o planejado. Consequentemente, o projeto está adiantado. Este tempo de adiantamento também recebe um valor monetário.

**Variação de custo** Como o valor obtido usa o preço do custo como multiplicador, o valor obtido indica o custo do trabalho realizado em um projeto. Conforme um projeto avança, o registo de transações fornece um registro do dinheiro que foi realmente gasto no projeto. Ao comparar o valor obtido com o custo real, você pode visualizar a quantidade de dinheiro que está sendo gasto versus o valor obtido. O resultado dessa comparação é chamado de variação de custo. 

Se o custo real gasto durante um período é maior que o valor obtido, gastou-se mais dinheiro do que foi ganho. Consequentemente, o projeto está fora do orçamento. 

Se o custo real gasto durante um período é menor que o valor obtido, ganhou-se mais dinheiro do que foi gasto. Consequentemente, o projeto está dentro do orçamento.

## <a name="wbs-templates"></a>Modelos de WBS
Você pode usar a funcionalidade de modelos de WBS para criar modelos padrão de projetos. Se os projetos que sua empresa oferece envolvem muito trabalho repetitivo, você deve considerar a criação de um modelo de WBS. 

Você pode criar um modelo de WBS a partir da WBS de um projeto existente, de modo que o conhecimento e as práticas adquiridos durante o planejamento daquele projeto possam ser reutilizados em projetos similares no futuro. No entanto, às vezes, pode não fazer sentido salvar toda a WBS como um modelo. Consequentemente, você também pode criar modelos a partir de partes da WBS para um projeto.

### <a name="saving-a-projects-wbs-as-a-template"></a>Salvando uma WBS de projeto como um modelo

Depois de criar um modelo, você pode importá-lo em uma nova WBS de projeto dentro do nó raiz, ou dentro de qualquer tarefa da WBS de projeto.

### <a name="importing-a-wbs-template-into-a-projects-wbs"></a>Importando um modelo de WBS em uma WBS de projeto

Quando você importa tarefas, as tarefas no modelo são organizadas com base na data de início da tarefa para a qual são importadas. Durante a importação, as relações de antecessor nas tarefas do modelo são usadas para calcular as datas de início para as tarefas importadas. O calendário padrão de trabalho do projeto de meta é aplicado para calcular as datas finais das tarefas importadas, de modo que os dias úteis e as horas de trabalho padrão que estão definidas no calendário de trabalho atual do projeto sejam mantidos. 

Valores de custo e preços de venda nas linhas de estimativa são aplicados para garantir que os preços específicos de um projeto ou contrato de projeto tenham datas válidas.

### <a name="differences-between-a-projects-wbs-and-a-wbs-template"></a>Diferenças entre uma WBS de projeto e um modelo de WBS

-   As tarefas em modelos de WBS não possuem datas de início e término.

Os dias úteis e não úteis não são definidos para modelos de WBS.

-   Os modelos de WBS sempre usam o calendário de planejamento que foi definido como calendário padrão para todos os projetos.

O calendário de planejamento padrão é usado somente para localizar horas em um dia útil padrão.

-   As relações de antecessor não são copiadas para um modelo de WBS.

Como os modelos de WBS não possuem datas, a lógica da data de início baseada na data final de um antecessor não é necessária.

-   Uma linha de estimativa de custo da mão de obra é automaticamente criada quando uma tarefa é criada em um modelo de WBS. O preço de venda e o valor de custo são copiados do funcionário selecionado.

As despesas e os custos de item podem ser criados manualmente, assim como podem em uma WBS de projeto.

-   Os erros de planejamento são exibidos quando existem desvios na seguinte fórmula:

Esforço = Número de recursos × Duração × Número de horas em um dia útil padrão no calendário 

Você pode corrigir erros de plano ao mesmo tempo clicando **Corrigir erros de plano**. 

Como alternativa, você pode corrigir erros de planejamento individualmente clicando no ícone de aviso de cada tarefa.




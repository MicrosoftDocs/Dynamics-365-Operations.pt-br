---
title: "Integração do plano de orçamento com outros módulos"
description: "Os planos de orçamento podem ser gerados a partir de vários recursos diferentes. Os elementos básicos do processo periódico são iguais para todos os recursos."
author: ShylaThompson
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BudgetPlanGenerate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 64443
ms.assetid: f9a94db5-906c-404a-9ca5-91528d67c490
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 4a18190152b6e5ea520a81f1db2cf67ded652bbe
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---

# <a name="budget-planning-integration-with-other-modules"></a>Integração do plano de orçamento com outros módulos

[!include [banner](../includes/banner.md)]

 Os planos de orçamento podem ser gerados a partir de vários recursos diferentes. Os elementos básicos do processo periódico são iguais para todos os recursos. 



<a name="periodic-processes-for-generating-budget-plans"></a>Processos periódicos para gerar planos de orçamento
----------------------------------------------

Os planos de orçamento podem ser gerados nos seguintes recursos:

-   Transações de contabilidade
-   Ativos fixos
-   Previsões de posições
-   Previsões de projeto
-   Previsões de fornecimento
-   Previsões de demanda
-   Entradas de registro de orçamento
-   Outros planos de orçamento

Os elementos básicos do processo periódico são iguais para todos os processos. As guias permitem definir a fonte dos dados, os atributos de destino (plano de orçamento) e as opções para executar o processo em segundo plano como um processo em lote. As seções posteriores deste artigo descrevem os itens que podem não ficar visíveis em cada processo.

### <a name="actions"></a>Ações

Para cada processo de geração, há três ações disponíveis:

-   **Criar um novo plano de orçamento** cria um novo plano que têm os atributos que são selecionados na seção **Destino**. Esses atributos não precisam ser exclusivos. Portanto, dois planos podem ter o mesmo nome e outros valores.
-   **Substituir o cenário existente de plano de orçamento** exclui todos os dados do plano de orçamento de destino no cenário de plano de orçamento selecionado e cria novas linhas que usam os dados de origem selecionado.
-   **Atualizar o cenário existente de plano de orçamento e acrescentar novos dados** atualiza as linhas no plano de destino que correspondem às linhas de origem e adiciona novas linhas para novos dados. A correspondência baseia-se na conta contábil, na data, na classe de orçamento e em vários outros campos. Por exemplo, quando você gera planos de orçamento a partir das posições de previsão, o número da posição é um campo importante. Todas as linhas que têm um número de posição correspondente ao número de posição de origem são substituídas pelas novas linhas da origem.

### <a name="source"></a>Fonte

Em todos os processos, a guia **Origem** permite filtrar dados por meio do botão **Filtro**. Por padrão, são adicionados campos específicos ao filtro de cada processo. Por exemplo, no processo **Gerar plano de orçamento da contabilidade**, as categorias **Conta contábil** e **Conta principal** estão disponíveis e aparecem na página de geração. Todos os campos que você adicionar ao filtro também serão adicionados à página, juntamente com os critérios que você adicionar.

### <a name="target"></a>Destino

A opção **Histórico** na guia **Destino** permite que você use as datas dos dados de origem como data efetiva no plano de orçamento. Normalmente, a data efetiva deve estar dentro do ciclo orçamentário do plano. Quando você define a opção **Histórico** para **Sim**, a data (até mesmo o ano) da origem é utilizada, para que você possa usar os dados anteriores como base para a comparação. Não é possível modificar dados históricos no plano de orçamento, e o plano é definido para um status de fluxo de trabalho aprovado. No entanto, você poderá redefinir o status se outros cenários no plano precisar de alterações.

O campo **Total agregado por** na parte superior da página também determina a data utilizada. O campo totaliza os valores e, opcionalmente, define a data efetiva para o primeiro dia do ano fiscal ou do período fiscal. 

Vários campos na guia <strong>Destino</strong> se tornam editáveis ou somente leitura, dependendo da ação selecionada. Quando você deixa de criar um novo plano de orçamento para atualizar um plano existente, o campo **Nome do plano de orçamento** se torna indisponível, e os campos relacionados à seleção de um plano existente é disponibilizado. Nas guias **Destino** e **Origem**, o campo **Razão** está sempre indisponível, porque o valor é determinado pelo processo de planejamento de orçamento selecionado. 

O campo **Classe de orçamento** permite que você defina as linhas do plano de orçamento como transações de despesa ou transações de receita. Geralmente, as transações de receita são creditados em uma conta contábil e, portanto, são armazenadas como valores negativos. Normalmente, essas transações também aparecem como valores negativos no plano de orçamento. No entanto, ao adicionar a classe de orçamento como um campo no layout do plano, você poderá habilitar a receita para aparecer como valores positivos.

### <a name="generation-rules"></a>Regras de geração

Três campos fornecem funcionalidade adicional: **Fator**, **Mínimo**, e **Regra de** **arredondamento**. 

O valor no campo **Fator** é multiplicado pelo valor de origem para definir o valor no plano de orçamento. Você poderá, então, fazer ajustes ao criar linhas de plano de orçamento. Por exemplo, você pode inserir **1,03** para um aumento de 3%. O fator deve ser um número positivo. 

O campo **Mínimo** permite que você defina o valor de limite para criar uma linha de plano de orçamento. Se o valor de origem for menor que esse número, a linha do plano de orçamento não será criada. O valor **0,00** permite todos os valores, mas não limita linhas para valores positivos. (Nenhum valor limita linhas para valores positivos. Os valores negativos são sempre incluídos e geralmente representam entradas de crédito.)

O campo **Regra arredondamento** permite que você defina a precisão das linhas de plano de orçamento criadas. Você pode arredondar os valores para o que for mais próximo de 1,00, 10,00, 100,00 da moeda e assim por diante.

## <a name="notes-for-specific-processes"></a>Observações para processos específicos
### <a name="generate-budget-plan-from-general-ledger"></a>Gerar plano de orçamento da contabilidade

Ao criar um plano de orçamento a partir dos dados da contabilidade, você precisará definir o campo **Total agregado por** para **Ano fiscal** se a opção **Histórico** for definida como **Não**. Os períodos e as datas da origem podem não corresponder aos períodos nas datas do destino. Como o processo não oferece uma maneira confiável de mapear esses valores, você deve limitá-lo ao primeiro do ano. 

No destino, o campo **Classe de orçamento** é definido como **Despesa** ou **Receita**. Essa configuração será usada para selecionar o atributo **Tipo de orçamento** para as linhas criadas, quando a conta principal em uma linha não for do tipo **Receita** ou **Despesa**.

### <a name="generate-budget-plan-from-fixed-assets"></a>Gerar plano de orçamento a partir dos ativos fixos

O processo **Gerar plano de orçamento a partir dos ativos fixos** não tem nenhuma opção para realizar a agregação por período ou dia. Também não há nenhuma opção para definir o plano como histórico. Você pode usar esse processo periódico para incluir transações projetadas de ativos fixos no planejamento de orçamento.

### <a name="generate-budget-plan-from-forecast-positions"></a>Gerar plano de orçamento a partir da previsão de posições

O processo **Gerar plano de orçamento a partir da previsão de posições** atribui a previsão de posição de origem à linha do plano de orçamento. Você pode exibir a posição adicionando a previsão de posição como uma linha no layout do plano de orçamento ou usando a consulta **Linhas do plano de orçamento**. Se você não deseja que a previsão de posição seja atribuída às linhas do plano de orçamento, defina a opção **Incluir posição na linha do plano de orçamento** para **Não**.

As linhas do plano de orçamento são agregadas por conta contábil e posição. No entanto, você pode excluir o número da posição, de modo que as linhas sejam agregadas somente por conta contábil. Na guia **Destino**, defina a opção **Incluir posição na linha do plano de orçamento** para **Não**.

No campo **Cenário FTE do plano de orçamento**, você pode selecionar um cenário para incluir o número de FETs (equivalentes ao tempo completo) do plano de orçamento. Esse campo limita-se aos cenários de tipo de quantidade que estão incluídos no layout do plano de orçamento de destino. Se você selecionar um cenário de FTE, também deverá selecionar uma conta principal de FTE. Essa conta é usada para criar as linhas de plano de orçamento da quantidade. 

O processo de planejamento de orçamento e o cenário de plano de orçamento selecionados na origem definem o processo de planejamento de orçamento do cenário de destino e o cenário. Como esses atributos são atribuídos às previsões de posição, eles devem corresponder ao plano de orçamento. Portanto, esses atributos não podem ser modificados no destino.

### <a name="generate-budget-plan-from-project-forecasts"></a>Gerar plano de orçamento a partir de previsões do projeto

O processo **Gerar plano de orçamento a partir de previsões do projeto**, assim como o processo **Gerar plano de orçamento a partir da previsão de posições**, tem uma opção para incluir quantidades de projeto (horas, despesas e itens e) em um cenário de quantidade. Os dois processos também têm filtros similares para as colunas no layout do plano de orçamento. 

Na guia **Origem**, três opções na seção **Incluir demonstrativo** determinam quais linhas do plano de orçamento são criadas. Essas opções são iguais às opções disponíveis quando você cria entradas de registro de orçamento diretamente das previsões de projeto. Defina a opção **Lucro e perda** para **Sim** a fim de criar linhas para custos e receitas. Defina opção **WIP** para **Sim** a fim de criar entradas do trabalho em andamento. Defina a opção **Alocação de folha de pagamento** para **Sim** a fim de criar linhas para as contrapartidas de folha de pagamento das transações de hora. 

Não há campo **Classe de orçamento** porque a classe de orçamento (**Despesa** ou **Receita**) é determinada pela origem. 

Você pode usar orçamentos de projeto como origem selecionando o modelo de previsão que contém os valores de orçamento do projeto. Lembre-se de que os orçamentos de projeto criam entradas de previsão do projeto à medida que elas são aprovadas.

Para selecionar somente os custos ou as receitas das linhas de plano de orçamento, use o filtro para selecionar <strong>Atualizações de orçamento: Tipo de valor = Custo</strong>. Para selecionar somente um tipo de previsão, use o filtro para selecionar <strong>Atualizações de orçamento: Tipo de transação = *xxx</strong>*. 

Somente um modelo de previsão pode ser usado para gerar um cenário de plano de orçamento. Se você executar o processo para um modelo de previsão e, em seguida, fizer uma atualização e tentar especificar outro modelo, o primeiro modelo será substituído se o mesmo projeto e contas contábeis forem aplicáveis. Para gerar um cenário de plano de orçamento com base em mais de um modelo de previsão, gere cenários de plano de orçamento diferentes e use as opções de alocação para uni-los em outro cenário. 

O processo **Gerar plano de orçamento a partir de previsões do projeto** também atribui o projeto de origem à linha do plano de orçamento.

### <a name="generate-budget-plan-from-supply-forecast"></a>Gerar plano de orçamento a partir da previsão de fornecimento

As opções de filtro de origem do processo **Gerar plano de orçamento a partir da previsão de fornecimento** foram modeladas após as opções da função **Transferir orçamento de compras para razão** devido às similaridades entre o processo e a função.

### <a name="generate-budget-plan-from-demand-forecast"></a>Gerar plano de orçamento a partir de previsões de demanda

No processo **Gerar plano de orçamento a partir de previsões de demanda**, você pode definir a opção **Ordem de venda** para **Sim** a fim de gerar linhas de receita no plano de orçamento, definir **Consumo** para **Sim** a fim de criar linhas de despesa ou definir as duas opções para **Sim**.

### <a name="generate-budget-plan-from-budget-register-entries"></a>Gerar o plano de orçamento a partir de entradas do registro de orçamento

No processo **Gerar o plano de orçamento a partir de entradas do registro de orçamento**, a origem deve especificar um submodelo, um código de orçamento e um número de entrada. Em outras palavras, você pode criar linhas de plano de orçamento apenas para uma entrada de registro de orçamento por vez. Você pode usar entradas adicionais no mesmo plano de orçamento executando o processo uma vez para cada entrada de origem.

### <a name="generate-budget-plan-from-budget-plan"></a>Gerar plano de orçamento a partir do plano de orçamento

No processo **Gerar plano de orçamento a partir do plano de orçamento**, um conjunto adicional de opções na guia **Destino** permite que você atribua novas dimensões financeiras. Se uma dimensão financeira for selecionada, esse valor será usado para todas as linhas do plano de orçamento. Portanto, você pode usar um plano de orçamento como base para outros planos de orçamento, mas também pode atribuir, por exemplo, um departamento ou um centro de custo diferente para os novos planos de orçamento.

## <a name="looking-back-from-the-budget-plan"></a>Rever o plano de orçamento
### <a name="budget-plans-by-dimension-set-inquiry"></a>Planos de orçamento por consulta do conjunto de dimensões

A consulta **Planos de orçamento por conjunto de dimensões** inclui várias opções que permitem executar uma consulta para identificar a origem dos dados do plano de orçamento. 

Selecione uma linha e clique no botão **Linhas do plano de orçamento** para executar a consulta **Linhas do plano de orçamento**. Os resultados são filtrados para os valores de dimensão da linha selecionada. Em seguida, você poderá aplicar parâmetros adicionais. 

Use os botões **Previsão de fornecimento** e **Previsão de demanda** para executar essas consultas. Nos dois casos, a consulta procura as linhas de previsão que podem ter criado as linhas do plano de orçamento. 

Os relatórios adicionais disponíveis incluem o relatório **Previsão de posições por plano de orçamento**. Esse relatório é especialmente útil quando você deseja determinar se uma posição foi alocada corretamente para os planos de orçamento.





---
title: Previsão de posição
description: As despesas relacionadas a trabalhadores costumam constituir uma grande proporção dos custos de uma organização. A previsão de posição permite planejar as despesas e incluí-las no planejamento de orçamentos.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmPositionForecast
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 64413
ms.assetid: 35e791d2-1905-4808-a579-7f181ddddd91
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d5bae90cf7c8f11fa5409014023d36cc68ae1bd0
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770864"
---
# <a name="position-forecasting"></a>Previsão de posição

[!include [banner](../includes/banner.md)]

As despesas relacionadas a trabalhadores costumam constituir uma grande proporção dos custos de uma organização. A previsão de posição permite planejar as despesas e incluí-las no planejamento de orçamentos.

## <a name="position-forecasting-in-budget-planning"></a>Previsão de posição no planejamento de orçamento

[![Componentes de previsão de posição](./media/graphic-top.png)](./media/graphic-top.png) 

A previsão de posição usa três componentes principais para fornecer valores de orçamento exatos para despesas de posições. Esses valores podem ser trazidos para um plano de orçamento para cálculos de orçamento. 

O componente principal é a **posição de previsão**, que representa todos os dados de custo relacionados a uma única posição. Você pode criar várias versões de uma posição de previsão ao atribuir um cenário diferente do plano de orçamento para cada versão. Várias versões permitem uma abordagem iterativa para orçamentos e permitem comparar cenários de teste de hipóteses. Cada posição de previsão tem uma posição correspondente em Recursos Humanos.

Um **Elemento de custo de orçamento** é um componente de configuração que representa um custo específico que é associado a uma posição, como pagamento base, seguro saúde pago pelo empregador, permissões de telefone celular e assim por diante. Um elemento de custo de orçamento inclui a conta principal que é usada para o custo e opções para o cálculo. Cada elemento de custo de orçamento pode ser atribuído a várias posições de previsão. 

Um **grupo de remuneração** é um componente de configuração opcional que é usado para aplicar um conjunto de elementos de custo de orçamento e cálculos de pagamento a posições com características semelhantes de pagamento. Um grupo de remuneração pode incluir uma grade de remuneração de taxas de pagamento. Quando o grupo é atribuído a uma posição de previsão, um nível e uma etapa na grade podem atribuir os ganhos da posição de previsão. O conjunto de elementos de custo é adicionado automaticamente.

### <a name="position-forecasting-processes"></a>Processos de previsão de posição

[![Ilustração de processos de previsão de posição](./media/graphic1b.png)](./media/graphic1b.png) 

Em um processo típico de previsão da posição, crie primeiro os componentes de configuração (elementos de custo de orçamento e grupos de remuneração). As posições de previsão são geradas com base em posições existentes. É possível fazer ajustes. Por exemplo, você pode adicionar ou finalizar posições, mudar taxas de pagamento e custos de benefício, e adicionar aumentos de salário. Você pode criar várias versões de uma posição de previsão para facilitar comparações entre diferentes cenários de orçamento. Em seguida, você pode incluir as posições de previsão em planos de orçamento e incluir os custos das posições de previsão como linhas do plano de orçamento.

Você pode criar versões adicionais da posição de previsão à medida que planos de orçamento são revisados. Essas novas versões fornecem a base das revisões.

## <a name="position-forecasting-setup"></a>Configuração da previsão de posição
[![Ilustração que realça a configuração](./media/graphic2-1024x327.png)](./media/graphic2.png)

### <a name="budget-cost-elements"></a>Elementos de custo do orçamento

Os elementos de custo de orçamento são usados para definir os detalhes de custo de uma posição de previsão. Esses detalhes incluem o tipo de custo, como os custos são calculados, e se os custos são alocados em várias datas quando a posição de previsão é incluída em um plano de orçamento. 

Os campos específicos definem o comportamento do elemento de custo de orçamento. Cada elemento de custo de orçamento recebe um tipo de custo de orçamento em **Ganho**, **Benefício**, **Impostos** ou **Outros**. Os tipos de custos de orçamento são usados principalmente para calcular totais. O valor **Substituição da posição de previsão** especifica se os valores do elemento podem ser modificados na posição de previsão. O campo **Método de alocação** é usado quando uma posição de previsão é adicionada a um plano de orçamento. Você pode dividir o valor de custo em linhas separadas do plano de orçamento que têm datas diferentes, a cada mês, trimestre, semana ou quinzena. Selecione uma data de início para atribuir os custos como um único valor na data inicial definida na posição de previsão. 

O cálculo do valor de custo do elemento de custo de orçamento usa datas efetivas para habilitar o mesmo elemento de custo a ser usado em períodos diferentes. Uma única conta principal é atribuída em cada período, junto com uma porcentagem ou valor anual que indica o valor do custo. Um elemento de custo de orçamento pode usar uma porcentagem de outros elementos de custo ou um valor anual, mas não ambos. Você também pode especificar um limite anual. 

Se o elemento de custo se baseia em uma porcentagem, você deve especificar os elementos de custo de orçamento usados como a base do cálculo.

**Exemplo** 

A organização de Jodi oferece uma bonificação de treinamento de 5% do pagamento base de um funcionário. Jodi deseja criar um elemento de custo de orçamento para esse custo. Ela cria um novo elemento de custo de orçamento e atribui o tipo de custo de orçamento **Benefício**.

Jodi não quer que os gerentes mudem o valor do benefício. Então, ela seleciona **Não permitir alterações de custo** no campo **Substituição da previsão de posição**. A organização deseja que esse custo seja atribuído uniformemente a cada mês. Então, a Jodi seleciona **Trimestral** no campo **Método de alocação**. 

Em seguida, a Jodi adiciona uma linha de cálculo de custo, define as datas e uma conta principal, e insere **5.00** como porcentagem. Sua organização tem uma capitalização de $5.000 por ano de benefício. Portanto, Jodi insere esse valor como o limite anual. 

Por fim, Jodi adiciona todos os elementos de custo de ganho usados para o pagamento base como as bases de cálculo. Seu elemento de custo de orçamento agora está pronto para ser usado.

### <a name="compensation-groups"></a>Grupos de remuneração

Os grupos de remuneração podem ser usados para agrupar a posição de previsão com atributos de remuneração semelhantes. Eles também podem ser usados para definir os ganhos de uma posição de previsão e os aumentos anuais, e para atribuir um conjunto de elementos comuns de custo de orçamento. 

Uma função básica de grupos de remuneração é atribuir um conjunto de elementos de custo de orçamento a uma posição de previsão. Assim, os grupos de remuneração podem ser usados para adicionar custos comuns, como planos de benefícios e impostos. Um gerente que esteja criando uma posição de previsão não precisa saber todos os elementos de custo que devem ser adicionados. Os elementos de custo podem ser adicionados quando o grupo de remuneração é selecionado. Os elementos são adicionados à configuração do grupo de remuneração na guia **Elementos de custo do orçamento**. 

Os grupos de remuneração também podem determinar as taxas de ganhos para uma posição de previsão. Você configura um grupo para usar com base no salário por hora ou por ano para calcular os ganhos da posição de previsão. Na guia **Tabelas de taxa de remuneração**, uma grade de compensação de taxas de pagamento determina os ganhos que são adicionados a uma posição de previsão, com base em nível e etapa atribuídos. Essas grades podem ser baseadas em grades de remuneração existentes em Recursos Humanos. Como alternativa, você pode criar novas grades de remuneração para o planejamento de orçamento. 

As datas efetivas e as datas de vencimento nas tabelas de taxa de remuneração permitem alterar as taxas de pagamento em qualquer data. Este recurso é útil quando uma unidade de negociação negocia um aumento global em um ciclo orçamentário. Nesse caso, você altera a data de vencimento da tabela existente do dia antes da data de alteração de taxa e adiciona uma nova tabela de taxa que comece na nova data. Quando você cria uma nova tabela de taxa, se selecionar **Criar uma nova grade de remuneração a partir de uma grade existente**, você pode selecionar uma tabela existente de taxa de recursos humanos. Na tabela de taxa que é criada, a opção **Alteração em Massa** permite aplicar uma porcentagem ou um aumento/redução de valor fixo a todas as taxas da grade. 

Os campos **Agenda de aumentos** e **Data do aumento** no grupo de remuneração são usados quando você precisa criar aumentos de pagamento pois as posições passam de uma etapa à seguinte. Um aumento de pagamento anual é um cenário típico. A agenda de aumentos determina se a data de aniversário de posições ou uma única data comum é usada para o aumento da etapa. A agenda de aumentos se aplica a todas as previsões de posições no grupo de remuneração. 

O elemento de custo de ganho selecionado no grupo de remuneração é usado quando você cria os ganhos para as previsões de posições no grupo, incluindo o pagamento base e todos os aumentos de etapa. O campo **Plano de remuneração fixa** vincula o grupo de remuneração a um plano de remuneração fixa em Recursos humanos. Esse link pode atribuir as informações de remuneração fixa de um trabalhador a uma previsão de posição, e pode tornar o planejamento de orçamento mais preciso. Lembre-se de que a estrutura da grade de compensação (os níveis e as etapas) para o grupo de remuneração deve corresponder à estrutura do plano de remuneração fixa. Caso contrário, o sistema não pode vincular corretamente o grupo de remuneração e o plano de remuneração fixa.

## <a name="creating-forecast-positions"></a>Como criar previsões de posições
[![Ilustração que realça "criar posições de previsão"](./media/graphic3-1024x327.png)](./media/graphic3.png)

### <a name="creating-forecast-positions-for-existing-positions"></a>Como criar previsões de posições para posições existentes

Para obter o planejamento de orçamento mais preciso, você pode criar previsões de posições usando detalhes das posições existentes, esteja a posição preenchida ou não no momento. 

A função **Adicionar posições existentes** exibe todas as posições para uma organização. Ao definir a data **A partir de**, você pode mudar a lista de posições para que ela contenha as posições que existiam em uma data anterior ou posterior, que é mais comum (por exemplo, o início do próximo ciclo orçamentário). Selecione um cenário de processamento de planejamento e de plano do orçamento, selecione posições na lista e clique em **OK** para criar previsões de posições para as posições selecionadas. Observe que você pode criar apenas uma previsão de posição para cada posição existente em cenário de processamento de planejamento de orçamento. No entanto, você pode criar versões adicionais, atribuindo cenários diferentes do plano de orçamento. 

Se os elementos de custo de orçamento tiverem sido atribuídos à posição em Recursos humanos, os elementos de custo de orçamento também serão atribuídos à previsão de posição e usarão os valores padrão. O campo **Trabalhador atribuído** na previsão de posição é definido como o nome do trabalhador atribuído à posição, caso um trabalhador seja atribuído. Este campo é um campo de texto simples. Nenhum link direto é criado. 

Se um elemento de custo de orçamento estiver selecionado, o valor anual de remuneração fixa será atribuído à previsão de posição usando o elemento de custo selecionado, desde que o trabalhador atribuído tenha um plano de remuneração fixa. Se o trabalhador não tiver um plano de remuneração fixa, ou se nenhum trabalhador for atribuído, o valor padrão será usado para o elemento de custo de orçamento. 

Quando a opção **Atribuir um grupo de remuneração** está definida como **Sim**, se o trabalhador atribuído à posição tem um plano de remuneração fixa baseado em etapa que está vinculado a um grupo de remuneração (conforme descrito antes), o nível e a etapa do trabalhador são atribuídos à previsão de posição, junto com o grupo de remuneração. O elemento de custo de orçamento de ganhos do grupo de remuneração é adicionado à previsão de posição. A taxa de pagamento é usada no nível e na etapa do grupo de remuneração. 

A configuração da opção **Atribua um grupo de remuneração** tem precedência sobre a configuração **Atribuição do elemento de custo de orçamento**. As duas configurações podem ser usadas ao mesmo tempo. 

[![Gráfico "Atribuir um grupo de compensação"](./media/graphic4.png)](./media/graphic4.png) 

Outra opção é atribuir uma data de aniversário. A data selecionada (data inicial ajustada, data inicial do trabalhador, data inicial de emprego ou data de tempo de serviço) do trabalhador atribuído está definida como a data de aniversário da previsão de posição, e é usada para informações e quando aumentos de pagamento são gerados.

### <a name="creating-new-forecast-positions"></a>Como criar novas previsões de posições

Você pode criar novas previsões de posições de duas maneiras: copiando uma previsão de posição existente e criando uma previsão de posição totalmente nova. 

Quando uma previsão de posição for selecionada, selecione **Copiar a previsão de posição selecionada** para criar uma nova previsão de posição com um estado de previsão **Proposto**. Esta previsão de posição tem os mesmos dados que a previsão de posição que foi copiada, exceto o trabalhador atribuído e as observações sobre os elementos de custo de orçamento. Observe que uma nova posição correspondente também é criada em Recursos humanos. Esta posição tem uma descrição **Criado pela previsão**. 

Você também pode criar uma previsão de posição totalmente nova. Selecione um trabalho existente, e também o cenário de processamento de planejamento do orçamento e de plano de orçamento. Você pode adicionar outros detalhes a serem adicionados. Mais uma vez, uma nova posição é criada em Recursos humanos ao mesmo tempo.

## <a name="working-with-forecast-positions"></a>Trabalho com previsões de posições
[![Ilustração que realça "modificar posições de previsão"](./media/graphic5-1024x327.png)](./media/graphic5.png)

### <a name="multiple-versions-of-a-forecast-position"></a>Várias versões de uma previsão de posição

Você pode mudar as previsões de posições para aplicar as alterações conhecidas para o ciclo orçamentário ou modelar as alterações propostas. Uma prática comum é criar uma linha de base definida de previsões de posições, criar cópias dessas previsões de posições e usar as cópias para modelar diferentes conjuntos de alterações. As cópias são atribuídas a um cenário de plano de orçamento diferente mas, pelo menos até que as alterações sejam feitas, são idênticas às previsões de posições de onde são copiadas. Os originais e s cópias compartilham a mesma posição em Recursos humanos. 

A função **Copiar em cenário** fornece essa funcionalidade. Observe que cada posição de Recursos humanos pode ter uma previsão de posição em cada cenário do plano de orçamento.

### <a name="modifying-forecast-positions"></a>Como modificar previsões de posições

As alterações feitas em previsões de posições se limitam a essas previsões de posições. As alterações não afetam os registros de posição em Recursos humanos. A maioria das alterações também se limitam à previsão de posição que está sendo editada. Ou seja, as alterações são específicas do cenário de processamento do planejamento de orçamento e do plano de orçamento que são atribuídos. As exceções são alterações nos campos que são compartilhados para a posição em processos e cenários. Estes campos incluem os campos na guia **Geral** e na guia **Dimensões financeiras** . Quando esses campos são alterados, os novos valores são aplicados à posição em todos os cenários de planejamento de orçamento. Portanto, esses campos permitem atualizar rapidamente todas as versões.

#### <a name="budget-cost-elements"></a>Elementos de custo do orçamento

Os elementos de custo de orçamento fornecem as informações principais para planos do orçamento: o valor do orçamento e a conta principal. O valor do orçamento é o valor que é enviado ao plano de orçamento quando uma previsão de posição é incluída em um plano. O valor do orçamento é calculado e não pode ser diretamente alterado. Esse valor é o valor anual ou um cálculo da porcentagem dos elementos base do valor anual (conforme definido na configuração do elemento de custo de orçamento). O valor é fatorado pelo número de dias no intervalo de datas do elemento (data de inicial até data final) e também pelo valor **Equivalente ao horário integral** (FTE) para a previsão de posição. 

Por exemplo, uma linha do elemento de custo de orçamento desde 1º de janeiro de 2017 até 30 de junho de 2017, com um valor anual de 100.000 e um valor FTE de **0,50**, é calculada como 100.000 × (181 dias ÷ 365 dias) × 0,50 = 24.794,52. 

As linhas de elementos de custo de orçamento devem ser recalculadas quando o valor FTE é alterado na previsão de posição. As linhas também devem ser recalculadas quando as datas de ativação ou s datas de aposentadoria são modificadas. As alterações nessas datas podem causar uma atualização das datas inicial e final do elemento de custo de orçamento, que devem estar no intervalo de datas da previsão de posição. Quando é necessário um recálculo, o botão **Recalcular** fica disponível e a mensagem “Requer cálculo” é exibida. O recálculo é necessário também se você adiciona ou remove um elemento de custo de orçamento.

**Exemplo** 

A organização está considerando duas opções para reduzir o custo de uma posição de contador. Uma opção é encerrar a parte da posição até o final do ano. A outra opção é alterar a posição para metade do ano inteiro. Brad criou uma previsão de posição para a posição de contador existente em um cenário da linha de base. Ele copia esta previsão de posição da linha de base no cenário A, define a data de aposentadoria como 31 de maio e recalcula. Brad copia a previsão de posição da linha de base no cenário B, altera o valor de FTE para **0,50** e recalcula. Agora Brad tem três versões, cada qual com o total de custo alinhado com suas opções.

#### <a name="assigning-a-compensation-group"></a>Atribuição de um grupo de remuneração

Quando você atribui primeiro um grupo de remuneração a uma previsão de posição, os elementos de custo de orçamento padrão do grupo de remuneração são adicionados. Se os elementos de custo já são atribuídos à previsão de posição, esses elementos de custo permanecem. Se um grupo de compensação tiver sido atribuído e estiver sendo alterado, os elementos de custo de orçamento existentes serão removidos e substituídos pelo conjunto do grupo de remuneração. 

Quando você seleciona um nível e uma etapa de remuneração, um elemento de custo de orçamento de ganhos (conforme definido no grupo de remuneração) é adicionado. O valor anual é calculado usando a taxa no nível e na etapa selecionados, e as horas anuais no grupo de remuneração (ou, para salários com base anual, no valor total no nível e na etapa). Novamente, esse valor é fatorado pelo intervalo de datas da linha de elemento de custo e o valor FTE da previsão de posição.

#### <a name="generating-increases"></a>Como gerar aumentos

Os aumentos anuais (um por ano civil) podem ser criados automaticamente para posições de previsão que têm um grupo de remuneração baseado em etapa atribuído. Clique em **Gerenciar aumentos** para adicionar um elemento de custo de orçamento de ganhos na próxima etapa mais alta. A data inicial do elemento de custo do novo orçamento de ganhos é a data agendada do aumento que aparece na previsão de posição. Essa data é definida no grupo de remuneração de duas formas. Se o plano de aumento do grupo de remuneração estiver definida como **Data comum**, a data de aumento será especificada no grupo de remuneração. Se o plano de aumento for definido como **Data de aniversário**, o campo de data de aniversário na previsão de posição será usado, e o ciclo orçamentário fornecerá o ano. Se houver vários anos civis em um ciclo orçamentário, vários aumentos serão adicionados. 

A data final do elemento de custo de orçamento atual de ganhos é atualizada com o dia antes da data de aumento. O processo de recálculo é usado automaticamente quando são gerados aumentos. Portanto, não é necessário recalcular manualmente. 

Se você clicar em **Gerar aumentos** uma segunda vez, o processo será executado novamente mas não adicionará mais registros. É criado apenas um aumento por ano civil.

#### <a name="changes-from-other-pages"></a>Alterações de outras páginas

As atualizações para previsão de posições também ocorrem em outras áreas, como o elemento de custo de orçamento e as páginas de configuração do grupo de remuneração. Você também pode modificar as previsões de posições usando o processo de atualização em massa. 

Há duas opções disponíveis na página de configuração **Elemento de custo de orçamento**: **Adicionar a posições** e **Atualizar posições**. A opção **Adicionar a posições** adiciona o elemento de custo de orçamento às previsões de posições selecionadas. Se o elemento já estiver atribuído a uma previsão de posição, essa previsão de posição será ignorada. A opção **Atualizar posições** aplica os valores atuais (a conta principal, a porcentagem, o valor anual e assim por diante) nas previsões de posições selecionadas. 

Cada processo tem uma página semelhante onde você pode selecionar previsões de posições. A página **Adicionar a posições** mostra todas as previsões de posições disponíveis para seleção, enquanto a página **Atualizar posições** mostra apenas as previsões de posições que já têm o elemento de custo de orçamento atribuído. (Portanto, a página **Atualizar posições** oferece uma forma de encontrar quais posições de previsão já têm o elemento de custo vinculado.) Você move as posições de previsão de uma grade superior a uma inferior para incluí-las na atualização. 

Observe que a função **Alterar datas** na guia **Cálculo de custo** altera imediatamente as datas inicial e final do elemento de custo de orçamento nas previsões de posições. Nenhuma opção de seleção está disponível. 

Na página **Grupo de remuneração**, a função **Atualizar taxas de posição** aplica as taxas da tabela atual de taxas de remuneração para prever as posições atribuídas ao grupo. As taxas são atualizadas, e as linhas adicionais do elemento de custo são adicionadas para as novas linhas da tabela de taxa (com base em datas). No entanto, os elementos de custo de orçamento e as datas de aumento não estão atualizados. Você pode selecionar o cenário de processamento de planejamento do orçamento e de plano de orçamento a ser atualizado. Assim, você pode atualizar um cenário, mas manter outros cenários inalteradas para comparação. 

Ao selecionar previsões de posições e clicar em **Atualização em massa**, você pode adicionar ou modificar mais de uma previsão de posição ao mesmo tempo. Muitas opções estão disponíveis. Uma opção na guia **Dimensões financeiras** diferente um pouco das outras e está relacionada a elementos de custo de orçamento. Você pode adicionar os elementos de custo de orçamento definindo a opção **Padrões de orçamento** como **Sim**. Se nenhum elemento de custo de orçamento for selecionado, mas **Padrões de orçamento** estiver definido como **Sim**, todos os elementos de custo de orçamento atribuídos no momento serão removidos. 

O processo de recálculo é usado automaticamente em qualquer previsão de posição que tenha sido alterada.

## <a name="bringing-forecast-positions-into-budget-plans"></a>Como trazer previsões de posições para planos de orçamento

[![Ilustração que realça "Adicionar ao plano de orçamento"](./media/graphic6-1024x327.png)](./media/graphic6.png)

A finalidade de criar e modificar previsões de posições é adicioná-las a planos de orçamento, de modo que esses planos incluam os valores de orçamento mais precisos. Há dois métodos para adicionar previsões de posições a planos de orçamento. Você pode usar um processo de geração ou um processo de seleção no plano de orçamento.

### <a name="generating-a-budget-plan-from-forecast-positions"></a>Como gerar um plano de orçamento a partir de previsões de posições

A função **Gerar plano de orçamento a partir da previsão de posições** cria ou atualiza planos de orçamento de modo que tenham os valores de orçamento e as contagens de FTE de previsões de posições. Os valores de orçamento da previsão de posição se tornam os valores da linha do plano de orçamento e são agregados por valores de dimensão financeira e data de efetivação. O processo de geração atribui a previsão de posição de origem à linha do plano de orçamento. Para exibir a posição, você pode adicionar a previsão de posição como uma linha no layout do plano de orçamento ou usar a consulta **Linhas do plano de orçamento**. Para ignorar essa atribuição, defina a opção **Incluir posição na linha do plano de orçamento** como **Não**. 

Você pode selecionar um cenário de FTE do plano de orçamento para incluir o número de FTEs no plano de orçamento. É possível selecionar apenas cenários do tipo de quantidade que estão incluídos no layout do plano de orçamento de destino. Ao selecionar um cenário de FTE, especifique também uma conta principal de FTE. Essa conta é usada para criar as linhas de plano de orçamento da quantidade. 

O processo de planejamento de orçamento e o cenário do plano de orçamento que são selecionados na origem determinam o processo de planejamento de orçamento do cenário de destino e o cenário. Como esses atributos são atribuídos às previsões de posições, eles devem estar sincronizados com o plano de orçamento. Portanto, os atributos não podem ser editados no destino. 

Quanto aos processos de geração, há três opções disponíveis:

-   **Criar um novo plano de orçamento** – Criar um novo plano com os atributos que são selecionados na seção **Destino**.
-   **Substituir o cenário existente de plano de orçamento** – Excluir todos os dados do plano de orçamento de destino no cenário de plano de orçamento selecionado e criar novas linhas com os dados de previsão de posição selecionados.
-   **Atualizar o cenário de plano de orçamento existente e anexar novos dados** – Atualizar linhas existentes no plano de destino que correspondam às linhas de origem, e adicionar novas linhas para novos dados. A correspondência é baseada na conta contábil, data, classe de orçamento e outros valores, como a previsão de posição. Todas as linhas que têm um número de posição correspondente ao número de posição de origem são substituídas pelas novas linhas da origem.

### <a name="selecting-forecast-positions"></a>Seleção de previsões de posições

Você também pode adicionar valores de orçamento da previsão de posição diretamente a um plano de orçamento. Use a função **Adicionar posições** acima das linhas do plano de orçamento para selecionar as previsões de posições a serem incluídas. 

Os cenários do plano de orçamento que você pode selecionar como a origem se limitam aos cenários que são incluídos no layout do plano. Uma opção na guia **Destino** permite especificar que o cenário e a conta principal de FTE estão disponíveis para incluir contas FTE, mas não são necessários. 

Este processo de seleção comporta-se como a opção **Atualizar o cenário do plano de orçamento existente e anexar novos dados** para um processo de geração. Todas as linhas existentes do plano de orçamento, onde a previsão de posição está sendo adicionada, são removidas e substituídas por novas linhas que se baseiam no estado atual da previsão de posição.

#### <a name="date-options"></a>Opções de data

Para o processo de geração e o processo de seleção, a data inicial na linha de elemento de custo de orçamento determina a data de efetivação da linha correspondente do plano de orçamento. O campo **Método de alocação** na página de configuração do elemento de custo de orçamento especifica o método de alocação:

-   **Data inicial** – A data inicial do elemento de custo de orçamento é usada como a data de efetivação da linha do plano de orçamento.
-   **Mensal** – O valor do orçamento é dividido uniformemente pelo número de meses no intervalo de datas para gerar um valor mensal típico que é atribuído no primeiro dia de cada mês. Se o primeiro período é um mês parcial, o valor desse mês é fatorado pelo número de dias em que os custos estão ativos nesse mês, e o resultado é atribuído à data inicial. O valor do último mês é a diferença entre o valor do orçamento total e a soma dos demais meses. Assim, o arredondamento pode afetar o valor do último mês.
-   **Trimestral** – Este método é o mesmo que **Mensal**, mas os cálculos são feitos por períodos de três meses.
-   **Semanal** – A lógica é semelhante à lógica dos métodos **Mensal** e **Trimestral**. O valor do orçamento é dividido uniformemente pelo número de semanas no intervalo de datas para gerar um valor semanal típico que é atribuído no primeiro dia de cada semana. Se o primeiro período é uma semana parcial, o valor dessa semana é fatorado pelo número de dias em que os custos estão ativos nessa semana, e o resultado é atribuído à data inicial. O valor da última semana é a diferença entre o valor do orçamento total e a soma das demais semanas. Assim, o arredondamento pode afetar o valor da última semana.
-   **Quinzenal** – Este método é o mesmo que **Semanal**, mas os cálculos são feitos por períodos de duas semanas.

#### <a name="changing-budget-plan-lines-that-have-forecast-positions"></a>Como alterar as linhas do plano de orçamento com previsões de posições

As linhas do plano de orçamento mostram a origem dos valores de orçamento (o número da previsão de posição), mas não estão vinculadas. Portanto, as alterações na previsão de posição não são mostradas na linha do plano de orçamento, e as alterações na linha do plano de orçamento são mostradas na previsão de posição. Se você alterar uma previsão de posição e desejar que as atualizações sejam incluídas em um plano de orçamento, traga a previsão de posição para o plano novamente. No entanto, lembre-se de que esse processo remove todas as linhas onde essa previsão de posição é atribuída. Consequentemente, quaisquer alterações feitas nessas linhas são removidas. 

Para ver em que planos de orçamento uma previsão de posição foi incluída, você pode gerar o relatório **Previsão de posições por plano de orçamento**. Como alternativa, na previsão de posição, você pode abrir o Quadro de Fatos **Planos de orçamento associados** para exibir os planos.




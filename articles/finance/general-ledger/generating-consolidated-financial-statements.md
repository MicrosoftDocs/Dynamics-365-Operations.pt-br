---
title: Gerar demonstrativos financeiros consolidados
description: Este tópico descreve os vários cenários em que você pode gerar demonstrativos financeiros consolidados.
author: aprilolson
manager: AnnBe
ms.date: 07/09/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: a32fb8cce4353f57155fc7a723aa90e3c17178e6
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770680"
---
# <a name="generate-consolidated-financial-statements"></a>Gerar demonstrativos financeiros consolidados

[!include [banner](../includes/banner.md)]

Este tópico descreve os vários cenários em que você pode gerar demonstrativos financeiros consolidados.

## <a name="single-level-and-multilevel-consolidations-across-legal-entities"></a>Consolidações de nível único e de vários níveis em entidades legais
O método mais simples de consolidação por meio de relatórios financeiros é usar as hierarquias organizacionais para agregar dados em empresas com o mesmo plano de contas e os mesmos períodos fiscais. Aqui estão as etapas de alto nível para consolidação por meio de uma hierarquia organizacional.

1. Crie uma definição de linha e verifique se todas as contas apropriadas em todas as empresas estão incluídas nas linhas.
2. Crie uma definição de coluna que inclua todas as colunas necessárias para o relatório que você está criando.
3. Crie uma hierarquia organizacional que inclua um nó de relatório para cada empresa que você está usando em relatórios consolidados.

> [!TIP]
> Para obter mais informações sobre como criar e gerenciar definições de linha, definições de coluna e hierarquias organizacionais, consulte [Componentes de relatórios financeiros](../../dev-itpro/analytics/financial-report-components.md).

A ilustração a seguir mostra como usar uma definição de hierarquia organizacional no Relatório financeiro para identificar cada empresa que você consolidará.

![Definição de hierarquia organizacional](./media/reporting-tree-definition.png "Definição de hierarquia organizacional")

Como mostra o relatório consolidado na ilustração a seguir, quando você usa a hierarquia organizacional em conjunto com uma definição de relatório, é possível exibir cada empresa separadamente. Os valores consolidados são mostrados no nível de resumo.

![Consolidar nível de resumo de valor](./media/consolidate-amount-summary-level.png "Consolidar nível de resumo de valor")

Você também pode criar uma hierarquia organizacional de vários níveis que inclua quantos níveis forem necessários. A ilustração a seguir mostra uma definição de hierarquia organizacional de vários níveis que possui acúmulos por região mundial.

![Definição de árvore de relatório de vários níveis com acúmulos por região](./media/multilevel-reporting-tree-definition-roll-ups-worldwide-region.png "Definição de árvore de relatório de vários níveis com acúmulos por região")

A ilustração a seguir mostra uma definição de hierarquia organizacional de vários níveis que possui acúmulos por função.

![Definição de árvore de relatório de vários níveis com acúmulos por função](./media/multilevel-reporting-tree-definition-roll-ups-by-function.png "Definição de árvore de relatório de vários níveis com acúmulos por função")

### <a name="viewing-companies-side-by-side"></a>Exibição de empresas lado a lado
Muitos clientes preferem relatórios em que as empresas aparecem lado a lado e onde uma coluna mostra o total consolidado. É fácil obter esse formato após a criação da hierarquia organizacional. Aqui estão as etapas de alto nível para exibir as empresas lado a lado nos demonstrativos financeiros consolidados.

1. Crie uma definição de coluna que inclua uma coluna **Dimensão financeira** para cada empresa.
2. Use o campo **Unidade organizacional** para selecionar a hierarquia e a unidade organizacional para cada coluna.
3. Opcional: adicione cabeçalhos e colunas totais.

A ilustração a seguir mostra uma definição de coluna em um formato lado a lado.

![Definição de coluna em um formato lado a lado](./media/column-definition-side-by-side-format.png "Definição de coluna em um formato lado a lado")

## <a name="consolidations-that-use-organization-structures-that-are-created-from-legal-entities"></a>Consolidações que usam estruturas organizacionais criadas a partir de entidades legais
Hierarquias de organização que contêm dimensões ou entidades legais criam dinamicamente as definições de hierarquia organizacional no Relatório financeiro. Uma maneira fácil de otimizar as consolidações é adicionar uma hierarquia da organização ao seu relatório no Relatório financeiro. Com base na data do relatório, o Relatório financeiro selecionará a hierarquia da organização na e antes da data de efetivação, conforme mostrado na ilustração a seguir.

![Criar dinamicamente uma definição de árvore de relatório](./media/dynamically-create-reporting-tree-definitions.png "Criar dinamicamente uma definição de árvore de relatório")

## <a name="consolidations-that-involve-eliminations"></a>Consolidações que envolvem eliminações
As transações de eliminação são uma parte comum do processo de consolidação. Neste exemplo, cinco contas são eliminadas durante a consolidação: 142600, 211400, 401420, 401180 e 510820. As empresas podem configurar suas contas intercompanhia de maneira diferente. Por exemplo, algumas empresas definem o último dígito como 9, se a conta for usada em transações intercompanhia. Independentemente do método, se conhecer as contas intercompanhia, você pode mostrar eliminações em seus demonstrativos financeiros consolidados.

A ilustração a seguir mostra uma definição de coluna para um demonstrativo de rendimento consolidado. Três contas intercompanhia de lucros e perdas são definidas para cada empresa usando o filtro de dimensão. A coluna D inclui as contas de eliminação apenas para a empresa USMF enquanto a coluna E inclui eliminações apenas para a empresa DEMF. Tanto a coluna D como a coluna E estão configuradas para que **não** sejam impressas no demonstrativo financeiro.

![Demonstrativo de receita consolidada com definição de coluna](./media/column-definition-consolidated-income-statement.png "Demonstrativo de receita consolidada com definição de coluna")

Quando o relatório é gerado, os valores de eliminação são calculados nas colunas F, G e H e são totalizados na coluna I. A coluna J mostra os valores consolidados. Esses valores de consolidação excluem as eliminações das empresas USMF, USRT e DEMF.

> [!TIP]
> Crie um segundo relatório que mostre apenas as entradas de eliminação e use-o em um grupo de relatórios que inclua seu relatório consolidado. Dessa forma, você terá todas as informações necessárias para criar qualquer entrada de diário necessária.

A ilustração a seguir mostra o relatório consolidado.

![Demonstrativo de receita de relatório consolidado](./media/consolidated-report-income-statement.png "Demonstrativo de receita de relatório consolidado")

Se usar contas, dimensões ou ambos, o Relatório financeiro permite descartar as entradas de eliminação utilizando os recursos de filtragem de dimensão.

## <a name="minority-interest"></a>Interesse minoritário
Uma empresa pode possuir apenas uma porcentagem de outra empresa. Nessa situação, quando você está produzindo um relatório consolidado, é importante que você contabilize apenas a porcentagem que a empresa possui. O Relatório financeiro tem várias maneiras de apresentar o interesse minoritário, dependendo da preferência do usuário. Uma delas é usar um percentual de acúmulo na definição de hierarquia organizacional. Outra maneira é mostrar a participação minoritária como uma linha separada em um relatório.

### <a name="using-the-reporting-tree-definition"></a>Usando a definição de hierarquia organizacional
Na definição de hierarquia organizacional, insira o percentual de participação na coluna **Porcentagem de acúmulo** (coluna H), conforme mostrado na ilustração a seguir. Quando o relatório for gerado, esse percentual será usado para calcular o valor consolidado. Neste exemplo, a Contoso possui apenas 80% da Contoso Alemanha. Você pode inserir **80** ou **,8** na coluna **Porcentagem de acúmulo** e 80% será acumulado no nível consolidado.

> [!NOTE]
> Você pode aplicar essa porcentagem de participação a qualquer unidade organizacional, não apenas no nível da empresa. 

![Uso de porcentagem na definição de árvore de relatório](./media/Using-reporting-tree-definition-percentage.png "Uso de porcentagem na definição de árvore de relatório")

Quando o relatório for gerado, o relatório da Contoso Alemanha mostrará 100% do valor das vendas, e 80% do valor será alocado e acumulado no nível consolidado para vendas.

Se você possuir menos de 1% de uma empresa, é possível marcar a caixa de seleção **Permitir acúmulo inferior a 1%** na guia **Opções adicionais** da página **Configurações do relatório**, conforme mostrado na ilustração a seguir. Nesse caso, os valores na coluna **Porcentagem de acúmulo** na hierarquia organizacional serão tratados como menos de 1%. Por exemplo, se você inserir **,8**, 0,8% será acumulado no nível consolidado, não 80%. Como alternativa, você pode obter o mesmo resultado deixando a caixa de seleção **Permitir acúmulo inferior a 1%** desmarcada e inserindo **,008** na coluna **Porcentagem de acúmulo**.

![Opções de configuração de relatório](./media/reporting-setting-options.png "Opções de configuração de relatório")

### <a name="showing-ownership-as-a-separate-row-on-the-consolidated-report"></a>Mostrando a participação como uma linha separada no relatório consolidado
Outra opção para participação minoritária é mostrar 100% da subsidiária para cada linha no relatório, mas subtrair o interesse não controlador da receita líquida.

Como mostra a ilustração a seguir, uma instrução **IF THEN ELSE** e a restrição de coluna na definição de linha podem ser usadas para calcular o interesse minoritário em relatórios financeiros.

![Mostrando a participação como uma linha separada no relatório consolidado](./media/Showing-ownership-separate-row-consolidated-report.png "Mostrando a participação como uma linha separada no relatório consolidado")

## <a name="multiple-charts-of-accounts-across-legal-entities"></a>Vários gráficos de contas em entidades legais
Em geral, entidades legais diferentes têm planos de contas diferentes, mas ainda desejam produzir demonstrativos financeiros consolidados. Nessa situação, o Relatório financeiro pode ser usado para consolidar os dados, para que você possa gerar relatórios financeiros consolidados. Aqui estão as etapas de alto nível para consolidação quando diferentes gráficos de contas existirem em entidades legais.

1. Crie uma definição de linha que tenha vários links para dimensões financeiras. Deve haver um link para cada plano de contas.
2. Use a restrição da unidade organizacional na definição da coluna para atribuir cada empresa à coluna apropriada.


Vários links para dimensões financeiras podem ser adicionados a cada linha na definição de linha para o plano de contas exclusivo de cada empresa. Na ilustração a seguir, a empresa USMF usa o conjunto de contas na primeira coluna **Vincular a Dimensões Financeiras** (coluna J) e a empresa DEMF usa as contas na segunda coluna **Vincular a Dimensões Financeiras** (coluna K).

> [!TIP]
> Para obter mais informações sobre a célula **Vincular a Dimensões Financeiras**, consulte Especificar a célula Vincular a Dimensões Financeiras

![Definir primeiro link de contas para dimensões financeiras](./media/set-accounts-first-Link-to-Financial-Dimensions.png "Definir primeiro link de contas para dimensões financeiras")

Você pode usar uma hierarquia organizacional para definir qual link para dimensões financeiras da definição de linha será usado em cada empresa. Selecione a definição de linha na coluna E e, em seguida, selecione o link de linha apropriado na coluna F, conforme mostrado na ilustração a seguir.

![Definição de Vincular linha de dimensões financeiras usada](./media/link-financial-dimensions-row-definition-used.png "Definição de Vincular linha de dimensões financeiras usada")

> [!TIP]
> Ao criar links para dimensões financeiras, use a descrição para identificar as empresas às quais cada link se aplica. Dessa forma, você poderá selecionar mais facilmente a empresa correta ao criar uma hierarquia organizacional. Na definição da coluna, o campo **Unidade organizacional** permite restringir cada coluna a uma unidade de hierarquia organizacional para que você possa exibir os dados lado a lado. Se você não indicar uma empresa específica para uma coluna, os dados consolidados de todas as empresas serão exibidos.

## <a name="different-fiscal-calendars-across-multiple-legal-entities"></a>Calendários fiscais diferentes em várias entidades legais
Entidades legais diferentes podem ter calendários fiscais diferentes, mas ainda precisam produzir demonstrativos financeiros consolidados. Existem duas maneiras de consolidar quando diferentes períodos fiscais existem em entidades legais:

- Crie uma definição de coluna e use o período e o ano para mapear os períodos apropriados para cada empresa.
- Em **Configurações** \> **Outros** \> **Opções adicionais**, selecione se deseja consolidar usando a data final do período ou o número do período.

Ao projetar a definição da coluna para várias empresas com períodos fiscais diferentes, é importante considerar qual empresa será atribuída ao campo **Nome da empresa** na definição de relatório. O calendário fiscal dessa empresa será usado como o calendário fiscal base para a definição de relatório. Por exemplo, a tabela a seguir mostra a configuração do período fiscal para as empresas USMF e INMF. Para relatórios consolidados, você deseja utilizar o calendário fiscal empregado pelo USMF. A coluna "Mapeamento" mostra o período e o ano equivalentes para cada empresa se um relatório for gerado para 30 de junho de 2018.

| Empresa   | Ano fiscal                                  | Mapeamento                     |
|-----------|----------------------------------------------|-----------------------------|
| USMF      | Ano fiscal, 1º de julho a 30 de junho          | Período 12, ano fiscal 2018 | 
| INMF      | Ano civil, 1º de janeiro a 31 de dezembro | Período 6, ano fiscal 2018  |

Na ilustração a seguir, a empresa USMF é especificada no campo **Nome da empresa** na definição de relatório. Portanto, o calendário fiscal da empresa USMF será usado como o calendário fiscal base. Neste exemplo, quando um relatório é gerado para 30 de junho de 2018, a empresa USMF usará o período BASE, que é definido como o período 12 na definição de relatório. A empresa INMF usará o BASE–6, que é o período 6. Ambas as colunas incluirão dados para junho de 2018.

![Período base do relatório](./media/report-base-period.png "Período base do relatório")

A ilustração a seguir mostra as opções na definição de relatório que permitem selecionar se o número do período ou a data final do período é usada para a consolidação.

![Número de período de definição de relatório de opções](./media/options-report-definition-period-number.png "Número de período de definição de relatório de opções")

## <a name="business-unit-consolidations"></a>Consolidações da unidade de negócios
Este tópico se concentrou no uso de definições de hierarquia organizacional e hierarquias da organização no Relatório financeiro para fins de consolidação. Você também pode usar a hierarquia organizacional para criar relatórios de consolidação de unidades de negócios, como relatórios sobre vendas ou operações em todo o mundo. Esses relatórios são um requisito comum. Para criá-los, selecione uma empresa e uma dimensão para cada unidade na qual deseja realizar a consolidação. Por exemplo, na ilustração a seguir, o acúmulo da unidade de negócios é realizado pela repetição de cada empresa na coluna **Empresa** (coluna A) e pela identificação de um grupo de valores de dimensão do departamento por empresa na coluna **Dimensões** (coluna D).

![Relatórios de consolidação da unidade de negócios](./media/business-unit-consolidation-reports.png "Relatórios de consolidação da unidade de negócios")

## <a name="consolidations-that-involve-multiple-reporting-currencies"></a>Consolidações que envolvem várias moedas de relatório
O Relatório financeiro oferece maior flexibilidade ao exibir dados reais, de orçamento, de controle de orçamento e de planejamento de orçamento em várias moedas. Ao fornecer dados de configuração de chave, você não precisa fazer nenhuma configuração adicional no Relatório financeiro para exibir qualquer relatório, em qualquer moeda e a qualquer momento, para qualquer usuário.

### <a name="prerequisites"></a>Pré-requisitos
Para calcular corretamente os saldos convertidos, o relatório financeiro exige que a categoria **Conta de ganhos retidos** seja atribuída à Conta de ganhos retidos na lista **Conta principal**. O Relatório financeiro não permite o lançamento na Conta de ganhos retidos. Se as transações forem lançadas na Conta de ganhos retidos, os saldos convertidos não serão calculados corretamente. Recomendamos que os usuários configurem uma Conta de ganhos retidos adicional para lançar ajustes na Conta de ganhos retidos.

Na conta principal, os campos **Tipo de taxa de câmbio de relatório financeiro** e **Tipo de conversão de moeda** da Guia Rápida **Relatórios financeiros** deve ser definido para cada conta, conforme mostrado na ilustração a seguir. Você pode concluir essa tarefa por conta ou usar os modelos de conta para facilitar a rolagem das alterações.

- No campo **Tipo de taxa de câmbio de relatório financeiro**, selecione o tipo de taxa de câmbio que contém as moedas e as taxas de câmbio a serem aplicadas à conta. Essa tabela de moedas e taxas de câmbio será aplicada aos dados reais no Relatório financeiro.
- No campo **Tipo de conversão de moeda**, selecione o método usado para calcular a taxa de câmbio da conta. Esse método de moeda é usado para dados reais e de orçamento no Relatório financeiro.

![Contas principais de relatório financeiro](./media/Financial-reporting-main-accounts.png "Contas principais de relatório financeiro")

Para dados de orçamento, controle de orçamento e planejamento de orçamento, o tipo de taxa de câmbio é definido na página **Razão**. Essa tabela será usada para extrair as taxas de câmbio, e o tipo de conversão de moeda atribuído à conta será usado.

### <a name="currency-translation-methods"></a>Métodos de conversão de moeda
Existem quatro opções para calcular as taxas de câmbio no Relatório financeiro:

- **Média ponderada** – Este método é usado com mais frequência para contas de lucros e perdas. Usa a seguinte fórmula:

    (Taxa de câmbio × Dias aplicados) ÷ Dias no período

- **Média** – Este método é um método alternativo para contas de lucros e perdas. Usa a seguinte fórmula:

    Total de taxas de câmbio ÷ Número de taxas de câmbio

- **Atual** – Este método é usado com mais frequência para as contas de balanço. A taxa de câmbio usada é a taxa na ou antes da data do relatório ou coluna no Relatório financeiro.
- **Data da transação** – Este método é usado para contas de ativos fixos. A taxa de câmbio usada é a taxa no dia em que o ativo foi adquirido. Se uma taxa não for inserida para essa data, a taxa anterior inserida mais próxima à data de aquisição do ativo será usada.

### <a name="report-designer-options-for-currency-translation"></a>Opções do designer de relatórios para conversão de moeda
No Relatório financeiro, qualquer relatório pode ser exibido em qualquer número de moedas de relatório. Os seguintes campos na definição de relatório permitem tal recurso:

- Na seção **Informações da moeda** na página **Definição de Relatório**. Esta seção mostra a moeda em que os valores são exibidos quando um relatório é gerado.
- Uma nova caixa de seleção **Incluir todas as moedas de relatório**. Quando essa caixa de seleção é marcada, um relatório para cada moeda de relatório será adicionado à fila de relatórios após a criação do relatório que usa a moeda funcional da empresa. Se a caixa de seleção estiver desmarcada, você ainda poderá selecionar uma moeda de relatório no Visualizador da Web. Nesse caso, a moeda de relatório será processada somente quando você a selecionar.

As opções na definição de relatório permitem converter facilmente um relatório em todas as suas moedas de relatório. Portanto, você poderá eliminar definições de relatório duplicadas que diferem apenas nas moedas usadas. Se precisar de um relatório que mostre várias moedas lado a lado, é possível continuar usando o campo **Exibição de Moeda** na página **Definição da coluna** para converter apenas essa coluna do relatório em uma moeda de relatório alternativa.

### <a name="currency-translation-adjustment"></a>Ajuste de conversão de moeda
O ajuste de conversão de moeda (currency translation adjustment, CTA) é a diferença entre as taxas usadas para calcular as contas de balanço e a taxa usada para as contas de demonstrativo de rendimento. Essa diferença fará com que o balanço fique distorcido. Você pode usar o Relatório financeiro para calcular o CTA de duas maneiras:

- Use a página **Ajustes de arredondamento** na definição da linha, conforme mostrado na ilustração a seguir.

    ![Ajustes de arredondamento de ajuste de conversão de moeda](./media/Currency-translation-adjustment-rounding-adjustments.png "Ajustes de arredondamento de ajuste de conversão de moeda")

    Quando você especifica a linha que deve mostrar o ajuste de arredondamento (CTA), a linha de total de ativos, o total de passivos, a linha de patrimônio e o limite com o qual você está confortável, o Relatório financeiro vai calcular a diferença e colocá-la na linha desejada. Uma linha nomeada **Ajuste de arredondamento** será criada e mostrada após busca detalhada, conforme mostrado na ilustração a seguir.

    ![Detalhamento de ajuste de arredondamento](./media/rounding-adjustment-drill-down.png "Detalhamento de ajuste de arredondamento")

- Coloque todas as contas em um intervalo, de ativos para despesas. Conforme mostrado na ilustração a seguir, a diferença será a mesma quantidade que o ajuste de arredondamento (CTA). Portanto, você pode usá-lo como um total de verificação para garantir que a página de ajuste de arredondamento não inclua saldos de conta perdidos.

    ![Verificação de formulário de ajuste de arredondamento](./media/rounding-adjustment-form-check.png "Verificação de formulário de ajuste de arredondamento")

### <a name="balance-calculation-approach"></a>Abordagem de cálculo de saldo
Para obter valores convertidos corretamente quando moedas são usadas, o Relatório financeiro usa os seguintes métodos de cálculo para os saldos:

- **Média ponderada e média** – Cada período é calculado com base na média ponderada e é totalizado para colunas como trimestral e anual.
- **Histórica** – Qualquer conta que usa o método de conversão histórica sempre retorna à data da transação. Se uma data de aquisição estiver associada à transação, tal data será usada para obter a taxa de câmbio. Cada período é então totalizado e armazenado para ajudar a melhorar o tempo de cálculo.
- **Atual** – As colunas calculadas e totais, como as colunas trimestral e anual, são calculadas na taxa à vista determinada na coluna ou no relatório. Por exemplo, a coluna **Trimestre 1** usará a taxa de 31 de março se um ano civil for usado.

## <a name="additional-resources"></a>Recursos adicionais

Para obter mais informações sobre consolidação e conversão de moeda, consulte o tópico principal deste tópico, [Visão geral de consolidações financeiras e conversão de moeda](./financial-consolidations-currency-translation.md).

Para obter mais informações sobre como inserir detalhes de consolidações online, consulte [Consolidações financeiras online](./consolidate-online.md).

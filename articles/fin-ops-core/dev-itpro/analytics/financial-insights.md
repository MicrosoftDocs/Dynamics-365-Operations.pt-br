---
title: Análise financeira
description: A análise financeira usa o Microsoft Power BI para reunir indicadores da chave de desempenho (KPIs) financeiros, gráficos e demonstrativos financeiros.
author: kweekley
ms.date: 08/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 106233
ms.assetid: 517e6a88-e7a1-4398-9971-b22fa83306ba
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 21d7d045c812c54d6776394ad9a0b025b55df8e1
ms.sourcegitcommit: 3289478a05040910f356baf1995ce0523d347368
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2022
ms.locfileid: "9109102"
---
# <a name="financial-analysis"></a>Análise financeira

[!include [banner](../includes/banner.md)]

A **Análise financeira** usa o Microsoft Power BI para reunir indicadores da chave de desempenho (KPIs) financeiros, gráficos e demonstrativos financeiros. O Power BI está inserido no aplicativo. O foco da **Análise financeira** é o relatório analítico. As pessoas de uma organização podem exibir, pesquisar, entender e atuar. 

A **Análise financeira** combina dados da contabilidade e dos razões auxiliares para fornecer uma visão mais completa da saúde financeira de uma organização.

> [!NOTE]
> Este documento usa a seguinte terminologia do Power BI:
> 
> - **Relatório** – Um arquivo .pbix único no qual todos os recursos visuais de todas as guias são salvos.
> - **Página** – Uma guia em um arquivo .pbix único. Cada página pode conter um ou mais recursos visuais.
> - **Recurso Visual** – Uma única fonte de dados, como um cartão, um KPI, um gráfico, um gráfico, uma matriz ou um demonstrativo financeiro. Uma página que tem um demonstrativo financeiro como um recurso visual não pode ter outros recursos visuais devido ao volume de dados que está sendo reportado.

O espaço de trabalho **Análise financeira** se concentra em permitir que você exiba e filtre os dados em relatórios existentes. Você poderá adicionar novos recursos visuais ao espaço de trabalho **Análise financeira**. O espaço de trabalho **Análise financeira** está disponível para a empresa atual, bem como para todas as empresas para mostrar os dados de todas as entidades legais, independentemente das entidades legais às quais a função tem acesso.

- [Adicionar ou editar visualizações do Power BI no painel](/powerapps/user/add-powerbi-dashboards)

## <a name="dynamics-365-finance-setup"></a>Configuração do Dynamics 365 Finance
**Contabilidade**

O tipo de conta principal e as categorias da conta principal são usados para preencher as contas principais padrão apropriadas no demonstrativo financeiro do **Balanço** e nos diversos demonstrativos financeiros de **Demonstração de lucros e perdas** na **Análise financeira**.

Na página **Contas principais** , você deve definir a conta principal, de modo que um dos seguintes tipos seja atribuído a ela:

- Receita
- Expense
- Ativos
- Passivo
- Capital próprio

Não atribua nenhum outro tipo de conta principal, como **Balanço** ou **Lucros e perdas**, às contas principais. O relatório pode determinar o tipo de conta principal no qual outros tipos de conta principais estão atribuídos porque não são granulares o suficiente. O tipo de conta principal deve ser determinado para mostrar passivos e receita como valores positivos nos relatórios financeiros.

Para aparecer em demonstrativos financeiros e para ser incluída em vários outros elementos visuais, como KPIs, cada conta principal deve ser atribuída a uma categoria de conta principal. As categorias de conta principal foram aprimoradas para que tenham uma ordem de exibição. A ordem de exibição é usada especificamente em demonstrativos financeiros na **Análise financeira**. Depois de editar ou adicionar uma nova categoria de conta principal, você pode alterar o valor da **Ordem de exibição** para definir a ordem em que as categorias de conta principais devem ser mostradas em um demonstrativo financeiro. Se for necessário alterar a ordem de exibição de muitas categorias de conta principal, você poderá usar o recurso Abrir no Excel para editar e publicar as alterações rapidamente no aplicativo.

## <a name="entity-store"></a>Repositório de entidades
Os dados da **Análise financeira** são recebidos do repositório de entidades (**Administrador do sistema** \> **Configurar** \> **Repositório de entidades**). Se você abrir o espaço de trabalho **Visão geral do CFO** ou **Análise financeira** e a seguinte mensagem de aviso for exibida nos elementos visuais, você deverá atualizar as entidades.

![Aviso.](./media/Cantdisplay.png)

Você deve atualizar as seguintes entidades para ver os dados nos espaços e trabalho **Análise financeira**:

- Dados de transação de relatórios financeiros versão 3 
- Crédito e cobranças V2
- LedgerCovLiquidityMeasurement
- Cubo de Compras
- Cubo de Vendas

Você pode definir um lote recorrente para atualizar regularmente os dados nas entidades. Como cada entidade é recriada completamente durante uma atualização, selecione a hora e frequência de atualizações da entidade cuidadosamente. A entidade principal usada para demonstrativos financeiros é a entidade FinancialReportingTransactionData. Portanto, você pode decidir atualizar essa entidade com mais frequência.

## <a name="security"></a>Segurança
No momento, os dados nos relatórios incorporados do Power BI não podem ser limitados às entidades legais às quais o usuário tem acesso. Por isso os relatórios incorporados do Power BI são controlados por meio de direitos na configuração de segurança. Os direitos definidos permitem acesso a dados de todas as entidades legais ou somente à empresa ativa. A tabela a seguir mostra os direitos que existem e as funções às quais eles estão atribuídos. Os direitos podem ser removidos ou atribuídos a diferentes funções, com base nos requisitos de sua organização.

| Obrigação                                    | Funções | descrição |
|-----------------------------------------|-------|------------|
| Exibir análise financeira da empresa atual | <ul><li>Contador</li><li>Gerente de contabilidade</li><li>Supervisor de contabilidade</li><li>Auditor</li><li>Gerente de orçamentos</li><li>Diretor executivo</li><li>Diretor financeiro</li><li>Controlador financeiro</li></ul> | Esta obrigação fornece acesso à análise financeira. Por padrão, a empresa ativa é usada como um filtro. Você não pode adicionar outras entidades legais. |
| Exibir análise financeira de toda a empresa   | No Microsoft Dynamics 365 Finance, Enterprise Edition 7.3, esse direito não é atribuído a uma função. Na próxima versão, essa obrigação será atribuída à função Diretor financeiro. | Esta obrigação fornece acesso ao item de menu do espaço de trabalho visão geral de CFO. Por padrão, a empresa ativa é usada como um filtro. Entretanto, você pode adicionar todas as entidades legais, independentemente de o usuário ter acesso às outras entidades legais. |


## <a name="financial-reporting-vs-financial-analysis"></a>Relatório financeiro vs. Análise financeira
Embora a **Análise financeira** contenha demonstrativos financeiros, eles não são substituem os Relatórios financeiros no aplicativo. Os demonstrativos financeiros padrão na **Análise financeira** são limitados no escopo e não incluem todos os tipos de demonstrativos financeiros. O relatório financeiro ainda é a ferramenta principal para projetar, criar e gerar demonstrativos financeiros estatutários.

O gráfico de comparação a seguir ajudará a diferenciar as duas opções:


| Recurso                                                   | Financial Reporting                                               | Análise financeira |
|----------------------------------------------------------|-------------------------------------------------------------------|--------------------|
| **Editar relatórios padrão**                                 | Sim                                                               | Não |
| **Criar novos relatórios**                                   | Sim                                                               | Não |
| **Imprimir relatórios**                                        | Sim                                                               | Não |
| **Exportar para o Excel**                                      | Sim                                                               | Limitado Exporta dados brutos para o Excel, não um relatório formatado |
| **Hierarquia de relatórios com suporte/hierarquia organizacional**   | Sim                                                               | Não |
| **Relatório de dados no razão auxiliar**                             | Sim Limitado somente ao fornecedor, cliente                              | Sim Fornecedor, cliente, grupos de fornecedores/clientes, endereços de fornecedor/cliente, etc. |
| **Moeda de Relatório**                                   | Sim Moeda contábil e traduz para a moeda de relatório       | Não Somente moeda contábil |
| **Segurança**                                             | Sim Adere ao Finance e à segurança da hierarquia organizacional | A exibição limitada relata para todas as empresas (independentemente da segurança de finanças e operações) ou somente para a empresa ativa |
| **Oferece suporte a diferentes planos de contas e anos fiscais** | Sim                                                               | Não |
| **relatório sobre dados esternos**                              | Não                                                                | Não |
| **Oferece suporte a consolidações**                               | Sim                                                               | Limitado Pode reportar sobre várias empresas mas usa somente a moeda contábil |

Os seguintes demonstrativos financeiros estão disponíveis:

- Balancete
- Balanço
- Lucros e perdas por região
- Demonstração de lucros e perdas real vs. orçamento
- Demonstração de lucros e perdas com variações
- Demonstrativo de renda de tendência de 12 meses
- Tendência de três anos de despesas
- Despesas por fornecedor
- Vendas por cliente

## <a name="edit-visuals"></a>Editar elementos visuais
Nas versões anteriores da **Análise financeira**, nenhum recurso visual pode ser editado. Nas versões futuras, os usuários que têm a segurança apropriada poderão criar novos elementos visuais, copiar elementos visuais existentes e editar elementos visuais. Embora os arquivos de .pbix que contêm os relatórios estejam disponíveis como recursos, não recomendamos que você edite os relatórios padrão. Alterações adicionais serão feitas no modelo de dados, relatórios padrão e no elemento visual do demonstrativo financeiro que são usados para criar os demonstrativos financeiros. Assim, para aproveitar os novos recursos e as alterações feitas no modelo de dados na próxima versão, você terá que refazer todas as alterações feitas nos relatórios padrão via Microsoft Power BI Desktop.

## <a name="filtering"></a>Filtragem
Os usuários podem filtrar o relatório usando o painel **Filtro** à esquerda. Esse painel é igual ao painel que está disponível por meio do Power BI Desktop. Há vários níveis de filtragem, algumas talvez não estejam disponíveis, dependendo do que você selecionou em uma página (guia) ou se você está usando os recursos de análise.

- **Filtros de nível do relatório** – Esses filtros são aplicados a todos os elementos visuais em todas as páginas (guias).
- **Filtros do nível de página** – Esses filtros são aplicados a todos os elementos visuais na guia ativa. Esses filtros são aplicados na parte superior dos filtros em nível de relatório.
- **Filtros de nível visual** – Esses filtros são aplicados somente ao elemento visual selecionado. Esses filtros são aplicados na parte superior dos filtros em nível de página.
- **Filtro de análise** – Este filtro é aplicado de um elemento visual de "origem" que é aplicado ao elemento visual atual quando você analisar o elemento visual em relação ao elemento visual atual.

![Opções de filtro.](./media/filter.png)

Para remover um valor de filtro específico, selecione o símbolo de borracha próximo a ele. Não remova um filtro selecionando o X. Se você selecionar o X, o campo que está filtrando será removido como uma opção do filtro. Se você remover acidentalmente um campo do filtro, feche o espaço de trabalho e depois o reabra. As configurações padrão de filtros serão reaplicadas.

Por padrão, quando você abrir os espaços de trabalho pela primeira vez, a entidade legal ativa será usada como o filtro em nível de relatório. Dependendo da sua segurança, usuários conseguirão adicionar outras entidades legais ou alterar a entidade legal padrão que é selecionada no filtro.

O filtro **Calendário fiscal** é necessário para que o calendário correto seja usado para o elemento visual. Por padrão, o filtro em nível de relatório é definido para o calendário fiscal da entidade legal ativa. Se você alterar o filtro para um calendário fiscal que tem uma data inicial ou final diferente, os saldos iniciais não serão incluídos. Portanto, os demonstrativos financeiros **Balanço** não mostrarão os saldos corretos. Se você selecionar um calendário fiscal adicional no filtro, você terá um conjunto adicional de colunas. Cada conjunto adicional de colunas mostra os valores para um calendário fiscal diferente.

O filtro **Nível de lançamento** também é necessário. Por padrão, o filtro é definido como Atual. Você pode selecionar os níveis de lançamento adicionais no filtro para mostrar os valores agregados.

Os filtros também estão disponíveis para os campos **Data** e **Ano fiscal**. Normalmente, esses filtros são aplicados em nível de página. Por padrão, o filtro **Data** usa uma data relacional que você pode alterar. Você também pode remover o filtro de data relacional e usar o filtro **Ano fiscal**.

## <a name="currency"></a>Moeda

Todos os elementos visuais que reportam dados da contabilidade mostram valores na moeda contábil. Portanto, ao filtrar a entidade legal, você deverá ter cuidado para incluir somente entidades legais que têm a mesma moeda contábil. Caso contrário, você agregará dados em diferentes moedas.

Todos os elementos visuais que são reportados nos dados do razão auxiliar, como elementos visuais **Previsão de fluxo de caixa** e **Dez melhores**, mostram valores na moeda do sistema. A moeda do sistema e o tipo de taxa de câmbio do sistema são definidos na página **Parâmetros do sistema**.

O elemento visual **Saldo por conta bancária** usa valores na moeda da conta bancária.

## <a name="dimensions"></a>Dimensões

Os demonstrativos financeiros padrão não incluem nenhuma dimensão financeira, mas estão concentrados somente na conta principal. O suporte para dimensões financeiras estará disponível nas versões futuras, quando os relatórios se tornarem editáveis. As organizações poderão ser filtradas nos valores da dimensão financeira.

Alguns demonstrativos financeiros contêm dimensões baseadas em transações do razão auxiliar. O objetivo de novos demonstrativos financeiros é permitir filtragem em dimensões que não estão configuradas como dimensões financeiras. Por exemplo, as Despesas padrão por relatório de fornecedor permitem que você expanda além da conta principal, para que possa ver os saldos divididos pelo fornecedor. O fornecedor não será configurado como uma dimensão financeira. Em vez disso, o sistema retornará para a transação do diário auxiliar de origem para localizar o fornecedor.

As seguintes dimensões são usadas nos relatórios padrão. Nenhuma dessas dimensões são financeiras.

- Fornecedor
- Grupo de fornecedores
- Cliente
- Grupo de clientes
- País/região
- Estado/província
- Cidade

> [!IMPORTANT] 
> Se você resumir transações para vários fornecedores ou clientes em um comprovante único usando os diários financeiros, os dados ficarão incorretos. O processo do relatório não pode determinar qual fornecedor ou cliente está relacionado a uma conta contábil específica em uma entrada de diário porque essas informações não são mantidas em qualquer lugar. Portanto, não recomendamos que você insira vários fornecedores, clientes, ativos fixos ou projetos em um comprovante único.

## <a name="drill-on-data"></a>Consultar dados

Há vários níveis de análise disponíveis no Power BI. Cada nível tem um nome e funcionalidade diferente. Você também pode detalhar linhas e colunas. Esta seção discute várias opções usando o demonstrativo financeiro **Balancete** como um exemplo e mostrando como você pode detalhar as linhas. A mesma funcionalidade existe para as colunas. Você apenas deve alterar a configuração **Detalhar**.

Na ilustração a seguir, o demonstrativo **Balancete** é recolhido para o nível mais alto da hierarquia de linha, o tipo de conta principal.

![Demonstrativo de balancete.](./media/trial-balance.png)

Para exibir o próximo nível da hierarquia, as categorias de conta principal, você pode definir o campo **Detalhar** para **Linhas** e selecionar o botão **Expandir** (o terceiro botão após o campo Detalhar). Agora você verá todas as categorias contábeis principais expandidas. No momento, o Power BI não permite expandir somente uma linha ou coluna, mas ver todas as outras linhas ou colunas.

![Detalhamento do balancete nas linhas.](./media/trial-balance2.png)

Para expandir as contas principais para todas as linhas, você pode usar novamente o botão **Expandir**. Porém, para fazer busca detalhada nas contas principais para somente uma linha, primeiro selecione o botão **Busca detalhada** (a seta curva para baixo no lado direito da janela) e, em seguida, selecione a linha para fazer a busca detalhada. A ilustração a seguir mostra o resultado quando a linha **Vendas** for selecionada depois que o botão **Detalhar** for selecionado.

![Botão Expansão do balancete.](./media/trial-balance3.png)

Depois de fazer busca detalhada em uma única linha, vários cliques são necessários para retornar ao balancete completo. O botão **Fazer drill up** (o primeiro botão depois do campo **Detalhar**) faz drill up somente no contexto da categoria de **Vendas**, conforme mostrado na ilustração a seguir.

![Botão Drill up de balancete.](./media/trial-balance4.png)

Você pode continuar usando o botão **Fazer drill up** para retornar ao mais alto nível de resumo das linhas.

O Power BI também tem um botão que permite ir para o próximo nível na hierarquia (o segundo botão após o campo **Detalhar**). O efeito deste botão difere do efeito do botão **Expandir** (o terceiro botão após o campo **Detalhar**), que é usado para expandir a hierarquia. Quando você expande a hierarquia, ela é mantida no relatório. Por exemplo, como mostrado anteriormente, se expandir o tipo de conta principal, você ainda verá o tipo de conta principal no relatório. Porém, quando você avançar para o próximo nível da hierarquia, o relatório não mostrará mais o pai na hierarquia, conforme mostrado na seguinte ilustração.

![Botão Reversão de balancete.](./media/trial-balance5.png)

Para ver os detalhes da transação além dos saldos resumidos, você pode selecionar alguns valores para reverter no Financial and Operations.

A reversão do demonstrativo financeiro o conduz ao ASE (Gerenciador de fontes contábeis), não às transações de comprovante. O ASE não mostrará apenas as entradas contábeis na contabilidade. Em vez disso, ele exibirá os detalhes da transação do razão auxiliar. Consequentemente, você obterá muito mais detalhes sobre a transação de origem e poderá usá-la para análise. Por exemplo, você pode ver quem era o fornecedor ou o cliente , o que o cliente comprou ou o fornecedor vendeu e, ainda qual projeto estava na transação.

Os seguintes filtros de demonstrativos financeiros são enviados ao ASE, dessa forma, o ASE mostrará as transações que são agregadas:

Campos obrigatórios para filtragem:

- Pessoa jurídica em geral
- Calendário fiscal
- Ano
- ID da conta principal

Campos opcionais para filtragem:

- Trimestre
- Mês
- Período

Se você não expandir para baixo o suficiente de uma linha, a busca detalhada não funcionará. Por exemplo, se você apenas expandir para baixo a categoria de conta principal, você não poderá fazer busca detalhada no ASE no saldo, porque a conta principal é um campo obrigatório para filtragem no ASE.

Se você expandir muito para baixo em uma linha, os filtros adicionais nos demonstrativos financeiros não serão enviados para o ASE. Portanto, você pode ver uma diferença nos seus números. Por exemplo, se você o expandir para o país ou a região nas linhas de demonstrativo de rendimentos por demonstrativo financeiro da região, o país ou a região não devem ser incluídos como filtro no ASE.

> [!NOTE]
> Você pode fazer busca detalhada nas linhas ou colunas do demonstrativo financeiro que o ASE atualmente suporta para filtragem. Portanto, em algumas situações, a soma das transações detalhadas no ASE não corresponderá ao saldo no qual você está fazendo drillback. Esta funcionalidade continuará sendo aperfeiçoada no futuro.

## <a name="hierarchies"></a>Hierarquias

Os demonstrativos financeiros padrão usam duas hierarquias padrão para detalhar e expandir os dados. Uma hierarquia é para as linhas e outra é para as colunas. Ambas as hierarquias são predefinidas no design do demonstrativo financeiro. Para a maioria de demonstrativos financeiros, a hierarquia de linha é **Tipo de conta principal** \> **Categorias de conta principais** \> **Conta principal**. No entanto, alguns relatórios contêm campos adicionais, como País e Região. Os nós adicionais da hierarquia são baseado nos dados do razão auxiliar para cada transação.

Para as colunas, a hierarquia é centrada nas entidades legais e nos períodos fiscais. Para a maioria de demonstrativos financeiros, a hierarquia de coluna é **Entidade legal** \> **Calendário fiscal** \> **Ano fiscal** \> **Trimestre** \> **Período**.

Atualmente, os demonstrativos financeiros não oferecem suporte às hierarquias organizacionais, que permitem a você agregar dados.

## <a name="data-limitations"></a>Limitações de dados
Os elementos visuais do demonstrativo financeiro têm um limite em relação ao número de linhas que podem ser exibidas. Atualmente, o limite é definido como 30.000. Se você exceder o limite, o elemento visual terá um símbolo de advertência para notificá-lo sobre essa situação.

![Limitações de dados.](./media/data-limit.png)

Se o máximo for excedido, os totais que aparecem no demonstrativo financeiro estarão incorretos, pois nem todas as linhas foram carregadas para o elemento visual.

### <a name="empty-rows"></a>Linhas vazias
O Power BI não tem uma opção para ocultar e mostrar linhas vazias. Se uma linha não tiver dados, a linha não aparecerá no elemento visual.


## <a name="additional-resources-for-power-bi"></a>Recursos adicionais para Power BI

As informações nos seguintes recursos não são necessárias para habilitar relatórios incorporados para o espaço de trabalho **Análise financeira** em um ambiente de produção. Em vez disso, elas são úteis para caixas de desenvolvimento e se você quiser incorporar seus relatórios do Power BI.

- [Como acessar espaços de trabalho analíticos e relatórios em um ambiente de 1 caixa](/archive/blogs/dynamicsaxbi/accessing-analytical-workspaces-on-1box-environment)

- [​Adicionar análise a espaços de trabalho usando o Power BI Embedded](/dynamics365/unified-operations/dev-itpro/analytics/add-analytics-tab-workspaces)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]


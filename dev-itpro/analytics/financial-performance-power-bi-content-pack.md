---
title: "Conteúdo de O power BI de desempenho financeiro"
description: "Este tópico descreve Microsoft Dynamics 365 para o bloco de conteúdo do desempenho financeiro das operações do power BI Microsoft. Descreve o painel e relatórios que são incluídos no bloco de conteúdo, além fornece informações sobre o modelo de dados e as entidades usados para construir o bloco de conteúdo."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 106233
ms.assetid: 517e6a88-e7a1-4398-9971-b22fa83306ba
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 227285720e7f28beeb135eea081940578531d458
ms.lasthandoff: 03/31/2017


---

# <a name="financial-performance-power-bi-content"></a>Conteúdo de O power BI de desempenho financeiro

Este tópico descreve Microsoft Dynamics 365 para o bloco de conteúdo do desempenho financeiro das operações do power BI Microsoft. Descreve o painel e relatórios que são incluídos no bloco de conteúdo, além fornece informações sobre o modelo de dados e as entidades usados para construir o bloco de conteúdo.

<a name="accessing-the-content-pack"></a>Acessando o bloco de conteúdo
--------------------------

Duas versões do bloco de conteúdo do desempenho financeiro estão disponíveis. Uma versão está disponível serviços (LCS) do Microsoft Dynamics lifecycle, e outros está disponível em PowerBI.com.

-   ** Versão disponível em LCS: ** O bloco de conteúdo do desempenho financeiro disponível em LCS suporta Microsoft Dynamics 365 para a versão 1611 de operações. Você pode encontrar o bloco de conteúdo na biblioteca de ativo compartilhado em LCS. Para obter mais informações sobre como o download do bloco de conteúdo e o seu alocação Microsoft Dynamics 365 de dados, consulte operações [conteúdo de O power BI em LCS Microsoft e seus parceiros (power-bi-content-microsoft-partners.md]).
-   ** Versão que está disponível em PowerBI.com: ** O bloco de conteúdo do desempenho financeiro que está disponível em PowerBI.com suporta versões 7.0 e 7.0.1 Microsoft Dynamics AX. Para obter mais informações sobre como conectar e cobrar sua dynamics 365 de dados, consulte operações [conteúdo de O power BI de acesso de power-bi-home-page.md] (PowerBI.com).

## <a name="main-account-setup"></a>Configuração de conta principal
Como organizações desejam responsabilidades e valores de receita para exibir como os valores positivos em relatórios, o de instalação contas principais em dynamics 365 para operações é importante. Para que as listas principais aparece como os valores positivos, o tipo de conta principal deve ser definido ** responsabilidade ** ou ** ** receita. Quando esses tipos de conta são usados, relatórios através de O power BI Microsoft inverterá os sinais e mostra os valores como o valor positivo.

## <a name="dashboard-and-reports-that-are-included-in-the-content-pack"></a>O painel e relatórios que são incluídos no bloco de conteúdo
Após ter conectado o pacote de conteúdo aos dados do Dynamics 365 for Operations, o painel e os relatórios mostram os dados financeiros. Se nunca você usou o power BI antes, você pode saber mais sobre ela em [guiado aprendizado a página do power] de BI (https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). O painel contém blocos de dados resumidos baseados em relatórios subjacentes. Cada bloco contém informações resumidas sobre o ano atual em todas as empresas de uma organização. Eis alguns caixas:

-   Pagamento à vista
-   Receita total neste ano
-   Despesas totais neste ano
-   Rendimento líquido deste ano
-   Índice de liquidez
-   Despesas totais deste ano por categoria de conta
-   Índice atual
-   Dívida em Relação aos Ativos Totais
-   Receita real vs prevista
-   Receita faturada deste ano
-   Taxa de despesas operacionais deste ano
-   Margem de lucro deste ano
-   Despesas reais vs orçadas – Todas as empresas

Cada quadro é voltado para um relatório de suporte. Esses relatórios contêm gráficos e tabelas que fornecem mais informações. A tabela a seguir descreve os relatórios.

| Relatório                      | As informações contidas no relatório                                                                                                                                                                                                                                                                                                          |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Análise de pagamento à vista               | Dinheiro por entidade legal, dinheiro trimestre, dinheiro total, e dinheiro por conta ** observação: ** ** Dinheiro trimestre ** o relatório não inclui os saldos inicial no total para o primeiro trimestre. Mostra o total de novas transações lançadas em cada trimestre.                                                                                |
| Análise de índice atual      | Índice atual por entidade legal, índice atual por trimestre, e saldos dos ativos e passivos atuais                                                                                                                                                                                                                              |
| Análise de índice de liquidez        | Índice rápido por entidade legal, taxas rápido trimestre, e saldos para o caixa, contas a receber, e passivos atuais                                                                                                                                                                                                                      |
| Análise de custo dos produtos vendidos | COGS (custo dos produtos vendidos) por entidade legal, COGS deste ano e do ano passado por trimestre, COGS em relação às vendas por entidade legal, COGS total e porcentagem do COGS em relação às vendas                                                                                                                                                                                   |
| Análise de capital de trabalho    | Capital de trabalho por entidade legal, capital de trabalho por trimestre, ativos atuais, passivos atuais e capital de trabalho total                                                                                                                                                                                                                   |
| Análise de ativos e dívidas     | Retorno sobre ativos totais e dívida em relação aos ativos totais por entidade legal, dívida em relação aos ativos totais e retorno sobre ativos totais do último trimestre até esta data, ativos e passivos                                                                                                                                                                                     |
| Análise de margem de lucro      | Margem de lucro real e do orçamento por entidade legal, marcação de lucro por trimestre, porcentagem da margem de lucro e margem de lucro                                                                                                                                                                                                                       |
| Análise de rendimento líquido         | Rendimento líquido real e do orçamento por entidade legal, rendimento líquido deste ano e do ano passado, e porcentagem das despesas em relação ao rendimento líquido                                                                                                                                                                                                                       |
| Análise de lucros           | Lucros reais e do orçamento EBIT (antes dos juros e dos impostos) por entidade legal, EBIT deste ano e do ano passado, porcentagem das despesas em relação à receita, e despesas reais e do orçamento em relação à receita                                                                                                                                                          |
| Análise de receita            | Receita total, receita total real e do orçamento por entidade legal, receita total deste ano e do ano passado, variação do orçamento de receitas por entidade legal e receita total deste e do último período                                                                                                                                                 |
| Análise de despesas            | Total de despesas, total de despesas reais e de orçamento por entidade legal, total de despesas reais e de orçamento por trimestre, total de despesas reais por categoria de conta e taxa de despesas operacionais                                                                                                                                                                 |
| Análise de receita faturada     | Totais contas a receber, contas a receber totais por entidade legal, contas a receber no total, o trimestre e saldos de contas de contas a receber ** observação: ** Os relatórios não incluem saldos iniciais das contas contábeis de contas a receber. Mostra o total de novas transações que são lançadas em contas a receber. |

Os gráficos e os blocos em todos esses relatórios podem ser filtrados e fixados no painel. Para obter mais informações sobre como filtrar e fixar no Power BI, consulte [Criar e configurar um painel](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Noções básicas sobre o modelo de dados e as entidades
Os dados que preenchem o painel e relatórios no conteúdo do desempenho financeiro são empacotam o dynamics 365 para dados de operações. Estas entidades foram usadas como base de blocos de conteúdo: ** Entidades agregadas ** de dados

-   ** GeneralLedgerActivities ** – esta entidade agrega saldos contábil por categoria de conta.
-   ** BudgetActivities ** – esta entidade agrega saldos de orçamento por categoria de conta.

**Data entities**

-   FiscalCalendars
-   MainAccounts
-   LegalEntities
-   Razões
-   ChartofAccounts

Essas entidades foram usadas para criar medidas calculadas no modelo de dados. As medidas calculadas são usadas para calcular os principais indicadores chave de desempenho (KPIs) e relatórios usados no bloco de conteúdo. Por padrão, o pacote de conteúdo possui dados dos três últimos anos e do ano futuro. Para incluir cálculos adicionais nos relatórios e no painel, você pode modificar a [pasta de trabalho do Microsoft Excel](https://mbs.microsoft.com/customersource/global/AX/downloads/reports/msdaxfinpercontentpowerbi). Essa pasta de trabalho é o modelo de dados padrão usado para criar o pacote de conteúdo. Depois que você terminar a marcação das modificações, poderá criar um painel e pacote de conteúdo organizacional contendo as informações adicionadas.

## <a name="additional-resources"></a>Recursos adicionais
Estes são alguns links úteis relacionados às entidades e ao desenvolvimento de conteúdo do Power BI:

-   [Entidades de dados](..\data-entities\data-entities.md)
-   [Criando pacotes de conteúdo organizacionais](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelagem de dados por meio do Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Adicionando blocos do Power BI aos espaços de trabalho](configure-power-bi-integration.md)




---
title: "Conteúdo de desempenho financeiro para Power BI"
description: "Este tópico descreve o pacote de conteúdo Desempenho financeiro do Microsoft Dynamics 365 for Operations para Microsoft Power BI. Ele descreve o painel e os relatórios incluídos no pacote de conteúdo, além de fornecer informações sobre o modelo de dados e as entidades usadas para criar o pacote de conteúdo."
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

# <a name="financial-performance-power-bi-content"></a>Conteúdo de desempenho financeiro para Power BI

[!include[banner](../includes/banner.md)]


Este tópico descreve o pacote de conteúdo Desempenho financeiro do Microsoft Dynamics 365 for Operations para Microsoft Power BI. Ele descreve o painel e os relatórios incluídos no pacote de conteúdo, além de fornecer informações sobre o modelo de dados e as entidades usadas para criar o pacote de conteúdo.

<a name="accessing-the-content-pack"></a>Acessando o pacote de conteúdo
--------------------------

Duas versões do pacote de conteúdo do desempenho financeiro estão disponíveis. Uma versão está disponível no Microsoft Dynamics Lifecycle Services (LCS) e a outra no PowerBI.com.

-   **Versão que está disponível no LCS:** O pacote de conteúdo de Desempenho financeiro que está disponível no LCS suporta Microsoft Dynamics 365 for Operations, versão 1611. Você pode encontrar o pacote de conteúdo na biblioteca de ativo compartilhado no LCS. Para obter mais informações sobre como baixar o pacote de conteúdo e conectá-lo a seus dados do Microsoft Dynamics 365 for Operations, consulte [Conteúdo do Power BI no LCS da Microsoft e seus parceiros](power-bi-content-microsoft-partners.md).
-   **Versão que está disponível no PowerBI.com:** O pacote de conteúdo de Desempenho financeiro que está disponível no PowerBI.com suporta Microsoft Dynamics AX, versões 7.0 e 7.0.1. Para obter mais informações sobre como conectar e carregar os dados do Dynamics 365 for Operations, consulte [Acessar o conteúdo do Power BI em PowerBI.com](power-bi-home-page.md).

## <a name="main-account-setup"></a>Configuração da conta principal
Como as organizações querem que os valores de passivos e receitas apareçam como valores positivos nos relatórios, é importante a instalação de contas principais no Dynamics 365 for Operations. Para que as contas principais apareçam como os valores positivos, o tipo de conta principal deve ser definido como **Passivo** ou **Receita**. Quando esses tipos de conta são usados, os relatórios através do Microsoft Power BI reverterão os sinais e mostrarão os valores como positivos.

## <a name="dashboard-and-reports-that-are-included-in-the-content-pack"></a>Painéis e relatórios incluídos no pacote de conteúdo
Após ter conectado o pacote de conteúdo aos dados do Dynamics 365 for Operations, o painel e os relatórios mostram os dados financeiros. Se você nunca usou o Power BI antes, você poderá saber mais sobre ele na página [Aprendizado guiado para Power BI](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). O painel contém blocos de dados resumidos baseados em relatórios subjacentes. Cada bloco contém informações resumidas sobre o ano atual em todas as empresas de uma organização. Estes são alguns dos blocos:

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

Cada bloco é respaldado por um relatório de suporte. Esses relatórios contêm gráficos e tabelas que fornecem mais informações. A tabela a seguir descreve os relatórios.

| Relatório                      | As informações contidas no relatório                                                                                                                                                                                                                                                                                                          |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Análise de pagamento à vista               | Pagamento à vista por entidade legal, pagamento à vista por trimestre, pagamento à vista total e pagamento à vista por conta **Observação:** O relatório **Pagamento à vista por trimestre** não inclui os saldos inicial no total do primeiro trimestre. Ele mostra o total de novas transações lançadas em cada trimestre.                                                                                |
| Análise de índice atual      | Índice atual por entidade legal, índice atual por trimestre, e saldos dos ativos e passivos atuais                                                                                                                                                                                                                              |
| Análise de índice de liquidez        | Índice de liquidez por entidade legal, índice de liquidez por trimestre, e saldos de pagamento à vista, contas a receber e passivos atuais                                                                                                                                                                                                                      |
| Análise de custo dos produtos vendidos | COGS (custo dos produtos vendidos) por entidade legal, COGS deste ano e do ano passado por trimestre, COGS em relação às vendas por entidade legal, COGS total e porcentagem do COGS em relação às vendas                                                                                                                                                                                   |
| Análise de capital de trabalho    | Capital de trabalho por entidade legal, capital de trabalho por trimestre, ativos atuais, passivos atuais e capital de trabalho total                                                                                                                                                                                                                   |
| Análise de ativos e dívidas     | Retorno sobre ativos totais e dívida em relação aos ativos totais por entidade legal, dívida em relação aos ativos totais e retorno sobre ativos totais do último trimestre até esta data, ativos e passivos                                                                                                                                                                                     |
| Análise de margem de lucro      | Margem de lucro real e do orçamento por entidade legal, marcação de lucro por trimestre, porcentagem da margem de lucro e margem de lucro                                                                                                                                                                                                                       |
| Análise de rendimento líquido         | Rendimento líquido real e do orçamento por entidade legal, rendimento líquido deste ano e do ano passado, e porcentagem das despesas em relação ao rendimento líquido                                                                                                                                                                                                                       |
| Análise de lucros           | Lucros reais e do orçamento EBIT (antes dos juros e dos impostos) por entidade legal, EBIT deste ano e do ano passado, porcentagem das despesas em relação à receita, e despesas reais e do orçamento em relação à receita                                                                                                                                                          |
| Análise de receita            | Receita total, receita total real e do orçamento por entidade legal, receita total deste ano e do ano passado, variação do orçamento de receitas por entidade legal e receita total deste e do último período                                                                                                                                                 |
| Análise de despesas            | Total de despesas, total de despesas reais e de orçamento por entidade legal, total de despesas reais e de orçamento por trimestre, total de despesas reais por categoria de conta e taxa de despesas operacionais                                                                                                                                                                 |
| Análise de receita faturada     | Total de contas a receber, total de contas a receber por entidade legal, total de contas a receber por trimestre e saldos de contas a receber **Observação:** Os relatórios não incluem saldos iniciais das contas contábeis de contas a receber. Mostram o total de novas transações que são lançadas em Contas a receber. |

Os gráficos e os blocos em todos esses relatórios podem ser filtrados e fixados no painel. Para obter mais informações sobre como filtrar e fixar no Power BI, consulte [Criar e configurar um painel](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Noções básicas sobre o modelo de dados e as entidades
Os dados que preenchem o painel e os relatórios no pacote de conteúdo Desempenho financeiro são os dados do Dynamics 365 for Operations. As entidades a seguir foram usadas como base do pacote de conteúdo: **Entidades de dados agregadas**

-   **GeneralLedgerActivities** – esta entidade agrega saldos contábeis por categoria de conta.
-   **BudgetActivities** – esta entidade agrega saldos contábeis por categoria de conta.

**Entidades de dados**

-   FiscalCalendars
-   MainAccounts
-   LegalEntities
-   Razões
-   ChartofAccounts

Essas entidades foram usadas para criar medidas calculadas no modelo de dados. As medidas calculadas são então usadas para calcular os KPIs (indicadores chave de desempenho) e os relatórios usados no pacote de conteúdo. Por padrão, o pacote de conteúdo possui dados dos três últimos anos e do ano futuro. Para incluir cálculos adicionais nos relatórios e no painel, você pode modificar a [pasta de trabalho do Microsoft Excel](https://mbs.microsoft.com/customersource/global/AX/downloads/reports/msdaxfinpercontentpowerbi). Essa pasta de trabalho é o modelo de dados padrão usado para criar o pacote de conteúdo. Depois que você terminar a marcação das modificações, poderá criar um painel e pacote de conteúdo organizacional contendo as informações adicionadas.

## <a name="additional-resources"></a>Recursos adicionais
Estes são alguns links úteis relacionados às entidades e ao desenvolvimento de conteúdo do Power BI:

-   [Entidades de dados](..\data-entities\data-entities.md)
-   [Criando pacotes de conteúdo organizacionais](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelagem de dados por meio do Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Adicionando blocos do Power BI aos espaços de trabalho](configure-power-bi-integration.md)






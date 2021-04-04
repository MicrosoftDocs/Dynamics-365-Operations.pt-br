---
title: Solução de desempenho financeiro do PowerBI.com
description: Este tópico descreve a solução de desempenho financeiro do PowerBI.com.
author: kweekley
manager: AnnBe
ms.date: 05/09/2018
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
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 76f0c35ce9db89dd93292c4e39315a5833f38d54
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5568837"
---
# <a name="financial-performance-powerbicom-solution"></a>Solução de desempenho financeiro do PowerBI.com

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Esta solução do PowerBI.com foi preterida, como documentado em [Recursos removidos ou preteridos do Finance and Operations](../migration-upgrade/deprecated-features.md#power-bi-content-packs-available-on-appsource).

Este tópico descreve a solução de **Desempenho financeiro** do PowerBI.com. Ele descreve o painel e os relatórios incluídos, além de fornecer informações sobre o modelo de dados e as entidades usadas para criar a solução.

## <a name="main-account-setup"></a>Configuração da conta principal
Como as organizações querem que os valores de passivos e receitas apareçam como valores positivos nos relatórios, é importante a instalação de contas principais. Para que as contas principais apareçam como os valores positivos, o tipo de conta principal deve ser definido como **Passivo** ou **Receita**. Quando esses tipos de conta forem usados, os relatórios no Power BI reverterão os sinais e mostrarão os valores como positivos.

## <a name="dashboard-and-reports-that-are-included-in-the-powerbicom-solution"></a>Painéis e relatórios incluídos na solução PowerBI.com
O painel contém blocos de dados resumidos baseados em relatórios subjacentes. Cada bloco contém informações resumidas sobre o ano atual em todas as empresas de uma organização. Estes são alguns dos blocos:

- Pagamento à vista
- Receita total neste ano
- Despesas totais neste ano
- Rendimento líquido deste ano
- Índice de liquidez
- Despesas totais deste ano por categoria de conta
- Índice atual
- Dívida em Relação aos Ativos Totais
- Receita real vs prevista
- Receita faturada deste ano
- Taxa de despesas operacionais deste ano
- Margem de lucro deste ano
- Despesas reais vs orçadas – Todas as empresas

Cada bloco é respaldado por um relatório de suporte. Esses relatórios contêm gráficos e tabelas que fornecem mais informações. A tabela a seguir descreve os relatórios.

| Relatório                      | As informações contidas no relatório |
|-----------------------------|--------------------------------------|
| Análise de pagamento à vista               | Pagamento à vista por entidade legal, pagamento à vista por trimestre, pagamento à vista total e pagamento à vista por conta<blockquote>[!NOTE] As informações de pagamento à vista por trimestre não incluem saldos iniciais no total referente ao primeiro trimestre. Ele mostra o total de novas transações lançadas em cada trimestre.</blockquote> |
| Análise de índice atual      | Índice atual por entidade legal, índice atual por trimestre, e saldos dos ativos e passivos atuais |
| Análise de índice de liquidez        | Índice de liquidez por entidade legal, índice de liquidez por trimestre, e saldos de pagamento à vista, contas a receber e passivos atuais |
| Análise de custo dos produtos vendidos | COGS (custo dos produtos vendidos) por entidade legal, COGS deste ano e do ano passado por trimestre, COGS em relação às vendas por entidade legal, COGS total e porcentagem do COGS em relação às vendas |
| Análise de capital de trabalho    | Capital de trabalho por entidade legal, capital de trabalho por trimestre, ativos atuais, passivos atuais e capital de trabalho total |
| Análise de ativos e dívidas     | Retorno sobre ativos totais e dívida em relação aos ativos totais por entidade legal, dívida em relação aos ativos totais e retorno sobre ativos totais do último trimestre até esta data, ativos e passivos |
| Análise de margem de lucro      | Margem de lucro real e do orçamento por entidade legal, marcação de lucro por trimestre, porcentagem da margem de lucro e margem de lucro |
| Análise de rendimento líquido         | Rendimento líquido real e do orçamento por entidade legal, rendimento líquido deste ano e do ano passado, e porcentagem das despesas em relação ao rendimento líquido |
| Análise de lucros           | Lucros reais e do orçamento EBIT (antes dos juros e dos impostos) por entidade legal, EBIT deste ano e do ano passado, porcentagem das despesas em relação à receita, e despesas reais e do orçamento em relação à receita |
| Análise de receita            | Receita total, receita total real e do orçamento por entidade legal, receita total deste ano e do ano passado, variação do orçamento de receitas por entidade legal e receita total deste e do último período |
| Análise de despesas            | Total de despesas, total de despesas reais e de orçamento por entidade legal, total de despesas reais e de orçamento por trimestre, total de despesas reais por categoria de conta e taxa de despesas operacionais |
| Análise de receita faturada     | Total de contas a receber, total de contas a receber por entidade legal, total de contas a receber por trimestre e saldos de contas a receber<blockquote>[!NOTE] A informação não inclui os saldos iniciais das contas contábeis de contas a receber. Mostra o total de novas transações que são lançadas em Contas a receber.</blockquote> |

Os gráficos e os blocos em todos esses relatórios podem ser filtrados e fixados no painel. Para obter mais informações sobre como filtrar e fixar no Power BI, consulte [Criar e configurar um dashboard](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Noções básicas sobre o modelo de dados e as entidades
As entidades a seguir foram usadas como base da solução **Desempenho financeiro** do PowerBI.com:

**Entidades de dados agregados**

- **GeneralLedgerActivities** – esta entidade agrega saldos contábeis por categoria de conta.
- **BudgetActivities** – esta entidade agrega saldos contábeis por categoria de conta.

**Entidades de dados**

- FiscalCalendars
- MainAccounts
- LegalEntities
- Razões
- ChartofAccounts

Essas entidades foram usadas para criar medidas calculadas no modelo de dados. As medidas calculadas são então usadas para calcular os KPIs (indicadores chave de desempenho) e os relatórios usados no conteúdo. Por padrão, o conteúdo possui dados dos três últimos anos e do ano futuro. Para incluir cálculos adicionais no painel e nos relatórios, você pode modificar a [pasta de trabalho do Microsoft Excel](https://docs.microsoft.com/dynamics/s-e/). Essa pasta de trabalho é o modelo de dados padrão usado para criar o conteúdo.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
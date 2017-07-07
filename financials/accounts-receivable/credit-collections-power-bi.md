---
title: "Conteúdo do Power BI para gerenciamento de crédito e cobranças"
description: "Este tópico descreve o que está incluído no conteúdo do Power BI para gerenciamento de crédito e cobranças. Ele explica como acessar os relatórios do Power BI, além de fornecer informações sobre o modelo de dados e as entidades usados para criar o pacote de conteúdo."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations, UnifiedOperations. Core
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 298ac47e2253f8add1aa3938dda15afe186afbeb
ms.openlocfilehash: c066e1a190a5536ad67368b4e059ab6bc66718e6
ms.contentlocale: pt-br
ms.lasthandoff: 06/20/2017

---

# <a name="credit-and-collections-management-power-bi-content"></a>Conteúdo do Power BI para gerenciamento de crédito e cobranças

Este tópico descreve o que está incluído no conteúdo do Microsoft Power BI para **Gerenciamento de crédito e cobranças**. Ele explica como acessar os relatórios do Power BI, além de fornecer informações sobre o modelo de dados e as entidades usados para criar o pacote de conteúdo.

## <a name="overview"></a>Visão Geral

O conteúdo do Power BI para **Gerenciamento de crédito e cobranças** foi criado para gerentes de crédito e cobranças e auxiliares de cobrança. Ele fornece as métricas de cobrança e de crédito chave, como vendas diárias pendentes, saldo atrasado, exposição de crédito e clientes que estão acima de seus limites de crédito. Ele usa dados transacionais e fornece exibições agregadas de crédito e cobranças entre todas as empresas. Também fornece uma divisão pela empresa, grupo de clientes e o cliente.

Este conteúdo do Power BI consiste em 10 páginas do relatório:

- Duas páginas de visão geral (páginas para uma visão geral de crédito e páginas para uma visão geral das cobranças)
- Oito páginas de detalhes que fornecem detalhes de crédito e métricas de cobrança que são divididos entre várias dimensões

Todos os valores são mostrados na moeda do sistema. Você pode definir a moeda do sistema na página **Parâmetros dos sistemas**.

Por padrão, são mostrados o crédito e os dados de cobrança da empresa atual. Para ver os dados entre todas as empresas, atribua o direito **CustCollectionsBICrossCompany** à função.

## <a name="accessing-the-power-bi-content"></a>Acessando o conteúdo do Power BI
Se estiver usando o Microsoft Dynamics 365 for Finance and Operations, Enterprise edition com atualização de julho de 2017, o conteúdo do Power BI **Gerenciamento de crédito e cobranças** será mostrado no espaço de trabalho **Crédito e cobranças de clientes**.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Relatórios incluídos no conteúdo do Power BI

O conteúdo **CustCollectionsBICrossCompany** do Power BI tem um relatório que consiste em um conjunto de métricas. Estas métricas são visualizadas como gráficos, blocos e tabelas. A tabela a seguir fornece uma visão geral das visualizações do conteúdo **CustCollectionsBICrossCompany** do Power BI.

| Página de relatório                 | Visualização |
|-----------------------------|---------------|
| Visão geral das Cobranças        | <ul><li>Clientes em Atraso</li><li>Clientes acima do limite de crédito</li><li>30 dias (DSO)</li><li>Casos abertos</li><li>Média de dias para fechar o caso</li><li>Atividades abertas</li><li>Média de dias para fechar as atividades</li><li>Abrir notas de juros</li><li>Abrir cartas de cobrança</li><li>Retenção do cliente</li><li>Retenção de venda</li><li>Saldos antigos</li><li>Valores de status de cobranças</li><li>Valores de código de cobranças</li><li>Baixa por motivo</li><li>Saldo devido por região</li><li>Pagamentos esperados</li></ul> |
| Visão geral de crédito             | <ul><li>Clientes em Atraso</li><li>Limite de crédito vs saldo devido</li><li>Clientes acima da grade de limite de crédito</li><li>Clientes no limite de crédito por empresa</li><li>Crédito usado vs limite de crédito total</li><li>Limite de crédito versus crédito usado por região</li><li>Clientes por avaliação de crédito</li></ul> |
| Limite de crédito                | <ul><li>Limite de crédito</li><li>Detalhes de limite de crédito</li><li>Limite de crédito por cliente</li><li>Limite de crédito por grupo de clientes</li><li>Limite de crédito por avaliação de crédito por empresa</li><li>Limite de crédito versus crédito usado por região</li></ul> |
| Clientes acima do limite de crédito | <ul><li>Clientes acima do limite de crédito</li><li>Clientes acima do detalhe do limite de crédito</li><li>Clientes no limite de crédito por empresa</li><li>Cliente acima do limite de crédito por grupo de clientes</li><li>Clientes acima do limite de crédito por região</li></ul> |
| Clientes em Atraso          | <ul><li>Clientes em Atraso</li><li>Detalhes do cliente em atraso</li><li>Cliente em atraso por empresa</li><li>Cliente em atraso por grupo de clientes</li><li>Cliente em atraso por região</li></ul> |
| Saldos antigos               | <ul><li>Saldos antigos</li><li>Detalhes de saldos antigos</li><li>Saldos antigos por empresa</li><li>Saldos antigos por grupo de clientes</li></ul> |
| Pagamentos esperados           | <ul><li>Pagamentos esperados</li><li>Detalhes dos pagamentos esperados</li><li>Pagamentos esperados por empresa</li><li>Pagamentos esperados por grupo de clientes</li><li>Pagamentos esperados por região</li></ul> |
| Baixas                  | <ul><li>Baixas por região</li><li>Detalhes de baixas</li><li>Baixas por conta principal</li><li>Baixas por empresa</li><li>Baixas por grupo de clientes</li><li>Baixas por região</li></ul> |
| Status das cobranças          | <ul><li>Contestado</li><li>Promessa de pagamento quebrada</li><li>Promessa de pagamento</li><li>Detalhes do status de cobranças</li><li>Valores de status de cobranças</li><li>Casos abertos</li><li>Atividades abertas</li></ul> |
| Cartas de cobranças         | <ul><li>Valores de código de cobrança</li><li>Detalhes do valor do código de cobrança</li><li>Valor da cartas de cobrança por empresa</li><li>Valor da carta de cobrança por grupo de clientes</li><li>Valor da carta de cobrança por região</li></ul> |

Os gráficos e os blocos em todos esses relatórios podem ser filtrados e fixados no painel. Para obter mais informações sobre como filtrar e fixar no Power BI, consulte [Criar e configurar um painel](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards/). Você também pode usar a funcionalidade Exportar dados subjacentes para exportar os dados subjacentes resumidos em uma visualização.

## <a name="extending-the-power-bi-content"></a>Aumentando o conteúdo do Power BI
Usando os pacotes de conteúdo disponíveis no Microsoft Dynamics Lifecycle Services (LCS), você pode fornecer grande análise às pessoas que não acessam o Finance and Operations. Você pode modificar esses pacotes de conteúdo para que eles incluam outros relatórios ou imagens e, em seguida, publique os pacotes de conteúdo no locatário do Power BI.com para análise.

Você pode encontrar o conteúdo do Power BI **Gerenciamento de crédito e cobranças** na biblioteca de ativos compartilhados no LCS. Para obter mais informações sobre como baixar o pacote de conteúdo e implementá-lo na sua organização, consulte [Conteúdo do Power BI no LCS da Microsoft e seus parceiros](/dynamics365/unified-operations/dev-itpro/analytics/power-bi-content-microsoft-partners). Para ver uma demonstração que mostra como implementar o conteúdo do Power BI, veja o Office Mix [Conteúdo do Power BI da Microsoft e seus parceiros no Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w).

Certifique-se de baixar o conteúdo do Power BI **Gerenciamento de crédito e cobranças** que se aplica à versão do Finance and Operations que você está usando.

## <a name="understanding-the-data-model-and-entities"></a>Noções básicas sobre o modelo de dados e as entidades

Os seguintes dados são usados para preencher o relatório no conteúdo do Power BI **Gerenciamento de crédito e cobranças**. Esses dados são representadas como medições agregadas que foram preparadas no Repositório de entidades. O Repositório de entidades é um banco de dados do Microsoft SQL Server otimizado para análise. Para obter mais informações, consulte [Visão geral da integração do Power BI com a loja Entidade](/dynamics365/unified-operations/dev-itpro/analytics/power-bi-integration-entity-store).

| Entidade                                      | Principais medidas agregadas           | Fonte de dados                                 | Campo                                                      | descrição |
|---------------------------------------------|--------------------------------------|---------------------------------------------|------------------------------------------------------------|-------------|
| CustCollectionsBIActivitiesAverageCloseTime | NumOfActivities, AveragecClosedTime  | smmActivities                               | AverageOfChildren(AverageClosedTime) Count(ActivityNumber) | A contagem das atividades fechadas e de tempo médio para fechar as atividades. |
| CustCollectionsBIActivitiesOpen             | ActivityNumber                       | smmActivities                               | Count(ActivityNumber)                                      | A contagem de atividades abertas. |
| CustCollectionsBIAgedBalances               | AgedBalances                         | CustCollectionsBIAgedBalancesView           | Sum(SystemCurrencyBalance)                                 | A soma de saldos antigos. |
| CustCollectionsBIBalancesDue                | SystemCurrencyAmount                 | CustCollectionsBIBalanceDueView             | Sum(SystemCurrencyAmount)                                  | Os valores que estão vencidos. |
| CustCollectionsBICaseAverageCloseTIme       | NumOfCases, CaseAverageClosedTime    | CustCollectionsCaseDetail                   | AverageOfChildren(CaseAverageClosedTime) Count(NumOfCases) | A contagem de casos fechados e de tempo médio para fechar os casos. |
| CustCollectionsBICasesOpen                  | CaseId                               | CustCollectionsCaseDetail                   | Count(CaseId)                                              | A contagem de casos abertos. |
| CustCollectionsBICollectionLetter           | CollectionLetterNum                  | CustCollectionLetterJour                    | Count(CollectionLetterNum)                                 | A contagem de cartas de cobranças abertas. |
| CustCollectionsBICollectionLetterAmount     | CollectionLetterAmounts              | CustCollectionsBIAccountsReceivables        | Sum(SystemCurrencyAmount)                                  | O saldo de cartas de cobrança lançadas. |
| CustCollectionsBICollectionStatus           | CollectionStatusAmounts              | CustCollectionsBIAccountsReceivables        | Sum(SystemCurrencyAmount)                                  | O saldo das transações com status de cobrança. |
| CustCollectionsBICredit                     | CreditExposed, AmountOverCreditLimit | CustCollectionsBICreditView                 | Sum(CreditExposed), Sum(AmountOverCreditLimit)             | A soma de exposição de crédito e valores cujos clientes estão sobre seu limite de crédito. |
| CustCollectionsBICustOnHold                 | Bloqueado                              | CustCollectionsBICustTable                  | Count(Blocked)                                             | O número de clientes que estão em espera. |
| CustCollectionsBIDSO                        | DSO30                                | CustCollectionsBIDSOView                    | AverageOfChildren(DSO30)                                   | Vendas diárias pendentes para 30 dias. |
| CustCollectionsBIExpectedPayment            | ExpectedPayment                      | CustCollectionsBIExpectedPaymentView        | Sum(SystemCurrencyAmounts)                                 | A soma de pagamentos esperados no próximo ano. |
| CustCollectionsBIInterestNote               | InterestNote                         | CustInterestJour                            | Count(InterestNote)                                        | O número de notas de juros que foram criadas. |
| CustCollectionsBISalesOnHold                | SalesId                              | SalesTable                                  | Count(SalesId)                                             | O número total de ordens de venda que estão em espera. |
| CustCollectionsBIWriteOff                   | WriteOffAmount                       | CustCollectionsBIWriteOffView               | Sum(SystemCurrencyAmount)                                  | A soma das transações que foram baixadas. |


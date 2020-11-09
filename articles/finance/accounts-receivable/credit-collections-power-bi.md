---
title: Conteúdo de gerenciamento de crédito e cobranças do Power BI
description: Este tópico descreve o que está incluído no conteúdo de gerenciamento de crédito e cobranças do Power BI. Ele explica como acessar os relatórios do Power BI e fornece informações sobre o modelo de dados e entidades que são usados para criar o conteúdo.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustomerCollectionManagerWorkspace
audience: Application User, IT Pro
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 6d6880e258510a79cdd5937f96af28e5ae148292
ms.sourcegitcommit: 1329b3b98854422c4c3773ede44a5cefa7d07085
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2020
ms.locfileid: "4040044"
---
# <a name="credit-and-collections-management-power-bi-content"></a>Conteúdo de gerenciamento de crédito e cobranças do Power BI

[!include [banner](../includes/banner.md)]

Este tópico descreve o que está incluído no conteúdo de **Gerenciamento de crédito e cobranças** do Microsoft Power BI. Ele explica como acessar os relatórios do Power BI e fornece informações sobre o modelo de dados e entidades que foram usados para criar o conteúdo.

## <a name="overview"></a>Visão Geral

O conteúdo de **Gerenciamento de crédito e cobranças** do Power BI foi criado para gerentes de crédito e cobranças e auxiliares de cobrança. Ele fornece as métricas de cobrança e de crédito chave, como vendas diárias pendentes, saldo atrasado, exposição de crédito e clientes que estão acima de seus limites de crédito. Ele usa dados transacionais e fornece exibições agregadas de crédito e cobranças entre todas as empresas. Também fornece uma divisão pela empresa, grupo de clientes e o cliente.

Este conteúdo do Power BI consiste em 10 páginas de relatório:

- Duas páginas de visão geral (páginas para uma visão geral de crédito e páginas para uma visão geral das cobranças)
- Oito páginas de detalhes que fornecem detalhes de crédito e métricas de cobrança que são divididos entre várias dimensões

Todos os valores são mostrados na moeda do sistema. Você pode definir a moeda do sistema na página **Parâmetros dos sistemas**.

Por padrão, são mostrados o crédito e os dados de cobrança da empresa atual. Para ver os dados entre todas as empresas, atribua o direito **CustCollectionsBICrossCompany** à função.

## <a name="setup-needed-to-view-power-bi-content"></a>Configuração necessária para exibir o conteúdo do Power BI

A configuração a seguir precisa ser concluída para que os dados sejam exibidos em recursos visuais **Crédito e cobranças de clientes** do Power BI.

1. Vá para **Administração do sistema > Configuração > Parâmetros do Sistema** para definir **Moeda do sistema** e **Taxa de Câmbio do Sistema**.
2. Vá para **Contabilidade > Calendários > Calendários fiscais** para validar as datas do calendário fiscal atribuídas ao período de tempo ativo.
3. Vá para **Contabilidade > Configuração > Razão** e defina **Moeda Contábil** e **Tipo de Taxa de Câmbio**.
4. Defina taxas de câmbio entre moedas de transação e moeda contábil, moeda contábil e moeda do sistema. Para fazer isso, vá para **Contabilidade > Moedas > Taxas de câmbio de moedas**.
5. Vá para **Administração do sistema > Configuração > Repositório de Entidades** para atualizar a medida de agregação **CustCollectionsBIMeasurementsV2**.

>[!NOTE] 
> As definições de período de classificação por vencimento devem ser configuradas em **Parâmetros de Contas a pagar > Coletas > Padrões de coletas** para habilitar dados de classificação por vencimento no conteúdo do Power BI.

## <a name="accessing-the-power-bi-content"></a>Acessando o conteúdo do Power BI

O conteúdo de **Gerenciamento de crédito e cobranças** do Power BI é exibido no espaço de trabalho **Crédito e cobranças de clientes**.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Relatórios incluídos no conteúdo do Power BI

O conteúdo de **CustCollectionsBICrossCompany** do Power BI tem um relatório que consiste em um conjunto de métricas. Estas métricas são visualizadas como gráficos, blocos e tabelas. A próxima tabela oferece uma visão geral das visualizações no conteúdo de **CustCollectionsBICrossCompany** do Power BI.

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

Os gráficos e os blocos em todos esses relatórios podem ser filtrados e fixados no painel. Para obter mais informações sobre como filtrar e fixar no Power BI, consulte [Criar e configurar um dashboard](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards/). Você também pode usar a funcionalidade Exportar dados subjacentes para exportar os dados subjacentes resumidos em uma visualização.

---
title: Espaço de trabalho de pagamentos dos fornecedores
description: Este tópico fornece informações sobre a área de trabalho móvel de pagamentos de fornecedor. A área de trabalho de pagamentos de fornecedor mostra informações relacionadas ao processamento de pagamentos de fornecedores.
author: abruer
manager: AnnBe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPaymentWorkspace
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 86091e16712092086a641d79e49afbc5b205e934
ms.sourcegitcommit: 14b554b43b9d86152ef27fdde6141589bcaf1161
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/16/2020
ms.locfileid: "3598100"
---
# <a name="vendor-payments-workspace"></a>Espaço de trabalho de pagamentos dos fornecedores

[!include [banner](../includes/banner.md)]

A área de trabalho **Pagamentos de fornecedor** mostra informações relacionadas ao processamento de pagamentos de fornecedores. Esta área de trabalho inclui uma visualização **Meu trabalho** e uma página **Análise**. A visualização **Meu trabalho** mostra quadros resumidos, grades de transação de fornecedor, e informações relacionadas do fornecedor. A página **Análise** usa recursos do Microsoft Power BI para mostrar os visuais relacionados a pagamentos de fornecedor.

## <a name="setup-needed-to-view-power-bi-content"></a>Configuração necessária para exibir o conteúdo do Power BI

A configuração a seguir precisa ser concluída para que os dados sejam exibidos em **Pagamentos do fornecedor** em recursos visuais do Power BI.
1. Vá para **Administração do sistema > Configuração > Parâmetros do Sistema** para definir **Moeda do sistema** e **Taxa de Câmbio do Sistema**.
2. Vá para **Contabilidade > Calendários > Calendários fiscais** para validar as datas do calendário fiscal atribuídas ao período de tempo ativo.
3. Vá para **Contabilidade > Configuração > Razão** para definir **Moeda Contábil** e **Tipo de Taxa de Câmbio**. 
4. Defina as taxas de câmbio entre as moedas de transação e a moeda contábil, e entre a moeda contábil e a moeda do sistema. Para fazer isso, vá para **Contabilidade > Moedas > Taxas de câmbio de moedas**.
5. Vá para **Administração do sistema > Configuração > Repositório de Entidades** para atualizar a medida de agregação **VendPaymentBIMeasureV2**.

## <a name="my-work-view"></a>Visualização Meu trabalho

### <a name="summary-tiles"></a>Blocos do resumo

Os quadros na seção **Resumo** fornecem uma visão geral do estado das informações de pagamento. Você pode ver os diários de pagamento que ainda não foram postados, faturas vencidas, todos os vendedores e fornecedores que estão em espera. Na seção **Resumo**, você pode criar uma nova definição de pagamento.

As informações na seção **Resumo** destinam-se à empresa à qual você está conectado.

### <a name="vendor-transactions-grids"></a>Grades de transações de fornecedor

A seção **Transações de fornecedor** contém grades que mostram as faturas passadas e os pagamentos que não são liquidados. Na grade **Fatura atrasada**, você pode visualizar o histórico de liquidação de uma fatura selecionada. Na grade **Pagamentos não liquidados**, você pode visualizar o histórico de liquidação de uma fatura selecionada e liquidar a fatura.

Funcionários de pagamento centralizados podem usar um filtro que aparece no topo de cada grade para selecionar uma empresa. A grade é filtrada de modo que mostre apenas as empresas que são definidas na hierarquia organizacional de pagamento centralizada que o funcionário de pagamento centralizado tem direitos de exibição.

A guia **Localizar transações** na seção **Transações de fornecedor** permite que você procure por uma transação de fornecedor.

### <a name="related-information"></a>Informações Relacionadas

Você pode exibir o relatório **Classificação por vencimento de fornecedores** e o relatório **Resumo de pagamento por data** com links na seção **Informações relacionadas** da área de trabalho.

## <a name="analytics-page"></a>Página de análise

A página **Análise** fornece métricas importantes, como faturas de fornecedor atrasadas e faturas de fornecedor que vencem no futuro. Esta página contém nove páginas de relatório. Uma página fornece uma visão geral, e as outras oito páginas fornecem detalhes sobre métricas de pagamento de contas a pagar.

A tabela a seguir mostra as visualizações disponíveis em cada página de relatório.


|            Página de relatório            |                                                                                                                                                                                Visualização                                                                                                                                                                                |
|-----------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     Visão geral de pagamentos do fornecedor      | <ul><li>Faturas em atraso</li><li>Faturas vencidas hoje</li><li>Descontos tomados para descontos perdidos</li><li>Faturas a vencer no futuro na data de desconto à vista</li><li>Faturas a vencer no futuro na data de vencimento</li><li>Faturas pagas em atraso para as faturas pagas a tempo</li><li>Atribuição de fluxo de trabalho de pagamento</li><li>Fornecedor para o saldo de cliente</li><li>Faturas em aberto com limite de pagamento</li></ul> |
|         Faturas em atraso         |                                                                                             <ul><li>Faturas em atraso</li><li>Detalhes das faturas vencidas</li><li>Total de faturas em aberto</li><li>Faturas devidas por grupo de fornecedores</li><li>Faturas vencidas por empresa</li></ul>                                                                                              |
|        Faturas em atraso hoje         |                                                                                                         <ul><li>Faturas em atraso hoje</li><li>Detalhes das faturas vencidas hoje</li><li>Faturas atualizadas hoje por empresa</li><li>Faturas atualizadas hoje por grupo de fornecedores</li></ul>                                                                                                          |
| Descontos tomados para descontos perdidos |                                                                             <ul><li>Descontos obtidos para o desconto perdido</li><li>Descontos feitos para detalhes do desconto perdido</li><li>Descontos feitos para desconto perdido por empresa</li><li>Descontos feitos para o desconto perdido por grupo de fornecedores</li></ul>                                                                              |
|      Faturas vencidas no futuro       |                                                 <ul><li>Faturas vencidas no futuro</li><li>Detalhes das faturas vencidas no futuro</li><li>Faturas a vencer no futuro por empresa</li><li>Faturas a vencer no futuro por grupo de fornecedores</li><li>Faturas a vencer no futuro na data de desconto à vista</li><li>Faturas a vencer no futuro na data de vencimento</li></ul>                                                  |
|        Faturas pagas em atraso         |                                                         <ul><li>Faturas pagas após o vencimento</li><li>Faturas pagas após detalhes da data de vencimento</li><li>Faturas pagas após a data de vencimento por empresa</li><li>Faturas pagas após a data de vencimento por grupo de fornecedores</li><li>As faturas pagas em atraso versus faturas pagas a tempo</li></ul>                                                          |
|         Fluxo de trabalho de pagamento          |                                                                                <ul><li>Instâncias de fluxo de trabalho de pagamento do fornecedor</li><li>Instâncias de fluxo de trabalho de pagamento de fornecedores por aprovador</li><li>Instâncias de fluxo de trabalho de pagamento do fornecedor por empresa</li><li>Média de dias no fluxo de trabalho por aprovador</li></ul>                                                                                |
|    Fornecedor para o saldo de cliente     |                                                                                                                   <ul><li>Fornecedor para o saldo de cliente</li><li>Vendedor para o saldo de cliente por empresa</li><li>Detalhes do saldo do fornecedor para o cliente</li></ul>                                                                                                                    |
|    Faturas com retenção de pagamento     |                                                                                         <ul><li>Faturas com retenção de pagamento</li><li>Faturas com detalhes de retenção de pagamento</li><li>Faturas com retenção de pagamento por empresa</li><li>Faturas com retenção de pagamento por grupo de fornecedores</li></ul>                                                                                          |


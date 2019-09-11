---
title: Lançamento de vendas e pagamentos online
description: Este procedimento orienta como configurar e executar um trabalho em lotes periódico para criar ordens de venda e pagamentos para transações de lojas online.
author: psimolin
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1d42b585a61214628980cd45a859215443ed55b5
ms.sourcegitcommit: c461758290d7ddc19f0b60701368937c35ef78b0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2019
ms.locfileid: "1864144"
---
# <a name="posting-of-online-sales-and-payments"></a>Lançamento de vendas e pagamentos online

[!include[task guide banner](../includes/task-guide-banner.md)]

Este procedimento orienta como configurar e executar um trabalho em lotes periódico para criar ordens de venda e pagamentos para transações de lojas online.

Lançar pagamentos e vendas on-line é um processo de dois estágios.

- Recebendo os dados de transação online de varejo na matriz.
- Sincronizando ordens criar ordens de venda na matriz.

Receber os dados de transação online de varejo pode ser feito manualmente executando o trabalho P ou criando um trabalho em lotes recorrente.

### <a name="manually-running-the-p-job"></a>Executando o trabalho P manualmente

1. Vá para Todos os espaços de trabalho > TI de Varejo.
2. Clique em Agenda de distribuição.
3. Selecione P-0001.
4. Ajuste os grupos do banco de dados do canal, se necessário.
5. Clique em Executar agora.
6. Clique em Sim.

### <a name="scheduling-a-recurring-p-job"></a>Agendando um trabalho P recorrente

1. Vá para Todos os espaços de trabalho > TI de Varejo.
2. Clique em Agenda de distribuição.
3. Selecione P-0001.
4. Clique em Criar trabalho em lotes.
5. Clique em Executar em segundo plano.
5. Habilitar Processamento em lotes.
6. Clique em Recorrência.
7. Selecione a opção Nenhuma data de término.
8. No campo Contagem, insira o intervalo entre as execuções em minutos. Normalmente isso seria 5-10.
9. Clique em OK.
10. Clique em OK.

As ordens podem ser sincronizadas manualmente, executando o trabalho "Sincronizar ordens" ou criando um trabalho em lotes recorrente.

### <a name="manually-running-order-synchronization"></a>Executando a sincronização da ordem manualmente 

Siga estas etapas para executar manualmente o trabalho "Sincronizar ordens" uma vez.

1. Vá para Todos os espaços de trabalho > Finanças da loja de varejo.
2. Clique em Sincronizar ordens.
3. No campo Hierarquia da organização, selecione 'Lojas de varejo por região'.
    * Selecione uma loja online específica ou selecione um nó se você deseja criar o trabalho em lotes para um grupo de lojas.  
    * Clique na seta para adicionar sua seleção.  
4. Clique na guia Executar em segundo plano.
5. Desativar processamento em lotes
6. Clique em Recorrência.
7. Selecione a opção Terminar Após
8. No campo Terminar Após, insira 1.
9. Clique em OK.
10. Clique em OK.

### <a name="scheduling-recurring-order-synchronization"></a>Agendando sincronização da ordem recorrente

Este procedimento orienta como configurar e executar um trabalho em lotes periódico para criar ordens de venda e pagamentos para transações de lojas online. Este procedimento usa a empresa USRT nos dados de demonstração.

1. Vá para Todos os espaços de trabalho > Finanças da loja de varejo.
2. Clique em Sincronizar ordens.
3. No campo Hierarquia da organização, selecione 'Lojas de varejo por região'.
    * Selecione uma loja online específica ou selecione um nó se você deseja criar o trabalho em lotes para um grupo de lojas.  
    * Clique na seta para adicionar sua seleção.  
4. Clique na guia Executar em segundo plano.
5. Habilitar processamento em lotes
6. Clique em Recorrência.
7. Selecione a opção Nenhuma data de término.
8. No campo Contagem, insira o intervalo entre as execuções em minutos. Normalmente isso seria 2-20
9. Clique em OK.
10. Clique em OK.

## <a name="data-entities-involved-in-the-process"></a>Entidades de dados envolvidas no processo

- RetailTransactionTable
- RetailTransactionAddressTrans
- RetailTransactionInfocodeTrans
- RetailTransactionTaxTrans
- RetailTransactionSalesTrans
- RetailTransactionTaxMeasure
- RetailTransactionDiscountTrans
- RetailTransactionTaxTransGTE
- RetailTransactionMarkupTrans
- RetailTransactionPaymentTrans
- RetailTransactionAttributeTrans

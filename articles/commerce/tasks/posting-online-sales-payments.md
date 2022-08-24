---
title: Lançamento de vendas e pagamentos online
description: Este procedimento orienta como configurar e executar um trabalho em lotes periódico para criar ordens de venda e pagamentos para transações de lojas online.
author: jashanno
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.industry: Retail
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
ms.openlocfilehash: 0db3414a41a27b5c383eddd4c3e7650fb828b422
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285677"
---
# <a name="posting-of-online-sales-and-payments"></a>Lançamento de vendas e pagamentos online

[!include [banner](../includes/banner.md)]

Este procedimento orienta como configurar e executar um trabalho em lotes periódico para criar ordens de venda e pagamentos para transações de lojas online.

Lançar pagamentos e vendas on-line é um processo de dois estágios.

- Recebendo os dados de transação online de comércio na matriz.
- Sincronizando ordens criar ordens de venda na matriz.

Receber os dados de transação online pode ser feito manualmente executando o trabalho P ou criando um trabalho em lotes recorrente.

### <a name="manually-running-the-p-job"></a>Executando o trabalho P manualmente

1. Acesse Todos os espaços de trabalho > TI de Varejo e Comércio.
2. Clique em Agenda de distribuição.
3. Selecione P-0001.
4. Ajuste os grupos do banco de dados do canal, se necessário.
5. Clique em Executar agora.
6. Clique em Sim.

### <a name="scheduling-a-recurring-p-job"></a>Agendando um trabalho P recorrente

1. Acesse Todos os espaços de trabalho > TI de Varejo e Comércio.
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

1. Acesse Todos os espaços de trabalho > Finanças da loja.
2. Clique em Sincronizar ordens.
3. No campo Hierarquia da organização, selecione 'Lojas por região'.
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

1. Acesse Todos os espaços de trabalho > Finanças da loja.
2. Clique em Sincronizar ordens.
3. No campo Hierarquia da organização, selecione 'Lojas por região'.
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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

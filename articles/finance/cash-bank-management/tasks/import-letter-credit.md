---
title: Importar carta de crédito
description: Este procedimento apresenta o processo de importação de uma carta de crédito.
author: kweekley
manager: AnnBe
ms.date: 02/28/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, VendBankAccounts, PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, BankLCImport,  PurchEditLines, VendEditInvoice, SrsReportViewerForm, LedgerJournalTable, LedgerJournalTransVendPaym, VendOpenTrans, SysQueryForm, BankAccountTableLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9f9c73ec1347e72f8cd4ae8eec580bb8fe3df8ed
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440419"
---
# <a name="import-letter-of-credit"></a>Importar carta de crédito

[!include [banner](../../includes/banner.md)]

Este procedimento apresenta o processo de importação de uma carta de crédito. As seguintes tarefas devem ser configuradas antes da conclusão deste procedimento: recursos bancários, perfis de lançamento, contrato de recurso bancário e detalhes bancários do fornecedor.

Este procedimento usa a empresa de dados de demonstração USMF.


## <a name="create-a-purchase-order-with-letter-of-credit"></a>Crie uma Ordem de compra com Carta de crédito
1. Vá para Contas a pagar > Ordens de compra > Todas as ordens de compra.
2. Clique em Novo.
3. No campo Conta de fornecedor, insira ou selecione um valor.
4. Na lista, localize e selecione o registro desejado.
5. Na lista, clique no link na linha selecionada.
6. Expanda a seção Geral.
7. No campo Local, insira ou selecione um valor.
8. Na lista, clique no link na linha selecionada.
9. No campo Depósito, insira ou selecione um valor.
10. Na lista, clique no link na linha selecionada.
11. No campo Data contábil, insira uma data.
12. No campo Data de entrega, insira uma data.
    * Observação: O campo 'Tipo de documento bancário' deve ser selecionado com o valor 'Carta de crédito'.  
13. Clique em OK.
14. No campo Número do item, insira ou selecione um valor.
15. Na lista, localize e selecione o PDV desejado.
16. Na lista, clique no link na linha selecionada.
17. Expanda a seção Detalhes da linha.
18. Clique na guia Entrega.
19. No campo Data de entrega, insira uma data.
20. No campo Data de entrega confirmada, insira uma data.
21. No campo Preço unitário, insira um número.
    * Define os detalhes da Carta de crédito.  
22. No Painel de Ação, clique em Gerenciar.
23. Clique em Carta de crédito/coleção de importação.
24. No campo Data da solicitação de emprego, insira uma data e hora.
    * Verifique se o campo “Conta bancária” tem a conta bancária ativa padrão, que é baseada na data de solicitação de emprego.  
25. No campo Número do documento bancário, digite um valor.
26. No campo Data de recebimento, insira uma data e hora.
27. Expanda a seção Documento bancário.
28. No campo Data de vencimento, insira uma data e hora.
29. Expanda a seção Detalhes bancários.
30. No campo Banco avisador, insira ou selecione um valor.
31. Na lista, clique no link na linha selecionada.
32. Clique em Salvar.
33. Clique em Buscar remessas de ordem de compra.
34. Feche a página.
35. No Painel de Ação, clique em Compra.
36. Clique em Confirmar.
37. No Painel de Ação, clique em Gerenciar.
38. Clique em Carta de crédito/coleção de importação.
39. Clique em Processo.
40. Clique em Confirmar.
    * Verifique se o saldo do recurso reduz o valor da ordem de compra.  Neste exemplo, valor de compra = 500,00, Limite de recurso = 10.000,00, consequentemente, Saldo de recursos = 9.500,00.  
41. Feche a página.
42. No campo Preço unitário, insira um número.
43. Clique em Salvar.
44. No Painel de Ação, clique em Compra.
45. Clique em Confirmar.
    * Modifique a carta de crédito em decorrência de alteração no Preço unitário.  
46. No Painel de Ação, clique em Gerenciar.
47. Clique em Carta de crédito/coleção de importação.
    * Modifique a carta de crédito em decorrência de alteração no Preço unitário para compra.  
48. Clique em Processo.
49. Clique em Corrigir.
50. Clique em Remover.
51. Clique em Sim.
52. Clique em Buscar remessas de ordem de compra.
53. Clique em Processo.
54. Clique em Confirmar.
    * Verifique se o saldo do recurso reduz o valor da ordem de compra.  Neste exemplo, Valor de compra editado = 600,00, Limite de recurso = 10.000,00, consequentemente, Saldo de recursos = 9.400,00.  
55. Feche a página.

## <a name="post-packing-slip"></a>Lance a guia de remessa
1. No Painel de Ação, clique em Receber.
2. Clique em Recebimento de produtos.
3. No campo PurchParmTable_Num, digite um valor.
    * Selecione o número de remessa criado com referência à Carta de crédito.  
4. Na lista, clique no link na linha selecionada.
5. No campo Data de recebimento de produtos, insira uma data.
6. Clique em OK.
7. Feche a página.
8. Feche a página.

## <a name="verify-import-letter-of-credit-status"></a>Verifique o status Importar carta de crédito
1. Vá para Gerenciamento de caixa e bancos > Cartas de crédito > Importar carta de crédito e importar coleção.
2. Na lista, localize e selecione o PDV desejado.
3. Na lista, clique no link na linha selecionada.
    * O status de Importar Carta de crédito.     
4. Feche a página.
5. Feche a página.

## <a name="post-purchase-invoice"></a>Lance a fatura de compra
1. Vá para Contas a pagar > Ordens de compra > Todas as ordens de compra.
    * Selecione a ordem de compra que foi criada com a carta de crédito.  
2. Na lista, localize e selecione o PDV desejado.
3. Na lista, clique no link na linha selecionada.
4. No Painel de Ação, clique em Fatura.
5. Clique em Fatura.
6. No campo Número, digite um valor.
7. No campo Número da remessa, insira ou selecione um valor.
8. Na lista, clique no link na linha selecionada.
9. No campo Data da fatura, insira uma data.
10. Clique em Atualizar status de conciliação.
11. Clique em Lançar.
12. Feche a página.
13. Feche a página.

## <a name="verify-import-letter-of-credit-status"></a>Verifique o status Importar carta de crédito
1. Vá para Gerenciamento de caixa e bancos > Cartas de crédito > Importar carta de crédito e importar coleção.
2. Na lista, localize e selecione o PDV desejado.
3. Na lista, clique no link na linha selecionada.
    * Verifique Importar Carta de crédito 2.  
    * Validar: Status da remessa = Detalhes do recurso bancário faturado  
4. Clique em Exibir.
5. Clique em Imprimir solicitação de emprego.
6. Clique em OK.
    * Verifique se a Carta da solicitação de crédito é impressa.  
7. Feche a página.
8. Feche a página.
9. Feche a página.

## <a name="post-vendor-payment-journal-for-the-created-purchase-invoice-with-letter-of-credit"></a>Lance o diário de pagamentos do fornecedor para a fatura de compra criada com a carta de crédito
1. Vá para Contas a pagar > Pagamentos > Diário de pagamentos.
2. Clique em Novo.
3. No campo Nome, insira ou selecione um valor.
4. Na lista, clique no link na linha selecionada.
5. Clique em Linhas.
6. No campo Data, insira uma data.
7. No campo Conta, especifique os valores desejados.
8. Clique em Liquidar transações.
9. Expanda a seção Totais.
10. No campo Mostrar, selecione uma opção.
    * Verifique se os campos Número do documento bancário e Número de remessa foram atualizados.  
11. Marque a caixa de seleção Marcar.
12. Clique em OK.
13. Clique na aba Pagamento.
    * Verifique se os campos Número do documento bancário e Número de remessa foram atualizados.  
14. Clique em Lançar.
15. Feche a página.
16. Feche a página.

## <a name="verify-import-letter-of-credit-status-after-invoice-paid"></a>Verifique o status de Importação da carta de crédito após a fatura ser paga
1. Vá para Gerenciamento de caixa e bancos > Cartas de crédito > Importar carta de crédito e importar coleção.
2. Na lista, localize e selecione o PDV desejado.
3. Na lista, clique no link na linha selecionada.
    * O status de Importar Carta de crédito.   
4. Feche a página.

## <a name="verify-the-bank-facility-limit-and-utilization-report"></a>Verifique o limite de recurso do banco e o relatório de utilização
1. Vá para Gerenciamento de caixa e bancos > Consultas e relatórios > Cartas de crédito ou garantia > Relatório de utilização e facilidades bancárias.
2. Expanda os Registros para incluir a seção.
3. Clique em Filtro.
    * Defina o campo Critérios com a conta bancária necessária.  
4. No campo Critérios, insira ou selecione um valor.
5. Na lista, clique no link na linha selecionada.
6. Clique em OK.
7. Clique em OK.
    * Verifique o relatório que lista as transações.  
    * Verifique se o relatório lista as transações com número do documento bancário, limite de recurso, valor utilizado e valor de saldo de recurso.  
8. Feche a página.


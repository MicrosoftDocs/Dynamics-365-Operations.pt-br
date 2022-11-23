---
title: Exportar carta de crédito
description: Este procedimento apresenta o processo de exportação de uma carta de crédito.
author: kweekley
ms.date: 11/15/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, DefaultDashboard, SalesTableListPage, SalesCreateOrder, SalesTable, BankLCExport, SalesEditLines,  LedgerJournalTable, LedgerJournalTransCustPaym, CustOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cf06a73bf7665059658c7884a0b9f973929d647c
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779545"
---
# <a name="export-letter-of-credit"></a>Exportar carta de crédito

[!include [banner](../../includes/banner.md)]

Este procedimento apresenta o processo de exportação de uma carta de crédito.

Uma carta de crédito é um contrato emitido por um banco, no qual o banco garante o pagamento em nome do comprador, se as condições do contrato entre o comprador e o vendedor forem atendidas.



Execute o procedimento **Configurar recursos bancários e perfis de lançamento** e o procedimento **Criar um contrato de recursos bancários para carta de crédito** antes deste procedimento. A empresa de demonstração de USMF deve ser selecionada para executar com êxito este procedimento.


## <a name="create-sales-order-for-export-letter-of-credit"></a>Criar Ordem de venda para exportação de carta de crédito
1. Acesse **Contas a receber > Ordens > Todas as ordens de venda**.
2. Clique em **Novo**.
3. No campo **Conta do cliente**, clique no botão suspenso para abrir a pesquisa.
4. Na lista, localize e selecione o registro desejado.
5. Na lista, clique no link na linha selecionada.
6. Expanda ou recolha a seção **Geral**.
7. No campo **Site**, clique no botão de menu suspenso para abrir a pesquisa.
    * Selecione o **Local** no qual o item a ser emitido está estocado.  
8. Na lista, clique no link na linha selecionada.
9. No campo **Depósito**, clique no botão suspenso para abrir a pesquisa.
    * Selecione o **Depósito** no qual o item a ser emitido está estocado.  
10. Na lista, clique no link na linha selecionada.
    * Observação: o campo **Tipo de documento bancário** deve ser selecionado com o valor **Carta de crédito**.  
11. No campo **Tipo de documento bancário**, selecione **Carta de crédito**.
12. Expanda ou recolha a seção **Entrega**.
    * Selecione **Controle da data de entrega** = **Nenhum**.  
13. No campo **Data de recebimento solicitada**, insira uma data.
14. Clique em **OK**.
15. No campo **Número do item**, clique no botão suspenso para abrir a pesquisa.
    * Selecione o item obrigatório a ser emitido/vendido.  
16. Na lista, localize e selecione o PDV desejado.
17. Na lista, clique no link na linha selecionada.
18. No campo **Preço unitário**, insira um número.
19. Expanda ou recolha a seção **Detalhes da linha**.
20. Clique na guia **Entrega**.
21. No campo **Data de remessa solicitada**, insira uma data.
22. No campo **Data de remessa confirmada**, insira uma data.
23. No Painel de Ação, clique em **Gerenciar**.
24. Clique em **Carta de crédito**.
25. No campo **Número do documento bancário**, digite um valor.
26. No campo **Data de vencimento**, insira uma data e hora.
27. Expandir ou recolher a seção **Detalhes bancários**.
28. No campo **Banco emissor**, clique no botão suspenso para abrir a pesquisa.
29. Na lista, clique no link na linha selecionada.
30. No campo **Banco avisador**, clique no botão suspenso para abrir a pesquisa.
31. Na lista, localize e selecione o registro desejado.
32. Na lista, clique no link na linha selecionada.
33. Clique em **Buscar remessas de ordem de venda**.
34. Clique em **Emitir o documento bancário**.
35. Feche a página.

## <a name="post-packing-slip"></a>Lance a guia de remessa
1. No Painel de Ação, clique em **Selecionar e empacotar**.
2. Clique em **Postar guia de remessa**.
3. Expanda e recolha a seção **Parâmetros**.
4. No campo **Quantidade**, selecione **Todas**.
5. Expanda ou recolha a seção **Configuração**.
6. No campo **Data da guia de remessa**, insira uma data.
7. Selecione o Número da remessa.
8. Na lista, clique no link na linha selecionada.
9. Clique em **OK**.
10. Clique em **OK**.

## <a name="post-sales-invoice"></a>Lance uma fatura de venda
1. No Painel de Ação, clique em **Fatura**.
2. Clique em **Fatura**.
3. Expanda ou recolha a seção **Visão geral**.
4. Selecione o **Número da remessa**.
5. Na lista, clique no link na linha selecionada.
6. Expanda ou recolha a seção **Configuração**.
7. No campo **Data da fatura**, insira uma data.
8. Clique em **OK**.
9. Clique em **OK**.

## <a name="shipment-document-submitted-status"></a>Status de envio do documento de remessa
1. No Painel de Ação, clique em **Gerenciar**.
2. Clique em **Carta de crédito**.
3. Expandir ou recolher a seção **Linhas**.
    * Observação: o campo **Documento enviado** deve ser definido como **Sim**.  

## <a name="verify-export-letter-of-credit"></a>Verificar carta de crédito de exportação
1. Vá para **Gerenciamento de caixa e bancos > Cartas de crédito > Exportar carta de crédito e importar coleção**.
2. Na lista, localize e selecione o PDV desejado.
3. Na lista, clique no link na linha selecionada.
    * Verifique se a **Carta de crédito de exportação** tem o **Status da remessa** **Faturado**.  

## <a name="customer-payment"></a>Pagamento de cliente
1. Vá para **Contas a receber > Pagamentos > Diário de pagamentos**.
2. Clique em **Novo**.
3. Na lista, marque a linha selecionada.
4. No campo **Nome**, clique no botão suspenso para abrir a pesquisa.
5. Na lista, clique no link na linha selecionada.
6. Clique em **Linhas**.
7. No campo **Data**, insira uma data.
8. No campo **Conta**, especifique os valores desejados.
9. Clique em **Liquidação**.
10. Marque a caixa de seleção no cabeçalho de Totais.
    * Observação: defina o campo **Mostrar** para **Carta de crédito**.  
11. Na lista, localize e selecione o registro desejado.
12. Marque ou desmarque a caixa de seleção **Marcar**.
13. Clique em **OK**.
14. Clique na aba **Pagamento**.
    * Verifique o Número do documento bancário e os Detalhes do número de remessa  
15. Clique em **Enviar**.

## <a name="verify-export-letter-of-credit-after-payment"></a>Verifique a carta de crédito de exportação após o pagamento
1. Vá para **Gerenciamento de caixa e bancos > Cartas de crédito > Exportar carta de crédito e importar coleção**.
2. Na lista, localize e selecione o PDV desejado.
3. Na lista, clique no link na linha selecionada.
    * Verifique se o **Status da remessa** = **Pagamento recebido** e o **Valor do saldo** = **0,00**.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

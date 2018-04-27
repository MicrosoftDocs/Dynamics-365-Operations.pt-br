--- 
title: "Exportar uma carta de crédito"
description: "Este procedimento apresenta o processo de exportação de uma carta de crédito."
author: kweekley
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 0fa4b57825bcf81778d91ee01484511bb40f6bd7
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="export-a-letter-of-credit"></a>Exportar uma carta de crédito

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento apresenta o processo de exportação de uma carta de crédito.

Uma carta de crédito é um contrato emitido por um banco, no qual o banco garante o pagamento em nome do comprador, se as condições do contrato entre o comprador e o vendedor forem atendidas.



Execute o procedimento 'Configurar recursos bancários e perfis de lançamento' e o procedimento 'Criar um contrato de recursos bancários para carta de crédito' antes deste procedimento. A empresa de demonstração de USMF deve ser selecionada para executar com êxito este procedimento.




## <a name="create-sales-order-for-export-letter-of-credit"></a>Criar Ordem de venda para exportação de carta de crédito
1. Vá para Contas a receber > Ordens > Todas as ordens de venda.
2. Clique em Novo.
3. No campo Conta do cliente, clique no botão suspenso para abrir a pesquisa.
4. Na lista, localize e selecione o registro desejado.
5. Na lista, clique no link na linha selecionada.
6. Expandir ou recolher a seção Geral.
7. No campo Local, clique no botão suspenso para abrir a pesquisa.
    * Selecione o local no qual o item a ser emitido está estocado.  
8. Na lista, clique no link na linha selecionada.
9. No campo Depósito, clique no botão suspenso para abrir a pesquisa.
    * Selecione o depósito no qual o item a ser emitido está estocado.  
10. Na lista, clique no link na linha selecionada.
    * Observação: O campo Tipo de documento bancário deve ser selecionado com o valor 'Carta de crédito'.  
11. No campo Tipo de documento bancário, selecione 'Carta de crédito'.
12. Expanda ou recolha a seção Entrega.
    * Selecione controle da data de entrega = nenhum.  
13. No campo Data de recebimento solicitada, insira uma data.
14. Clique em OK.
15. No campo Número de item, clique no botão suspenso para abrir a pesquisa.
    * Selecione o item obrigatório a ser emitido/vendido.  
16. Na lista, localize e selecione o PDV desejado.
17. Na lista, clique no link na linha selecionada.
18. No campo Preço unitário, insira um número.
19. Expandir ou recolher a seção Detalhes de linha.
20. Clique na guia Entrega.
21. No campo Data de remessa solicitada, insira uma data.
22. No campo Data de remessa confirmada, insira uma data.
23. No Painel de Ação, clique em Gerenciar.
24. Clique em Carta de crédito.
25. No campo Número do documento bancário, digite um valor.
26. No campo Data de vencimento, insira uma data e hora.
27. Expandir ou recolher a seção Detalhes bancários.
28. No campo Banco emissor, clique no botão suspenso para abrir a pesquisa.
29. Na lista, clique no link na linha selecionada.
30. No campo Banco avisador, clique no botão suspenso para abrir a pesquisa.
31. Na lista, localize e selecione o registro desejado.
32. Na lista, clique no link na linha selecionada.
33. Clique em Buscar remessas de ordem de venda.
34. Clique em Emitir o documento bancário.
35. Feche a página.

## <a name="post-packing-slip"></a>Lance a guia de remessa
1. No Painel de Ação, clique em Separar e empacotar.
2. Clique em Lançar guia de remessa.
3. Expanda e recolha a seção Parâmetros.
4. No campo Quantidade, selecione 'Todas'.
5. Expanda ou recolha a seção Configuração.
6. No campo Data da guia de remessa, insira uma data.
7. Selecione o Número da remessa.
8. Na lista, clique no link na linha selecionada.
9. Clique em OK.
10. Clique em OK.

## <a name="post-sales-invoice"></a>Lance uma fatura de venda
1. No Painel de Ação, clique em Fatura.
2. Clique em Fatura.
3. Expanda ou recolha a seção Visão geral.
4. Selecione o Número da remessa.
5. Na lista, clique no link na linha selecionada.
6. Expanda ou recolha a seção Configuração.
7. No campo Data da fatura, insira uma data.
8. Clique em OK.
9. Clique em OK.

## <a name="shipment-document-submitted-status"></a>Status de envio do documento de remessa
1. No Painel de Ação, clique em Gerenciar.
2. Clique em Carta de crédito.
3. Expandir ou recolher a seção Linhas.
    * Observação: O campo 'Documento enviado” deve ser definido como 'Sim'.  

## <a name="verify-export-letter-of-credit"></a>Verificar carta de crédito de exportação
1. Vá para Gerenciamento de caixa de bando > Cartas de crédito > Exportar carta de crédito e importar cobranças.
2. Na lista, localize e selecione o PDV desejado.
3. Na lista, clique no link na linha selecionada.
    * Verifique se a Carta de crédito de exportação tem o Status da remessa 'Faturado'.  

## <a name="customer-payment"></a>Pagamento de cliente
1. Vá para Contas a receber > Pagamentos > Diário de pagamentos.
2. Clique em Novo.
3. Na lista, marque a linha selecionada.
4. No campo Nome, clique no botão suspenso para abrir a pesquisa.
5. Na lista, clique no link na linha selecionada.
6. Clique em Linhas.
7. No campo Data, insira uma data.
8. No campo Conta, especifique os valores desejados.
9. Clique em Liquidação.
10. Marque a caixa de seleção no cabeçalho de Totais.
    * Observação: Defina o campo Mostrar para 'Carta de crédito'.  
11. Na lista, localize e selecione o PDV desejado.
12. Marque ou desmarque a caixa de seleção Marcar.
13. Clique em OK.
14. Clique na aba Pagamento.
    * Verifique o Número do documento bancário e os Detalhes do número de remessa  
15. Clique em Lançar.

## <a name="verify-export-letter-of-credit-after-payment"></a>Verifique a carta de crédito de exportação após o pagamento
1. Vá para Gerenciamento de caixa de bando > Cartas de crédito > Exportar carta de crédito e importar cobranças.
2. Na lista, localize e selecione o PDV desejado.
3. Na lista, clique no link na linha selecionada.
    * Verifique o Status da remessa = Pagamento recebido e o Valor do saldo = 0,00.  



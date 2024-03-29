---
title: Gerar e processar reembolsos de cliente
description: Este procedimento demonstra como processar reembolsos de cliente desde a geração da reivindicação até o momento de passá-las como provisões para Contas a receber.
author: Henrikan
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PdsRebateAgreement, SalesTableListPage, SalesCreateOrder, SalesTable, MCRPriceHistory, SalesEditLines,  PdsRebateTableListPage, MCRBrokerWriteOffReason, MRCHierarchyAddCust, PdsItemRebateGroup, PdsRebate, PdsRebateProgramTMATable, PdsRebateTable, PdsRebateTableListPagePreviewPane, PdsRebateTrans, PdsRebateType_CustLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a85c027571a6d77ed61cd874bb9d97221b099967
ms.sourcegitcommit: 133aa728b8a795eaeaef22544f76478da2bd1df9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2022
ms.locfileid: "7969078"
---
# <a name="generate-and-process-customer-rebates"></a>Gerar e processar reembolsos de cliente

[!include [banner](../../includes/banner.md)]

Este procedimento demonstra como processar reembolsos de cliente desde a geração da reivindicação até o momento de passá-las como provisões para Contas a receber. Ele irá apresentar um exemplo específico para explicar como as diversas condições nas linhas de reembolso afetam o valor final que será creditado ao cliente. Você precisa utilizar a empresa de dados demonstrativos USMF, e executar as seguintes tarefas antes de iniciar o guia: (1) Acesse a página Parâmetros de contas a receber, e expanda a aba Preços e então a aba Detalhes do preço, e verifique se a opção Habilitar detalhes do preço está definida como Sim. (2) Acesse a página Contratos de reembolso e selecione o contrato de reembolso do cliente: USMF-000001. Se o campo Status de aprovação do fluxo de trabalho não estiver definido como Aprovado, você precisa clicar em Validação no Painel de Ações para aprová-lo.


## <a name="review-a-customer-rebate-agreement"></a>Revisar um contrato de reembolso do cliente
1. Acesse **Painel de Navegação > Módulos > Vendas e marketing > Reembolsos de clientes > Acordos de descontos**.
    - As próximas etapas abordam as condições do contrato USMF-000001. Isso facilita o entendimento de como os valores de crédito do cliente são calculados posteriormente no procedimento.  
    - O contrato é para um cliente individual, neste exemplo para o cliente US-009.  
    - Reembolsos são dados para o cliente quando compram um produto específico. Nesse caso, o produto tem número de item T0020.   
    - O desempenho de vendas do cliente, sobre o qual os valores do reembolso são estimados, deve ser acumulado semanalmente.  
    - A configuração para "Preço extraído de" é Bruto, o que significa que a quantia de venda da linha sobre a qual a reivindicação é estimada não é reduzida pelo desconto de linha.  
    - O campo Tipo de divisão da linha de reembolso mostra o método para calcular os reembolsos. Nesse caso, a meta de vendas sobre a qual os reembolsos serão estimados é definida como Quantidade.   
    - As linhas do contrato especificam o tipo da quantia de reembolso, o valor real do reembolso, e os limites. Neste exemplo, o cliente irá se qualificar para um reembolso de 20 USD por unidade vendida, se suas compras semanais do produto estiverem entre 1 e 50 unidades; e um reembolso de 40 USD por unidade vendida, se comprarem acima de 50 unidades.  
2. Feche a página.

## <a name="generate-rebate-claims"></a>Gerar reivindicações de reembolso
1. Acesse **Painel de navegação > Módulos > Vendas e marketing > Ordens de venda > Todas as ordens de venda**.
2. Clique em **Novo**. Para imitar a forma como reivindicações de reembolso são geradas, a próxima tarefa é criar uma ordem de venda, onde o produto e a quantidade irão qualificar o cliente em questão para um reembolso.    
3. No campo **Conta de cliente**, insira ou selecione um valor.
4. Clique em **OK**.
5. No campo **Número do item**, insira ou selecione um valor.
6. Defina **Quantidade** como '40'.
7. Na seção **Linhas de ordem de venda**, clique em **Linha da ordem de venda**.
8. Clique em **Detalhes de preço**. Se você não visualizar esta opção, é porque não definiu a opção **Habilitar detalhes de preço** como "Sim" antes de iniciar o guia.     
9. Expanda a seção **Reembolsos**. A guia **Reembolsos** lista todos os acordos de descontos que são aplicáveis à linha de ordem atual e mostra o valor estimado do reembolso. Observe que os valores exibidos são apenas indicações do que futuras reivindicações de reembolsos possam ser. Os valores reais de reembolsos podem ser diferentes dependendo de: o volume total de vendas obtido pelo cliente em um contrato de reembolso periódico; se o cliente devolveu quantidades parciais ou totais; e se a ordem de venda aplicável foi faturada.
10. Feche a página.
11. Clique em **Adicionar linha**.
12. No campo **Número do item**, insira ou selecione um valor.
13. Defina **Quantidade** como '60'.
14. Clique em **Salvar**.
15. No **Painel de Ações**, clique em **Fatura**.
16. Clique em **Fatura**.
17. Expanda a seção **Parâmetros**.
18. No campo **Quantidade**, selecione "Todas".
19. Clique em **OK**.
20. Clique em **OK**.

## <a name="process-rebate-claims"></a>Solicitações de reembolso do processo
1. Acesse **Painel de Navegação > Módulos > Vendas e marketing > Reembolsos de clientes > Reembolso**.
    - A página Reembolsos atua como uma bancada na qual você pode revisar, aprovar e processar reivindicações de reembolso. Agora você processará as reivindicações que foram criadas como resultado da cobrança de uma ordem de venda para o cliente US-009, que é o sujeito do contrato de reembolso USMF-000001.   
    - A primeira linha representa uma reivindicação de reembolso de 800 USD, com base nas vendas de 40 unidades do produto T0020, calculado a 20 USD por unidade. Isso corresponde às condições da primeira divisão de quantidade do acordo de reembolso.  
    - A segunda reivindicação é de 2.400 USD, que se baseia nas vendas de 60 unidades do produto T0020, calculada a 40 USD por unidade, como previsto pela segunda divisão de quantidade do contrato.  
    - Ambas as reivindicações estão no estado "A ser calculada". Isso significa que elas estão associadas a um contrato que rastreia o desempenho de vendas do cliente periodicamente e que elas devem ser calculadas novamente para levar em consideração o volume total de vendas dentro do respectivo período.   
2. Clique em **Acumular**.
3. No campo **Cliente**, insira ou selecione um valor.
4. No campo **Data de início**, selecione a data de hoje.
5. Clique em **OK**. Como resultado da execução da função **Acumular**, o valor de reivindicação estimado foi agora ajustado para levar em consideração o fato de que o volume total de vendas do cliente durante o período relevante é maior do que era quando o primeiro reembolso foi gerado. Mais especificamente, como a quantidade comprada total atingiu 100 unidades, o cliente agora se qualifica para 40 USD por unidade (de acordo com a segunda divisão de quantidade do contrato), ou 4,000 USD de quantidade total de reembolso. A diferença é registrada como um novo "ajuste" de reivindicação para os 800 USD adicionais. O status das reivindicações de reembolso que foram incluídas na atualização gerada pelo Acumular estão agora definidas como Calculada. 
6. Na lista, marque todas as linhas.
7. Clique em **Aprovar**.
8. Clique em **Processar**.
9. No campo **Cliente**, insira ou selecione um valor.
10. Clique em **OK**. Uma mensagem mostra que o reembolso foi processado com êxito, e o status das reivindicações foi alterado para Marcar. Isso significa que como resultado do lançamento de um Diário de provisão de reembolso que está sendo lançado:
    - As solicitações foram agora transferidas para o saldo temporário do cliente como deduções.
    - A Conta de provisão de reembolso foi creditada para representar o passivo futuro com o cliente.
    - A Conta de despesa de reembolso foi debitada, em reconhecimento dos custos contraídos em conexão com as vendas.   



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

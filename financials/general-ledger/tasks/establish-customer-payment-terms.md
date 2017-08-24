--- 
title: "Estabelecer condições de pagamento de cliente"
description: "Este procedimento define uma configuração de desconto à vista e a data de vencimento."
author: aprilolson
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
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: c871421254be6b0e9443fdf596932776d64428ae
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="establish-customer-payment-terms"></a>Estabelecer condições de pagamento de cliente

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimento define uma configuração de desconto à vista e a data de vencimento. Este guia de tarefa usa a empresa demo USMF.

1. Vá para Contas a receber > Configurar pagamentos > Dias de pagamento
    * A configuração das condições de pagamento será compartilhada para contas a receber e contas a pagar. Se você define o no módulo, estarão disponíveis em outro módulo também. Para este guia de tarefa, eu configurei todos os termos de pagamento em contas a receber.  
2. Clique em Novo.
    * Crie um dia de pagamento se as condições de pagamento exigem um determinado dia da semana (segunda-feira, terça-feira, etc.) ou uma data específica do mês (5º, 10º, etc.).  
3. No campo de dia de pagamento, digite uma ID para o dia de pagamento no campo do dia de pagamento.
4. No campo Descrição, insira uma descrição do tipo de dia de pagamento.
5. No campo da semana ou mês, selecione a semana ou mês.
    * Se você deseja inserir um dia da semana, como segunda-feira, selecione a semana. Se você deseja inserir uma data no mês, como o 10º, selecione o mês. Selecione Mês neste exemplo.  
6. No campo Dia do mês, insira uma data.
    * A data deve ser inserida como um número, como '10', e não como '10º'.  
7. Clique em Salvar.
8. Feche a página.
9. Vá para Contas a receber > Configurar pagamentos > Termos de pagamento.
10. Clique em Novo.
    * As condições de pagamento são usadas para definir como as datas de vencimento serão calculadas. A data de desconto à vista é definida em uma página separada.  
11. No campo condições de pagamento, insira uma ID de campo nas condições de pagamento.
12. No campo Descrição, insira uma descrição.
13. Selecione um método de pagamento como C.O.D., a rede, o mês atual, etc.
    * O método Pagamento é usado para definir como a data de vencimento será calculada.  Por exemplo, Rede é usada se a data de vencimento for sempre um número definido de meses ou dias após a data da fatura. C.O.D. pode ser usado para quando o pagamento é necessário na fatura, dessa forma uma data de vencimento não seria calculada. Selecione o mês atual para esta guia de tarefa.  
14. Selecione um dia de pagamento se um determinado dia da semana ou a data serão incluídos no cálculo.
    * Dependendo das condições de pagamento, você pode inserir uma quantidade em meses ou dias. Ou você pode usar o plano de pagamento ou o dia de pagamento 'adicionar' ao final do método de pagamento. Se a data de vencimento for sempre o 10º dia do mês seguinte, selecione um dia de pagamento do 10º.  
15. Clique em Salvar.
16. Feche a página.
17. Vá para Contas a receber > Configurar pagamentos > Descontos à vista.
18. Clique em Novo.
    * Essa página é usada para definir como a data de desconto à vista será calculada.  
19. No campo desconto à vista, digite uma ID no campo desconto à vista.
20. No campo Descrição, insira uma descrição.
21. Se um desconto à vista estratificado estiver disponível, selecione o próximo código do desconto que é relevante após esse novo desconto à vista.
22. Insira o número de dias usados para calcular a data do desconto à vista.
    * Se o princípio líquido for selecionado, o número de dias será adicionado à data da nota fiscal para calcular a data do desconto à vista.  
23. Inserir percentual do desconto à vista.
24. Insira a conta principal a qual o desconto à vista será lançado para as notas fiscais do cliente.
25. No campo Contas de contrapartida de desconto, selecione uma opção.
    * Se você selecionar 'Contas nas linhas da nota fiscal', o desconto à vista será lançado na mesma conta principal do ativo/despesa nas linhas da nota fiscal do fornecedor. Se você selecionar 'Usar conta principal para faturas de fornecedor', o desconto à vista lançará na conta principal definida por você em 'Conta principal para faturas de fornecedor'. Neste exemplo, selecione 'Usar conta principal para faturas de fornecedor'.  
26. Insira a conta principal a qual o desconto à vista será lançado para as notas fiscais do fornecedor.
27. Clique em Salvar.



---
title: Estabelecer condições de pagamento de cliente
description: Este procedimento define uma configuração de desconto à vista e a data de vencimento.
author: aprilolson
ms.date: 08/29/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PaymDay, PaymTerm, CashDisc
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9b2ae5e63a2efb4bc913efa4d88c65a70133a2d9
ms.sourcegitcommit: f96e5dec5a808d9819d2a23b8e15ce00aeff475b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2022
ms.locfileid: "9752767"
---
# <a name="establish-customer-payment-terms"></a>Estabelecer condições de pagamento de cliente

[!include [banner](../../includes/banner.md)]

Este procedimento define uma configuração de desconto à vista e a data de vencimento. Este guia de tarefa usa a empresa demo USMF.

1. Acesse **Painel de Navegação > Módulos > Contas a receber > Configuração de pagamentos > Dias de pagamento**. A configuração das **Condições de pagamento** será compartilhada para **Contas a receber** e **Contas a pagar**. Se você define o no módulo, estarão disponíveis em outro módulo também. Para este guia de tarefas, configuramos todas as condições de pagamento em **Contas a receber**.
2. Clique em **Novo**. Crie um dia de pagamento se as condições de pagamento exigem um determinado dia da semana (segunda-feira, terça-feira, etc.) ou uma data específica do mês (5º, 10º, etc.). 
3. No campo **Dia de pagamento**, insira uma ID.
4. No campo **Descrição**, insira uma descrição do dia de pagamento.
5. No campo **Semana/mês**, selecione 'Semana' ou 'Mês'. Se você deseja inserir um dia da semana, como segunda-feira, selecione a semana. Se você deseja inserir uma data no mês, como o 10º, selecione o mês. Selecione Mês neste exemplo. 
6. No campo **Dia do mês**, insira uma data. A data deve ser inserida como um número, como '10', e não como '10º'. 
7. Clique em **Salvar**.
8. Feche a página.
9. Acesse **Painel de Navegação > Módulos > Contas a receber > Configuração de pagamentos > Condições de pagamento**. 

>[!NOTE] 
>Se as **Condições de pagamento** forem **À Vista**, o campo **Pagamento à vista**, na página **Condições de pagamento**, deve ser **Não**.

10. Clique em **Novo**. As **condições de pagamento** são usadas para definir como as datas de vencimento serão calculadas. A data de desconto à vista é definida em uma página separada. 
11. No campo **Condições de pagamento**, insira uma ID.
12. No campo **Descrição**, insira uma descrição.
13. Selecione uma **Forma de pagamento**, como **C.O.D.**, **Líquido**, **Mês atual** etc. A **Forma de pagamento** é usada para definir como o vencimento será calculado. Por exemplo, **Líquido** é usada se a data de vencimento for sempre um número definido de meses ou dias após a data da fatura. **C.O.D.** pode ser usado para quando o pagamento é necessário na fatura, dessa forma uma data de vencimento não seria calculada. Selecione **Mês atual** para este guia de tarefas.  
14. Selecione um **Dia de pagamento** se um determinado dia da semana ou uma data forem incluídos no cálculo. Dependendo das condições de pagamento, você pode inserir uma quantidade em meses ou dias. Ou você pode usar o **Plano de pagamento** ou o **Dia de pagamento** para 'adicionar' ao final da **Forma de pagamento**. Se a data de vencimento for sempre o 10º dia do mês seguinte, selecione um **Dia de pagamento** 10. Se estiver usando um **Calendário de pagamentos**, você poderá definir como a data de vencimento será determinada quando a data calculada cair em um dia não útil. A data de vencimento inicial é calculada usando os dias do calendário. Se a data calculada não for um dia útil, você poderá ajustar a data de vencimento calculada para o próximo dia útil ou para o dia útil anterior.
15. Clique em **Salvar**.
16. Feche a página.
17. Acesse **Contas a receber > Configuração de pagamentos > Descontos à vista**.
18. Clique em **Novo**. Essa página é usada para definir como a data de desconto à vista será calculada. 
19. No campo **Desconto à vista**, insira uma ID.
20. No campo **Descrição**, insira uma descrição.
21. Se um desconto à vista estratificado estiver disponível, selecione o **Próximo código do desconto** relevante após esse novo desconto à vista.
22. No campo **Dias**, insira o número de dias usado para calcular a data do desconto à vista. Se o princípio **Líquido** for selecionado, o número de dias será adicionado à data da fatura para calcular a data do desconto à vista.  
23. No campo **Porcentagem de desconto**, insira a porcentagem do desconto à vista.
24. Em **Conta principal para descontos do cliente**, insira a conta principal na qual o desconto à vista lançará as faturas de clientes.
25. No campo **Contas de contrapartida de desconto**, selecione uma opção. Se você selecionar 'Contas nas linhas da nota fiscal', o desconto à vista será lançado na mesma conta principal do ativo/despesa nas linhas da nota fiscal do fornecedor. Se você selecionar **Usar conta principal para faturas de fornecedor**, o desconto à vista será lançado na conta principal definida por você em **Conta principal para faturas de fornecedor**. Neste exemplo, selecione **Usar conta principal para faturas de fornecedor**. 
26. No campo **Conta principal para descontos do fornecedor**, insira a conta principal na qual o desconto à vista lançará as faturas de fornecedores.
27. Clique em **Salvar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

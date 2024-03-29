---
title: Calcular juros e multas em pagamentos de clientes (Brasil)
description: Você pode aplicar juros e multas a pagamentos de cliente que estejam atrasados.
author: AdamTrukawka
ms.date: 06/26/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Brazil
ms.author: atrukawk
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a3bf4454696644fa44f4a867fb44d7934ae587a3
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9281206"
---
# <a name="calculate-interest-and-fines-on-customer-payments-brazil"></a>Calcular juros e multas em pagamentos de clientes (Brasil)

[!include [banner](../../includes/banner.md)]

Você pode aplicar juros e multas a pagamentos de cliente que estejam atrasados. Os valores dos juros e da multa que se aplicam a um pagamento podem ser calculados quando você recebe um pagamento de um cliente. Antes de calcular os códigos de juros ou de multa para pagamentos de cliente, você deverá configurar uma lista de feriados bancários e de feriados nacionais. Uma data de feriado que é configurada na página Calendário de pagamentos será considerada como um dia que não é útil. Se uma fatura vencer em um dia que não seja útil, a data de vencimento se deslocará para o próximo dia útil no calendário, e os juros e as multas serão calculadas de acordo com essa data. Esta tarefa usa a empresa de demonstração BRMF.



1. Ir para Contas recebíveis > Clientes > Todos os clientes.
2. Na lista, localize e selecione o PDV desejado.
3. Na lista, clique no link na linha selecionada.
4. Expanda a seção de padrões de pagamento.
5. Clique em Editar.
6. No campo Plano de pagamento, insira ou selecione um valor.
7. Na lista, clique no link na linha selecionada.
8. No campo Código de juros, insira ou selecione um valor.
9. Na lista, clique no link na linha selecionada.
10. No campo Código de juros, insira ou selecione um valor.
11. Clique em Salvar.
12. Feche a página.
13. Feche a página.
14. Acesse Vendas e marketing > Ordens de venda > Todas as ordens de venda.
15. Clique em Novo.
16. No campo Conta de cliente, insira ou selecione um valor.
17. Clique em OK.
18. Clique em Adicionar nova linha.
19. Na lista, marque a linha selecionada.
20. No campo Número do item, insira ou selecione um valor.
21. No campo Quantidade, insira um número.
22. No campo CFOP, insira ou selecione um valor.
23. Clique em Salvar.
24. Clique em Fatura.
25. No campo Quantidade, selecione uma opção.
26. Selecione Sim no campo Imprimir fatura.
27. Clique em OK.
28. Clique em Sim.
29. Feche a página.
30. Feche a página.
31. Feche a página.
32. Acesse Contas a receber > Pagamentos > Diário de pagamentos.
33. Clique em Novo.
34. Na lista, marque a linha selecionada.
35. No campo Nome, insira ou selecione um valor.
36. Clique em Linhas.
37. Na lista, marque a linha selecionada.
38. No campo Data, insira uma data.
39. No campo Conta, especifique os valores desejados.
40. Clique em Liquidar transações.
41. Na lista, localize e selecione o PDV desejado.
42. Marque a caixa de seleção Marcar.
43. Marque a caixa de seleção Marcar.
44. Clique em OK.
45. Na lista, marque a linha selecionada.
46. No campo Descrição, insira ou selecione um valor.
47. No campo Contrapartida, especifique os valores desejados.
48. Clique em Lançar.
49. Feche a página.
50. Feche a página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

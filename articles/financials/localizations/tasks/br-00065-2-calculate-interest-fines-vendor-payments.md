--- 
title: Calcular juros e multas sobre pagamentos de fornecedores (Brasil)
description: "Você pode aplicar juros e multas a pagamentos de fornecedor que estejam atrasados."
author: sndray
manager: AnnBe
ms.date: 06/26/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5d78d10bcf1150b392aee845f2a330962005e276
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="calculate-interest-and-fines-on-vendor-payments-brazil"></a>Calcular juros e multas sobre pagamentos de fornecedores (Brasil)

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Você pode aplicar juros e multas a pagamentos de fornecedor que estejam atrasados. Os valores dos juros e da multa que se aplicam a um pagamento podem ser calculados quando você faz um pagamento para um fornecedor. Antes de calcular os códigos de juros ou de multa para pagamentos de fornecedor, você deverá configurar uma lista de feriados bancários e de feriados nacionais. Uma data de feriado que é configurada na página Calendário de pagamentos será considerada como um dia que não é útil. Se uma fatura vencer em um dia que não seja útil, a data de vencimento se deslocará para o próximo dia útil no calendário, e os juros e as multas serão calculadas de acordo com essa data. Esta tarefa usa a empresa de demonstração BRMF.

1. Vá para Contas a pagar > Fornecedores > Todos os fornecedores.
2. Na lista, localize e selecione o PDV desejado.
3. Na lista, clique no link na linha selecionada.
4. Expandir a seção Pagamento.
5. Clique em Editar.
6. No campo Plano de pagamento, insira ou selecione um valor.
7. Na lista, clique no link na linha selecionada.
8. No campo Código de juros, insira ou selecione um valor.
9. Na lista, clique no link na linha selecionada.
10. No campo Código de juros, insira ou selecione um valor.
11. Clique em Salvar.
12. Feche a página.
13. Feche a página.
14. Vá para Aquisição e fornecimento > Ordens de compra > Todas as ordens de compra.
15. Clique em Novo.
16. No campo Conta de fornecedor, insira ou selecione um valor.
17. Clique em OK.
18. Clique em Adicionar nova linha.
19. Na lista, marque a linha selecionada.
20. No campo Número do item, insira ou selecione um valor.
21. No campo CFOP, insira ou selecione um valor.
22. No campo Quantidade, insira um número.
23. Clique em Salvar.
24. No Painel de Ação, clique em Compra.
25. Clique em Confirmar.
26. Feche a página.
27. Feche a página.
28. Vá para Contas a pagar > Ordens de compra > Todas as ordens de compra.
29. Na lista, clique no link na linha selecionada.
30. No Painel de Ação, clique em Fatura.
31. Clique em Fatura.
32. Clique em Padrão de: Quantidade de recebimento de produtos para abrir a caixa de diálogo suspensa.
33. No campo Quantidade padrão para linhas, selecione uma opção.
34. Clique em OK.
35. No campo Chave de acesso, digite um valor.
36. No campo Data da fatura, insira uma data.
37. Clique em Lançar.
38. Feche a página.
39. Feche a página.
40. Vá para Contas a pagar > Pagamentos > Diário de pagamentos.
41. Clique em Novo.
42. Na lista, marque a linha selecionada.
43. No campo Nome, insira ou selecione um valor.
44. Clique em Linhas.
45. Na lista, marque a linha selecionada.
46. No campo Data, insira uma data.
47. No campo Conta, especifique os valores desejados.
48. No campo Descrição, insira ou selecione um valor.
49. Clique em Liquidar transações.
50. Na lista, localize e selecione o PDV desejado.
51. Marque a caixa de seleção Marcar.
52. Marque a caixa de seleção Marcar.
53. Clique em OK.
54. Na lista, marque a linha selecionada.
55. No campo Contrapartida, especifique os valores desejados.
56. Clique em Lançar.
57. Feche a página.
58. Feche a página.



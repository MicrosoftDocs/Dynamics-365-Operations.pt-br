---
title: Ativos fixos de PIS e COFINS (Brasil)
description: Quando uma entidade legal compra um ativo fixo, o crédito fiscal de PIS e COFINS que é calculado sobre essa transação pode ser adquirido em um número de parcelas específico.
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
ms.openlocfilehash: 2392e4634026fab3fb1d575ac0d97c4054859da3
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282376"
---
# <a name="pis-and-cofins-fixed-assets-brazil"></a>Ativos fixos de PIS e COFINS (Brasil)

[!include [banner](../../includes/banner.md)]

Quando uma entidade legal compra um ativo fixo, o crédito fiscal de PIS e COFINS que é calculado sobre essa transação pode ser adquirido em um número de parcelas específico. Para ter o cálculo correto desta restituição do imposto, a entidade legal deve apresentar um livro fiscal específico ou relatar informações no arquivo Contribuições EFD SPED para demonstrar a apropriação correta do valor do crédito fiscal de PIS e COFINS. O controle de crédito apropriado no período de avaliação de imposto é detalhado em registros F120 e F130 de contribuições de EFD SPED. Esta tarefa usa a empresa de demonstração BRMF.

1. Acesse Aquisição e fornecimento > Ordens de compra > Todas as ordens de compra.
2. Clique em Novo.
3. No campo Conta de fornecedor, insira ou selecione um valor.
4. Clique em OK.
5. Clique em Adicionar nova linha.
6. Na lista, marque a linha selecionada.
7. No campo Número do item, insira ou selecione um valor.
8. No campo CFOP, insira ou selecione um valor.
9. No campo Quantidade, insira um número.
10. No campo Preço unitário, insira um número.
11. Expanda a seção Detalhes da linha.
12. Clique na guia Ativos fixos.
13. Selecione Sim no campo Novo ativo fixo? .
14. No campo Grupo de ativo fixo, insira ou selecione um valor.
15. Clique na guia Dimensões financeiras.
16. No campo CostCenter, insira ou selecione um valor.
17. No campo Filial, insira ou selecione um valor.
18. No Painel de Ação, clique em Compra.
19. Clique em Confirmar.
20. Feche a página.
21. Feche a página.
22. Acesse Contas a pagar > Ordens de compra > Todas as ordens de compra.
23. Na lista, clique no link na linha selecionada.
24. No Painel de Ação, clique em Fatura.
25. Clique em Fatura.
26. Clique em Padrão de: Quantidade de recebimento de produtos para abrir a caixa de diálogo suspensa.
27. No campo Quantidade padrão para linhas, selecione uma opção.
28. Clique em OK.
29. No campo Modelo do documento, insira ou selecione um valor.
30. No campo Chave de acesso, digite um valor.
31. No campo Data da fatura, insira uma data.
32. No campo Lançamento, insira uma data.
33. Clique em Lançar.
34. Feche a página.
35. Feche a página.
36. Acesse Livros fiscais > Comum > Período de escrituração.
37. Clique em Criar novo período de escrituração para abrir a caixa de diálogo suspensa.
38. No campo Estabelecimento fiscal, insira ou selecione um valor.
39. No campo Mês, selecione uma opção.
40. No campo Ano, insira um número.
41. Clique em OK.
42. Clique em Sincronizar.
43. Clique em OK.
44. Clique em PIS-COFINS.
45. Clique em Apuração de imposto PIS e COFINS para abrir a caixa de diálogo suspensa.
46. Clique em OK.
47. Feche a página.
48. Feche a página.
49. Acesse Livros fiscais > Comum > Ativos fixos > Todos os ativos fixos com PIS e COFINS.
50. Na lista, clique no link na linha selecionada.
51. Expanda a seção de transações de ativo fixo de PIS e COFINS.
52. Feche a página.
53. Feche a página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

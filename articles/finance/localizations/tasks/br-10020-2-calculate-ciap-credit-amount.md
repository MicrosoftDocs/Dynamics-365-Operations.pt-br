---
title: Calcular o valor de crédito CIAP (Brasil)
description: Cada mês, para cada estabelecimento fiscal, o valor de crédito de imposto é calculado para aquisições anteriores de ativo fixo de cada ativo fixo.
author: sndray
ms.date: 06/26/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1cee2ac378cf90f43e36668b671a256b12203b1c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823613"
---
# <a name="calculate-ciap-credit-amount-brazil"></a>Calcular o valor de crédito CIAP (Brasil)

[!include [banner](../../includes/banner.md)]

Cada mês, para cada estabelecimento fiscal, o valor de crédito de imposto é calculado para aquisições anteriores de ativo fixo de cada ativo fixo. O cálculo ocorre até que o número máximo de pagamentos de parcelas de crédito fiscal seja atingido, ou o ativo fixo não pertença à entidade legal. Cada pagamento de parcela de crédito fiscal do ativo fixo é usado para criar uma nota fiscal de transferência ou apropriação de imposto que faz parte da apuração do imposto ICMS da entidade legal. Esta tarefa usa a empresa de demonstração BRMF.

1. Vá para Livros fiscais > Comum > Período de escrituração.
2. Clique em Criar novo período de escrituração para abrir a caixa de diálogo suspensa.
3. No campo Estabelecimento fiscal, insira ou selecione um valor.
4. No campo Mês, selecione uma opção.
5. No campo Ano, insira um número.
6. Clique em OK.
7. Clique em Sincronizar.
8. Clique em OK.
9. Clicar em ICMS.
10. Clique em Apuração de imposto ICMS para abrir a caixa de diálogo suspensa.
11. Clique em OK.
12. Clique em Apuração do CIAP.
13. Clique em Calcular fator do CIAP.
14. Feche a página.
15. Feche a página.
16. Feche a página.
17. Vá para Contabilidade > Entradas de diário > Todas as notas fiscais de transferência ou apropriação de imposto.
18. Clique em Novo.
19. No campo Tipo de documento fiscal de transferência ou apropriação de imposto, selecione uma opção.
20. No campo ID do estabelecimento fiscal, insira ou selecione um valor.
21. No campo Número de conta, insira ou selecione um valor.
22. No campo Data, insira uma data.
23. No campo Nota fiscal, insira ou selecione um valor.
24. Clique em Salvar.
25. Clique em Adicionar nova linha.
26. No campo Descrição do item, digite um valor.
27. Na lista, marque a linha selecionada.
28. No campo CFOP, insira ou selecione um valor.
29. No campo Código de impostos sobre vendas, insira ou selecione um valor.
30. No campo Valor, insira um número.
31. Clique em Lançar.
32. Clique em OK.
33. Feche a página.
34. Feche a página.
35. Vá para Contas a receber > Notas fiscais > Notas fiscais eletrônicas > Exportar/importar processo de NF-e.
36. Clique em OK.
37. Vá para Livros fiscais > Comum > Período de escrituração.
38. Na lista, marque a linha selecionada.
39. Clique em Sincronizar.
40. Clique em OK.
41. Clicar em ICMS.
42. Feche a página.
43. Feche a página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
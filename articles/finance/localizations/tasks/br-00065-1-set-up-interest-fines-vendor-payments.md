---
title: Configurar juros e multas para pagamentos de fornecedores (Brasil)
description: Você deve configurar contas para juros e multas financeiras, códigos padrão para juros e multas, e códigos de juros e de multas para fornecedores e ordens de compra.
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
ms.openlocfilehash: acfcf1b81fc464b576b2a019dc7da83154a1874a
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269310"
---
# <a name="set-up-interest-and-fines-for-vendor-payments-brazil"></a>Configurar juros e multas para pagamentos de fornecedores (Brasil)

[!include [banner](../../includes/banner.md)]

Você deve configurar contas para juros e multas financeiras, códigos padrão para juros e multas, e códigos de juros e de multas para fornecedores e ordens de compra. Também é necessário definir os feriados ou dias não úteis durante um ano financeiro que não serão considerados quando as multas e os juros forem calculados.  Esta tarefa usa a empresa de demonstração BRMF.

1. Acesse Contas a pagar > Configuração > Perfis de lançamentos de fornecedores.
2. Use o Filtro Rápido para localizar registros. Por exemplo, filtre no campo Perfil de lançamento com um valor de '010'.
3. Na lista, localize e selecione o PDV desejado.
4. Clique em Editar.
5. No campo Juros financeiros, especifique os valores desejados.
6. No campo Multa, especifique os valores desejados.
7. Clique em Salvar.
8. Feche a página.
9. Acesse Contas a pagar > Configuração de pagamento > Calendário de pagamentos.
10. Use o Filtro Rápido para localizar registros. Por exemplo, filtre o campo Calendário de pagamentos com um valor de 'Brasil'.
11. Clique em feriados do estado/província.
12. Use o Filtro Rápido para localizar registros. Por exemplo, filtre o campo Estado/província com um valor de 'SP'.
13. Clique em Novo.
14. No campo Data, insira uma data.
15. No campo Descrição, digite um valor.
16. Clique em Salvar.
17. Clique em Feriados municipais.
18. Use o Filtro Rápido para localizar registros. Por exemplo, filtre no campo Cidade com um valor de 'São Paulo'.
19. Clique em Adicionar.
20. No campo Data, insira uma data.
21. No campo Descrição, digite um valor.
22. Clique em Salvar.
23. Feche a página.
24. Feche a página.
25. Feche a página.
26. Acesse Contas a receber > Configuração de pagamento > Códigos de multa.
27. Clique em Novo.
28. No campo Código de multa, digite um valor.
29. No campo Descrição, digite um valor.
30. No campo % de multa, digite um número.
31. Clique em Salvar.
32. Feche a página.
33. Acesse Contas a pagar > Configuração de pagamento > Códigos de juros.
34. Clique em Novo.
35. No campo Código de juros, digite um valor.
36. No campo Descrição, digite um valor.
37. No campo % de juros, insira um número.
38. No campo Cálculo de juros por campo, insira um número.
39. Clique em Salvar.
40. Feche a página.
41. Acesse Contas a pagar > Fornecedores > Todos os fornecedores.
42. Use o Filtro Rápido para localizar registros. Por exemplo, no campo Conta de fornecedor, filtre com um valor de 'BRMF-000001'.
43. Na lista, clique no link na linha selecionada.
44. Expandir a seção Pagamento.
45. Clique em Editar.
46. No campo Código de juros, insira ou selecione um valor.
47. No campo Código de juros, insira ou selecione um valor.
48. Clique em Salvar.
49. Feche a página.
50. Feche a página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

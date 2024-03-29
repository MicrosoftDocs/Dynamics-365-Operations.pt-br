---
title: Atributos de imposto de estabelecimento fiscal (Brasil)
description: Use este procedimento para criar um ou mais estabelecimentos fiscais para uma entidade legal.
author: AdamTrukawka
ms.date: 06/24/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Brazil
ms.author: atrukawk
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.search.industry: Manufacturing;Distribution;Service industries
ms.openlocfilehash: ec4db214afd2cdd45ce4c5bd5eb9776207d4ba03
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288498"
---
# <a name="fiscal-establishment-tax-attributes-brazil"></a>Atributos de imposto de estabelecimento fiscal (Brasil)

[!include [banner](../../includes/banner.md)]

Use este procedimento para criar um ou mais estabelecimentos fiscais para uma entidade legal. Um estabelecimento fiscal requer um número de inscrição fiscal no CNPJ (Cadastro Nacional da Pessoa Jurídica) ou IE (Inscrição Estadual). Você pode agrupar estabelecimentos fiscais e configurar grupos de impostos para cada grupo de estabelecimentos fiscais na página Matriz de impostos. Esta tarefa usa a empresa de demonstração BRMF.

1. Acesse Administração da organização > Organizações > Entidades legais.
2. Clique para seguir o link no campo Nome.
3. Expanda a seção Endereços.
4. Clique em Adicionar.
5. No campo Nome ou Descrição, digite um valor.
6. No campo Motivo, insira ou selecione um valor.
7. No campo País/Região, digite um valor.
8. Clique em Sim.
9. No campo CEP/código postal, digite um valor.
10. No campo Número da rua, digite um valor.
11. Clique em OK.
12. Feche a página.
13. Feche a página.
14. Acesse Administração da organização > Organizações > Estabelecimentos fiscais > Grupos de estabelecimentos fiscais.
15. Crie um novo grupo de estabelecimentos fiscais.
16. No campo Grupo de estabelecimento fiscal, digite um valor.
17. No campo Descrição, digite um valor.
18. Clique em Salvar.
19. Feche a página.
20. Acesse Administração da organização > Organizações > Estabelecimentos fiscais > Estabelecimentos fiscais.
21. Crie um novo estabelecimento fiscal.
22. No campo ID do estabelecimento fiscal, digite um valor.
23. No campo Grupo de estabelecimento fiscal, insira ou selecione um valor.
24. No campo CNPJ, insira o CNPJ do novo estabelecimento fiscal.
25. Expanda a seção Endereço.
26. No campo Nome, insira ou selecione um valor.
27. No campo IE, insira o IE do estabelecimento fiscal com base no estado do endereço.
28. Clique em Salvar.
29. Feche a página.
30. Acesse Gerenciamento do estoque > Configuração > Divisão do estoque > Sites.
31. Clique em Novo.
32. No campo Local, digite um valor.
33. No campo Nome, digite um valor.
34. No campo ID do estabelecimento fiscal, insira ou selecione um valor.
35. Expanda a seção Dimensões financeiras.
36. Clique para seguir o link no campo Filial.
37. Clique em Novo.
38. No campo Valor da dimensão, digite um valor.
39. No campo Descrição, digite um valor.
40. Clique em Adicionar para abrir a caixa de diálogo suspensa.
41. Clique em Adicionar.
42. Clique em Salvar.
43. Feche a página.
44. No campo Filial, insira ou selecione um valor.
45. Clique em Salvar.
46. Feche a página.
47. Acesse Administração da organização > Organizações > Estabelecimentos fiscais > Estabelecimentos fiscais.
48. Abrir a caixa de diálogo de seleção avançada de linha
49. Aplique os seguintes filtros: insira um valor de filtro de "NovaFilial", no campo "ID do estabelecimento fiscal" usando o operador de filtro "é exatamente"
50. Clique em Tipos de documento fiscal.
51. Clique em Novo.
52. No campo Tipo de documento fiscal, digite um valor.
53. No campo Nome, digite um valor.
54. No campo Série, digite um valor.
55. No campo Sequência numérica de nota fiscal, insira ou selecione um valor.
56. No campo Modelo do documento, insira ou selecione um valor.
57. Clique em Salvar.
58. Feche a página.
59. Feche a página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

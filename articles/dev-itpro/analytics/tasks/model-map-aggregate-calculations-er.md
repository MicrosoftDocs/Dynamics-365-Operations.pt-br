---
title: Usar configurações de mapeamento de modelo para cálculos agregados no nível do banco de dados
description: Este procedimento fornece informações sobre como criar uma nova configuração de mapeamento de modelo de Relatório eletrônico (ER) e usar funções de ER internas para obter cálculos agregados eficientes.
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a462a3997644a494b5cea89c9530ddba67c32450
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "313626"
---
# <a name="use-model-mapping-configurations-for-aggregate-calculations-at-the-database-level"></a>Usar configurações de mapeamento de modelo para cálculos agregados no nível do banco de dados

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento fornece informações sobre como criar uma nova configuração de mapeamento de modelo de Relatório eletrônico (ER) e usar funções de ER internas para obter cálculos agregados eficientes. Neste procedimento, você criará uma configuração para a empresa de exemplo, Litware, Inc. 

Este procedimento é criado para usuários com a função atribuída de Administrador do sistema ou Desenvolvedor de relatório eletrônico. Estas etapas podem ser concluídas usando qualquer conjunto de dados.

 Para concluir essas etapas, você deve primeiro concluir as etapas do procedimento "O ER melhora a eficiência de cálculos agregados executando-os no nível do banco de dados (Parte 1: Preparar configurações)”.

1. Vá para Administração da organização > Relatório eletrônico > Configurações.
2. Na árvore, expanda 'Modelo intrastat'.
3. Na árvore, selecione "Intrastat model\Intrastat sample mapping".
4. Clique em Designer.
5. Clique em Designer.
6. Na árvore, selecione 'Dynamics 365 for Operations\Registros da tabela'.
7. Clique em Adicionar raiz.
    * Adicionar uma nova fonte de dados que represente os registros que deseja agrupar.  
8. No campo Nome, digite 'Transações'.
    * Transações  
9. No campo Tabela, digite 'Intrastat'.
    * Intrastat  
10. Clique em OK.
11. Na árvore, selecione 'Funções\Agrupar por'.
    * Este tipo de fonte de dados é usado para apresentar uma nova fonte de dados no tempo de execução para agrupar registros e calcular agregações necessárias.  
12. Clique em Adicionar raiz.
13. No campo Nome, digite 'TransactionsGroups'.
    * TransactionsGroups  
14. Clique em Editar grupo por.
15. Na árvore, selecione 'Transações'.
    * Selecione a fonte de dados adicionada do tipo 'Lista de registros' que represente os registros que deseja agrupar.  
16. Clique em Adicionar campo a.
17. Clique em O que agrupar.
18. Na árvore, expanda 'Transações'.
19. Na árvore, selecione "Transactions\Direction".
20. Clique em Adicionar campo a.
21. Clique em Campos agrupados.
    * Selecione o campo para especificar o nível de agrupamento. Com base nessa seleção, a fonte de dados retornará no tempo de execução a mesma quantidade de grupos de transações e códigos de direção que serão encontrados na tabela intrastat.  
22. Na árvore, selecione "Transactions\Invoice amount(AmountMST)".
    * Selecione o campo para especificar a fonte para o cálculo de agregação.  
23. Clique em Adicionar campo a.
24. Clique em Campos de agregação.
25. Na lista, marque a linha selecionada.
26. No campo Método, selecione 'Soma'.
    * Selecione o tipo de agregação.  
27. No campo Nome, digite 'SumOfAmountMST'.
    * Especifique o nome dessa agregação na fonte de dados configurada.  
28. Clique em Salvar.
    * Observe que o campo 'Execução em' indica que esse agrupamento será executado no tempo de execução no banco de dados SQL.  
29. Feche a página.
30. Clique em OK.
31. Na árvore, expanda 'Totais'.
32. Na árvore, expanda 'TransactionsGroups'.
33. Na árvore, expanda "TransactionsGroups\aggregated".
34. Na árvore, selecione "TransactionsGroups\aggregated\SumOfAmountMST".
35. Na árvore, selecione "Totals\Total invoice value(TotalInvoiceValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$AmountMSTRounded')".
36. Clique em Associar.
    * Com base nessa configuração, essa fonte de dados calculará a soma dos valores do campo 'AmountMST' para cada grupo de transações. Esse cálculo de agregação estará disponível como o item TransactionsGroups.aggregated.TotalAmount.  
37. Na árvore, expanda 'TransactionsGroups'.
38. Na árvore, selecione 'TransactionsGroups'.
39. Clique em Editar.
40. Clique em Editar grupo por.
41. Na árvore, expanda 'Transações'.
42. Na árvore, selecione "Transactions\Invoice amount(AmountMST)".
43. Clique em Adicionar campo a.
44. Clique em Campos de agregação.
45. Na lista, marque a linha selecionada.
46. No campo Método, selecione 'Máx.'.
47. No campo Nome, digite 'MaxOfAmountMST'.
48. Clique em Salvar.
    * Atualmente, a execução de fontes de dados GROUPBY pode ser traduzida para o nível do banco de dados SQL com algumas limitações. A tradução pode ser feita para fontes de dados do tipo 'Lista de registros' ou fontes de dados representadas como uma expressão usando a função FILTER. Também pode ser feita quando a única agregação estiver configurada para um único campo dos registros de agrupamento.  
    * Observe que, apesar de mais de uma agregação ter sido configurada para o campo AmountMST, o campo 'Execução em' ainda indica que esse agrupamento será executado no tempo de execução no banco de dados SQL. Isso porque somente uma agregação é associada ao item do modelo de dados e será usada no tempo de execução para receber dados dessa fonte.  
49. Feche a página.
50. Clique em OK.
51. Na árvore, expanda 'TransactionsGroups'.
52. Na árvore, expanda "TransactionsGroups\aggregated".
53. Na árvore, selecione "TransactionsGroups\aggregated\MaxOfAmountMST".
54. Na árvore, selecione "Totals\Total statistical value(TotalStatisticalValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$StatisticalValueRounded')".
55. Clique em Associar.
56. Na árvore, expanda 'TransactionsGroups'.
57. Na árvore, selecione 'TransactionsGroups'.
58. Clique em Editar.
59. Clique em Editar grupo por.
    * Observe que o campo 'Execução em' indica que esse agrupamento será executado no tempo de execução na memória porque as duas agregações do mesmo campo estão associadas aos itens do modelo de dados.   
60. Na lista, marque ou desmarque todas as linhas.
61. Clique em Excluir.
62. Clique em Sim.
63. Clique em Excluir.
64. Clique em Sim.
65. Clique em Adicionar campo a.
66. Clique em O que agrupar.
67. Na árvore, expanda 'Registro de mercadoria(Intrastat)'.
68. Clique em Salvar.
    * Observe que o campo 'Execução em' indica que esse agrupamento será executado no tempo de execução na memória mesmo que não haja nenhuma agregação definida e a fonte de dados selecionada do tipo 'Registros da tabela' refira-se à mesma tabela ‘Intrastat’. Isso é porque a fonte de dados contém alguns campos calculados que ainda não podem ser traduzidos para o nível do banco de dados SQL.  


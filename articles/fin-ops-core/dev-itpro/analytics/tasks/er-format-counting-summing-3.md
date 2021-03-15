---
title: ER Configurar o formato para fazer contagem e soma (Parte 3 - Usar cálculos para criar a saída)
description: Este tópico descreve como configurar um formato de relatório eletrônico para contar e somar com base nos dados da saída de texto já gerada. (Parte 3)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner, ERDataSourceAddDropDialog, ERExpressionDesignerFormula, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4a69dd28051d8e98643eb95c663525075bed8dec
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092963"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-3---use-computations-to-make-the-output"></a>ER Configurar o formato para fazer contagem e soma (Parte 3 - Usar cálculos para criar a saída)

[!include [banner](../../includes/banner.md)]

As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou de desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para fazer a contagem e soma com base nos dados já gerados do texto de saída. Essas etapas podem ser executadas em qualquer empresa.

Para concluir estas etapas, primeiramente você deve concluir as etapas no procedimento "ER Configurar o formato para fazer a contagem e soma (Parte 2: configurar cálculos)".

Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.


## <a name="configure-this-report-to-use-counting-and-summing-info"></a>Configurar este relatório para usar as informações de contagem e soma
1. Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.
2. Clique em Configurações de relatórios.
3. Na árvore, expanda 'Modelo intrastat'.
4. Na árvore, expanda 'Modelo intrastat\Intrastat (DE)'.
5. Na árvore, selecione "Modelo intrastat\Intrastat (DE)\Intrastat (DE) com contagem e soma".
6. Clique em Designer.
7. Clique na aba Mapeamento.
8. Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.
    * Adicione uma nova fonte de dados para obter a lista de blocos memorizados.  
9. Na árvore, selecione 'Funções\Campo calculado'.
10. No campo Nome, digite '$BlocksList'.
    * $BlocksList  
11. Clique em Editar fórmula.
12. Na árvore, selecione 'Funções de coleta de dados\COLLECTEDLIST'.
13. Clique em Adicionar função.
14. Clique em Adicionar fonte de dados.
15. No campo Fórmula, insira 'COLLECTEDLIST('$BlockName', '.
    * COLLECTEDLIST('$BlockName',  
16. No campo Fórmula, insira 'COLLECTEDLIST('$BlockName', "*")'.
    * COLLECTEDLIST('$BlockName', "*")  
17. Clique em Salvar.
    * O padrão "*" significa que todos os blocos serão incluídos na lista para este registro.  
18. Feche a página.
19. Clique em OK.
20. Clique na guia Formato.
21. Na árvore, selecione 'Intrastat\Dados'.
22. Clique em Adicionar para abrir a caixa de diálogo suspensa.
23. Na árvore, selecione 'Texto\Sequência'.
24. No campo Nome, digite 'Totais por blocos'.
    * Totais por blocos  
25. No campo Caracteres especiais, selecione 'Nova linha - Windows (CR LF)'.
26. Clique em OK.
27. Na árvore, selecione 'Intrastat\Dados\Totais por blocos'.
28. Clique em Adicionar para abrir a caixa de diálogo suspensa.
29. Na árvore, selecione 'Texto\Cadeia de caracteres'.
30. No campo Nome, digite 'Código do bloco'.
    * Código do bloco  
31. Clique em OK.
32. Clique em Adicionar cadeia de caracteres
33. No campo Nome, digite 'Contagem de linhas'.
    * Contagem de linhas  
34. Clique em OK.
35. Clique em Adicionar cadeia de caracteres
36. No campo Nome, digite 'Valor total'.
    * Valor total  
37. Clique em OK.
38. Clique na aba Mapeamento.
39. Na árvore, selecione '$BlocksList'.
40. Clique em Associar.
    * Crie uma linha de resumo para cada bloco memorizado.  
41. Clique na guia Formato.
42. Na árvore, selecione 'Intrastat\Dados\Totais por blocos\Código do bloco'.
43. Clique na aba Mapeamento.
44. Clique em Editar fórmula.
45. No campo Fórmula, insira '"Id do bloco: " & '.
    * "Id do bloco: " &  
46. Na árvore, expanda '$BlocksList'.
47. Na árvore, selecione '$BlocksList\Valor'.
48. Clique em Adicionar fonte de dados.
49. Clique em Salvar.
50. Feche a página.
51. Clique na guia Formato.
52. Na árvore, selecione 'Intrastat\Dados\Totais por blocos\Contagem de linhas'.
53. Clique na aba Mapeamento.
54. Clique em Editar fórmula.
    * Crie saídas para o número de linhas para cada bloco apresentado neste relatório.  
55. No campo Fórmula, insira '"Número de linhas neste bloco: " & '.
    * "Número de linhas neste bloco: " &  
56. No campo Fórmula, insira '"Número de linhas neste bloco: " & TEXT('.
    * "Número de linhas neste bloco: " & TEXT(  
57. Na árvore, selecione 'Funções de coleta de dados\COUNTIFS'.
58. Clique em Adicionar função.
59. Clique em Adicionar fonte de dados.
60. No campo de fórmula, insira '"Número de linhas neste bloco: " & TEXT(COUNTIFS('$BlockName', '.
    * "Número de linhas neste bloco: " & TEXT(COUNTIFS('$BlockName',  
61. Na árvore, expanda '$BlocksList'.
62. Na árvore, selecione '$BlocksList\Valor'.
63. Clique em Adicionar fonte de dados.
64. No campo Fórmula, insira '"Número de linhas neste bloco: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '.
    * "Número de linhas neste bloco: " & TEXT(COUNTIFS ('$BlockName', '$BlocksList'.Value,  
65. Na árvore, selecione '$RecName'.
66. Clique em Adicionar fonte de dados.
67. No campo Fórmula, insira '"Número de linhas neste bloco: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "*"))'.
    * "Número de linhas neste bloco: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "*"))  
68. Clique em Salvar.
69. Feche a página.
70. Clique na guia Formato.
71. Na árvore, selecione 'Intrastat\Dados\Totais por blocos\Valor total'.
72. Clique na aba Mapeamento.
73. Clique em Editar fórmula.
    * Crie saídas que serão o total do valor da fatura para cada bloco apresentado neste relatório.  
74. No campo Fórmula, insira '"Soma do valor faturado: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "*"))'.
    * "Soma do valor faturado: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "*"))  
75. Clique em Salvar.
76. Feche a página.
77. Clique em Salvar.
78. Feche a página.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
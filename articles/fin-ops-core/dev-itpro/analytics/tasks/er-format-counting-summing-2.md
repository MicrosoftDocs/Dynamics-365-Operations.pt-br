---
title: ER Configurar formato para fazer contagem e soma (Parte 2 - Configurar cálculos)
description: Este tópico descreve como configurar um formato de relatório eletrônico para contar e somar com base nos dados da saída de texto já gerada. (Parte 2)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERDataSourceAddDropDialog, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d6eb3d686e8f60de51001deffb4c2460c181a4ab
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565156"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-2---configure-computations"></a>ER Configurar formato para fazer contagem e soma (Parte 2 - Configurar cálculos)

[!include [banner](../../includes/banner.md)]

As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou de desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para fazer a contagem e soma com base nos dados já gerados do texto de saída. Essas etapas podem ser executadas em qualquer empresa.

Para concluir estas etapas, primeiramente você deve concluir as etapas no procedimento "ER Configurar o formato para fazer a contagem e soma (Parte 1: criar formato)".

Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.


## <a name="create-a-format-configuration-to-add-counting-and-summing-details"></a>Criar uma configuração de formato para adicionar detalhes de contagem e soma
1. Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.
2. Clique em Configurações de relatórios.
3. Na árvore, expanda 'Modelo intrastat'.
4. Na árvore, selecione 'Modelo intrastat\Intrastat (DE)'.
    * Suponha que você precise personalizar o formato fornecido pela Microsoft adicionando linhas com os detalhes do resumo no final do relatório intrastat. Você precisa fazer isso derivando nossa própria instância da configuração do intrastat a partir da instância da Microsoft para fazer as modificações.  
5. Clique em Criar configuração para abrir a caixa de diálogo suspensa.
6. No campo Novo, insira 'Derivar de Nome: Intrastat (DE), Microsoft'.
7. No campo Nome, digite "Intrastat (DE) com contagem e soma".
8. Clique em Criar configuração.

## <a name="configure-this-report-to-do-counting-and-summation-based-on-output-details"></a>Configurar este relatório para fazer a contagem e soma baseadas nos detalhes de saída
1. Clique em Designer.
2. Selecione Sim no campo Coletar detalhes de saída.
    * Este sinalizador será ativado no tempo de execução do processo de coleta dos detalhes de saída para gerar o arquivo do intrastat.  
    * Você precisa fazer a contagem das diferentes direções do intrastat, portanto adicione uma enumeração do modelo dedicada à lista de fontes de dados desta configuração de formato.  
3. Clique na aba Mapeamento.
4. Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.
5. Na árvore, selecione 'Modelo de dados\Enumeração'.
6. No campo Nome, digite 'Direção'.
7. No campo Enumeração do modelo, insira ou selecione um valor.
    * Selecione o valor Direção.  
8. Clique em OK.
9. Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.
10. Na árvore, selecione 'Funções\Campo calculado'.
11. No campo Nome, digite '$BlockName'.
12. Clique em Editar fórmula.
13. No campo Fórmula, insira '"bloco"'.
14. Clique em Salvar.
15. Feche a página.
16. Clique em OK.
17. Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.
18. Na árvore, selecione 'Funções\Campo calculado'.
19. No campo Nome, digite '$RecName'.
20. Clique em Editar fórmula.
21. No campo Fórmula, insira '"registro"'.
22. Clique em Salvar.
23. Feche a página.
24. Clique em OK.
25. Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.
26. Na árvore, selecione 'Funções\Campo calculado'.
27. No campo Nome, digite '$InvName'.
28. Clique em Editar fórmula.
29. No campo Fórmula, insira '"InvoicedAmountEUR"'.
30. Clique em Salvar.
31. Feche a página.
32. Clique em OK.
33. Na árvore, selecione 'Intrastat\Dados'.
34. Clique no botão Editar do campo "Nome da chave de dados coletada"
35. Clique em Adicionar fonte de dados.
    * $BlockName  
36. Clique em Salvar.
37. Feche a página.
38. Clique no botão Editar do campo Valor da chave de dados coletada.
39. No campo Fórmula, insira 'IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export")'.
    * IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export")  
40. Clique em Salvar.
41. Feche a página.
    * Conte as linhas da sequência. Os resultados serão usados com o nome "bloco" separadamente para as diferentes direções. O valor "Importar" será usado para todas as transações intrastat de entrada. O valor "Exportar" será usado para todas as transações intrastat de expedição. Considere isso como uma planilha de Excel virtual. Para cada transação, uma linha em que a primeira coluna "bloco" será preenchida com os valores "Importar" e "Exportar" consequentemente.  
42. Na árvore, expanda 'Intrastat\Dados: Sequência'.
43. Na árvore, selecione 'Intrastat\Dados: Sequência\Entradas?'.
44. Clique no botão Editar do campo "Nome da chave de dados coletada".
    * Conte as linhas da sequência. Os resultados serão memorizados usando o nome "registro".  
45. Na árvore, selecione '$RecName'.
46. Clique em Adicionar fonte de dados.
47. Clique em Salvar.
48. Feche a página.
49. Clique no botão Editar do campo "Valor da chave de dados coletada"
50. No campo Fórmula, insira 'Intrastat.CommodityRecord.CommodityCode'.
51. Clique em Salvar.
52. Feche a página.
    * Conte as linhas da sequência. Os resultados serão usados com o nome "registro" separadamente para os diferentes códigos de mercadoria. Considere isso como uma planilha de Excel virtual. Para cada transação, uma linha na primeira coluna "bloco" será preenchida com valores "Importar" e "Exportar" consequentemente e o segundo bloco "registro" será preenchido com o valor do código de mercadoria.  
53. Na árvore, selecione 'Intrastat\Dados: Sequência\Expedições?'.
54. Clique no botão Editar do campo "Nome da chave de dados coletada"
55. Na árvore, selecione '$RecName'.
56. Clique em Adicionar fonte de dados.
57. Clique em Salvar.
58. Feche a página.
59. Clique no botão Editar do campo "Valor da chave de dados coletada".
60. No campo Fórmula, insira 'Intrastat.CommodityRecord.CommodityCode'.
61. Clique em Salvar.
62. Feche a página.
63. Na árvore, expanda 'Intrastat\Dados: Sequência\Expedições: Sequência?'.
64. Na árvore, expanda 'Intrastat\Dados: Sequência\Expedições: Sequência?\Registro =  Intrastat.CommodityRecord'.
65. Clique na guia Formato.
66. Na árvore, selecione 'Intrastat\Dados\Expedições\Registro\Valor da fatura em EUR'.
67. Clique na aba Mapeamento.
68. Clique no botão Editar do campo "Nome da chave de dados coletada",
69. Na árvore, selecione '$InvName'.
70. Clique em Adicionar fonte de dados.
71. Clique em Salvar.
72. Feche a página.
    * Resuma os valores do valor faturado das linhas desta sequência. Os resultados serão usados com o nome "InvoicedAmountEUR" separadamente para as diferentes direções intrastat e os códigos de mercadoria. Considere isso como uma criação virtual em planilha de Excel. Para cada transação, uma linha em que a primeira coluna "bloco" será preenchida com os valores "Importar" e "Exportar" consequentemente. O segundo bloco "registro" será preenchido com o valor do código de mercadoria e a terceira coluna "InvoicedAmountEUR" será preenchida com o valor da fatura.  
73. Na árvore, expanda 'Intrastat\Dados\Entradas?'.
74. Na árvore, expanda 'Intrastat\Dados\Entradas?\Registro =  Intrastat.CommodityRecord'.
75. Clique na guia Formato.
76. Na árvore, selecione 'Intrastat\Dados\Entradas\Registro\Valor da fatura em EUR'.
77. Clique na aba Mapeamento.
78. Clique no botão Editar do campo "Nome da chave de dados coletada",
79. Na árvore, selecione '$InvName'.
80. Clique em Adicionar fonte de dados.
81. Clique em Salvar.
82. Feche a página.
83. Clique em Salvar.
84. Feche a página.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
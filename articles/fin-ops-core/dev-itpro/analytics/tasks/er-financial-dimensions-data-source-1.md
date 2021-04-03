---
title: ER Usar dimensões financeiras como uma fonte de dados (Parte 1 - Criar modelo de dados)
description: Este tópico descreve como configurar um modelo de relatório eletrônico (ER) para usar dimensões financeiras como uma fonte de dados para relatórios ER. (Parte 1)
author: NickSelin
manager: AnnBe
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b5ecae444d80698c03ac050b49894daa1b090f74
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570183"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-1---design-data-model"></a>ER Usar dimensões financeiras como uma fonte de dados (Parte 1 - Criar modelo de dados)

[!include [banner](../../includes/banner.md)]

As etapas a seguir explicam como um administrador do sistema ou desenvolvedor de relatório eletrônico pode configurar um modelo de relatório eletrônico (ER) para usar dimensões financeiras como uma fonte de dados para relatórios ER. Essas etapas podem ser executadas em qualquer empresa.

Para completar essas etapas, você deve primeiro completar as etapas do procedimento "Criar um provedor de configuração e marcá-lo como ativo".


## <a name="create-a-new-data-model"></a>Criar um novo modelo de dados
1. Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.
    * Verifique se o provedor "Litware, Inc." está disponível e marcado como ativo.  
2. Clique em Configurações de relatórios.
3. Clique em Criar configuração para abrir a caixa de diálogo suspensa.
4. No campo Nome, digite "Modelo de amostra de dimensão financeira".
5. Clique em Criar configuração.
6. Clique em Designer.
7. Clique em Novo para abrir a caixa de diálogo suspensa.
8. No campo Nome, digite "Entrada".
9. Clique em Adicionar.
10. Clique em Novo para abrir a caixa de diálogo suspensa.
11. No campo Nome, digite 'Empresa'.
12. Clique em Adicionar.
    * Nós adicionaremos nosso modelo a uma lista do novo registro. Esta lista exporá (para qualquer relatórios ER usando este modelo como a fonte de dados) as configurações de dimensões financeiras selecionadas. Cada dimensão financeira será exibida nesta lista como um registro com os campos apropriados que representam a configuração de dimensão.  
13. Clique em Novo para abrir a caixa de diálogo suspensa.
14. No campo Nome, digite "Configurações de dimensão".
15. No campo Tipo de item, selecione 'Lista de Registro'.
16. Clique em Adicionar.
17. Clique em Novo para abrir a caixa de diálogo suspensa.
18. No campo Nome, digite "Código".
19. No campo Tipo de item, selecione 'String'.
20. Clique em Adicionar.
21. Clique em Novo para abrir a caixa de diálogo suspensa.
22. No campo Nome, digite 'Nome'.
23. Clique em Adicionar.
24. Na árvore, selecione 'Entrada'.
25. Clique em Novo para abrir a caixa de diálogo suspensa.
26. No campo Nome, digite "Diário".
27. No campo Tipo de item, selecione 'Lista de Registro'.
28. Clique em Adicionar.
29. Clique em Novo para abrir a caixa de diálogo suspensa.
30. No campo Nome, digite "Lote".
31. No campo Tipo de item, selecione 'String'.
32. Clique em Adicionar.
33. Clique em Novo para abrir a caixa de diálogo suspensa.
34. No campo Nome, digite 'Transação'.
35. No campo Tipo de item, selecione 'Lista de Registro'.
36. Clique em Adicionar.
37. Clique em Novo para abrir a caixa de diálogo suspensa.
38. No campo Nome, digite "Data".
39. No campo Tipo de item, selecione 'Data'.
40. Clique em Adicionar.
41. Clique em Novo para abrir a caixa de diálogo suspensa.
42. No campo Nome, digite "Débito".
43. No campo Tipo de item, selecione 'Real'.
44. Clique em Adicionar.
45. Clique em Novo para abrir a caixa de diálogo suspensa.
46. No campo Nome, digite 'Crédito'.
47. Clique em Adicionar.
48. Clique em Novo para abrir a caixa de diálogo suspensa.
49. No campo Nome, digite 'Moeda'.
50. No campo Tipo de item, selecione 'String'.
51. Clique em Adicionar.
52. Clique em Novo para abrir a caixa de diálogo suspensa.
53. No campo Nome, digite "Comprovante".
54. Clique em Adicionar.
55. Clique em Novo para abrir a caixa de diálogo suspensa.
56. No campo Nome, digite "Dados de dimensão".
57. No campo Tipo de item, selecione 'Lista de Registro'.
58. Clique em Adicionar.
    * Nós adicionamos nosso modelo a uma lista do novo registro. Esta lista exporá (para qualquer ER relatórios usando este modelo como a fonte de dados) os valores de dimensões financeiras selecionados. Cada dimensão financeira será exibida nesta lista como um registro com os campos apropriados que representam os valores de dimensão. O nome de dimensões será apresentado também neste registro pois um campo a ser usado, se necessário, para fins de seleção.  
59. Clique em Novo para abrir a caixa de diálogo suspensa.
60. No campo Nome, digite "Código".
61. No campo Tipo de item, selecione 'String'.
62. Clique em Adicionar.
63. Clique em Novo para abrir a caixa de diálogo suspensa.
64. No campo Nome, digite 'Descrição'.
65. Clique em Adicionar.
66. Clique em Novo para abrir a caixa de diálogo suspensa.
67. No campo Nome, digite 'Nome'.
68. Clique em Adicionar.
69. Clique em Salvar.
70. Feche a página.

![Página do designer de modelo de dados de ER](../media/er-financial-dimensions-guides-data-model.png)



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
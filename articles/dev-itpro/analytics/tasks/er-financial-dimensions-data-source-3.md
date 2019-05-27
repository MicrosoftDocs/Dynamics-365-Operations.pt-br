---
title: 'ER Usar dimensões financeiras como uma fonte de dados (Parte 3: Criar o relatório)'
description: As etapas a seguir explicam como um usuário atribuído ao administrador do sistema ou função do desenvolvedor de relatório eletrônico pode configurar um modelo de relatório eletrônico (ER) para usar dimensões financeiras como uma fonte de dados para relatórios ER.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 45096a728ad6f9e331b53b4e12ca0ff9317a3939
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1544716"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-3-design-the-report"></a>O ER usa dimensões financeiras como uma fonte de dados (parte 3: criar o relatório)

[!include [task guide banner](../../includes/task-guide-banner.md)]

As etapas a seguir explicam como um usuário atribuído ao administrador do sistema ou função do desenvolvedor de relatório eletrônico pode configurar um modelo de relatório eletrônico (ER) para usar dimensões financeiras como uma fonte de dados para relatórios ER. Essas etapas podem ser executadas em qualquer empresa.

Para completar essas etapas, primeiro você deve concluir as etapas “dimensões financeiras de uso ER como uma fonte de dados do procedimento (parte 2: mapeamento de modelo).”


## <a name="design-a-report-to-present-financial-dimensions"></a>Criar um relatório para apresentar dimensões financeiras
1. Vá para Administração da organização > Relatório eletrônico > Configurações.
2. Na árvore, selecione "Modelo de amostra de dimensão financeira".
3. Clique em Criar configuração para abrir a caixa de diálogo suspensa.
4. No campo Novo, insira 'Formato baseado no modelo de dados modelo de amostra de dimensões financeiras'.
    * Use o modelo criado antecipado como a fonte de dados de seu novo relatório.  
5. No campo Nome, digite "Relatório de jornal razão".
6. No campo Definição de modelo de dados, selecione Entrada.
7. Clique em Criar configuração.
8. Clique em Designer.
9. Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.
10. Na árvore, selecione 'XML\Elemento'.
11. No campo Nome, digite "Raiz".
12. Clique em OK.
13. Clique em Adicionar para abrir a caixa de diálogo suspensa.
14. Na árvore, selecione 'XML\Atributo'.
15. No campo Nome, digite 'Empresa'.
16. Clique em OK.
17. Clique em Adicionar para abrir a caixa de diálogo suspensa.
18. Na árvore, selecione 'XML\Elemento'.
19. No campo Nome, digite "Diário".
20. Clique em OK.
21. Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML".
22. Clique em Adicionar para abrir a caixa de diálogo suspensa.
23. Na árvore, selecione 'XML\Atributo'.
24. No campo Nome, digite "Lote".
25. Clique em OK.
26. Clique em Adicionar para abrir a caixa de diálogo suspensa.
27. Na árvore, selecione 'XML\Elemento'.
28. No campo Nome, digite 'Transação'.
29. Clique em OK.
30. Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML".
31. Clique em Adicionar para abrir a caixa de diálogo suspensa.
32. Na árvore, selecione 'XML\Atributo'.
33. No campo Nome, digite "Comprovante".
34. Clique em OK.
35. Clique em Adicionar atributo.
36. No campo Nome, digite "Data".
37. Clique em OK.
38. Clique em Adicionar atributo.
39. No campo Nome, digite 'Moeda'.
40. Clique em OK.
41. Clique em Adicionar atributo.
42. No campo Nome, digite "Dt".
43. Clique em OK.
44. Clique em Adicionar atributo.
45. No campo Nome, digite "Ct".
46. Clique em OK.
47. Clique em Adicionar para abrir a caixa de diálogo suspensa.
48. Na árvore, selecione 'XML\Elemento'.
49. No campo Nome, digite "Dimensões".
50. Clique em OK.
51. Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dimensões: Elemento XML".
52. Clique em Adicionar para abrir a caixa de diálogo suspensa.
53. Na árvore, selecione 'XML\Atributo'.
54. No campo Nome, digite "Código".
55. Clique em OK.
56. Clique em Adicionar atributo.
57. No campo Nome, digite "Valor".
58. Clique em OK.
59. Clique em Adicionar atributo.
60. No campo Nome, digite "Desc".
61. Clique em OK.

## <a name="map-report-elements-to-data-sources"></a>Mapear elementos de relatório para fontes de dados
1. Clique na aba Mapeamento.
2. Na árvore, expanda "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados".
3. Na árvore, expanda "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros".
4. Na árvore, expanda "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros".
5. Na árvore, expanda "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Dados de dimensões: Lista de registros".
6. Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dimensões: Elemento XML\Desc: Atributo XML".
7. Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Dados de dimensões: Lista de registros\Descrição: Cadeia de caracteres".
8. Clique em Associar.
9. Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dimensões: Elemento XML\Valor: Atributo XML".
10. Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Dados de dimensões: Lista de registros\Código: Cadeia de caracteres".
11. Clique em Associar.
12. Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dimensões: Elemento XML\Código: Atributo XML".
13. Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Dados de dimensões: Lista de registros\Nome: Cadeia de caracteres".
14. Clique em Associar.
15. Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Dados de dimensões: Lista de registros".
16. Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dimensões: Elemento XML".
17. Clique em Associar.
18. Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Ct: Atributo XML".
19. Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Crédito: Real".
20. Clique em Associar.
21. Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dt: Atributo XML".
22. Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Débito: Real".
23. Clique em Associar.
24. Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Moeda: Atributo XML".
25. Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Moeda: Cadeia de caracteres".
26. Clique em Associar.
27. Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Data: Atributo XML".
28. Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Data: Data".
29. Clique em Associar.
30. Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Comprovante: Atributo XML".
31. Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Comprovante: Cadeia de caracteres".
32. Clique em Associar.
33. Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML".
34. Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros".
35. Clique em Associar.
36. Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Lote: Atributo XML".
37. Na árvore, selecione 'modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Lote: Sequência de caracteres'.
38. Clique em Associar.
39. Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML".
40. Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros".
41. Clique em Associar.
42. Na árvore, selecione "Raiz: Elemento XML\Empresa: Atributo XML".
43. Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Empresa: Cadeia de caracteres".
44. Clique em Associar.
45. Clique em Salvar.
46. Feche a página.


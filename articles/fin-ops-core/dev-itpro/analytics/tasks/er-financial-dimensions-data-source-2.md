---
title: ER Usar dimensões financeiras como uma fonte de dados (Parte 2 - Mapeamento de modelo)
description: As etapas a seguir explicam como um usuário atribuído ao administrador do sistema ou função do desenvolvedor de relatório eletrônico pode configurar um modelo de relatório eletrônico (ER) para usar dimensões financeiras como uma fonte de dados para relatórios ER.
author: NickSelin
manager: AnnBe
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3aabd622d15917d7e4549d0b0679aa20231c5815
ms.sourcegitcommit: d9125c20b21459076e4fd92fd9ebfe2e53a0431b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "3406511"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-2---model-mapping"></a>ER Usar dimensões financeiras como uma fonte de dados (Parte 2 - Mapeamento de modelo)

[!include [banner](../../includes/banner.md)]

As etapas a seguir explicam como um usuário atribuído ao administrador do sistema ou função do desenvolvedor de relatório eletrônico pode configurar um modelo de relatório eletrônico (ER) para usar dimensões financeiras como uma fonte de dados para relatórios ER. Essas etapas podem ser executadas em qualquer empresa.

Para concluir estas etapas, primeiramente conclua as etapas no procedimento "ER Usar dimensões financeiras como fonte de dados (Parte 1: projetar modelo de dados".


## <a name="add-required-data-sources-to-model-mapping"></a>Adicionar fontes de dados necessários para criar mapeamento
1. Vá para Administração da organização > Relatório eletrônico > Configurações.
2. Na árvore, selecione "Modelo de amostra de dimensão financeira".
3. Clique em Designer.
4. Clique em Mapear modelo para fonte de dados.
5. Clique em Novo.
6. No campo Definição, selecione Entrada.
7. No campo Nome, digite "Mapeamento de dados de dimensão".
8. No campo Descrição, digite "Mapeamento de dados de dimensão".
9. Clique em Salvar.
10. Clique em Designer.
11. Na árvore, selecione 'Dynamics 365 for Operations\Tabela'.
12. Clique em Adicionar raiz.
13. No campo Nome, digite 'Empresa'.
14. No campo Tabela, digite 'CompanyInfo'.
15. Clique em OK.
16. Na árvore, selecione "Detalhes de funções\dimensões financeiras".
17. Clique em Adicionar raiz.
    * Essa fonte de dados especifica como o escopo de dimensões financeiras será definido para todos os relatórios que usa esse método como uma fonte de dados.  
18. No campo Nome, digite um valor.
19. Selecione Sim no campo Pedir dimensões.
    * Selecione Sim para permitir que o usuário seleciona dimensões em tempo de execução na caixa de diálogo formulário. Se selecionado Não, as dimensões financeiras da instância atual serão usadas por padrão.  
20. No campo de seleção Dimensões financeiras, selecione "Entidade legal".
    * Selecionar todos para permitir que o usuário seleciona dimensões de desejo para a instância atual no campo de pesquisa.  Selecionar Entidade legal para permitir que o usuário seleciona dimensões para a empresa no campo de pesquisa.  Selecione a dimensão para permitir que o usuário seleciona dimensões com um único conjunto de dimensões.  
21. Selecione Sim no campo Pedir conta principal.
    * Defina "Solicitar conta principal" como Sim para permitir que usuários selecionem a contra principal como parte da lista de dimensões.   Defina como Não. A contra principal não será incluída na lista de dimensões, e a opção "A conta principal é obrigatória?" será habilitada. Se "A conta principal é obrigatória?" for definida como Sim, inclua a contra principal na lista de dimensões, independentemente da seleção do usuário.  
22. Clique em OK.
![Página de designer de mapeamento de modelo de ER](../media/er-financial-dimensions-guides-model-mapping1.png)
23. Na árvore, selecione 'Dynamics 365 for Operations\Registros da tabela'.
24. Clique em Adicionar raiz.
25. No campo Nome, digite "LedgerJournal".
26. Selecione Sim no campo Pedir consulta.
27. No campo Tabela, digite 'LedgerJournalTable'.
28. Clique em OK.
![Página de designer de mapeamento de modelo de ER](../media/er-financial-dimensions-guides-model-mapping2.png)

## <a name="map-data-model-elements-to-added-data-sources"></a>Mapear elementos de modelo de dados para adicionar fontes de dados
1. Na árvore, expanda 'Diário'.
2. Na árvore, expanda 'Diário\Transação'.
3. Na árvore, expanda 'Diário\Transação\Dados de dimensões'.
4. Na árvore, expandir "Configurações de dimensões".
5. Na árvore, expandir "LedgerJournal".
6. Na árvore, expanda "LedgerJournal\<Relações".
7. Na árvore, expanda "LedgerJournal\<Relações\LedgerJournalTrans".
8. Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Comprovante".
9. Na árvore, selecione 'Diário\Transações\Comprovante'.
10. Clique em Associar.
11. Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)".
    * Lembre-se que para qualquer referência às dimensões financeiras a que é definido, por exemplo, LedgerDimension, de item correspondente fonte de dados disponível (LedgerDimension.Dimension). Este item de fonte de dados oferece as dimensões financeiras das dimensões definidas como a lista do registro.  
12. Na árvore, expanda "LedgerJournal\<Relações\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)".
13. Na árvore, expanda "LedgerJournal\<Relações\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Conta principal e dimensões".
14. Na árvore, expanda "LedgerJournal\<Relações\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Conta principal e dimensões\Valor".
15. Na árvore, expanda "LedgerJournal\<Relações\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Conta principal e dimensões\Definição".
16. Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Conta principal e dimensões\Definição\Nome".
17. Na árvore, selecione 'Diário\Transação\Dados de dimensões\Nome'.
18. Clique em Associar.
19. Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Conta principal e dimensões\Valor\Descrição".
20. Na árvore, selecione 'Diário\Transação\Dados de dimensões\Descrição'.
21. Clique em Associar.
22. Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Conta principal e dimensões\Valor\Código".
23. Na árvore, selecione 'Diário\Transação\Dados de dimensões\Código'.
24. Clique em Associar.
25. Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Conta principal e dimensões".
26. Na árvore, selecione 'Diário\Transação\Dados de dimensões'.
27. Clique em Associar.
![Página de designer de mapeamento de modelo de ER](../media/er-financial-dimensions-guides-model-mapping3.png)
28. Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Débito(AmountCurDebit)".
29. Na árvore, selecione 'Diário\Transações\Débito'.
30. Clique em Associar.
31. Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Data(TransDate)".
32. Na árvore, selecione 'Diário\Transações\Data'.
33. Clique em Associar.
34. Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Moeda(CurrencyCode)".
35. Na árvore, selecione 'Diário\Transações\Moeda'.
36. Clique em Associar.
37. Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Crédito(AmountCurCredit)".
38. Na árvore, selecione 'Diário\Transações\Crédito'.
39. Clique em Associar.
40. Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans".
41. Na árvore, selecione 'Diário\Transações'.
42. Clique em Associar.
43. Na árvore, selecione 'LedgerJournal\Número do lote do diário(JournalNum)'.
44. Na árvore, selecione 'Diário\Lote'.
45. Clique em Associar.
46. Na árvore, selecione 'LedgerJournal'.
47. Na árvore, selecione 'Diário'.
48. Clique em Associar.
49. Na árvore, expanda 'Dimensões'.
50. Na árvore, expanda 'Dimensões\Conta principal e dimensões'.
51. Na árvore, expanda “dimensões \ conta principal e dimensões\Definição.
52. Na árvore, selecione 'Dimensões\Conta principal e dimensões\Definição\Nome'.
53. Na árvore, selecione "Configurações de dimensões\Código".
54. Clique em Associar.
55. Na árvore, selecione 'Dimensões\Conta principal e dimensões\Definição\Nome\Nome da coluna de relatório'.
56. Na árvore, selecione "Configurações de dimensões\Nome".
57. Clique em Associar.
58. Na árvore, selecione 'Dimensões\Conta principal e dimensões'.
59. Na árvore, selecione "Configurações de dimensões".
60. Clique em Associar.
61. Na árvore, selecione 'Empresa'.
62. Clique em Editar.
63. No campo expressionAsStringText, insira 'Company.'find()'.'name()''.
    * Empresa.'find()'.'name()'  
64. Clique em Salvar.
![Página de designer de mapeamento de modelo de ER](../media/er-financial-dimensions-guides-model-mapping4.png)
65. Feche a página.
66. Clique em Salvar.
67. Feche a página.

## <a name="complete-this-draft-models-version"></a>Conclua esta versão do modelo de rascunho
1. Feche a página.
2. Feche a página.
3. Clique em Alterar status.
4. Clique em Concluir.
5. Clique em OK.
![Página de designer de mapeamento de modelo de ER](../media/er-financial-dimensions-guides-model-mapping5.png)

---
title: Criar uma hierarquia de relatórios da organização
description: Use este procedimento para criar uma hierarquia do relatório da organização.
author: ShylaThompson
manager: AnnBe
ms.date: 10/30/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5684c710b8e167a4a39f106eb3c0fd77e3011dbd
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2187834"
---
# <a name="create-an-organization-report-hierarchy"></a>Criar uma hierarquia de relatórios da organização

[!include [task guide banner](../../includes/task-guide-banner.md)]

Use este procedimento para criar uma hierarquia do relatório da organização. A finalidade desta gravação é guiá-lo pela hierarquia de dimensão, de forma que você possa continuar, enquanto toda a estrutura de relatório de organização é criada. Esta gravação usa os dados da empresa de demonstração USP2.

1. Vá para Contabilização de custos > Dimensões > Hierarquias de dimensões.
2. Clique em Novo.
3. No campo HierarchyTypeComboBox, selecione 'Hierarquia de classificação de dimensões'.
    * Selecione Hierarquia de classificação de dimensões. O tipo de Hierarquia de classificação de dimensões é usado para definir regras e para fins de relatório. Ele oferece suporte a todas as dimensões, como objetos de custos, elementos de custo, dimensões estatísticas.  
4. Clique em Criar.
5. No campo Nome de hierarquia de dimensões, digite 'Organização USP2'.
6. No campo Dimensão, insira ou selecione um valor.
    * Selecione Centros de custo.  
7. Clique em Salvar.
8. Clique em Exibir hierarquia.
9. Clique em Novo.
10. No campo Nome do nó, digite 'CEO'.
11. Clique em Salvar.
12. Clique em Novo.
13. No campo Nome do nó, digite 'Centros de custos de CEO'.
14. Clique em Salvar.
15. Clique em Novo.
16. No campo Nome do nó, digite "Região Leste".
17. Clique em Salvar.
18. Clique em Novo.
19. Na lista, marque a linha selecionada.
20. No campo Membro da dimensão de origem, insira ou selecione um valor.
    * Selecione o membro da dimensão que corresponde ao nó.  
21. Clique em Salvar.
22. Na árvore, selecione 'Organização USP2\CEO\Centros de custos de CEO'.
23. Clique em Novo.
24. No campo Nome do nó, digite "Região Oeste".
25. Clique em Salvar.
26. Clique em Novo.
27. Na lista, marque a linha selecionada.
28. No campo Membro da dimensão de origem, insira ou selecione um valor.
    * Selecione o membro da dimensão que corresponde ao nó.  
29. Clique em Salvar.
30. Na árvore, selecione 'Organização USP2\CEO'.
31. Clique em Novo.
32. No campo Nome do nó, digite 'Centros de custos de CFO'.
33. Clique em Salvar.
34. Clique em Novo.
35. No campo Nome do nó, digite "Campanha de Marketing".
36. No campo Nome do nó, digite "Campanha de Marketing".
37. Clique em Salvar.
38. Clique em Novo.
39. Na lista, marque a linha selecionada.
40. No campo Membro da dimensão de origem, insira ou selecione um valor.
    * Selecione o membro da dimensão que corresponde ao nó.  
41. Clique em Salvar.
42. Na árvore, selecione 'Centros de custos da organização USP2\CEO\CFO'.
43. Clique em Novo.
44. No campo Nome do nó, digite "Feiras profissionais".
45. Clique em Salvar.
46. Clique em Novo.
47. Na lista, marque a linha selecionada.
48. No campo Membro da dimensão de origem, insira ou selecione um valor.
    * Selecione o membro da dimensão que corresponde ao nó.  
49. Clique em Salvar.
50. Na árvore, selecione 'Organização USP2\CEO'.
51. No campo Nome do nó, digite 'Centros de custos de CIO'.
52. Clique em Salvar.
53. Clique em Novo.
54. No campo Nome do nó, digite 'Membro da dimensão de origem'.
55. Clique em Salvar.
56. Clique em Novo.
57. Na lista, marque a linha selecionada.
58. No campo Membro da dimensão de origem, insira ou selecione um valor.
    * Selecione o membro da dimensão que corresponde ao nó.  
59. Clique em Salvar.


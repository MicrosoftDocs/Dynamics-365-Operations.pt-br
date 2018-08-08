--- 
title: "Criar e atribuir uma política de comportamento de custos para uma unidade de controle de custos"
description: "O comportamento de custo é a classificação de custos como fixo ou variável."
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 392cb83ceb8612a2e73cc54bb2d8d40c62a6b7b6
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="create-and-assign-a-cost-behavior-policy-to-a-cost-control-unit"></a>Criar e atribuir uma política de comportamento de custos para uma unidade de controle de custos

[!include [task guide banner](../../includes/task-guide-banner.md)]

O comportamento de custo é a classificação de custos como fixo ou variável. Uma política e as regras correspondentes precisam ser atribuídas a uma unidade de controle de custo para que a política se torne efetiva. Use esse procedimento para criar uma política e depois atribua a política a uma unidade de controle de custo.


## <a name="create-a-cost-behavior-hierarchy"></a>Criar uma hierarquia de comportamento de custo
1. Vá para Contabilização de custos > Dimensões > Hierarquias de dimensões.
2. Clique em Novo.
3. Clique em Criar.
4. No campo Nome de hierarquia de dimensões, digite "Hierarquia de comportamento de custo".
5. No campo Dimensão, insira ou selecione um valor.
    * Selecione Elementos de custo.  
6. Clique em Salvar.
7. Clique em Exibir hierarquia.
8. Clique em Novo.
9. No campo Nome do nó, digite um valor.
    * Insira Custo fixo.  
10. Na árvore, selecione "Hierarquia de comportamento de custo".
11. Clique em Novo.
12. No campo Nome do nó, digite um valor.
    * Insira Custo variável.  
13. Clique em Salvar.
14. Na árvore, selecione 'Hierarquia de comportamento de custo\Custo fixo'.
15. Clique em Novo.
16. Na lista, marque a linha selecionada.
17. No campo Membro da dimensão de origem, insira ou selecione um valor.
    * O intervalo de membros de dimensão pode conter intervalos, mas os membros não serão sobrepostos.  
18. No campo Membro da dimensão de destino, insira ou selecione um valor.
    * O intervalo de membros de dimensão pode conter intervalos, mas os membros não serão sobrepostos.  
19. Na árvore, selecione 'Hierarquia de comportamento de custo\Custo variável'.
20. Clique em Novo.
21. Na lista, marque a linha selecionada.
22. No campo Membro da dimensão de origem, insira ou selecione um valor.
    * O intervalo de membros de dimensão pode conter intervalos, mas os membros não serão sobrepostos.  
23. No campo Membro da dimensão de destino, insira ou selecione um valor.
    * O intervalo de membros de dimensão pode conter intervalos, mas os membros não serão sobrepostos.  
24. Clique em Salvar.

## <a name="create-the-policy-and-rules"></a>Criar a política e as regras
1. Vá para Contabilização de custos > Políticas > Políticas de comportamento de custo.
2. Clique em Novo.
3. No campo Nome da política, digite um valor.
4. No campo Hierarquia da dimensão de elemento de custo, insira ou selecione um valor.
    * Selecione a hierarquia da política que acabou de criar.  
5. No campo Hierarquia da dimensão de objeto de custo, insira ou selecione um valor.
    * Selecione Organização.  
6. Clique em Salvar.
7. Clique em Novo.
8. Na lista, marque a linha selecionada.
9. No campo Nó da hierarquia da dimensão de elemento de custo, insira ou selecione um valor.
    * Expanda a hierarquia para selecionar Custo variável.  
10. No campo Nó da hierarquia da dimensão de objeto de custo, insira ou selecione um valor.
    * Por padrão, a porcentagem variável é 100%.  
11. Clique em Atribuições de políticas para unidade de controle de custo.
12. Clique em Novo.
13. Na lista, marque a linha selecionada.
14. No campo Válido a partir da data contábil, insira uma data.
    * As regras são efetivas de acordo com a data, e o usuário ou o sistema podem fazer com que uma regra expire se uma versão mais recente for criada.  
15. No campo Unidade de controle de custo, insira ou selecione um valor.
16. Clique em Salvar.



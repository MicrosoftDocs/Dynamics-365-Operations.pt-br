---
title: Criar e atribuir uma política de comportamento de custos para uma unidade de controle de custos
description: O comportamento de custo é a classificação de custos como fixo ou variável.
author: twheeloc
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CAMCostBehaviorRule
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 653bfb69c4ca118c700755cb95a6b349d2c6bbad
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2022
ms.locfileid: "8735132"
---
# <a name="create-and-assign-a-cost-behavior-policy-to-a-cost-control-unit"></a>Criar e atribuir uma política de comportamento de custos para uma unidade de controle de custos

[!include [banner](../../includes/banner.md)]

O comportamento de custo é a classificação de custos como fixo ou variável. Uma política e as regras correspondentes precisam ser atribuídas a uma unidade de controle de custo para que a política se torne efetiva. Use esse procedimento para criar uma política e depois atribua a política a uma unidade de controle de custo.


## <a name="create-a-cost-behavior-hierarchy"></a>Criar uma hierarquia de comportamento de custo
1. Acesse **Contabilização de custos > Dimensões > Hierarquias de dimensões**.
2. Clique em **Novo**.
3. Clique em **Criar**.
4. No campo **Nome de hierarquia de dimensões**, digite "Hierarquia de comportamento de custo".
5. No campo **Dimensão**, insira ou selecione um valor.
    * Selecione Elementos de custo.  
6. Clique em **Salvar**.
7. Clique em **Exibir hierarquia**.
8. Clique em **Novo**.
9. No campo **Nome do nó**, digite um valor.
    * Insira Custo fixo.  
10. Na árvore, selecione "Hierarquia de comportamento de custo".
11. Clique em **Novo**.
12. No campo **Nome do nó**, digite um valor.
    * Insira Custo variável.  
13. Clique em **Salvar**.
14. Na árvore, selecione 'Hierarquia de comportamento de custo\Custo fixo'.
15. Clique em **Novo**.
16. Na lista, marque a linha selecionada.
17. No campo **Membro da dimensão de origem**, insira ou selecione um valor.
    * O intervalo de membros de dimensão pode conter intervalos, mas os membros não serão sobrepostos.  
18. No campo **Membro da dimensão de destino**, insira ou selecione um valor.
    * O intervalo de membros de dimensão pode conter intervalos, mas os membros não serão sobrepostos.  
19. Na árvore, selecione 'Hierarquia de comportamento de custo\Custo variável'.
20. Clique em **Novo**.
21. Na lista, marque a linha selecionada.
22. No campo **Membro da dimensão de origem**, insira ou selecione um valor.
    * O intervalo de membros de dimensão pode conter intervalos, mas os membros não serão sobrepostos.  
23. No campo **Membro da dimensão de destino**, insira ou selecione um valor.
    * O intervalo de membros de dimensão pode conter intervalos, mas os membros não serão sobrepostos.  
24. Clique em **Salvar**.

## <a name="create-the-policy-and-rules"></a>Criar a política e as regras
1. Acesse **Contabilização de custos > Políticas > Políticas de comportamento de custo**.
2. Clique em **Novo**.
3. No campo **Nome da política**, digite um valor.
4. No campo **Hierarquia da dimensão de elemento de custo**, insira ou selecione um valor.
    * Selecione a hierarquia da política que acabou de criar.  
5. No campo **Hierarquia da dimensão de objeto de custo**, insira ou selecione um valor.
    * Selecione Organização.  
6. Clique em **Salvar**.
7. Clique em **Novo**.
8. Na lista, marque a linha selecionada.
9. No campo **Nó da hierarquia da dimensão de elemento de custo**, insira ou selecione um valor.
    * Expanda a hierarquia para selecionar Custo variável.  
10. No campo **Nó da hierarquia da dimensão de objeto de custo**, insira ou selecione um valor.
    * Por padrão, a porcentagem variável é 100%.  
11. Clique em **Atribuições de políticas para unidade de controle de custo**.
12. Clique em **Novo**.
13. Na lista, marque a linha selecionada.
14. No campo **Válido a partir da data contábil**, insira uma data.
    * As regras são efetivas de acordo com a data, e o usuário ou o sistema podem fazer com que uma regra expire se uma versão mais recente for criada.  
15. No campo **Unidade de controle de custo**, insira ou selecione um valor.
16. Clique em **Salvar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

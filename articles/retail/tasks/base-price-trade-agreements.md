--- 
title: " Preço base e contratos comerciais"
description: "Este procedimento orienta na criação de contratos comerciais de preço de venda específicos para o canal."
author: josaw1
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 6fe49a5c871a175612223e0354e7880f17108044
ms.contentlocale: pt-br
ms.lasthandoff: 07/28/2017

---
# <a name="base-price-and-trade-agreements"></a> Preço base e contratos comerciais

[!include[task guide banner](../includes/task-guide-banner.md)]

Este procedimento orienta na criação de contratos comerciais de preço de venda específicos para o canal. Este procedimento usa a empresa de dados de demonstração USRT.

1. Vá para Varejo e comércio > Preços e descontos > Grupos de preços > Todos os grupos de preços.
    * Os grupos de preço são como os contratos comerciais são atribuídos a canais específicos. O uso de grupos de preços para atribuir contratos comerciais a um canal habilita a definição de preços específica para o canal.  
2. Clique em Novo.
3. No campo Grupos de preços, digite um valor.
4. No campo Nome, digite um valor.
5. Clique em Salvar.
6. Feche a página.
7. Vá para Varejo e comércio > Canais > Lojas de varejo > Todas as lojas de varejo.
8. Na lista, selecione 'Nova York'.
9. No Painel de Ação, clique em Loja.
10. Clique em Grupos de preços.
11. Clique em Novo.
12. No campo Grupos de preços, clique no botão suspenso para abrir a pesquisa.
13. Na lista, localize e selecione o PDV desejado.
14. Clique em Salvar.
15. Feche a página.
16. Feche a página.
17. Vá para Varejo e comércio > Produtos e categorias > Produtos liberados por categoria.
18. Na lista, clique no link na linha selecionada.
19. Clique em Editar.
20. Ative/desative a expansão da seção Vender.
21. No campo Preço, insira um número.
    * Esse preço será usado se nenhum contrato comercial aplicável for encontrado.  
22. Clique em Salvar.
23. No Painel de Ação, clique em Vender.
24. Criar em Criar contratos comerciais.
25. Clique em Novo.
26. No campo Nome, clique no botão suspenso para abrir a pesquisa.
27. Na lista, selecione 'Varejo'.
    * Nos dados de demonstração, o nome do diário 'Varejo' tem a relação de 'Preço (vendas)' padrão. Isso significa que todas as novas linhas criadas assumirão como padrão os contratos comerciais de preço de venda.  
28. Clique em Linhas.
29. No campo Código da conta, selecione 'Grupo'.
30. No campo Seleção de conta, clique no botão suspenso para abrir a pesquisa.
31. Na lista, localize e selecione o PDV desejado.
    * Isso completará o link do canal com o grupo de preços com o contrato comercial.  
32. No campo Relação de item, digite um valor.
33. No campo Valor em moeda, insira um número.
34. Marque ou desmarque a caixa de seleção Localizar próximo.
    * Quando Localizar próximo estiver definido como 'Sim', o mecanismo de definição de preços continuará a pesquisar por contratos comerciais aplicáveis com um preço de venda mais baixo. Quando Localizar próximo estiver definido como 'Não', o mecanismo de definição de preços para de pesquisar e usa o contrato comercial.  
35. Clique em Lançar.
36. Clique em OK.
37. Feche a página.
38. No Painel de Ação, clique em Vender.
39. Clique em Preço de venda.


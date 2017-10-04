--- 
title: "Criar matérias-primas (apenas fevereiro de 2016)"
description: Esta tarefa tem como foco criar os componentes de produtos finalizados e semifinalizados.
author: YuyuScheller
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: a20a2c720af7c981cced231c0f863a1bd8283f2c
ms.contentlocale: pt-br
ms.lasthandoff: 07/28/2017

---
# <a name="create-raw-materials-february-2016-only"></a>Criar matérias-primas (apenas fevereiro de 2016)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Esta tarefa tem como foco criar os componentes de produtos finalizados e semifinalizados. Trata-se da terceira tarefa na série de cálculo BOM. A empresa de dados demo usada para criar esta tarefa é USMF.


## <a name="create-the-first-material"></a>Criar o primeiro material
1. Vá para Gerenciamento de informações do produto > Produtos > Produtos liberados.
2. Clique em Novo.
3. No campo Número do produto, digite um valor.
    * Neste exemplo, insira ITEM_A.  
4. No campo Grupo de modelos do item, insira ou selecione um valor.
    * Selecione STD. STD significa "custo padrão" e é o modelo mais comumente utilizado ao se trabalhar com cálculos de custo.  
5. No campo Grupo de itens, insira ou selecione um valor.
    * Por exemplo, selecione Áudio. Isso não tem impacto sobre os cálculos de custo.  
6. No campo Grupo de dimensões de armazenamento, insira ou selecione um valor.
    * Selecione SiteWH. Apenas Site e Depósito serão usados na demonstração.  
7. No campo Grupo de dimensões de rastreamento, insira ou selecione um valor.
    * A dimensão de rastreamento não será usada neste exemplo. Selecione Nenhuma.  
8. Clique em OK.
9. No Painel de Ação, clique em Gerenciar estoque.
10. Clique em Configurações de ordem padrão.
11. No campo Site de compra, insira ou selecione um valor.
    * Neste exemplo, selecione Site 1.  
12. No campo Site de estoque, insira ou selecione um valor.
    * Neste exemplo, selecione Site 1.  
13. No campo Site de vendas, insira ou selecione um valor.
    * Neste exemplo, selecione Site 1.  
14. Feche a página.
15. Feche a página.
16. Na lista, clique no link na linha selecionada.
    * Clique em ITEM_A.  
17. Expanda a seção Gerenciar custos.
18. No campo Grupo de custos, digite um valor.
    * Neste exemplo, digite M2.  
19. No Painel de Ação, clique em Gerenciar custos.
20. Clique em Preço de item.
21. Clique em Novo.
22. No campo Versão, insira ou selecione um valor.
    * Neste exemplo, selecione 10, que é o tipo de custo Custo padrão.  
23. No campo Local, insira ou selecione um valor.
    * Neste exemplo, selecione Site 1.  
24. No campo Preço, insira um número.
    * Neste exemplo, digite 10.  
25. Clique em Salvar.
26. Clique em Ativar preço(s) pendente(s).
27. Feche a página.
28. Feche a página.

## <a name="create-the-second-material"></a>Criar o segundo material
1. Clique em Novo.
2. No campo Número do produto, digite um valor.
    * Neste exemplo, digite ITEM_B.  
3. No campo Grupo de modelos do item, insira ou selecione um valor.
    * Selecione STD. STD significa "custo padrão" e é o modelo mais comumente utilizado ao se trabalhar com cálculos de custo.  
4. No campo Grupo de itens, insira ou selecione um valor.
    * Por exemplo, selecione Áudio. Isso não tem impacto sobre os cálculos de custo.  
5. No campo Grupo de dimensões de armazenamento, insira ou selecione um valor.
    * Selecione SiteWH. Apenas Site e Depósito serão usados neste exemplo.  
6. No campo Grupo de dimensões de rastreamento, insira ou selecione um valor.
    * A dimensão de rastreamento não será usada neste exemplo. Selecione Nenhuma.  
7. Clique em OK.
8. No Painel de Ação, clique em Gerenciar estoque.
9. Clique em Configurações de ordem padrão.
10. No campo Site de compra, insira ou selecione um valor.
    * Neste exemplo, selecione Site 1.  
11. No campo Site de estoque, insira ou selecione um valor.
    * Neste exemplo, selecione Site 1.  
12. No campo Site de vendas, insira ou selecione um valor.
    * Neste exemplo, selecione Site 1.  
13. Feche a página.
14. Feche a página.
15. Na lista, clique no link na linha selecionada.
    * Clique em ITEM_B.  
16. Expanda a seção Gerenciar custos.
17. No campo Grupo de custos, digite um valor.
    * Neste exemplo, digite M2.  
18. No Painel de Ação, clique em Gerenciar custos.
19. Clique em Preço de item.
20. Clique em Novo.
21. No campo Versão, insira ou selecione um valor.
    * Neste exemplo, selecione 10. Este é o tipo de custo Custo padrão.  
22. No campo Local, insira ou selecione um valor.
    * Neste exemplo, selecione Site 1.  
23. No campo Preço, insira um número.
    * Para a demonstração, digite 10.  
24. Clique em Salvar.
25. Clique em Ativar preço(s) pendente(s).
26. Feche a página.
27. Feche a página.

## <a name="create-the-third-material"></a>Criar o terceiro material
1. Clique em Novo.
2. No campo Número do produto, digite um valor.
    * Para a demonstração, digite ITEM_C  
3. No campo Grupo de modelos do item, insira ou selecione um valor.
    * Selecione STD. STD significa "custo padrão" e é o modelo mais comumente utilizado ao se trabalhar com cálculos de custo.  
4. No campo Grupo de itens, insira ou selecione um valor.
    * Por exemplo, selecione Áudio. Isso não tem impacto sobre os cálculos de custo.  
5. No campo Grupo de dimensões de armazenamento, insira ou selecione um valor.
    * Selecione SiteWH. Apenas Site e Depósito serão usados na demonstração.  
6. No campo Grupo de dimensões de rastreamento, insira ou selecione um valor.
    * A dimensão de rastreamento não será usada neste exemplo. Selecione Nenhuma.  
7. Clique em OK.
8. No Painel de Ação, clique em Gerenciar estoque.
9. Clique em Configurações de ordem padrão.
10. No campo Site de compra, insira ou selecione um valor.
    * Neste exemplo, selecione Site 1.  
11. No campo Site de estoque, insira ou selecione um valor.
    * Neste exemplo, selecione Site 1.  
12. No campo Site de vendas, insira ou selecione um valor.
    * Neste exemplo, selecione Site 1.  
13. Feche a página.
14. Feche a página.
15. Na lista, clique no link na linha selecionada.
    * Clique em ITEM_C.  
16. Expanda a seção Gerenciar custos.
17. No campo Grupo de custos, digite um valor.
    * Neste exemplo, digite M1.  
18. No Painel de Ação, clique em Gerenciar custos.
19. Clique em Preço de item.
20. Clique em Novo.
21. No campo Versão, insira ou selecione um valor.
    * Neste exemplo, selecione 10. Este é o tipo de custo Custo padrão.  
22. No campo Local, insira ou selecione um valor.
    * Neste exemplo, selecione Site 1.  
23. No campo Preço, insira um número.
    * Neste exemplo, digite 10.  
24. Clique em Salvar.
25. Clique em Ativar preço(s) pendente(s).
26. Feche a página.
27. Feche a página.


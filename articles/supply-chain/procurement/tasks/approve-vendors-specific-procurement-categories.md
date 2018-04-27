--- 
title: "Aprovar fornecedores para categorias específicas da compras"
description: "Quando uma requisição da compra é criada, pode haver uma exigência para selecionar um vendedor aprovado ou preferido, dependendo de como as políticas de compra são definidas."
author: mkirknel
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 83945932d56abf6bf44476e5647f8ae7abdc3602
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="approve-vendors-for-specific-procurement-categories"></a>Aprovar fornecedores para categorias específicas da compras

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Quando uma requisição da compra é criada, pode haver uma exigência para selecionar um vendedor aprovado ou preferido, dependendo de como as políticas de compra são definidas. Este procedimento mostra como especificar se um vendedor é aprovado ou preferido para uma categoria específica da obtenção. Essa tarefa é tipicamente realizada por um profissional de aquisição. Você pode usar este procedimento na empresa USMF de dados de demonstração.

1. Vá para Aquisição e fornecimento > Fornecedores > Todos os fornecedores.
2. Selecione o vendedor que você quer ajustar como um vendedor aprovado ou preferido para uma categoria.
3. No Painel de Ação, clique em Geral.
4. Clique em Categorias.
5. Clique em Adicionar categoria.
6. No campo Categoria, selecione ACESSÓRIOS DE ESCRITÓRIO E MESA (ACESSÓRIOS DE ESCRITÓRIO E MESA).
7. No campo Status da categoria do vendedor, selecione "Preferido".
    * É possível especificar mais de um vendedor preferido para uma categoria.  
8. Clique em Salvar.
9. Vá para Aquisição e fornecimento > Categorias de aquisição.
10. Na árvore, selecione 'CATEGORIAS DE AQUISIÇÃO CORPORATIVA\ESCRITÓRIO E ACESSÓRIOS DE MESA'.
11. Expanda a seção Fornecedores.
    * Verifique se o vendedor que você selecionou aparece como um vendedor preferido para a categoria dos acessórios do escritório e de mesa. Se você está executando este procedimento como um guia da tarefa, você pode ter que clicar no botão para destravar para poder rolar para baixo a lista de vendedores.  É igualmente possível adicionar vendedores preferidos e aprovados nesta página.  
12. Na árvore, expanda 'ACESSÓRIOS DE ESCRITÓRIO E MESA'.
13. Na árvore, selecione "Tesouras".
14. Selecione Não no campo Fornecedores herdados da categoria principal:.
15. Selecione Sim no campo Fornecedores herdados da categoria principal:.



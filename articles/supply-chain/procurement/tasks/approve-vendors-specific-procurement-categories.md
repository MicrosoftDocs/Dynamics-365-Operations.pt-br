---
title: Aprovar fornecedores para categorias específicas da compras
description: Este tópico explica como aprovar fornecedores para categorias específicas de compras no Dynamics 365 Supply Chain Management.
author: mkirknel
manager: AnnBe
ms.date: 07/30/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, DirPartyEcoResCategory, EcoResCategorySingleLookup, ProcCategoryHierarchyManagement
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 135b3a6bea2c0a8940550299504139551c9c3559
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3147494"
---
# <a name="approve-vendors-for-specific-procurement-categories"></a>Aprovar fornecedores para categorias específicas da compras

[!include [banner](../../includes/banner.md)]

Este tópico explica como aprovar fornecedores para categorias específicas de compras no Dynamics 365 Supply Chain Management. Quando uma requisição da compra é criada, pode haver uma exigência para selecionar um vendedor aprovado ou preferido, dependendo de como as políticas de compra são definidas. Este procedimento mostra como especificar se um vendedor é aprovado ou preferido para uma categoria específica da obtenção. Essa tarefa é tipicamente realizada por um profissional de aquisição. Você pode usar este procedimento na empresa USMF de dados de demonstração.

1. No Painel de Navegação, vá para **Módulos > Compras e fornecimento > Fornecedores > Todos os fornecedores**.
2. Selecione o vendedor que você quer ajustar como um vendedor aprovado ou preferido para uma categoria.
3. No Painel de Ação, selecione **Geral**.
4. Selecione **Categorias**.
5. Selecione **Adicionar categoria**.
6. No campo **Categoria**, selecione **ACESSÓRIOS DE ESCRITÓRIO E MESA (ACESSÓRIOS DE ESCRITÓRIO E MESA)**.
7. No campo **Status da categoria do fornecedor**, selecione **Preferencial**. É possível especificar mais de um vendedor preferido para uma categoria.  
8. Selecione **Salvar**.
9. No Painel de Navegação, vá para **Módulos > Compras e fornecimento > Categorias de compras**.
10. Na árvore, selecione **CATEGORIAS DE AQUISIÇÃO CORPORATIVA\ESCRITÓRIO E ACESSÓRIOS DE MESA**.
11. Expanda a seção **Fornecedores**. Verifique se o fornecedor que você selecionou aparece como vendedor preferencial na categoria Acessórios de escritório e mesa. Se você está executando este procedimento como um guia da tarefa, você pode ter que selecionar o botão **Desbloquear** para destravar para poder rolar para baixo a lista de vendedores.  É igualmente possível adicionar vendedores preferidos e aprovados nesta página.  
12. Na árvore, expanda **ACESSÓRIOS DE ESCRITÓRIO E MESA** e selecione **Tesouras**.
13. Selecione **Não** no campo **Fornecedores herdados da categoria principal:**.
14. Selecione **Sim** no campo **Fornecedores herdados da categoria principal:**.


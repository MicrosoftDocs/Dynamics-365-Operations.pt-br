---
title: Criar um catálogo de compras
description: Este tópico explica como criar um catálogo de compras.
author: mkirknel
manager: tfehr
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProcCategoryHierarchyManagement, CatProcureCatalogListPage, CatProcureCatalogCreate, CatProcureCatalogEdit, SysPolicyListPage, SysPolicy, CatCatalogPolicyRule, PurchReqTableListPage, PurchReqCreate, PurchReqTable, PurchReqAddItem
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 20966291ce6297561514ce9d9f7e945859997351
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422127"
---
# <a name="create-a-procurement-catalog"></a>Criar um catálogo de compras

[!include [banner](../../includes/banner.md)]

Este tópico explica como criar um catálogo de compras. Essa tarefa é tipicamente realizada por um profissional de aquisição. Você também aprenderá como os empregados podem usar o catálogo quando criam uma requisição. Antes de criar um catálogo, deve haver uma hierarquia da categoria da obtenção em seu sistema. A hierarquia é herdada pelo catálogo novo, junto com todos os produtos que estão na hierarquia. Você pode usar este guia na empresa USMF dos dados do programa demonstrativo onde a hierarquia da categoria da obtenção está disponível, assim como os exemplos usados nas etapas de procedimento.


## <a name="ensure-that-a-procurement-category-hierarchy-exists"></a>Assegure-se de que uma hierarquia da categoria da obtenção exista
1. Vá para **Painel de navegação > Módulos > Compras e fornecimento > Categorias de compras**. Uma hierarquia de categorias de compras está disponível na empresa de dados de demonstração de USMF e os produtos foram adicionados às **máquinas de escritório/categoria dos computadores**. Se você estiver executando este procedimento como um guia de tarefa você precisará desbloquear o guia se quiser pesquisar entre a categoria. Se uma hierarquia não estava disponível, você a criaria clicando em **Novo**. Isso só pode ser feito uma vez.  
2. Feche a página.

## <a name="create-a-catalog"></a>Criar um catálogo
1. Vá para **Painel de navegação > Módulos > Compras e fornecimento > Catálogos > Catálogos de compras**.
2. Selecione **Novo catálogo de compras** para abrir a caixa de diálogo suspensa.
3. No campo **Nome**, digite um valor.
4. Selecione **OK**.
5. Na árvore, expanda **CATEGORIAS DE AQUISIÇÃO CORPORATIVA**.
6. Na árvore, expanda **MÁQUINAS DE ESCRITÓRIO**.
7. Na árvore, selecione **Computadores**.

  - Os produtos da categoria da obtenção são indicados na lista. Se quiser adicionar um produto à categoria, faça isso na página **Hierarquia de categorias de compras** ou na página **Detalhes do item**.  
  - O tipo de atualização **Padrão** determina se os produtos novos que foram adicionados à hierarquia de categorias de compras são imediatamente visíveis no catálogo. Se o tipo de atualização for definido como **Dinâmico**, as mudanças ficarão logo visíveis. Se o tipo de atualização for **Estático**, os produtos novos são somente visíveis às pessoas que usam o catálogo depois que o catálogo foi publicado novamente. A ação **Publicar** está disponível no Painel de Ação na parte superior da página. Se os produtos forem removidos da hierarquia de categorias de compras, a mudança ficará logo visível, independentemente do valor no campo de tipo de atualização **Padrão**.  

8. No Painel de Ação, selecione **Navegação de categoria** e certifique-se de que **Habilitar** esteja selecionado.
9. Selecione **Ativar catálogo**.
10. Feche a página.

## <a name="make-the-catalog-visible"></a>Tornar o catálogo visível
1. Vá para **Painel de navegação > Módulos > Compras e fornecimento > Configuração > Políticas > Políticas de compras**.
2. Selecione **USMF da Política de Aquisição**. Você precisa selecionar a política de compras para a entidade legal em que é permitido ao trabalhador conectado a seu perfil de usuário a pedir produtos. Nos dados de demonstração USMF, o usuário administrador é conectado ao trabalhador chamado **Julia Funderburk**; ela pede produtos em USMF por padrão.  
3. Selecione o catálogo que você acabou de criar.
4. Selecione **OK**.

## <a name="use-the-catalog"></a>Usar o catálogo
1. Vá para **Painel de navegação > Módulos > Compras e fornecimento > Requisições de compras > Todas as requisições de compras**.
2. Selecione **Novo**.
3. No campo **Nome**, digite um valor.
4. Selecione **OK**.
5. Selecione **Adicionar produtos**.
6. Na lista, localize e selecione o registro desejado. Você pode usar a hierarquia da categoria à esquerda ou o filtro na parte superior da lista para filtrar os produtos.  
7. Selecione **Adicionar a linhas**.
8. Selecione **OK**.


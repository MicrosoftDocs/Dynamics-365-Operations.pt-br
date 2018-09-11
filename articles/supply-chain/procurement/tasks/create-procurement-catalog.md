--- 
title: "Criar um catálogo de compras"
description: "Este guia mostra como criar um catálogo de compras."
author: mkirknel
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProcCategoryHierarchyManagement, CatProcureCatalogListPage, CatProcureCatalogCreate, CatProcureCatalogEdit, SysPolicyListPage, SysPolicy, CatCatalogPolicyRule, PurchReqTableListPage, PurchReqCreate, PurchReqTable, PurchReqAddItem
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: df844ba3834972441daa61899294b3e95cac96c1
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-procurement-catalog"></a>Criar um catálogo de compras

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este guia mostra como criar um catálogo de compras. Essa tarefa é tipicamente realizada por um profissional de aquisição. Você também aprenderá como os empregados podem usar o catálogo quando criam uma requisição. Antes de criar um catálogo, deve haver uma hierarquia da categoria da obtenção em seu sistema. A hierarquia é herdada pelo catálogo novo, junto com todos os produtos que estão na hierarquia. Você pode usar este guia na empresa USMF dos dados do programa demonstrativo onde a hierarquia da categoria da obtenção está disponível, assim como os exemplos usados nas etapas de procedimento.


## <a name="ensure-that-a-procurement-category-hierarchy-exists"></a>Assegure-se de que uma hierarquia da categoria da obtenção exista
1. Vá para Aquisição e fornecimento > Categorias de aquisição.
    * Uma hierarquia da categoria da obtenção está disponível na empresa dos dados do programa demonstrativo de USMF e os produtos foram adicionados às máquinas de escritório/categoria dos computadores. Se você estiver executando este procedimento como um guia de tarefa você precisará desbloquear o guia se quiser pesquisar entre a categoria. Se uma hierarquia não estava disponível, você a criaria clicando em Novo. Isso só pode ser feito uma vez.  
2. Feche a página.

## <a name="create-a-catalog"></a>Criar um catálogo
1. Vá para Compras > Catálogos > Catálogos de compras.
2. Clique em Novo catálogo de compras para abrir o formulário suspenso da caixa de diálogo.
3. No campo Nome, digite um valor.
4. Clique em OK.
5. Na árvore, expanda 'CATEGORIAS DE AQUISIÇÃO CORPORATIVA\MÁQUINAS DE ESCRITÓRIO'.
6. Na árvore, expanda 'OFFICE MACHINES'.
7. Na árvore, selecione o nó ''Computadores".
    * Os produtos da categoria da obtenção são indicados na lista. Se você quer adicionar um produto à categoria, você precisa fazer isso na página da hierarquia da categoria da obtenção ou na página dos detalhes do artigo.  
    * O tipo de atualização padrão determina se os produtos novos que foram adicionados à hierarquia da categoria da obtenção são imediatamente visíveis no catálogo. Se o tipo de atualização ajustado é dinâmico, as mudanças são visíveis imediatamente. Se o tipo de atualização é estática, os produtos novos são somente visíveis às pessoas que usam o catálogo depois que o catálogo foi publicado novamente. A ação da publicação está disponível na placa da ação na parte superior da página. Se os produtos são removidos da hierarquia da categoria da obtenção, a mudança é imediatamente visível, apesar do valor no tipo de atualização campo padrão.  
8. Na lista, localize e selecione o PDV desejado.
9. Clique em Esconder.
10. No Painel de Ação, clique em Navegação de categoria.
11. Clique em Desabilitar.
12. No Painel de Ação, clique em Navegação de categoria.
13. Clique em Habilitar.
14. Clique em Ativar catálogo.
15. Feche a página.

## <a name="make-the-catalog-visible"></a>Tornar o catálogo visível
1. Vá para Compras > Configuração > Políticas > Políticas de compras.
2. Selecione Política de compras USMF.
    * Você precisa selecionar a política de compras para a entidade legal em que é permitido ao trabalhador conectado a seu perfil de usuário a pedir produtos. Nos dados do programa demonstrativo de USMF, o usuário do Admin é conectado ao trabalhador chamado Julia Funderburk, e pede produtos em USMF por padrão.  
3. Na lista, clique no link na linha selecionada.
4. Selecione o catálogo que você acabou de criar.
5. Clique em OK.
6. Feche a página.
7. Feche a página.

## <a name="use-the-catalog"></a>Usar o catálogo
1. Vá para Compras > Requisições de compra > Todas as requisições de compra.
2. Clique em Novo.
3. No campo Nome, digite um valor.
4. Clique em OK.
5. Clique em Adicionar produtos.
6. Na lista, localize e selecione o PDV desejado.
    * Você pode usar a hierarquia da categoria à esquerda ou o filtro na parte superior da lista para filtrar os produtos.  
7. Clique em Adicionar às linhas.
8. Na lista, localize e selecione o PDV desejado.
9. Clique em Adicionar às linhas.
10. Clique em OK.



---
title: Configurar uma hierarquia de categorias de compras
description: Este procedimento mostra como criar novos nós em uma hierarquia de categorias de aquisição e como configurar uma categoria de aquisição para ser usada em um processo de aquisição.
author: mkirknel
manager: AnnBe
ms.date: 11/06/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 01809a8a3256342682d8a9cfb296a355310fe4ed
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1569882"
---
# <a name="set-up-a-procurement-category-hierarchy"></a>Configurar uma hierarquia de categorias de compras

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como criar novos nós em uma hierarquia de categorias de aquisição e como configurar uma categoria de aquisição para ser usada em um processo de aquisição. Essas tarefas são normalmente realizadas por um Gerente de compras. Antes que você possa começar esse procedimento, é necessário que exista uma hierarquia de categoria do tipo Aquisição. Se você for utilizar uma empresa de dados demonstrativos, é possível executar esse procedimento na empresa USMF.


## <a name="add-a-new-procurement-category"></a>Adicione uma nova categoria de aquisição.
1. Vá para Aquisição e fornecimento > Categorias de aquisição.
2. Clique em Editar hierarquia de categoria.
    * A hierarquia de categorias de aquisição atual é exibida no lado esquerdo da página. Você está prestes a modificar a hierarquia.  
3. Clique em Novo nó de categoria.
    * O sistema seleciona o nó superior por padrão. Se você estiver executando esse procedimento como um guia de tarefa, é possível clicar no botão Desbloquear e selecionar outro nó superior onde irá inserir o novo nó. Assim que isso for feito, bloqueie o guia de tarefa novamente e clique em Novo nó de categoria.  
4. No campo Nome, digite um valor.
5. No campo Descrição, digite um valor.
6. No campo Nome amigável, digite um valor.
    * O nome amigável é opcional. Ele será exibido nas pesquisas de categoria junto com o nome da categoria.  
7. Clique em Salvar.

## <a name="add-products-to-your-new-procurement-category"></a>Adicionar produtos a sua nova categoria de aquisição
1. Vá para Aquisição e fornecimento > Categorias de aquisição.
    * Selecione o nó que você acabou de adicionar. Se você estiver executando este procedimento como um guia de tarefa você talvez precise desbloquear o guia de tarefa para selecionar o nó.  
2. Ative a expansão da seção Produtos.
3. Clique em Adicionar para associar produtos à categoria de aquisição.
4. Selecione o produto que você deseja adicionar à categoria de aquisição.
5. Clique na seta para selecionar o produto.
6. Selecione outro produto para adicionar à categoria de aquisição.
7. Clique na seta para selecionar o produto.
8. Clique em OK.

## <a name="add-approved-and-preferred-vendors"></a>Adicionar fornecedores aprovados e preferenciais
1. Alternar a expansão da seção Fornecedores.
2. Clique em Adicionar.
    * Você pode adicionar um fornecedor à uma categoria de aquisição e especificar se um fornecedor é o preferencial ou apenas aprovado na categoria. Quando você exclui um fornecedor de uma categoria, as transações do histórico com o fornecedor na categoria não serão excluídas.   
3. Encontre o fornecedor que você deseja adicionar à categoria.
4. Clique na seta para selecionar o fornecedor.
5. Clique em OK.
6. Selecione a linha de fornecedor que você deseja modificar.
7. No campo Status do fornecedor, selecione uma opção.
    * A configuração de seleção do fornecedor na regra Política de categoria controla se os preferenciais, aprovados, ou todos os fornecedores estão disponíveis para requisições de compra.   

## <a name="add-additional-information-to-the-category"></a>Adicionar informações adicionais à categoria
1. Ative a expansão da seção Grupos de critério de avaliação do fornecedor.
    * Esta aba permite que você defina os critérios sobre os quais os fornecedores na categoria de aquisição devem ser avaliados. Para fazer isso você deve clicar em Adicionar e então selecionar um grupo de avaliação de fornecedores que contêm os critérios desejados.  
2. Ative a expansão da seção Questionários.
    * Esta aba permite que você adicione questionários que irão aparecer na requisição, desde que você defina o Tipo de atividade como "Requisição". O solicitante precisa então preencher um questionário antes de enviar uma requisição para os produtos ou produto específico na categoria de aquisição.  
3. Ative a expansão da seção Grupos de imposto sobre vendas do item.
4. No campo Grupo de imposto sobre vendas do item:, clique no botão suspenso para abrir a pesquisa.
5. Selecione um grupo de impostos sobre vendas.
6. Ative a expansão da seção Página de categoria.
    * Páginas de categoria são criadas na página Hierarquia de categoria. Elas contêm informação sobre a categoria de aquisição como por exemplo informações sobre o tipo de produtos em uma categoria, imagens de produtos em uma categoria, ou anúncios como os descontos disponíveis em uma categoria. As informações em uma página de categoria são exibidas em requisições de compra.  
7. Feche a página.


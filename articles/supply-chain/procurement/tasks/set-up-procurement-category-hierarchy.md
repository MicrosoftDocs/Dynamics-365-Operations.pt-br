---
title: Configurar uma hierarquia de categorias de compras
description: Este procedimento mostra como criar novos nós em uma hierarquia de categorias de aquisição e como configurar uma categoria de aquisição para ser usada em um processo de aquisição.
author: kamaybac
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 206dd5dc8f332268fe7665d84b005b5a7bfd1f9a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837696"
---
# <a name="set-up-a-procurement-category-hierarchy"></a>Configurar uma hierarquia de categorias de compras

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como criar novos nós em uma hierarquia de categorias de aquisição e como configurar uma categoria de aquisição para ser usada em um processo de aquisição. Essas tarefas são normalmente realizadas por um Gerente de compras. Antes que você possa começar esse procedimento, é necessário que exista uma hierarquia de categoria do tipo Aquisição. Se você for utilizar uma empresa de dados demonstrativos, é possível executar esse procedimento na empresa USMF.


## <a name="add-a-new-procurement-category"></a>Adicione uma nova categoria de aquisição.
1. Vá para **Painel de navegação > Módulos > Compras e fornecimento > Consignação > Categorias de compras**.
2. No Painel de Ações, selecione **Editar hierarquia de categoria**. A hierarquia de categorias de aquisição atual é exibida no lado esquerdo da página. Você está prestes a modificar a hierarquia.  
3. No Painel de Ações, selecione **Novo nó de categoria**. O sistema seleciona o nó superior por padrão. Se você estiver executando esse procedimento como um guia de tarefa, é possível clicar no botão Desbloquear e selecionar outro nó superior onde irá inserir o novo nó. Assim que isso for feito, bloqueie o guia de tarefa novamente e clique em Novo nó de categoria.  
4. No campo **Nome**, digite um valor.
5. No campo **Descrição**, digite um valor.
6. No campo **Nome amigável**, digite um valor. O nome amigável é opcional. Ele será exibido nas pesquisas de categoria junto com o nome da categoria.  
7. Selecione **Salvar**.

## <a name="add-products-to-your-new-procurement-category"></a>Adicionar produtos a sua nova categoria de aquisição
1. Vá para **Compras e fornecimento > Consignação > Categorias de compras**. Selecione o nó que você acabou de adicionar. Se você estiver executando este procedimento como um guia de tarefa você talvez precise desbloquear o guia de tarefa para selecionar o nó.  
2. Ative a expansão da seção **Produtos**.
3. Selecione **Adicionar** para associar produtos à categoria de compras.
4. Selecione os produtos que você deseja adicionar à categoria de compras.
5. Selecione a seta para adicionar os produtos à tabela **Selecionados**.
6. Selecione **OK**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
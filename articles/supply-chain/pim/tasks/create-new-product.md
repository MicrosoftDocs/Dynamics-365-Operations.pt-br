---
title: Criar um novo produto
description: Essa tarefa mostra como criar um novo produto compartilhado.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductInventoryDimensionGroups
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7a603d89749242a4c6039ab83da286ec6ab727d8
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "328530"
---
# <a name="create-a-new-product"></a>Criar um novo produto

[!include [task guide banner](../../includes/task-guide-banner.md)]

Essa tarefa mostra como criar um novo produto compartilhado. Geralmente é realizado por um designer do produto. A empresa de dados demo usada para criar esta tarefa é USMF.

1. Vá para Gerenciamento de informações sobre produtos > Produtos > Produtos.

## <a name="create-a-product"></a>Criar um produto
1. Clique em Novo.
2. No campo Número do produto, digite um valor.
    * Se uma sequência numérica não foi configurada para o número do produto, deve ser inserida manualmente.  
3. No campo Nome do produto, digite um valor.
    * O Nome do produto padrão ao nome de pesquisa. Você pode mudar isso, se necessário.  
4. Clique em OK.

## <a name="set-up-dimension-groups"></a>Configurar grupos de dimensões
1. Clique em Grupos de dimensões para abrir a caixa de diálogo suspensa.
2. No campo Grupo de dimensões de armazenamento, insira ou selecione um valor.
    * O grupo de dimensões de armazenamento determina quais dimensões de estoque você deve inserir em cada transação para o produto e como são rastreados no estoque.  
3. No campo Grupo de dimensões de rastreamento, insira ou selecione um valor.
    * O grupo de dimensões de rastreamento determina quais dimensões de rastreamento você deve inserir em cada transação para o produto e como são lidadas no estoque.  
4. Clique em OK.


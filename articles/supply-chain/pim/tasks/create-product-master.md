---
title: Criar um produto mestre
description: Crie um produto mestre para as variáveis predefinidas.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductInventoryDimensionGroups
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 70008e903763fff35c6cff12c42396fe5fcabbee
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5832073"
---
# <a name="create-a-product-master"></a>Criar um produto mestre

[!include [banner](../../includes/banner.md)]

Crie um produto mestre para as variáveis predefinidas. A empresa de dados demo usada para criar este procedimento é USMF. Este procedimento é voltado ao designer de produtos.


## <a name="create-a-new-product-master"></a>Criar um novo produto mestre
1. Vá para **Painel de navegação > Módulos > Gerenciamento de informações sobre produtos > Produtos > Produtos mestres**.
2. Clique em **Novo**.
3. No campo **Número do produto**, digite um valor. O número deve ser exclusivo. É possível definir uma sequência numérica para o campo **Número do produto**. Nesse caso, o usuário não precisará inserir um valor.
4. No campo **Nome do produto**, digite um valor. Insira um nome de produto descritivo. O valor será padronizada pelo nome de pesquisa, mas isso pode ser alterado pelo usuário.
5. No campo **Grupo de dimensões do produto**, clique no botão suspenso para abrir a pesquisa. O grupo de dimensões do produto determina quais das 4 dimensões do produto podem ser usadas para criar variantes do produto. Este exemplo usa um grupo com cor e tamanho.
6. Na lista, localize e selecione o registro desejado.
7. Na lista, clique no link na linha selecionada. A **Tecnologia de configuração** padrão é 'Grade predefinida'. Isso será usado neste exemplo.
8. Clique em **OK**.

## <a name="select-product-dimension-groups"></a>Selecionar os grupos de dimensão do produto
1. No campo **Grupo de cores**, clique no botão suspenso para abrir a pesquisa.
2. Na lista, localize e selecione o registro desejado.
3. Na lista, clique no link na linha selecionada.
4. No campo **Grupo de tamanhos**, clique no botão suspenso para abrir a pesquisa.
5. Na lista, localize e selecione o PDV desejado.
6. Na lista, clique no link na linha selecionada.

## <a name="add-dimension-groups"></a>Adicionar grupos de dimensões
1. No **Painel de Ação**, clique em **Produto**.
2. Clique em **Grupos de dimensões** para abrir a caixa de diálogo suspensa.
3. No campo **Grupo de dimensões de armazenamento**, clique no botão suspenso para abrir a pesquisa. As dimensões de armazenamento ajudam a controlar como os itens são armazenados e retirados do estoque. Por exemplo, uma dimensão de armazenamento pode incluir o Local e o Depósito.
4. Na lista, localize e selecione o PDV desejado.
5. Na lista, clique no link na linha selecionada.
6. No campo **Grupo de dimensões de rastreamento**, clique no botão suspenso para abrir a pesquisa. O grupo de dimensões de rastreamento determina quais dimensões de rastreamento você pode adicionar a um produto. Por exemplo, o número de lote e o número de série são usados para rastrear itens de estoque.
7. Na lista, localize e selecione o PDV desejado.
8. Na lista, clique no link na linha selecionada.
9. Clique em **OK**.
10. Clique em **Salvar**.
11. Feche a página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
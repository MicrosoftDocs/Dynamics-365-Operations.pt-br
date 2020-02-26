---
title: Criar uma hierarquia de navegação de canal
description: Este tópico descreve como criar uma hierarquia de navegação de canal no Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: e83860667f142adcc85cd8542d521e18f16dbc2c
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002027"
---
# <a name="create-a-channel-navigation-hierarchy"></a>Criar uma hierarquia de navegação de canal


[!include [banner](includes/banner.md)]

Este tópico descreve como criar uma hierarquia de navegação de canal no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

Uma hierarquia de navegação de canal é usada para agrupar e organizar os produtos em categorias, de modo que eles possam ser procurados online ou em pontos de venda (PDV).

## <a name="create-a-channel-navigation-hierarchy"></a>Criar uma hierarquia de navegação de canal

Para criar uma hierarquia de navegação de canal, siga estas etapas.

1. No painel de navegação, vá para **Módulos \> Varejo e comércio \> Produtos e categorias \> Categorias de navegação de canal**.
1. No painel de ação, selecione **Novo**.
1. Na caixa **Nome**, insira um nome.
1. Na caixa **Descrição**, insira uma descrição.
1. Selecione **Criar**.
1. No painel de ação, selecione **Novo nó de categoria** para criar um nó raiz.
1. Na caixa **Nome**, insira um nome.
1. Na caixa **Descrição**, insira uma descrição.
1. Na caixa **Nome amigável**, insira um nome amigável.
1. No painel de ação, selecione **Salvar**.

A imagem a seguir mostra um exemplo de nó raiz.

![Nó raiz de exemplo](media/create-channel-hierarchy-1.png)

## <a name="create-navigation-category-nodes"></a>Criar nós de categoria de navegação

Para criar outros nós de categoria de navegação para representar as categorias de produto no canal, siga estas etapas.

1. No painel de navegação, selecione o nó pai ao qual adicionar uma categoria.
1. No painel de ação, selecione **Novo nó de categoria**.
1. Na caixa **Nome**, insira um nome.
1. Na caixa **Descrição**, insira uma descrição.
1. Na caixa **Nome amigável**, insira um nome amigável.
1. Na caixa **Ordem de exibição**, insira uma ordem de exibição (opcional).
1. No painel de ação, selecione **Salvar**.

A imagem a seguir mostra um exemplo de hierarquia de navegação de canal concluída.

![Hierarquia de canal de exemplo](media/create-channel-hierarchy-2.png)

## <a name="add-products-to-category-nodes"></a>Adicionar produtos a nós de categoria

Para adicionar produtos a nós de categoria, siga estas etapas.

1. Selecione um nó de categoria.
1. Em **Produtos**, selecione **Adicionar**.
1. Localize o(s) novo(s) produto(s) que você quer adicionar usando o número ou o nome do produto e selecione **OK**.
1. No painel de ação, selecione **Salvar**.

> [!NOTE]
> Adicionar produtos a um nó dentro da hierarquia de navegação de canal não é suficiente para os produtos serem mostrados no canal selecionado; eles também devem ser classificados para um produto.

A imagem a seguir mostra um exemplo de nó com produtos adicionados.

![Produtos adicionados a um nó de categoria](media/create-channel-hierarchy-3.png)

## <a name="add-product-attribute-groups-to-category-nodes"></a>Adicionar grupos de atributo de produto a nós de categoria

> [!NOTE]
> Grupos de atributo devem ser criados para que você possa adicioná-los a um nó dentro da hierarquia de navegação de canal.

Para adicionar um grupo de atributos de produto a um nó de categoria, siga estas etapas.

1. Selecione um nó de categoria.
1. Em **Grupo de atributos de produto**, selecione **Adicionar**.
1. Localize o(s) grupo(s) de atributos que você gostaria de adicionar e selecione **OK**.
1. No painel de ação, selecione **Salvar**.

A imagem a seguir mostra um nó de exemplo com grupos de atributo de produto adicionados.

![Grupos de atributo de produto em um nó](media/create-channel-hierarchy-4.png)

## <a name="additional-resources"></a>Recursos adicionais

[Configurar classificações](set-up-assortments.md)

[Gerenciar atributos e grupos de atributos](attribute-attributegroups-lifecycle.md)

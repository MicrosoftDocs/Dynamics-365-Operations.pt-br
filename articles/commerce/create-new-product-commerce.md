---
title: Criar um novo produto no Commerce
description: Este tópico descreve como criar um novo produto no Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 44a58da0be280b06d96cdeae6929042bb50ed4a6
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795706"
---
# <a name="create-a-new-product-in-commerce"></a>Criar um novo produto no Commerce


[!include [banner](includes/banner.md)]

Este tópico descreve como criar um novo produto no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão Geral

Um produto é definido principalmente por um número de produto, nome e descrição. No entanto, outros dados também são necessários para descrever um produto ou serviço:

## <a name="create-a-new-product"></a>Criar um novo produto

1. No painel de navegação, vá para **Módulos \> Varejo e comércio \> Produtos e categorias \> Produtos por categoria**.
1. No painel de ação, selecione **Novo**.
1. Na lista suspensa **Tipo de produto**, selecione **Item** ou **Serviço**.
1. Na lista suspensa **Subtipo de produto**, selecione **Produto** (se o produto não tiver grades) ou **Produto mestre** (se o produto tiver grades).
1. Na caixa **Número do produto**, insira um número de produto se já não houver um preenchido previamente.
1. Na caixa **Nome do produto**, insira um nome de produto.
1. Na caixa **Nome da pesquisa**, insira um nome de pesquisa.
1. Na lista suspensa **Categoria de varejo**, selecione uma categoria apropriada.
1. Se o produto for um kit, selecione **Sim** para **Kit de produtos**.
1. Se o subtipo de produto for produto mestre, defina o **Grupo de dimensões do produto** para incluir as grades com suporte. As opções incluem **Cor**, **Tamanho**, **Estilo** e **Configuração**. Pode ser necessário criar mais grupos de dimensões do produto.
1. Na lista suspensa **Tecnologia de configuração**, selecione uma opção apropriada.
1. Selecione **OK**.

A imagem a seguir mostra um exemplo de produto sendo adicionado.

![Criar um produto](media/create-new-product.png)

Depois que um produto é adicionado, é possível definir outros dados para ele, como **Descrição do produto**, **Grupos de grades**, **Grupos de dimensões**, **Atributos de produto** e **Produtos relacionados**.

A imagem a seguir mostra mais detalhes de um produto.

![Detalhes do produto](media/create-new-product-2.png)

### <a name="create-product-variants"></a>Criar grades de produtos

Se o subtipo de produto for **Produto mestre**, será necessário criar grades específicas. 

Para criar grades de produto, siga estas etapas.

1. No painel de ação, selecione **Grades de produto**.
1. Se grupos de grades tiverem sido selecionados no painel de ação, selecione **Sugestões de grade*.
1. Selecione as grades do produto às quais você gostaria de oferecer suporte.
1. Selecione **Criar**.

## <a name="release-a-product"></a>liberar produtos

Para vender um produto, primeiro ele deve ser liberado para uma entidade legal.

1. Na página do produto, selecione **Liberar produtos**.

    ![Liberar produto](media/create-new-product-3.png)

1. Selecione o produto a ser liberado e clique em **Avançar**.

    ![Escolher o produto a ser liberado](media/create-new-product-4.png)

1. Selecione o conjunto de grades de produto para liberação e clique em **Avançar**.

    ![Escolher as grades a serem liberadas](media/create-new-product-5.png)

1. Selecione a entidade legal e clique em **Avançar**.

    ![Escolher entidade legal](media/create-new-product-6.png)

1. Selecione **Concluir**.

    ![Concluir liberação de produto](media/create-new-product-7.png)

## <a name="configure-a-released-product"></a>Configurar um produto liberado

Depois que um produto é liberado, ele precisa de mais configurações, entre elas adicionar um preço ao produto.

1. No painel de navegação, vá para **Módulos \> Varejo e Comércio \> Produtos e categorias \> Produtos lançados por categoria**.
1. Selecione o nó de categoria de produto do produto que foi liberado e, depois, escolha o produto na lista de produtos.
1. No painel de ação, selecione **Editar**.
1. Na seção **Compra**, configure todas as propriedades necessárias, inclusive **Unidade**, **Preço** e **Quantidade**.
1. No painel de ação, selecione **Validar** para garantir que não haja erros de campos ausentes.
1. No painel de ação, selecione **Salvar**.

A imagem a seguir mostra um exemplo de configuração de produto liberado.

![Configurar produto liberado](media/create-new-product-8.png)

## <a name="additional-resources"></a>Recursos adicionais

[Criar entidades legais](channels-legal-entities.md)

[Criar um grupo de grades](create-variant-group.md) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
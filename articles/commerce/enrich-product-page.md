---
title: Enriquecer uma página de produto
description: Este tópico descreve como enriquecer uma página de produto no Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: ef9e65b2027a41ca152afaf20ac2fb9a69cd9b96
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698133"
---
# <a name="enrich-a-product-page"></a>Enriquecer uma página de produto

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tópico descreve como enriquecer uma página de produto no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

Por padrão, seu site usa uma página genérica para exibir dados de produto. Essa página inclui informações básicas sobre o produto e controles necessários para vendê-lo. Entretanto, você pode adicionar as informações que vem do servidor de varejo com imagens adicionais ou texto para um produto específico. Esse processo é conhecido como enriquecimento da página de produto.

Em muitos casos, você desejará usar conteúdo adicional específico de seus produtos. Quando você vai para **Varejo** na ferramenta de criação, você verá uma lista de produtos no canal atribuído ao site. Na lista, a coluna **Enriquecido** indica se a página do produto de um produto foi enriquecida. Se uma marca de seleção é exibida na coluna, uma página enriquecida de produto existe para o produto. Se nenhuma marca de seleção for exibida, a página de produto padrão e o conteúdo são usados para o produto. Você pode visualizar as páginas de produto enriquecida e não enriquecida selecionando um nome de produto na lista.

## <a name="enrich-a-product-page"></a>Enriquecer uma página de produto

Para enriquecer uma página de produto, siga estas etapas.

1. Em **Sites**, selecione **Fabrikam** (ou o nome do seu site).
1. No painel de navegação à esquerda, selecione **Produtos**.
1. Selecione todos os produtos que não têm uma página de produto enriquecida.
1. No Painel de Ação, selecione **Enriquecer página de produto**.
1. Selecione **Modelo PDP** e, depois, **OK**.
1. Na árvore em destaque da página à esquerda, expanda o slot **Principal**.
1. Selecione o botão de reticências (**...**) para o slot **Principal** e depois selecione **Adicionar módulo**.
1. Selecione **Contêiner 2** e, depois, **OK**.
1. Selecione o botão de reticências para **Contêiner 2** e depois selecione **Adicionar módulo**.
1. Selecione **Recurso** e, depois, **OK**.
1. No painel de propriedades à direita, no campo **Texto rico**, digite a descrição atualizada do produto.
1. No campo **Cabeçalho**, insira texto de cabeçalho e depois selecione **OK**.
1. Selecione **Salvar** e **Fazer Check-in**.
1. No campo **Comentários**, insira **Enriqueceu um produto** e depois selecione **OK**.
1. Selecione **Visualizar** para visualizar a página de produto enriquecida. Quando terminar, feche a guia de visualização para retornar à ferramenta de criação.
1. Selecione **Publicar**.

## <a name="additional-resources"></a>Recursos adicionais

[Modificar uma página de site existente](modify-existing-page.md)

[Adicionar uma nova página do site](add-new-page.md)

[Selecionar layouts de página](select-page-layouts.md)

[Gerenciar metadados de SEO](manage-seo-metadata.md)

[Salvar, visualizar, e publicar uma página](save-preview-publish-page.md)

[Enriquecer uma página de aterrissagem da categoria](enrich-category-page.md)


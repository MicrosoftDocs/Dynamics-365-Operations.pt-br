---
title: Enriquecer uma página de aterrissagem da categoria
description: Este tópico cobre o enriquecimento de páginas de categoria no Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 4ab152dff0925f9c816419083577b5272ac813be
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "2945764"
---
# <a name="enrich-a-category-landing-page"></a>Enriquecer uma página de aterrissagem da categoria

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tópico cobre o enriquecimento de páginas de categoria no Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

Comércio fornece uma página de aterrissagem de categoria padrão usada quando dados de categoria são mostrados. Uma página da categoria padrão contém elementos necessários, como os refinadores, posicionamento de produto categorizado, classificação de opções, um resumo de escolhas e controles de paginação. 

Entretanto, em vez de usar a página da categoria padrão, você poderá usar uma página de aterrissagem de categoria "enriquecida" que tem mais conteúdo e mais elementos específicos. Um enriquecimento típico pode envolver adicionar conteúdo de marketing específico do conteúdo à página de categoria. O conteúdo deve incluir o posicionamento de produtos entre categoria para fins de venda, listas de editorial, imagens, vídeos e outro texto. Você também pode modificar a página da categoria padrão ou definir uma página diferente de categoria para uma categoria específica.

![Página de aterrissagem da categoria enriquecida](./media/CategoryLandingPages.png)

Na ferramenta de criação, a página **Produto** inclui uma lista de categorias do canal que são atribuídas ao site. Se o status **Enriquecido** é selecionado para uma página de categoria, essa página de categoria foi enriquecida. Se não, a página da categoria padrão e o conteúdo são usados para a categoria. Você pode visualizar as páginas de categoria de produto enriquecida para a categoria selecionando o nome da categoria.

Para enriquecer uma pagina de categoria, siga este procedimento.

1. Na página **Produtos**, selecione o nome da categoria para a qual deseja enriquecer a página da categoria. A página da categoria padrão para a categoria selecionada é aberta no editor de páginas.
2. Selecione **Enriquecer página de categoria**.
3. Selecione um modelo para a página de categoria enriquecida. Se estiver fazendo apenas alterações menores, selecione a página da categoria padrão. Alternativamente, você pode selecionar um modelo específico de página de categoria. Quando você seleciona o modelo, o editor de páginas é aberto e o modelo selecionado é usado para criar uma nova página de categoria para a categoria selecionada. A página realizará check-out, e agora você pode fazer as alterações.

> [!NOTE]
> Módulos que usam dados de especificação de categoria usam os dados da categoria selecionada.
>
> As configurações do modelo selecionado determinam as alterações que você pode fazer.

## <a name="additional-resources"></a>Recursos adicionais

[Modificar uma página de site existente](modify-existing-page.md)

[Adicionar uma nova página do site](add-new-page.md)

[Selecionar layouts de página](select-page-layouts.md)

[Gerenciar metadados de SEO](manage-seo-metadata.md)

[Salvar, visualizar, e publicar uma página](save-preview-publish-page.md)

[Enriquecer uma página de produto](enrich-product-page.md)

[Verificar acessibilidade de conteúdo da página](verify-accessibility.md)

---
title: Gerenciar metadados de SEO
description: Este tópico descreve como gerenciar metadados da otimização do mecanismo de pesquisa (SEO) no Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c7cf9e76ffb30ee5c8bba318b2644e67c757bff0
ms.sourcegitcommit: 872600103d2a444d78963867e5e0cdc62e68c3ec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2021
ms.locfileid: "5097406"
---
# <a name="manage-seo-metadata"></a>Gerenciar metadados de SEO


[!include [banner](includes/banner.md)]

Este tópico descreve como gerenciar metadados da otimização do mecanismo de pesquisa (SEO) no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

Os metadados de SEO para um site podem ser gerenciados usando mapas do site e metadados da página.
    
## <a name="site-maps"></a>Mapas do site

Um mapa do site é uma lista legível por máquina, no formato XML, das páginas do seu site. Ele deve ser consumido pelos mecanismos de pesquisa, para que eles possam fornecer melhores resultados de pesquisa em seu site. Os mapas do site podem ser incorporados manualmente pelos mecanismos de pesquisa ou publicados em um arquivo robots.txt.

O Dynamics 365 Commerce oferece suporte à geração automática de mapas de site. Os mapas de site são atualizados automaticamente quando as páginas são publicadas e as publicações canceladas.

### <a name="turn-on-site-map-generation"></a>Ative a geração do mapa do site

1. Conectar-se à ferramenta de criação.
1. Em **Sites**, selecione **Fabrikam** (ou o nome do seu site).
1. No painel de navegação à esquerda, selecione **Gerenciamento de sites**.
1. Verifique se a opção **Mapas de site habilitados** está ativada.

## <a name="page-metadata"></a>Metadados da página

O Dynamics 365 Commerce permite gerenciar metadados de SEO para páginas individuais. É possível exibir e modificar estas informações na seção **Propriedades de SEO** de um contêiner de página. As seguintes propriedades de metadados de SEO são suportadas:

- Cargo
- Descrição
- Palavras-chave de SEO
- Etiquetas Aria
- noindex
- nofollow
- noarchive
- nocache
- noOpenDirectoryProject
- nosnippet
- noImageIndex
- unavailableAfter

### <a name="modify-page-metadata"></a>Modificar metadados da página

Para modificar os metadados da página, siga estas etapas.

1. Em **Sites**, selecione o **Fabrikam** (ou o nome do seu site).
1. No painel de navegação à esquerda, selecione **Páginas**.
1. Selecione a home page para abri-la no editor de páginas.
1. Na barra de comandos, selecione **Editar**.
1. No painel de propriedades à direita, expanda **Marcas meta padrão**.
1. Para adicionar uma nova marca meta, selecione **Adicionar** e informe a marca no campo. Para remover uma marca meta existente, selecione o símbolo da lata de lixo à direita dela.
1. Selecione **Salvar** e **Finalizar edição**.
1. No campo **Comentários**, insira **Marcas meta atualizadas** e depois selecione **OK**.
1. Selecione **Visualizar** para exibir a página. Quando terminar, feche a guia de visualização para retornar à ferramenta de criação.
1. Selecione **Publicar**.

## <a name="additional-resources"></a>Recursos adicionais

[Modificar uma página de site existente](modify-existing-page.md)

[Adicionar uma nova página do site](add-new-page.md)

[Selecionar layouts de página](select-page-layouts.md)

[Salvar, visualizar, e publicar uma página](save-preview-publish-page.md)

[Enriquecer uma página de produto](enrich-product-page.md)

[Enriquecer uma página de aterrissagem da categoria](enrich-category-page.md)

[Verificar acessibilidade do conteúdo da página](verify-accessibility.md)

[Criar páginas dinâmicas de comércio eletrônico com base nos parâmetros da URL](create-dynamic-pages.md)

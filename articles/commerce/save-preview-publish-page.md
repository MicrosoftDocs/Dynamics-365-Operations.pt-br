---
title: Salvar, visualizar, e publicar uma página
description: Este artigo descreve como salvar, visualizar e publicar uma página no Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: bf9cc4eb916976ed0c87f27cf8df7c0d52d07ef0
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280205"
---
# <a name="save-preview-and-publish-a-page"></a>Salvar, visualizar, e publicar uma página

[!include [banner](includes/banner.md)]

Este artigo descreve como salvar, visualizar e publicar uma página no Microsoft Dynamics 365 Commerce.

## <a name="save-a-page"></a>Salvar uma página

Para salvar uma página, você deve fazer check-out e abri-la no editor de páginas. Para fazer check-out de uma página, selecione **Editar** na barra de comandos. Depois de terminar de editar uma página, salve-a imediatamente para garantir que suas alterações sejam armazenadas.

Ao salvar uma página, as alterações ficarão visível apenas para você. A operação de salvar destina-se principalmente a armazenar alterações enquanto a página ainda não está pronta para o check-in. Quando você terminar de modificar a página, recomendamos que faça o check-in, para que as alterações fiquem visíveis para outras pessoas. Nesse ponto, também pode ser feito check-out da página por outros usuários que precisam modificá-la.

## <a name="preview-a-page"></a>Visualizar uma página

A ferramenta de criação oferece dois tipos de recursos de visualização: construtor de página visual, que é um painel de visualização "você vê como vai aparecer" (WYSIWYG) no editor de páginas e uma janela de visualização separada.

Ao usar o editor de páginas, uma visualização "você vê como vai aparecer" (WYSIWYG) aparece no painel central. Essa visualização é automaticamente atualizada sempre que você salvar a página. Você também pode atualizá-la manualmente, selecionando **Atualizar** na barra de comandos. A visualização renderiza a página exatamente como os usuários do site a verão, mas os auxiliares de criação serão renderizados na parte superior dela.

Quando você terminar de modificar a página, convém visualizá-la para ver o que os clientes verão. Para visualizar uma página, selecione **Visualizar** na barra de comandos. A visualização aparecerá em uma janela separada do navegador. A página na janela de visualização é renderizada exatamente como o usuário do site a vê. Você pode redimensionar a janela para garantir que os módulos responsivos sejam renderizados corretamente em todas as portas de exibição.

> [!NOTE]
> É necessária autenticação e permissões corretas para visualizar o conteúdo não publicado. Portanto, se você compartilhar a URL da visualização com alguém, essa pessoa deverá ter as permissões corretas para acessar o conteúdo.

## <a name="publish-a-page"></a>Publicar uma página

Quando sua página estiver pronta, a próxima etapa será publicá-la, para que usuários externos possam visualizar o conteúdo. Antes de publicar uma página, você deve fazer check-in selecionando **Concluir edição** na barra de comandos.

Você pode publicar e cancelar a publicação de páginas do inspetor ou do editor de páginas. O inspetor de páginas mostra uma lista de páginas e permite operações em massa. O editor de páginas pode ser usado para publicar ou cancelar a publicação apenas da única página aberta nela.

Para publicar uma ou mais páginas do inspetor de páginas, selecione as páginas, verifique se elas foram submetidas a check-in e, em seguida, selecione **Publicar** na barra de comandos. As páginas serão publicadas e você receberá uma notificação sobre a operação na ferramenta de criação.

Para publicar uma única página no editor de páginas, o procedimento é semelhante. Enquanto a página estiver aberta no editor de páginas, verifique se ela foi submetida a check-in e, em seguida, selecione **Publicar** na barra de comandos. A página será publicada e você receberá uma notificação sobre a operação.

Quando você publica uma página, apenas o conteúdo da página é publicado. Você e outros usuários podem acessar a página e visualizá-la somente depois que uma URL estiver associada a ela. A URL deverá ser publicada separadamente.

> [!IMPORTANT]
> Antes de poder publicar uma página, todas as imagens ou fragmentos mencionados pela página já devem ser publicados.

## <a name="save-preview-and-publish-a-home-page"></a>Salvar, visualizar e publicar uma home page

Para salvar, visualizar e publicar uma home page, siga estas etapas.

1. Em **Sites**, selecione **Fabrikam** (ou o nome do seu site).
1. No painel de navegação à esquerda, selecione **Páginas**.
1. Localize e selecione a home page para abri-la no editor de páginas.
1. Selecione **Editar**.
1. Modifique a página, como necessário.
1. Selecione **Salvar** e **Finalizar edição**.
1. No campo **Comentários** , insira uma observação sobre as alterações feitas e selecione **OK**.
1. Selecione **Visualizar** para exibir a página. Quando terminar, feche a guia de visualização para retornar à ferramenta de criação.
1. Selecione **Publicar**.

## <a name="publish-a-url"></a>Publicar uma URL

Para publicar uma URL, siga estas etapas.

1. Em **Sites**, selecione **Fabrikam** (ou o nome do seu site).
1. No painel de navegação à esquerda, selecione **URLs**.
1. Encontre e selecione a URL para publicar.
1. Na barra de comandos, selecione **Publicar**.

## <a name="additional-resources"></a>Recursos adicionais

[Modificar uma página de site existente](modify-existing-page.md)

[Adicionar uma nova página do site](add-new-page.md)

[Selecionar layouts de página](select-page-layouts.md)

[Gerenciar metadados de SEO](manage-seo-metadata.md)

[Enriquecer uma página de produto](enrich-product-page.md)

[Enriquecer uma página de aterrissagem da categoria](enrich-category-page.md)

[Verificar acessibilidade do conteúdo da página](verify-accessibility.md)

[Criar páginas dinâmicas de comércio eletrônico com base nos parâmetros da URL](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

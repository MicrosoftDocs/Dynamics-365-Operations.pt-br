---
title: Trabalhar com layouts predefinidos
description: Este artigo descreve como trabalhar com layouts predefinidos no Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 02/03/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: b588df5702657f07e1e790ffba39d2e459901557
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286267"
---
# <a name="work-with-preset-layouts"></a>Trabalhar com layouts predefinidos

[!include [banner](includes/banner.md)]

Este artigo descreve como trabalhar com layouts predefinidos no Microsoft Dynamics 365 Commerce.

Antes de concluir os procedimentos neste artigo, não deixe de ler [Layouts predefinidos e personalizados](templates-layouts-overview.md#preset-and-custom-layouts). Para obter uma visão geral, consulte [Visão geral de modelos e layouts](templates-layouts-overview.md).

## <a name="create-a-new-preset-layout"></a>Criar um novo layout predefinido

Há dois métodos para criar um layout predefinido. Você pode salvar um layout personalizado existente como um novo layout predefinido, ou criar um layout predefinido a partir do zero.

### <a name="create-a-preset-layout-from-an-existing-custom-layout"></a>Crie um layout predefinido de um layout personalizado existente

Para criar um layout predefinido de um layout personalizado existente, siga estas etapas.

1. Abra uma página existente que atualmente não use um layout predefinido e que tenha uma estrutura de módulo que você deseja reutilizar para outras páginas do seu site.
1. Selecione **Editar** para verificar a página.
1. Selecione **Salvar como novo layout**. A caixa de diálogo **Salvar como novo layout** será exibida.
1. Digite um nome e uma descrição para seu layout predefinido. Os valores que você inserir serão mostrados a outros autores quando eles criarem novas páginas do seu layout ou mudarem para ele. Portanto, insira valores que serão úteis para os criadores de página.
1. Selecione **OK**.

O layout predefinido agora estará disponível quando você criar novas páginas ou selecionar um layout diferente para uma página na mesma hierarquia de modelo.

> [!TIP]
> Para ver rapidamente se uma página específica está atualmente vinculada a um layout predefinido, selecione a página na exibição de lista de páginas e inspecione os metadados do layout no painel de propriedades à direita.

### <a name="create-a-new-preset-layout"></a>Criar um novo layout predefinido

Para criar um layout predefinido do zero, siga estas etapas.

1. No painel de navegação à esquerda, selecione **Layouts**.
1. Selecione **Novo Layout**. A caixa de diálogo **Novo layout** será exibida.
1. Selecione o modelo a ser usado para o layout predefinido.
1. Digite um nome e uma descrição para seu layout predefinido. Os valores que você inserir serão mostrados a outros autores quando eles criarem novas páginas do seu layout ou mudarem para ele. Portanto, insira valores que serão úteis para os criadores de página.
1. Selecione **OK** para criar o novo layout predefinido e abrir o editor de layout.
1. No editor de layout, adicione e configure módulos usando a árvore de estrutura de tópicos à esquerda e o painel de propriedades à direita. (O processo se assemelha ao processo de adição e configuração de módulos para um modelo no editor de modelos.) A organização dos módulos e quaisquer configurações padrão bloqueadas tornam-se a configuração centralizada do módulo para todas as páginas que usam esse layout predefinido.

## <a name="modify-a-preset-layout"></a>Modifique um layout predefinido

Para modificar um layout predefinido, siga estas etapas.

1. No painel de navegação à esquerda, selecione **Layouts**.
1. No editor do layout, na árvore de estrutura de tópicos à esquerda, selecione o módulo para alterar. Em seguida, siga quaisquer uma dessas etapas:

    - Para mover um módulo para cima ou para baixo dentro de seu pai, selecione o botão de reticências (**...**) do módulo e selecione **Mover para cima** ou **Mover para baixo**.
    - Para alterar as configurações padrão de um módulo, use o painel de propriedades para inserir valores padrão e para bloquear-los opcionalmente para todas as páginas downstream.
    - Para adicionar novos módulos ou fragmentos aos módulos de contêiner, selecione o botão de reticências e selecione **Adicionar módulo** ou **Adicionar fragmento**.
    - Para remover um módulo do layout, selecione o botão de reticências e depois **Excluir**.

## <a name="change-a-preset-layout-theme"></a>Alterar um tema predefinido de layout

Uma prática comum é definir um tema padrão para todas as páginas com um layout predefinido.

Para definir ou alterar um tema para todas as páginas filho com o layout predefinido, siga estas etapas.

1. No editor do layout, na árvore de estrutura de tópicos à esquerda, selecione o módulo de contêiner. (Normalmente, este módulo é o segundo nó e é chamado **Página padrão**.)
1. No campo **Tema**, do painel de propriedades à direita, selecione um tema.

## <a name="save-check-in-preview-and-publish-a-preset-layout"></a>Salvar, fazer check-in, visualizar e publicar um layout predefinido

Para salvar e fazer check-in do layout predefinido, siga estas etapas.

1. Selecione **Salvar** na parte superior do editor do layout. As alterações salvas não afetam as páginas downstream até o check-in.
1. Selecione **Concluir edição**. Suas alterações agora são detectáveis para fluxos de trabalho downstream.

Para visualizar as alterações, abra uma página existente que usa o layout predefinido ou crie uma nova página do layout.

Depois que você visualizou alterações no layout predefinido, siga uma dessas etapas para publicar o layout em seu site ativo:

1. Acesse **Layouts**, selecione o layout depois **Publicar**.
1. Selecione o nome do layout para abrir o editor de layout e selecione **Publicar**.
1. Publicar uma página que faça referência ao layout não publicado. O layout será publicado automaticamente.

> [!WARNING]
> Os layouts predefinidos podem ser referenciados a várias páginas. Quando você publica um layout predefinido, saiba que pode afetar o layout de várias páginas.

## <a name="rename-a-preset-layout"></a>Renomeie um layout predefinido

Para renomear um layout predefinido no construtor de sites, siga estas etapas.

1. No painel de navegação à esquerda, selecione **Layouts**.
1. Selecione o nome do layout que você deseja renomear.
1. Selecione **Editar** para iniciar a edição do layout.
1. No painel de propriedades do layout, selecione o símbolo da caneta ao lado do nome do layout.
1. Edite o nome do layout, conforme necessário.
1. Marque a caixa de seleção para confirmar a alteração do nome.
1. Selecione **Concluir edição**.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de modelos e layouts](templates-layouts-overview.md)

[Trabalhar com modelos](work-with-templates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

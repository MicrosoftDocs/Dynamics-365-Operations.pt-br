---
title: Trabalhar com fragmentos
description: Este tópico descreve por que, quando e como usar fragmentos no Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: retail
ms.author: phinneyridge
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 7ae834f38fe380ce0a66f5b1968f1261af670979
ms.sourcegitcommit: 078befcd7f3531073ab2c08b365bcf132d6477b0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/31/2020
ms.locfileid: "3645982"
---
# <a name="work-with-fragments"></a>Trabalhar com fragmentos 

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Este tópico descreve por que, quando e como usar fragmentos no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

Os fragmentos permitem uma experiência de criação centralizada para configurações de módulos que devem ser reutilizadas em todo o site. Por exemplo, cabeçalhos, rodapés e banners geralmente são configurados como fragmentos, porque são compartilhados em várias páginas. Você pode pensar em fragmentos como páginas da Web em miniatura que podem ser inseridas em outras páginas do seu site. Os fragmentos têm seu próprio ciclo de vida. Em outras palavras, eles são criados, referenciados, atualizados e excluídos como entidades independentes nas ferramentas de criação.

Após a configuração dos fragmentos, eles podem ser usados sempre que os módulos puderem ser usados na estrutura do site. Os fragmentos podem ser referenciados em páginas, layouts, modelos e em outros fragmentos.

> [!NOTE]
> Os fragmentos podem ser aninhados até sete níveis dentro de outros fragmentos.

Por exemplo, se quiser promover um evento sazonal em muitas páginas do site, você pode usar um fragmento. A primeira etapa no processo de criação de um novo fragmento é selecionar o tipo de módulo que você deseja iniciar. Neste exemplo, você pode construir o fragmento a partir de um módulo herói.

> [!NOTE]
> Os fragmentos podem ser criados em qualquer tipo de módulo.

É possível configurar o fragmento de herói com seu conteúdo promocional específico. Você também pode localizá-lo, conforme necessário. O novo fragmento de herói independente pode ser consumido como um módulo pré-configurado em todo o site. Você pode adicioná-lo facilmente a modelos, páginas específicas ou outros fragmentos que podem conter módulos de heróis.

Todos os locais onde o fragmento é adicionado são referências ao fragmento de herói central que você criou. Se você publicar alterações no fragmento, essas alterações serão refletidas imediatamente em todos os locais em que o fragmento é referenciado no site. Portanto, os fragmentos fornecem uma maneira poderosa e eficiente de reutilizar e gerenciar centralmente as configurações dos módulos em um site. Ao usá-los efetivamente, você pode aumentar significativamente a agilidade e ajudar a reduzir o custo associado ao gerenciamento do conteúdo do site.

A ilustração a seguir mostra como os fragmentos podem ser usados para centralizar a criação das configurações de módulo compartilhadas através de um site de Comércio eletrônico.

![Uma ilustração que mostra como os fragmentos podem ser usados para centralizar a criação de configurações de módulos compartilhados em um site de Comércio eletrônico](./media/fragment-figure1.png)

## <a name="create-a-fragment"></a>Criar um fragmento

Você pode criar um novo fragmento ou salvar uma configuração de módulo existente como um fragmento.

### <a name="save-an-existing-module-configuration-as-a-fragment"></a>Salvar uma configuração de módulo existente como um fragmento

Para converter um módulo configurado anteriormente a um fragmento reutilizável, siga estas etapas.

1. Abra uma página ou modelo que contém o módulo que você deseja converter em um fragmento.
1. No painel de estrutura de tópicos à esquerda ou diretamente na tela principal, selecione o módulo configurado anteriormente.
1. Selecione as reticências (**...**) ao lado do nome do módulo no painel de estrutura de tópicos ou na barra de ferramentas do módulo selecionado na tela. 
1. Selecione **Compartilhar como Fragmento de Página**. 
1. Na caixa de diálogo **Salvar como Fragmento de Página**, insira um nome para o fragmento.
1. Selecione **OK** para salvar a configuração do módulo como um fragmento que possa ser adicionado a outras páginas.

A imagem a seguir mostra como salvar uma configuração de módulo como fragmento.

![Uma captura de tela de como salvar uma configuração de módulo como fragmento](./media/save-as-fragment.png)

### <a name="create-a-new-fragment"></a>Criar um novo documento

Para criar um novo fragmento, siga estas etapas.

1. No painel de navegação à esquerda, selecione **Fragmentos**.
1. Selecione **Novo Fragmento da Página**. É exibida uma caixa de diálogo que mostra todos os tipos de módulo disponíveis. Como mencionado anteriormente, os fragmentos podem ser criados de qualquer tipo de módulo.
1. Selecione um tipo de módulo para o fragmento.

A imagem a seguir mostra onde criar um novo fragmento.

![Uma captura de tela de onde criar um novo fragmento](./media/fragment-nav-menu.png)

> [!TIP]
> Ao selecionar um tipo de módulo de contêiner genérico, você obtém maior flexibilidade quando precisar atualizar e configurar seu fragmento posteriormente.

## <a name="add-remove-or-edit-fragments-on-a-page"></a>Adicionar, remover ou editar fragmentos em uma página

Os procedimentos a seguir descrevem como adicionar, remover e edite fragmentos.

### <a name="add-a-fragment"></a>Adicionar um fragmento

Para adicionar um fragmento a uma página, siga estas etapas.

1. No painel de estrutura de tópicos à esquerda ou diretamente na tela principal, selecione um contêiner ou slot ao qual os módulos filho possam ser adicionados.
1. No painel online, selecione as reticências (**...**) ao lado do nome do contêiner ou slot.  Como alternativa, se usar a tela principal, selecione o símbolo de adição (**+**).  
1. Selecione **Adicionar Fragmento**.

    ![Uma captura de tela de como adicionar um fragmento existente a um slot ou contêiner](./media/add-fragment.png)
 
    > [!NOTE]
    > Se o contêiner ou slot não suportar novos módulos filhos, a opção **Adicionar Fragmento** não ficará disponível.
    
1. Na caixa de diálogo **Adicionar Fragmento**, procure e selecione um fragmento a ser adicionado. Se nenhum fragmento disponível estiver listado, você poderá primeiro criar um fragmento a partir de um tipo de módulo suportado pelo contêiner ou slot selecionado.
1. Selecione o fragmento desejado para adicionar ao contêiner ou ao slot na sua página.

    ![Uma captura de tela da janela modal do seletor de fragmento](./media/fragment-picker.png)

> [!NOTE]
> Os módulos permitidos em um contêiner ou slot são definidos pelo modelo da página ou pelas próprias definições dos módulos.

### <a name="remove-a-fragment"></a>Remova um fragmento

Para remover um fragmento de um slot ou contêiner em uma página, siga estas etapas.

1. No painel de estrutura de tópicos à esquerda, selecione as reticências (**...**) ao lado do nome do fragmento a ser removido e, depois, selecione o símbolo de lixeira.  Como alternativa, você pode selecionar o fragmento na tela e selecionar o símbolo de lixeira na barra de ferramentas do fragmento.
1. Quando for solicitado para confirmar se você deseja remover o fragmento, selecione **OK**.

> [!NOTE]
> Ao remover um fragmento de uma página, você apenas remove a referência a ele dessa página. Você **não** exclui o fragmento de seu site. Para excluir fragmentos de seu site, você deve usar a interface de usuário (UI) do inspetor de fragmento. Você pode excluir fragmentos do site apenas se não forem referidos atualmente por quaisquer páginas, modelos, ou por outros fragmentos.

### <a name="edit-a-fragment"></a>Editar um fragmento

Para editar fragmentos, você deve usar a interface de usuário do editor de fragmento. Esta restrição é por design. Isso ajuda a garantir que os autores não confundam o processo de edição dos módulos de uma página específica com o processo de edição de fragmentos que podem ser compartilhados em várias páginas.

Para editar um fragmento, siga estas etapas.

1. No painel de navegação à esquerda, selecione **Fragmentos**.
1. Em **Fragmentos**, selecione o fragmento para editar.
1. Edite as propriedades e a estrutura do módulo do fragmento, conforme necessário. O processo se assemelha ao processo de edição dos módulos que são editados na visualização do editor de páginas.

Você também pode editar um fragmento selecionando-o em uma página, em um modelo ou em um fragmento pai e, em seguida, selecionando **Editar Fragmento** no painel propriedades à direita.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de modelos e layouts](templates-layouts-overview.md)

[Trabalhar com modelos](work-with-templates.md)

[Trabalhar com layouts predefinidos](work-with-layouts.md)

[Trabalhar com grupos de publicações](publish-groups.md)

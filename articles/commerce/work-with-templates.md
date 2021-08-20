---
title: Trabalhar com modelos
description: Este tópico descreve como trabalhar com modelos no Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: f9487ab7a6ea10c841708e41fb7085d4bafe0d224ec5eb28810ec34b35a0ebc0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6762515"
---
# <a name="work-with-templates"></a>Trabalhar com modelos

[!include [banner](includes/banner.md)]

Este tópico descreve como trabalhar com modelos no Microsoft Dynamics 365 Commerce.

Conforme discutido em [Visão geral de modelos e layouts](templates-layouts-overview.md), modelos definem o conjunto de opções disponíveis para autores downstream. Os modelos são úteis para a equipe de criação na Web de uma empresa por vários motivos, e modelos bem estruturados podem ajudar com todos os seguintes objetivos:

- Simplifique a experiência de criação para funções diárias do editor de conteúdo.

    - Filtre as opções do módulo para que apenas os módulos relevantes sejam mostrados para uma seção específica da página. (Por exemplo, uma seção de marketing de um modelo pode ser configurada para filtrar módulos irrelevantes que nunca devem ser usados nesse contexto e que apenas complicarão as tarefas de criação de conteúdo, se forem mostrados).
    - Configure a definição do módulo padrão para ajudar a melhorar a eficiência da criação.
    - Defina fragmentos de página padrão para ajudar a aumentar a eficiência de criação. (Por exemplo, os fragmentos de cabeçalho e rodapé em um modelo aparecerão automaticamente na página downstream).

- Mantenha os sites corporativos na marca definindo um conjunto de opções de configuração e organização aprovadas.

    > [!TIP] 
    > Sites de comércio eletrônico bem-sucedidos fornecem aos clientes padrões de design familiares, repetitivo e de experiência do usuário (UX) na marca. Ao usar modelos, você ajuda a controlar a consistência em todo o site.

- Melhore as pontuações de otimização de mecanismo de pesquisa (SEO), garantindo definições de páginas e metadados de repetitivos e definidos por programação.

> [!NOTE]
> Embora os modelos sejam projetados para controlar a consistência em um site, eles podem ser configurados teoricamente para não impor nenhuma consistência. Os administradores de marca e site podem definir qualquer nível de variabilidade para as páginas em seu site. Por exemplo, um modelo pode ser deixado totalmente aberto, para que os autores do conteúdo possam criar qualquer design de página que escolherem. Nesse caso, nenhum dos benefícios na lista anterior é aplicável.

## <a name="modify-a-template"></a>Modificar um modelo

Os modelos são modificados no editor de modelo.

Para abrir o editor de modelo, siga uma dessas etapas:

- No painel de navegação de site, selecione **Modelos** e o modelo a ser alterado.
- No editor de páginas de uma página existente, selecione o nó superior na árvore de estrutura de tópicos à esquerda. Em seguida, no painel de propriedades à direita, selecione **Editar Modelo**.

A exibição em árvore de estrutura de tópicos à esquerda mostra as opções e estruturas do módulo disponíveis para layouts e páginas filho. Ao selecionar um módulo na árvore de estrutura de tópicos, é possível visualizar as propriedades do modelo para o módulo selecionado no painel de propriedades à direita. Algumas dessas propriedades são exclusivas para edição do modelo. A tabela a seguir descreve essas propriedades.

| Nome da propriedade | Descrição |
|---|---|
| Ocorre o Mínimo | Esta propriedade define o número mínimo de ocorrências para o módulo selecionado. Por exemplo, se o valor estiver definido como **1**, o módulo será necessário para autores downstream, enquanto que se o valor estiver definido como **0** (zero), o módulo será opcional. |
| Ocorre o Máximo | Esta propriedade define o número máximo de ocorrências para o módulo selecionado. Por exemplo, se o valor for definido como **1**, o módulo poderá ser adicionado somente uma vez. |
| Número Mín. de Módulos (Contêineres) | Para módulos que contêm outros módulos (isto é, para *módulos de contêineres*), essa propriedade define o número mínimo de módulos totais que devem ser adicionados como filhos. Por exemplo, para um módulo de carrossel, o valor pode ser definido como um número maior que 1. |
| Número Máx. de Módulos (Contêineres) | Para módulos de contêiner, essa propriedade define o número máximo de módulos totais que devem ser adicionados como filhos. Por exemplo, para um módulo de carrossel, o valor pode ser definido como um número menor que 10. |
| Bloqueada | Um controle booliano **Bloqueado** aparece ao lado de todas as propriedades do módulo principal. Ele permite que o autor do modelo bloqueie uma configuração de módulo no modelo. Uma configuração de módulo bloqueada não pode ser substituída por layouts ou páginas filho. Torna-se um valor de propriedade editável centralmente para todos os layouts e páginas que usam o modelo. |

## <a name="create-a-new-template"></a>Criar um novo modelo

Para criar um novo modelo, siga estas etapas.

1. No painel de navegação de site, selecione **Modelos** para a exibição do inspetor do modelo.
1. Selecione **Novo Modelo**.
1. Na caixa de diálogo de criação do modelo, insira um nome e uma descrição para o modelo. Os valores inseridos serão mostrados aos autores quando eles criarem novas páginas. Portanto, insira metadados que serão úteis para os criadores de página. Por exemplo, digite **Use este modelo para criar páginas gerais marketing** como a descrição. Esses metadados podem ser editados posteriormente.
1. Selecione **OK** para criar o novo modelo e abrir o editor de modelos. O editor de modelo mostra uma árvore da estrutura de tópicos à esquerda e o painel de propriedade à direita.
1. Na árvore de estrutura de tópicos, expanda os nós e selecione o slot **Head do HTML**.
1. Se ainda não houver nenhum módulo neste slot, selecione o botão de reticências (**...**) e depois **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione **Resumo da página padrão** e depois **OK**.
1. Na árvore de estrutura de tópicos, selecione o novo módulo e, no painel de propriedades, insira as configurações padrão que devem ser definidas automaticamente para todas as páginas filho do modelo. Se você não quiser configurações padrão, deixe os valores em branco.
1. Na árvore de estrutura de tópicos, selecione o slot **Corpo**, o botão de reticências e depois **Adicionar Módulo**.
1. Selecione um módulo de contêiner da página (pode haver apenas uma opção) e depois **OK**.

No novo módulo de contêiner de páginas, você verá um novo conjunto de slots (**Cabeçalho**, **Principal** etc). Aqui, você pode adicionar e configurar as opções do módulo que estarão disponíveis para os autores quando eles criarem páginas deste modelo. Por padrão, se você não adicionar nenhum módulo a um slot, todos os tipos de módulos disponíveis serão suportados para esse slot.

Por padrão, se você não adicionar nenhum módulo a um slot, todos os tipos de módulos disponíveis serão utilizados para esse slot. No entanto, as próximas três seções descrevem algumas outras configurações padrão que você pode querer definir primeiro.

## <a name="add-a-header-and-a-footer"></a>Adicionar um cabeçalho e um rodapé

Se o seu site já tiver um fragmento de cabeçalho, siga estas etapas para adicionar um cabeçalho e rodapé a um modelo.

1. Na árvore de estrutura de tópicos, expanda o slot **Corpo** e seu módulo de página filho.
1. Selecione o slot **Cabeçalho**.
1. Selecione o botão de reticência para o slot **Cabeçalho** e depois **Adicionar Fragmento**.
1. Pesquise e selecione o fragmento de cabeçalho do seu site e selecione **OK**.

Todas as páginas que usam o modelo agora herdarão automaticamente esse fragmento de cabeçalho.

Se seu site ainda não possui um fragmento de cabeçalho, consulte [Criar um fragmento](work-with-fragments.md#create-a-fragment) para obter informações sobre como criá-lo e, em seguida, concluir o procedimento anterior.

## <a name="change-the-template-theme"></a>Alterar o tema do modelo

Para definir o tema padrão de todas as páginas que usam um modelo, siga estas etapas.

1. Na árvore de estrutura de tópicos à esquerda, expanda o slot **Corpo**.
1. No slot **Corpo** selecione o módulo de contêiner de página (por exemplo, , **Página Padrão**).
1. No painel de propriedade à direita, no campo **Tema** , selecione um tema.

Por padrão, todas as novas páginas agora usarão o tema selecionado. Para impedir que as páginas substituam essa configuração no layout ou no nível da página, defina o controle booliano **Bloqueado** como **Verdadeiro**.

## <a name="add-a-script-to-a-template"></a>Adicionar um script a um modelo

Você pode adicionar elementos de **&lt;script&gt;** HTML que contenham JavaScript em seu modelo. Dessa forma, você pode fornecer comportamentos de script padrão para as seções de cabeçalho, início do corpo e final do corpo de suas páginas.

Para adicionar um script a um modelo, siga estas etapas.

1. Na árvore de estrutura de tópicos à esquerda, selecione o slot no qual deseja adicionar o elemento **&lt;script&gt;** (por exemplo, o cabeçalho HTML, início do corpo ou fim do corpo).
1. Selecione o botão de reticências do slot e depois selecione **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione um módulo de script (por exemplo, **Script Externo** ou **Script Embutido**).
1. No painel de propriedades à direita, no controle de propriedade de script apropriado (por exemplo, **Script Embutido** ou **Marcas de script**), digite seu script.
1. No painel de propriedades, insira outras configurações opcionais que você deseja definir.

> [!TIP]
> Se você quiser reutilizar qualquer um dos seus módulos de script para outros modelos, poderá convertê-los em fragmentos. Dessa maneira, você ajuda a tornar o processo de criação mais eficiente e centraliza o processo de atualização. Para obter informações sobre como converter um módulo de script em um fragmento, consulte [Salvar uma configuração de módulo existente como um fragmento](work-with-fragments.md#save-an-existing-module-configuration-as-a-fragment).

## <a name="save-check-in-preview-and-publish-a-template"></a>Salvar, fazer check-in, visualizar e publicar um modelo

Para salvar e fazer check-in em um modelo, siga estas etapas.

1. Selecione **Salvar** na parte superior do editor de modelos. As alterações salvas não afetam as páginas downstream até o check-in.
1. Selecione **Concluir edição**. Suas alterações agora são detectáveis para fluxos de trabalho downstream.

Para visualizar as alterações, abra uma página existente que usa o modelo ou crie uma nova página do modelo.

Depois que você visualizou alterações no modelo, siga uma dessas etapas para publicar o modelo em seu site ativo:

* Acesse **Modelos**, selecione o modelo e depois **Publicar**.
* Selecione o nome do layout para abrir o editor de layout e selecione **Publicar**.
* Publicar uma página que faça referência ao modelo não publicado. O modelo será publicado automaticamente.

> [!WARNING]
> Quando um modelo ou qualquer outro item do sistema de gerenciamento de conteúdo (CMS) é publicado, ele pode ser descoberto na Internet. Não publique documentos ou ativos até estar pronto para publicá-los. As versões do documento que foram salvas e registradas, mas que não foram publicadas, são detectáveis apenas para usuários do sistema autenticados.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de modelos e layouts](templates-layouts-overview.md)

[Trabalhar com layouts predefinidos](work-with-layouts.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

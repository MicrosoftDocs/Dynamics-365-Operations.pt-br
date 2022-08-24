---
title: Criar uma URL da página
description: Este artigo cobre conceitos básicos e os procedimentos para criar uma página na URL do site.
author: bicyclingfool
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 8718a3a2854ecdc7aec0853569dcba9e26a86d67
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270145"
---
# <a name="create-a-page-url"></a>Criar uma URL da página

[!include [banner](includes/banner.md)]

Este artigo cobre conceitos básicos e os procedimentos para criar uma página na URL do site.

A URL total ou absoluta que aponta para uma página no site consiste em partes diferentes. Por exemplo, a URL `https://www.contoso.com/en-us/contactus` tem as seguintes partes:

- `https://www.contoso.com` – O protocolo do HTTP e o domínio do site.
- `/en-us` – O caminho de idioma do site.
- `/contactus` – A URL relacionada à página  **Fale conosco**. Uma URL relacionada também é conhecida como uma URL *Campo de dados dinâmico*.

Você estabelece o domínio do site e o caminho opcional do idioma quando configura o site. Você pode adicionar mais domínios e caminhos de idioma ao site por meio da página de armazenamento online nas configurações do site.

A URL de Campo de dados dinâmico de uma página existe como uma entidade autônoma no ambiente de criação do site. Uma página de URL é feita de duas partes: um nome que representa o Campo de dados dinâmico da URL e um ponteiro a uma página em seu site ou em um site externo. Uma página URL também pode ser configurada para agir como um redirecionamento a outra página em seu site ou em um site externo.

## <a name="create-a-page-url"></a>Criar uma URL da página

Há duas maneiras de criar a URLs de página:

- Automaticamente, quando você cria uma página
- Manualmente, da página de **URLs**

### <a name="create-a-page-url-when-you-create-a-page"></a>Crie uma URL da página ao criar uma página

Se fornecer um nome no campo **URL** quando você cria uma nova página, uma URL de página que aponta para essa página será criada automaticamente na **URL**. Após publicar a URL e a página que a redireciona, os usuários de sites (os clientes) podem acessar a página associada à URL.

> [!NOTE]
> Se você um publica uma URL sem publicar a página que redireciona, os usuários recebem um erro 404 quando tentar acessar a página. Se você publicar páginas sem publicar a URL que a redireciona, a página não pode ser acessada usando uma URL.

### <a name="manually-create-a-page-url"></a>Crie manualmente uma URL da página

Quando você cria novas páginas, não é necessário especificar uma URL da página. Se você deixar o campo da URL em branco, a página é criada em um estado não vinculado. Nesse caso, os clientes não poderão acessar a página, mesmo se estiver publicada. Para tornar a página acessível, você deverá criar manualmente a URL e vinculá-lo a página.

Para criar manualmente a URL de página para uma página, siga estas etapas.

1. Na página **URLs**, selecione **Novo**.
1. Selecione a página do site para associar com a URL.
1. Insira a URL de Campo de dados dinâmico e depois selecione **OK**.

Nesse momento, a URL em um estado de rascunho. Deve ser publicada antes que os usuários possam acessar o site da página associada.

## <a name="update-a-page-url"></a>Atualizar uma URL da página

Para atualizar a página de destino de uma URL de página, siga estas etapas.

1. Na página de **URLs**, selecione a URL para atualizar.
1. No painel de propriedade à direita, selecione o botão de reticências (**...**) ao lado do campo da página de destino.
1. Na caixa de diálogo, selecione uma página diferente e depois **OK**.
1. Salvar e publicar a URL.

## <a name="redirect-a-page-url"></a>Redirecionar uma URL de página

Certas vezes, você pode desejar que seus clientes vejam uma página diferente quando solicitam uma URL específica. Nesses casos, a melhor e mais fácil abordagem é mudar a página para a qual a URL aponta. Entretanto, você pode ter motivos legítimos para usar os redirecionamentos do HTTP 301 ou 3023 para redirecionar solicitações de um a URL uma URL diferente.

Para redirecionar uma URL a uma URL diferente, siga essas etapas.

1. Na página de **URLs**, selecione a URL para atualizar.
1. No painel de propriedade à direita, selecione **Redirecionar**.
1. Selecione um destino para redirecionar:

    - Para apontar para outra página em seu site, selecione **URL interna**, selecione o botão de reticências (**…**), e a URL para redirecionar para.
    - Para apontar a uma página em um site externo, selecione **URL externa**, e depois insira a URL completa dessa página. Não se esqueça de incluir o protocolo. Por exemplo, insira `https://domain.com/new/page`. Se a URL já redireciona para uma URL interna, você deve selecionar **Limpar seleção** antes de inserir uma URL externa.

1. Selecionar um tipo de redirecionamento:

    - **Redirecionamento permanente (301)** – Selecione esta opção quando você sabe que o conteúdo está se movendo permanentemente e não reverterá à URL anterior. Os mecanismos de pesquisa atribuirão o valor de otimização de mecanismo de pesquisa (SEO) da URL de redirecionamento à URL que está sendo redirecionada e atualizará seu registro para exibir a nova URL. 
    - **Redirecionamento temporário (302)** – Selecione esta opção para redirecionar o tráfego sem atualizar os mecanismos de pesquisa. Esta abordagem é normalmente usada se o conteúdo reverterá logo à URL anterior.

1. Quando estiver pronto para implementar redirecionar, salve e publique a URL.

## <a name="additional-resources"></a>Recursos adicionais

[Personalizar a navegação do site](customize-site-navigation.md)

[Adicionar uma nova página do site](add-new-page.md)

[Configure seu nome de domínio](configure-your-domain-name.md)

[Adicionar idiomas ao seu site](add-languages-to-site.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

---
title: Habilitar e usar o compartilhamento entre canais
description: Este tópico descreve como habilitar e usar o recurso de compartilhamento entre canais do construtor de sites do Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 987dca54e47b909014862e310aa424019d8c4677
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5207814"
---
# <a name="enable-and-use-cross-channel-sharing"></a>Habilitar e usar o compartilhamento entre canais

[!include [banner](includes/banner.md)]

Este tópico descreve como habilitar e usar o recurso de compartilhamento entre canais do construtor de sites do Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão Geral

O compartilhamento entre canais permite reutilizar e compartilhar conteúdo entre vários canais de um site. Esse recurso é útil quando os canais de site têm um idioma base compatível, ou quando têm vários itens de conteúdo em comum.

O compartilhamento entre canais permite habilitar um canal padrão que será pesquisado quanto ao conteúdo disponível quando uma versão de canal específica do conteúdo solicitado não for encontrada. O conteúdo que deve ser compartilhado entre canais é criado no canal padrão. Esse conteúdo pode ser localizado para qualquer localidade usada em qualquer canal de site.

## <a name="when-to-use-cross-channel-sharing"></a>Quando usar o compartilhamento entre canais

O compartilhamento entre canais é útil quando vários canais em um único site podem compartilhar conteúdo. Por exemplo, um varejista que tem várias marcas e lojas que são agrupadas em um único site pode compartilhar algum conteúdo entre algumas ou todas as lojas. Esse conteúdo compartilhado pode incluir páginas para termos e condições, condições de pagamento, métodos de remessa e perguntas frequentes (FAQ).

O compartilhamento entre canais também oferece suporte a fragmentos. Portanto, uma página de conteúdo que contém fragmentos específicos do canal pode ser criada como conteúdo entre canais. Nesse caso, embora a maior parte do conteúdo seja compartilhada entre canais, os fragmentos específicos do canal em uma página de canal cruzado serão processados apenas quando forem solicitados do canal de loja correspondente.

Os sites que têm apenas um canal ou sites que possuem vários canais que não podem compartilhar conteúdo não se beneficiarão do compartilhamento entre canais.

## <a name="enable-cross-channel-sharing"></a>Habilitar o compartilhamento entre canais

O compartilhamento entre canais está habilitado no nível do site. Esta operação é unidirecional. Em outras palavras, depois que o compartilhamento entre canais for habilitado, ele não poderá ser desabilitado.

Para habilitar o compartilhamento entre canais no construtor de sites do Commerce, siga estas etapas.

1. Acesse **Configurações do site \> Recursos**.
1. Defina a opção para o recurso **Entre Canais** como **Ativado**.

    ![Opção Entre Canais definida como Ativado no construtor de sites do Commerce](./media/enabling-cross-channel-sharing.png)

Depois que você habilitar o compartilhamento entre canais, as informações entre canais aparecerão na seção **Canais** em **Configurações do site \> Recursos**, como mostra o exemplo na ilustração a seguir.

![Informações sobre canais visíveis após o compartilhamento entre canais ser habilitado](./media/channels-cross-channel.png)

Além disso, depois de habilitar o compartilhamento entre canais, o campo **Canal** no canto superior direito do construtor de sites do Commerce incluirá uma opção **Loja Online Entre Canais** que pode ser usada para gerenciar conteúdo entre canais, conforme mostrado na ilustração a seguir.

![Opção Loja Online Entre Canais no campo Canais após o compartilhamento entre canais ser habilitado](./media/cross-channel-dropdown.png)

## <a name="create-and-use-cross-channel-content"></a>Criar e usar o conteúdo entre canais

Você pode criar e usar conteúdo entre canais de várias maneiras. Por exemplo, você pode criar fragmentos entre canais, criar páginas de canal cruzado que usam conteúdo entre canais e específicos de canais e substituir fragmentos entre canais com versões de fragmentos específicas de canais.

### <a name="create-a-cross-channel-fragment"></a>Criar um fragmento entre canais

Para criar um fragmento entre canais no construtor de sites do Commerce, siga estas etapas.

1. Vá para **Fragmentos** e selecione **Novo** para criar um novo fragmento.
1. Na caixa de diálogo **Novo fragmento de página**, selecione o módulo **Faixa promocional** e, em **Nome do fragmento**, insira um nome (por exemplo, **Faixa entre canais**). Em seguida, selecione **OK**.
1. No painel de propriedades do módulo **Faixa promocional**, selecione **Adicionar Mensagem** e, em seguida, selecione **Mensagem** .
1. Na caixa de diálogo **Mensagem**, em **Texto**, insira **Entre canais** e selecione **OK**. 
1. Selecione **Salvar**, **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.

Esse fragmento de canal cruzado pode ser usado em páginas de canal cruzado ou específicas de canal que são criadas em qualquer canal de site.

### <a name="create-a-cross-channel-page-that-uses-cross-channel-content"></a>Criar uma página entre canais que usa conteúdo entre canais

As páginas entre canais podem ser usadas em qualquer canal do site. Portanto, você pode criar uma página de conteúdo compartilhada uma vez e fazer as atualizações subsequentes em um único local. Por exemplo, uma página **Termos e condições** entre canais com a URL `/toc` pode ser compartilhada entre todos os canais de um site. Se as URLs de base para os canais de site forem `www.fabrikam.com/brand1` e `www.fabrikam.com/brand2`, a mesma página entre canais, a página **Termos e condições** compartilhada estará disponível nas duas URLs de canal de site, em `www.fabrikam.com/brand1/toc` e `www.fabrikam.com/brand2/toc`, respectivamente. Se a página **Termos e condições** precisar ser atualizada posteriormente, você terá que atualizar somente a página compartilhada única.

Para criar uma página entre canais no construtor de sites do Commerce que usa conteúdo entre canais, siga estas etapas.

1. Vá para **Páginas** e selecione **Novo** para criar uma nova página.
1. Na caixa de diálogo **Escolher um modelo**, selecione o modelo, como **Marketing**.
1. Em **Nome da página**, insira um nome para a página (por exemplo, **Página entre canais**).
1. Em **URL da Página**, insira uma URL de página (por exemplo, **examplepage**) e, em seguida, selecione **OK**.
1. No slot **Principal** da nova página, selecione as reticências (**...**) e, em seguida, selecione **Adicionar fragmento**.
1. Na caixa de diálogo **Adicionar fragmento**, selecione o fragmento entre canais criado anteriormente com uma faixa promocional e, em seguida, selecione **OK**.
1. Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página. Você verá a faixa promocional que diz "Entre canais".
1. Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.

### <a name="create-a-channel-specific-page-that-uses-cross-channel-content"></a>Criar uma página específica do canal que usa conteúdo entre canais

Usando o conteúdo entre canais em páginas específicas de canal, você pode criar um fragmento de conteúdo compartilhado uma vez e usá-lo em páginas específicas de canal. Essa "origem única" é útil para conteúdo compartilhado, como termos e condições, condições de pagamento ou informações de contato.

Para criar uma página específica do canal no construtor de sites do Commerce que usa conteúdo entre canais, siga estas etapas.

1. Em um canal específico, como a **loja online estendida da Fabrikam**, vá para **Páginas** e selecione **Novo** para criar uma nova página.
1. Na caixa de diálogo **Escolher um modelo**, selecione o modelo, como **Marketing**.
1. Em **Nome da página**, insira um nome para a página (por exemplo, **Página específica do canal**).
1. Em **URL da Página**, insira uma URL de página (por exemplo, **channelspecificpage**) e, em seguida, selecione **OK**.
1. No slot **Principal** da nova página, selecione as reticências (**...**) e, em seguida, selecione **Adicionar fragmento**.
1. Na caixa de diálogo **Adicionar fragmento** , em **Canal**, selecione **Loja Online Entre Canais**. O fragmento entre canais que você criou anteriormente deve aparecer na lista. Selecione-o e depois selecione **OK**.
1. Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página. Você verá a faixa promocional que diz "Entre canais".
1. Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.

### <a name="create-a-channel-specific-version-of-a-cross-channel-page"></a>Criar uma versão específica do canal de uma página entre canais

O compartilhamento entre canais oferece suporte a substituições de conteúdo entre canais. Por exemplo, todos exceto um dos canais de site compartilham o mesmo conteúdo. Que um canal de site requer conteúdo diferente. Para implementar o conteúdo diferente para ele, você poderá substituir o conteúdo entre canais por conteúdo específico do canal criando uma versão específica do canal da página entre canais.

Para criar uma versão específica do canal de uma página entre canais no construtor de sites do Commerce, siga estas etapas.

1. No campo **Canal**, no canto superior direito, selecione **Loja Online Entre Canais**.
1. Abra a página entre canais criada anteriormente.
1. No campo **Canal**, no canto superior direito, selecione o canal que deve ter um conteúdo específico. O editor de página mostra uma mensagem que solicita que você crie uma nova variante de página.
1. Selecione **Criar variante de página**.
1. No slot **Principal** da variante de página padrão, selecione as reticências (**...**) e, em seguida, **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Faixa promocional** e, depois, **OK**.
1. No painel de propriedades do módulo **Faixa promocional**, selecione **Adicionar Mensagem** e, em seguida, selecione **Mensagem** .
1. Na caixa de diálogo **Mensagem**, em **Texto**, insira **Específico do canal** e selecione **OK**.
1. Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página. Você verá a faixa promocional que diz "Específico do canal".
1. Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.

Agora, se você usar a URL base do canal e ir para a URL da página entre canais no site, verá o conteúdo específico do canal, em vez do conteúdo entre canais.

## <a name="additional-resources"></a>Recursos adicionais

[Maneiras de adicionar conteúdo](add-manage-content.md)

[Glossário do modelo de página](page-elements-overview.md)

[Estados de documento e de ciclo de vida](document-states-overview.md)

[Trabalhar com grupos de publicações](publish-groups.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
---
title: Módulo de cabeçalho
description: Este tópico abrange os módulos de cabeçalho e descreve como criar cabeçalhos de página no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/20/2020
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
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 52069af5ca2211473d4a096ad850b5be1290bba1
ms.sourcegitcommit: eee3523be26369aecdb36c0143a6ee3dab4b7966
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2020
ms.locfileid: "4410324"
---
# <a name="header-module"></a>Módulo de cabeçalho

[!include [banner](includes/banner.md)]

Este tópico abrange os módulos de cabeçalho e descreve como criar cabeçalhos de página no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão Geral

No Dynamics 365 Commerce, um cabeçalho de página é configurado como um fragmento de página que inclui os módulos de cabeçalho, faixa promocional e consentimento de cookie. 

O módulo de cabeçalho inclui um logotipo do site, links para a hierarquia de navegação, links para outras páginas do site, um módulo de ícone de carrinho, um símbolo de lista de desejos, opções de entrada e a barra de pesquisa. Um módulo de cabeçalho é otimizado automaticamente para o dispositivo onde o site está sendo exibido (ou seja, um dispositivo móvel ou de desktop). Por exemplo, em um dispositivo móvel, a barra de navegação é recolhida em um botão **Menu** (que é conhecido ocasionalmente como *menu hambúrguer*).

A imagem a seguir mostra um exemplo de um módulo de cabeçalho em uma home page.

![Exemplo de um módulo de cabeçalho](./media/ecommerce-header.png)

## <a name="properties-of-a-header-module"></a>Propriedades de um módulo de cabeçalho

Um módulo de cabeçalho oferece suporte às propriedades **Imagem de logotipo**, **Link de logotipo** e **Links da minha conta**. 

As propriedades **Imagem de logotipo** e **Link de logotipo** são usadas para definir um logotipo na página. Para obter mais informações, consulte [Adicionar um logotipo](add-logo.md). 

A propriedade **Links da minha conta** pode ser usada para definir as páginas da conta das quais o proprietário do site quer mostrar links rápidos no cabeçalho.

## <a name="modules-that-are-available-within-a-header-module"></a>Módulos disponíveis em um módulo de cabeçalho

Os módulos a seguir podem ser usados em um módulo de cabeçalho:

- **Menu de navegação** – O menu de navegação representa a hierarquia de navegação de canal e outros links estáticos de navegação. Para obter mais informações, consulte [Módulo do menu de navegação](nav-menu-module.md).

- **Pesquisa** – O módulo de pesquisa permite que os usuários insiram termos para procurar produtos. A URL da página de pesquisa padrão e os parâmetros de consulta de pesquisa devem ser fornecidos em **Configurações do Site \> Extensões**. O módulo de pesquisa tem propriedades que permitem suprimir o botão ou o rótulo de pesquisa, conforme necessário. O módulo de pesquisa também oferece suporte a opções de sugestão automática, como resultados de pesquisa por produtos, palavras-chave e categorias.

- **Ícone do carrinho** - O módulo de ícone do carrinho representa o ícone do carrinho, que mostra o número de itens no carrinho a qualquer momento. Para obter mais informações, consulte [Módulo de ícone de carrinho](cart-icon-module.md).

- **Seletor de site** — o módulo seletor de site permite que os usuários naveguem por diferentes sites predefinidos, com base no mercado, nas regiões e localidades. Para obter mais informações, consulte [Módulo de seletor de site](site-selector.md).

- **Seletor de loja** — o módulo seletor de loja pode ser incluído em um slot do seletor de loja do módulo de cabeçalho. Ele permite que os usuários procurem e encontrem lojas próximas. Os usuários também podem especificar uma loja preferida. Essa loja será mostrada no cabeçalho. Quando o módulo seletor de loja é incluído no módulo de cabeçalho, sua propriedade **Modo** deve ser definida como **Localizar lojas**. Para obter mais informações, consulte [Módulo de seletor de loja](store-selector.md).

> [!NOTE]
> - O suporte ao uso do módulo de ícone de carrinho nos módulos de cabeçalho está disponível no Dynamics 365 Commerce versão 10.0.11.
> - O suporte ao uso do módulo de ícone de selector de site nos módulos de cabeçalho está disponível no Dynamics 365 Commerce versão 10.0.14.
> - O suporte ao uso do módulo de ícone de selector de loja nos módulos de cabeçalho está disponível no Dynamics 365 Commerce versão 10.0.15.

## <a name="create-a-header-fragment-for-a-page"></a>Criar um fragmento de cabeçalho para uma página

Para criar um fragmento de cabeçalho, siga estas etapas.

1. Vá para **Fragmentos** e selecione **Novo** para criar um novo fragmento.
1. Na caixa de diálogo **Novo fragmento**, selecione o módulo **Contêiner**, insira um nome para o fragmento e, em seguida, selecione **OK**.
1. Selecione o slot **Contêiner padrão** e, no painel de propriedades à direita, defina a propriedade **Largura** como **Preencher Tela**.
1. No slot **Contêiner padrão**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione os módulos **Consentimento de cookie**, **Cabeçalho** e **Faixa promocional** e, em seguida, selecione **OK**.
1. No painel de propriedades do módulo **Faixa promocional**, selecione **Adicionar Mensagem** e, em seguida, selecione **Mensagem** .
1. Na caixa de diálogo **Mensagem**, adicione texto e links para o conteúdo promocional e, em seguida, selecione **OK**.
1. No painel de propriedades do módulo **Consentimento de cookie**, adicione e configure o texto e um link para a página de privacidade do site.
1. No slot **Menu de navegação** do módulo de cabeçalho, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Menu de navegação** e, depois, **OK**.
1. No painel de propriedades do módulo do menu de navegação, em **Origem do menu de navegação**, selecione **Retail Server**.
1. No painel de propriedades do módulo do menu de navegação, em **Itens de menu estático**, selecione **Adicionar item de menu** e, em seguida, selecione **Item de menu**. 
1. Na caixa de diálogo **Item de menu**, em **Texto do Item de Menu**, insira "Contato".
1. Na caixa de diálogo **Item de menu**, em **Destino do link do item de menu**, selecione **Adicionar um link**.
1. Na caixa de diálogo **Adicionar um link**, selecione a URL para a página "Contato" do site e, em seguida, selecione **OK**.  
1. Na caixa de diálogo **Item de menu**, selecione **OK**.
1. No slot **Pesquisar** do módulo de cabeçalho, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Pesquisar** e, depois, **OK**.
1. No painel de propriedades do módulo de pesquisa, configure as propriedades conforme necessário.
1. No slot **Ícone de carrinho** do módulo de cabeçalho, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo de **Ícone de carrinho** e, depois, **OK**.
1. No painel de propriedades do módulo de ícone de carrinho, configure as propriedades conforme necessário. Se desejar que o ícone de carrinho exiba um resumo de carrinho (também conhecido como um minicarrinho) quando os usuários passarem o mouse sobre ele, selecione **Mostrar minicarrinho**.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in do fragmento e depois selecione **Publicar** para publicá-lo.

Para ajudar a garantir que um cabeçalho apareça em todas as páginas, siga estas etapas em todos os modelos de página criados para o site.

1. No slot **Cabeçalho** do módulo **Página padrão**, adicione o fragmento de rodapé que você criou.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Módulo de contêiner](add-container-module.md)

[Módulo de ícone de carrinho](cart-icon-module.md)

[Módulo de banner de promoção](add-alert.md)

[Módulo do menu de navegação](nav-menu-module.md) 

[Consentimento de cookie](cookie-consent-module.md)

[Módulo de rodapé](author-footer-module.md)

[Módulo de seletor de site](site-selector.md)

[Módulo de seletor de loja](store-selector.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
---
title: Módulo de cabeçalho
description: Este artigo abrange os módulos de cabeçalho e descreve como criar cabeçalhos de página no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 63c298f36f64f2e107d3df3c0c5f3b6445546aa1
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275776"
---
# <a name="header-module"></a>Módulo de cabeçalho

[!include [banner](includes/banner.md)]

Este artigo abrange os módulos de cabeçalho e descreve como criar cabeçalhos de página no Microsoft Dynamics 365 Commerce.

No Dynamics 365 Commerce, um cabeçalho de página é configurado como um fragmento de página que inclui os módulos de cabeçalho, faixa promocional e consentimento de cookie. 

O módulo de cabeçalho inclui um logotipo do site, links para a hierarquia de navegação, links para outras páginas do site, um módulo de ícone de carrinho, um símbolo de lista de desejos, opções de entrada e a barra de pesquisa. Um módulo de cabeçalho é otimizado automaticamente para o dispositivo onde o site está sendo exibido (ou seja, um dispositivo móvel ou de desktop). Por exemplo, em um dispositivo móvel, a barra de navegação é recolhida em um botão **Menu** (que é conhecido ocasionalmente como *menu hambúrguer*).

A imagem a seguir mostra um exemplo de um módulo de cabeçalho em uma home page.

![Exemplo de um módulo de cabeçalho.](./media/ecommerce-header.png)

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
> - O suporte ao uso do módulo de ícone de carrinho nos módulos de cabeçalho está disponível a partir da versão 10.0.11 do Dynamics 365 Commerce.
> - O suporte ao uso do módulo de seletor de site nos módulos de cabeçalho está disponível a partir da versão 10.0.14 do Dynamics 365 Commerce.
> - O suporte ao uso do módulo de seletor de loja nos módulos de cabeçalho está disponível a partir da versão 10.0.15 do Dynamics 365 Commerce.

## <a name="header-module-in-the-adventure-works-theme"></a>Módulo de cabeçalho no tema Adventure Works

No tema Adventure Works, o módulo de cabeçalho oferece suporte à propriedade **Logotipo móvel**. Esta propriedade permite a especificação de um logotipo para portas de exibição móveis. A propriedade **Logotipo móvel** está disponível como uma extensão de definição de módulo.

> [!IMPORTANT]
> O tema Adventure Works está disponível a partir da versão 10.0.20 do Dynamics 365 Commerce.

## <a name="create-a-header-fragment-for-a-page"></a>Criar um fragmento de cabeçalho para uma página

Para criar um fragmento de cabeçalho, siga estas etapas.

1. Acesse **Fragmentos** e selecione **Novo** para criar um novo fragmento.
1. Na caixa de diálogo **Selecionar um fragmento**, selecione o módulo **Contêiner**, insira um nome para o fragmento e, depois, selecione **OK**.
1. Selecione o slot **Contêiner padrão** e, no painel de propriedades à direita, defina a propriedade **Largura** como **Preencher Tela**.
1. No slot **Contêiner padrão**, selecione as reticências (**...**) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione os módulos **Consentimento de cookie**, **Cabeçalho** e **Faixa promocional** e, depois, selecione **OK**.
1. No painel de propriedades do módulo **Faixa promocional**, selecione **Adicionar Mensagem** e, em seguida, selecione **Mensagem** .
1. Na caixa de diálogo **Mensagem**, adicione texto e links para o conteúdo promocional e, em seguida, selecione **OK**.
1. No painel de propriedades do módulo **Consentimento de cookie**, adicione e configure o texto e um link para a página de privacidade do site.
1. No slot **Menu de navegação** do módulo de cabeçalho, selecione as reticências (**...**) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Menu de navegação** e, depois, **OK**.
1. No painel de propriedades do módulo do menu de navegação, em **Origem do menu de navegação**, selecione **Retail Server**.
1. No painel de propriedades do módulo do menu de navegação, em **Itens de menu estático**, selecione **Adicionar item de menu** e, em seguida, selecione **Item de menu**. 
1. Na caixa de diálogo **Item de menu**, em **Texto do Item de Menu**, insira "Contato".
1. Na caixa de diálogo **Item de menu**, em **Destino do link do item de menu**, selecione **Adicionar um link**.
1. Na caixa de diálogo **Adicionar um link**, selecione a URL para a página "Contato" do site e, em seguida, selecione **OK**.  
1. Na caixa de diálogo **Item de menu**, selecione **OK**.
1. No slot **Pesquisar** do módulo de cabeçalho, selecione as reticências (**...**) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Pesquisar** e, depois, **OK**.
1. No painel de propriedades do módulo de pesquisa, configure as propriedades conforme necessário.
1. No slot **Ícone de carrinho** do módulo de cabeçalho, selecione as reticências (**...**) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Ícone de carrinho** e, depois, **OK**.
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

---
title: Módulo de seletor de catálogo
description: Este artigo aborda módulos de selecionador de catálogo e descreve como adicioná-los a sites de comércio eletrônico B2B (entre empresas) do Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 07/11/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2022-04-21
ms.openlocfilehash: 642319eea7e40415fd32898f6ec07bfc86f3b1b1
ms.sourcegitcommit: d1491362421bf2fcf72a81dc2dc2d13d3b98122b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2022
ms.locfileid: "9136936"
---
# <a name="catalog-picker-module"></a>Módulo de seletor de catálogo

[!include [banner](includes/banner.md)]

Este artigo aborda módulos de selecionador de catálogo e descreve como adicioná-los a sites de comércio eletrônico B2B (entre empresas) do Microsoft Dynamics 365 Commerce.

Um módulo de seletor de catálogo é um contêiner especial usado para listar todos os catálogos de produtos que estão disponíveis para os usuários do site B2B para compras. No momento, só há suporte para vários catálogos em sites B2B.

A ilustração a seguir mostra um exemplo de um módulo de seletor de catálogo.

![Exemplo de um módulo de seletor de catálogo que lista três catálogos de produtos.](./media/Catalog-picker-sample.png)

## <a name="add-a-catalog-picker-module-to-your-site"></a>Adicionar um módulo de seletor de catálogo ao seu site

Para adicionar um módulo de seletor de catálogo a seu site no construtor de sites do Commerce, siga estas etapas.

### <a name="create-a-catalog-picker-page"></a>Criar uma página de seletor de catálogo

Primeiramente, crie uma página de seletor de catálogo.

1. Acesse **Páginas** e selecione **Novo** para criar uma nova página.
1. Na caixa de diálogo **Criar uma página**, em **Nome da página**, insira **Seletor de catálogo**.
1. Em **URL da página**, insira uma URL para a página e, em seguida, selecione **Avançar**.

    ![Crie uma caixa de diálogo de página.](./media/Create-catalog-picker-page.png)

1. Em **Escolher um modelo**, selecione **Conteúdo geral** e **Avançar**.
1. Em **Escolher um layout**, selecione **Layout flexível** e, em seguida, clique **Avançar**.
1. Em **Revisar e concluir**, revise a configuração da página. Se você precisar editar as informações da página, selecione **Voltar**. Se as informações da página estiverem corretas, selecione **Criar página**.
1. Em **Seletor de catálogo**, selecione **Slot principal**, selecione as reticências (**...**) e **Adicionar módulo**.

    ![Adicionando um módulo ao Slot principal no Seletor de catálogo.](./media/Author-web-page-catalog-picker-1.png)

1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Contêiner** e, depois, **OK**.
1. Selecione o slot **Contêiner**, selecione as reticências (**...**) e, em seguida, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Seletor de catálogo** e **OK**.
1. No painel de propriedades do **Seletor de catálogo**, em **Título**, selecione **Catálogos** e, em seguida, insira um título para a página do seletor de catálogo.
1. Em **Nível do título**, selecione um nível de título e, em seguida, **OK**.
1. Em **Rich text**, digite o texto que será exibido na parte superior da página do seletor de catálogo.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.

### <a name="add-a-link-on-your-account-page"></a>Adicionar um link na página da sua conta

Em seguida, adicione uma referência à sua página de seletor de catálogo na página **Minha conta**.

1. Vá para **Páginas**, localize e selecione a página **Minha conta** do site e, em seguida, selecione **Editar**.
1. No slot **Principal** da página, selecione o slot **Bloco genérico da conta**. 
1. No painel de propriedades **Bloco genérico da conta**, em **Links**, selecione **Adicionar link de ação** e selecione **Link de ação**.
1. Na caixa de diálogo **Link de ação**, em **Texto do link**, digite o texto do link para a página do seletor de catálogo.
1. Em **Destino do link**, selecione **Adicionar um link**.
1. Na caixa de diálogo **Adicionar um link**, selecione **Página personalizada** e, em seguida, **Avançar**.
1. Em **Nome**, selecione a página do seletor de catálogo, selecione **Aplicar** e, em seguida, **OK**.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.

A ilustração a seguir mostra um exemplo de uma página de contas com uma referência à página do catálogo.

![Página Minhas contas com link para o catálogo.](./media/my-accounts.png)

### <a name="add-a-link-from-the-header"></a>Adicionar um link do cabeçalho

Por fim, adicione um link do cabeçalho do seu site a seus catálogos.

1. Vá para **Fragmentos**, localize e selecione o fragmento de cabeçalho do site e, em seguida, selecione **Editar**.
1. Selecione o slot **Cabeçalho**. 
1. No painel de propriedades **Cabeçalho**, em **Links para Minha conta**, selecione **Adicionar link de ação** e selecione **Link de ação**.
1. Na caixa de diálogo **Link de ação**, em **Texto do link**, digite o texto do link para a página do seletor de catálogo.
1. Em **Destino do link**, selecione **Adicionar um link**.
1. Na caixa de diálogo **Adicionar um link**, selecione **Página personalizada** e, em seguida, **Avançar**.
1. Em **Nome**, selecione a página do seletor de catálogo, selecione **Aplicar** e, em seguida, **OK**.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in do fragmento do cabeçalho e depois selecione **Publicar** para publicá-lo.

A ilustração a seguir mostra um exemplo de cabeçalho de site de comércio eletrônico com um link para o catálogo B2B.

![Cabeçalho do site de comércio eletrônico com link suspenso para o catálogo.](./media/catalog-in-header.png)


## <a name="additional-resources"></a>Recursos adicionais 

[Criar catálogos do Commerce para sites B2B](catalogs-b2b-sites.md)

[Impacto da extensibilidade de catálogos do Commerce para personalizações B2B](catalogs-b2b-sites-dev.md)

[Perguntas frequentes sobre Catálogos do Commerce para B2B](catalogs-b2b-sites-FAQ.md)

[Páginas e módulos de gerenciamento de contas](account-management.md)

[Módulo de cabeçalho](author-header-module.md)

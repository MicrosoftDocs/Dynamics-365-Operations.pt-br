---
title: Módulos de comparação de produtos
description: Este artigo descreve os módulos de comparação de produtos e como implementá-los para que os clientes possam fazer comparações de produtos nos sites de comércio eletrônico do Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 10/03/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2022-02-28
ms.openlocfilehash: 9ff45f3fbcc86b21f336d580582adef586417de4
ms.sourcegitcommit: 66b954827826706ea2ba00c2afd5d694ad92148d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/03/2022
ms.locfileid: "9618376"
---
# <a name="product-comparison-modules"></a>Módulos de comparação de produtos

[!include [banner](../includes/banner.md)]

Este artigo descreve os módulos de comparação de produtos e como implementá-los para que os clientes possam fazer comparações de produtos nos sites de comércio eletrônico do Microsoft Dynamics 365 Commerce.

> [!NOTE]
> Os módulos do botão de comparação de produtos e da comparação de produtos estão disponíveis a partir da versão 10.0.29 do Dynamics 365 Commerce. Eles podem ser usados para os sites business-to-consumer (B2C) e business-to-business (B2B).

A funcionalidade de comparação de produtos permite que os compradores comparem detalhes do produto em uma página de comparação de produtos para ajudá-los a tomar melhores decisões de compra. Essa funcionalidade é configurada no criador de sites do Commerce usando o módulo comparação de produtos. Nas páginas da lista de produtos (PLPs), como resultados de categorias, resultados de pesquisa e páginas de coleções de produtos, você pode configurar um botão de comparação de produtos que permite aos compradores adicionar produtos a uma bandeja de comparação. Essa funcionalidade é configurada no construtor de sites usando o módulo do botão de comparação de produtos, que funciona como o [módulo de exibição rápida](quick-view-module.md).

Quando os usuários do site adicionam produtos para comparação, selecionando-os em blocos de produtos, uma bandeja de comparação aparece na parte inferior da página. A bandeja de comparação mostra os produtos que o comprador está comparando atualmente, juntamente com pequenas visualizações dos produtos. Os usuários do site também podem adicionar produtos das páginas de detalhes do produto (PDPs) e podem adicionar grades de produtos específicos para comparar com os produtos mestre.

Depois que os clientes adicionarem alguns produtos à bandeja de comparação, eles poderão selecionar **Comparar** para ser redirecionado para uma página de comparação de produtos. A página comparação de produtos mostra detalhes do produto para cada produto selecionado para que os clientes possam comparar imagens, preços, dimensões de produtos (tamanho, estilo e cor), informações de classificação agregadas e outros atributos de produto.

A ilustração a seguir mostra exemplos do botão comparar produto, do botão remover da comparação, da bandeja de comparação e da página de comparação de produtos.

![Visão geral de comparação do produto mostrando o botão comparar produto, o botão remover da comparação, o painel da bandeja de comparação e a página de comparação de produtos.](./media/Product-Comparison-Overview.png)

> [!NOTE]
> - A página comparação de produtos compara um conjunto padrão de propriedades de produtos e todos os atributos que podem ser exibidos em um PDP para um determinado produto.
> - Propriedades como o modo de entrega, o estoque disponível e a unidade de medida não podem ser exibidas em uma página de comparação de produtos.
> - Os clientes podem adicionar produtos de diferentes categorias à bandeja de comparação, desde que os produtos sejam do mesmo catálogo.
> - No momento, a funcionalidade de comparação de produtos está limitada à comparação de produtos em um catálogo individual. Os usuários do site não podem fazer comparações entre catálogos.
> - Verifique se a propriedade **Lado do cliente do módulo de renderização** está desmarcada para todos os módulos de comparação de produtos.
> - Você deve garantir que o cache no nível de página esteja desabilitado para todas as páginas nas quais o módulo de comparação de produtos é usado. Essas páginas incluem as páginas PDPs, PLPs e comparação de produtos. Para obter mais informações, consulte [Configurar cache de página](e-commerce-extensibility/page-caching.md).

A ilustração a seguir mostra um exemplo de uma página de comparação de produtos.

![Página de comparação de produtos.](./media/Product-Comparison-Page.png)

## <a name="add-the-product-comparison-module-to-a-new-product-comparison-page"></a>Adicionar o módulo de comparação de produtos a uma nova página de comparação de produtos

Você pode criar uma página de comparação de produtos dedicada adicionando um módulo de comparação de produtos ao corpo de uma página. Além de permitir que os clientes comparem detalhes de produtos de diferentes produtos, você pode configurar o módulo de comparação de produtos para oferecer aos clientes a opção de concluir rapidamente a compra depois de compararem os produtos. O módulo comparação de produtos também contém um slot de **Comparação vazia**, no qual é possível adicionar um módulo de bloco de conteúdo que descreve o estado vazio (por exemplo, "A comparação de produtos está vazia").

Para adicionar um módulo de comparação de produtos a uma nova página de comparação de produtos, siga estas etapas.

1. Acesse **Páginas** e selecione **Novo** para criar uma nova página.
1. Na caixa de diálogo **Criar uma nova página**, em **Nome da página**, insira um nome de página apropriado (por exemplo, **Comparação de produtos**) e selecione **Avançar**.
1. Em **Escolher um modelo**, selecione o modelo apropriado (por exemplo, o modelo usado por sua página de categoria padrão) e selecione **Avançar**.
1. Em **Escolher um layout**, selecione um layout de página (por exemplo, **Layout flexível**) e selecione **Avançar**.
1. Em **Revisar e concluir**, revise a configuração da página. Se você precisar editar as informações da página, selecione **Voltar**. Se as informações da página estiverem corretas, selecione **Criar página**.
1. No **Slot principal**, selecione as reticências (**...**) e depois selecione **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Contêiner** e, depois, **OK**.
1. No slot **Contêiner**, selecione as reticências (**...**) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Comparação de produtos** e, depois, **OK**.
1. No slot **Botão de visualização rápida**, selecione as reticências (**...**) e depois **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Exibição rápida do produto** e, depois, **OK**.
1. No painel de propriedades à direita, configure as propriedades do módulo **Exibição rápida do produto**.
1. No slot **Comparação vazia**, selecione as reticências (**...**) e, depois, selecione **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Bloco de conteúdo** e, depois, **OK**.
1. No painel de propriedades à direita, configure as propriedades do módulo **Bloco de conteúdo**. 
1. Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página.
1. Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.

A ilustração a seguir mostra um exemplo da página de comparação vazia no construtor de sites.

![Módulo de comparação de produtos.](./media/Product-comparison-module.png)

## <a name="add-a-product-comparison-button-to-product-tiles-on-search-and-category-results-pages"></a>Adicionar um botão de comparação de produtos a blocos de produtos em páginas de resultados de pesquisa e categoria

O botão de comparação de produtos permite que os usuários adicionem rapidamente um produto à bandeja de comparação ao procurarem produtos em uma página de listagem. Eles podem adicionar um ou mais produtos à bandeja de comparação a partir de uma página de listagem sem ter de ir a um PDP.

O botão de comparação de produtos é compatível com os módulos coleção de produtos, resultados de pesquisa e caixa de compras de PDP.

Para adicionar um botão de comparação de produtos a blocos de produtos em páginas de resultados de pesquisa e categoria, siga estas etapas.

1. No criador de sites, vá para **Páginas** e abra a página de categoria à qual deseja adicionar um botão de comparação de produtos.
1. No **Slot principal**, selecione as reticências (**...**) e depois selecione **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Resultados da pesquisa** e, depois, **OK**.
1. No slot **Botão de comparação de produtos** do módulo **Resultados da pesquisa**, selecione as reticências (**...**) e depois **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Botão de comparação de produtos** e, depois, **OK**.
1. No painel de propriedades à direita, configure as propriedades do módulo **Botão de comparação de produtos**.
1. Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página.
1. Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.

## <a name="add-a-product-comparison-preview-panel-module-to-pages-on-your-website"></a>Adicionar um módulo do painel de visualização de comparação de produtos a páginas no seu site

Um módulo do painel de visualização de comparação de produtos fornece aos seus clientes a opção de revisar produtos adicionados ou removidos da comparação. O painel visualização também fornece as opções para navegar até a página de comparação diretamente ou limpar toda a lista de produtos. 

É recomendável habilitar o painel de visualização em todas as páginas que tenham o botão **Comparação de produtos** habilitado. O módulo pode ser adicionado ao **botão Comparação de produtos** como um slot ou pode ser usado como um módulo independente que você poderá configurar em qualquer página, mesmo quando não houver funcionalidade para adicionar ou remover produtos para comparação. 

Você deve adicionar o produto manualmente o módulo do painel de visualização de comparação de produtos à página. Você deve adicionar somente um módulo do painel de visualização a uma página. Se você adicionar várias instâncias do módulo a uma página, o primeiro módulo será renderizado e o restante será ignorado.

![Painel de visualização de comparação de produtos](./media/product-comparison-preview-panel-2.png)

Se especificar um limite de comparação de produtos, você terá a opção de habilitar espaços reservados cinza no painel de visualização para indicar quantos produtos podem ser adicionados à comparação. Os espaços reservados cinza serão substituídos pelos produtos à medida que eles forem adicionados à comparação. Para configurar um limite de comparação de produtos e habilitar os espaços reservados cinza, no construtor de sites, acesse **Configurações do site > Extensões** e faça as alterações na seção **Comparações de produtos**. A configuração será aplicada a todos os painéis de visualização de todas as páginas. 


## <a name="specify-the-maximum-number-of-products-to-show-in-the-comparison-tray"></a>Especifique o número máximo de produtos a serem mostrados na bandeja de comparação

Você pode especificar o número máximo de produtos a serem mostrados na bandeja de comparação indo para **Configurações de site \> Extensões** no construtor de sites. Você pode configurar limites máximos separados para exibições de área de trabalho e dispositivo móvel/tablet. Por padrão, nenhum limite será imposto, se nenhum limite máximo for definido.

> [!NOTE]
> Para obter uma experiência de navegação ideal, recomendamos que você defina o número máximo de produtos na bandeja de comparação como **2** para a porta de exibição móvel e **4** para que a porta de exibição da área de trabalho reduza o valor de rolagem horizontal, se necessário.

Para especificar o número máximo de produtos a serem mostrados na bandeja, siga estas etapas.

1. No construtor de sites, vá para **Configurações do site \> Extensões**.
1. Para a propriedade **Produtos no limite de comparação - dispositivos da área de trabalho** insira o número máximo de produtos que devem ser mostrados na bandeja de comparação para as portas de exibição da área de trabalho.
1. Para a propriedade **Produtos no limite de comparação - dispositivos móveis e tablet** insira o número máximo de produtos que devem ser mostrados na bandeja de comparação para as portas de exibição de dispositivo móvel e tablet.
1. Na barra de comandos, selecione **Salvar e publicar**.

![Configurações do site para limitar os produtos na bandeja de comparação.](./media/Site-settings-to-limit-products-in-comparison-tray.png)

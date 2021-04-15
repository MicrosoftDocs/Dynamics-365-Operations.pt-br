---
title: Módulo de seletor de loja
description: Este tópico abrange o módulo de seletor de loja e descreve como adicioná-lo às páginas do site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: ''
ms.openlocfilehash: e73338666c0bd8c0dc8df840b308ec758ee812dd
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798624"
---
# <a name="store-selector-module"></a>Módulo de seletor de loja

[!include [banner](includes/banner.md)]

Este tópico abrange o módulo de seletor de loja e descreve como adicioná-lo às páginas do site no Microsoft Dynamics 365 Commerce.

Os clientes podem usar o módulo de seletor de loja para retirar um produto em uma loja selecionada após realizarem uma compra online. Na versão 10.0.13 do Commerce, o módulo de seletor de loja também inclui recursos que podem exibir uma página **Localizar uma loja** que mostra as lojas próximas.

O módulo de seletor de loja permite que os usuários insiram um local (cidade, estado, endereço, etc.) para procurar lojas em um raio de pesquisa. Ao abrir o módulo pela primeira vez, ele usará o local do navegador do cliente para localizar lojas (se esse recurso tiver sido autorizado).

## <a name="store-selector-module-usage-in-e-commerce"></a>Uso do módulo de seletor de loja no comércio eletrônico

- Um módulo de seletor de loja pode ser usado na página de detalhes de um produto (PDP) para selecionar uma loja onde será feita a retirada.
- Um módulo de seletor de loja pode ser usado na página de um carrinho para selecionar uma loja onde será feita a retirada.
- Um módulo de seletor de loja pode ser usado em uma página autônoma que mostra todas as lojas disponíveis.

## <a name="bing-maps-integration"></a>Integração do Bing Maps

O módulo de seletor de loja é integrado às [interfaces de programação de aplicativo (APIs) REST do Bing Maps](https://docs.microsoft.com/bingmaps/rest-services/) para usar os recursos de Geocodificação e Sugestão Automática do Bing. Uma chave de API do Bing Maps é necessária e deve ser adicionada à página de parâmetros compartilhados na Sede do Commerce. A API de Geocodificação é usada para converter um local em valores de latitude e longitude. A integração com a API de Sugestão Automática é usada para mostrar sugestões de pesquisa quando os usuários inserem locais no campo de pesquisa.

Para a API REST da Sugestão Automática, é necessário garantir que as seguintes URLs sejam permitidas de acordo com a política de segurança de conteúdo (CSP) do site. Essa configuração é executada na criação de site do Commerce, adicionando as URLs permitidas às várias diretivas da CSP do site (por exemplo, **img-src**). Para obter mais informações, consulte [Política de segurança de conteúdo](manage-csp.md). 

- Para a diretiva **connect-src**, adicione **&#42;.bing.com**.
- Para a diretiva **img-src**, adicione **&#42;.virtualearth.net**.
- Para a diretiva **script-src**, **adicione &#42;.bing.com, &#42;.virtualearth.net**.
- Para a diretiva **script style-src**, adicione **&#42;.bing.com**.
 
## <a name="pickup-in-store-mode"></a>Modo Retirar na loja

O módulo de seletor de loja oferece suporte para o modo **Retirar na loja**, que mostra uma lista de lojas nas quais o produto está disponível para retirada. Ele também mostra o horário de funcionamento e o estoque de produtos de todas as lojas na lista. O módulo de seletor de loja requer o contexto de um produto para renderizar a disponibilidade do produto e para permitir que o usuário adicione o produto ao carrinho, caso o modo de entrega do produto esteja definido como **retirada** na loja selecionada. Para obter mais informações, consulte [configurações de estoque](inventory-settings.md). 

O módulo de seletor de loja pode ser adicionado a um módulo de caixa de compra em uma PDP para mostrar as lojas em que um produto está disponível para retirada. Também pode ser adicionado a um módulo de carrinho. Nesse caso, o módulo de seletor de loja mostra as opções de retirada para cada item de linha no carrinho. O módulo de seletor de loja também pode ser adicionado a outras páginas ou módulos por meio de extensões e personalizações.

Para que esse cenário funcione, os produtos devem ser configurados para usar o modo de entrega **retirada**. Caso contrário, o módulo não será mostrado nas páginas de produtos. Para obter mais informações sobre como configurar o modo de entrega, consulte [Configurar os modos de entrega](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

A imagem a seguir mostra um exemplo de um módulo de seletor de loja usado em uma PDP.

![Exemplo de um módulo de seletor de loja usado em um PDP](./media/BOPIS.PNG)

> [!NOTE]
> Na versão 10.0.16 ou posterior, um novo recurso pode ser habilitado, permitindo que uma organização defina vários modos de separação de opções de entrega para os clientes.  Se esse recurso estiver habilitado, o seletor de loja e outros módulos de comércio eletrônico serão aprimorados para permitir que o comprador escolha entre as opções de entrega de separação potencialmente múltiplas, se configurado.  Para saber mais sobre esse recurso, consulte [esta documentação](https://docs.microsoft.com/dynamics365/commerce/multiple-pickup-modes). 

## <a name="find-stores-mode"></a>Modo Localizar lojas

O módulo de seletor de loja também oferece suporte para um modo **Localizar lojas**. Esse modo pode ser usado para criar uma página de localizações de lojas que mostra as lojas disponíveis e suas informações. Nesse modo, o módulo de seletor de loja funciona sem o contexto do produto e pode ser usado como um módulo autônomo em qualquer página do site. Além disso, se as configurações relevantes estiverem ativadas para o módulo, os usuários poderão selecionar a sua loja preferida. Quando uma loja é selecionada como a preferida do usuário, a sua ID será mantida no cookie do navegador. Portanto, o usuário deverá aceitar a mensagem de consentimento de cookies.

A ilustração a seguir mostra um exemplo de um módulo de seletor de loja usado com um módulo de mapa na página de localizações da loja.

![Exemplo de um módulo de seletor de armazenamento e um módulo de mapa em uma página de locais de armazenamento](./media/ecommerce-Storelocator.PNG)

## <a name="render-a-map"></a>Renderizar um mapa

O módulo de seletor de loja pode ser usado com o módulo de mapa para exibir as localizações da loja no mapa. Para obter mais informações sobre o módulo de mapa, consulte o [Módulo de mapa](map-module.md)

## <a name="store-selector-module-properties"></a>Propriedades do módulo de seletor de loja

| Nome da propriedade | Alíquota | descrição |
|---------------|-------|-------------|
| Título | Texto | O título do módulo. |
| Modo | **Localizar lojas** ou **Retirar na loja** | O modo **Localizar lojas** mostra as lojas disponíveis. O modo **Retirar na loja** permite que os usuários selecionem uma loja para retirar o produto. |
| Estilo | **Caixa de diálogo** ou **Em linha** | O módulo pode ser renderizado em linha ou em uma caixa de diálogo. |
| Definir como loja preferida | **Verdadeiro** ou **Falso** | Quando essa propriedade for definida como **True**, os usuários poderão definir uma loja preferida. Esse recurso requer que os usuários aceitem uma mensagem de consentimento de cookies. |
| Mostrar todas as lojas | **Verdadeiro** ou **Falso** | Quando essa propriedade for definida como **True**, os usuários poderão ignorar a propriedade **Raio de pesquisa** e exibir todas as lojas. |
| Opções de sugestão automática: resultados máximos | Número | Essa propriedade define o número máximo de resultados de sugestão automática que podem ser exibidos pela API de Sugestão Automática do Bing. |
| Pesquisar raio | Número | Essa propriedade define o raio de pesquisa de lojas, em milhas. Se nenhum valor for especificado, o raio de pesquisa padrão de 50 milhas será usado. |
| Termos de serviço | URL |  Essa propriedade especifica a URL de termos de serviço necessária para usar o serviço Bing Maps. |

## <a name="add-a-store-selector-module-to-a-page"></a>Adicionar um módulo de seletor de loja a uma página

O modo **Retirar na loja** pode ser usado somente em PDPs e páginas de carrinho. Defina o modo como **Retirar na loja** no painel de propriedades do módulo.

- Para obter informações sobre como adicionar um módulo de seletor de loja a um módulo de caixa de compra, consulte [Módulo de caixa de compra](add-buy-box.md). 
- Para obter informações sobre como adicionar um módulo de seletor de loja a um módulo de carrinho, consulte [Módulo de carrinho](add-cart-module.md)

Para configurar o módulo de seletor de loja a fim de mostrar as lojas disponíveis na página de localizações, conforme a ilustração exibida anteriormente nesse tópico, siga estas etapas.

1. Vá para **Modelos** e selecione **Novo** para criar um novo modelo.
1. Na caixa de diálogo **Novo Modelo**, em **Nome do modelo**, insira **Modelo de marketing** e selecione **OK**.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.
1. Vá para **Páginas** e selecione **Novo** para criar uma nova página.
1. Na caixa de diálogo **Escolher um modelo**, selecione o modelo **Modelo de marketing**. Em **Nome da página**, insira **Localizações de lojas** e selecione **OK**.
1. No slot **Principal** da nova página, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Contêiner** e, depois, **OK**.
1. No slot **Contêiner**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Contêiner com 2 colunas** e, depois, **OK**.
1. No painel de propriedades do módulo, defina o valor de **Largura** como **Preencher Contêiner**.
1. Defina o valor de **Configuração da coluna da porta de exibição extra pequena** como **100%**.
1. Defina o valor de **Configuração da coluna da porta de exibição pequena** como **100%**.
1. Defina o valor de **Configuração da coluna da porta de exibição média** como **33% 67%**.
1. Defina o valor de **Configuração da coluna da porta de exibição grande** como **33% 67%**.
1. No slot **Contêiner com 2 colunas**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Seletor de loja** e, depois, **OK**.
1. No painel de propriedades do módulo, defina o valor de **Modo** como **Localizar lojas**.
1. Defina o valor de **Raio de pesquisa** em milhas.
1. Defina as outras propriedades, como **Definir como loja preferida**, **Exibir todas as lojas** e **Habilitar a sugestão automática**, conforme necessário.
1. No slot **Contêiner com 2 colunas**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Mapa** e, depois, **OK**.
1. No painel de propriedades do módulo, defina as propriedades adicionais conforme necessário.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.
 
## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Módulo de caixa de compra](add-buy-box.md)

[Módulo de carrinho](add-cart-module.md)

[Tour rápido da PDP](quick-tour-pdp.md)

[Tour rápido do carrinho e do check-out](quick-tour-cart-checkout.md)

[Configurar os modos de entrega](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)

[Gerenciar o Bing Mapas da sua organização](dev-itpro/manage-bing-maps.md)

[APIs REST do Bing Maps](https://docs.microsoft.com/bingmaps/rest-services/)

[Módulo de mapa](map-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
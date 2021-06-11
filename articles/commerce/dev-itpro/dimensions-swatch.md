---
title: Configurar valores de dimensão de produto para serem exibidos como amostras
description: Este tópico descreve como configurar valores de dimensão de produto como amostras no Microsoft Dynamics 365 Commerce headquarters.
author: anupamar-ms
ms.date: 05/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2020-09-20
ms.dyn365.ops.version: Retail 10.0.20 update
ms.openlocfilehash: 08564ce7af7412f2501b917b3496942004402611
ms.sourcegitcommit: 53b797ff1b524f581046b48cdde42f50b37495bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/28/2021
ms.locfileid: "6117208"
---
# <a name="configure-product-dimension-values-to-appear-as-swatches"></a>Configurar valores de dimensão de produto para serem exibidos como amostras

[!include [banner](../../includes/banner.md)]
[!include [banner](../../includes/preview-banner.md)]

Este tópico descreve como configurar valores de dimensão de produto como amostras no Microsoft Dynamics 365 Commerce headquarters. Para obter informações sobre dimensões do produto, consulte [Dimensões do produto](../../supply-chain/pim/product-dimensions.md).

O Dynamics 365 Commerce oferece suporte ao uso de dimensões de tamanho, estilo e cor para representar grades de produtos. As dimensões do produto têm nomes amigáveis que são mostrados nas páginas de detalhes do produto (PDPs) para que as grades de produto possam ser selecionadas. Exemplos desses nomes amigáveis são "Pequeno", "Médio" e "Grande" para tamanhos e "Preto" e "Marrom" para cores. No entanto, se um produto oferecer suporte a várias variações, várias seleções são necessárias para exibir a imagem de cada grade de produto. Portanto, pode ser lento e tedioso para os clientes procurarem e selecionarem grades de produtos.

Quando as dimensões são mostradas como amostras no PDPs, os clientes obtêm uma visualização visual das variações de um produto. Eles podem navegar facilmente por uma grande variedade de cores, padrões e texturas e podem exibir rapidamente combinações diferentes de variações de produtos.

O recurso Exibir dimensões como amostras permite que o Commerce use códigos hexadecimais (hex) e imagens para mostrar as dimensões como amostras. Além disso, dimensões semelhantes, como cores, podem ser agrupadas em páginas de lista de produtos. Por exemplo, um cliente está procurando produtos que estão em azul. Se os vários valores de dimensão azuis são agrupados juntos, a página lista de resultados de pesquisa mostra os produtos que têm os diferentes tons de azul. O agrupamento de dimensões melhora significativamente a experiência de refinamento do produto e ajuda os clientes a encontrar mais produtos por meio de uma única consulta de pesquisa de produtos.

> [!NOTE]
> O recurso Exibir dimensões como amostras está disponível a partir da versão 10.0.20 do Dynamics 365 Commerce.

A ilustração a seguir mostra um exemplo em que cores aparecem como amostras em um PDP do Commerce.

![Exemplo de cores mostradas como amostras em uma página de detalhes do produto](../dev-itpro/media/swatch_pdp.png)

A ilustração a seguir mostra um exemplo em que cores aparecem como amostras em uma página da lista de resultados de pesquisa do Commerce.

![Exemplo de cores mostradas como amostras em uma página da lista de resultados de pesquisa](../dev-itpro/media/swatch_searchresults.PNG)

## <a name="enable-the-display-dimensions-as-swatches-feature-in-commerce-headquarters"></a>Habilitar as dimensões de exibição como um recurso de amostras no Commerce Headquarters

Para habilitar o recurso Exibir dimensões como amostras no Commerce Headquarters, vá para **Espaços de trabalho \> Gerenciamento de recursos** e ative o recurso **Habilitar suporte de imagem para valores de dimensão do produto**. Quando esse sinalizador de recursos é habilitado, três novos campos são adicionados para cada dimensão nas tabelas apropriadas no Commerce Headquarters: **Hexcode**, **URL** (para imagens) e **RefinerGroup**.

## <a name="configure-dimension-values-in-commerce-headquarters"></a>Configurar valores de dimensão no Commerce Headquarters

O recurso Exibir dimensões como amostras tem suporte para dimensões de tamanho, estilo e cor. Código hexadecimal e valores da URL de imagem para as dimensões apropriadas podem ser especificados no Commerce Headquarters. Por padrão, se os valores de código hexadecimal e URL da imagem não forem fornecidos para uma dimensão, o sistema mostrará o texto do nome amigável da dimensão.

A configuração pode ser realizada em qualquer um dos seguintes níveis:

- **Dimensão** – no Commerce Headquarters, abra a página de uma dimensão pesquisando **Cor**, **Tamanho** ou **Estilo**. Em cada página, uma grade lista os valores de dimensão. Você pode gerenciar os valores de ordem de exibição, código hexadecimal e URL da imagem. A ilustração a seguir mostra uma configuração de exemplo da página **Cores**.

    ![Exemplo de configuração de dimensão na página Cores](../dev-itpro/media/swatch_Color.PNG)

- **Grupo de dimensões** – no Dynamics 365 Commerce, você pode usar a propriedade **RefinerGroup** para criar grupos de dimensões. Se os grupos de dimensões estiverem definidos, abra a página apropriada procurando **Grupo de cores**, **Grupo de tamanho** ou **Grupo de estilos**. Em cada página, é possível gerenciar o código hexadecimal, a URL da imagem e os valores do grupo refinado. A ilustração a seguir mostra uma configuração de exemplo da página **Grupos de cores**.

    ![Exemplo de configuração de dimensão na página Grupos de cores](../dev-itpro/media/swatch_colorGroup.PNG)

- **Dimensão do produto (durante a criação do produto)** – ao criar um novo produto, você pode usar a página **Dimensões do produto** para inserir os valores de dimensão. Para produtos existentes, os campos **Hexcode**, **URL** (para imagens) e **RefinerGroup** já podem estar definidos. No entanto, você pode alterar os valores, conforme desejado. A ilustração a seguir mostra uma configuração de exemplo da página **Dimensões do produto**.

    ![Exemplo de configuração de dimensão na página Dimensões do produto](../dev-itpro/media/swatch_product_dimensions.PNG)

> [!NOTE]
> O processo de gerenciamento de código hexadecimal e configurações de URL de imagem segue o mesmo padrão usado para gerenciar a ordem de exibição de dimensões.

## <a name="configure-dimension-values-by-using-hex-codes"></a>Configurar valores de dimensão usando códigos hexadecimais

Para a maioria das dimensões de cor, um valor de cor de código hexadecimal deve ser fornecido em páginas de dimensão no Commerce Headquarters. Por exemplo, a cor preta deve ter um valor de código hexadecimal de **#00000**. Quando o Commerce processa uma página do site, o código hexadecimal é representado por uma amostra colorida.

A ilustração a seguir mostra um exemplo no qual as dimensões de cores são configuradas usando valores de código hexadecimal.

![Exemplo de configuração de dimensão que usa códigos hexadecimais](../dev-itpro/media/swatch_color_hexcode.png)

## <a name="configure-dimension-values-by-using-image-urls"></a>Configurar valores de dimensão usando URLs de imagem

Algumas dimensões de cor representam padrões, não cores sólidas. Por exemplo, uma dimensão de cor pode ser descrita como 'leopard'. Nesses casos, você pode representar mais efetivamente as dimensões de cor usando imagens publicadas, em vez de códigos hexadecimais para amostras.

Você deve carregar cada imagem para o construtor de sites do Commerce e publicá-la. Em seguida, insira a URL de imagem para a imagem publicada nas páginas de dimensão apropriadas no Commerce Headquarters. Se uma dimensão tiver sido selecionada para exibição como uma amostra, mas um código hexadecimal não estiver definido, o Commerce fará uma pesquisa de imagem ao renderizar a página. Se a pesquisa de imagem falhar, o Commerce mostrará o texto do nome amigável da dimensão.

A ilustração a seguir mostra um exemplo no qual os URLs da imagem são usados para a configuração na página **Cores**.

![Exemplo de configuração de dimensão que usa URLs de imagem](../dev-itpro/media/swatch_color_urls.PNG)

Você pode usar um modelo de mídia para definir URLs de imagem, da mesma forma que é possível para imagens de produtos e categorias. Ao carregar imagens para o construtor de sites, as convenções de nome de arquivo e os caminhos de arquivo devem ser consistentes.

A ilustração a seguir mostra um exemplo no qual as URLs da imagem são usadas para a configuração de um modelo de mídia.

![Exemplo de configuração de modelo de mídia](../dev-itpro/media/swatch_media_template.PNG)

## <a name="configure-dimension-values-by-using-both-hex-codes-and-image-urls"></a>Configurar valores de dimensão usando códigos hexadecimais e URLs de imagem

Para a maioria das dimensões de cor, você pode configurar códigos hexadecimais e URLs de imagem. A lógica de fallback de renderização do Commerce procurará automaticamente um código hexadecimal ou uma URL de imagem para mostrar uma amostra de cor. Usando códigos hexadecimais e URLs de imagem para configurar dimensões de cores, você ajuda a simplificar o gerenciamento de imagens quando o número de cores é grande.

A ilustração a seguir mostra um exemplo no qual os códigos hexadecimais e URLs da imagem são usados para a configuração na página **Cores**.

![Exemplo de configuração de dimensão que usa URLs de imagem e códigos hexadecimais](../dev-itpro/media/swatch_color_hexandimage.png)

## <a name="configure-refiner-groups"></a>Configurar grupos do refinador

Ao definir um código hexadecimal ou URL de imagem para um valor de dimensão, você também pode especificar um valor para o campo **RefinerGroup**. Este campo define a dimensão que deve ser usada para agrupar valores de dimensão semelhantes na experiência do refinador.

Por exemplo, se os valores de dimensão de cor forem "azul", "xadrez azul", azul desbotado" e "azul escuro", cada valor é mapeado para um código hexadecimal ou URL de imagem diferente. Portanto, cada valor aparecerá como uma cor diferente em PDPs e cartões de produto para os produtos apropriados. No entanto, se você mapear todos esses valores de dimensão de cor para um valor de **RefinerGroup** de **Azul**, uma pesquisa de produtos "azul" gerará resultados de pesquisa da página da lista para produtos que têm valores de cor da dimensão de "azul", "xadrez azul," "azul desbotado" e "azul escuro".

O exemplo na ilustração a seguir mostra o relacionamento entre as propriedades de **Cor** e **RefinerGroup** no Commerce Headquarters.

![Exemplo de gerenciamento de grupos do refinador](../dev-itpro/media/swatch_refiner_group.png)

## <a name="manage-images-in-commerce-site-builder"></a>Gerenciar imagens no construtor de sites do Commerce

Se as URLs de imagem forem usadas para qualquer valor de dimensão, as imagens correspondentes deverão ser carregadas no construtor de sites do Commerce. A localização de cada imagem deve corresponder ao nome do arquivo e ao caminho da pasta definidos para a imagem no Commerce Headquarters. Os arquivos de imagem devem ser carregados para as localizações de categoria apropriadas no construtor de sites. Por exemplo, imagens coloridas devem ser carregadas na pasta da categoria **Cor**. Para obter mais informações sobre como carregar imagens no construtor de sites, consulte [Carregar imagens](../dam-upload-images.md).

A ilustração a seguir mostra um exemplo onde a caixa de diálogo **Carregar arquivos** está sendo usada para carregar imagens na biblioteca de mídia do construtor de sites. Ele realça as categorias **Tamanho**, **Cor** e **Estilo** que estão disponíveis para seleção.

![Exemplo de categorias de arquivo de imagem durante o carregamento na biblioteca de mídia do construtor de sites](../dev-itpro/media/swatch_sitebuilder.png)

## <a name="enable-swatch-display-on-e-commerce-site-pages"></a>Habilitar exibição de amostra nas páginas do site de comércio eletrônico

Antes que as amostras possam aparecer nas páginas do site de comércio eletrônico que exigem seleção de dimensão, como PDPs e páginas de listagem, você deve definir configurações de site de dimensão no Commerce Headquarters. Para obter mais informações, consulte [Aplicar configurações do site para dimensões](../dimension-settings.md).

Além disso, você deve habilitar a propriedade **Incluir atributos de produtos em resultados de pesquisa** para módulos de resultados de pesquisa. Se o seu site usar páginas personalizadas de categoria, você deve atualizar os módulos de resultados de pesquisa usados nessas páginas, de forma que a propriedade **Incluir atributos de produto em resultados de pesquisa** esteja habilitada. Para obter mais informações, consulte [Módulo de resultados de pesquisa](../search-result-module.md).

## <a name="display-swatches-in-pos-and-other-channels"></a>Exibir amostras no PDV e em outros canais

O Commerce não tem atualmente uma implementação pronta para uso com suporte para a exibição de amostras em pontos de venda (PDV) e outros canais. No entanto, você pode implementar a funcionalidade de exibição de amostra como uma extensão que faz com que as APIs de canal retornem os códigos hexadecimais e URLs de imagem que são necessários para processar amostras.

## <a name="additional-resources"></a>Recursos adicionais

[Módulo de resultados de pesquisa](../search-result-module.md)

[Aplicar configurações de site para dimensões](../dimension-settings.md)

[Dimensões do produto](../../supply-chain/pim/product-dimensions.md)

[Carregar imagem](../dam-upload-images.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

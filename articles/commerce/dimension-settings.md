---
title: Aplicar configurações de exibição para dimensões do produto
description: Este artigo abrange as configurações de exibição para dimensões do produto e descreve como aplicá-las no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: 9324518fff35d357f845c08cba25e2faded2f381
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269961"
---
# <a name="apply-display-settings-for-product-dimensions"></a>Aplicar configurações de exibição para dimensões do produto

[!include [banner](includes/banner.md)]


Este artigo abrange as configurações de exibição para dimensões do produto e descreve como aplicá-las no Microsoft Dynamics 365 Commerce.

O Dynamics 365 Commerce oferece suporte a dimensões de tamanho, estilo e cor para distinguir grades de produtos. Normalmente, as dimensões são mostradas como valores de texto, como "Pequeno", "Médio" e "Grande" para tamanhos e "Preto" e "Marrom" para cores. No entanto, se um produto oferecer suporte a várias variações, pode ser difícil procurar grades de produtos, pois várias seleções são necessárias para exibir a imagem de cada grade. Para facilitar a navegação por grades de produtos, a versão 10.0.20 do Commerce pode usar imagens e códigos hexadecimais (hex) para mostrar as dimensões como amostras.

No construtor de sites do Commerce, as configurações de dimensão são definidas em **Configurações do Site \> Extensões \> Configurações da Dimensão**. A ilustração a seguir mostra um exemplo das configurações de dimensão no construtor de sites.

![Exemplo de configurações de site no construtor de sites do Commerce.](./dev-itpro/media/swatch_site_settings.PNG)

Duas configurações de dimensão estão disponíveis:

- **Dimensões a serem exibidas como imagem** – especifique quais dimensões devem aparecer como amostras nas páginas de site de comércio eletrônico, como PDPs (páginas de detalhes do produto) e páginas de lista de resultados de pesquisa. Qualquer combinação de dimensões de estilo, tamanho e cor pode ser mostrada como uma amostra. Se uma dimensão for selecionada para exibição como uma amostra, a renderização do módulo comercial procurará uma configuração disponível de uma amostra de código hexadecimal. Se nenhum código hexadecimal for configurado, a lógica do sistema procurará uma configuração de uma amostra de URL da imagem. Se nem um código hexadecimal nem uma URL de imagem estiverem configurados, o texto será mostrado.

    A ilustração a seguir mostra um exemplo em que um PDP em um site de comércio eletrônico inclui amostras de cor e tamanho. Neste exemplo, um código hexadecimal é configurado para a dimensão de cor. Portanto, as amostras são mostradas como cores. No entanto, nem um código hexadecimal nem uma URL de imagem estão configurados para a dimensão de tamanho. Portanto, o texto é exibido.

    ![Exemplo da dimensão de cor mostrada como amostras em uma página de detalhes de produtos de comércio eletrônico.](./dev-itpro/media/swatch_pdp.png)

- **Dimensões a serem exibidas no cartão de produto** – especifique quais dimensões devem aparecer em cartões de produtos que são mostrados nas listas e nas páginas de listagem. Antes que uma dimensão possa aparecer em um cartão de produto, essa configuração deve ser habilitada para essa dimensão. A configuração **Dimensões a serem exibidas como imagem** também deve ser habilitada. O comportamento de seleção de amostras em cartões de produto é otimizado para a dimensão de cor. Para outras dimensões, uma extensão de exibição pode ser necessária para personalizar o comportamento de seleção de amostra.

    A ilustração a seguir mostra um exemplo onde uma página de listagem em um site de comércio eletrônico contém cartões de produto que incluem amostras de cores.

    ![Exemplo da dimensão de cor mostrada como amostras em uma página de lista de comércio eletrônico.](./dev-itpro/media/swatch_searchresults.PNG)

Para obter informações sobre como configurar dimensões de produto para que sejam mostradas como amostras nas páginas do site, consulte [Configurar valores de dimensão do produto para serem exibidos como amostras](./dev-itpro/dimensions-swatch.md).

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Módulo de resultados de pesquisa](search-result-module.md)

[Módulo de caixa de compra](add-buy-box.md)

[Configurar valores de dimensão de produto para serem exibidos como amostras](./dev-itpro/dimensions-swatch.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]

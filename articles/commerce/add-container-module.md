---
title: Módulo de contêiner
description: Este tópico abrange os módulos de contêiner e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 22a09b61fbe3bd1cca96011d3fb81a12ef1bc844
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697051"
---
# <a name="container-module"></a>Módulo de contêiner

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tópico abrange os módulos de contêiner e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

Um módulo de contêiner é um módulo dentro do qual outros módulos são hospedados. É o contêiner mais genérico usado no Dynamics 365 Commerce. O objetivo principal de um módulo de contêiner é definir, por meio das suas propriedades definidas, o layout dos módulos que estão dentro dele. Por exemplo, esses módulos podem aparecer lado a lado em um layout de duas colunas, três colunas, quatro colunas ou seis colunas. Eles também podem ser limitados à largura do contêiner ou podem preencher a tela. Um cabeçalho também pode ser adicionado a cada módulo de contêiner.

Existem três tipos padrão de módulos de contêiner: contêiner, contêiner com 2 slots e contêiner com 3 slots. Módulos de qualquer tipo de módulo podem ser colocados dentro desses contêineres. Também existem tipos especiais de módulos de contêiner, como carrossel, bloco de conteúdo sofisticado, posicionamento do conteúdo, carrinho, finalização de compra, caixa de compra, cabeçalho e rodapé. Esses contêineres têm finalidades específicas e apenas tipos específicos de módulos compatíveis podem ser colocados dentro deles.

Recomendamos que você coloque módulos dentro de um contêiner, para que possam ser limitados à largura do contêiner.

## <a name="examples-of-container-modules-in-e-commerce"></a>Exemplos de módulos de contêiner no comércio online

- O autor do site deseja um layout de três colunas, onde três módulos apareçam lado a lado. Portanto, o autor do site usa um módulo de contêiner do tipo com 3 slots.
- O autor do site deseja um layout de seis colunas, onde seis módulos apareçam lado a lado. Portanto, o autor do site usa um contêiner do tipo de contenção que possui seis colunas.
- O autor do site deseja colocar um módulo em uma página, mas não deseja que ele preencha a tela. Sendo assim, o autor do site adiciona o módulo a um módulo de contêiner e define a propriedade **Largura** do contêiner como **Ajustar contêiner**.

## <a name="container-module-properties"></a>Propriedades de módulo de contêiner

| Nome da propriedade     | Valores | Descrição |
|-------------------|--------|-------------|
| Cabeçalho           | Texto do cabeçalho e tag do cabeçalho (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | Um cabeçalho opcional pode ser fornecido para o contêiner. Por padrão, a tag de cabeçalho **H2** é usada para o cabeçalho. No entanto, a tag pode ser alterada para atender aos requisitos de acessibilidade. |
| Largura             | **Ajustar contêiner** ou **Preencher tela** | Se o valor estiver definido como **Ajustar contêiner** (o valor padrão), os módulos dentro do contêiner serão limitados à largura do contêiner. Se o valor estiver definido como **Preencher tela**, os módulos não estarão limitados à largura do contêiner, mas poderão preencher a tela. |
| Número de colunas | **1**, **2**, **3**, **4**, **6** ou **12** | Esta propriedade define o número de colunas no contêiner. Um contêiner pode ter até 12 colunas. |

## <a name="container-with-2-slots"></a>Contêiner com 2 slots

O contêiner do tipo com 2 slots é otimizado para um layout de duas colunas. Esse tipo de contêiner possui dois slots para permitir uma visualização lado a lado dos módulos que estão dentro.

Propriedades adicionais podem ser usadas para otimizar o layout para diferentes portas de exibição (dispositivos móveis, tablets, computadores e assim por diante). Para cada porta de exibição, a largura de cada coluna pode ser definida. As seguintes configurações de largura da coluna estão disponíveis:

- **75%/25%** – O primeiro módulo possui uma largura de coluna de 75% e o segundo módulo possui uma largura de coluna de 25%. Uma opção **25%/75%** também está disponível.
- **50%/50%** – Ambos os módulos têm largura de coluna igual.
- **67%/33%** – O primeiro módulo possui uma largura de coluna de 67% e o segundo módulo possui uma largura de coluna de 33%. Uma opção **33%/67%** também está disponível.
- **100%** – Ambos os módulos têm uma largura de coluna completa. Portanto, os módulos são empilhados verticalmente em uma única coluna. Embora esse layout de coluna única seja contrário ao objetivo do contêiner com tipo com 2 slots, pode ser preferível para algumas portas de exibição (por exemplo, portas de exibição extra pequenas, como dispositivos móveis).

### <a name="container-with-2-slots-properties"></a>Contêiner com propriedades de 2 slots

| Nome da propriedade                   | Valores | Descrição |
|---------------------------------|--------|-------------|
| Cabeçalho                         | Texto do cabeçalho e tag do cabeçalho | Um opcional pode ser fornecido para o contêiner. |
| Configuração da porta de exibição extra pequena | **25%/75%**, **75%/25%**, **50%/50%**, **67%/33%**, **33%/67%** ou **100%** | Esta propriedade define o layout para portas de exibição extra pequenas. |
| Configuração da porta de exibição pequena   | **25%/75%**, **75%/25%**, **50%/50%**, **67%/33%**, **33%/67%** ou **100%** | Essa propriedade define o layout para pequenas portas de exibição, como dispositivos móveis. |
| Configuração da porta de exibição média  | **25%/75%**, **75%/25%**, **50%/50%**, **67%/33%**, **33%/67%** ou **100%** | Essa propriedade define o layout para portas de exibição média, como tablets. |
| Configuração da porta de exibição grande   | **25%/75%**, **75%/25%**, **50%/50%**, **67%/33%**, **33%/67%** ou **100%** | Essa propriedade define o layout para grandes portas de exibição, como computadores. |

## <a name="container-with-3-slots"></a>Contêiner com 3 slots

O contêiner com módulos de 3 slots é otimizado para um layout de três colunas.

Propriedades adicionais podem ser usadas para otimizar o layout para diferentes portas de exibição. Para cada porta de exibição, a largura de cada coluna pode ser definida. As seguintes configurações de largura da coluna estão disponíveis:

- **33%/33%/33%** – Todos os três módulos têm largura de coluna igual.
- **50%/25%/25%** – O primeiro módulo possui uma largura de coluna de 50% e cada um dos dois módulos restantes possui uma largura de coluna de 25%. As opções **25%/50%/25%** e **25%/25%/50%** também estão disponíveis.
- **16%/16%/67%** – Cada um dos dois primeiros módulos possui uma largura de coluna de 16% e o terceiro módulo possui uma largura de coluna de 67%. As opções **16%/67%/16%** e **67%/16%/16%** também estão disponíveis.

### <a name="container-with-3-slots-properties"></a>Contêiner com propriedades de 3 slots

| Nome da propriedade                   | Valores | Descrição |
|---------------------------------|--------|-------------|
| Cabeçalho                         | Texto do cabeçalho e tag do cabeçalho | Um cabeçalho opcional pode ser adicionado ao contêiner. |
| Configuração da porta de exibição extra pequena | **33%/33%/33%**, **50%/25%/25%**, **25%/50%/25%**, **25%/25%/50%**, **16%/16%/67%**, **16%/67%/16%** ou **67%/16%/16%** | Esta propriedade define o layout para portas de exibição extra pequenas. |
| Configuração da porta de exibição pequena   | **33%/33%/33%**, **50%/25%/25%**, **25%/50%/25%**, **25%/25%/50%**, **16%/16%/67%**, **16%/67%/16%** ou **67%/16%/16%** | Essa propriedade define o layout para pequenas portas de exibição, como dispositivos móveis. |
| Configuração da porta de exibição média  | **33%/33%/33%**, **50%/25%/25%**, **25%/50%/25%**, **25%/25%/50%**, **16%/16%/67%**, **16%/67%/16%** ou **67%/16%/16%** | Essa propriedade define o layout para portas de exibição média, como tablets. |
| Configuração da porta de exibição grande   | **33%/33%/33%**, **50%/25%/25%**, **25%/50%/25%**, **25%/25%/50%**, **16%/16%/67%**, **16%/67%/16%** ou **67%/16%/16%** | Essa propriedade define o layout para grandes portas de exibição, como computadores. |

## <a name="add-a-container-module-to-a-page"></a>Adicionar um módulo de contêiner a uma página

Para adicionar um módulo de reprodução de contêiner a uma nova página e definir as propriedades necessárias, siga estas etapas.

1. Criar um modelo da página chamado **modelo de contêiner**.
1. No slot **Principal** da página padrão, adicione um módulo de contêiner.
1. No módulo de contêiner, adicione um módulo de recurso.
1. Faça check-in do modelo e publique-o.
1. Use o modelo de contêiner que criou para criar uma página nomeada **Página do contêiner**.
1. No slot **Principal** da nova página, adicione um módulo de contêiner.
1. No painel de propriedades do módulo de contêiner, defina a propriedade **Número de colunas** como **1** e a propriedade **Largura** como **Ajustar contêiner**.
1. No módulo de contêiner, adicione um módulo de recurso.
1. No painel de propriedades do módulo de recurso, configure um cabeçalho.
1. Salve e exiba a página. Você deve verificar um módulo de recurso que se ajusta à largura do módulo do contêiner.
1. No painel de propriedades do módulo de contêiner, altere o valor da propriedade **Número de colunas** para **3**.
1. Adicione mais dois módulos de recursos ao módulo de contêiner.
1. Salve e exiba a página. Agora você deve verificar três módulos de recursos que aparecem lado a lado.
1. Depois de atingir o layout desejado, verifique a página e publique-a.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do kit de início](starter-kit-overview.md)

[Módulo de carrossel](add-carousel.md)

[Módulo de bloco de conteúdo sofisticado](add-content-rich-block.md)

[Módulo de posicionamento de conteúdo](add-content-placement-modules.md)

[Módulo de caixa de compra](add-buy-box.md)

[Módulo de carrinho](add-cart-module.md)

[Módulo de finalização da compra](add-checkout-module.md)

[Módulo de cabeçalho](author-header-module.md)

[Módulo de rodapé](author-footer-module.md)

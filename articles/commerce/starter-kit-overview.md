---
title: Visão geral da biblioteca de módulos
description: Este tópico fornece uma visão geral da biblioteca de módulos do Microsoft Dynamics 365 Commerce.
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
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 76fd75c2ed9a3ba4728129b77a43b50267be3bf3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795324"
---
# <a name="module-library-overview"></a>Visão geral da biblioteca de módulos

[!include [banner](includes/banner.md)]

Este tópico fornece uma visão geral da biblioteca de módulos do Microsoft Dynamics 365 Commerce.

A biblioteca de módulos do Dynamics 365 Commerce é um conjunto de módulos que pode ser usado para criar um site de comércio eletrônico. Os módulos têm tanto aspectos da interface do usuário (IU) quanto do comportamento funcional.

Os temas podem ser aplicados aos módulos na biblioteca de módulos para alterar a aparência. Os temas usam Folhas de Estilos em Cascata (CSS). Um tema para um site de comércio eletrônico fictício chamado "Fabrikam" é fornecido como parte da biblioteca de módulos e pode ser usado como uma referência.

## <a name="module-library-modules"></a>Módulos da biblioteca de módulos

Os seguintes tipos de módulos são fornecidos na biblioteca de módulos:

- **Módulo de contêiner** – Um módulo do contêiner é um módulo simples que atua como um host de outros módulos. Ele controla o layout de módulos que estão dentro deles.
- **Módulos de marketing** – Os módulos de marketing contêm o bloco de conteúdo, bloco de texto, player de vídeo e carrossel. Todos esses módulos podem ser usados para mostrar o conteúdo. Eles podem ser colocados em qualquer página e direcionados por dados do sistema de gerenciamento de conteúdo (CMS).
- **Módulos de cabeçalho e rodapé** – Os módulos de cabeçalho e rodapé aparecem no cabeçalho e no rodapé de todas as páginas do site. Esse módulos podem ser configurados, conforme necessário, por meio de propriedades.
- **Módulos de pesquisa** – Os produtos podem ser descobertos usando o módulo de pesquisa no cabeçalho. Os resultados de pesquisa aparecem na página de resultados de pesquisa. Os produtos também podem ser descobertos nas páginas da categoria, que são páginas dedicadas para cada categoria suportada na hierarquia de navegação do canal. Além disso, os módulos do refinador podem ser usados para filtrar os resultados nos resultados da pesquisa e nas páginas da categoria.
- **Módulos da página de detalhes do produto** – As páginas de detalhes do produto usam vários módulos para mostrar informações sobre o produto. O módulo da caixa de compra permite que os clientes exibam os produtos e os adicionem ao carrinho. Outros módulos, tais como módulo específicos de tecnologia, mostram os detalhes do produto. O módulo de classificações e opiniões pode ser usado para exibir e fornecer opiniões.
- **Módulo Comprar online, retirar na loja** – O módulo Comprar online, retirar na loja é integrado ao Bing Maps. Pode ser usado para localizar lojas próximas onde os cliente podem retirar os produtos comprados.
- **Módulos de compra** – Os módulos de compra têm o módulo do carrinho que pode ser usado para adicionar itens ao carrinho. O módulo de finalização de compra captura o endereço de remessa, opções de entrega e vale-presente, programa de fidelidade e informações do cartão de crédito, de forma que uma ordem possa ser processada. Depois que uma ordem é efetuada, o módulo de confirmação de ordem pode ser usado para exibir os detalhes da confirmação.
- **Módulos de gerenciamento da conta** – O módulo de login permite que os clientes entrem em uma conta existente e o módulo de inscrição permite que eles criem uma nova conta. Depois que uma conta é criada, o módulo do histórico da ordem pode ser usado para exibir as ordens recentes e o módulo de detalhes da ordem pode ser usado para exibir os detalhes da ordem.
- **Módulo de recomendações** – As recomendações são mostradas usando o módulo de posicionamento do produto. Este módulo suporta as listas algorítmicas e de editorial que podem ser apresentadas em qualquer página.

## <a name="additional-resources"></a>Recursos adicionais

[Módulo de contêiner](add-container-module.md)

[Módulo de caixa de compra](add-buy-box.md)

[Módulo de carrinho](add-cart-module.md)

[Módulo de finalização da compra](add-checkout-module.md)

[Módulo de confirmação da ordem](order-confirmation-module.md)

[Módulo de cabeçalho](author-header-module.md)

[Módulo de rodapé](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
---
title: Módulo de cabeçalho
description: Este tópico abrange os módulos de cabeçalho e descreve como criá-los no Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 10/31/2019
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
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: d393701dacb88ab03a4b56724d93c794da6bb5c8
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697266"
---
# <a name="header-module"></a>Módulo de cabeçalho

[!include [banner](includes/preview-banner.md)] [!include [banner](includes/banner.md)]

Este tópico abrange os módulos de cabeçalho e descreve como criá-los no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

Um módulo de cabeçalho é um contêiner especial usado para todos os módulos que serão mostrados em um cabeçalho de página. Por exemplo, pode incluir o logotipo do site, links para a hierarquia de navegação, links para outras páginas no site e a barra de pesquisa.

Um módulo de cabeçalho é otimizado automaticamente paro dispositivo onde o site está sendo exibido (isto é, um dispositivo da área de trabalho ou um dispositivo móvel). Por exemplo, em um dispositivo móvel, a barra de navegação é recolhida em um botão **Menu** (que é conhecido ocasionalmente como *menu hambúrguer*).

## <a name="properties-of-a-header"></a>Propriedades de um cabeçalho

Como contêiner genéricos, um módulo de cabeçalho suporta as propriedades de **cabeçalho** e **largura** .

Um módulo de cabeçalho tem várias slots. Por exemplo, há slots para uma mensagem informativa, um menu de navegação, um logotipo, uma barra de pesquisa, um ícone móvel, um ícone da lista de objetivos e informações da conta. Cada slot suporta um conjunto específico de módulos.

## <a name="modules-that-are-available-in-a-header-module"></a>Módulos disponíveis em um módulo de cabeçalho

Os módulos a seguir podem ser usados em um módulo de cabeçalho:

- **Menu de navegação** – O menu de navegação representa a hierarquia de navegação de canal e outros links estáticos de navegação. A hierarquia de navegação de canal pode ser configurada no Dynamics 365 Retail. Os itens configurados aparecerão como navegação de cabeçalho. Além disso, links estáticos de navegação podem ser configurados e links links relativos a outras páginas no site comercial online pode ser promovido. O cabeçalho em si pode ser alinhado à esquerda e direita ou no centro.
- **Ícone de carrinho** – O ícone de carrinho é um ícone especial que representa o carrinho. É exibido no cabeçalho e indica o número de itens no carrinho. Um link para a página do carrinho deve acompanhar o ícone do carrinho para que os clientes possam ser redirecionados à página do carrinho quando interagem com o ícone.
- **Ícone da lista de desejos** – O ícone da lista de desejos é exibido no cabeçalho e indica o número de itens que foram adicionados à lista de desejos do cliente. Um link para a página de lista de desejos deve acompanhar esse ícone para que os clientes possam ser redirecionados à página de lista de desejos quando interagem com o ícone.
- **Módulo de login** – O módulo de login é exibido no cabeçalho. Permite que os clientes entrem em sua conta ou se inscrevam em uma conta. Se o cliente já estiver conectado, o módulo pode ser configurado para exibir links na página da conta, a página de histórico de ordens ou outra página.
- **Módulo de logotipo** – Este módulo mostra o logotipo representando o fornecedor e a marca. É uma imagem que tem o link. O link é normalmente configurado de forma que possa redirecionar para a página principal. Portanto, os clientes podem retornar rapidamente para a página inicial de qualquer página no site.
- **Alerta** – Um alerta é exibido no cabeçalho e é usado para mostrar a mensagem embutida que se aplica a quaisquer páginas no site. Por exemplo, o alerta pode mostrar a mensagem como "Venda anual termina em 2 dias".
- **Barra de pesquisa** – A barra de tarefas permite que o usuário insira tais termos para que possam pesquisar por produtos. O módulo deve ser configurado com a URL da página de resultados de busca. O parâmetro de sequência de pesquisa pode ser configurado (o valor padrão é **"q"**). A barra de pesquisa têm um slot de sugestão automática que sugere automaticamente o módulo que deve ser adicionado.
- **Sugestão automática** – O módulo de sugestão automática mostra resultados sugeridos automaticamente. Os resultados podem ser palavras-chave, produtos ou categorias onde o termo de pesquisa é encontrado.

## <a name="create-a-header-module"></a>Criar um módulo de cabeçalho

Para criar um módulo de cabeçalho, siga estas etapas.

1. Criar um fragmento de página que inclui um módulo de cabeçalho.
1. Adicionar os módulos aos slots no módulo de cabeçalho.
1. Atualizar as configurações de cada módulo.
1. Salvar o fragmento de página. 
1. Insira a página e publique-a.

Para ajudar a garantir que um cabeçalho aparece em cada página, siga estas etapas em cada modelo da página que é desenvolvido para o site.

1. Na página padrão, adicione a parte mais importante da página que contém o módulo de cabeçalho no cabeçalho no slot principal.
1. Salve o modelo. 
1. Faça check-in do modelo e publique-o.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do kit de início](starter-kit-overview.md)

[Módulo de contêiner](add-container-module.md)

[Comprar módulo de caixa](add-buy-box.md)

[Módulo de carrinho](add-cart-module.md)

[Módulo de finalização da compra](add-checkout-module.md)

[Módulo de confirmação da ordem](order-confirmation-module.md)

[Módulo de cabeçalho](author-header-module.md)

[Módulo de rodapé](author-footer-module.md)

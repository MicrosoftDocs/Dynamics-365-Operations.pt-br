---
title: Módulo de detalhes da ordem
description: Este tópico abrange os módulos de detalhes da ordem e descreve como usá-los no Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 01/23/2020
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
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: cb09a0b6ce1e48707f96021e9fad0006d9c1c55c
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2020
ms.locfileid: "3026008"
---
# <a name="order-details-module"></a>Módulo de detalhes da ordem


[!include [banner](includes/banner.md)]

Este tópico abrange os módulos de detalhes da ordem e descreve como usá-los no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

O módulo de detalhes de ordem é usado para mostrar detalhes da confirmação da ordem após ela ser colocada. Ele mostra a ID de confirmação da ordem, as informações de contato da ordem e outros detalhes da ordem, como os itens que foram comprados, as informações de pagamento e o método de remessa.

## <a name="order-confirmation-module-properties"></a>Propriedades do módulo de confirmação da ordem

| Nome da propriedade  | Valores | Descrição |
|----------------|--------|-------------|
| Cabeçalho        | Texto do cabeçalho e tag do cabeçalho (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | O módulo de confirmação da ordem pode ter um título. Por padrão, a tag de cabeçalho **H2** é usada para o cabeçalho. No entanto, a tag pode ser alterada para atender aos requisitos de acessibilidade. |
| Número do contato | Text | Um número de contato pode ser fornecido para perguntas relativas a ordens. |

## <a name="modules-that-can-be-used-on-an-order-details-page"></a>Os módulos que podem ser usados em uma página de detalhes da ordem

Ao criar uma página de detalhes da ordem, você pode adicionar outros módulos relevantes além do módulo de detalhes da ordem. Eis alguns exemplos:

- **Módulo de recomendações** – O módulo de recomendações pode ser adicionado à página de detalhes da ordem para sugerir outros produtos para o cliente.
- **Módulos de marketing** – qualquer módulo de marketing pode ser adicionado à página de detalhes da ordem para mostrar o conteúdo de marketing.

## <a name="create-an-order-details-page-module"></a>Criar um módulo da página de detalhes da ordem

1. Criar um modelo da página chamado **Modelo de detalhes da ordem**.
1. No slot **Principal** da página padrão, adicione um módulo de detalhes da ordem.
1. No módulo de detalhes da ordem, adicione um módulo de recomendações.
1. Salve e exiba o modelo. O módulo de detalhes da ordem não será processado porque ele exige o contexto do número de confirmação da ordem.
1. Termine de editar o modelo e publique-o.
1. Use o modelo de detalhes da ordem recém-criado para criar uma página chamada **página de detalhes da ordem**.
1. Adicione a página padrão à descrição da página.
1. No slot **Cabeçalho** , adicione um fragmento do cabeçalho.
1. No slot **Rodapé** , adicione um fragmento do rodapé.
1. No slot **Principal**, adicione um módulo de detalhes da ordem.
1. No painel de propriedade do módulo de detalhes da ordem, adicione o título **Detalhes da ordem**.
1. Abaixo do módulo de detalhes da ordem, adicione um módulo de recomendações e configure-o de forma que ele use as configurações **Novo** e **Mais Vendidos**.
1. Salve e exiba a página.
1. Termine de editar a página e publique-a.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do kit de início](starter-kit-overview.md)

[Módulo de contêiner](add-container-module.md)

[Módulo de caixa de compra](add-buy-box.md)

[Módulo de carrinho](add-cart-module.md)

[Módulo de finalização da compra](add-checkout-module.md)

[Módulo de cabeçalho](author-header-module.md)

[Módulo de rodapé](author-footer-module.md)

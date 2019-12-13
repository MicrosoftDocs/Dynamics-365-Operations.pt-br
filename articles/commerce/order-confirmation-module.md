---
title: Módulo de confirmação da ordem
description: Este tópico abrange os módulos de confirmação da ordem e descreve como criá-los no Microsoft Dynamics 365 Commerce.
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
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e339ce02bb646d0d9a68c22b24fde9b72071de6f
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698317"
---
# <a name="order-confirmation-module"></a>Módulo de confirmação da ordem

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tópico abrange os módulos de confirmação da ordem e descreve como criá-los no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

Um módulo de confirmação de ordem será usado para mostrar a mensagem de confirmação em uma página de confirmação da ordem, depois que uma ordem é efetuada. O módulo de confirmação da ordem mostra o número de confirmação da ordem e o endereço de email do cliente fornecido durante a finalização da compra.

Quando uma ordem é efetuada durante a finalização da compra, o número de confirmação da ordem e o endereço de email do cliente são passados para a página de confirmação da ordem como uma cadeia de caracteres de consulta na URL da página. O módulo de confirmação da ordem recebe estas informações e renderiza o status da ordem na página de confirmação da ordem. O módulo de confirmação da ordem exige que este contexto da página forneça o status da ordem.

## <a name="order-confirmation-module-properties"></a>Propriedades do módulo de confirmação da ordem

| Nome da propriedade | Valores | Descrição |
|---------------|--------|-------------|
| Cabeçalho       | Texto do cabeçalho e tag do cabeçalho (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | O módulo de confirmação da ordem pode ter um título. Por padrão, a tag de cabeçalho **H2** é usada para o cabeçalho. No entanto, a tag pode ser alterada para atender aos requisitos de acessibilidade. |

## <a name="modules-that-can-be-used-in-an-order-confirmation-page-module"></a>Os módulos que podem ser usados em um módulo da página de confirmação da ordem 

- **Recomendações** – O módulo de recomendações pode ser colocado na página de confirmação da ordem para sugerir outros produtos para o cliente.
- **Marketing** – O módulo de marketing pode adicionar o conteúdo de marketing à página de confirmação da ordem.

## <a name="create-an-order-confirmation-page-module"></a>Criar um módulo da página de confirmação da ordem

1. Criar um modelo da página chamado **modelo de confirmação da ordem**.
1. No slot **Principal** da página padrão, adicione um módulo de confirmação da ordem.
1. No módulo de confirmação da ordem, adicione um módulo de recomendações.
1. Salve e exiba o modelo. O módulo de confirmação da ordem não deve ser processado porque exige o contexto do número de confirmação da ordem.
1. Faça check-in do modelo e publique-o.
1. Use o modelo de confirmação da ordem que você acabou de criar para criar uma página chamada **página de confirmação da ordem**.
1. Adicione a página padrão à descrição da página.
1. No slot **Cabeçalho** , adicione um fragmento do cabeçalho.
1. No slot **Rodapé** , adicione um fragmento do rodapé.
1. No slot **Principal**, adicione um módulo de confirmação da ordem.
1. No painel de propriedade do módulo de confirmação da ordem, adicione o título **Confirmação da ordem**.
1. Abaixo do módulo de confirmação da ordem, adicione um módulo de recomendações e configure-o de forma que ele use as configurações **Novo** e **Mais Vendidos**.
1. Salve e visualize a página, faça check-in e publique-a.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do kit de início](starter-kit-overview.md)

[Módulo de contêiner](add-container-module.md)

[Módulo de caixa de compra](add-buy-box.md)

[Módulo de carrinho](add-cart-module.md)

[Módulo de finalização da compra](add-checkout-module.md)

[Módulo de cabeçalho](author-header-module.md)

[Módulo de rodapé](author-footer-module.md)

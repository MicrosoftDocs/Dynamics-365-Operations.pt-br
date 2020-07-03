---
title: Módulo de detalhes da ordem
description: Este tópico abrange os módulos de detalhes da ordem e descreve como usá-los no Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 06/18/2020
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
ms.openlocfilehash: c2ec629d9fd027be01652351ab1c99001e063e30
ms.sourcegitcommit: 49656661c89c864e8e067259a601c3bbceb8bef4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/18/2020
ms.locfileid: "3464921"
---
# <a name="order-details-module"></a>Módulo de detalhes da ordem


[!include [banner](includes/banner.md)]

Este tópico abrange os módulos de detalhes da ordem e descreve como usá-los no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

O módulo de detalhes de ordem é usado para mostrar detalhes da confirmação da ordem após ela ser colocada. Ele mostra a ID de confirmação da ordem, as informações de contato da ordem e outros detalhes da ordem, como os itens que foram comprados, as informações de pagamento e o método de remessa.

## <a name="order-details-module-properties"></a>Propriedades do módulo de detalhes da ordem

| Nome da propriedade  | Valores | descrição |
|----------------|--------|-------------|
| Título        | Texto do cabeçalho e tag do cabeçalho (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | O módulo de detalhes da ordem pode ter um título. Por padrão, a tag de cabeçalho **H2** é usada para o cabeçalho. No entanto, a tag pode ser alterada para atender aos requisitos de acessibilidade. |
| Número do contato | Text | Um número de contato pode ser fornecido para perguntas relativas a ordens. |

## <a name="modules-that-can-be-used-on-an-order-details-page"></a>Os módulos que podem ser usados em uma página de detalhes da ordem

Ao criar uma página de detalhes da ordem, você pode adicionar outros módulos relevantes além do módulo de detalhes da ordem. Eis alguns exemplos:

- **Módulo de recomendações** – O módulo de recomendações pode ser adicionado à página de detalhes da ordem para sugerir outros produtos para o cliente.
- **Módulos de marketing** – qualquer módulo de marketing pode ser adicionado à página de detalhes da ordem para mostrar o conteúdo de marketing.

## <a name="add-an-order-details-module-to-a-page"></a>Adicionar um módulo de detalhes da ordem a uma página

Para adicionar um módulo de detalhes da ordem a uma nova página e definir as propriedades necessárias, siga estas etapas.

1. Vá para **Modelos** e selecione **Novo** para criar um novo modelo.
1. Na caixa de diálogo **Novo Modelo**, em **Nome do modelo**, insira o nome **Modelo de detalhes da ordem** e selecione **OK**.
1. No slot **Corpo**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Página padrão** e, depois, **OK**.
1. No slot **Principal** do módulo **Página Padrão**, selecione as reticências (**...**) e, em seguida, **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Detalhes da ordem** e, em seguida, **OK**.
1. Selecione **Salvar** e, em seguida, **Visualizar** para visualizar o modelo. O módulo de detalhes da ordem não será processado porque ele exige o contexto do número de confirmação da ordem.
1. Selecione **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.
1. Vá para **Páginas** e selecione **Novo** para criar uma nova página.
1. Na caixa de diálogo **Escolher um modelo**, selecione o **modelo Detalhes da ordem**. Em **Nome da página**, insira **página Detalhes da ordem** e selecione **OK**.
1. No slot **Principal** do módulo **Página Padrão**, selecione as reticências (**...**) e, em seguida, **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Detalhes da ordem** e, em seguida, **OK**.
1. No painel de propriedades do módulo de detalhes da ordem, selecione **Título** ao lado do símbolo de lápis.
1. No campo **Texto do Título** da caixa de diálogo **Título**, insira o texto do título **Detalhes da ordem** e, em seguida, selecione **OK**.
1. Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página.
1. Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do kit de início](starter-kit-overview.md)

[Módulo de contêiner](add-container-module.md)

[Módulo de caixa de compra](add-buy-box.md)

[Módulo de carrinho](add-cart-module.md)

[Módulo de finalização da compra](add-checkout-module.md)

[Módulo de cabeçalho](author-header-module.md)

[Módulo de rodapé](author-footer-module.md)

---
title: Módulo de confirmação da ordem
description: Este tópico abrange os módulos de confirmação da ordem e descreve como usá-los no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 11/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 407fc2724d4b589ef5f611974f9358e879dba7ed
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5257138"
---
# <a name="order-confirmation-module"></a>Módulo de confirmação da ordem

[!include [banner](includes/banner.md)]

Este tópico abrange os módulos de confirmação da ordem e descreve como usá-los no Microsoft Dynamics 365 Commerce.

O módulo de confirmação da ordem é usado para mostrar detalhes da confirmação da ordem após ela ser realizada. Ele mostra a ID de confirmação, as informações de contato e outros detalhes da ordem, como os itens que foram comprados, as informações de pagamento, as opções de retirada e o método de remessa.

## <a name="order-confirmation-module-properties"></a>Propriedades do módulo de confirmação da ordem

| Nome da propriedade  | Valores | Descrição |
|----------------|--------|-------------|
| Cabeçalho        | Texto do cabeçalho e tag do cabeçalho (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | O módulo de confirmação da ordem pode ter um título. Por padrão, a tag de cabeçalho **H2** é usada para o cabeçalho. No entanto, a tag pode ser alterada para atender aos requisitos de acessibilidade. |
| Número do contato | Text | Um número de contato pode ser fornecido para perguntas relativas a ordens. |
| Mostrar informações do intervalo de tempo de retirada | Verdadeiro ou Falso | Esta propriedade está disponível no Dynamics 365 Commerce 10.0.15 e superiores. Quando verdadeira, ela exibe as informações do intervalo de tempo de retirada, se forem fornecidas, de um item de retirada|

## <a name="modules-that-can-be-used-on-an-order-confirmation-page"></a>Módulos que podem ser usados em uma página de confirmação da ordem

Ao criar uma página de confirmação da ordem, você pode adicionar outros módulos relevantes além do módulo de confirmação da ordem. Eis alguns exemplos:

- **Módulo de recomendações** – O módulo de recomendações pode ser adicionado à página de confirmação da ordem para sugerir outros produtos para o cliente.
- **Módulos de marketing** – Qualquer módulo de marketing pode ser adicionado à página de confirmação da ordem para mostrar conteúdo de marketing.

## <a name="add-an-order-confirmation-module-to-a-page"></a>Adicionar um módulo de confirmação da ordem a uma página

Para adicionar um módulo de confirmação da ordem a uma nova página e definir as propriedades necessárias, siga estas etapas.

1. Vá para **Modelos** e selecione **Novo** para criar um novo modelo.
1. Na caixa de diálogo **Novo Modelo**, em **Nome do modelo**, insira o nome **Modelo de confirmação da ordem** e selecione **OK**.
1. No slot **Corpo**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Página padrão** e, depois, **OK**.
1. No slot **Principal** do módulo **Página Padrão**, selecione as reticências (**...**) e, em seguida, **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Confirmação da ordem** e, em seguida, **OK**.
1. Selecione **Salvar** e, em seguida, **Visualizar** para visualizar o modelo. O módulo de confirmação da ordem não será renderizado porque exige o contexto do número de confirmação da ordem.
1. Selecione **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.
1. Vá para **Páginas** e selecione **Novo** para criar uma nova página.
1. Na caixa de diálogo **Escolher um modelo**, selecione **Modelo de confirmação da ordem**. Em **Nome da página**, insira **Página de confirmação da ordem** e selecione **OK**.
1. No slot **Principal** do módulo **Página Padrão**, selecione as reticências (**...**) e, em seguida, **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Confirmação da ordem** e, em seguida, **OK**.
1. No painel de propriedades do módulo de confirmação da ordem, selecione **Título** ao lado do símbolo de lápis.
1. No campo **Texto do Título** da caixa de diálogo **Título**, insira o texto do título **Confirmação da ordem** e, em seguida, selecione **OK**.
1. Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página.
1. Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.

## <a name="additional-resources"></a>Recursos adicionais

[Módulo de carrinho](add-cart-module.md)

[Módulo de ícone de carrinho](cart-icon-module.md)

[Módulo de finalização da compra](add-checkout-module.md)

[Módulo de pagamento](payment-module.md)

[Módulo de endereço de remessa](ship-address-module.md)

[Módulo de opções de entrega](delivery-options-module.md)

[Módulo de informações sobre retirada](pickup-info-module.md)

[Módulo de cartão-presente](add-giftcard.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
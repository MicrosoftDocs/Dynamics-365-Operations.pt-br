---
title: Módulo de confirmação da ordem
description: Este artigo abrange os módulos de confirmação da ordem e descreve como usá-los no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 6011c7e4713813a02fa8f812ea8981fd6fa0253f
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269126"
---
# <a name="order-confirmation-module"></a>Módulo de confirmação da ordem

[!include [banner](includes/banner.md)]

Este artigo abrange os módulos de confirmação da ordem e descreve como usá-los no Microsoft Dynamics 365 Commerce.

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

1. Acesse **Modelos** e selecione **Novo** para criar um novo modelo.
1. Na caixa de diálogo **Novo modelo**, em **Nome do modelo**, insira o nome **Modelo de confirmação da ordem** e selecione **OK**.
1. No slot **Corpo**, selecione as reticências (**...**) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Página padrão** e, depois, **OK**.
1. No slot **Principal** do módulo **Página padrão**, selecione as reticências (**...**) e, em seguida, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Confirmação da ordem** e, depois, **OK**.
1. Selecione **Salvar** e, em seguida, **Visualizar** para visualizar o modelo. O módulo de confirmação da ordem não será renderizado porque exige o contexto do número de confirmação da ordem.
1. Selecione **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.
1. Acesse **Páginas** e selecione **Novo** para criar uma nova página.
1. Na caixa de diálogo **Criar uma nova página**, em **Nome da página**, insira **Página Confirmação de ordem** e selecione **Avançar**.
1. Em **Escolher um modelo**, selecione o **Módulo de confirmação da ordem** e escolha **Avançar**.
1. Em **Escolher um layout**, selecione um layout de página (por exemplo, **Layout flexível**) e selecione **Avançar**.
1. Em **Revisar e concluir**, revise a configuração da página. Se você precisar editar as informações da página, selecione **Voltar**. Se as informações da página estiverem corretas, selecione **Criar página**. 
1. No slot **Principal** do módulo **Página padrão**, selecione as reticências (**...**) e, em seguida, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Confirmação da ordem** e, depois, **OK**.
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

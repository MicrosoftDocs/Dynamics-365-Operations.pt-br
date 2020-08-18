---
title: Módulo de carrinho
description: Este tópico abrange os módulos de carrinho e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 05/28/2020
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
ms.openlocfilehash: f21268ed4cffed1d5c789f722796cdf05e965819
ms.sourcegitcommit: 4a981ee4be6d7e6c0e55541535d386bce2565cba
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/27/2020
ms.locfileid: "3621027"
---
# <a name="cart-module"></a>Módulo de carrinho

[!include [banner](includes/banner.md)]

Este tópico abrange os módulos de carrinho e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão Geral

Um módulo de carrinho mostra os itens que foram adicionados ao carrinho antes de o cliente prosseguir para finalizar a compra. O módulo também mostra um resumo da ordem e permite que o cliente aplique ou remova códigos promocionais.

O módulo do carrinho oferece suporte a finalização de compra em conexão e a finalização de compra de convidado. Ele também oferece suporte ao link **Voltar para compra**. Você pode configurar o roteiro desse link em **Configurações de Site \> Extensões \> Roteiros**.

O módulo do carrinho processa os dados com base na ID do carrinho, que é um cookie do navegador disponível em todo o site. 

A imagem a seguir mostra um exemplo de uma página de carrinho no site da Fabrikam.

![Exemplo de um módulo de carrinho](./media/cart2.PNG)

## <a name="cart-module-properties-and-slots"></a>Propriedades e slots do módulo de carrinho

O módulo do carrinho tem uma propriedade **Título** que pode ser definida com valores como **Sacola de compras** e **Itens no seu carrinho**. 

## <a name="modules-that-can-be-used-in-a-cart-module"></a>Módulos que podem ser usados em um módulo de carrinho

- **Bloco de texto** – Este módulo fornece suporte a mensagens personalizadas no módulo de carrinho. As mensagens são direcionadas pelo sistema de gerenciamento de conteúdo (CMS). Qualquer mensagem pode ser adicionada, como "Caso você tenha problemas com o pedido, entre em contato com 1-800-Fabrikam".
- **Seletor de loja** – Este módulo mostra uma lista de lojas próximas, onde um item está disponível para retirada. Ele permite que os usuários insiram um local para encontrar lojas próximas. Para obter mais informações sobre este módulo, consulte [Módulo do seletor de armazenamento](store-selector.md).

## <a name="module-properties"></a>Propriedades do módulo

As seguintes configurações de módulo de carrinho podem ser definidas em **Configurações de Site \> Extensões**:

- **Quantidade máxima** – Esta propriedade é usada para especificar o número máximo de cada item que pode ser adicionado ao carrinho. Por exemplo, um varejista pode decidir que apenas 10 de cada produto podem ser vendidos em uma única transação.
- **Estoque** – para obter informações sobre como aplicar configurações de estoque, consulte [Aplicar configurações de estoque](inventory-settings.md).
- **Voltar para compra** – Esta propriedade é usada para especificar o roteiro do link **Voltar para compra**. O roteiro pode ser configurado no nível do site, permitindo que os varejistas retornem o cliente para a Home Page ou qualquer outra página no site.

## <a name="commerce-scale-unit-interaction"></a>Interação do Commerce Scale Unit

O módulo de carrinho recupera informações do produto usando as APIs de Commerce Scale Unit. A ID de carrinho do cookie do navegador é usada para recuperar todas as informações do produto direto do Commerce Scale Unit.

## <a name="add-a-cart-module-to-a-page"></a>Adicionar um módulo de carrinho a uma página

Para adicionar um módulo de carrinho a uma nova página e definir as propriedades necessárias, siga estas etapas.

1. Vá para **Fragmentos de Página** e selecione **Novo** para criar um novo fragmento.
1. Na caixa de diálogo **Novo Fragmento de Página**, selecione o módulo **Carrinho**.
1. Em **Nome do Fragmento de Página**, digite o nome **Fragmento de carrinho** e selecione **OK**.
1. Selecione o slot **Carrinho**.
1. No painel de propriedades à direita, selecione o símbolo de lápis, digite o texto do título no campo e, em seguida, selecione o símbolo de marca de seleção.
1. No slot **Carrinho**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Seletor de loja** e, depois, **OK**.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in do fragmento e depois selecione **Publicar** para publicá-lo.
1. Vá para **Modelos** e selecione **Novo** para criar um novo modelo.
1. Na caixa de diálogo **Novo Modelo**, em **Nome do modelo**, insira um nome para o modelo.
1. Na árvore de estrutura de tópicos, selecione o slot **Corpo**, as reticências (**...**) e, depois, **Adicionar Fragmento**.
1. Na caixa de diálogo **Selecionar Fragmento de Página**, selecione o fragmento **Fragmento de carrinho** e **OK**.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.
1. Vá para **Páginas** e selecione **Novo** para criar uma nova página.
1. Na caixa de diálogo **Escolher um modelo**, selecione o modelo que você criou, insira um nome de página e selecione **OK**.
1. Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página.
1. Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do kit de início](starter-kit-overview.md)

[Módulo de contêiner](add-container-module.md)

[Módulo de seletor de loja](store-selector.md)

[Módulo de caixa de compra](add-buy-box.md)

[Módulo de ícone de carrinho](cart-icon-module.md)

[Módulo de finalização da compra](add-checkout-module.md)

[Módulo de confirmação da ordem](order-confirmation-module.md)

[Módulo de cabeçalho](author-header-module.md)

[Módulo de rodapé](author-footer-module.md)

[Calcular disponibilidade de estoque para canais de varejo](calculated-inventory-retail-channels.md)

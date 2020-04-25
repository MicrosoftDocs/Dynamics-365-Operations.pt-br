---
title: Módulo de carrinho
description: Este tópico abrange os módulos de carrinho e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 04/13/2020
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
ms.openlocfilehash: d91f6ff24f8f2c051ed23565983c2bc6a2c12b55
ms.sourcegitcommit: ac966ea3a6c557fb5f9634b187b0e788d3e82d4d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2020
ms.locfileid: "3261412"
---
# <a name="cart-module"></a>Módulo de carrinho

[!include [banner](includes/banner.md)]

Este tópico abrange os módulos de carrinho e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão Geral

Um módulo de carrinho mostra os itens que foram adicionados ao carrinho antes de o cliente prosseguir para finalizar a compra. O módulo também mostra um resumo da ordem e permite que o cliente aplique ou remova códigos promocionais.

O módulo do carrinho oferece suporte a finalização de compra em conexão e a finalização de compra de convidado. Ele também oferece suporte ao link **Voltar para compra**. Você pode configurar o roteiro desse link em **Configurações de Site \> Extensões \> Roteiros**.

O módulo do carrinho processa os dados com base na ID do carrinho, que é um cookie do navegador disponível em todo o site.

## <a name="cart-module-properties-and-slots"></a>Propriedades e slots do módulo de carrinho

O módulo do carrinho tem uma propriedade **Título** que pode ser definida com valores como **Sacola de compras** e **Itens no seu carrinho**. 

## <a name="modules-that-can-be-used-in-a-cart-module"></a>Módulos que podem ser usados em um módulo de carrinho

- **Bloco de texto** – Este módulo fornece suporte a mensagens personalizadas no módulo de carrinho. As mensagens são direcionadas pelo sistema de gerenciamento de conteúdo (CMS). Qualquer mensagem pode ser adicionada, como "Caso você tenha problemas com o pedido, entre em contato com 1-800-Fabrikam".
- **Seletor de loja** – Este módulo mostra uma lista de lojas próximas, onde um item está disponível para retirada. Ele permite que os usuários insiram um local para encontrar lojas próximas. Para obter mais informações sobre este módulo, consulte [Módulo do seletor de armazenamento](store-selector.md).


## <a name="module-properties"></a>Propriedades do módulo

Os módulos de carrinho têm as seguintes configurações que podem ser definidas em **Configurações de Site \> Extensões**:

- **Quantidade máxima** – Esta propriedade é usada para especificar o número máximo de cada item que pode ser adicionado ao carrinho. Por exemplo, um varejista pode decidir que apenas 10 de cada produto podem ser vendidos em uma única transação.
- **Verificação de estoque** – Quando o valor é definido como **Verdadeiro**, um item é adicionado ao carrinho somente após o módulo da caixa de compra garantir que ele esteja em estoque. Essa verificação de estoque é feita tanto para os cenários em que o item será enviado como para os cenários em que ele será retirado na loja. Se o valor estiver definido como **Falso**, nenhuma verificação de estoque será feita antes que um item seja adicionado ao carrinho e a ordem seja feita. Para obter informações sobre como definir as configurações de estoque no back office, consulte [Calcular a disponibilidade de estoque para canais de varejo](calculated-inventory-retail-channels.md).
- **Buffer de estoque** – Esta propriedade é usada para especificar um número de buffer para o estoque. O estoque é mantido em tempo real e, quando muitos clientes fazem pedidos, pode ser difícil manter uma contagem precisa do estoque. Quando uma verificação de estoque é feita, se o estoque for menor que a quantidade do buffer, o produto é tratado como esgotado no estoque. Sendo assim, quando as vendas ocorrem rapidamente por meio de vários canais, e a contagem do estoque não está totalmente sincronizada, há menos risco de que um item esgotado no estoque seja vendido.
- **Voltar para compra** – Esta propriedade é usada para especificar o roteiro do link **Voltar para compra**. O roteiro pode ser configurado no nível do site, permitindo que os varejistas retornem o cliente para a Home Page ou qualquer outra página no site.

## <a name="commerce-scale-unit-interaction"></a>Interação do Commerce Scale Unit

O módulo de carrinho recupera informações do produto usando as APIs de Commerce Scale Unit. A ID de carrinho do cookie do navegador é usada para recuperar todas as informações do produto direto do Commerce Scale Unit.

## <a name="add-a-cart-module-to-a-page"></a>Adicionar um módulo de carrinho a uma página

Para adicionar um módulo de carrinho a uma nova página e definir as propriedades necessárias, siga estas etapas.

1. Crie um fragmento chamado **Fragmento do carrinho** e adicione um módulo ao novo fragmento.
1. Adicione um título ao módulo de carrinho.
1. Adicione um módulo de seletor de loja ao módulo de carrinho.
1. Salve o fragmento, termine de editá-lo e publique o fragmento.
1. Crie um modelo chamado **Modelo de carrinho** e adicione o fragmento do carrinho que você acabou de criar.
1. Salve o modelo, termine de editá-lo e publique o modelo.
1. Crie uma página que use o novo modelo.
1. Salve e exiba a página.
1. Termine a edição da página e publique-a.

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

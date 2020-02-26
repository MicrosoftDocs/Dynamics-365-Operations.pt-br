---
title: Módulo de finalização da compra
description: Este tópico descreve como adicionar um módulo de finalização da compra a uma página e definir as propriedades necessárias.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3805c0faabc8afc3decffb924b7f25332ff1ab16
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025381"
---
# <a name="checkout-module"></a>Módulo de finalização da compra


[!include [banner](includes/banner.md)]

Este tópico descreve como adicionar um módulo de finalização da compra a uma página e definir as propriedades necessárias.

## <a name="overview"></a>Visão geral

Um módulo de finalização da compra é um contêiner especial que hospeda todos os módulos necessários para criar um pedido. Apresenta um fluxo passo a passo que um cliente usa para inserir todas as informações relevantes para fazer uma compra. Ele captura o endereço de remessa, o método de remessa e as informações de cobrança. Ele também fornece um resumo do pedido e outras informações relacionadas a um pedido do cliente.

Um módulo de finalização da compra renderiza dados com base na ID de carrinho. Essa ID de carrinho é salva como um cookie do navegador. É necessária uma ID de carrinho para renderizar informações no módulo de finalização da compra, como os itens da ordem, o valor total e os descontos.

## <a name="checkout-module-properties"></a>Propriedades do módulo de finalização da compra

Um módulo de finalização de compra mostra um resumo do pedido e fornece a funcionalidade para a realização de um pedido. Para coletar todas as informações de cliente necessárias antes que um pedido possa ser feito, os módulos adicionais devem ser adicionados ao módulo de finalização de compra. Portanto, os varejistas têm a flexibilidade de adicionar módulos personalizados ao fluxo de finalização de compra ou a excluir módulos, de acordo com suas necessidades.

### <a name="modules-that-can-be-used-in-the-checkout-module"></a>Módulos que podem ser usados no módulo de finalização da compra

- **Endereço de remessa** – Este módulo permite que um cliente adicione ou selecione o endereço de remessa para uma ordem. Se o cliente estiver conectado, quaisquer endereços que foram salvos anteriormente para esse cliente serão mostrados. O cliente pode então selecionar entre esses endereços. O cliente também pode adicionar um novo endereço. O endereço de remessa é usado para todos os itens na ordem que requerem remessa. Não é possível personalizá-lo para itens de linha individuais. Os formatos de endereço de remessa são definidos para cada país ou região e as regras específicas de país/região são aplicadas por esse módulo. Embora esse módulo não forneça validação de endereço, a validação de endereço pode ser implementada por meio da personalização. Se a ordem incluir somente itens que serão retirados na loja, esse módulo ficará oculto automaticamente.
- **Opções de entrega** – Este módulo permite que um cliente selecione uma opção de entrega para uma ordem. As opções de entrega são baseadas no endereço de remessa. Se o endereço de remessa for alterado, as opções de entrega deverão ser recuperadas novamente. Se a ordem incluir somente itens que serão retirados na loja, esse módulo ficará oculto automaticamente.
- **Contêiner da seção de finalização da compra** – Este módulo é um contêiner dentro do qual é possível colocar vários módulos para criar uma seção dentro do fluxo de finalização da compra. Por exemplo, você pode colocar todos os módulos relacionados a pagamento dentro desse contêiner para que eles apareçam como uma seção. Esse módulo afeta apenas o layout do fluxo.
- **Vale-presente** – Este módulo permite que um cliente pague uma ordem usando um vale-presente. Ele só é compatível com vales-presente do Microsoft Dynamics 365 Commerce. Um ou mais vales-presente podem ser aplicados a uma ordem. Se o saldo do vale-presente não cobrir o valor do carrinho, ele poderá ser combinado com outra forma de pagamento. Os vales-presente podem ser resgatados apenas se o cliente estiver conectado.
- **Pontos de fidelidade** – Este módulo permite que um cliente pague uma ordem usando pontos de fidelidade. Ele fornece um resumo dos pontos disponíveis e pontos vencidos e permite que o cliente selecione o número de pontos a serem resgatados. Se o cliente não estiver conectado ou não for um membro de fidelidade, ou se o valor total no carrinho for 0 (zero), esse módulo ficará oculto automaticamente.
- **Pagamento** – Este módulo permite que um cliente pague um pedido usando um cartão de crédito. Se o valor total do carrinho estiver coberto por pontos de fidelidade ou vale-presente e ou se for 0 (zero), esse módulo ficará oculto automaticamente. A integração do cartão de crédito é fornecida pelo conector de pagamento Adyen para esse módulo. Para obter mais informações sobre como usar esse conector, consulte o [Conector de pagamento do Dynamics 365 para Adyen](dev-itpro/adyen-connector.md).
- **Endereço de cobrança** – Este módulo permite que um cliente forneça informações de cobrança. Essas informações são processadas, juntamente com as informações do cartão de crédito, pela Adyen. Essas informações são processadas, juntamente com as informações do cartão de crédito, pela Adyen.
- **Informações de contato** – Este módulo permite que um cliente adicione ou altere as informações de contato (endereço de email) de uma ordem.
- **Bloco de texto** – Este módulo contém mensagens controladas pelo sistema de gerenciamento de conteúdo (CMS). Por exemplo, ele pode conter uma mensagem informando "Caso você tenha problemas com uma ordem, entre em contato com 1-800-Fabrikam". 

## <a name="commerce-scale-unit-interaction"></a>Interação do Commerce Scale Unit

A maioria das informações de finalização da compra, como endereço e método de remessa, é armazenada no carrinho e processada como parte da ordem. A única exceção são as informações de cartão de crédito. Essas informações são processadas diretamente usando o conector de pagamento Adyen. O pagamento é autorizado, mas não é cobrado.

## <a name="add-a-checkout-module-to-a-new-page-and-set-the-required-properties"></a>Adicionar um módulo de finalização da compra a uma nova página e definir as propriedades necessárias

Para adicionar um módulo de finalização da compra a uma nova página e definir as propriedades necessárias, siga estas etapas.

1. Vá para **Fragmento \> Novo Fragmento** e nomeie o novo fragmento como **Fragmento de finalização da compra**.
1. Adicione um módulo de finalização da compra ao fragmento.
1. Adicione um cabeçalho ao módulo de finalização da compra.
1. Adicione módulos de endereço de remessa, opções de entrega, contêiner da seção de finalização de compra e informações de contato. 
1. No módulo de contêiner de finalização da compra, adicione módulos de vale-presente, pontos de fidelidade e pagamento. Dessa forma, verifique se todos os métodos de pagamento aparecem juntos em uma seção.
1. Salve e visualize o fragmento. Alguns módulos que não tem um contexto de carrinho talvez não sejam renderizados na visualização.
1. Termine de editar o fragmento e publique-o.
1. Crie um modelo que use o novo fragmento de finalização da compra.
1. Crie uma página de finalização da compra que use o novo modelo.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do kit de início](starter-kit-overview.md)

[Módulo de contêiner](add-container-module.md)

[Módulo de caixa de compra](add-buy-box.md)

[Módulo de carrinho](add-cart-module.md)

[Módulo de confirmação da ordem](order-confirmation-module.md)

[Módulo de cabeçalho](author-header-module.md)

[Módulo de rodapé](author-footer-module.md)

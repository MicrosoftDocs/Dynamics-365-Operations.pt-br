---
title: Módulo de finalização da compra
description: Este tópico descreve como adicionar um módulo de finalização da compra a uma página e definir as propriedades necessárias.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: 4b810441fd25d41ee0893b119b4f7d91e7435d21
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697074"
---
# <a name="checkout-module"></a>Módulo de finalização da compra

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tópico descreve como adicionar um módulo de finalização da compra a uma página e definir as propriedades necessárias.

## <a name="overview"></a>Visão geral

Um módulo de finalização da compra é um contêiner especial que hospeda todos os módulos necessários para criar uma ordem. Um módulo de finalização da compra pode incluir módulos que gerenciam o endereço de remessa, métodos de remessa, informações para cobrança, resumo da ordem e outras informações relacionadas a uma ordem do cliente. Apresenta um fluxo passo a passo que um cliente usa para inserir todas as informações relevantes para fazer uma compra.

Um módulo de finalização da compra renderiza dados com base na ID de carrinho. Essa ID de carrinho é salva como um cookie do navegador. É necessária uma ID de carrinho para renderizar informações no módulo de finalização da compra, como os itens da ordem, o valor total e os descontos.

## <a name="checkout-module-properties"></a>Propriedades do módulo de finalização da compra

Um módulo de finalização da compra hospeda um conjunto de módulos dentro dele. Uma propriedade Largura permite especificar se os itens no módulo de finalização da compra devem se ajustar à largura ou preencher a tela.

Um módulo de finalização da compra possui vários slots, como um slot **Informações de finalização da compra**, um slot **Resumo da ordem** e um slot **Colocar ordem**. Cada slot permite um conjunto de módulos que aparecerão em um layout específico na página. Por exemplo, o slot **Informações de finalização da compra** contém todos os módulos necessários para acionar uma finalização da compra, como módulos para o endereço de remessa e o método de pagamento. O slot **Resumo da ordem** mostra um resumo da ordem e permite a ação para colocar a ordem. O slot **Colocar ordem** também permite a ação para colocar a ordem. Os módulos de colocar a ordem podem ser definidos em dois slots para otimizar o processo de colocação de ordens de várias plataformas.

### <a name="modules-that-can-be-used-in-the-checkout-module"></a>Módulos que podem ser usados no módulo de finalização da compra

- **Endereço de remessa** – Este módulo permite que um cliente adicione ou selecione o endereço de remessa para uma ordem. Se o cliente estiver conectado, quaisquer endereços que foram salvos anteriormente para esse cliente serão mostrados. O cliente pode então selecionar entre esses endereços. O cliente também pode adicionar um novo endereço. O endereço de remessa é usado para todos os itens na ordem que requerem remessa. Não é possível personalizá-lo para itens de linha individuais. Os formatos de endereço de remessa são definidos para cada país ou região e as regras específicas de país/região são aplicadas por esse módulo. Embora esse módulo não forneça validação de endereço, a validação de endereço pode ser implementada por meio da personalização. Se a ordem incluir somente itens que serão retirados na loja, esse módulo ficará oculto automaticamente.
- **Opções de entrega** – Este módulo permite que um cliente selecione uma opção de entrega para uma ordem. As opções de entrega são baseadas no endereço de remessa. Se o endereço de remessa for alterado, as opções de entrega deverão ser recuperadas novamente. Se a ordem incluir somente itens que serão retirados na loja, esse módulo ficará oculto automaticamente.
- **Contêiner da seção de finalização da compra** – Este módulo é um contêiner dentro do qual é possível colocar vários módulos para criar uma seção dentro do fluxo de finalização da compra. Por exemplo, você pode colocar todos os módulos relacionados a pagamento dentro desse contêiner para que eles apareçam como uma seção. Esse módulo afeta apenas o layout do fluxo.
- **Vale-presente** – Este módulo permite que um cliente pague uma ordem usando um vale-presente. Ele só é compatível com vales-presente do Microsoft Dynamics 365 Commerce. Um ou mais vales-presente podem ser aplicados a uma ordem. Se o saldo do vale-presente não cobrir o valor do carrinho, ele poderá ser combinado com outra forma de pagamento. Os vales-presente podem ser resgatados apenas se o cliente estiver conectado.
- **Pontos de fidelidade** – Este módulo permite que um cliente pague uma ordem usando pontos de fidelidade. Ele fornece um resumo dos pontos disponíveis e pontos vencidos e permite que o cliente selecione o número de pontos a serem resgatados. Se o cliente não estiver conectado ou não for um membro de fidelidade, ou se o valor total no carrinho for 0 (zero), esse módulo ficará oculto automaticamente.
- **Cartão de crédito** – Este módulo permite que um cliente pague uma ordem usando um cartão de crédito. Se o valor total do carrinho estiver coberto por pontos de fidelidade ou vale-presente e ou se for 0 (zero), esse módulo ficará oculto automaticamente. A integração do cartão de crédito é fornecida pelo conector de pagamento Adyen. Para obter mais informações sobre como usar esse conector, consulte o [conector de pagamento Adyen](https://).
- **Endereço de cobrança** – Este módulo permite que um cliente forneça informações de cobrança. Essas informações são processadas, juntamente com as informações do cartão de crédito, pela Adyen. Essas informações são processadas, juntamente com as informações do cartão de crédito, pela Adyen.
- **Informações de contato** – Este módulo permite que um cliente adicione ou altere as informações de contato (endereço de email) de uma ordem.
- **Colocar ordem** – Este módulo permite que um cliente coloque uma ordem.
- **Bloco de conteúdo sofisticado** – Este módulo contém qualquer mensagem conduzida pelo sistema de gerenciamento de conteúdo (CMS). Por exemplo, pode conter uma mensagem informando "For issues with your order, please contact 1-800-FABRIKAM" (Caso você tenha problemas com uma ordem, entre em contato com 1-800-FABRIKAM). 
- **Resumo da ordem** – Este módulo mostra o detalhamento de custos de uma ordem.
- **Itens de linha de ordem** – Este módulo mostra um resumo dos itens que serão incluídos em uma ordem.

## <a name="retail-server-interaction"></a>Interação do Retail Server

A maioria das informações de finalização da compra, como endereço e método de remessa, é armazenada no carrinho e processada como parte da ordem. A única exceção são as informações de cartão de crédito. Essas informações são processadas diretamente usando o conector de pagamento Adyen. O pagamento é autorizado, mas não é cobrado.

## <a name="add-a-checkout-module-to-a-new-page-and-set-the-required-properties"></a>Adicionar um módulo de finalização da compra a uma nova página e definir as propriedades necessárias

Para adicionar um módulo de finalização da compra a uma nova página e definir as propriedades necessárias, siga estas etapas.

1. Vá para **Fragmento \> Novo Fragmento** e nomeie o novo fragmento como **Fragmento de finalização da compra**.
1. Adicione um módulo de finalização da compra ao fragmento.
1. Adicione um cabeçalho ao módulo de finalização da compra.
1. No slot **Informações de finalização da compra**, adicione módulos de endereço de remessa, opções de entrega, contêiner da seção de finalização da compra e informações de contato. Agora deve haver quatro seções no slot **Informações de finalização da compra**.
1. No módulo de contêiner de finalização da compra, adicione módulos de vale-presente, pontos de fidelidade e cartão de crédito. Dessa forma, verifique se todos os métodos de pagamento aparecem juntos em uma seção.
1. No slot **Resumo da ordem**, adicione módulos de resumo de ordem, colocação de ordem e bloco de conteúdo sofisticado.
1. No módulo de bloco de conteúdo sofisticado, adicione o seguinte texto: **Em caso de dúvidas sobre ordens, entre em contato com 1-800-FABRIKAM.**
1. No slot **Colocar ordem**, adicione um módulo de colocação de ordem.
1. Selecione **Salvar**. Alguns módulos podem não ser renderizados na visualização, porque não possuem um contexto de carrinho.
1. Verifique o fragmento e publique-o.
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

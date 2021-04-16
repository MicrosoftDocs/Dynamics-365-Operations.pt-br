---
title: Configurar o imposto para ordens online
description: Este tópico fornece uma visão geral da seleção do grupo de impostos para diferentes tipos de ordens online no Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: gmohanv
ms.search.validFrom: 2020-11-01
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 68b7e59a1e1ea18bdcd4e7a9117e4892407f40ff
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791838"
---
# <a name="configure-sales-tax-for-online-orders"></a>Configurar o imposto para ordens online

[!include [banner](includes/banner.md)]

Este tópico fornece uma visão geral da seleção do grupo de impostos para diferentes tipos de ordens online. 

Seu canal de comércio eletrônico pode oferecer suporte a opções como entrega ou retirada para ordens online. A aplicabilidade do imposto é baseada na opção selecionada por seus usuários online. Quando um cliente do site opta por comprar um item online e o envia para um endereço, o imposto é determinado com base na configuração do grupo de impostos do endereço de remessa do cliente. Quando um cliente opta por retirar um item comprado em uma loja, o imposto é determinado com base na configuração do grupo de impostos da loja. 

## <a name="orders-shipped-to-a-customer-address"></a>Ordens enviadas para o endereço de um cliente 

Em geral, os impostos para ordens online que enviam para endereços de clientes são definidos pelo destino. Cada grupo de imposto tem uma configuração de imposto com base no destino de varejo na qual sua empresa pode definir detalhes de destino, como região, estado e cidade de forma hierárquica. Quando uma ordem online é feita, o mecanismo de imposto do Commerce usa o endereço de entrega de cada item de linha na ordem e encontra grupos de impostos com critérios de imposto baseados no destino correspondentes. Por exemplo, em uma ordem online com um endereço de entrega de item de linha para São Francisco (Califórnia), o mecanismo de cálculo de impostos encontrará o grupo de impostos e o código do imposto para a Califórnia e calculará o imposto para cada item de linha apropriadamente.  

## <a name="customer-based-tax-groups"></a>Grupos de imposto baseados no cliente

Na sede do Comércio, existem dois locais onde os grupos de imposto do cliente são configurados:

- **Perfil do cliente**
- **Endereço de remessa do cliente**

### <a name="if-a-customers-profile-has-a-tax-group-configured"></a>Se o perfil de um cliente tiver um grupo de imposto configurado

O registro do perfil de um cliente na sede pode ter um grupo de imposto configurado; porém, para ordens online, o grupo de imposto configurado no perfil de um cliente não será usado pelo mecanismo de cálculo de impostos. 

### <a name="if-a-customers-shipping-address-has-a-tax-group-configured"></a>Se o endereço de remessa de um cliente tiver um grupo de imposto configurado

Se o registro de endereço de remessa de um cliente tiver um grupo de imposto configurado e uma ordem online (ou item de linha) for enviado ao endereço de remessa do cliente, o grupo de imposto configurado no registro de endereço do cliente será usado pelo mecanismo de cálculo de impostos.

#### <a name="configure-a-tax-group-for-a-customers-shipping-address-record"></a>Configurar um grupo de imposto para o registro do endereço de remessa de um cliente

Para configurar um grupo de impostos para o registro do endereço de remessa de um cliente na sede do Commerce, siga estas etapas:

1. Acesse **Todos os clientes** e selecione o cliente desejado. 
1. Na FastTab **Endereços**, selecione o endereço desejado e depois escolha **Mais opções \> Avançado**. 
1. Na guia **Geral** da página **Gerenciar endereços**, defina o valor do imposto conforme necessário.

> [!NOTE]
> O grupo de imposto é definido usando o endereço de entrega da linha de ordem e os impostos com base no destino são configurados no próprio grupo de imposto. Para obter mais informações, consulte [Configurar os impostos para as lojas online com base no destino](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).

## <a name="order-pickup-in-store"></a>Retirada de ordens na loja

Para linhas de ordem com retirada na loja ou retirada em frente à loja especificada, o grupo de imposto da loja de retirada selecionada será aplicado. Para obter detalhes sobre como configurar o grupo de imposto para determinada loja, consulte [Definir outras opções de imposto para lojas](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).

> [!NOTE]
> Quando uma linha de ordem é retirada em uma loja, as configurações de impostos do endereço do cliente (se configuradas) serão ignoradas pelo mecanismo de cálculo de impostos e a configuração de impostos da loja de coleta será aplicada. 

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de imposto](https://docs.microsoft.com/dynamics365/finance/general-ledger/indirect-taxes-overview?toc=/dynamics365/commerce/toc.json) 

[Métodos de cálculo de impostos no campo de Origem](https://docs.microsoft.com/dynamics365/finance/general-ledger/sales-tax-calculation-methods-origin-field?toc=/dynamics365/commerce/toc.json) 

[ Substituições e atribuições de impostos](https://docs.microsoft.com/dynamics365/supply-chain/procurement/tasks/sales-tax-assignment-overrides?toc=/dynamics365/commerce/toc.json) 

[Opções de cálculo do valor total e do intervalo para códigos de impostos](https://docs.microsoft.com/dynamics365/finance/general-ledger/whole-amount-interval-options-sales-tax-codes?toc=/dynamics365/commerce/toc.json) 

[Cálculo da isenção de imposto](tax-exempt-price-inclusive.md) 



[!INCLUDE[footer-include](../includes/footer-banner.md)]
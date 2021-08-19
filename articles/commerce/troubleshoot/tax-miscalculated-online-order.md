---
title: Os impostos sobre ordens online são calculados incorretamente
description: Este tópico fornece orientação de solução de problemas que pode ajudar quando os impostos sobre ordens online são calculados incorretamente ou quando o grupo de impostos na linha de venda não está corretamente definido.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: e51ae789dad2c7b5118be2cf8a88f4e4090a8c74c8259b4eaaddad1a134af80a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6715251"
---
# <a name="taxes-on-online-orders-are-incorrectly-calculated"></a>Os impostos sobre ordens online são calculados incorretamente

[!include [banner](../../includes/banner.md)]

Este tópico fornece orientação de solução de problemas que pode ajudar quando os impostos sobre ordens online são calculados incorretamente ou quando o grupo de impostos na linha de venda não está corretamente definido.

## <a name="description"></a>descrição

Quando uma ordem de comércio eletrônico é realizada, os impostos são calculados incorretamente ou o grupo de impostos na linha de venda é definido incorretamente.

## <a name="resolution"></a>Resolução

### <a name="configure-the-sales-tax-for-a-retail-store-in-commerce-headquarters"></a>Configurar o imposto de uma loja de varejo na matriz do Commerce

Para configurar o imposto de uma loja de varejo na matriz do Commerce, siga estas etapas.

1. Acesse **Varejo e Comércio \> Canais \> Todas as lojas**.
1. Selecione a loja para configurar o imposto.
1. Na guia rápida **Geral**, na seção **Imposto**, configure as informações sobre o imposto para a loja.

> [!NOTE]
> Para a retirada de produtos de uma loja, o grupo de impostos vem da loja selecionada para entrega. Para obter mais informações, consulte [Definir outras opções de imposto para lojas](/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).

### <a name="configure-the-sales-tax-for-a-customers-address-in-commerce-headquarters"></a>Configurar o imposto de um endereço do cliente na matriz do Commerce

Para configurar o imposto de um endereço do cliente na matriz do Commerce, siga estas etapas.

1. Ir para **Contas recebíveis \> Clientes \> Todos os clientes**.
1. Selecione o cliente para o qual os impostos devem ser configurados.
1. Na guia rápida **Endereços**, selecione o endereço para o qual deseja configurar impostos, selecione **Mais opções** e, em seguida, selecione **Avançado**.
1. Na guia rápida **Geral**, selecione o **Grupo de impostos**.
1. No campo **Imposto** selecione o valor apropriado.

> [!NOTE]
> Para remessa que envolve imposto no endereço do cliente, o endereço de entrega da linha determina o grupo de impostos para a linha. Se o cliente estiver enviando para um endereço existente que tenha um grupo de impostos já configurado, o grupo de impostos existente será usado. Por padrão, os endereços não têm um grupo de impostos quando são criados.

### <a name="configure-general-sales-tax-groups-in-commerce-headquarters"></a>Configurar grupos de impostos gerais na matriz do Commerce

Para configurar grupos de impostos gerais na matriz do Commerce, siga estas etapas:

1. Acesse **Imposto \> Impostos indiretos \> Imposto \> Grupo de impostos**.
1. Na navegação à esquerda, selecione o grupo de impostos a ser configurado.
1. Na guia rápida **Imposto baseado no destino de varejo**, configure os impostos para o grupo de impostos.

> [!NOTE]
> Para remessas que não envolvem impostos no endereço do cliente, o endereço de entrega da linha e os impostos baseados no destino que são configurados para o grupo de impostos determinam o grupo de impostos. Para obter mais informações, consulte [Configurar os impostos para as lojas online com base no destino](/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).

## <a name="additional-resources"></a>Recursos adicionais

[Configurar impostos para ordens online](../sales-tax-config.md)
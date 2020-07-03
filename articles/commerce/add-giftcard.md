---
title: Módulo do vale-presente
description: Este tópico abrange os módulos de cartão-presente e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: a8428963e105e422dcd048863c17df0926a409ac
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411103"
---
# <a name="gift-card-module"></a>Módulo do vale-presente

[!include [banner](includes/banner.md)]

Este tópico abrange os módulos de cartão-presente e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão Geral

Os cartões-presente são uma forma comum de pagamento, e o módulo de cartão-presente pode ser usado em um módulo de check-out para aceitar cartões-presente. O módulo de cartão-presente oferece suporte a cartões-presente Dynamics 365, SVS e Givex. Os cartões-presente SVS e Givex são resgatados por meio do provedor de pagamentos Adyen.

Para obter mais informações sobre suporte a cartões-presente externos, como SVS e Givex, consulte [Suporte a cartões-presente externos](./dev-itpro/gift-card.md)

A imagem a seguir mostra um exemplo de um módulo de cartão-presente em uma página de finalização de compra.

![Exemplo de um módulo de cartão-presente](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a>Propriedades do módulo

- **Mostrar campos adicionais**- Essa propriedade define quais campos devem ser exibidos para cartões-presente além do número do cartão-presente, que é sempre exibido por padrão. Por exemplo, alguns cartões-presente suportam a exibição de um PIN (número de identificação pessoal) e outros suportam a exibição de um PIN e uma data de validade. Como alternativa, essa propriedade pode ser definida como "Nenhum", que exibiria somente o número do cartão-presente e nenhum outro campo.

Valores com suporte:
-   PIN
-   Data de validade
-   PIN e data de vencimento 
-   Nemhum(a)

## <a name="site-settings-for-gift-card-modules"></a>Configurações do site para módulos de cartão-presente

No construtor de sites do Commerce em **Configurações de site \> Extensões**, há uma configuração de módulo de cartão-presente chamada **Tipo de cartão-presente compatível**. Esta configuração oferece suporte a três valores:
- **Cartão-presente do Dynamics 365** - Quando essa configuração é aplicada, o módulo do cartão-presente só permite o resgate dos cartões-presente do Dynamics 365. Essa configuração só tem suporte para usuários conectados no site de comércio eletrônico.
- **Cartões-presente SVS e Givex** - Quando essa configuração é aplicada, o módulo do cartão-presente só permite o resgate dos cartões-presente Givex e SVS. Essa configuração tem suporte para usuários conectados e anônimos no site de comércio eletrônico.
- **Cartões-presente Dynamics 365, SVS e Givex** - Quando essa configuração é aplicada, o módulo do cartão-presente só permite o resgate dos cartões-presente Dynamics 365, Givex e SVS. Essa configuração só tem suporte para usuários conectados no site de comércio eletrônico.

## <a name="add-a-gift-card-module-to-a-page"></a>Adicionar um módulo de cartão-presente a uma página

Para obter instruções sobre como adicionar um módulo de cartão-presente a uma página de check-in e definir as propriedades necessárias, consulte [Módulo de finalização](add-checkout-module.md).

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do kit de início](starter-kit-overview.md)

[Módulo de finalização da compra](add-checkout-module.md)

[Suporte a cartões-presente externos](./dev-itpro/gift-card.md)

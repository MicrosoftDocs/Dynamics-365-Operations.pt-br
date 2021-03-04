---
title: Módulo do vale-presente
description: Este tópico abrange os módulos de cartão-presente e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
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
ms.openlocfilehash: fa6b98bb41c0845cfa3ab36767f304ad70f46399
ms.sourcegitcommit: 12d271bb26c7490e7525d9b4bbf125cdc39fef43
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "4410353"
---
# <a name="gift-card-module"></a>Módulo do vale-presente

[!include [banner](includes/banner.md)]

Este tópico abrange os módulos de cartão-presente e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão Geral

Os módulos de cartão-presente podem ser usados em módulos de finalização de compra para aceitar cartões-presente, uma forma comum de pagamento usada para transações de comércio eletrônico. O módulo de cartão-presente oferece suporte a cartões-presente Dynamics 365, SVS e Givex. Os cartões-presente SVS e Givex são resgatados por meio do provedor de pagamentos Adyen. Para obter mais informações sobre suporte a cartões-presente externos, como SVS e Givex, consulte [Suporte a cartões-presente externos](./dev-itpro/gift-card.md).

> [!NOTE]
> O suporte para o resgate de vales-presentes SVS e Givex durante o fluxo de finalização de compra está disponível na versão 10.0.11 do Dynamics 365 Commerce. 

Há dois módulos de cartão-presente disponíveis:

- **Cartão-presente** - Este módulo pode ser usado em uma página de finalização de compra para resgatar um cartão-presente como meio de pagamento. 
- **Verificação de saldo do cartão-presente** - Este módulo pode ser usado em qualquer página para verificar o saldo de um cartão-presente. Este módulo está disponível nas versões 10.0.14 e posterior do Commerce.

> [!NOTE]
> O suporte para o módulo de verificação de saldo de vale-presente está disponível na versão do 10.0.14 do Dynamics 365 Commerce.

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

> [!IMPORTANT]
> Essas configurações estão disponíveis na versão 10.0.11 do Dynamics 365 Commerce e são necessárias somente se você precisar de suporte para vales-presente SVS ou Givex. Se estiver atualizando de uma versão mais antiga do Dynamics 365 Commerce, você deverá atualizar manualmente o arquivo appsettings.json. Para obter instruções sobre como atualizar o arquivo appsettings.json, consulte [SDK e atualizações da biblioteca de módulos](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file). 

## <a name="add-a-gift-card-module-to-a-page"></a>Adicionar um módulo de cartão-presente a uma página

Para obter instruções sobre como adicionar um módulo de cartão-presente a uma página de check-in e definir as propriedades necessárias, consulte [Módulo de finalização](add-checkout-module.md).

## <a name="additional-resources"></a>Recursos adicionais

[Módulo de carrinho](add-cart-module.md)

[Módulo de ícone de carrinho](cart-icon-module.md)

[Módulo de finalização da compra](add-checkout-module.md)

[Módulo de pagamento](payment-module.md)

[Módulo de endereço de remessa](ship-address-module.md)

[Módulo de opções de entrega](delivery-options-module.md)

[Módulo de informações sobre retirada](pickup-info-module.md)

[Módulo de detalhes da ordem](order-confirmation-module.md)

[Suporte a cartões-presente externos](./dev-itpro/gift-card.md)

[SDK e atualizações da biblioteca de módulos](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
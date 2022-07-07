---
title: Ocultar informações de divisão de imposto em resumos de ordens
description: Este artigo descreve como ocultar informações de separação de impostos em resumos de ordens em páginas de carrinho, finalização de compra, confirmação de ordem e detalhes da ordem no Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 05/17/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-03-28
ms.openlocfilehash: 669534a6611860ac73439460afedce341310cc7d
ms.sourcegitcommit: 6616b969afd6beb11a79d8e740560bf00016ea7f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2022
ms.locfileid: "9027326"
---
# <a name="hide-tax-breakup-information-in-order-summaries"></a>Ocultar informações de divisão de imposto em resumos de ordens

[!include [banner](includes/banner.md)]

Este artigo descreve como ocultar informações de separação de impostos em resumos de ordens em páginas de carrinho, finalização de compra, confirmação de ordem e detalhes da ordem no Microsoft Dynamics 365 Commerce.

Por padrão, o Dynamics 365 Commerce mostra informações de separação de impostos em resumos de ordens em páginas de carrinho, finalização de compra, confirmação de ordem e detalhes da ordem. A partir do Commerce versão 10.0.27, o criador de sites do Commerce inclui uma opção que permite ocultar as informações de separação de impostos nos resumos de ordens.

A ilustração a seguir mostra um exemplo de dois resumos de ordens. O primeiro mostra as informações de separação de impostos, e o segundo as oculta.

![Exemplos de carrinhos em que as informações de separação de impostos são exibidas e ocultas.](media/prices-include-sales-tax-e-Commerce.png)

> [!NOTE]
> - A opção de ocultar informações de separação de impostos em resumos de ordens está disponível somente quando a opção **Os preços incluem o imposto** para o canal de comércio eletrônico está definida como **Sim** no Commerce headquarters, em **Varejo e Comércio \> Canais \> Lojas \> Todas as Lojas**. 
> - Por padrão, a opção **Mostrar separação de impostos no resumo da ordem** está habilitada no criador de sites.

## <a name="hide-tax-breakup-information-in-order-summaries"></a>Ocultar informações de separação de impostos em resumos de ordens

Para ocultar informações de separação de impostos em resumos de ordens, siga estas etapas.

1. No criador de sites do Commerce, vá para o site que deseja atualizar.
1. Acesse **Configurações do site \> Extensões**.
1. Desmarque a caixa de seleção **Mostrar separação de impostos no resumo da ordem**.

Para mostrar informações de separação de impostos nos resumos de ordens, marque a caixa de seleção **Mostrar separação de impostos no resumo da ordem**.  

A ilustração a seguir mostra a caixa de seleção **Mostrar separação de impostos no resumo da ordem** destacada e selecionada no criador de sites.

![A opção Mostrar separação de impostos no resumo da ordem no criador de sites.](media/prices-include-sales-tax-e-Commerce-site-settings.png)

> [!NOTE]
> Se você personalizou os módulos de resumo de ordem e não deseja herdar a funcionalidade "ocultar as informações de separação de impostos em resumos de ordens" no Commerce versão 10.0.27 ou posterior, consulte [O subtotal do resumo de ordem não inclui impostos sobre encargos ao usar módulos de resumo de ordem personalizados](troubleshoot/summary-taxes-custom-modules-10.0.27.md#resolution).

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de imposto](/finance/general-ledger/indirect-taxes-overview)

[Configurar impostos para ordens online](sales-tax-config.md)

[Solução de problemas: Os impostos sobre ordens online são calculados incorretamente](troubleshoot/tax-miscalculated-online-order.md)

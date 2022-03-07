---
title: Habilitar pagamentos de clientes e descontos à vista
description: Este tópico explica como habilitar o recálculo dos descontos à vista.
author: kfend
ms.date: 10/16/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 270254
ms.assetid: 92223189-69a8-4a40-b867-ef9b4f14c23d
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2019-10-07
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f29acb1920b1988f3d66aca9f80c9382ad19754d39514f7d6c73fae97b39953a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6722654"
---
# <a name="enable-customer-payments-and-cash-discounts"></a>Habilitar pagamentos de clientes e descontos à vista

[!include [banner](../includes/banner.md)]

Ao criar um diário de pagamentos do cliente em uma entidade legal configurada para o Brasil, e os descontos à vista são aplicáveis na data do pagamento, se você alterar a data do pagamento no diário de pagamentos para uma data em que os descontos não sejam mais aplicáveis, o diário de pagamentos atualmente continua a calcular descontos à vista. Ele não remove os descontos à vista do valor de liquidação.

O recurso "Corrigindo o cálculo do valor de desconto quando a data de pagamento for alterada" altera o algoritmo para o cálculo dos descontos à vista, para que os descontos sejam dados no intervalo correto das datas, de acordo com a configuração do método de pagamento. Quando você ativa esse recurso, o diário de pagamentos do cliente recalcula o valor da liquidação e remove os descontos à vista se a data do pagamento mudar e ficar desatualizada. Para usar esse recurso, Acesse **Feature management**, localize o recurso **Corrigindo o cálculo do valor de desconto quando a data de pagamento for alterada** na lista e ative-o.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
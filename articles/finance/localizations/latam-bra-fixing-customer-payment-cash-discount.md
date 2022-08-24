---
title: Habilitar pagamentos de clientes e descontos à vista
description: Este artigo explica como habilitar o recálculo dos descontos à vista.
author: kfend
ms.date: 10/16/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Brazil
ms.author: atrukawk
ms.search.validFrom: 2019-10-07
ms.dyn365.ops.version: 10.0.5
ms.custom: 270254
ms.assetid: 92223189-69a8-4a40-b867-ef9b4f14c23d
ms.search.form: ''
ms.openlocfilehash: 76454e9b92889a3e6db33cfeb45f68f7755ce0ce
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280649"
---
# <a name="enable-customer-payments-and-cash-discounts"></a>Habilitar pagamentos de clientes e descontos à vista

[!include [banner](../includes/banner.md)]

Ao criar um diário de pagamentos do cliente em uma entidade legal configurada para o Brasil, e os descontos à vista são aplicáveis na data do pagamento, se você alterar a data do pagamento no diário de pagamentos para uma data em que os descontos não sejam mais aplicáveis, o diário de pagamentos atualmente continua a calcular descontos à vista. Ele não remove os descontos à vista do valor de liquidação.

O recurso "Corrigindo o cálculo do valor de desconto quando a data de pagamento for alterada" altera o algoritmo para o cálculo dos descontos à vista, para que os descontos sejam dados no intervalo correto das datas, de acordo com a configuração do método de pagamento. Quando você ativa esse recurso, o diário de pagamentos do cliente recalcula o valor da liquidação e remove os descontos à vista se a data do pagamento mudar e ficar desatualizada. Para usar esse recurso, Acesse **Feature management**, localize o recurso **Corrigindo o cálculo do valor de desconto quando a data de pagamento for alterada** na lista e ative-o.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

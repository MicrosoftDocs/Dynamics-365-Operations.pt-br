---
title: Habilitar pagamentos de clientes e descontos à vista
description: Este tópico explica como habilitar o recálculo dos descontos à vista.
author: kfend
manager: AnnBe
ms.date: 10/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 270254
ms.assetid: 92223189-69a8-4a40-b867-ef9b4f14c23d
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2019-10-07
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e192b4829511bdecdb34d4315bce5710957f8ef2
ms.sourcegitcommit: 9f65743d7fac2faea5b36a225be15b2783509182
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2019
ms.locfileid: "2651480"
---
# <a name="enable-customer-payments-and-cash-discounts"></a><span data-ttu-id="a7536-103">Habilitar pagamentos de clientes e descontos à vista</span><span class="sxs-lookup"><span data-stu-id="a7536-103">Enable customer payments and cash discounts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a7536-104">Ao criar um diário de pagamentos do cliente em uma entidade legal configurada para o Brasil, e os descontos à vista são aplicáveis na data do pagamento, se você alterar a data do pagamento no diário de pagamentos para uma data em que os descontos não sejam mais aplicáveis, o diário de pagamentos atualmente continua a calcular descontos à vista.</span><span class="sxs-lookup"><span data-stu-id="a7536-104">When you create a Customer payment journal in a legal entity that is configured for Brazil, and cash discounts are applicable on the payment date, if you change the payment date in the payment journal to a date when discounts are no longer applicable, the payment journal currently continues to calculate cash discounts.</span></span> <span data-ttu-id="a7536-105">Ele não remove os descontos à vista do valor de liquidação.</span><span class="sxs-lookup"><span data-stu-id="a7536-105">It doesn't remove the cash discounts from the settlement amount.</span></span>

<span data-ttu-id="a7536-106">O recurso "Corrigindo o cálculo do valor de desconto quando a data de pagamento for alterada" altera o algoritmo para o cálculo dos descontos à vista, para que os descontos sejam dados no intervalo correto das datas, de acordo com a configuração do método de pagamento.</span><span class="sxs-lookup"><span data-stu-id="a7536-106">The "Fixing the calculation of discount amount when the payment date changes" feature changes the algorithm for calculating cash discounts, so that cash discounts are given in the correct range of the dates, according to the setup of the payment method.</span></span> <span data-ttu-id="a7536-107">Quando você ativa esse recurso, o diário de pagamentos do cliente recalcula o valor da liquidação e remove os descontos à vista se a data do pagamento mudar e ficar desatualizada.</span><span class="sxs-lookup"><span data-stu-id="a7536-107">When you turn on this feature, the Customer payment journal recalculates the settlement amount and removes cash discounts if the payment date changes and becomes out of date.</span></span> <span data-ttu-id="a7536-108">Para usar esse recurso, vá para **Feature management**, localize o recurso **Corrigindo o cálculo do valor de desconto quando a data de pagamento for alterada** na lista e ative-o.</span><span class="sxs-lookup"><span data-stu-id="a7536-108">To use this feature, go to **Feature management**, find the **Fixing the calculation of discount amount when the payment date changes** feature in the list, and turn it on.</span></span>

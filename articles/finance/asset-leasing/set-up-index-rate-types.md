---
title: Configurar taxas indexadas
description: Este tópico explica como configurar taxas indexadas. As taxas indexadas são necessárias se a sua organização associa os valores de pagamento de arrendamento a um conjunto de taxas indexadas.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseIndexRateType
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 40f230a9d69a142b18eb27a2d5e420dbadc600d2
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5880951"
---
# <a name="set-up-index-rates"></a><span data-ttu-id="064e2-104">Configurar taxas indexadas</span><span class="sxs-lookup"><span data-stu-id="064e2-104">Set up index rates</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="064e2-105">Se os pagamentos de arrendamento dependerem de um índice, os tipos de taxa indexada poderão ser adicionados e mantidos no sistema.</span><span class="sxs-lookup"><span data-stu-id="064e2-105">If lease payments depend on an index, the index rate types can be added and maintained in the system.</span></span> <span data-ttu-id="064e2-106">Para reavaliar os pagamentos de arrendamento da página **Tipo de taxa indexada**, o processo de reavaliação de taxa indexada usa a taxa indexada mais recente a partir da data de reavaliação.</span><span class="sxs-lookup"><span data-stu-id="064e2-106">To revalue the lease payments from the **Index rate type** page, the index rate revaluation process uses the most recent index rate from the date of revaluation.</span></span>

<span data-ttu-id="064e2-107">Para adicionar tipos de taxa indexada e taxas indexada, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="064e2-107">To add index rate types and index rates, follow these steps.</span></span>

1. <span data-ttu-id="064e2-108">Vá para **Arrendamento de ativo \> Configuração \> Tipo de taxa indexada**.</span><span class="sxs-lookup"><span data-stu-id="064e2-108">Go to **Asset leasing \> Setup \> Index rate type**.</span></span>
2. <span data-ttu-id="064e2-109">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="064e2-109">Select **New**.</span></span>
3. <span data-ttu-id="064e2-110">Nos campos apropriados, insira o tipo de taxa e o nome da taxa indexada.</span><span class="sxs-lookup"><span data-stu-id="064e2-110">In the appropriate fields, enter the rate type and the name of the index rate.</span></span>
4. <span data-ttu-id="064e2-111">Para adicionar um novo valor de taxa indexada, selecione o tipo de taxa indexada e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="064e2-111">To add a new index rate value, select the index rate type, and then select **Add**.</span></span>
5. <span data-ttu-id="064e2-112">Selecione a data de início efetiva da taxa e selecione o valor da taxa.</span><span class="sxs-lookup"><span data-stu-id="064e2-112">Select the effective start date of the rate, and select the rate value.</span></span>

<span data-ttu-id="064e2-113">Você deve selecionar **Diferença de valor de taxa indexada** ou **Valor de taxa indexada** como o método de taxa indexada.</span><span class="sxs-lookup"><span data-stu-id="064e2-113">You must select either **Index rate value difference** or **Index rate value** as the index rate method.</span></span>

- <span data-ttu-id="064e2-114">Selecione o método **Diferença de valor de taxa indexada** para calcular um novo pagamento de arrendamento, com base na diferença entre a taxa indexada na data de início e a taxa indexada mais recente.</span><span class="sxs-lookup"><span data-stu-id="064e2-114">Select the **Index rate value difference** method to calculate a new lease payment, based on the difference between the index rate on the start date and the most recent index rate.</span></span> <span data-ttu-id="064e2-115">A taxa indexada é definida no campo **Taxa indexada (%)**.</span><span class="sxs-lookup"><span data-stu-id="064e2-115">The index rate is defined in the **Index rate (%)** field.</span></span>
- <span data-ttu-id="064e2-116">Selecione o método **Valor de taxa indexada** para calcular o pagamento do arrendamento usando a porcentagem especificada no campo **Taxa indexada (%)**.</span><span class="sxs-lookup"><span data-stu-id="064e2-116">Select the **Index rate value** method to calculate the lease payment by using the percentage that is specified in the **Index rate (%)** field.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

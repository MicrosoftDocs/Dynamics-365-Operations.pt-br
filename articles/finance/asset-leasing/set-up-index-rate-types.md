---
title: Configurar taxas indexadas
description: Este tópico explica como configurar taxas indexadas. As taxas indexadas são necessárias se a sua organização associa os valores de pagamento de arrendamento a um conjunto de taxas indexadas.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: f362bf4a6b5de3ce16330aea08880b07b4145792
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992855"
---
# <a name="set-up-index-rates"></a><span data-ttu-id="2d8cb-104">Configurar taxas indexadas</span><span class="sxs-lookup"><span data-stu-id="2d8cb-104">Set up index rates</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2d8cb-105">Se os pagamentos de arrendamento dependerem de um índice, os tipos de taxa indexada poderão ser adicionados e mantidos no sistema.</span><span class="sxs-lookup"><span data-stu-id="2d8cb-105">If lease payments depend on an index, the index rate types can be added and maintained in the system.</span></span> <span data-ttu-id="2d8cb-106">Para reavaliar os pagamentos de arrendamento da página **Tipo de taxa indexada**, o processo de reavaliação de taxa indexada usa a taxa indexada mais recente a partir da data de reavaliação.</span><span class="sxs-lookup"><span data-stu-id="2d8cb-106">To revalue the lease payments from the **Index rate type** page, the index rate revaluation process uses the most recent index rate from the date of revaluation.</span></span>

<span data-ttu-id="2d8cb-107">Para adicionar tipos de taxa indexada e taxas indexada, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="2d8cb-107">To add index rate types and index rates, follow these steps.</span></span>

1. <span data-ttu-id="2d8cb-108">Vá para **Arrendamento de ativo \> Configuração \> Tipo de taxa indexada**.</span><span class="sxs-lookup"><span data-stu-id="2d8cb-108">Go to **Asset leasing \> Setup \> Index rate type**.</span></span>
2. <span data-ttu-id="2d8cb-109">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="2d8cb-109">Select **New**.</span></span>
3. <span data-ttu-id="2d8cb-110">Nos campos apropriados, insira o tipo de taxa e o nome da taxa indexada.</span><span class="sxs-lookup"><span data-stu-id="2d8cb-110">In the appropriate fields, enter the rate type and the name of the index rate.</span></span>
4. <span data-ttu-id="2d8cb-111">Para adicionar um novo valor de taxa indexada, selecione o tipo de taxa indexada e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2d8cb-111">To add a new index rate value, select the index rate type, and then select **Add**.</span></span>
5. <span data-ttu-id="2d8cb-112">Selecione a data de início efetiva da taxa e selecione o valor da taxa.</span><span class="sxs-lookup"><span data-stu-id="2d8cb-112">Select the effective start date of the rate, and select the rate value.</span></span>

<span data-ttu-id="2d8cb-113">Você deve selecionar **Diferença de valor de taxa indexada** ou **Valor de taxa indexada** como o método de taxa indexada.</span><span class="sxs-lookup"><span data-stu-id="2d8cb-113">You must select either **Index rate value difference** or **Index rate value** as the index rate method.</span></span>

- <span data-ttu-id="2d8cb-114">Selecione o método **Diferença de valor de taxa indexada** para calcular um novo pagamento de arrendamento, com base na diferença entre a taxa indexada na data de início e a taxa indexada mais recente.</span><span class="sxs-lookup"><span data-stu-id="2d8cb-114">Select the **Index rate value difference** method to calculate a new lease payment, based on the difference between the index rate on the start date and the most recent index rate.</span></span> <span data-ttu-id="2d8cb-115">A taxa indexada é definida no campo **Taxa indexada (%)**.</span><span class="sxs-lookup"><span data-stu-id="2d8cb-115">The index rate is defined in the **Index rate (%)** field.</span></span>
- <span data-ttu-id="2d8cb-116">Selecione o método **Valor de taxa indexada** para calcular o pagamento do arrendamento usando a porcentagem especificada no campo **Taxa indexada (%)**.</span><span class="sxs-lookup"><span data-stu-id="2d8cb-116">Select the **Index rate value** method to calculate the lease payment by using the percentage that is specified in the **Index rate (%)** field.</span></span>

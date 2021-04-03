---
title: Módulo de informações sobre retirada
description: Este tópico aborda o módulo de informações sobre retirada e descreve como adicioná-lo às páginas de finalização de compra no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 11/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-09021
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 222e8ad79b30e5197f7140958309d442b284f286
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263171"
---
# <a name="pickup-information-module"></a><span data-ttu-id="096c5-103">Módulo de informações de retirada</span><span class="sxs-lookup"><span data-stu-id="096c5-103">Pickup information module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="096c5-104">Este tópico aborda o módulo de informações sobre retirada e descreve como adicioná-lo às páginas de finalização de compra no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="096c5-104">This topic covers the pickup information module and describes how to add it to checkout pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="096c5-105">O módulo de informações sobre retirada pode ser usado em um módulo de finalização de compra para mostrar informações sobre retirada de ordens.</span><span class="sxs-lookup"><span data-stu-id="096c5-105">The pickup information module can be used in a checkout module to show order pickup information.</span></span> <span data-ttu-id="096c5-106">Os clientes podem ver as datas de retirada e os intervalos de tempo disponíveis e, em seguida, selecionar um horário adequado para retirar a ordem.</span><span class="sxs-lookup"><span data-stu-id="096c5-106">Customers can view available pickup dates and time slots, and then select a suitable time to pick up their order.</span></span> <span data-ttu-id="096c5-107">Por exemplo, um cliente pode optar por retirar uma ordem às 15h em 21 de março na loja de São Francisco.</span><span class="sxs-lookup"><span data-stu-id="096c5-107">For example, a customer can choose to pick up an order at 3 PM on March 21 from the San Francisco store.</span></span>

<span data-ttu-id="096c5-108">Os intervalos de tempo de retirada para as lojas apropriadas devem ser configurados na sede do Commerce.</span><span class="sxs-lookup"><span data-stu-id="096c5-108">Pickup time slots for the appropriate stores must be configured in Commerce headquarters.</span></span> <span data-ttu-id="096c5-109">Para obter mais informações, consulte [Criar e atualizar os intervalos de tempo para retirada pelo cliente](dev-itpro/pickup-timeslots.md).</span><span class="sxs-lookup"><span data-stu-id="096c5-109">For more information, see [Create and update time slots for customer pickup](dev-itpro/pickup-timeslots.md).</span></span>

<span data-ttu-id="096c5-110">Se um módulo de informações sobre retirada for criado em uma página de finalização de compra, mas nenhum intervalo de tempo for definido para a loja selecionada para retirada, o módulo mostrará informações, mas o usuário não poderá selecionar nenhum intervalo de tempo.</span><span class="sxs-lookup"><span data-stu-id="096c5-110">If a pickup information module is created on a checkout page, but no time slots are defined for the store that is selected for pickup, the module will show information, but the user won't be able to select any time slots.</span></span> <span data-ttu-id="096c5-111">Os intervalos de tempo são opcionais e não são necessários para realizar uma ordem.</span><span class="sxs-lookup"><span data-stu-id="096c5-111">Time slots are optional and aren't required to place an order.</span></span>

<span data-ttu-id="096c5-112">Se vários itens forem selecionados para retirada em várias lojas, o módulo de informações sobre retirada permitirá que o usuário selecione um intervalo de tempo para cada loja, desde que os intervalos de tempo estejam disponíveis nela.</span><span class="sxs-lookup"><span data-stu-id="096c5-112">If multiple items are selected for pickup across multiple stores, the pickup information module will let the user select a time slot for each store, provided that time slots are available for it.</span></span>

> [!NOTE]
> <span data-ttu-id="096c5-113">O suporte para os intervalos de tempo e o módulo de informações sobre retirada de finalização de compra está disponível no Dynamics 365 Commerce versão 10.0.15 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="096c5-113">Support for time slots and the checkout pickup information module is available in Dynamics 365 Commerce version 10.0.15 and later.</span></span>

<span data-ttu-id="096c5-114">A ilustração a seguir mostra um exemplo de seleção de intervalo de tempo por meio do módulo de informações sobre retirada em uma página de finalização de compra.</span><span class="sxs-lookup"><span data-stu-id="096c5-114">The following illustration shows an example of time slot selection through the pickup information module on a checkout page.</span></span>

![Exemplo de um módulo de informações sobre retirada em uma página de finalização de compra](./dev-itpro/media/Curbside_timeslot_eCommerce.PNG)

## <a name="module-properties"></a><span data-ttu-id="096c5-116">Propriedades do módulo</span><span class="sxs-lookup"><span data-stu-id="096c5-116">Module properties</span></span>

- <span data-ttu-id="096c5-117">**Título** – Insira um título para o módulo.</span><span class="sxs-lookup"><span data-stu-id="096c5-117">**Heading** – Enter a heading for the module.</span></span>

## <a name="show-time-slot-information-after-an-order-is-placed"></a><span data-ttu-id="096c5-118">Mostrar informações do intervalo de tempo após uma ordem ser realizada</span><span class="sxs-lookup"><span data-stu-id="096c5-118">Show time slot information after an order is placed</span></span>

<span data-ttu-id="096c5-119">Após uma ordem ser realizada, as informações sobre o intervalo de tempo selecionado poderão ser exibidas no [módulo de confirmação da ordem](order-confirmation-module.md) e no [módulo de detalhes da ordem](account-management.md#order-details-page).</span><span class="sxs-lookup"><span data-stu-id="096c5-119">After an order is placed, information about the selected time slot can be viewed in the [order confirmation module](order-confirmation-module.md) and the [order details module](account-management.md#order-details-page).</span></span> <span data-ttu-id="096c5-120">Esses dois módulos têm uma propriedade **Mostrar informações do intervalo de tempo**.</span><span class="sxs-lookup"><span data-stu-id="096c5-120">Both these modules have a **Show timeslot information** property.</span></span> <span data-ttu-id="096c5-121">Para que eles possam mostrar o intervalo de tempo selecionado durante o processo da ordem, essa propriedade deve ser definida como **Verdadeiro**.</span><span class="sxs-lookup"><span data-stu-id="096c5-121">Before they can show the selected time slot during the order process, this property must be set to **True**.</span></span>

## <a name="add-a-checkout-pickup-information-module-to-a-page"></a><span data-ttu-id="096c5-122">Adicionar um módulo de informações sobre retirada de finalização de compra a uma página</span><span class="sxs-lookup"><span data-stu-id="096c5-122">Add a checkout pickup information module to a page</span></span>

<span data-ttu-id="096c5-123">Para obter instruções sobre como adicionar um módulo de informações sobre retirada a uma página de finalização de compra e definir as propriedades necessárias, consulte [Módulo de finalização de compra](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="096c5-123">For instructions about how to add a pickup information module to a checkout page and set the required properties, see [Checkout module](add-checkout-module.md).</span></span>

<span data-ttu-id="096c5-124">A ilustração a seguir mostra um exemplo de uma página de finalização de compra no comércio eletrônico que inclui intervalos de tempo para itens da linha de retirada.</span><span class="sxs-lookup"><span data-stu-id="096c5-124">The following illustration shows an example of an e-Commerce checkout page that includes time slots for pickup line items.</span></span>

![Exemplo de uma página de finalização de compra no comércio eletrônico que inclui intervalos de tempo para itens da linha de retirada](./dev-itpro/media/Curbside_timeslot_eCommerce_checkoutsummary.PNG)

## <a name="additional-resources"></a><span data-ttu-id="096c5-126">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="096c5-126">Additional resources</span></span>

[<span data-ttu-id="096c5-127">Criar e atualizar os intervalos de tempo para retirada pelo cliente</span><span class="sxs-lookup"><span data-stu-id="096c5-127">Create and update time slots for customer pickup</span></span>](dev-itpro/pickup-timeslots.md)

[<span data-ttu-id="096c5-128">Módulo de finalização da compra</span><span class="sxs-lookup"><span data-stu-id="096c5-128">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="096c5-129">Módulo de confirmação da ordem</span><span class="sxs-lookup"><span data-stu-id="096c5-129">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="096c5-130">Módulo de detalhes da ordem</span><span class="sxs-lookup"><span data-stu-id="096c5-130">Order details module</span></span>](account-management.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
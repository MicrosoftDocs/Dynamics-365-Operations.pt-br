---
title: Os impostos sobre ordens online são calculados incorretamente
description: Este tópico fornece orientação de solução de problemas que pode ajudar quando os impostos sobre ordens online são calculados incorretamente ou quando o grupo de impostos na linha de venda não está corretamente definido.
author: Reza-Assadi
manager: AnnBe
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
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
ms.openlocfilehash: 421df7545e285950ef8a3c4b753c8c6dc5f26422
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585191"
---
# <a name="taxes-on-online-orders-are-incorrectly-calculated"></a><span data-ttu-id="169fe-103">Os impostos sobre ordens online são calculados incorretamente</span><span class="sxs-lookup"><span data-stu-id="169fe-103">Taxes on online orders are incorrectly calculated</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="169fe-104">Este tópico fornece orientação de solução de problemas que pode ajudar quando os impostos sobre ordens online são calculados incorretamente ou quando o grupo de impostos na linha de venda não está corretamente definido.</span><span class="sxs-lookup"><span data-stu-id="169fe-104">This topic provides troubleshooting guidance that can help when taxes on online orders are incorrectly calculated, or when the tax group on the sales line isn't correctly set.</span></span>

## <a name="description"></a><span data-ttu-id="169fe-105">descrição</span><span class="sxs-lookup"><span data-stu-id="169fe-105">Description</span></span>

<span data-ttu-id="169fe-106">Quando uma ordem de comércio eletrônico é realizada, os impostos são calculados incorretamente ou o grupo de impostos na linha de venda é definido incorretamente.</span><span class="sxs-lookup"><span data-stu-id="169fe-106">When an e-commerce order is placed, the taxes are incorrectly calculated, or the tax group on the sales line is incorrectly set.</span></span>

## <a name="resolution"></a><span data-ttu-id="169fe-107">Resolução</span><span class="sxs-lookup"><span data-stu-id="169fe-107">Resolution</span></span>

### <a name="configure-the-sales-tax-for-a-retail-store-in-commerce-headquarters"></a><span data-ttu-id="169fe-108">Configurar o imposto de uma loja de varejo na matriz do Commerce</span><span class="sxs-lookup"><span data-stu-id="169fe-108">Configure the sales tax for a retail store in Commerce headquarters</span></span>

<span data-ttu-id="169fe-109">Para configurar o imposto de uma loja de varejo na matriz do Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="169fe-109">To configure the sales tax for a retail store in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="169fe-110">Vá para **Varejo e Comércio \> Canais \> Todas as lojas**.</span><span class="sxs-lookup"><span data-stu-id="169fe-110">Go to **Retail and Commerce \> Channels \> All stores**.</span></span>
1. <span data-ttu-id="169fe-111">Selecione a loja para configurar o imposto.</span><span class="sxs-lookup"><span data-stu-id="169fe-111">Select the store to configure sales tax for.</span></span>
1. <span data-ttu-id="169fe-112">Na guia rápida **Geral**, na seção **Imposto**, configure as informações sobre o imposto para a loja.</span><span class="sxs-lookup"><span data-stu-id="169fe-112">On the **General** FastTab, in the **Sales tax** section, configure the sales tax information for the store.</span></span>

> [!NOTE]
> <span data-ttu-id="169fe-113">Para a retirada de produtos de uma loja, o grupo de impostos vem da loja selecionada para entrega.</span><span class="sxs-lookup"><span data-stu-id="169fe-113">For product pickup from a store, the tax group comes from the store that is selected for pickup.</span></span> <span data-ttu-id="169fe-114">Para obter mais informações, consulte [Definir outras opções de imposto para lojas](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).</span><span class="sxs-lookup"><span data-stu-id="169fe-114">For more information, see [Set other tax options for stores](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).</span></span>

### <a name="configure-the-sales-tax-for-a-customers-address-in-commerce-headquarters"></a><span data-ttu-id="169fe-115">Configurar o imposto de um endereço do cliente na matriz do Commerce</span><span class="sxs-lookup"><span data-stu-id="169fe-115">Configure the sales tax for a customer's address in Commerce headquarters</span></span>

<span data-ttu-id="169fe-116">Para configurar o imposto de um endereço do cliente na matriz do Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="169fe-116">To configure the sales tax for a customer's address in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="169fe-117">Ir para **Contas recebíveis \> Clientes \> Todos os clientes**.</span><span class="sxs-lookup"><span data-stu-id="169fe-117">Go to **Accounts receivable \> Customers \> All customers**.</span></span>
1. <span data-ttu-id="169fe-118">Selecione o cliente para o qual os impostos devem ser configurados.</span><span class="sxs-lookup"><span data-stu-id="169fe-118">Select the customer to configure sales taxes for.</span></span>
1. <span data-ttu-id="169fe-119">Na guia rápida **Endereços**, selecione o endereço para o qual deseja configurar impostos, selecione **Mais opções** e, em seguida, selecione **Avançado**.</span><span class="sxs-lookup"><span data-stu-id="169fe-119">On the **Addresses** FastTab, select the address to configure sales taxes for, select **More options**, and then select **Advanced**.</span></span>
1. <span data-ttu-id="169fe-120">Na guia rápida **Geral**, selecione o **Grupo de impostos**.</span><span class="sxs-lookup"><span data-stu-id="169fe-120">On the **General** FastTab, select the **Tax group**.</span></span>
1. <span data-ttu-id="169fe-121">No campo **Imposto** selecione o valor apropriado.</span><span class="sxs-lookup"><span data-stu-id="169fe-121">In the **Sales tax** field, select the appropriate value.</span></span>

> [!NOTE]
> <span data-ttu-id="169fe-122">Para remessa que envolve imposto no endereço do cliente, o endereço de entrega da linha determina o grupo de impostos para a linha.</span><span class="sxs-lookup"><span data-stu-id="169fe-122">For shipping that involves sales tax on the customer's address, the delivery address of the line determines the tax group for the line.</span></span> <span data-ttu-id="169fe-123">Se o cliente estiver enviando para um endereço existente que tenha um grupo de impostos já configurado, o grupo de impostos existente será usado.</span><span class="sxs-lookup"><span data-stu-id="169fe-123">If the customer is shipping to an existing address that has a tax group that is already configured, the existing tax group will be used.</span></span> <span data-ttu-id="169fe-124">Por padrão, os endereços não têm um grupo de impostos quando são criados.</span><span class="sxs-lookup"><span data-stu-id="169fe-124">By default, addresses don't have a tax group when they are created.</span></span>

### <a name="configure-general-sales-tax-groups-in-commerce-headquarters"></a><span data-ttu-id="169fe-125">Configurar grupos de impostos gerais na matriz do Commerce</span><span class="sxs-lookup"><span data-stu-id="169fe-125">Configure general sales tax groups in Commerce headquarters</span></span>

<span data-ttu-id="169fe-126">Para configurar grupos de impostos gerais na matriz do Commerce, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="169fe-126">To configure general sales tax groups in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="169fe-127">Vá para **Imposto \> Impostos indiretos \> Imposto \> Grupo de impostos**.</span><span class="sxs-lookup"><span data-stu-id="169fe-127">Go to **Tax \> Indirect taxes \> Sales tax \> Sales tax group**.</span></span>
1. <span data-ttu-id="169fe-128">Na navegação à esquerda, selecione o grupo de impostos a ser configurado.</span><span class="sxs-lookup"><span data-stu-id="169fe-128">In the left navigation, select the tax group to configure.</span></span>
1. <span data-ttu-id="169fe-129">Na guia rápida **Imposto baseado no destino de varejo**, configure os impostos para o grupo de impostos.</span><span class="sxs-lookup"><span data-stu-id="169fe-129">On the **Retail destination based tax** FastTab, configure the taxes for the sales tax group.</span></span>

> [!NOTE]
> <span data-ttu-id="169fe-130">Para remessas que não envolvem impostos no endereço do cliente, o endereço de entrega da linha e os impostos baseados no destino que são configurados para o grupo de impostos determinam o grupo de impostos.</span><span class="sxs-lookup"><span data-stu-id="169fe-130">For shipping that doesn't involve sales tax on the customer's address, the delivery address of the line and the destination-based taxes that are configured for the tax group determine the tax group.</span></span> <span data-ttu-id="169fe-131">Para obter mais informações, consulte [Configurar os impostos para as lojas online com base no destino](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).</span><span class="sxs-lookup"><span data-stu-id="169fe-131">For more information, see [Set up taxes for online stores based on destination](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="169fe-132">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="169fe-132">Additional resources</span></span>

[<span data-ttu-id="169fe-133">Configurar impostos para ordens online</span><span class="sxs-lookup"><span data-stu-id="169fe-133">Configure sales tax for online orders</span></span>](../sales-tax-config.md)

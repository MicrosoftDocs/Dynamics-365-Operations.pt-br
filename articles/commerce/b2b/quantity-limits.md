---
title: Definir limites de quantidade de produto para sites de comércio eletrônico B2B
description: Este tópico descreve como definir os limites da quantidade de produtos para sites de comércio eletrônico B2B.
author: josaw1
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: e9f14bc9aa6586e87f3e8ccb82e63d0ec2e46534
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799772"
---
# <a name="set-product-quantity-limits-for-b2b-e-commerce-sites"></a><span data-ttu-id="25cb6-103">Definir limites de quantidade de produto para sites de comércio eletrônico B2B</span><span class="sxs-lookup"><span data-stu-id="25cb6-103">Set product quantity limits for B2B e-commerce sites</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="25cb6-104">Este tópico descreve como definir os limites da quantidade de produtos para sites de comércio eletrônico B2B.</span><span class="sxs-lookup"><span data-stu-id="25cb6-104">This topic describes how to set product quantity limits for business-to-business (B2B) e-commerce sites.</span></span>

<span data-ttu-id="25cb6-105">A maioria dos produtos tem uma unidade de medida que define seu agrupamento.</span><span class="sxs-lookup"><span data-stu-id="25cb6-105">Most products have a unit of measure that defines their grouping.</span></span> <span data-ttu-id="25cb6-106">O agrupamento afeta a forma como os produtos podem ser vendidos.</span><span class="sxs-lookup"><span data-stu-id="25cb6-106">The grouping affects how the products can be sold.</span></span> <span data-ttu-id="25cb6-107">Alguns produtos podem ter um agrupamento adicional para quantidades.</span><span class="sxs-lookup"><span data-stu-id="25cb6-107">Some products might have an additional grouping for quantities.</span></span> <span data-ttu-id="25cb6-108">Esse agrupamento determina se os produtos podem ser vendidos como unidades individuais ou múltiplos e se há um limite mínimo ou máximo de quantidade de ordens que deve ser seguido.</span><span class="sxs-lookup"><span data-stu-id="25cb6-108">This grouping determines whether the products can be sold as individual units or multiples, and whether there is a minimum or maximum order quantity limit that must be followed.</span></span>

<span data-ttu-id="25cb6-109">O recurso de limitação de quantidade garante que as quantidades mínimas, máximas, múltiplas e padrão que são configuradas no Microsoft Dynamics 365 Commerce (nas configurações de ordem padrão ou configurações do site criador do Commerce) sejam aplicadas às ordens de cliente realizadas em um site de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="25cb6-109">The quantity limiting feature ensures that the minimum, maximum, multiple, and standard quantities that are configured in Microsoft Dynamics 365 Commerce (in the default order settings or the Commerce site builder site settings) are applied to customer orders that are placed on an e-commerce site.</span></span> <span data-ttu-id="25cb6-110">No momento, não há suporte para os limites de quantidade do produto para o ponto de venda (POS) e call centers.</span><span class="sxs-lookup"><span data-stu-id="25cb6-110">Product quantity limits aren't currently supported for the point of sale (POS) and call centers.</span></span>

<span data-ttu-id="25cb6-111">Muitos revendedores fornecem a opção de ordens de cliente (também conhecidas como ordens especiais) para atender a vários requisitos de produto e atendimento.</span><span class="sxs-lookup"><span data-stu-id="25cb6-111">Many retailers provide the option of customer orders (also known as special orders) to meet various product and fulfillment requirements.</span></span> <span data-ttu-id="25cb6-112">Estes são alguns dos cenários típicos:</span><span class="sxs-lookup"><span data-stu-id="25cb6-112">Here are some typical scenarios:</span></span>

- <span data-ttu-id="25cb6-113">Um cliente quer que produtos de variantes específicas sejam vendidos em grupos de poucas unidades.</span><span class="sxs-lookup"><span data-stu-id="25cb6-113">A customer wants products of specific variants to be sold in multiples of a few.</span></span>
- <span data-ttu-id="25cb6-114">Um cliente deseja retirar produtos de uma loja ou local que é diferente da loja ou local no qual ele comprou esses produtos.</span><span class="sxs-lookup"><span data-stu-id="25cb6-114">A customer wants to pick up products from a store or location that differs from the store or location where the customer purchased those products.</span></span> <span data-ttu-id="25cb6-115">No entanto, os padrões de embalagem para os armazenamentos são diferentes dos padrões de embalagem para distribuição de vendas online.</span><span class="sxs-lookup"><span data-stu-id="25cb6-115">However, the packing standards for the stores differ from the packing standards for online sales distribution.</span></span>
- <span data-ttu-id="25cb6-116">Um cliente quer comprar um produto de edição limitada que tem uma quantidade máxima de itens que podem ser comprados.</span><span class="sxs-lookup"><span data-stu-id="25cb6-116">A customer wants to buy a limited-edition product that has a maximum quantity limit for items that can be purchased.</span></span>

## <a name="turn-on-the-default-order-settings-feature-in-commerce-headquarters"></a><span data-ttu-id="25cb6-117">Ativar o recurso de configurações de ordem padrão na matriz do Commerce</span><span class="sxs-lookup"><span data-stu-id="25cb6-117">Turn on the default order settings feature in Commerce headquarters</span></span>

<span data-ttu-id="25cb6-118">Para poder definir limites de quantidade do produto, o recurso de configurações de ordem padrão deve ser ativado na matriz do Commerce.</span><span class="sxs-lookup"><span data-stu-id="25cb6-118">Before you can set product quantity limits, the default order settings feature must be turned on in Commerce headquarters.</span></span>

<span data-ttu-id="25cb6-119">Siga estas etapas para ativar o recurso de configurações de ordem padrão.</span><span class="sxs-lookup"><span data-stu-id="25cb6-119">To turn on the default order settings feature, follow these steps.</span></span>

1. <span data-ttu-id="25cb6-120">Vá para **Administrador do sistema \> Espaços de trabalho \> Gerenciamento de recursos**.</span><span class="sxs-lookup"><span data-stu-id="25cb6-120">Go to **System administration \> Workspaces \> Feature management**.</span></span>
1. <span data-ttu-id="25cb6-121">Localize e selecione o recurso **Suporte às configurações de ordem do site e padrão na ordem de cliente**.</span><span class="sxs-lookup"><span data-stu-id="25cb6-121">Find and select the **Support the Site and Default order settings in the customer order** feature.</span></span>
1. <span data-ttu-id="25cb6-122">Na parte inferior do painel à direita, selecione **Ativar agora**.</span><span class="sxs-lookup"><span data-stu-id="25cb6-122">At the bottom of the right pane, select **Enable now**.</span></span> 

## <a name="define-quantity-settings"></a><span data-ttu-id="25cb6-123">Definir configurações de quantidade</span><span class="sxs-lookup"><span data-stu-id="25cb6-123">Define quantity settings</span></span> 

<span data-ttu-id="25cb6-124">Você pode definir as configurações de quantidade na página **Configurações de ordem padrão**.</span><span class="sxs-lookup"><span data-stu-id="25cb6-124">You can define the quantity settings on the **Default order settings** page.</span></span>

<span data-ttu-id="25cb6-125">Para definir as configurações de ordem, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="25cb6-125">To define the quantity settings, follow these steps.</span></span> 

1. <span data-ttu-id="25cb6-126">Vá para Produto **Retail e Commerce \> Produtos e categorias \> Produtos liberados por categoria**.</span><span class="sxs-lookup"><span data-stu-id="25cb6-126">Go to Product **Retail and Commerce \> Products and categories \> Released products by category**.</span></span>
1. <span data-ttu-id="25cb6-127">Selecione um produto liberado.</span><span class="sxs-lookup"><span data-stu-id="25cb6-127">Select a released product.</span></span>
1. <span data-ttu-id="25cb6-128">No Painel de ações da guia **Gerenciar estoque**, no grupo **Configurações da ordem**, selecione **Configurações padrão da ordem**.</span><span class="sxs-lookup"><span data-stu-id="25cb6-128">On the Action Pane, on the **Manage inventory** tab, in the **Order settings** group, select **Default order settings**.</span></span> 
1. <span data-ttu-id="25cb6-129">Na página **Configurações de ordem padrão**, na guia rápida **Ordem de venda**, na seção **Quantidade de venda**, defina as quantidades de vendas do produto:</span><span class="sxs-lookup"><span data-stu-id="25cb6-129">On the **Default order settings** page, on the **Sales order** FastTab, in the **Sales quantity** section, set the product sales quantities:</span></span>

    - <span data-ttu-id="25cb6-130">**Múltiplos** – A quantidade em que o produto pode ser comprado em múltiplos.</span><span class="sxs-lookup"><span data-stu-id="25cb6-130">**Multiple** – The quantity that the product can be bought in multiples of.</span></span>
    - <span data-ttu-id="25cb6-131">**Quantidade mínima da ordem** – O número mínimo de produtos que devem ser comprados.</span><span class="sxs-lookup"><span data-stu-id="25cb6-131">**Minimum Order Quantity** – The minimum number of products that must be purchased.</span></span>
    - <span data-ttu-id="25cb6-132">**Quantidade máximo da ordem** – O número máximo de produtos que podem ser comprados.</span><span class="sxs-lookup"><span data-stu-id="25cb6-132">**Maximum Order Quantity** – The maximum number of products that can be purchased.</span></span>
    - <span data-ttu-id="25cb6-133">**Quantidade de ordem padrão** – A quantidade padrão que é inserida automaticamente quando o produto é selecionado.</span><span class="sxs-lookup"><span data-stu-id="25cb6-133">**Standard Order Quantity** – The default quantity that is automatically entered when the product is selected.</span></span>

## <a name="turn-on-the-b2b-order-quantity-limits-feature-in-commerce-site-builder"></a><span data-ttu-id="25cb6-134">Ativar o recurso de limites de quantidade da ordem B2B no criador de sites do Commerce</span><span class="sxs-lookup"><span data-stu-id="25cb6-134">Turn on the B2B order quantity limits feature in Commerce site builder</span></span>

<span data-ttu-id="25cb6-135">Para ativar o recurso de limites de quantidade da ordem B2B no criador de sites do Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="25cb6-135">To turn on the B2B order quantity limits feature in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="25cb6-136">Acesse **Configurações do site \> Extensões**</span><span class="sxs-lookup"><span data-stu-id="25cb6-136">Go to **Site settings \> Extensions**</span></span>
1. <span data-ttu-id="25cb6-137">Em **Habilitar limites de quantidade da ordem**, selecione **Habilitado para clientes B2B** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="25cb6-137">Under **Enable Order Quantity Limits**, select **Enabled for B2B customers** in the drop-down menu.</span></span> 

> [!NOTE] 
> <span data-ttu-id="25cb6-138">As configurações atualizadas do construtor de sites terão efeito somente depois que o arquivo app.settings.json for atualizado.</span><span class="sxs-lookup"><span data-stu-id="25cb6-138">Updated site builder settings take effect only after the app.settings.json file has been updated.</span></span> <span data-ttu-id="25cb6-139">Para obter mais informações, consulte [SDK e atualizações da biblioteca de módulos](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span><span class="sxs-lookup"><span data-stu-id="25cb6-139">For more information, see [SDK and Module library updates](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="25cb6-140">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="25cb6-140">Additional resources</span></span>

[<span data-ttu-id="25cb6-141">Configurar um site de comércio eletrônico B2B</span><span class="sxs-lookup"><span data-stu-id="25cb6-141">Set up a B2B e-commerce site</span></span>](set-up-b2b-site.md)

[<span data-ttu-id="25cb6-142">Criar hierarquias de modelagem de organização para organizações B2B</span><span class="sxs-lookup"><span data-stu-id="25cb6-142">Create org modeling hierarchies for B2B organizations</span></span>](org-model.md)

[<span data-ttu-id="25cb6-143">Gerenciar usuários parceiros comerciais em sites de comércio eletrônico B2B</span><span class="sxs-lookup"><span data-stu-id="25cb6-143">Manage business partner users on B2B e-commerce sites</span></span>](manage-b2b-users.md)

[<span data-ttu-id="25cb6-144">Configurar o método de pagamento da conta do cliente para sites de comércio eletrônico B2B</span><span class="sxs-lookup"><span data-stu-id="25cb6-144">Configure the customer account payment method for B2B e-commerce sites</span></span>](payment-method.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
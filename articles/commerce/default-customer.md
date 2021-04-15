---
title: Criar um cliente padrão
description: Este tópico descreve como criar um cliente padrão para usar na criação de um canal no Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: ecdf4e5618d3397527bf83977857fbe3f8dbb265
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799170"
---
# <a name="create-a-default-customer"></a><span data-ttu-id="3b208-103">Criar um cliente padrão</span><span class="sxs-lookup"><span data-stu-id="3b208-103">Create a default customer</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3b208-104">Este tópico descreve como criar um cliente padrão para usar na criação de um canal no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3b208-104">This topic describes how to create a default customer to use when creating a channel in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="3b208-105">Quando for criar um canal, você precisará fornecer um cliente padrão.</span><span class="sxs-lookup"><span data-stu-id="3b208-105">When creating a channel, you will need to provide a default customer.</span></span> <span data-ttu-id="3b208-106">É possível criar um cliente padrão facilmente após a criação do grupo de clientes e do catálogo de endereços do cliente.</span><span class="sxs-lookup"><span data-stu-id="3b208-106">A default customer can easily be created after first creating the customer group and customer address book.</span></span>

## <a name="create-a-customer-group"></a><span data-ttu-id="3b208-107">Criar um grupo de clientes</span><span class="sxs-lookup"><span data-stu-id="3b208-107">Create a customer group</span></span>

<span data-ttu-id="3b208-108">Se ainda não existe nenhum grupo de clientes, você pode criar um.</span><span class="sxs-lookup"><span data-stu-id="3b208-108">If no customer groups exist yet, you can create one.</span></span> <span data-ttu-id="3b208-109">Exemplos podem ser grupos para representar diferentes grupos de clientes, como atacado, varejo, Internet, funcionários etc.</span><span class="sxs-lookup"><span data-stu-id="3b208-109">Examples may be groups to represent different customer groups, such as wholesale, retail, Internet, Employees, etc.</span></span>

<span data-ttu-id="3b208-110">Para criar um grupo de clientes, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="3b208-110">To create a customer group, follow these steps.</span></span>

1. <span data-ttu-id="3b208-111">No painel de navegação, vá para **Módulos \> Varejo e comércio \> Clientes \> Grupos de clientes**.</span><span class="sxs-lookup"><span data-stu-id="3b208-111">In the navigation pane, go to **Modules \> Retail and commerce \> Customers \> Customer groups**.</span></span>
1. <span data-ttu-id="3b208-112">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="3b208-112">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="3b208-113">Na caixa **Grupo de clientes**, insira uma ID de grupo de clientes.</span><span class="sxs-lookup"><span data-stu-id="3b208-113">In the **Customer group** box, enter a customer group ID.</span></span>
1. <span data-ttu-id="3b208-114">Na caixa **Descrição**, insira uma descrição apropriada.</span><span class="sxs-lookup"><span data-stu-id="3b208-114">In the **Description** box, enter an appropriate description.</span></span>
1. <span data-ttu-id="3b208-115">Na caixa **Condições de pagamento**, insira um valor apropriado.</span><span class="sxs-lookup"><span data-stu-id="3b208-115">In the **Terms of payment** box, enter an appropriate value.</span></span>
1. <span data-ttu-id="3b208-116">Na caixa **Tempo entre a data de vencimento da fatura e a data de pagamento**, insira um valor apropriado.</span><span class="sxs-lookup"><span data-stu-id="3b208-116">In the **Time between invoice due date and payment date** box, enter an appropriate value.</span></span>
1. <span data-ttu-id="3b208-117">Na caixa **Grupo de impostos padrão**, insira um grupo de impostos se aplicável.</span><span class="sxs-lookup"><span data-stu-id="3b208-117">In the **Default tax group** box, enter a tax group if applicable.</span></span>
1. <span data-ttu-id="3b208-118">Marque a caixa de seleção **Preços incluem imposto** se aplicável.</span><span class="sxs-lookup"><span data-stu-id="3b208-118">Select the **Prices include sales tax** check box if applicable.</span></span>
1. <span data-ttu-id="3b208-119">Na caixa **Motivo de baixa padrão**, insira um valor apropriado se aplicável.</span><span class="sxs-lookup"><span data-stu-id="3b208-119">In the **Default write-off reason** box, enter an appropriate value, if applicable.</span></span>

<span data-ttu-id="3b208-120">A imagem a seguir mostra vários grupos de clientes configurados.</span><span class="sxs-lookup"><span data-stu-id="3b208-120">The following image shows several configured customer groups.</span></span>

![Grupos de clientes](media/customer-groups.png)

## <a name="create-a-customer-address-book"></a><span data-ttu-id="3b208-122">Criar um catálogo de endereços do cliente</span><span class="sxs-lookup"><span data-stu-id="3b208-122">Create a customer address book</span></span>

<span data-ttu-id="3b208-123">Um cliente precisa estar associado a um catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="3b208-123">A customer needs to be associated with an address book.</span></span> <span data-ttu-id="3b208-124">Caso um catálogo de endereços ainda não tenha sido criado, você precisará criar um.</span><span class="sxs-lookup"><span data-stu-id="3b208-124">If one has not yet been created, then you will need to create one.</span></span>

<span data-ttu-id="3b208-125">Para criar um catálogo de endereços do cliente, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="3b208-125">To create a customer address book, follow these steps.</span></span>

1. <span data-ttu-id="3b208-126">No painel de navegação, vá para **Módulos \> Varejo e comércio \> Configuração de canal \> Catálogos de Endereços**.</span><span class="sxs-lookup"><span data-stu-id="3b208-126">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Address Books**.</span></span>
1. <span data-ttu-id="3b208-127">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="3b208-127">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="3b208-128">Na caixa **Nome**, insira um nome.</span><span class="sxs-lookup"><span data-stu-id="3b208-128">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="3b208-129">Na caixa **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="3b208-129">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="3b208-130">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="3b208-130">On the action pane, select **Save**.</span></span>

<span data-ttu-id="3b208-131">A imagem a seguir mostra um exemplo de catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="3b208-131">The following image shows an example address book.</span></span>

![Catálogo de endereços](media/address-book.png)

## <a name="create-a-default-customer&quot;></a><span data-ttu-id=&quot;3b208-133&quot;>Criar um cliente padrão</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;3b208-133&quot;>Create a default customer</span></span>

<span data-ttu-id=&quot;3b208-134&quot;>Para criar um cliente padrão, siga estas etapas.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;3b208-134&quot;>To create a default customer, follow these steps.</span></span>

1. <span data-ttu-id=&quot;3b208-135&quot;>No painel de navegação, vá para **Módulos \> Varejo e comércio \> Clientes \> Todos os clientes**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;3b208-135&quot;>In the navigation pane, go to **Modules \> Retail and commerce \> Customers \> All customers**.</span></span>
1. <span data-ttu-id=&quot;3b208-136&quot;>No painel de ação, selecione **Novo**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;3b208-136&quot;>On the action pane, select **New**.</span></span>
1. <span data-ttu-id=&quot;3b208-137&quot;>Na lista suspensa **Tipo**, selecione &quot;Pessoa&quot;.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;3b208-137&quot;>In the **Type** drop-down list, select &quot;Person&quot;.</span></span>
1. <span data-ttu-id=&quot;3b208-138&quot;>Na lista suspensa **Conta de cliente**, selecione ou insira um número de conta (por exemplo, &quot;100001").</span><span class="sxs-lookup"><span data-stu-id="3b208-138">In the **Customer account** drop-down list, select or enter an account number (for example, "100001").</span></span>
1. <span data-ttu-id="3b208-139">Na lista suspensa **Nome**, selecione ou insira um nome (por exemplo, "Padrão").</span><span class="sxs-lookup"><span data-stu-id="3b208-139">In the **First name** drop-down list, select or enter a name (for example, "Default").</span></span>
1. <span data-ttu-id="3b208-140">Na lista suspensa **Nome do meio**, selecione ou insira um nome (por exemplo, "Varejo").</span><span class="sxs-lookup"><span data-stu-id="3b208-140">In the **Middle name** drop-down list, select or enter a name (for example, "Retail").</span></span>
1. <span data-ttu-id="3b208-141">Na lista suspensa **Sobrenome**, selecione ou insira um nome (por exemplo, "Cliente").</span><span class="sxs-lookup"><span data-stu-id="3b208-141">In the **Last name** drop-down list, select or enter a name (for example, "Customer").</span></span>
1. <span data-ttu-id="3b208-142">Na lista suspensa **Moeda**, selecione ou insira uma moeda (por exemplo, "USD").</span><span class="sxs-lookup"><span data-stu-id="3b208-142">In the **Currency** drop-down list, select or enter a currency (for example, "USD").</span></span>
1. <span data-ttu-id="3b208-143">Na lista suspensa **Moeda**, selecione o grupo de clientes criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="3b208-143">In the **Currency** drop-down list, select the customer group created previously.</span></span>
1. <span data-ttu-id="3b208-144">Na lista suspensa **Catálogos de endereços**, selecione um catálogo de endereços do cliente existente.</span><span class="sxs-lookup"><span data-stu-id="3b208-144">In the **Address books**  drop-down list, select an existing customer address book.</span></span>
1. <span data-ttu-id="3b208-145">Selecione **Salvar** para salvar e voltar à tela de detalhes de cliente do novo cliente.</span><span class="sxs-lookup"><span data-stu-id="3b208-145">Select **Save** to save and return to customer details screen for the new customer.</span></span>

> [!NOTE]
> <span data-ttu-id="3b208-146">Não é necessário adicionar um endereço para um cliente padrão.</span><span class="sxs-lookup"><span data-stu-id="3b208-146">It is not necessary to add an address for a default customer.</span></span>

<span data-ttu-id="3b208-147">A imagem a seguir mostra um exemplo de criação de cliente.</span><span class="sxs-lookup"><span data-stu-id="3b208-147">The following image shows an example of customer creation.</span></span>

![Criação de cliente padrão](media/default-customer-creation.png)

<span data-ttu-id="3b208-149">A imagem a seguir mostra a configuração de um cliente padrão.</span><span class="sxs-lookup"><span data-stu-id="3b208-149">The following image shows a default customer configuration.</span></span>

![Configuração de cliente de exemplo](media/default-customer-configuration1.png)

<span data-ttu-id="3b208-151">A maioria dos valores padrão na tela de detalhes do cliente pode permanecer, mas dois valores devem ser alterados.</span><span class="sxs-lookup"><span data-stu-id="3b208-151">Most of the default values on the customer detials screen can remain, but two values should be changed.</span></span>

1. <span data-ttu-id="3b208-152">Na tela de detalhes do cliente, expanda **Padrões da ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="3b208-152">On the customer details screen, expand **Sales order defaults**.</span></span>
1. <span data-ttu-id="3b208-153">Na lista suspensa **Site**, selecione ou insira um site pré-configurado.</span><span class="sxs-lookup"><span data-stu-id="3b208-153">In the **Site** drop-down list, select or enter a pre-configured site.</span></span>
1. <span data-ttu-id="3b208-154">Na lista suspensa **Depósito**, selecione ou insira um depósito pré-configurado.</span><span class="sxs-lookup"><span data-stu-id="3b208-154">In the **Warehouse** drop-down list, and select or enter a pre-configured warehouse.</span></span>

<span data-ttu-id="3b208-155">A imagem a seguir mostra um exemplo de configuração de cliente.</span><span class="sxs-lookup"><span data-stu-id="3b208-155">The following image shows an example customer configuration.</span></span>

![Exemplo de configuração de cliente](media/default-customer-configuration2.png)

## <a name="additional-resources"></a><span data-ttu-id="3b208-157">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="3b208-157">Additional resources</span></span>

[<span data-ttu-id="3b208-158">Visão geral de canais</span><span class="sxs-lookup"><span data-stu-id="3b208-158">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="3b208-159">Pré-requisitos de configuração de canal</span><span class="sxs-lookup"><span data-stu-id="3b208-159">Channel setup prerequisites</span></span>](channels-prerequisites.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]

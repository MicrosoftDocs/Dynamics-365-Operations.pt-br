---
title: Criar um cliente padrão
description: Este tópico descreve como criar um cliente padrão para usar na criação de um canal no Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 1dd4dfc5b8ca7af66941d081b4c20be0f5d6001d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993391"
---
# <a name="create-a-default-customer"></a><span data-ttu-id="20339-103">Criar um cliente padrão</span><span class="sxs-lookup"><span data-stu-id="20339-103">Create a default customer</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="20339-104">Este tópico descreve como criar um cliente padrão para usar na criação de um canal no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="20339-104">This topic describes how to create a default customer to use when creating a channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="20339-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="20339-105">Overview</span></span>

<span data-ttu-id="20339-106">Quando for criar um canal, você precisará fornecer um cliente padrão.</span><span class="sxs-lookup"><span data-stu-id="20339-106">When creating a channel, you will need to provide a default customer.</span></span> <span data-ttu-id="20339-107">É possível criar um cliente padrão facilmente após a criação do grupo de clientes e do catálogo de endereços do cliente.</span><span class="sxs-lookup"><span data-stu-id="20339-107">A default customer can easily be created after first creating the customer group and customer address book.</span></span>

## <a name="create-a-customer-group"></a><span data-ttu-id="20339-108">Criar um grupo de clientes</span><span class="sxs-lookup"><span data-stu-id="20339-108">Create a customer group</span></span>

<span data-ttu-id="20339-109">Se ainda não existe nenhum grupo de clientes, você pode criar um.</span><span class="sxs-lookup"><span data-stu-id="20339-109">If no customer groups exist yet, you can create one.</span></span> <span data-ttu-id="20339-110">Exemplos podem ser grupos para representar diferentes grupos de clientes, como atacado, varejo, Internet, funcionários etc.</span><span class="sxs-lookup"><span data-stu-id="20339-110">Examples may be groups to represent different customer groups, such as wholesale, retail, Internet, Employees, etc.</span></span>

<span data-ttu-id="20339-111">Para criar um grupo de clientes, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="20339-111">To create a customer group, follow these steps.</span></span>

1. <span data-ttu-id="20339-112">No painel de navegação, vá para **Módulos \> Varejo e comércio \> Clientes \> Grupos de clientes**.</span><span class="sxs-lookup"><span data-stu-id="20339-112">In the navigation pane, go to **Modules \> Retail and commerce \> Customers \> Customer groups**.</span></span>
1. <span data-ttu-id="20339-113">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="20339-113">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="20339-114">Na caixa **Grupo de clientes**, insira uma ID de grupo de clientes.</span><span class="sxs-lookup"><span data-stu-id="20339-114">In the **Customer group** box, enter a customer group ID.</span></span>
1. <span data-ttu-id="20339-115">Na caixa **Descrição**, insira uma descrição apropriada.</span><span class="sxs-lookup"><span data-stu-id="20339-115">In the **Description** box, enter an appropriate description.</span></span>
1. <span data-ttu-id="20339-116">Na caixa **Condições de pagamento**, insira um valor apropriado.</span><span class="sxs-lookup"><span data-stu-id="20339-116">In the **Terms of payment** box, enter an appropriate value.</span></span>
1. <span data-ttu-id="20339-117">Na caixa **Tempo entre a data de vencimento da fatura e a data de pagamento**, insira um valor apropriado.</span><span class="sxs-lookup"><span data-stu-id="20339-117">In the **Time between invoice due date and payment date** box, enter an appropriate value.</span></span>
1. <span data-ttu-id="20339-118">Na caixa **Grupo de impostos padrão**, insira um grupo de impostos se aplicável.</span><span class="sxs-lookup"><span data-stu-id="20339-118">In the **Default tax group** box, enter a tax group if applicable.</span></span>
1. <span data-ttu-id="20339-119">Marque a caixa de seleção **Preços incluem imposto** se aplicável.</span><span class="sxs-lookup"><span data-stu-id="20339-119">Select the **Prices include sales tax** check box if applicable.</span></span>
1. <span data-ttu-id="20339-120">Na caixa **Motivo de baixa padrão**, insira um valor apropriado se aplicável.</span><span class="sxs-lookup"><span data-stu-id="20339-120">In the **Default write-off reason** box, enter an appropriate value, if applicable.</span></span>

<span data-ttu-id="20339-121">A imagem a seguir mostra vários grupos de clientes configurados.</span><span class="sxs-lookup"><span data-stu-id="20339-121">The following image shows several configured customer groups.</span></span>

![Grupos de clientes](media/customer-groups.png)

## <a name="create-a-customer-address-book"></a><span data-ttu-id="20339-123">Criar um catálogo de endereços do cliente</span><span class="sxs-lookup"><span data-stu-id="20339-123">Create a customer address book</span></span>

<span data-ttu-id="20339-124">Um cliente precisa estar associado a um catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="20339-124">A customer needs to be associated with an address book.</span></span> <span data-ttu-id="20339-125">Caso um catálogo de endereços ainda não tenha sido criado, você precisará criar um.</span><span class="sxs-lookup"><span data-stu-id="20339-125">If one has not yet been created, then you will need to create one.</span></span>

<span data-ttu-id="20339-126">Para criar um catálogo de endereços do cliente, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="20339-126">To create a customer address book, follow these steps.</span></span>

1. <span data-ttu-id="20339-127">No painel de navegação, vá para **Módulos \> Varejo e comércio \> Configuração de canal \> Catálogos de Endereços**.</span><span class="sxs-lookup"><span data-stu-id="20339-127">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Address Books**.</span></span>
1. <span data-ttu-id="20339-128">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="20339-128">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="20339-129">Na caixa **Nome**, insira um nome.</span><span class="sxs-lookup"><span data-stu-id="20339-129">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="20339-130">Na caixa **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="20339-130">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="20339-131">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="20339-131">On the action pane, select **Save**.</span></span>

<span data-ttu-id="20339-132">A imagem a seguir mostra um exemplo de catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="20339-132">The following image shows an example address book.</span></span>

![Catálogo de endereços](media/address-book.png)

## <a name="create-a-default-customer"></a><span data-ttu-id="20339-134">Criar um cliente padrão</span><span class="sxs-lookup"><span data-stu-id="20339-134">Create a default customer</span></span>

<span data-ttu-id="20339-135">Para criar um cliente padrão, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="20339-135">To create a default customer, follow these steps.</span></span>

1. <span data-ttu-id="20339-136">No painel de navegação, vá para **Módulos \> Varejo e comércio \> Clientes \> Todos os clientes**.</span><span class="sxs-lookup"><span data-stu-id="20339-136">In the navigation pane, go to **Modules \> Retail and commerce \> Customers \> All customers**.</span></span>
1. <span data-ttu-id="20339-137">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="20339-137">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="20339-138">Na lista suspensa **Tipo**, selecione "Pessoa".</span><span class="sxs-lookup"><span data-stu-id="20339-138">In the **Type** drop-down list, select "Person".</span></span>
1. <span data-ttu-id="20339-139">Na lista suspensa **Conta de cliente**, selecione ou insira um número de conta (por exemplo, "100001").</span><span class="sxs-lookup"><span data-stu-id="20339-139">In the **Customer account** drop-down list, select or enter an account number (for example, "100001").</span></span>
1. <span data-ttu-id="20339-140">Na lista suspensa **Nome**, selecione ou insira um nome (por exemplo, "Padrão").</span><span class="sxs-lookup"><span data-stu-id="20339-140">In the **First name** drop-down list, select or enter a name (for example, "Default").</span></span>
1. <span data-ttu-id="20339-141">Na lista suspensa **Nome do meio**, selecione ou insira um nome (por exemplo, "Varejo").</span><span class="sxs-lookup"><span data-stu-id="20339-141">In the **Middle name** drop-down list, select or enter a name (for example, "Retail").</span></span>
1. <span data-ttu-id="20339-142">Na lista suspensa **Sobrenome**, selecione ou insira um nome (por exemplo, "Cliente").</span><span class="sxs-lookup"><span data-stu-id="20339-142">In the **Last name** drop-down list, select or enter a name (for example, "Customer").</span></span>
1. <span data-ttu-id="20339-143">Na lista suspensa **Moeda**, selecione ou insira uma moeda (por exemplo, "USD").</span><span class="sxs-lookup"><span data-stu-id="20339-143">In the **Currency** drop-down list, select or enter a currency (for example, "USD").</span></span>
1. <span data-ttu-id="20339-144">Na lista suspensa **Moeda**, selecione o grupo de clientes criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="20339-144">In the **Currency** drop-down list, select the customer group created previously.</span></span>
1. <span data-ttu-id="20339-145">Na lista suspensa **Catálogos de endereços**, selecione um catálogo de endereços do cliente existente.</span><span class="sxs-lookup"><span data-stu-id="20339-145">In the **Address books**  drop-down list, select an existing customer address book.</span></span>
1. <span data-ttu-id="20339-146">Selecione **Salvar** para salvar e voltar à tela de detalhes de cliente do novo cliente.</span><span class="sxs-lookup"><span data-stu-id="20339-146">Select **Save** to save and return to customer details screen for the new customer.</span></span>

> [!NOTE]
> <span data-ttu-id="20339-147">Não é necessário adicionar um endereço para um cliente padrão.</span><span class="sxs-lookup"><span data-stu-id="20339-147">It is not necessary to add an address for a default customer.</span></span>

<span data-ttu-id="20339-148">A imagem a seguir mostra um exemplo de criação de cliente.</span><span class="sxs-lookup"><span data-stu-id="20339-148">The following image shows an example of customer creation.</span></span>

![Criação de cliente padrão](media/default-customer-creation.png)

<span data-ttu-id="20339-150">A imagem a seguir mostra a configuração de um cliente padrão.</span><span class="sxs-lookup"><span data-stu-id="20339-150">The following image shows a default customer configuration.</span></span>

![Configuração de cliente de exemplo](media/default-customer-configuration1.png)

<span data-ttu-id="20339-152">A maioria dos valores padrão na tela de detalhes do cliente pode permanecer, mas dois valores devem ser alterados.</span><span class="sxs-lookup"><span data-stu-id="20339-152">Most of the default values on the customer detials screen can remain, but two values should be changed.</span></span>

1. <span data-ttu-id="20339-153">Na tela de detalhes do cliente, expanda **Padrões da ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="20339-153">On the customer details screen, expand **Sales order defaults**.</span></span>
1. <span data-ttu-id="20339-154">Na lista suspensa **Site**, selecione ou insira um site pré-configurado.</span><span class="sxs-lookup"><span data-stu-id="20339-154">In the **Site** drop-down list, select or enter a pre-configured site.</span></span>
1. <span data-ttu-id="20339-155">Na lista suspensa **Depósito**, selecione ou insira um depósito pré-configurado.</span><span class="sxs-lookup"><span data-stu-id="20339-155">In the **Warehouse** drop-down list, and select or enter a pre-configured warehouse.</span></span>

<span data-ttu-id="20339-156">A imagem a seguir mostra um exemplo de configuração de cliente.</span><span class="sxs-lookup"><span data-stu-id="20339-156">The following image shows an example customer configuration.</span></span>

![Exemplo de configuração de cliente](media/default-customer-configuration2.png)

## <a name="additional-resources"></a><span data-ttu-id="20339-158">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="20339-158">Additional resources</span></span>

[<span data-ttu-id="20339-159">Visão geral de canais</span><span class="sxs-lookup"><span data-stu-id="20339-159">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="20339-160">Pré-requisitos de configuração de canal</span><span class="sxs-lookup"><span data-stu-id="20339-160">Channel setup prerequisites</span></span>](channels-prerequisites.md)

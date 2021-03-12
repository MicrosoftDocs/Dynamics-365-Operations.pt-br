---
title: Adicionar um endereço a uma ordem de serviço
description: Este tópico descreve como adicionar um endereço do cliente em uma ordem de serviço.
author: ShylaThompson
manager: tfehr
ms.date: 05/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d6c8f00eb1a1fe2ef3aea22da20ce218d7568f64
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4966046"
---
# <a name="add-an-address-to-a-service-order"></a><span data-ttu-id="13a24-103">Adicionar um endereço a uma ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="13a24-103">Add an address to a service order</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="13a24-104">Este tópico descreve como adicionar um endereço do cliente em uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="13a24-104">This topic describes how to add a customer address to a service order.</span></span> <span data-ttu-id="13a24-105">Ao criar uma ordem de serviço, as informações de endereço são transferidas do projeto ao qual a ordem de serviço está anexada.</span><span class="sxs-lookup"><span data-stu-id="13a24-105">When you create a service order, the address information is transferred from the project that the service order is attached to.</span></span> <span data-ttu-id="13a24-106">No entanto, você pode selecionar um local alternativo a partir dos endereços que já foram inseridos no Microsoft Dynamics AX para clientes, fornecedores, sites, depósitos, ordens de serviço e projetos.</span><span class="sxs-lookup"><span data-stu-id="13a24-106">However, you can select an alternative location from addresses that are already entered in Microsoft Dynamics AX for customers, vendors, sites, warehouses, service orders, and projects.</span></span>

<span data-ttu-id="13a24-107">Também é possível criar um novo endereço.</span><span class="sxs-lookup"><span data-stu-id="13a24-107">You can also create a new address.</span></span> <span data-ttu-id="13a24-108">Por padrão, o novo endereço é transferido para o projeto.</span><span class="sxs-lookup"><span data-stu-id="13a24-108">By default, the new address is transferred to the project.</span></span> <span data-ttu-id="13a24-109">No entanto, você pode especificar que o novo endereço é relevante apenas para essa instância de serviço.</span><span class="sxs-lookup"><span data-stu-id="13a24-109">However, you can specify that the new address is only relevant for this instance of the service.</span></span> <span data-ttu-id="13a24-110">Se fizer isso, o novo endereço não será transferido para o projeto.</span><span class="sxs-lookup"><span data-stu-id="13a24-110">If you do, the new address is not transferred to the project.</span></span>

## <a name="create-a-customer-address-for-a-service-order"></a><span data-ttu-id="13a24-111">Criar um endereço do cliente para uma ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="13a24-111">Create a customer address for a service order</span></span>

<span data-ttu-id="13a24-112">Para adicionar um endereço em uma ordem de serviço, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="13a24-112">To add an address to a service order, follow these steps:</span></span>

1.  <span data-ttu-id="13a24-113">Clique em **Gerenciamento de serviços** \> **Comum** \> **Ordens de serviço** \> **Ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="13a24-113">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="13a24-114">Abra a ordem de serviço para a qual você deseja criar um endereço.</span><span class="sxs-lookup"><span data-stu-id="13a24-114">Open the service order that you want to create an address for.</span></span>

3.  <span data-ttu-id="13a24-115">No **Painel de Ação**, clique em **Editar** e, em seguida, clique em **Exibição do cabeçalho**.</span><span class="sxs-lookup"><span data-stu-id="13a24-115">On the **Action Pane**, click **Edit**, and then click **Header view**.</span></span>

4.  <span data-ttu-id="13a24-116">Na Guia Rápida **Endereço**, clique em **Adicionar endereço**.</span><span class="sxs-lookup"><span data-stu-id="13a24-116">On the **Address** FastTab, click **Add address**.</span></span>

5.  <span data-ttu-id="13a24-117">No formulário **Novo endereço**, insira um nome exclusivo para o endereço e preencha os campos restantes.</span><span class="sxs-lookup"><span data-stu-id="13a24-117">In the **New address** form, enter a unique name for the address and complete the remaining fields.</span></span> 
    

    > [!WARNING]
    > <P><span data-ttu-id="13a24-118">Se você inserir o mesmo nome de um endereço existente, as informações inseridas nos campos restantes substituirão as informações do endereço existente.</span><span class="sxs-lookup"><span data-stu-id="13a24-118">If you enter the same name as an existing address, the information that you enter in the remaining fields will overwrite information for the existing address.</span></span></P>


6.  <span data-ttu-id="13a24-119">Clique em **OK** para copiar o novo endereço para sua ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="13a24-119">Click **OK** to copy the new address to your service order.</span></span>

## <a name="specify-an-alternative-address-on-a-service-order"></a><span data-ttu-id="13a24-120">Especificar um endereço alternativo em uma ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="13a24-120">Specify an alternative address on a service order</span></span>

<span data-ttu-id="13a24-121">Para adicionar um endereço alternativo em uma ordem de serviço, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="13a24-121">To add an alternative address to a service order, follow these steps:</span></span>

1.  <span data-ttu-id="13a24-122">Clique em **Gerenciamento de serviços** \> **Comum** \> **Ordens de serviço** \> **Ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="13a24-122">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="13a24-123">Abra a ordem de serviço para a qual você deseja inserir um endereço alternativo.</span><span class="sxs-lookup"><span data-stu-id="13a24-123">Open the service order that you want to enter an alternative address for.</span></span>

3.  <span data-ttu-id="13a24-124">No **Painel de Ação**, clique em **Editar** e, em seguida, clique em **Exibição do cabeçalho**.</span><span class="sxs-lookup"><span data-stu-id="13a24-124">On the **Action Pane**, click **Edit**, and then click **Header view**.</span></span>

4.  <span data-ttu-id="13a24-125">Na Guia Rápida **Endereço**, clique em **Outro endereço**.</span><span class="sxs-lookup"><span data-stu-id="13a24-125">On the **Address** FastTab, click **Other address**.</span></span>

5.  <span data-ttu-id="13a24-126">No formulário **Seleção de endereço**, no campo **Tipo de registro**, selecione **Ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="13a24-126">In the **Address selection** form, in the **Record type** field, select **Service orders**.</span></span>

6.  <span data-ttu-id="13a24-127">Selecione um endereço e, em seguida, clique em **OK** para copiá-lo em sua ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="13a24-127">Select an address, and then click **OK** to copy it to your service order.</span></span>


  



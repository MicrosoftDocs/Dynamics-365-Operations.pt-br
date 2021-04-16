---
title: Adicionar um endereço a uma ordem de serviço
description: Este tópico descreve como adicionar um endereço do cliente em uma ordem de serviço.
author: ShylaThompson
ms.date: 05/02/2018
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: a54ec439fc88dc9688bbb3d6b833b5d80482f024
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5824645"
---
# <a name="add-an-address-to-a-service-order"></a><span data-ttu-id="20857-103">Adicionar um endereço a uma ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="20857-103">Add an address to a service order</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="20857-104">Este tópico descreve como adicionar um endereço do cliente em uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="20857-104">This topic describes how to add a customer address to a service order.</span></span> <span data-ttu-id="20857-105">Ao criar uma ordem de serviço, as informações de endereço são transferidas do projeto ao qual a ordem de serviço está anexada.</span><span class="sxs-lookup"><span data-stu-id="20857-105">When you create a service order, the address information is transferred from the project that the service order is attached to.</span></span> <span data-ttu-id="20857-106">No entanto, você pode selecionar um local alternativo a partir dos endereços que já foram inseridos no Microsoft Dynamics AX para clientes, fornecedores, sites, depósitos, ordens de serviço e projetos.</span><span class="sxs-lookup"><span data-stu-id="20857-106">However, you can select an alternative location from addresses that are already entered in Microsoft Dynamics AX for customers, vendors, sites, warehouses, service orders, and projects.</span></span>

<span data-ttu-id="20857-107">Também é possível criar um novo endereço.</span><span class="sxs-lookup"><span data-stu-id="20857-107">You can also create a new address.</span></span> <span data-ttu-id="20857-108">Por padrão, o novo endereço é transferido para o projeto.</span><span class="sxs-lookup"><span data-stu-id="20857-108">By default, the new address is transferred to the project.</span></span> <span data-ttu-id="20857-109">No entanto, você pode especificar que o novo endereço é relevante apenas para essa instância de serviço.</span><span class="sxs-lookup"><span data-stu-id="20857-109">However, you can specify that the new address is only relevant for this instance of the service.</span></span> <span data-ttu-id="20857-110">Se fizer isso, o novo endereço não será transferido para o projeto.</span><span class="sxs-lookup"><span data-stu-id="20857-110">If you do, the new address is not transferred to the project.</span></span>

## <a name="create-a-customer-address-for-a-service-order"></a><span data-ttu-id="20857-111">Criar um endereço do cliente para uma ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="20857-111">Create a customer address for a service order</span></span>

<span data-ttu-id="20857-112">Para adicionar um endereço em uma ordem de serviço, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="20857-112">To add an address to a service order, follow these steps:</span></span>

1.  <span data-ttu-id="20857-113">Clique em **Gerenciamento de serviços** \> **Comum** \> **Ordens de serviço** \> **Ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="20857-113">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="20857-114">Abra a ordem de serviço para a qual você deseja criar um endereço.</span><span class="sxs-lookup"><span data-stu-id="20857-114">Open the service order that you want to create an address for.</span></span>

3.  <span data-ttu-id="20857-115">No **Painel de Ação**, clique em **Editar** e, em seguida, clique em **Exibição do cabeçalho**.</span><span class="sxs-lookup"><span data-stu-id="20857-115">On the **Action Pane**, click **Edit**, and then click **Header view**.</span></span>

4.  <span data-ttu-id="20857-116">Na Guia Rápida **Endereço**, clique em **Adicionar endereço**.</span><span class="sxs-lookup"><span data-stu-id="20857-116">On the **Address** FastTab, click **Add address**.</span></span>

5.  <span data-ttu-id="20857-117">No formulário **Novo endereço**, insira um nome exclusivo para o endereço e preencha os campos restantes.</span><span class="sxs-lookup"><span data-stu-id="20857-117">In the **New address** form, enter a unique name for the address and complete the remaining fields.</span></span> 
    

    > [!WARNING]
    > <P><span data-ttu-id="20857-118">Se você inserir o mesmo nome de um endereço existente, as informações inseridas nos campos restantes substituirão as informações do endereço existente.</span><span class="sxs-lookup"><span data-stu-id="20857-118">If you enter the same name as an existing address, the information that you enter in the remaining fields will overwrite information for the existing address.</span></span></P>


6.  <span data-ttu-id="20857-119">Clique em **OK** para copiar o novo endereço para sua ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="20857-119">Click **OK** to copy the new address to your service order.</span></span>

## <a name="specify-an-alternative-address-on-a-service-order"></a><span data-ttu-id="20857-120">Especificar um endereço alternativo em uma ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="20857-120">Specify an alternative address on a service order</span></span>

<span data-ttu-id="20857-121">Para adicionar um endereço alternativo em uma ordem de serviço, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="20857-121">To add an alternative address to a service order, follow these steps:</span></span>

1.  <span data-ttu-id="20857-122">Clique em **Gerenciamento de serviços** \> **Comum** \> **Ordens de serviço** \> **Ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="20857-122">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="20857-123">Abra a ordem de serviço para a qual você deseja inserir um endereço alternativo.</span><span class="sxs-lookup"><span data-stu-id="20857-123">Open the service order that you want to enter an alternative address for.</span></span>

3.  <span data-ttu-id="20857-124">No **Painel de Ação**, clique em **Editar** e, em seguida, clique em **Exibição do cabeçalho**.</span><span class="sxs-lookup"><span data-stu-id="20857-124">On the **Action Pane**, click **Edit**, and then click **Header view**.</span></span>

4.  <span data-ttu-id="20857-125">Na Guia Rápida **Endereço**, clique em **Outro endereço**.</span><span class="sxs-lookup"><span data-stu-id="20857-125">On the **Address** FastTab, click **Other address**.</span></span>

5.  <span data-ttu-id="20857-126">No formulário **Seleção de endereço**, no campo **Tipo de registro**, selecione **Ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="20857-126">In the **Address selection** form, in the **Record type** field, select **Service orders**.</span></span>

6.  <span data-ttu-id="20857-127">Selecione um endereço e, em seguida, clique em **OK** para copiá-lo em sua ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="20857-127">Select an address, and then click **OK** to copy it to your service order.</span></span>


  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
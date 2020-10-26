---
title: Criar relacionamentos de objeto de serviço
description: Este tópico descreve como criar relações de objeto de serviço para um contrato de serviço e uma ordem de serviço.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 352d3b790da340102b7dbe116d9deeb2f3cbfc4e
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3985960"
---
# <a name="create-service-object-relations"></a><span data-ttu-id="266a5-103">Criar relacionamentos de objeto de serviço</span><span class="sxs-lookup"><span data-stu-id="266a5-103">Create service object relations</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="266a5-104">Este tópico descreve como criar relações de objeto de serviço para um contrato de serviço e uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="266a5-104">This topic describes how to create service object relations for a service agreement and a service order.</span></span> <span data-ttu-id="266a5-105">Ao criar uma relação de objeto de serviço, você associa o objeto de serviço a um contrato de serviço ou à ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="266a5-105">When you a create service object relation, you associate the service object to a service agreement or service order.</span></span> <span data-ttu-id="266a5-106">Quando um cliente solicita o serviço para um item que é um objeto de serviço, você pode selecionar o objeto de serviço na lista de relações de objeto de serviço.</span><span class="sxs-lookup"><span data-stu-id="266a5-106">When a customer requests service for an item that is a service object, you can select the service object from the list of service object relations.</span></span>

## <a name="create-a-service-object-relation-for-a-service-agreement"></a><span data-ttu-id="266a5-107">Criar uma relação de objeto de serviço para um contrato de serviço</span><span class="sxs-lookup"><span data-stu-id="266a5-107">Create a service object relation for a service agreement</span></span>

<span data-ttu-id="266a5-108">Use as seguintes etapas para criar uma relação de objeto de serviço para um contrato de serviço:</span><span class="sxs-lookup"><span data-stu-id="266a5-108">Use the following steps to create a service object relation for a service agreement:</span></span>

1.  <span data-ttu-id="266a5-109">Clique em **Gerenciamento de serviços** \> **Comum** \> **Contratos de serviço** \> **Contratos de serviço**.</span><span class="sxs-lookup"><span data-stu-id="266a5-109">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="266a5-110">Na lista de **Contratos de serviço**, selecione um contrato de serviço existente ou clique em **Novo** para criar um novo contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="266a5-110">In the **Service agreements** list, select an existing service agreement, or click **New** to create a new service agreement.</span></span>

3.  <span data-ttu-id="266a5-111">No formulário de **Contratos de serviço**, no **Painel de Ação**, na guia **Contrato de serviço**, no grupo **Relações**, clique em **Objetos de serviço**.</span><span class="sxs-lookup"><span data-stu-id="266a5-111">In the **Service agreements** form, on the **Action Pane**, on the **Service agreement** tab, in the **Relations** group, click **Service objects**.</span></span>

4.  <span data-ttu-id="266a5-112">No formulário **Objetos de serviço**, clique em **Novo** e, em seguida, selecione um objeto de serviço para este contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="266a5-112">In the **Service objects** form, click **New**, and then select a service object for this service agreement.</span></span>

5.  <span data-ttu-id="266a5-113">Para atribuir uma lista de materiais (BOM) de modelo ao contrato de serviço, clique em **Funções** e, em seguida, selecione **Anexar modelo de BOM**.</span><span class="sxs-lookup"><span data-stu-id="266a5-113">To assign a template bill of materials (BOM) to the service agreement, click **Functions**, and then select **Attach template BOM**.</span></span> <span data-ttu-id="266a5-114">No formulário **Selecionar modelo de BOM**, no campo **Modelo de BOM**, selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="266a5-114">In the **Select template BOM** form, in the **Template BOM** field, select a template.</span></span> 

## <a name="create-a-service-object-relation-for-a-service-order"></a><span data-ttu-id="266a5-115">Criar uma relação de objeto de serviço para uma ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="266a5-115">Create a service object relation for a service order</span></span>

<span data-ttu-id="266a5-116">Use as seguintes etapas para criar uma relação de objeto de serviço para uma ordem de serviço:</span><span class="sxs-lookup"><span data-stu-id="266a5-116">Use the following steps to create a service object relation for a service order:</span></span>

1.  <span data-ttu-id="266a5-117">Clique em **Gerenciamento de serviços** \> **Comum** \> **Ordens de serviço** \> **Ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="266a5-117">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="266a5-118">Na lista de **Ordens de serviço**, selecione uma ordem de serviço existente ou crie uma nova ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="266a5-118">In the **Service orders** list, select an existing service order, or create a new service order.</span></span>

3.  <span data-ttu-id="266a5-119">No formulário de **Ordens de serviço**, no **Painel de Ação**, na guia **Ordem de serviço**, no grupo **Relações**, clique em **Objetos de serviço**.</span><span class="sxs-lookup"><span data-stu-id="266a5-119">In the **Service orders** form, on the **Action Pane**, on the **Service order** tab, in the **Relations** group, click **Service objects**.</span></span>

4.  <span data-ttu-id="266a5-120">No formulário **Objetos de serviço**, clique em **Novo** e, em seguida, selecione um objeto de serviço para esta ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="266a5-120">In the **Service objects** form, click **New**, and then select a service object for this service order.</span></span>

5.  <span data-ttu-id="266a5-121">Para atribuir uma lista de materiais (BOM) de modelo ao contrato de serviço, clique em **Funções** e, em seguida, selecione **Anexar modelo de BOM**.</span><span class="sxs-lookup"><span data-stu-id="266a5-121">To assign a template BOM to the service agreement, click **Functions**, and then select **Attach template BOM**.</span></span> <span data-ttu-id="266a5-122">No formulário **Selecionar modelo de BOM**, no campo **Modelo de BOM**, selecione um modelo.</span><span class="sxs-lookup"><span data-stu-id="266a5-122">In the **Select template BOM** form, in the **Template BOM** field, select a template.</span></span> 


## <a name="see-also"></a><span data-ttu-id="266a5-123">Consulte também</span><span class="sxs-lookup"><span data-stu-id="266a5-123">See also</span></span>

[<span data-ttu-id="266a5-124">Visão geral de objetos de serviço</span><span class="sxs-lookup"><span data-stu-id="266a5-124">Service objects overview</span></span>](service-objects.md)

[<span data-ttu-id="266a5-125">Relações do objeto de serviço</span><span class="sxs-lookup"><span data-stu-id="266a5-125">Service object relations</span></span>](service-object-relations.md)

[<span data-ttu-id="266a5-126">​BOMs de modelo​</span><span class="sxs-lookup"><span data-stu-id="266a5-126">Template BOMs</span></span>](template-boms.md)

  



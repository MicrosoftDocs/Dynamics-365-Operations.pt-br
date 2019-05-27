---
title: Relações do objeto de serviço
description: Você pode criar relações de objeto de serviço entre um objeto de serviço e um contrato de serviço ou uma ordem de serviço.
author: ShylaThompson
manager: AnnBe
ms.date: 02/21/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceObjectRelation
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 03047b3eccf3c90d4cf7426ddaec83f10dbea1b0
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571808"
---
# <a name="service-object-relations"></a><span data-ttu-id="af3fb-103">Relações do objeto de serviço</span><span class="sxs-lookup"><span data-stu-id="af3fb-103">Service object relations</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="af3fb-104">Você pode criar relações de objeto de serviço entre um objeto de serviço e um contrato de serviço ou uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="af3fb-104">You can create service object relations between a service object and a service agreement or service order.</span></span> <span data-ttu-id="af3fb-105">Ao criar uma relação, você anexa o objeto de serviço ao contrato de serviço ou à ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="af3fb-105">When you create a relation, you attach the service object to the service agreement or service order.</span></span>

<span data-ttu-id="af3fb-106">Quando a relação tiver sido criada, você anexa o objeto de serviço a qualquer linha no contrato de serviço ou na ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="af3fb-106">After the relation is created, you can attach the service object to any lines on the service agreement or service order.</span></span>

## <a name="template-boms"></a><span data-ttu-id="af3fb-107">BOMs de modelo</span><span class="sxs-lookup"><span data-stu-id="af3fb-107">Template BOMs</span></span>

<span data-ttu-id="af3fb-108">Você também pode especificar uma BOM de modelo para a relação de objeto.</span><span class="sxs-lookup"><span data-stu-id="af3fb-108">You can also specify a template BOM for the object relation.</span></span> <span data-ttu-id="af3fb-109">A BOM de modelo é uma lista de materiais para o objeto no qual você realiza um serviço.</span><span class="sxs-lookup"><span data-stu-id="af3fb-109">The template BOM is a bill of materials for the object on which you perform service.</span></span> <span data-ttu-id="af3fb-110">Se você substituir uma parte componente do objeto de serviço durante uma visita de serviço, você pode registrar essa alteração na BOM de serviço usando o formulário Objetos de serviço.</span><span class="sxs-lookup"><span data-stu-id="af3fb-110">If you replace a component part of the service object during a service visit, you can register this change in the service BOM by using the Service objects form.</span></span>

## <a name="example"></a><span data-ttu-id="af3fb-111">Exemplo</span><span class="sxs-lookup"><span data-stu-id="af3fb-111">Example</span></span>

<span data-ttu-id="af3fb-112">Você cria um contrato de serviço para atender dois elevadores no local do cliente.</span><span class="sxs-lookup"><span data-stu-id="af3fb-112">You create a service agreement for servicing two elevators at a customer site.</span></span>
<span data-ttu-id="af3fb-113">O contrato de serviço tem a identificação ID SAL-001.</span><span class="sxs-lookup"><span data-stu-id="af3fb-113">The service agreement has the identifier ID SAL-001.</span></span>

<span data-ttu-id="af3fb-114">Os elevadores foram configurados no formulário Objetos de serviço como objetos, EL-S/1000 e EL-L/1000.</span><span class="sxs-lookup"><span data-stu-id="af3fb-114">The elevators are set up in the Service objects form as objects, EL-S/1000 and EL-L/1000.</span></span>

<span data-ttu-id="af3fb-115">Você anexa os objetos de serviço (EL-S/1000 e EL-L/1000) ao contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="af3fb-115">You attach the service objects, EL-S/1000 and EL-L/1000, to the service agreement.</span></span>

<span data-ttu-id="af3fb-116">Você deseja registrar as alterações na BOM para o objeto de serviço enquanto substitui partes componentes do objeto; assim, anexa uma BOM de serviço à relação de objeto de serviço, conforme descrito na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="af3fb-116">You want to register changes in the BOM for the service object as you replace component parts of the object, so you attach a service BOM to the service object relation, as described in the following table.</span></span>

| <span data-ttu-id="af3fb-117">Objeto de serviço</span><span class="sxs-lookup"><span data-stu-id="af3fb-117">Service object</span></span> | <span data-ttu-id="af3fb-118">Relação - Contrato de serviço</span><span class="sxs-lookup"><span data-stu-id="af3fb-118">Relation – Service agreement</span></span> | <span data-ttu-id="af3fb-119">BOM de serviço</span><span class="sxs-lookup"><span data-stu-id="af3fb-119">Service BOM</span></span>   |
|----------------|------------------------------|---------------|
| <span data-ttu-id="af3fb-120">EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="af3fb-120">EL-S/1000</span></span>      | <span data-ttu-id="af3fb-121">ID SAL-001</span><span class="sxs-lookup"><span data-stu-id="af3fb-121">ID SAL-001</span></span>                   | <span data-ttu-id="af3fb-122">BOM-EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="af3fb-122">BOM-EL-S/1000</span></span> |
| <span data-ttu-id="af3fb-123">EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="af3fb-123">EL-L/1000</span></span>      | <span data-ttu-id="af3fb-124">ID SAL-001</span><span class="sxs-lookup"><span data-stu-id="af3fb-124">ID SAL-001</span></span>                   | <span data-ttu-id="af3fb-125">BOM-EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="af3fb-125">BOM-EL-L/1000</span></span> |

<span data-ttu-id="af3fb-126">Como há relações de objeto de serviço para o contrato, agora você pode criar linhas de contrato de serviço com esses objetos, conforme descrito na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="af3fb-126">Because there are service object relations for the agreement, you can now create service agreement lines with these objects, as shown in the following table.</span></span>

| <span data-ttu-id="af3fb-127">Tipo de transação</span><span class="sxs-lookup"><span data-stu-id="af3fb-127">Transaction type</span></span> | <span data-ttu-id="af3fb-128">Categoria</span><span class="sxs-lookup"><span data-stu-id="af3fb-128">Category</span></span>           | <span data-ttu-id="af3fb-129">Objeto de serviço</span><span class="sxs-lookup"><span data-stu-id="af3fb-129">Service object</span></span> |
|------------------|--------------------|----------------|
| <span data-ttu-id="af3fb-130">Hora</span><span class="sxs-lookup"><span data-stu-id="af3fb-130">Hour</span></span>             | <span data-ttu-id="af3fb-131">Inspeção</span><span class="sxs-lookup"><span data-stu-id="af3fb-131">Inspection</span></span>         | <span data-ttu-id="af3fb-132">EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="af3fb-132">EL-S/1000</span></span>      |
| <span data-ttu-id="af3fb-133">Hora</span><span class="sxs-lookup"><span data-stu-id="af3fb-133">Hour</span></span>             | <span data-ttu-id="af3fb-134">Limpeza da caixa de engrenagens</span><span class="sxs-lookup"><span data-stu-id="af3fb-134">Gear box cleaning</span></span>  | <span data-ttu-id="af3fb-135">EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="af3fb-135">EL-S/1000</span></span>      |
| <span data-ttu-id="af3fb-136">Item</span><span class="sxs-lookup"><span data-stu-id="af3fb-136">Item</span></span>             | <span data-ttu-id="af3fb-137">Material de limpeza</span><span class="sxs-lookup"><span data-stu-id="af3fb-137">Cleaning materials</span></span> | <span data-ttu-id="af3fb-138">EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="af3fb-138">EL-S/1000</span></span>      |
| <span data-ttu-id="af3fb-139">Hora</span><span class="sxs-lookup"><span data-stu-id="af3fb-139">Hour</span></span>             | <span data-ttu-id="af3fb-140">Inspeção</span><span class="sxs-lookup"><span data-stu-id="af3fb-140">Inspection</span></span>         | <span data-ttu-id="af3fb-141">EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="af3fb-141">EL-L/1000</span></span>      |
| <span data-ttu-id="af3fb-142">Hora</span><span class="sxs-lookup"><span data-stu-id="af3fb-142">Hour</span></span>             | <span data-ttu-id="af3fb-143">Limpeza da caixa de engrenagens</span><span class="sxs-lookup"><span data-stu-id="af3fb-143">Gearbox cleaning</span></span>   | <span data-ttu-id="af3fb-144">EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="af3fb-144">EL-L/1000</span></span>      |
| <span data-ttu-id="af3fb-145">Item</span><span class="sxs-lookup"><span data-stu-id="af3fb-145">Item</span></span>             | <span data-ttu-id="af3fb-146">Material de limpeza</span><span class="sxs-lookup"><span data-stu-id="af3fb-146">Cleaning materials</span></span> | <span data-ttu-id="af3fb-147">EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="af3fb-147">EL-L/1000</span></span>      |

<span data-ttu-id="af3fb-148">Em uma visita de serviço, é necessário substituir a caixa de embreagens do elevador EL-S/1000.</span><span class="sxs-lookup"><span data-stu-id="af3fb-148">On a service visit, you have to replace the gearbox for elevator EL-S/1000.</span></span> <span data-ttu-id="af3fb-149">Para substituir uma parte componente do objeto, você pode acessar o Designer de BOM usando a relação de objeto de serviço configurada para o contrato de serviço atual.</span><span class="sxs-lookup"><span data-stu-id="af3fb-149">To replace a component part of the object, you can access the BOM Designer by using the service object relation that you set up for the current service agreement.</span></span>

<span data-ttu-id="af3fb-150">Acessar o Designer de BOM usando uma relação de objeto de serviço</span><span class="sxs-lookup"><span data-stu-id="af3fb-150">Access the BOM Designer by using a service object relation</span></span>

1. <span data-ttu-id="af3fb-151">Contratos de serviço</span><span class="sxs-lookup"><span data-stu-id="af3fb-151">Service agreements</span></span>
2. <span data-ttu-id="af3fb-152">Clique duas vezes em um contrato de serviço ou clique em Contrato de serviço para criar um novo contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="af3fb-152">Double-click a service agreement, or click Service agreement to create a service agreement.</span></span>
3. <span data-ttu-id="af3fb-153">Clique na guia Configuração.</span><span class="sxs-lookup"><span data-stu-id="af3fb-153">Click the Setup tab.</span></span>
4. <span data-ttu-id="af3fb-154">Clique em Objetos de serviço para anexar uma BOM de modelo ao contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="af3fb-154">Click Service objects to attach a template BOM to the service agreement.</span></span>
5. <span data-ttu-id="af3fb-155">No formulário Objetos de serviço, clique em Designer para abrir o formulário Designer para modificar a BOM de modelo.</span><span class="sxs-lookup"><span data-stu-id="af3fb-155">In the Service objects form, click Designer to open the Designer form to modify the template BOM.</span></span>

## <a name="automatically-created-service-orders"></a><span data-ttu-id="af3fb-156">Ordens de serviço criadas automaticamente</span><span class="sxs-lookup"><span data-stu-id="af3fb-156">Automatically created service orders</span></span>

<span data-ttu-id="af3fb-157">Se você criar ordens de serviço automaticamente para um contrato de serviço, as relações de objeto de serviço no contrato também estarão nas ordens de serviço criadas.</span><span class="sxs-lookup"><span data-stu-id="af3fb-157">If you automatically create service orders for a service agreement, the service object relations in the agreement are also created in the service orders.</span></span>


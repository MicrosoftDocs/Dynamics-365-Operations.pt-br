---
title: Combinar ordens de serviço
description: Você pode combinar ordens de serviço.
author: ShylaThompson
ms.date: 05/01/2018
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
ms.openlocfilehash: 41b4a3234e4104372f1052d89c2417984e9cd10d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840548"
---
# <a name="combine-service-orders"></a><span data-ttu-id="3ce38-103">Combinar ordens de serviço</span><span class="sxs-lookup"><span data-stu-id="3ce38-103">Combine service orders</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="3ce38-104">Quando você cria linhas de ordem de serviço automaticamente no formulário de **Contratos de serviço**, é possível escolher uma das seguintes opções para especificar como deseja agrupá-las:</span><span class="sxs-lookup"><span data-stu-id="3ce38-104">When you create service order lines automatically in the **Service agreements** form, you can choose one of the following options to specify how you want to group them:</span></span>

  - <span data-ttu-id="3ce38-105">**Por contrato de serviço**</span><span class="sxs-lookup"><span data-stu-id="3ce38-105">**By service agreement**</span></span>

  - <span data-ttu-id="3ce38-106">**Por tarefa de serviço**</span><span class="sxs-lookup"><span data-stu-id="3ce38-106">**By service task**</span></span>

  - <span data-ttu-id="3ce38-107">**Por funcionário**</span><span class="sxs-lookup"><span data-stu-id="3ce38-107">**By employee**</span></span>

  - <span data-ttu-id="3ce38-108">**Por objeto de serviço**</span><span class="sxs-lookup"><span data-stu-id="3ce38-108">**By service object**</span></span>

## <a name="example"></a><span data-ttu-id="3ce38-109">Exemplo</span><span class="sxs-lookup"><span data-stu-id="3ce38-109">Example</span></span>

<span data-ttu-id="3ce38-110">Você cria um contrato de serviço com uma data inicial em 31-03-2007.</span><span class="sxs-lookup"><span data-stu-id="3ce38-110">You create a service agreement that has a start date on 03-31-2007.</span></span> <span data-ttu-id="3ce38-111">No campo **Combinar ordens de serviço**, você especifica **Por objeto de serviço**.</span><span class="sxs-lookup"><span data-stu-id="3ce38-111">In the **Combine service orders** field, you specify **By service object**.</span></span> <span data-ttu-id="3ce38-112">Em seguida, será possível criar estas linhas de contrato de serviço:</span><span class="sxs-lookup"><span data-stu-id="3ce38-112">You then create the following service agreement lines:</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="3ce38-113">Número da linha do contrato</span><span class="sxs-lookup"><span data-stu-id="3ce38-113">Agreement line number</span></span></p></th>
<th><p><span data-ttu-id="3ce38-114">Tipo de transação</span><span class="sxs-lookup"><span data-stu-id="3ce38-114">Transaction type</span></span></p></th>
<th><p><span data-ttu-id="3ce38-115">descrição</span><span class="sxs-lookup"><span data-stu-id="3ce38-115">Description</span></span></p></th>
<th><p><span data-ttu-id="3ce38-116">Intervalo</span><span class="sxs-lookup"><span data-stu-id="3ce38-116">Interval</span></span></p></th>
<th><p><span data-ttu-id="3ce38-117">Objeto de serviço</span><span class="sxs-lookup"><span data-stu-id="3ce38-117">Service object</span></span></p></th>
<th><p><span data-ttu-id="3ce38-118">Data de início</span><span class="sxs-lookup"><span data-stu-id="3ce38-118">Start date</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ce38-119">1</span><span class="sxs-lookup"><span data-stu-id="3ce38-119">1</span></span></p></td>
<td><p><span data-ttu-id="3ce38-120"><strong>Hora</strong></span><span class="sxs-lookup"><span data-stu-id="3ce38-120"><strong>Hour</strong></span></span></p></td>
<td><p><span data-ttu-id="3ce38-121">SAL1</span><span class="sxs-lookup"><span data-stu-id="3ce38-121">SAL1</span></span></p></td>
<td><p><span data-ttu-id="3ce38-122">Semanalmente</span><span class="sxs-lookup"><span data-stu-id="3ce38-122">Weekly</span></span></p></td>
<td><p><span data-ttu-id="3ce38-123">X-1</span><span class="sxs-lookup"><span data-stu-id="3ce38-123">X-1</span></span></p></td>
<td><p><span data-ttu-id="3ce38-124">04-01-2007</span><span class="sxs-lookup"><span data-stu-id="3ce38-124">04-01-2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ce38-125">2</span><span class="sxs-lookup"><span data-stu-id="3ce38-125">2</span></span></p></td>
<td><p><span data-ttu-id="3ce38-126"><strong>Hora</strong></span><span class="sxs-lookup"><span data-stu-id="3ce38-126"><strong>Hour</strong></span></span></p></td>
<td><p><span data-ttu-id="3ce38-127">SAL2</span><span class="sxs-lookup"><span data-stu-id="3ce38-127">SAL2</span></span></p></td>
<td><p><span data-ttu-id="3ce38-128">Quinzenal</span><span class="sxs-lookup"><span data-stu-id="3ce38-128">Biweekly</span></span></p></td>
<td><p><span data-ttu-id="3ce38-129">X-2</span><span class="sxs-lookup"><span data-stu-id="3ce38-129">X-2</span></span></p></td>
<td><p><span data-ttu-id="3ce38-130">04-01-2007</span><span class="sxs-lookup"><span data-stu-id="3ce38-130">04-01-2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ce38-131">3</span><span class="sxs-lookup"><span data-stu-id="3ce38-131">3</span></span></p></td>
<td><p><span data-ttu-id="3ce38-132"><strong>Hora</strong></span><span class="sxs-lookup"><span data-stu-id="3ce38-132"><strong>Hour</strong></span></span></p></td>
<td><p><span data-ttu-id="3ce38-133">SAL3</span><span class="sxs-lookup"><span data-stu-id="3ce38-133">SAL3</span></span></p></td>
<td><p><span data-ttu-id="3ce38-134">Semanalmente</span><span class="sxs-lookup"><span data-stu-id="3ce38-134">Weekly</span></span></p></td>
<td><p><span data-ttu-id="3ce38-135">X-2</span><span class="sxs-lookup"><span data-stu-id="3ce38-135">X-2</span></span></p></td>
<td><p><span data-ttu-id="3ce38-136">04-01-2007</span><span class="sxs-lookup"><span data-stu-id="3ce38-136">04-01-2007</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3ce38-137">Você não especifica janelas de tempo para nenhuma das linhas de contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="3ce38-137">You do not specify time windows for any of the service agreement lines.</span></span> <span data-ttu-id="3ce38-138">Portanto, as linhas da ordem de serviço não serão movidas a partir do dia calculado em que caem.</span><span class="sxs-lookup"><span data-stu-id="3ce38-138">Therefore, the service order lines will not move from the calculated day on which they fall.</span></span>

<span data-ttu-id="3ce38-139">Em seguida, gere as linhas de ordem de serviço no formulário **Criar ordens de serviço** de 01-04-2007 até 30-04-2007.</span><span class="sxs-lookup"><span data-stu-id="3ce38-139">Next, you generate service order lines from the **Create service orders** form from 04-01-2007 until 04-30-2007.</span></span>

<span data-ttu-id="3ce38-140">No total, serão criadas 10 ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="3ce38-140">In total, 10 service orders are created.</span></span> <span data-ttu-id="3ce38-141">Como a configuração combinada selecionada era **Por objeto de serviço**, todas as ordens de serviço que forem criadas terão somente linhas de ordem de serviço com um objeto de serviço específico.</span><span class="sxs-lookup"><span data-stu-id="3ce38-141">Because the combined setting that you selected was **By service object**, all service orders that are created have only service order lines with one specific service object.</span></span> <span data-ttu-id="3ce38-142">As linhas de ordem de serviço são geradas a partir do contrato de serviço e que têm a mesma data de serviço e objeto que serão combinados na mesma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="3ce38-142">Service order lines that are generated from the service agreement and have the same service date and object are combined on the same service order.</span></span>


> [!NOTE]
> <P><span data-ttu-id="3ce38-143">Neste exemplo, o calendário especificado no formulário de <STRONG>Parâmetros de gerenciamento de serviços</STRONG> não tem dias fechados.</span><span class="sxs-lookup"><span data-stu-id="3ce38-143">In this example, the calendar that is specified in the <STRONG>Service management parameters</STRONG> form has no closed days.</span></span></P>



<span data-ttu-id="3ce38-144">O agrupamento adicional de linhas de ordem de serviço em ordens de serviço ocorre de acordo com a janela de tempo especificada nas linhas de contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="3ce38-144">Additional grouping of service order lines into service orders occurs according to any time window that you specify on the service agreement lines.</span></span>

## <a name="see-also"></a><span data-ttu-id="3ce38-145">Consulte também</span><span class="sxs-lookup"><span data-stu-id="3ce38-145">See also</span></span>

[<span data-ttu-id="3ce38-146">Criar ordens de serviço automaticamente</span><span class="sxs-lookup"><span data-stu-id="3ce38-146">Create service orders automatically</span></span>](create-service-orders-automatically.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
---
title: "Habilitar o processo de folha de pagamento para horário e presença"
description: "Este procedimento mostra como habilitar o processo de folha de pagamento de tempo e presença."
author: johanhoffmann
manager: AnnBe
ms.date: 02/12/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: dadf0e87eac8522f61bb094c146e37f46a21fc09
ms.openlocfilehash: 16d8fc2120dfb7b356b238957019a29d05963f9a
ms.contentlocale: pt-br
ms.lasthandoff: 02/06/2018

---
# <a name="enable-the-payroll-process-for-time-and-attendance"></a><span data-ttu-id="a586a-103">Habilitar o processo de folha de pagamento para horário e presença</span><span class="sxs-lookup"><span data-stu-id="a586a-103">Enable the payroll process for time and attendance</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a586a-104">Este procedimento mostra como habilitar o processo de folha de pagamento de tempo e presença.</span><span class="sxs-lookup"><span data-stu-id="a586a-104">This procedure shows how to enable the payroll process for time and attendance.</span></span> <span data-ttu-id="a586a-105">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="a586a-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-pay-type-with-a-related-pay-rate"></a><span data-ttu-id="a586a-106">Criar um tipo de pagamento com uma taxa de pagamento relacionada</span><span class="sxs-lookup"><span data-stu-id="a586a-106">Create a pay type with a related pay rate</span></span>
1. <span data-ttu-id="a586a-107">Hora e atendimento > Configuração > Folha de pagamento > Tipos de pagamento</span><span class="sxs-lookup"><span data-stu-id="a586a-107">Time and attendance > Setup > Payroll > Pay types</span></span>
2. <span data-ttu-id="a586a-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="a586a-108">Click New.</span></span>
3. <span data-ttu-id="a586a-109">No campo Tipo de pagamento, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="a586a-109">In the Pay type field, type a value.</span></span>
4. <span data-ttu-id="a586a-110">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="a586a-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="a586a-111">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="a586a-111">Click Save.</span></span>
6. <span data-ttu-id="a586a-112">Clique em Taxas.</span><span class="sxs-lookup"><span data-stu-id="a586a-112">Click Rates.</span></span>
    * <span data-ttu-id="a586a-113">As taxas para os tipos de pagamento são definidas para intervalos de tempo específicos e taxas individuais podem ser criadas para trabalhadores.</span><span class="sxs-lookup"><span data-stu-id="a586a-113">Rates for pay types are set up for specific time intervals, and individual rates can be created for workers.</span></span> <span data-ttu-id="a586a-114">Nem sempre é necessário criar taxas para tipos de pagamento em tempo e presença.</span><span class="sxs-lookup"><span data-stu-id="a586a-114">It is not always necessary to create rates for pay types in time and attendance.</span></span> <span data-ttu-id="a586a-115">Essas informações já podem existir no sistema de folha de pagamento usado na geração dos salários.</span><span class="sxs-lookup"><span data-stu-id="a586a-115">This information may already exist in the payroll system that is used to generate wages.</span></span>  
7. <span data-ttu-id="a586a-116">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="a586a-116">Click New.</span></span>
8. <span data-ttu-id="a586a-117">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="a586a-117">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="a586a-118">No campo Taxa, insira um número.</span><span class="sxs-lookup"><span data-stu-id="a586a-118">In the Rate field, enter a number.</span></span>
10. <span data-ttu-id="a586a-119">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="a586a-119">Click Save.</span></span>

## <a name="create-a-pay-agreement"></a><span data-ttu-id="a586a-120">Criar um contrato de pagamento</span><span class="sxs-lookup"><span data-stu-id="a586a-120">Create a pay agreement</span></span>
1. <span data-ttu-id="a586a-121">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a586a-121">Close the page.</span></span>
2. <span data-ttu-id="a586a-122">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a586a-122">Close the page.</span></span>
3. <span data-ttu-id="a586a-123">Vá para Contratos de pagamento.</span><span class="sxs-lookup"><span data-stu-id="a586a-123">Go to Pay agreements.</span></span>
    * <span data-ttu-id="a586a-124">Hora e atendimento > Configuração > Contratos de pagamento</span><span class="sxs-lookup"><span data-stu-id="a586a-124">Time and attendance > Setup > Pay agreements</span></span>  
4. <span data-ttu-id="a586a-125">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="a586a-125">Click New.</span></span>
5. <span data-ttu-id="a586a-126">No campo Contrato de pagamento, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="a586a-126">In the Pay agreement field, type a value.</span></span>
6. <span data-ttu-id="a586a-127">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="a586a-127">In the Description field, type a value.</span></span>
7. <span data-ttu-id="a586a-128">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="a586a-128">Click Save.</span></span>
8. <span data-ttu-id="a586a-129">Clique em Linhas de contrato.</span><span class="sxs-lookup"><span data-stu-id="a586a-129">Click Agreement lines.</span></span>
9. <span data-ttu-id="a586a-130">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="a586a-130">Click New.</span></span>
10. <span data-ttu-id="a586a-131">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="a586a-131">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="a586a-132">No campo Tipo de perfil, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="a586a-132">In the Profile type field, enter or select a value.</span></span>
12. <span data-ttu-id="a586a-133">No campo Tipo de pagamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="a586a-133">In the Pay type field, enter or select a value.</span></span>

## <a name="set-up-pay-agreement-for-time-and-registration-worker"></a><span data-ttu-id="a586a-134">Configurar o contrato de pagamento do funcionário por tempo e registro</span><span class="sxs-lookup"><span data-stu-id="a586a-134">Set up pay agreement for time and registration worker</span></span>
1. <span data-ttu-id="a586a-135">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a586a-135">Close the page.</span></span>
2. <span data-ttu-id="a586a-136">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a586a-136">Close the page.</span></span>
3. <span data-ttu-id="a586a-137">Vá para Trabalhadores de registro de tempo.</span><span class="sxs-lookup"><span data-stu-id="a586a-137">Go to Time registration workers.</span></span>
    * <span data-ttu-id="a586a-138">Hora e atendimento > Configuração > Tempo de registro dos trabalhadores</span><span class="sxs-lookup"><span data-stu-id="a586a-138">Time and attendance > Setup > Time registration workers</span></span>  
4. <span data-ttu-id="a586a-139">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="a586a-139">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="a586a-140">Clique na guia Emprego.</span><span class="sxs-lookup"><span data-stu-id="a586a-140">Click the Employment tab.</span></span>
6. <span data-ttu-id="a586a-141">Expanda a seção de Tempo de registro.</span><span class="sxs-lookup"><span data-stu-id="a586a-141">Expand the Time registration section.</span></span>
7. <span data-ttu-id="a586a-142">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="a586a-142">Click Edit.</span></span>
8. <span data-ttu-id="a586a-143">No campo Contrato de pagamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="a586a-143">In the Pay agreement field, enter or select a value.</span></span>


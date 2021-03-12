---
title: Habilitar o processo de folha de pagamento para horário e presença
description: Este procedimento mostra como habilitar o processo de folha de pagamento de tempo e presença.
author: johanhoffmann
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgPayTable, JmgPayRate, JmgPayAgreementTable, JmgPayAgreementLine, HcmWorker
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c855f388e8afbd12559cd633cfcdebc7740bce6a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977779"
---
# <a name="enable-the-payroll-process-for-time-and-attendance"></a><span data-ttu-id="7b33e-103">Habilitar o processo de folha de pagamento para horário e presença</span><span class="sxs-lookup"><span data-stu-id="7b33e-103">Enable the payroll process for time and attendance</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7b33e-104">Este procedimento mostra como habilitar o processo de folha de pagamento de tempo e presença.</span><span class="sxs-lookup"><span data-stu-id="7b33e-104">This procedure shows how to enable the payroll process for time and attendance.</span></span> <span data-ttu-id="7b33e-105">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="7b33e-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-pay-type-with-a-related-pay-rate"></a><span data-ttu-id="7b33e-106">Criar um tipo de pagamento com uma taxa de pagamento relacionada</span><span class="sxs-lookup"><span data-stu-id="7b33e-106">Create a pay type with a related pay rate</span></span>
1. <span data-ttu-id="7b33e-107">Hora e atendimento > Configuração > Folha de pagamento > Tipos de pagamento</span><span class="sxs-lookup"><span data-stu-id="7b33e-107">Time and attendance > Setup > Payroll > Pay types</span></span>
2. <span data-ttu-id="7b33e-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="7b33e-108">Click New.</span></span>
3. <span data-ttu-id="7b33e-109">No campo Tipo de pagamento, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7b33e-109">In the Pay type field, type a value.</span></span>
4. <span data-ttu-id="7b33e-110">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7b33e-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="7b33e-111">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="7b33e-111">Click Save.</span></span>
6. <span data-ttu-id="7b33e-112">Clique em Taxas.</span><span class="sxs-lookup"><span data-stu-id="7b33e-112">Click Rates.</span></span>
    * <span data-ttu-id="7b33e-113">As taxas para os tipos de pagamento são definidas para intervalos de tempo específicos e taxas individuais podem ser criadas para trabalhadores.</span><span class="sxs-lookup"><span data-stu-id="7b33e-113">Rates for pay types are set up for specific time intervals, and individual rates can be created for workers.</span></span> <span data-ttu-id="7b33e-114">Nem sempre é necessário criar taxas para tipos de pagamento em tempo e presença.</span><span class="sxs-lookup"><span data-stu-id="7b33e-114">It is not always necessary to create rates for pay types in time and attendance.</span></span> <span data-ttu-id="7b33e-115">Essas informações já podem existir no sistema de folha de pagamento usado na geração dos salários.</span><span class="sxs-lookup"><span data-stu-id="7b33e-115">This information may already exist in the payroll system that is used to generate wages.</span></span>  
7. <span data-ttu-id="7b33e-116">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="7b33e-116">Click New.</span></span>
8. <span data-ttu-id="7b33e-117">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="7b33e-117">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="7b33e-118">No campo Taxa, insira um número.</span><span class="sxs-lookup"><span data-stu-id="7b33e-118">In the Rate field, enter a number.</span></span>
10. <span data-ttu-id="7b33e-119">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="7b33e-119">Click Save.</span></span>

## <a name="create-a-pay-agreement"></a><span data-ttu-id="7b33e-120">Criar um contrato de pagamento</span><span class="sxs-lookup"><span data-stu-id="7b33e-120">Create a pay agreement</span></span>
1. <span data-ttu-id="7b33e-121">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7b33e-121">Close the page.</span></span>
2. <span data-ttu-id="7b33e-122">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7b33e-122">Close the page.</span></span>
3. <span data-ttu-id="7b33e-123">Vá para Contratos de pagamento.</span><span class="sxs-lookup"><span data-stu-id="7b33e-123">Go to Pay agreements.</span></span>
    * <span data-ttu-id="7b33e-124">Hora e atendimento > Configuração > Contratos de pagamento</span><span class="sxs-lookup"><span data-stu-id="7b33e-124">Time and attendance > Setup > Pay agreements</span></span>  
4. <span data-ttu-id="7b33e-125">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="7b33e-125">Click New.</span></span>
5. <span data-ttu-id="7b33e-126">No campo Contrato de pagamento, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7b33e-126">In the Pay agreement field, type a value.</span></span>
6. <span data-ttu-id="7b33e-127">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7b33e-127">In the Description field, type a value.</span></span>
7. <span data-ttu-id="7b33e-128">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="7b33e-128">Click Save.</span></span>
8. <span data-ttu-id="7b33e-129">Clique em Linhas de contrato.</span><span class="sxs-lookup"><span data-stu-id="7b33e-129">Click Agreement lines.</span></span>
9. <span data-ttu-id="7b33e-130">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="7b33e-130">Click New.</span></span>
10. <span data-ttu-id="7b33e-131">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="7b33e-131">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="7b33e-132">No campo Tipo de perfil, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7b33e-132">In the Profile type field, enter or select a value.</span></span>
12. <span data-ttu-id="7b33e-133">No campo Tipo de pagamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7b33e-133">In the Pay type field, enter or select a value.</span></span>

## <a name="set-up-pay-agreement-for-time-and-registration-worker"></a><span data-ttu-id="7b33e-134">Configurar o contrato de pagamento do funcionário por tempo e registro</span><span class="sxs-lookup"><span data-stu-id="7b33e-134">Set up pay agreement for time and registration worker</span></span>
1. <span data-ttu-id="7b33e-135">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7b33e-135">Close the page.</span></span>
2. <span data-ttu-id="7b33e-136">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7b33e-136">Close the page.</span></span>
3. <span data-ttu-id="7b33e-137">Vá para Trabalhadores de registro de tempo.</span><span class="sxs-lookup"><span data-stu-id="7b33e-137">Go to Time registration workers.</span></span>
    * <span data-ttu-id="7b33e-138">Hora e atendimento > Configuração > Tempo de registro dos trabalhadores</span><span class="sxs-lookup"><span data-stu-id="7b33e-138">Time and attendance > Setup > Time registration workers</span></span>  
4. <span data-ttu-id="7b33e-139">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="7b33e-139">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="7b33e-140">Clique na guia Emprego.</span><span class="sxs-lookup"><span data-stu-id="7b33e-140">Click the Employment tab.</span></span>
6. <span data-ttu-id="7b33e-141">Expanda a seção de Tempo de registro.</span><span class="sxs-lookup"><span data-stu-id="7b33e-141">Expand the Time registration section.</span></span>
7. <span data-ttu-id="7b33e-142">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="7b33e-142">Click Edit.</span></span>
8. <span data-ttu-id="7b33e-143">No campo Contrato de pagamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7b33e-143">In the Pay agreement field, enter or select a value.</span></span>


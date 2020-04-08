---
title: Habilitar o processo de folha de pagamento para horário e presença
description: Este procedimento mostra como habilitar o processo de folha de pagamento de tempo e presença.
author: johanhoffmann
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgPayTable, JmgPayRate, JmgPayAgreementTable, JmgPayAgreementLine, HcmWorker
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2df4695b796b4e96e01fe5dac538b344cb76b910
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3146712"
---
# <a name="enable-the-payroll-process-for-time-and-attendance"></a><span data-ttu-id="1eb96-103">Habilitar o processo de folha de pagamento para horário e presença</span><span class="sxs-lookup"><span data-stu-id="1eb96-103">Enable the payroll process for time and attendance</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1eb96-104">Este procedimento mostra como habilitar o processo de folha de pagamento de tempo e presença.</span><span class="sxs-lookup"><span data-stu-id="1eb96-104">This procedure shows how to enable the payroll process for time and attendance.</span></span> <span data-ttu-id="1eb96-105">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="1eb96-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-pay-type-with-a-related-pay-rate"></a><span data-ttu-id="1eb96-106">Criar um tipo de pagamento com uma taxa de pagamento relacionada</span><span class="sxs-lookup"><span data-stu-id="1eb96-106">Create a pay type with a related pay rate</span></span>
1. <span data-ttu-id="1eb96-107">Hora e atendimento > Configuração > Folha de pagamento > Tipos de pagamento</span><span class="sxs-lookup"><span data-stu-id="1eb96-107">Time and attendance > Setup > Payroll > Pay types</span></span>
2. <span data-ttu-id="1eb96-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="1eb96-108">Click New.</span></span>
3. <span data-ttu-id="1eb96-109">No campo Tipo de pagamento, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="1eb96-109">In the Pay type field, type a value.</span></span>
4. <span data-ttu-id="1eb96-110">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="1eb96-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="1eb96-111">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="1eb96-111">Click Save.</span></span>
6. <span data-ttu-id="1eb96-112">Clique em Taxas.</span><span class="sxs-lookup"><span data-stu-id="1eb96-112">Click Rates.</span></span>
    * <span data-ttu-id="1eb96-113">As taxas para os tipos de pagamento são definidas para intervalos de tempo específicos e taxas individuais podem ser criadas para trabalhadores.</span><span class="sxs-lookup"><span data-stu-id="1eb96-113">Rates for pay types are set up for specific time intervals, and individual rates can be created for workers.</span></span> <span data-ttu-id="1eb96-114">Nem sempre é necessário criar taxas para tipos de pagamento em tempo e presença.</span><span class="sxs-lookup"><span data-stu-id="1eb96-114">It is not always necessary to create rates for pay types in time and attendance.</span></span> <span data-ttu-id="1eb96-115">Essas informações já podem existir no sistema de folha de pagamento usado na geração dos salários.</span><span class="sxs-lookup"><span data-stu-id="1eb96-115">This information may already exist in the payroll system that is used to generate wages.</span></span>  
7. <span data-ttu-id="1eb96-116">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="1eb96-116">Click New.</span></span>
8. <span data-ttu-id="1eb96-117">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="1eb96-117">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="1eb96-118">No campo Taxa, insira um número.</span><span class="sxs-lookup"><span data-stu-id="1eb96-118">In the Rate field, enter a number.</span></span>
10. <span data-ttu-id="1eb96-119">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="1eb96-119">Click Save.</span></span>

## <a name="create-a-pay-agreement"></a><span data-ttu-id="1eb96-120">Criar um contrato de pagamento</span><span class="sxs-lookup"><span data-stu-id="1eb96-120">Create a pay agreement</span></span>
1. <span data-ttu-id="1eb96-121">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1eb96-121">Close the page.</span></span>
2. <span data-ttu-id="1eb96-122">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1eb96-122">Close the page.</span></span>
3. <span data-ttu-id="1eb96-123">Vá para Contratos de pagamento.</span><span class="sxs-lookup"><span data-stu-id="1eb96-123">Go to Pay agreements.</span></span>
    * <span data-ttu-id="1eb96-124">Hora e atendimento > Configuração > Contratos de pagamento</span><span class="sxs-lookup"><span data-stu-id="1eb96-124">Time and attendance > Setup > Pay agreements</span></span>  
4. <span data-ttu-id="1eb96-125">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="1eb96-125">Click New.</span></span>
5. <span data-ttu-id="1eb96-126">No campo Contrato de pagamento, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="1eb96-126">In the Pay agreement field, type a value.</span></span>
6. <span data-ttu-id="1eb96-127">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="1eb96-127">In the Description field, type a value.</span></span>
7. <span data-ttu-id="1eb96-128">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="1eb96-128">Click Save.</span></span>
8. <span data-ttu-id="1eb96-129">Clique em Linhas de contrato.</span><span class="sxs-lookup"><span data-stu-id="1eb96-129">Click Agreement lines.</span></span>
9. <span data-ttu-id="1eb96-130">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="1eb96-130">Click New.</span></span>
10. <span data-ttu-id="1eb96-131">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="1eb96-131">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="1eb96-132">No campo Tipo de perfil, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="1eb96-132">In the Profile type field, enter or select a value.</span></span>
12. <span data-ttu-id="1eb96-133">No campo Tipo de pagamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="1eb96-133">In the Pay type field, enter or select a value.</span></span>

## <a name="set-up-pay-agreement-for-time-and-registration-worker"></a><span data-ttu-id="1eb96-134">Configurar o contrato de pagamento do funcionário por tempo e registro</span><span class="sxs-lookup"><span data-stu-id="1eb96-134">Set up pay agreement for time and registration worker</span></span>
1. <span data-ttu-id="1eb96-135">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1eb96-135">Close the page.</span></span>
2. <span data-ttu-id="1eb96-136">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1eb96-136">Close the page.</span></span>
3. <span data-ttu-id="1eb96-137">Vá para Trabalhadores de registro de tempo.</span><span class="sxs-lookup"><span data-stu-id="1eb96-137">Go to Time registration workers.</span></span>
    * <span data-ttu-id="1eb96-138">Hora e atendimento > Configuração > Tempo de registro dos trabalhadores</span><span class="sxs-lookup"><span data-stu-id="1eb96-138">Time and attendance > Setup > Time registration workers</span></span>  
4. <span data-ttu-id="1eb96-139">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="1eb96-139">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="1eb96-140">Clique na guia Emprego.</span><span class="sxs-lookup"><span data-stu-id="1eb96-140">Click the Employment tab.</span></span>
6. <span data-ttu-id="1eb96-141">Expanda a seção de Tempo de registro.</span><span class="sxs-lookup"><span data-stu-id="1eb96-141">Expand the Time registration section.</span></span>
7. <span data-ttu-id="1eb96-142">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="1eb96-142">Click Edit.</span></span>
8. <span data-ttu-id="1eb96-143">No campo Contrato de pagamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="1eb96-143">In the Pay agreement field, enter or select a value.</span></span>


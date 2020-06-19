---
title: Processo de qualificação para benefícios
description: Este procedimento mostra como funciona o processo de qualificação para benefícios.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysPolicyListPage, SysPolicy, HcmBenefitEligibilityPolicy, HcmBenefit, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: d23dcf4a16979b14ddf58b54e812f21e6698dfc7
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2020
ms.locfileid: "3430799"
---
# <a name="benefit-eligibility-process"></a><span data-ttu-id="8370e-103">Processo de qualificação para benefícios</span><span class="sxs-lookup"><span data-stu-id="8370e-103">Benefit eligibility process</span></span>

<span data-ttu-id="8370e-104">Este procedimento mostra como funciona o processo de qualificação para benefícios.</span><span class="sxs-lookup"><span data-stu-id="8370e-104">This procedure shows how the benefit eligibility process works.</span></span> <span data-ttu-id="8370e-105">Ao concluir o processo é possível exibir os resultados.</span><span class="sxs-lookup"><span data-stu-id="8370e-105">When the process is complete you can view the results.</span></span> <span data-ttu-id="8370e-106">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="8370e-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="8370e-107">Ir para Recursos humanos > Benefícios > Benefícios.</span><span class="sxs-lookup"><span data-stu-id="8370e-107">Go to Human resources > Benefits > Benefits.</span></span>
2. <span data-ttu-id="8370e-108">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="8370e-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="8370e-109">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="8370e-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="8370e-110">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="8370e-110">Click Edit.</span></span>
5. <span data-ttu-id="8370e-111">No campo Qualificação, selecione 'Baseado na regra'.</span><span class="sxs-lookup"><span data-stu-id="8370e-111">In the Eligibility field, select 'Rule based'.</span></span>
6. <span data-ttu-id="8370e-112">No campo Tipo de regra, selecione a regra de política de benefício que você deseja aplicar ao benefício.</span><span class="sxs-lookup"><span data-stu-id="8370e-112">In the Rule type field, select the benefit policy rule you would like applied to the benefit.</span></span>
7. <span data-ttu-id="8370e-113">No Painel de Ação, clique em Benefício.</span><span class="sxs-lookup"><span data-stu-id="8370e-113">On the Action Pane, click Benefit.</span></span>
8. <span data-ttu-id="8370e-114">Clique em Criar evento de qualificação para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="8370e-114">Click Create eligibility event to open the drop dialog.</span></span>
9. <span data-ttu-id="8370e-115">No campo Evento, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="8370e-115">In the Event field, type a value.</span></span>
10. <span data-ttu-id="8370e-116">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="8370e-116">In the Description field, type a value.</span></span>
11. <span data-ttu-id="8370e-117">No campo Tipo de evento, selecione 'Abrir a inscrição'.</span><span class="sxs-lookup"><span data-stu-id="8370e-117">In the Event type field, select 'Open enrollment'.</span></span>
12. <span data-ttu-id="8370e-118">No campo Data de início da cobertura, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="8370e-118">In the Coverage start date field, enter a date and time.</span></span>
13. <span data-ttu-id="8370e-119">No campo Data de início do período de inscrição, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="8370e-119">In the Enrollment period start date field, enter a date and time.</span></span>
14. <span data-ttu-id="8370e-120">No campo Dias até a inscrição, insira um número.</span><span class="sxs-lookup"><span data-stu-id="8370e-120">In the Days to enroll field, enter a number.</span></span>
15. <span data-ttu-id="8370e-121">Clique em Criar evento.</span><span class="sxs-lookup"><span data-stu-id="8370e-121">Click Create event.</span></span>
16. <span data-ttu-id="8370e-122">Clique em Adicionar na Guia Rápida Trabalhadores.</span><span class="sxs-lookup"><span data-stu-id="8370e-122">Click Add in the Workers FastTab.</span></span>
17. <span data-ttu-id="8370e-123">No campo Mostrar por tipo, selecione 'Funcionários'.</span><span class="sxs-lookup"><span data-stu-id="8370e-123">In the Show by type field, select 'Employees'.</span></span>
18. <span data-ttu-id="8370e-124">No campo Mostrar por entidade legal, selecione 'Entidade legal atual'.</span><span class="sxs-lookup"><span data-stu-id="8370e-124">In the Show by legal entity field, select 'Current legal entity'.</span></span>
19. <span data-ttu-id="8370e-125">Na lista, marque ou desmarque todas as linhas.</span><span class="sxs-lookup"><span data-stu-id="8370e-125">In the list, mark or unmark all rows.</span></span>
20. <span data-ttu-id="8370e-126">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="8370e-126">Click OK.</span></span>
21. <span data-ttu-id="8370e-127">Clique em Processo.</span><span class="sxs-lookup"><span data-stu-id="8370e-127">Click Process.</span></span>
22. <span data-ttu-id="8370e-128">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="8370e-128">Click OK.</span></span>
23. <span data-ttu-id="8370e-129">Atualize a página.</span><span class="sxs-lookup"><span data-stu-id="8370e-129">Refresh the page.</span></span>
24. <span data-ttu-id="8370e-130">Clique em Mostrar resultados.</span><span class="sxs-lookup"><span data-stu-id="8370e-130">Click Show results.</span></span>
25. <span data-ttu-id="8370e-131">Abra o filtro da coluna Status.</span><span class="sxs-lookup"><span data-stu-id="8370e-131">Open Status column filter.</span></span>
26. <span data-ttu-id="8370e-132">Classificar de A para Z</span><span class="sxs-lookup"><span data-stu-id="8370e-132">Sort A to Z</span></span>


---
title: Acumular planos de licença e ausência
description: Você pode acumular licenças e ausências no Dynamics 365 Human Resources para vários funcionários ou para uma pessoa.
author: andreabichsel
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 53c089da64f6b5f950a92afb9246454fb9a9686d
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800252"
---
# <a name="accrue-leave-and-absence-plans"></a><span data-ttu-id="9480b-103">Acumular planos de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="9480b-103">Accrue leave and absence plans</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="9480b-104">Você pode acumular licenças e ausências no Dynamics 365 Human Resources para vários funcionários ou para uma pessoa.</span><span class="sxs-lookup"><span data-stu-id="9480b-104">You can accrue leave and absence in Dynamics 365 Human Resources for multiple employees or for an individual.</span></span>

## <a name="accrue-leave-and-absence-for-multiple-employees"></a><span data-ttu-id="9480b-105">Acumular licenças e ausências para vários funcionários</span><span class="sxs-lookup"><span data-stu-id="9480b-105">Accrue leave and absence for multiple employees</span></span>

1. <span data-ttu-id="9480b-106">Na página **Licença e ausência**, selecione a guia **Links**.</span><span class="sxs-lookup"><span data-stu-id="9480b-106">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="9480b-107">Em **Gerenciar licença**, selecione **Acumular planos de licença e ausência**.</span><span class="sxs-lookup"><span data-stu-id="9480b-107">Under **Manage leave**, select **Accrue leave and absence plans**.</span></span>

3. <span data-ttu-id="9480b-108">A caixa de diálogo **Acumular planos de licença e ausência** é exibida.</span><span class="sxs-lookup"><span data-stu-id="9480b-108">The **Accrue leave and absence plans** dialog box appears.</span></span> <span data-ttu-id="9480b-109">Em **Acumular a partir de**, selecione **Data de hoje** ou selecione **Data personalizada** e insira uma data personalizada.</span><span class="sxs-lookup"><span data-stu-id="9480b-109">In **Accrue as of**, either select **Today's date** or select **Custom date** and enter a custom date.</span></span>

4. <span data-ttu-id="9480b-110">Se quiser executar competências para todas as empresas, selecione **Todas as empresas**.</span><span class="sxs-lookup"><span data-stu-id="9480b-110">If you want to run accruals for all companies, select **All companies**.</span></span> <span data-ttu-id="9480b-111">Se quiser processar competências para um único plano de licença, selecione **Não** para **Todos os planos** e selecione um **Plano de licença**.</span><span class="sxs-lookup"><span data-stu-id="9480b-111">If you want to process accruals for a single leave plan, select **No** for **All plans**, and then select a **Leave plan**.</span></span> <span data-ttu-id="9480b-112">Se selecionar todas as empresas, não poderá selecionar um plano de licença individual.</span><span class="sxs-lookup"><span data-stu-id="9480b-112">If you select all companies, you can't select an individual leave plan.</span></span> 

5. <span data-ttu-id="9480b-113">Se você deseja executar o processo de acúmulo em segundo plano, selecione **Executar em segundo plano** e execute as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="9480b-113">If you want to run the accrual process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="9480b-114">Insira informações para o processo de acúmulo.</span><span class="sxs-lookup"><span data-stu-id="9480b-114">Enter information for the accrual process.</span></span>

   2. <span data-ttu-id="9480b-115">Para configurar um trabalho recorrente, selecione **Recorrência**, insira as informações de recorrência e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="9480b-115">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="9480b-116">Para configurar um alerta de trabalho, selecione **Alertas**, selecione os alertas a receber e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="9480b-116">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="9480b-117">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="9480b-117">Select **OK**.</span></span> <span data-ttu-id="9480b-118">O processo de acúmulo será executado com os parâmetros definidos por você.</span><span class="sxs-lookup"><span data-stu-id="9480b-118">The accrual process will run with the parameters you set.</span></span>

## <a name="accrue-leave-and-absence-for-an-employee"></a><span data-ttu-id="9480b-119">Acumular licenças e ausências para um funcionário</span><span class="sxs-lookup"><span data-stu-id="9480b-119">Accrue leave and absence for an employee</span></span>

1. <span data-ttu-id="9480b-120">No registro do funcionário, selecione **Licença**.</span><span class="sxs-lookup"><span data-stu-id="9480b-120">On the employee's record, select **Leave**.</span></span>

2. <span data-ttu-id="9480b-121">Selecione **Acumular licenças e ausências**.</span><span class="sxs-lookup"><span data-stu-id="9480b-121">Select **Accrue leave and absence**.</span></span>

3. <span data-ttu-id="9480b-122">A caixa de diálogo **Acumular planos de licença e ausência** é exibida.</span><span class="sxs-lookup"><span data-stu-id="9480b-122">The **Accrue leave and absence plans** dialog box appears.</span></span> <span data-ttu-id="9480b-123">Em **Acumular a partir de**, selecione **Data de hoje** ou selecione **Data personalizada** e insira uma data personalizada.</span><span class="sxs-lookup"><span data-stu-id="9480b-123">In **Accrue as of**, either select **Today's date** or select **Custom date** and enter a custom date.</span></span>

4. <span data-ttu-id="9480b-124">Se quiser executar competências para todas as empresas, selecione **Todas as empresas**.</span><span class="sxs-lookup"><span data-stu-id="9480b-124">If you want to run accruals for all companies, select **All companies**.</span></span> <span data-ttu-id="9480b-125">Se quiser processar competências para um único plano de licença, selecione **Não** para **Todos os planos** e selecione um **Plano de licença**.</span><span class="sxs-lookup"><span data-stu-id="9480b-125">If you want to process accruals for a single leave plan, select **No** for **All plans**, and then select a **Leave plan**.</span></span> <span data-ttu-id="9480b-126">Se selecionar todas as empresas, não poderá selecionar um plano de licença individual.</span><span class="sxs-lookup"><span data-stu-id="9480b-126">If you select all companies, you can't select an individual leave plan.</span></span> 

5. <span data-ttu-id="9480b-127">Se você deseja executar o processo de acúmulo em segundo plano, selecione **Executar em segundo plano** e execute as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="9480b-127">If you want to run the accrual process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="9480b-128">Insira informações para o processo de acúmulo.</span><span class="sxs-lookup"><span data-stu-id="9480b-128">Enter information for the accrual process.</span></span>

   2. <span data-ttu-id="9480b-129">Para configurar um trabalho recorrente, selecione **Recorrência**, insira as informações de recorrência e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="9480b-129">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="9480b-130">Para configurar um alerta de trabalho, selecione **Alertas**, selecione os alertas a receber e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="9480b-130">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="9480b-131">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="9480b-131">Select **OK**.</span></span> <span data-ttu-id="9480b-132">O processo de acúmulo será executado com os parâmetros definidos por você.</span><span class="sxs-lookup"><span data-stu-id="9480b-132">The accrual process will run with the parameters you set.</span></span>

## <a name="delete-leave-and-absence-accruals-for-multiple-employees"></a><span data-ttu-id="9480b-133">Excluir acúmulos de licenças e ausências para vários funcionários</span><span class="sxs-lookup"><span data-stu-id="9480b-133">Delete leave and absence accruals for multiple employees</span></span>

<span data-ttu-id="9480b-134">Exclua os registros de acúmulo para um plano e um intervalo de datas específicos.</span><span class="sxs-lookup"><span data-stu-id="9480b-134">Delete accrual records for a specific plan and date range.</span></span> <span data-ttu-id="9480b-135">As datas de acúmulo devem ser datadas hoje ou no futuro.</span><span class="sxs-lookup"><span data-stu-id="9480b-135">Accrual dates must be dated today or in the future.</span></span>

1. <span data-ttu-id="9480b-136">Na página **Licença e ausência**, selecione a guia **Links**.</span><span class="sxs-lookup"><span data-stu-id="9480b-136">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="9480b-137">Em **Gerenciar licença**, selecione **Excluir acúmulos de plano de licença e ausência**.</span><span class="sxs-lookup"><span data-stu-id="9480b-137">Under **Manage leave**, select **Delete leave and absence plan accruals**.</span></span>

3. <span data-ttu-id="9480b-138">Na caixa de diálogo **Excluir competências do plano de licença e ausência**, selecione o **Plano de licença**.</span><span class="sxs-lookup"><span data-stu-id="9480b-138">In the **Delete leave and absence plan accruals** dialog box, select the **Leave plan**.</span></span> 

4. <span data-ttu-id="9480b-139">Se aplicável, escolha **Excluir ajustes de saldo**.</span><span class="sxs-lookup"><span data-stu-id="9480b-139">If applicable, choose **Delete balance adjustments**.</span></span>

5. <span data-ttu-id="9480b-140">Insira ou selecione uma **Data da competência de licença**.</span><span class="sxs-lookup"><span data-stu-id="9480b-140">Enter or select a **Leave accrual date**.</span></span> <span data-ttu-id="9480b-141">Essa data deve ser hoje ou futuramente.</span><span class="sxs-lookup"><span data-stu-id="9480b-141">This date has to be either today or in the future.</span></span> 

6. <span data-ttu-id="9480b-142">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="9480b-142">Select **OK**.</span></span> <span data-ttu-id="9480b-143">O processo de acúmulo excluirá acúmulos com os parâmetros definidos por você.</span><span class="sxs-lookup"><span data-stu-id="9480b-143">The accrual process will delete accruals with the parameters you set.</span></span> 

## <a name="delete-leave-and-absence-accruals-for-a-single-employee"></a><span data-ttu-id="9480b-144">Excluir acúmulos de licenças e ausências para um único funcionário</span><span class="sxs-lookup"><span data-stu-id="9480b-144">Delete leave and absence accruals for a single employee</span></span>

1. <span data-ttu-id="9480b-145">No registro do funcionário, selecione **Licença**.</span><span class="sxs-lookup"><span data-stu-id="9480b-145">On the employee's record, select **Leave**.</span></span>

2. <span data-ttu-id="9480b-146">Selecione **Excluir competências do plano de licença e ausência**.</span><span class="sxs-lookup"><span data-stu-id="9480b-146">Select **Delete leave and absence plan accruals**.</span></span>

3. <span data-ttu-id="9480b-147">Na caixa de diálogo **Excluir competências do plano de licença e ausência**, selecione o **Plano de licença**.</span><span class="sxs-lookup"><span data-stu-id="9480b-147">In the **Delete leave and absence plan accruals** dialog box, select **Leave plan**.</span></span> 

4. <span data-ttu-id="9480b-148">Se aplicável, escolha **Excluir ajustes de saldo**.</span><span class="sxs-lookup"><span data-stu-id="9480b-148">If applicable, choose **Delete balance adjustments**.</span></span>

5. <span data-ttu-id="9480b-149">Insira ou selecione uma **Data da competência de licença**.</span><span class="sxs-lookup"><span data-stu-id="9480b-149">Enter or select a **Leave accrual date**.</span></span> <span data-ttu-id="9480b-150">Essa data deve ser hoje ou futuramente.</span><span class="sxs-lookup"><span data-stu-id="9480b-150">This date must be either today or in the future.</span></span> 

6. <span data-ttu-id="9480b-151">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="9480b-151">Select **OK**.</span></span> <span data-ttu-id="9480b-152">O processo de acúmulo excluirá acúmulos com os parâmetros definidos por você.</span><span class="sxs-lookup"><span data-stu-id="9480b-152">The accrual process will delete accruals with the parameters you set.</span></span> 

## <a name="review-leave-accrual-and-deletion-processes"></a><span data-ttu-id="9480b-153">Revisar processos de acúmulo de licença e exclusão</span><span class="sxs-lookup"><span data-stu-id="9480b-153">Review leave accrual and deletion processes</span></span>

<span data-ttu-id="9480b-154">**Auditoria do acúmulo de folgas** é exibido cada vez que você executar ou excluir uma competência para um ou todos os funcionários.</span><span class="sxs-lookup"><span data-stu-id="9480b-154">**Leave accrual audit** displays each time you run or delete an accrual for one or all employees.</span></span> <span data-ttu-id="9480b-155">A data e a pessoa que executou a ação também são exibidas.</span><span class="sxs-lookup"><span data-stu-id="9480b-155">The date and person who performed the action also displays.</span></span>

1. <span data-ttu-id="9480b-156">Na página **Licença e ausência**, selecione a guia **Links**.</span><span class="sxs-lookup"><span data-stu-id="9480b-156">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="9480b-157">Em **Gerenciar licença**, selecione **Excluir auditoria de acúmulo de licença**.</span><span class="sxs-lookup"><span data-stu-id="9480b-157">Under **Manage leave**, select **Delete leave accrual audit**.</span></span>

## <a name="see-also"></a><span data-ttu-id="9480b-158">Consulte também</span><span class="sxs-lookup"><span data-stu-id="9480b-158">See also</span></span>

[<span data-ttu-id="9480b-159">Visão geral de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="9480b-159">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)</br>
[<span data-ttu-id="9480b-160">Criar um plano de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="9480b-160">Create a leave and absence plan</span></span>](hr-leave-and-absence-plans.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
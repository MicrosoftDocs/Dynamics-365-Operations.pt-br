---
title: Registrar consumo
description: Este tópico explica como registrar o consumo no Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 08/21/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderJournal, EntAssetWorkOrderAddSparePart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ea1522f8a8e4867d8d70fea59b493d139a1b01ef
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5020771"
---
# <a name="register-consumption"></a><span data-ttu-id="8e942-103">Registrar consumo</span><span class="sxs-lookup"><span data-stu-id="8e942-103">Register consumption</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="8e942-104">Quando um trabalho de manutenção tiver sido concluído em uma ordem de serviço, a próxima etapa será criar registros de consumo e lançar diários.</span><span class="sxs-lookup"><span data-stu-id="8e942-104">When a maintenance job has been completed on a work order, the next step is to make consumption registrations and post the journals.</span></span> <span data-ttu-id="8e942-105">Você pode criar registros nos seguintes tipos de consumo: horas, itens e despesas.</span><span class="sxs-lookup"><span data-stu-id="8e942-105">You can make registrations on the following consumption types: Hours, items, and expenses.</span></span> <span data-ttu-id="8e942-106">Os diferentes tipos de consumo são registrados e lançados na página **Diários de ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="8e942-106">The different consumption types are registered and posted on the **Work order journals** page.</span></span> <span data-ttu-id="8e942-107">A configuração de diário em **Gerenciamento de Ativos** é usada para criar e lançar diários separados para horas, itens e despesas no módulo **Gerenciamento e contabilidade de projeto**.</span><span class="sxs-lookup"><span data-stu-id="8e942-107">The journal setup in **Asset Management** is used for creating and posting separate journals for hours, items, and expenses in the **Project management and accounting** module.</span></span>

<span data-ttu-id="8e942-108">Em alguns casos, você pode adicionar ou excluir linhas de previsão em uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="8e942-108">In some cases, you may be able to add or delete forecast lines on a work order.</span></span> <span data-ttu-id="8e942-109">A configuração de um estado de ciclo de vida de ordem de serviço, o tipo de projeto relacionado e as regras de estágio relacionadas ao tipo de projeto determinam se você é capaz de adicionar ou editar linhas de diário.</span><span class="sxs-lookup"><span data-stu-id="8e942-109">The setup of a work order lifecycle state, the related project type, and the stage rules related to the project type determine if you are able to add or edit journal lines.</span></span> <span data-ttu-id="8e942-110">Leia mais sobre os estados de ciclo de vida da ordem de serviço e os estágios do projeto relacionados, consulte [Previsões, ordens de serviço e projetos](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="8e942-110">Read more about work order lifecycle states and related project stages in [Forecasts, work orders, and projects](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).</span></span>

>[!NOTE]
><span data-ttu-id="8e942-111">É possível configurar o lançamento automático de diários em um estado de ciclo de vida de ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="8e942-111">It is possible to set up automatic posting of journals on a work order lifecycle state.</span></span> <span data-ttu-id="8e942-112">Consulte [Estados de ciclo de vida de ordem de serviço](../setup-for-work-orders/work-order-lifecycle-states.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="8e942-112">Refer to [Work order lifecycle states](../setup-for-work-orders/work-order-lifecycle-states.md) for more information.</span></span>

1. <span data-ttu-id="8e942-113">Clique em **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**.</span><span class="sxs-lookup"><span data-stu-id="8e942-113">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="8e942-114">Selecione a ordem de serviço e clique em **Diários**.</span><span class="sxs-lookup"><span data-stu-id="8e942-114">Select the work order, and click **Journals**.</span></span>

3. <span data-ttu-id="8e942-115">Clique em **Copiar de previsão** para transferir todas as linhas de previsão que possam estar conectadas à ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="8e942-115">Click **Copy from forecast** to transfer any forecast lines that may be connected to the work order.</span></span> <span data-ttu-id="8e942-116">Você pode selecionar os tipos de consumo que deseja transferir.</span><span class="sxs-lookup"><span data-stu-id="8e942-116">You can select which consumption types you want to transfer.</span></span>

4. <span data-ttu-id="8e942-117">Se necessário, você poderá adicionar mais linhas de consumo à Guia Rápida clicando em **Adicionar linha** e preenchendo a linha com dados.</span><span class="sxs-lookup"><span data-stu-id="8e942-117">If necessary, you can add more consumption lines on the relevant FastTab by clicking **Add line** and filling out data on the line.</span></span>

5. <span data-ttu-id="8e942-118">Clique em **Validar diários** para validar as linhas de diário antes do lançamento.</span><span class="sxs-lookup"><span data-stu-id="8e942-118">Click **Validate journals** to validate the journal lines before posting.</span></span>

6. <span data-ttu-id="8e942-119">Clique em **Lançar diários** para lançar as linhas do diário.</span><span class="sxs-lookup"><span data-stu-id="8e942-119">Click **Post journals** to post the journal lines.</span></span>

7. <span data-ttu-id="8e942-120">Após ter lançado os diários de consumo, você pode atualizar o estado do ciclo de vida da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="8e942-120">After you've posted the consumption journals, you can update the work order lifecycle state.</span></span> <span data-ttu-id="8e942-121">Por exemplo, para indicar que a ordem de serviço for concluída, você pode atualizar o estado do ciclo de vida para "concluído".</span><span class="sxs-lookup"><span data-stu-id="8e942-121">For example, to indicate that the work order has been completed, you can update the lifecycle state to "Ended".</span></span>

    - <span data-ttu-id="8e942-122">No campo **Mostrar**, localizado na parte superior da página **Diários de ordem de serviço**, selecione quais linhas de diário você deseja ver: **Todos**, **Não lançados** ou **Lançados**.</span><span class="sxs-lookup"><span data-stu-id="8e942-122">In the **Show** field at the top of the **Work order journals** page, select which journal lines you want to see: **All**, **Not posted**, or **Posted**.</span></span> <span data-ttu-id="8e942-123">Os diários lançados têm uma marca de seleção na caixa de seleção **Lançados**.</span><span class="sxs-lookup"><span data-stu-id="8e942-123">Posted journals have a check mark in the **Posted** check box.</span></span>  
    - <span data-ttu-id="8e942-124">Quando linhas de item forem criadas no diário de ordem de serviço, as dimensões de produto e as dimensões de rastreamento relacionadas ao item serão automaticamente transferidas para a linha de diário.</span><span class="sxs-lookup"><span data-stu-id="8e942-124">When item lines are created in the work order journal, product dimensions and tracking dimensions related to the item are automatically transferred to the journal line.</span></span>  

<span data-ttu-id="8e942-125">A captura de tela a seguir mostra um exemplo de registros de hora e item em uma ordem de serviço em **Diários de ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="8e942-125">The screenshot below shows an example of hour and item registrations on a work order in **Work order journals**.</span></span>

![Figura 1](media/01-consumption.png)


## <a name="split-hours-on-work-orders-with-several-work-order-jobs"></a><span data-ttu-id="8e942-127">Horas divididas em ordens de serviço com vários trabalhos de ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="8e942-127">Split hours on work orders with several work order jobs</span></span>

<span data-ttu-id="8e942-128">Se uma ordem de serviço contiver vários trabalhos de ordem de serviço, você poderá registrar horas de trabalho usando a funcionalidade **Dividir horas**, o que significa que a linha de registro de uma hora pode ser distribuída uniformemente em cada trabalho de ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="8e942-128">If a work order contains several work order jobs, you can register work hours using the **Split hours** functionality, meaning one hour registration line can be distributed evenly on each work order job.</span></span>

1. <span data-ttu-id="8e942-129">Clique em **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**.</span><span class="sxs-lookup"><span data-stu-id="8e942-129">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="8e942-130">Selecione a ordem de serviço e clique em **Diários**.</span><span class="sxs-lookup"><span data-stu-id="8e942-130">Select the work order and click **Journals**.</span></span>

3. <span data-ttu-id="8e942-131">Selecione a linha de registro de hora que você deseja dividir e clique em **Dividir horas**.</span><span class="sxs-lookup"><span data-stu-id="8e942-131">Select the hour registration line you want to split, and click **Split hours**.</span></span>

4. <span data-ttu-id="8e942-132">No diálogo **Dividir horas em trabalhos de manutenção de ordem de serviço**, o nome do trabalhador conectado é automaticamente mostrado no campo **Trabalhador**.</span><span class="sxs-lookup"><span data-stu-id="8e942-132">In the **Split hours on work order maintenance jobs** dialog, the name of the worker who is logged in is automatically shown in the **Worker** field.</span></span> <span data-ttu-id="8e942-133">Se necessário, você pode selecionar outro trabalhador.</span><span class="sxs-lookup"><span data-stu-id="8e942-133">If required, you can select another worker.</span></span>

5. <span data-ttu-id="8e942-134">Selecione uma categoria para o registro de horas no campo **Categoria**.</span><span class="sxs-lookup"><span data-stu-id="8e942-134">Select a category for the hour registration in the **Category** field.</span></span>

6. <span data-ttu-id="8e942-135">Insira o número de horas de trabalho a serem divididas no campo **Horas**.</span><span class="sxs-lookup"><span data-stu-id="8e942-135">Insert number of work hours to be split in the **Hours** field.</span></span>

    ![Figura 2](media/02-consumption.png)

7. <span data-ttu-id="8e942-137">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8e942-137">Click **OK**.</span></span>

<span data-ttu-id="8e942-138">*Exemplo:* na captura de tela a seguir, as linhas de diário para uma ordem de serviço com três trabalhos de ordem de serviço são mostradas.</span><span class="sxs-lookup"><span data-stu-id="8e942-138">*Example:* In the screenshot below, journal lines for a work order containing three work order jobs are shown.</span></span> <span data-ttu-id="8e942-139">A primeira linha, com três horas de trabalho, foi dividida e uma hora de trabalho é registrada em cada trabalho de ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="8e942-139">The first line, containing three work hours, has been split, and one work hour is registered on each work order job.</span></span> <span data-ttu-id="8e942-140">Depois que as três linhas de registro de hora tiverem sido criadas, você decidirá o que fazer com a linha de registro de hora original (a primeira linha, no exemplo).</span><span class="sxs-lookup"><span data-stu-id="8e942-140">After the three hour registration lines have been created, you decide what to do with the original hour registration line (the first line in the example).</span></span> <span data-ttu-id="8e942-141">É possível mantê-la como está ou excluí-la.</span><span class="sxs-lookup"><span data-stu-id="8e942-141">You can keep it as is or delete it.</span></span> 

![Figura 3](media/03-consumption.png)

## <a name="financial-dimensions-on-consumption-registrations"></a><span data-ttu-id="8e942-143">Dimensões financeiras em registros de consumo</span><span class="sxs-lookup"><span data-stu-id="8e942-143">Financial dimensions on consumption registrations</span></span>

<span data-ttu-id="8e942-144">Quando você cria registros de consumo, as dimensões financeiras relacionados a diferentes tipos de registro serão adicionadas aos registros em uma sequência específica.</span><span class="sxs-lookup"><span data-stu-id="8e942-144">When you make consumption registrations, financial dimensions related to the different registration types are added to the registrations in a specific sequence.</span></span> 

- <span data-ttu-id="8e942-145">*Registros de Horas e Despesas:* primeiro, as dimensões financeiras do cabeçalho de diário são adicionadas, se houver.</span><span class="sxs-lookup"><span data-stu-id="8e942-145">*Hour and Expense registrations:* First, financial dimensions from the journal header are added, if any.</span></span> <span data-ttu-id="8e942-146">Em seguida, as dimensões financeiras do projeto de ordem de serviço relacionado são adicionadas.</span><span class="sxs-lookup"><span data-stu-id="8e942-146">Next, financial dimensions from the related work order project are added.</span></span> <span data-ttu-id="8e942-147">Por fim, as dimensões financeiras do recurso (trabalhador) são adicionadas.</span><span class="sxs-lookup"><span data-stu-id="8e942-147">Finally, financial dimensions from the resource (worker) are added.</span></span>

- <span data-ttu-id="8e942-148">*Registros de Item:* primeiro, as dimensões financeiras do cabeçalho de diário são adicionadas, se houver.</span><span class="sxs-lookup"><span data-stu-id="8e942-148">*Item registrations:* First, financial dimensions from the journal header are added, if any.</span></span> <span data-ttu-id="8e942-149">Então, as dimensões financeiras do projeto de ordem de serviço relacionado são adicionadas.</span><span class="sxs-lookup"><span data-stu-id="8e942-149">Then, financial dimensions from the related work order project are added.</span></span> <span data-ttu-id="8e942-150">Em seguida, as dimensões financeiras do site são adicionadas.</span><span class="sxs-lookup"><span data-stu-id="8e942-150">Next, financial dimensions from the site are added.</span></span> <span data-ttu-id="8e942-151">Por fim, as dimensões financeiras do item são adicionadas.</span><span class="sxs-lookup"><span data-stu-id="8e942-151">Finally, financial dimensions from the item are added.</span></span>

>[!NOTE]
><span data-ttu-id="8e942-152">Para todos os três tipos de registro, a combinação de dimensão financeira é validada, e as combinações inválidas são anuladas.</span><span class="sxs-lookup"><span data-stu-id="8e942-152">For all three registration types, the financial dimension combination is validated, and invalid combinations are blanked.</span></span> <span data-ttu-id="8e942-153">Esta é a configuração padrão com outros aplicativos do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8e942-153">This is standard setup with other Finance and Operations apps.</span></span>


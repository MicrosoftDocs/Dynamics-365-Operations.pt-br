---
title: Processar alterações de taxa
description: Processe alterações na taxa de benefícios no Microsoft Dynamics 365 Human Resources quando um plano de benefícios novo ou existente tiver uma alteração nas configurações da regra de qualificação.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9ebe5cfc2bdf7790770d27ece2dc67f7677db593
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008049"
---
# <a name="process-rate-changes"></a><span data-ttu-id="533d1-103">Processar alterações de taxa</span><span class="sxs-lookup"><span data-stu-id="533d1-103">Process rate changes</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="533d1-104">Processe alterações na taxa de benefícios no Microsoft Dynamics 365 Human Resources quando um plano de benefícios novo ou existente tiver uma alteração nas configurações da regra de qualificação.</span><span class="sxs-lookup"><span data-stu-id="533d1-104">Process benefit rate changes in Microsoft Dynamics 365 Human Resources when a new or existing benefit plan has a change in eligibility rule settings.</span></span> <span data-ttu-id="533d1-105">Se uma nova regra de qualificação for criada e atribuída ao plano, isso fará com que o sistema execute novamente a qualificação do trabalhador de modo a verificar se agora ele pode estar qualificado para o plano com base nas novas opções de qualificação.</span><span class="sxs-lookup"><span data-stu-id="533d1-105">If a new eligibility rule is created and assigned to the plan, this prompts the system to re-run worker eligibility to check if workers may now be eligible for the plan based on new eligibility options.</span></span> 

1. <span data-ttu-id="533d1-106">No espaço de trabalho **Gerenciamento de benefícios**, em **Processando**, selecione **Processamento de atualização de alteração de taxa**.</span><span class="sxs-lookup"><span data-stu-id="533d1-106">In the **Benefits management** workspace, under **Processing**, select **Rate change update processing**.</span></span>

2. <span data-ttu-id="533d1-107">No caixa de diálogo **Executar processo de atualização de taxa de benefício**, especifique valores para os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="533d1-107">In the **Run benefit rate update process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="533d1-108">Campo</span><span class="sxs-lookup"><span data-stu-id="533d1-108">Field</span></span> | <span data-ttu-id="533d1-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="533d1-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="533d1-110">Período de inscrição</span><span class="sxs-lookup"><span data-stu-id="533d1-110">Enrollment period</span></span> | <span data-ttu-id="533d1-111">O período de inscrição para processar alterações de taxa.</span><span class="sxs-lookup"><span data-stu-id="533d1-111">The enrollment period to process rate changes for.</span></span> |

3. <span data-ttu-id="533d1-112">Se você deseja executar o processo em segundo plano, selecione **Executar em segundo plano** e execute as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="533d1-112">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="533d1-113">Insira informações para o processo.</span><span class="sxs-lookup"><span data-stu-id="533d1-113">Enter information for the process.</span></span>

   2. <span data-ttu-id="533d1-114">Para configurar um trabalho recorrente, selecione **Recorrência**, insira as informações de recorrência e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="533d1-114">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="533d1-115">Para configurar um alerta de trabalho, selecione **Alertas**, selecione os alertas a receber e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="533d1-115">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="533d1-116">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="533d1-116">Select **OK**.</span></span> <span data-ttu-id="533d1-117">O processo será executado com os parâmetros definidos por você.</span><span class="sxs-lookup"><span data-stu-id="533d1-117">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="533d1-118">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="533d1-118">Select **OK**.</span></span>

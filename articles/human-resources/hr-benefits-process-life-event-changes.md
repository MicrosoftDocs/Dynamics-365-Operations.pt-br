---
title: Processar alterações de eventos de vida
description: Processe alterações de eventos de vida no Microsoft Dynamics 365 Human Resources para alterações de eventos de vida.
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
ms.openlocfilehash: f9bce9394a361bbecfcc0531c5d7ebe9302c8f11
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008103"
---
# <a name="process-life-event-changes"></a><span data-ttu-id="261f1-103">Processar alterações de eventos de vida</span><span class="sxs-lookup"><span data-stu-id="261f1-103">Process life event changes</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="261f1-104">Processe alterações de eventos de vida no Microsoft Dynamics 365 Human Resources para duas alterações de eventos de vida:</span><span class="sxs-lookup"><span data-stu-id="261f1-104">Process life event changes in Microsoft Dynamics 365 Human Resources for two life event changes:</span></span>

- <span data-ttu-id="261f1-105">Alterações de aniversário</span><span class="sxs-lookup"><span data-stu-id="261f1-105">Birthday changes</span></span>
- <span data-ttu-id="261f1-106">A regra de qualificação substitui as alterações de expiração</span><span class="sxs-lookup"><span data-stu-id="261f1-106">Eligibility rule override expiration changes</span></span> 

1. <span data-ttu-id="261f1-107">No espaço de trabalho **Gerenciamento de benefícios**, em **Processando**, selecione **Processamento da alteração de eventos de vida**.</span><span class="sxs-lookup"><span data-stu-id="261f1-107">In the **Benefits management** workspace, under **Processing**, select **Life event change processing**.</span></span>

2. <span data-ttu-id="261f1-108">No caixa de diálogo **Executar o processamento da alteração de eventos de vida**, especifique valores para os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="261f1-108">In the **Run life event change process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="261f1-109">Campo</span><span class="sxs-lookup"><span data-stu-id="261f1-109">Field</span></span> | <span data-ttu-id="261f1-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="261f1-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="261f1-111">Período de inscrição</span><span class="sxs-lookup"><span data-stu-id="261f1-111">Enrollment period</span></span> | <span data-ttu-id="261f1-112">O período de inscrição para processar as alterações de eventos de vida.</span><span class="sxs-lookup"><span data-stu-id="261f1-112">The enrollment period to process life event changes for.</span></span> |
   | <span data-ttu-id="261f1-113">Pessoa jurídica em geral</span><span class="sxs-lookup"><span data-stu-id="261f1-113">Legal entity</span></span> | <span data-ttu-id="261f1-114">A entidade legal para processar alterações de eventos de vida.</span><span class="sxs-lookup"><span data-stu-id="261f1-114">The legal entity to process life event changes for.</span></span> |

3. <span data-ttu-id="261f1-115">Se você deseja executar o processo em segundo plano, selecione **Executar em segundo plano** e execute as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="261f1-115">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="261f1-116">Insira informações para o processo.</span><span class="sxs-lookup"><span data-stu-id="261f1-116">Enter information for the process.</span></span>

   2. <span data-ttu-id="261f1-117">Para configurar um trabalho recorrente, selecione **Recorrência**, insira as informações de recorrência e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="261f1-117">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="261f1-118">Para configurar um alerta de trabalho, selecione **Alertas**, selecione os alertas a receber e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="261f1-118">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="261f1-119">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="261f1-119">Select **OK**.</span></span> <span data-ttu-id="261f1-120">O processo será executado com os parâmetros definidos por você.</span><span class="sxs-lookup"><span data-stu-id="261f1-120">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="261f1-121">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="261f1-121">Select **OK**.</span></span>

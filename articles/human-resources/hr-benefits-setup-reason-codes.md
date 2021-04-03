---
title: Configurar códigos de motivo
description: O Dynamics 365 Human Resources usa códigos de motivo para explicar por que os benefícios de um funcionário estão mudando.
author: andreabichsel
manager: tfehr
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c799a81f38a5dbd5996afbda9529fa83d7fe5cf9
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5468386"
---
# <a name="set-up-reason-codes"></a><span data-ttu-id="c6784-103">Configurar códigos de motivo</span><span class="sxs-lookup"><span data-stu-id="c6784-103">Set up reason codes</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="c6784-104">O Dynamics 365 Human Resources usa códigos de motivo para explicar por que os benefícios de um funcionário estão mudando.</span><span class="sxs-lookup"><span data-stu-id="c6784-104">Dynamics 365 Human Resources uses reason codes to explain why an employee’s benefits are changing.</span></span>

> [!NOTE]
> <span data-ttu-id="c6784-105">Desde janeiro de 2021, os códigos de motivo estão migrando para o espaço de trabalho **Gerenciamento de pessoal** em vez do espaço de trabalho **Gerenciamento de benefícios**.</span><span class="sxs-lookup"><span data-stu-id="c6784-105">As of January 2021, reason codes are migrating to the **Personnel management** workspace instead of the **Benefits management** workspace.</span></span> <span data-ttu-id="c6784-106">Para obter mais informações, consulte [Migrar manualmente códigos de motivo para gerenciamento de pessoal](hr-benefits-setup-reason-codes.md#manually-migrate-reason-codes-to-personnel-management).</span><span class="sxs-lookup"><span data-stu-id="c6784-106">For more information, see [Manually migrate reason codes to Personnel management](hr-benefits-setup-reason-codes.md#manually-migrate-reason-codes-to-personnel-management).</span></span>

## <a name="create-reason-codes"></a><span data-ttu-id="c6784-107">Criar códigos de motivo</span><span class="sxs-lookup"><span data-stu-id="c6784-107">Create reason codes</span></span>

1. <span data-ttu-id="c6784-108">No espaço de trabalho **Gerenciamento de pessoal** (ou espaço de trabalho **Gerenciamento de benefícios** se os códigos de motivo ainda não tiverem sido migrados), selecione **Links** e, depois, **Códigos de motivo**.</span><span class="sxs-lookup"><span data-stu-id="c6784-108">In the **Personnel management** workspace (or **Benefits management** workspace if your reason codes haven't yet migrated), select **Links**, and then select **Reason codes**.</span></span>

2. <span data-ttu-id="c6784-109">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c6784-109">Select **New**.</span></span>

3. <span data-ttu-id="c6784-110">Especifique valores para os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="c6784-110">Specify values for the following fields:</span></span>

   | <span data-ttu-id="c6784-111">Campo</span><span class="sxs-lookup"><span data-stu-id="c6784-111">Field</span></span> | <span data-ttu-id="c6784-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="c6784-112">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="c6784-113">**Código de motivo**</span><span class="sxs-lookup"><span data-stu-id="c6784-113">**Reason code**</span></span> | <span data-ttu-id="c6784-114">Um nome exclusivo para identificar o motivo pelo qual um funcionário alteraria um registro de plano de benefícios.</span><span class="sxs-lookup"><span data-stu-id="c6784-114">A unique name to identify the reason an employee would change a benefit plan enrollment.</span></span> |
   | <span data-ttu-id="c6784-115">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="c6784-115">**Description**</span></span> | <span data-ttu-id="c6784-116">Uma descrição do código de motivo.</span><span class="sxs-lookup"><span data-stu-id="c6784-116">A description of the reason code.</span></span> |

4. <span data-ttu-id="c6784-117">Em **Cenários aplicáveis**, defina **Gerenciamento de benefícios** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="c6784-117">Under **Applicable scenarios**, set **Benefits management** to **Yes**.</span></span> <span data-ttu-id="c6784-118">(Não aplicável se os códigos de motivo ainda não tiverem migrado para o espaço de trabalho **Gerenciamento de pessoal**.)</span><span class="sxs-lookup"><span data-stu-id="c6784-118">(Not applicable if your reason codes haven't yet migrated to the **Personnel management** workspace.)</span></span>

5. <span data-ttu-id="c6784-119">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c6784-119">Select **Save**.</span></span>

## <a name="manually-migrate-reason-codes-to-personnel-management"></a><span data-ttu-id="c6784-120">Migrar manualmente códigos de motivo para Gerenciamento de pessoal</span><span class="sxs-lookup"><span data-stu-id="c6784-120">Manually migrate reason codes to Personnel management</span></span>

<span data-ttu-id="c6784-121">Em janeiro de 2021, os códigos de motivo migraram para o espaço de trabalho **Gerenciamento de pessoal** em vez do espaço de trabalho **Gerenciamento de benefícios**.</span><span class="sxs-lookup"><span data-stu-id="c6784-121">In January 2021, reason codes are migrating to the **Personnel management** workspace instead of the **Benefits management** workspace.</span></span> <span data-ttu-id="c6784-122">A maioria dos dados de código de motivo migrarão automaticamente no seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="c6784-122">Most reason code data will automatically migrate in your environment.</span></span> <span data-ttu-id="c6784-123">Alguns dados do código de motivo talvez não migrem.</span><span class="sxs-lookup"><span data-stu-id="c6784-123">Some reason code data might not migrate.</span></span> <span data-ttu-id="c6784-124">Por exemplo, os códigos de motivo agora têm no máximo 15 caracteres; portanto, qualquer código de motivo com mais de 15 caracteres não migrará automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c6784-124">For example, reason codes now have a 15-character maximum, so any reason codes longer than 15 characters won't migrate automatically.</span></span>

<span data-ttu-id="c6784-125">Você verá uma faixa na página **Links** do espaço de trabalho **Gerenciamento de benefícios** informando sobre a migração e se algum código de motivo não foi migrado.</span><span class="sxs-lookup"><span data-stu-id="c6784-125">You'll see a banner on the **Links** page of the **Benefits management** workspace informing you about the migration and whether any reason codes didn't migrate.</span></span>

1. <span data-ttu-id="c6784-126">Selecione **Códigos de motivo** para obter detalhes sobre o status da migração.</span><span class="sxs-lookup"><span data-stu-id="c6784-126">Select **Reason codes** for details about migration status.</span></span>

   <span data-ttu-id="c6784-127">[![Códigos de motivo](./media/hr-benefits-setup-reason-codes-link.png)](./media/hr-benefits-setup-reason-codes-link.png)</span><span class="sxs-lookup"><span data-stu-id="c6784-127">[![Reason codes](./media/hr-benefits-setup-reason-codes-link.png)](./media/hr-benefits-setup-reason-codes-link.png)</span></span>

2. <span data-ttu-id="c6784-128">Selecione um código de motivo que falhou na migração.</span><span class="sxs-lookup"><span data-stu-id="c6784-128">Select a reason code that failed to migrate.</span></span>

   <span data-ttu-id="c6784-129">[![Status da migração do código de motivo](./media/hr-benefits-setup-reason-codes-status.png)](./media/hr-benefits-setup-reason-codes-status.png)</span><span class="sxs-lookup"><span data-stu-id="c6784-129">[![Reason code migration status](./media/hr-benefits-setup-reason-codes-status.png)](./media/hr-benefits-setup-reason-codes-status.png)</span></span>

3. <span data-ttu-id="c6784-130">Selecione **Migrar código de motivo**.</span><span class="sxs-lookup"><span data-stu-id="c6784-130">Select **Migrate reason code**.</span></span>

   <span data-ttu-id="c6784-131">[![Migrar código de motivo](./media/hr-benefits-setup-reason-codes-migrate.png)](./media/hr-benefits-setup-reason-codes-migrate.png)</span><span class="sxs-lookup"><span data-stu-id="c6784-131">[![Migrate reason code](./media/hr-benefits-setup-reason-codes-migrate.png)](./media/hr-benefits-setup-reason-codes-migrate.png)</span></span>

4. <span data-ttu-id="c6784-132">No painel **Migração de código de motivo do benefício**, você tem duas opções para mapear um código de motivo de Gerenciamento de pessoal:</span><span class="sxs-lookup"><span data-stu-id="c6784-132">In the **Benefit reason code migration** pane, you have two options for mapping to a Personnel management reason code:</span></span>

   - <span data-ttu-id="c6784-133">Para usar um código de motivo existente em Gerenciamento de pessoal, escolha um no menu suspenso **Usar código de motivo existente**.</span><span class="sxs-lookup"><span data-stu-id="c6784-133">To use an existing reason code in Personnel management, choose one from the **Use existing reason code** dropdown.</span></span>
     > [!NOTE]
     > <span data-ttu-id="c6784-134">Só será possível usar um código de motivo existente no Gerenciamento de pessoal se outro código de motivo de Gerenciamento de benefícios ainda não tiver migrado para ele.</span><span class="sxs-lookup"><span data-stu-id="c6784-134">You can only use an existing reason code in Personnel management if another Benefits management reason code hasn't already migrated to it.</span></span>
   - <span data-ttu-id="c6784-135">Para criar um novo código de motivo no Gerenciamento de pessoal, insira um novo em **Novo código de motivo** e, depois, insira uma descrição em **Nova descrição**.</span><span class="sxs-lookup"><span data-stu-id="c6784-135">To create a new reason code in Personnel management, enter a new one in **New reason code**, and then enter a description in **New description**.</span></span>

   <span data-ttu-id="c6784-136">[![Mapear para um código de motivo de Gerenciamento de pessoal](./media/hr-benefits-setup-reason-codes-mapping.png)](./media/hr-benefits-setup-reason-codes-mapping.png)</span><span class="sxs-lookup"><span data-stu-id="c6784-136">[![Map to a Personnel management reason code](./media/hr-benefits-setup-reason-codes-mapping.png)](./media/hr-benefits-setup-reason-codes-mapping.png)</span></span>

<span data-ttu-id="c6784-137">Depois que os códigos de motivo migram para o Gerenciamento de pessoal, a opção para usá-los no Gerenciamento de benefícios é definida automaticamente como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="c6784-137">After reason codes migrate to Personnel management, the option for using them in Benefits management is automatically set to **Yes**.</span></span>

<span data-ttu-id="c6784-138">[![Usar código de motivo em Gerenciamento de benefícios](./media/hr-benefits-setup-reason-codes-use.png)](./media/hr-benefits-setup-reason-codes-use.png)</span><span class="sxs-lookup"><span data-stu-id="c6784-138">[![Use reason code in Benefits management](./media/hr-benefits-setup-reason-codes-use.png)](./media/hr-benefits-setup-reason-codes-use.png)</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
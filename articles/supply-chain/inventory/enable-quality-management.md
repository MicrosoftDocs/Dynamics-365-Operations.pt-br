---
title: Habilitar gerenciamento de qualidade e não conformidade
description: Este tópico fornece uma visão geral do processo de configuração de recursos de gerenciamento de qualidade e não conformidade no Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestAssociationTable, InventTestGroup, InventTestItemQualityGroup, InventTestTable, InventTestVariable, InventTestVariableOutcome, InventParameters, InventProblemType, InventProblemTypeSetup, InventQuarantineZone, InventTestDiagnosticType, InventTestReportSetup, SysUserManagement, InventTestRelatedOperations
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 67d5da648e31d07d054246f5d308a6c6cdeb506c
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956245"
---
# <a name="enable-quality-and-nonconformance-management"></a><span data-ttu-id="62161-103">Habilitar gerenciamento de qualidade e não conformidade</span><span class="sxs-lookup"><span data-stu-id="62161-103">Enable quality and nonconformance management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="62161-104">Este tópico fornece uma visão geral do processo de configuração de recursos de gerenciamento de qualidade e não conformidade no Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="62161-104">This topic provides an overview of the process for setting up and configuring quality and nonconformance management features in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="enable-quality-and-nonconformance-management"></a><a name="enable-qm"></a><span data-ttu-id="62161-105">Habilitar gerenciamento de qualidade e não conformidade</span><span class="sxs-lookup"><span data-stu-id="62161-105">Enable quality and nonconformance management</span></span>

<span data-ttu-id="62161-106">Siga estas etapas para habilitar o gerenciamento de qualidade no sistema.</span><span class="sxs-lookup"><span data-stu-id="62161-106">Follow these steps to enable quality management on your system.</span></span>

1. <span data-ttu-id="62161-107">Ir para **Gerenciamento de estoque \> Configuração \> Parâmetros de gerenciamento de depósito e estoque**.</span><span class="sxs-lookup"><span data-stu-id="62161-107">Go to **Inventory management \> Setup \> Inventory and warehouse management parameters**.</span></span>
1. <span data-ttu-id="62161-108">Na guia **Gerenciamento de qualidade**, defina a opção **Usar gerenciamento de qualidade** como *Sim*.</span><span class="sxs-lookup"><span data-stu-id="62161-108">On the **Quality management** tab, set the **Use quality management** option to *Yes*.</span></span>
1. <span data-ttu-id="62161-109">No campo **Preço por hora**, insira um preço de mão de obra por hora na moeda local.</span><span class="sxs-lookup"><span data-stu-id="62161-109">In the **Hourly rate** field, enter an hourly labor rate in the local currency.</span></span> <span data-ttu-id="62161-110">O preço por hora é usado para calcular o custo de operações relacionadas à não conformidade.</span><span class="sxs-lookup"><span data-stu-id="62161-110">The hourly rate is used to calculate costs for operations that are related to a nonconformance.</span></span> <span data-ttu-id="62161-111">O preço por hora e os custos calculados fornecem informações de referência para uma não conformidade.</span><span class="sxs-lookup"><span data-stu-id="62161-111">The hourly rate and calculated costs provide reference information for a nonconformance.</span></span> <span data-ttu-id="62161-112">Eles não interagem com outra funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="62161-112">They don't interact with other functionality.</span></span>
1. <span data-ttu-id="62161-113">Selecione **Configuração de relatório**.</span><span class="sxs-lookup"><span data-stu-id="62161-113">Select **Report setup**.</span></span>
1. <span data-ttu-id="62161-114">Adicione novas linhas para os vários tipos de relatório e selecione o tipo de documento a ser usado para cada relatório.</span><span class="sxs-lookup"><span data-stu-id="62161-114">Add new lines for the various report types, and select the type of document to use for each report.</span></span>
1. <span data-ttu-id="62161-115">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="62161-115">Close the page.</span></span>
1. <span data-ttu-id="62161-116">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="62161-116">Close the page.</span></span>

## <a name="quality-management-configuration-process"></a><span data-ttu-id="62161-117">Processo de configuração de gerenciamento de qualidade</span><span class="sxs-lookup"><span data-stu-id="62161-117">Quality management configuration process</span></span>

<span data-ttu-id="62161-118">Antes de começar a usar os recursos de gerenciamento de qualidade e gerar ordens de qualidade, você deve configurar o sistema e os pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="62161-118">Before you can start to use the quality management features and generate quality orders, you must configure the system and prerequisites.</span></span> <span data-ttu-id="62161-119">Esta é uma lista das etapas necessárias para configurar o gerenciamento de qualidade.</span><span class="sxs-lookup"><span data-stu-id="62161-119">Here is a list of the steps that are required to configure quality management.</span></span>

1. <span data-ttu-id="62161-120">[Habilitar gerenciamento de qualidade e não conformidade](#enable-qm).</span><span class="sxs-lookup"><span data-stu-id="62161-120">[Enable quality and nonconformance management](#enable-qm).</span></span>
1. <span data-ttu-id="62161-121">Opcional: [Configurar instrumentos de teste](quality-test-instruments.md).</span><span class="sxs-lookup"><span data-stu-id="62161-121">Optional: [Configure test instruments](quality-test-instruments.md).</span></span>
1. <span data-ttu-id="62161-122">[Configurar testes](quality-tests.md).</span><span class="sxs-lookup"><span data-stu-id="62161-122">[Configure tests](quality-tests.md).</span></span>
1. <span data-ttu-id="62161-123">[Configurar variáveis e resultados de teste](quality-test-variables.md).</span><span class="sxs-lookup"><span data-stu-id="62161-123">[Configure test variables and outcomes](quality-test-variables.md).</span></span>
1. <span data-ttu-id="62161-124">[Configurar grupos de teste](quality-test-groups.md).</span><span class="sxs-lookup"><span data-stu-id="62161-124">[Configure test groups](quality-test-groups.md).</span></span>
1. <span data-ttu-id="62161-125">Opcional: [Configurar grupos de qualidade e vincular a produtos](quality-groups.md).</span><span class="sxs-lookup"><span data-stu-id="62161-125">Optional: [Configure quality groups, and link to products](quality-groups.md).</span></span>
1. <span data-ttu-id="62161-126">Opcional: [Configurar associações de qualidade](quality-associations.md).</span><span class="sxs-lookup"><span data-stu-id="62161-126">Optional: [Configure quality associations](quality-associations.md).</span></span>

<span data-ttu-id="62161-127">Depois de concluída a configuração, você pode começar a criar e processar ordens de qualidade.</span><span class="sxs-lookup"><span data-stu-id="62161-127">After the configuration is completed, you can start to create and process quality orders.</span></span> <span data-ttu-id="62161-128">Para obter mais informações sobre como criar e trabalhar com ordens de qualidade, consulte [Ordens de qualidade](quality-orders.md).</span><span class="sxs-lookup"><span data-stu-id="62161-128">For more information about how to create and work with quality orders, see [Quality orders](quality-orders.md).</span></span>

## <a name="nonconformance-management-configuration-process"></a><span data-ttu-id="62161-129">Processo de configuração de gerenciamento de não conformidade</span><span class="sxs-lookup"><span data-stu-id="62161-129">Nonconformance management configuration process</span></span>

<span data-ttu-id="62161-130">Antes de começar a usar os recursos de gerenciamento de não conformidade e gerar não conformidades, você deve configurar o sistema e os pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="62161-130">Before you can start to use the nonconformance management features and generate nonconformances, you must configure the system and prerequisites.</span></span> <span data-ttu-id="62161-131">Esta é uma lista das etapas necessárias para configurar o gerenciamento de não conformidade.</span><span class="sxs-lookup"><span data-stu-id="62161-131">Here is a list of the steps that are required to configure nonconformance management.</span></span>

1. <span data-ttu-id="62161-132">[Habilitar gerenciamento de qualidade e não conformidade](#enable-qm).</span><span class="sxs-lookup"><span data-stu-id="62161-132">[Enable quality and nonconformance management](#enable-qm).</span></span>
1. <span data-ttu-id="62161-133">[Configurar trabalhadores que são responsáveis por aprovar não conformidades](quality-responsible-workers.md).</span><span class="sxs-lookup"><span data-stu-id="62161-133">[Configure workers who are responsible for approving nonconformances](quality-responsible-workers.md).</span></span>
1. <span data-ttu-id="62161-134">[Configurar tipos de problema](quality-problem-types.md).</span><span class="sxs-lookup"><span data-stu-id="62161-134">[Configure problem types](quality-problem-types.md).</span></span>
1. <span data-ttu-id="62161-135">[Configurar zonas de quarentena](quality-quarantine-zones.md).</span><span class="sxs-lookup"><span data-stu-id="62161-135">[Configure quarantine zones](quality-quarantine-zones.md).</span></span>
1. <span data-ttu-id="62161-136">[Configurar tipos de diagnóstico](quality-diagnostic-types.md).</span><span class="sxs-lookup"><span data-stu-id="62161-136">[Configure diagnostic types](quality-diagnostic-types.md).</span></span>
1. <span data-ttu-id="62161-137">[Configurar operações](quality-operations.md).</span><span class="sxs-lookup"><span data-stu-id="62161-137">[Configure operations](quality-operations.md).</span></span>
1. <span data-ttu-id="62161-138">Opcional: [Configurar encargos de qualidade](quality-charges.md).</span><span class="sxs-lookup"><span data-stu-id="62161-138">Optional: [Configure quality charges](quality-charges.md).</span></span>

<span data-ttu-id="62161-139">Depois de concluída a configuração, você pode começar a criar e processar não conformidades.</span><span class="sxs-lookup"><span data-stu-id="62161-139">After the configuration is completed, you can start to create and process nonconformances.</span></span> <span data-ttu-id="62161-140">Para obter mais informações sobre como criar e trabalhar com não conformidades, consulte [Criar e processar não conformidades](tasks/create-process-non-conformance.md).</span><span class="sxs-lookup"><span data-stu-id="62161-140">For more information about how to create and work with nonconformances, see [Create and process nonconformances](tasks/create-process-non-conformance.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="62161-141">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="62161-141">Additional resources</span></span>

- [<span data-ttu-id="62161-142">Visão geral do gerenciamento de qualidade</span><span class="sxs-lookup"><span data-stu-id="62161-142">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="62161-143">Habilitar gerenciamento de qualidade e não conformidade</span><span class="sxs-lookup"><span data-stu-id="62161-143">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="62161-144">Gerenciamento de qualidade para processos de depósito</span><span class="sxs-lookup"><span data-stu-id="62161-144">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

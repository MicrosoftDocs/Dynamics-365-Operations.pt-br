---
title: Desempenho de agendamento de recursos de projeto
description: Este tópico fornece informações sobre como melhorar o desempenho do planejamento de recursos para um grande número de projetos.
author: Yowelle
manager: AnnBe
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 10.0.14
ms.search.validFrom: 2020-09-01
ms.openlocfilehash: 988fc83230f08a6534caa7c37784757d73c1cc12
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760479"
---
# <a name="project-resource-scheduling-performance"></a><span data-ttu-id="d5f29-103">Desempenho de agendamento de recursos de projeto</span><span class="sxs-lookup"><span data-stu-id="d5f29-103">Project resource scheduling performance</span></span>

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]


<span data-ttu-id="d5f29-104">Os problemas de desempenho relacionados ao planejamento de recursos podem ocorrer quando o número de projetos chega a milhares.</span><span class="sxs-lookup"><span data-stu-id="d5f29-104">Performance issues related to resource scheduling can occur when the number of projects reaches into the thousands.</span></span> <span data-ttu-id="d5f29-105">Para melhorar o desempenho do planejamento de recursos, está disponível um recurso que permite aos usuários reduzir o tempo necessário para iniciar o formulário disponibilidade de recursos.</span><span class="sxs-lookup"><span data-stu-id="d5f29-105">To improve resource scheduling performance, a feature is available that allows users to reduce the time that it takes to launch the resource availability form.</span></span> <span data-ttu-id="d5f29-106">Especificamente, isso remove o processo de sincronização de acúmulo de capacidade de recursos e usa a tabela **ResProjectResource** para acelerar a pesquisa de recursos.</span><span class="sxs-lookup"><span data-stu-id="d5f29-106">Specifically, this removes the resource capacity roll-up synchronization process and uses the **ResProjectResource** table to speed up the resource lookup.</span></span> <span data-ttu-id="d5f29-107">Observe que a tabela **ResRollup** não será mais usada.</span><span class="sxs-lookup"><span data-stu-id="d5f29-107">Note that the **ResRollup** table will no longer be used.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d5f29-108">Se houver uma dependência no processo de sincronização de acúmulo de capacidade de recursos na tabela **ResProjectResource**, não use esse recurso.</span><span class="sxs-lookup"><span data-stu-id="d5f29-108">If there is a dependency on either the resource capacity roll-up synchronization process or the **ResProjectResource** table, do not use this feature.</span></span>

## <a name="enable-resource-scheduling-performance-enhancement"></a><span data-ttu-id="d5f29-109">Habilitar o aperfeiçoamento de desempenho de planejamento de recursos</span><span class="sxs-lookup"><span data-stu-id="d5f29-109">Enable resource scheduling performance enhancement</span></span>
<span data-ttu-id="d5f29-110">Para habilitar a melhoria do desempenho do agendamento de recursos, conclua as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="d5f29-110">To enable resource scheduling performance enhancement, complete the following steps.</span></span>

1. <span data-ttu-id="d5f29-111">Vá para **Gerenciamento de recursos** > **Tudo** e, na lista de recursos, localize **Habilitar recurso de aperfeiçoamento de desempenho do agendamento de recursos do projeto**.</span><span class="sxs-lookup"><span data-stu-id="d5f29-111">Go to **Feature management** > **All**, and in the feature list, locate **Enable project resource scheduling performance enhancement feature**.</span></span>
2. <span data-ttu-id="d5f29-112">Selecione **Habilitar agora**.</span><span class="sxs-lookup"><span data-stu-id="d5f29-112">Select **Enable now**.</span></span>

> [!NOTE]
> <span data-ttu-id="d5f29-113">Se você não conseguir encontrar o recurso na lista, selecione **Verificar se há atualizações** para atualizar a lista.</span><span class="sxs-lookup"><span data-stu-id="d5f29-113">If you can't find the feature in the list, select **Check for updates** to refresh the list.</span></span>

3. <span data-ttu-id="d5f29-114">Atualize o navegador e vá para **Gerenciamento e contabilidade de projeto** > **Periódico** > **Recursos do projeto** > **Sincronizar capacidade de calendários de recursos em todas as empresas**.</span><span class="sxs-lookup"><span data-stu-id="d5f29-114">Refresh your browser, and then go to **Project management and accounting** > **Periodic** > **Project resources** > **Synchronize resource calendars capacity across all companies**.</span></span>
4. <span data-ttu-id="d5f29-115">Defina **Remover registros de capacidade existentes** como **Sim** para remover os dados anteriores.</span><span class="sxs-lookup"><span data-stu-id="d5f29-115">Set **Remove existing capacity records** to **Yes** to remove previous data.</span></span> <span data-ttu-id="d5f29-116">Se desejar gerar dados incrementais, defina a opção como **Não**.</span><span class="sxs-lookup"><span data-stu-id="d5f29-116">If you want generate incremental data, set it to **No**.</span></span>
5. <span data-ttu-id="d5f29-117">No campo **Código do período**, selecione o período no qual os dados devem ser gerados.</span><span class="sxs-lookup"><span data-stu-id="d5f29-117">In the **Period code** field, select the period in which data should be generated.</span></span> <span data-ttu-id="d5f29-118">Se você selecionar um código de período, não será necessário definir datas de início e término.</span><span class="sxs-lookup"><span data-stu-id="d5f29-118">If you select a period code, a start and end date do not need to be defined.</span></span>
6. <span data-ttu-id="d5f29-119">Se você deixar o campo **Código do período** em branco, selecione datas de início e término específicas para gerar dados.</span><span class="sxs-lookup"><span data-stu-id="d5f29-119">If you leave the **Period code** field blank, select specific start and end dates to generate data.</span></span>
7. <span data-ttu-id="d5f29-120">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="d5f29-120">Select **OK**.</span></span>

 > [!NOTE]
 > <span data-ttu-id="d5f29-121">Isso distribuirá dados gerais para a tabela **ResCalendarCapacity** em todas as empresas do seu ambiente, de forma que o trabalho em lotes só precise ser executado em uma entidade legal.</span><span class="sxs-lookup"><span data-stu-id="d5f29-121">This will distribute general data to the **ResCalendarCapacity** table across all companies in your environment, so the batch job only needs to be run in one legal entity.</span></span> <span data-ttu-id="d5f29-122">Os dados nesse trabalho em lotes são necessários para calcular a capacidade de recursos por meio do calendário associado.</span><span class="sxs-lookup"><span data-stu-id="d5f29-122">The data in this batch job is needed to calculate resource capacity through the associated calendar.</span></span>

8. <span data-ttu-id="d5f29-123">Vá para **Gerenciamento e contabilidade de projeto** > **Periódico** > **Recursos de projeto** > **Popular recursos de projeto em todas as empresas** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="d5f29-123">Go to **Project management and accounting** > **Periodic** > **Project resources** > **Populate project resources across all companies** and then select **OK**.</span></span> <span data-ttu-id="d5f29-124">Este é o script de atualização de dados para dados gerais nas tabelas **ResProjectResource**, **ResCalendarDateTimeRange** e **ResEffectiveDateTimeRange**.</span><span class="sxs-lookup"><span data-stu-id="d5f29-124">This is the data upgrade script for general data in the **ResProjectResource**, **ResCalendarDateTimeRange**, and **ResEffectiveDateTimeRange** tables.</span></span> <span data-ttu-id="d5f29-125">Os valores do campo **PSAPRojSchedRole.RootActivity** também são atualizados.</span><span class="sxs-lookup"><span data-stu-id="d5f29-125">Values for the **PSAPRojSchedRole.RootActivity** field are also updated.</span></span> <span data-ttu-id="d5f29-126">Se isso não for executado, você receberá um aviso quando tentar executar operações de agendamento de recursos.</span><span class="sxs-lookup"><span data-stu-id="d5f29-126">If this is not run, you will receive a warning when you try to execute resource scheduling operations.</span></span>
 
## <a name="turn-off-resource-scheduling-performance-enhancement"></a><span data-ttu-id="d5f29-127">Ativar o aperfeiçoamento de desempenho de agendamento de recursos</span><span class="sxs-lookup"><span data-stu-id="d5f29-127">Turn off resource scheduling performance enhancement</span></span>

1. <span data-ttu-id="d5f29-128">Vá para **Gerenciamento de recursos** > **Tudo** e procure por **Habilitar recurso de aperfeiçoamento de desempenho do agendamento de recursos do projeto**.</span><span class="sxs-lookup"><span data-stu-id="d5f29-128">Go to **Feature management** > **All**  and search for **Enable project resource scheduling performance enhancement feature**.</span></span>
2. <span data-ttu-id="d5f29-129">Selecione o recurso e o botão **Desabilitar**.</span><span class="sxs-lookup"><span data-stu-id="d5f29-129">Select the feature, and then select the **Disable** button.</span></span>
3. <span data-ttu-id="d5f29-130">Atualize seu navegador.</span><span class="sxs-lookup"><span data-stu-id="d5f29-130">Refresh your browser.</span></span>
4. <span data-ttu-id="d5f29-131">Vá para **Gerenciamento e contabilidade de projeto** > **Periódico** > **Sincronização de capacidade** > **Sincronizar acúmulos de capacidade de recursos**.</span><span class="sxs-lookup"><span data-stu-id="d5f29-131">Go to **Project management and accounting** > **Periodic** > **Capacity synchronization** > **Synchronize resource capacity roll-ups**.</span></span>
5. <span data-ttu-id="d5f29-132">Na página **Organização de acúmulo de capacidade**, defina **Remover registros de capacidade existentes** como **Sim** para remover dados anteriores.</span><span class="sxs-lookup"><span data-stu-id="d5f29-132">On the **Capacity roll-up synchronization** page, set **Remove existing capacity records** to **Yes** to remove previous data.</span></span> <span data-ttu-id="d5f29-133">Se desejar gerar dados incrementais, defina a opção como **Não**.</span><span class="sxs-lookup"><span data-stu-id="d5f29-133">If you want to generate incremental data, set it to **No**.</span></span>
6. <span data-ttu-id="d5f29-134">No campo **Código do período**, selecione o período no qual os dados devem ser gerados.</span><span class="sxs-lookup"><span data-stu-id="d5f29-134">In the **Period code** field, select the period in which data should be generated.</span></span> <span data-ttu-id="d5f29-135">Se você selecionar um código de período, não será necessário definir datas de início e término.</span><span class="sxs-lookup"><span data-stu-id="d5f29-135">If you select a period code, a start and end date do not need to be defined.</span></span>
7. <span data-ttu-id="d5f29-136">Se você deixar o campo **Código do período** em branco, selecione datas de início e término específicas para gerar dados.</span><span class="sxs-lookup"><span data-stu-id="d5f29-136">If you leave the **Period code** field blank, select specific start and end dates to generate data.</span></span>
8. <span data-ttu-id="d5f29-137">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="d5f29-137">Select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="d5f29-138">Isso distribuirá dados gerais para a tabela **ResRollup** em todas as empresas do seu ambiente, de forma que o trabalho em lotes só precise ser executado em uma entidade legal.</span><span class="sxs-lookup"><span data-stu-id="d5f29-138">This will distribute general data to the **ResRollup** table across all companies in your environment, so the batch job only needs to be run in one legal entity.</span></span> <span data-ttu-id="d5f29-139">Esse trabalho em lotes é necessário para todas as exibições **Disponibilidade de recursos**.</span><span class="sxs-lookup"><span data-stu-id="d5f29-139">This batch job is needed for all **Resource Availability** views.</span></span> <span data-ttu-id="d5f29-140">Se esse trabalho em lotes não for executado, os dados **ResRollup** serão gerados rapidamente, o que pode levar tempo.</span><span class="sxs-lookup"><span data-stu-id="d5f29-140">If this batch job is not run, the **ResRollup** data will be generated on the fly, which can take time.</span></span>

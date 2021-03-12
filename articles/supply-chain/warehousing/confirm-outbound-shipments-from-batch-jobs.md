---
title: Confirmar remessas de saída de trabalhos em lote
description: Este tópico descreve como configurar um trabalho em lotes que automaticamente confirma remessas de ordem de transferência de saída para cargas prontas para a remessa.
author: perlynne
manager: tfehr
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 48257967ce360b1d4969124411d5976b807bf9e4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996292"
---
# <a name="confirm-outbound-shipments-from-batch-jobs"></a><span data-ttu-id="16fc2-103">Confirmar remessas de saída de trabalhos em lote</span><span class="sxs-lookup"><span data-stu-id="16fc2-103">Confirm outbound shipments from batch jobs</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="16fc2-104">Este tópico descreve como configurar um trabalho em lotes que automaticamente confirma remessas de ordem de transferência de saída para cargas prontas para a remessa.</span><span class="sxs-lookup"><span data-stu-id="16fc2-104">This topic describes how to set up a batch job that automatically confirms outbound transfer-order shipments for ready-to-ship loads.</span></span> <span data-ttu-id="16fc2-105">O trabalho em lotes aqui descrito só se aplica a remessas de ordens de transferência e não a ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="16fc2-105">The batch job described here only applies to transfer order shipments, not to sales orders.</span></span>

## <a name="enable-the-confirm-outbound-shipments-from-batch-jobs-feature"></a><span data-ttu-id="16fc2-106">Habilitar o recurso Confirmar remessas de saída de trabalhos em lote</span><span class="sxs-lookup"><span data-stu-id="16fc2-106">Enable the Confirm outbound shipments from batch jobs feature</span></span>

<span data-ttu-id="16fc2-107">Antes de poder usar esse recurso, ele deverá estar habilitado no seu sistema.</span><span class="sxs-lookup"><span data-stu-id="16fc2-107">Before you can use this feature, it must be enabled on your system.</span></span> <span data-ttu-id="16fc2-108">Os administradores podem usar a página [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo, se necessário.</span><span class="sxs-lookup"><span data-stu-id="16fc2-108">Administrators can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) page to check the feature status and enable it if needed.</span></span> <span data-ttu-id="16fc2-109">O recurso está listado como:</span><span class="sxs-lookup"><span data-stu-id="16fc2-109">The feature is listed as:</span></span>

- <span data-ttu-id="16fc2-110">**Módulo** - *Gerenciamento de depósito*</span><span class="sxs-lookup"><span data-stu-id="16fc2-110">**Module** - *Warehouse management*</span></span>
- <span data-ttu-id="16fc2-111">**Nome do recurso** - *Confirmar remessas de saída de trabalhos em lote*</span><span class="sxs-lookup"><span data-stu-id="16fc2-111">**Feature name** - *Confirm outbound shipments from batch jobs*</span></span>

## <a name="process-outbound-shipments"></a><span data-ttu-id="16fc2-112">Processar remessas de saída</span><span class="sxs-lookup"><span data-stu-id="16fc2-112">Process outbound shipments</span></span>

<span data-ttu-id="16fc2-113">Para configurar um trabalho em lotes agendado para executar a confirmação de remessa de saída para cargas prontas para remessa:</span><span class="sxs-lookup"><span data-stu-id="16fc2-113">To set up a scheduled batch job to run the outbound shipment confirmation for loads that are ready to ship:</span></span>

1. <span data-ttu-id="16fc2-114">Vá para **Gerenciamento de depósito \> Tarefas periódicas \> Processar remessas de saída**.</span><span class="sxs-lookup"><span data-stu-id="16fc2-114">Go to **Warehouse management \> Periodic tasks \> Process outbound shipments**.</span></span>
1. <span data-ttu-id="16fc2-115">A caixa de diálogo **Confirmar remessa** é aberta.</span><span class="sxs-lookup"><span data-stu-id="16fc2-115">The **Confirm shipment** dialog box opens.</span></span> <span data-ttu-id="16fc2-116">Na Guia Rápida **Registros a incluir**, selecione **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="16fc2-116">On the **Records to include** FastTab, select **Filter**.</span></span>
1. <span data-ttu-id="16fc2-117">A caixa de diálogo do editor de consultas é aberta.</span><span class="sxs-lookup"><span data-stu-id="16fc2-117">The query editor dialog box opens.</span></span> <span data-ttu-id="16fc2-118">Na guia **Intervalo**, adicione uma linha com os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="16fc2-118">On the **Range** tab, add a row with the following values:</span></span>
    - <span data-ttu-id="16fc2-119">**Tabela** - *Cargas*</span><span class="sxs-lookup"><span data-stu-id="16fc2-119">**Table** - *Loads*</span></span>
    - <span data-ttu-id="16fc2-120">**Tabela derivada** - *Cargas*</span><span class="sxs-lookup"><span data-stu-id="16fc2-120">**Derived table** - *Loads*</span></span>
    - <span data-ttu-id="16fc2-121">**Campo** - *Status de carga*</span><span class="sxs-lookup"><span data-stu-id="16fc2-121">**Field** - *Load status*</span></span>
    - <span data-ttu-id="16fc2-122">**Critérios** - *Carregados*</span><span class="sxs-lookup"><span data-stu-id="16fc2-122">**Criteria** - *Loaded*</span></span>
1. <span data-ttu-id="16fc2-123">Selecione **OK** para retornar à caixa de diálogo **Confirmar remessa**.</span><span class="sxs-lookup"><span data-stu-id="16fc2-123">Select **OK** to return to the **Confirm shipment** dialog box.</span></span>
1. <span data-ttu-id="16fc2-124">Na guia rápida **Executar em segundo plano**, defina **Processamento em lotes** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="16fc2-124">On the **Run in the background** FastTab, set **Batch processing** to **Yes**.</span></span>
1. <span data-ttu-id="16fc2-125">Na guia rápida **Executar em segundo plano**, selecione **Recorrência**.</span><span class="sxs-lookup"><span data-stu-id="16fc2-125">On the **Run in the background** FastTab, select **Recurrence**.</span></span>
1. <span data-ttu-id="16fc2-126">A caixa de diálogo **Definir recorrência** será aberta.</span><span class="sxs-lookup"><span data-stu-id="16fc2-126">The **Define recurrence** dialog box opens.</span></span> <span data-ttu-id="16fc2-127">Defina o plano de execução, conforme necessário para a sua empresa.</span><span class="sxs-lookup"><span data-stu-id="16fc2-127">Set the run schedule as needed for your business.</span></span>
1. <span data-ttu-id="16fc2-128">Selecione **OK** para retornar à caixa de diálogo **Confirmar remessa**.</span><span class="sxs-lookup"><span data-stu-id="16fc2-128">Select **OK** to return to the **Confirm shipment** dialog box.</span></span>
1. <span data-ttu-id="16fc2-129">Selecione **OK** na caixa de diálogo **Confirmar remessa** para adicionar o trabalho em lotes à fila de lotes.</span><span class="sxs-lookup"><span data-stu-id="16fc2-129">Select **OK** on the **Confirm shipment** dialog box to add the batch job to the batch queue.</span></span>

<span data-ttu-id="16fc2-130">Para obter mais informações, consulte [Visão geral do processamento em lotes](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md).</span><span class="sxs-lookup"><span data-stu-id="16fc2-130">For more information, see [Batch processing overview](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md).</span></span>

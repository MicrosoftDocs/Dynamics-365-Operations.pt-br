---
title: Numerar documentos e comprovantes cronologicamente
description: Este tópico explica como configurar e usar números cronológicos para documentos aplicáveis e comprovantes relacionados.
author: ikond
manager: AnnBe
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: NumberSequenceGroup
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 401195
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-15
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 31745632de7339d167ac9f18f02e6611e1a78b28
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104347"
---
# <a name="numbering-documents-and-vouchers-chronologically"></a><span data-ttu-id="836b2-103">Numerar documentos e comprovantes cronologicamente</span><span class="sxs-lookup"><span data-stu-id="836b2-103">Numbering documents and vouchers chronologically</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="836b2-104">Em alguns países, há um requisito legal para numerar documentos e comprovantes relacionados em ordem cronológica.</span><span class="sxs-lookup"><span data-stu-id="836b2-104">In some countries, there is a legal requirement to number documents and related vouchers in chronological order.</span></span> <span data-ttu-id="836b2-105">A cronologia deve ter suporte de períodos.</span><span class="sxs-lookup"><span data-stu-id="836b2-105">The chronology must be supported by periods.</span></span> <span data-ttu-id="836b2-106">Todos os números pertencentes a períodos anteriores devem ser menores que os números pertencentes a períodos posteriores.</span><span class="sxs-lookup"><span data-stu-id="836b2-106">All of the numbers that belong to earlier periods must be less than the numbers that belong to later periods.</span></span> <span data-ttu-id="836b2-107">Para atender a esse requisito, a funcionalidade de numeração cronológica foi implementada.</span><span class="sxs-lookup"><span data-stu-id="836b2-107">To meet this requirement, chronological numbering functionality has been implemented.</span></span> <span data-ttu-id="836b2-108">Este tópico explica como configurar e usar números cronológicos para documentos aplicáveis e comprovantes relacionados.</span><span class="sxs-lookup"><span data-stu-id="836b2-108">This topic explains how to configure and use chronological numbers for applicable documents and related vouchers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="836b2-109">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="836b2-109">Prerequisites</span></span>

<span data-ttu-id="836b2-110">No espaço de trabalho Gerenciamento de recursos, ative o recurso **Numeração cronológica**.</span><span class="sxs-lookup"><span data-stu-id="836b2-110">In the Feature management workspace, turn on the **Chronological numbering** feature.</span></span> <span data-ttu-id="836b2-111">Para obter mais informações, consulte [Visão geral do Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="836b2-111">For more information, see [Feature management overview](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>

## <a name="configure-chronological-numbering"></a><span data-ttu-id="836b2-112">Configurar numeração cronológica</span><span class="sxs-lookup"><span data-stu-id="836b2-112">Configure chronological numbering</span></span>

<span data-ttu-id="836b2-113">A numeração cronológica afeta os documentos a seguir.</span><span class="sxs-lookup"><span data-stu-id="836b2-113">Chronological numbering affects the following documents.</span></span>

<span data-ttu-id="836b2-114">**Contas a receber**</span><span class="sxs-lookup"><span data-stu-id="836b2-114">**Accounts receivable**</span></span>
- <span data-ttu-id="836b2-115">Fatura de cliente</span><span class="sxs-lookup"><span data-stu-id="836b2-115">Customer invoice</span></span>
- <span data-ttu-id="836b2-116">Comprovante de fatura de cliente</span><span class="sxs-lookup"><span data-stu-id="836b2-116">Customer invoice voucher</span></span>
- <span data-ttu-id="836b2-117">Nota de crédito de venda</span><span class="sxs-lookup"><span data-stu-id="836b2-117">Sales credit note</span></span>
- <span data-ttu-id="836b2-118">Comprovante de nota de crédito de venda</span><span class="sxs-lookup"><span data-stu-id="836b2-118">Sales credit note voucher</span></span>
- <span data-ttu-id="836b2-119">Fatura de texto livre</span><span class="sxs-lookup"><span data-stu-id="836b2-119">Free text invoice</span></span>
- <span data-ttu-id="836b2-120">Comprovante de fatura de texto livre</span><span class="sxs-lookup"><span data-stu-id="836b2-120">Free text invoice voucher</span></span>
- <span data-ttu-id="836b2-121">Nota de crédito em texto livre</span><span class="sxs-lookup"><span data-stu-id="836b2-121">Free text credit note</span></span>
- <span data-ttu-id="836b2-122">Comprovante de nota de crédito em texto livre</span><span class="sxs-lookup"><span data-stu-id="836b2-122">Free text credit note voucher</span></span>
- <span data-ttu-id="836b2-123">Guia de Remessa</span><span class="sxs-lookup"><span data-stu-id="836b2-123">Packing slip</span></span>
- <span data-ttu-id="836b2-124">Comprovante de guia de remessa</span><span class="sxs-lookup"><span data-stu-id="836b2-124">Packing slip voucher</span></span>
- <span data-ttu-id="836b2-125">Comprovante de correção da guia de remessa</span><span class="sxs-lookup"><span data-stu-id="836b2-125">Packing slip correction voucher</span></span>
- <span data-ttu-id="836b2-126">Comprovante de nota de juros</span><span class="sxs-lookup"><span data-stu-id="836b2-126">Interest note voucher</span></span>
- <span data-ttu-id="836b2-127">Comprovante de carta de cobrança</span><span class="sxs-lookup"><span data-stu-id="836b2-127">Collection letter voucher</span></span>

<span data-ttu-id="836b2-128">**Contas a pagar**</span><span class="sxs-lookup"><span data-stu-id="836b2-128">**Accounts payable**</span></span>
- <span data-ttu-id="836b2-129">Comprovante de fatura</span><span class="sxs-lookup"><span data-stu-id="836b2-129">Invoice voucher</span></span>
- <span data-ttu-id="836b2-130">Comprovante de nota de crédito</span><span class="sxs-lookup"><span data-stu-id="836b2-130">Credit note voucher</span></span>
- <span data-ttu-id="836b2-131">Comprovante de recebimento de produtos</span><span class="sxs-lookup"><span data-stu-id="836b2-131">Product receipt voucher</span></span>

<span data-ttu-id="836b2-132">**Gerenciamento de projetos**</span><span class="sxs-lookup"><span data-stu-id="836b2-132">**Project management**</span></span>
- <span data-ttu-id="836b2-133">Fatura</span><span class="sxs-lookup"><span data-stu-id="836b2-133">Invoice</span></span>
- <span data-ttu-id="836b2-134">Comprovante de fatura</span><span class="sxs-lookup"><span data-stu-id="836b2-134">Invoice voucher</span></span>
- <span data-ttu-id="836b2-135">Nota de Crédito</span><span class="sxs-lookup"><span data-stu-id="836b2-135">Credit note</span></span>
- <span data-ttu-id="836b2-136">Comprovante de nota de crédito</span><span class="sxs-lookup"><span data-stu-id="836b2-136">Credit note voucher</span></span> 

### <a name="define-number-sequences"></a><span data-ttu-id="836b2-137">Definir sequências numéricas</span><span class="sxs-lookup"><span data-stu-id="836b2-137">Define number sequences</span></span>

<span data-ttu-id="836b2-138">Para definir as sequências numéricas, acesse **Administração da organização** > **Sequências numéricas** > **Sequências numéricas**.</span><span class="sxs-lookup"><span data-stu-id="836b2-138">To define number sequences, go to **Organization administration** > **Number sequences** > **Number sequences**.</span></span> <span data-ttu-id="836b2-139">É possível definir as sequências numéricas necessárias para cobrir os períodos afetados para os documentos necessários.</span><span class="sxs-lookup"><span data-stu-id="836b2-139">You can define as many number sequences as required to cover the affected periods for required documents.</span></span> 

<span data-ttu-id="836b2-140">Especifique uma empresa para cada sequência numérica.</span><span class="sxs-lookup"><span data-stu-id="836b2-140">Specify a company for each number sequence.</span></span> <span data-ttu-id="836b2-141">Os segmentos das sequências numéricas devem ser definidos para que forneçam ordem cronológica para períodos.</span><span class="sxs-lookup"><span data-stu-id="836b2-141">The segments of the number sequences must be defined so that they provide chronological order for periods.</span></span> <span data-ttu-id="836b2-142">Por exemplo, os nomes de segmento podem conter um prefixo especial que identifica um período específico.</span><span class="sxs-lookup"><span data-stu-id="836b2-142">For example, the segment names can contain a special prefix that identifies a specific period.</span></span>

![Configuração da sequência numérica](media/chrono-num-sequence.jpg)

### <a name="configure-number-sequence-groups"></a><span data-ttu-id="836b2-144">Configurar grupos de sequências numéricas</span><span class="sxs-lookup"><span data-stu-id="836b2-144">Configure number sequence groups</span></span>

<span data-ttu-id="836b2-145">Para configurar grupos de sequências numéricas, acesse **Contas a receber** > **Configuração** > **Parâmetros de contas a receber**.</span><span class="sxs-lookup"><span data-stu-id="836b2-145">To configure number sequence groups, go to **Accounts receivable** > **Setup** > **Accounts receivable parameters**.</span></span> <span data-ttu-id="836b2-146">Na guia **Sequências numéricas**, defina quantos grupos de sequências numéricas forem necessários para cobrir os períodos afetados.</span><span class="sxs-lookup"><span data-stu-id="836b2-146">On the **Number sequences** tab, define as many number sequences groups as required to cover the affected periods.</span></span> 

<span data-ttu-id="836b2-147">Para cada grupo, na seção **Referência**, selecione uma das referências de documento com suporte e, no campo **Código de sequência numérica**, consulte uma sequência numérica criada anteriormente para o período relacionado.</span><span class="sxs-lookup"><span data-stu-id="836b2-147">For each group, in the **Reference** section, select one of the supported document references, and in the **Number sequence code** field, refer to a number sequence that was previously created for the related period.</span></span>

![Configuração do grupo de sequências numéricas](media/chrono-num-sequence-group.jpg)

<span data-ttu-id="836b2-149">Da mesma forma, configure grupos de sequências numéricas nos módulos **Contas a pagar** e **Gerenciamento de projetos e contabilidade**.</span><span class="sxs-lookup"><span data-stu-id="836b2-149">Similarly, configure number sequence groups in **Accounts payable** and **Project management and accounting** modules.</span></span>

### <a name="configure-number-sequence-groups-chronology"></a><span data-ttu-id="836b2-150">Configurar cronologia de grupos de sequências numéricas</span><span class="sxs-lookup"><span data-stu-id="836b2-150">Configure number sequence groups chronology</span></span>

<span data-ttu-id="836b2-151">Para configurar a cronologia de grupos de sequências numéricas, acesse **Administração da organização** > **Sequências numéricas** > **Cronologia de grupos de sequências numéricas**.</span><span class="sxs-lookup"><span data-stu-id="836b2-151">To configure number sequence groups chronology, go to **Organization administration** > **Number sequences** > **Chronological number sequence groups**.</span></span> <span data-ttu-id="836b2-152">Defina as condições de aplicabilidade para grupos de sequências numéricas.</span><span class="sxs-lookup"><span data-stu-id="836b2-152">Define the applicability conditions for number sequence groups.</span></span>

![Configuração de números cronológicos](media/chrono-num-sequence-group-period.jpg)

| <span data-ttu-id="836b2-154">Campo</span><span class="sxs-lookup"><span data-stu-id="836b2-154">Field</span></span>            | <span data-ttu-id="836b2-155">Descrição</span><span class="sxs-lookup"><span data-stu-id="836b2-155">Description</span></span>                                                                                                                                                                                                                                                                                                                                                                                   |
|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="836b2-156">Efetivação</span><span class="sxs-lookup"><span data-stu-id="836b2-156">Effective</span></span>  | <span data-ttu-id="836b2-157">A data de início da aplicabilidade do grupo de sequências numéricas.</span><span class="sxs-lookup"><span data-stu-id="836b2-157">The start date of number sequence group applicability.</span></span> |
| <span data-ttu-id="836b2-158">Vencimento</span><span class="sxs-lookup"><span data-stu-id="836b2-158">Expiration</span></span>      | <span data-ttu-id="836b2-159">A data de término da aplicabilidade do grupo de sequências numéricas.</span><span class="sxs-lookup"><span data-stu-id="836b2-159">The end date of number sequence group applicability.</span></span> <span data-ttu-id="836b2-160">Se nenhuma data de término for aplicada, selecione **Nunca**.</span><span class="sxs-lookup"><span data-stu-id="836b2-160">If no end date is applied, select **Never**.</span></span> |
| <span data-ttu-id="836b2-161">Grupo de sequências numéricas</span><span class="sxs-lookup"><span data-stu-id="836b2-161">Number sequence group</span></span> | <span data-ttu-id="836b2-162">Grupo de sequências numéricas que será usado para gerar números de documento durante o período.</span><span class="sxs-lookup"><span data-stu-id="836b2-162">Number sequence group that will be used to generate document numbers during the period.</span></span> |
| <span data-ttu-id="836b2-163">Grupo de sequências numéricas original</span><span class="sxs-lookup"><span data-stu-id="836b2-163">Original number sequence group</span></span> | <span data-ttu-id="836b2-164">Esse código de grupo de sequências numéricas é usado para filtragem adicional dos casos em que documentos já têm um grupo de sequências numéricas *permanente* específico atribuído.</span><span class="sxs-lookup"><span data-stu-id="836b2-164">This number sequence group code is used for additional filtering for the cases when documents already have a specific *permanent* number sequence group assigned.</span></span> <span data-ttu-id="836b2-165">Um valor vazio é considerado um valor específico.</span><span class="sxs-lookup"><span data-stu-id="836b2-165">An empty value is considered a specific value.</span></span> <span data-ttu-id="836b2-166">Se você precisar ignorar um grupo atribuído preliminar, use a opção **Padrão** para essa configuração.</span><span class="sxs-lookup"><span data-stu-id="836b2-166">If you need to ignore a preliminary assigned group, use the **Default** option for this setup.</span></span> |
| <span data-ttu-id="836b2-167">Padrão</span><span class="sxs-lookup"><span data-stu-id="836b2-167">Default</span></span> | <span data-ttu-id="836b2-168">Se ela estiver ativada, o sistema ignorará o grupo preliminar de sequências numéricas de documentos atribuídos e usará somente as datas de início e de término dos períodos para análise de aplicabilidade.</span><span class="sxs-lookup"><span data-stu-id="836b2-168">If turned on, the system ignores the preliminary assigned document number sequence group and uses only the periods start and end dates for applicability analysis.</span></span> <span data-ttu-id="836b2-169">Se ela estiver desativada, o sistema usará a combinação total **Efetivação** + **Expiração** + **Grupo de sequências numéricas original** para seleção.</span><span class="sxs-lookup"><span data-stu-id="836b2-169">If turned off, the system uses the full combination **Effective** + **Expiration** + **Original number sequence group** for selection.</span></span> |

## <a name="document-posting"></a><span data-ttu-id="836b2-170">Lançamento de documento</span><span class="sxs-lookup"><span data-stu-id="836b2-170">Document posting</span></span>
<span data-ttu-id="836b2-171">Quando você lança um documento, o grupo de sequências numéricas apropriado é atribuído ao documento, com base na data de lançamento do documento. Depois, ele é usado para gerar um número de documento com base na sequência numérica detectada.</span><span class="sxs-lookup"><span data-stu-id="836b2-171">When you post a document, the appropriate number sequence group is assigned to the document, based on document's posting date, and then used to generate a document number based on the detected number sequence.</span></span> <span data-ttu-id="836b2-172">O sistema fornece uma mensagem sobre a atribuição de grupo de sequências numéricas.</span><span class="sxs-lookup"><span data-stu-id="836b2-172">The system provides a message regarding the number sequence group assignment.</span></span>

![Número do documento](media/chrono-num-sequence-fti.jpg)

> [!NOTE]
> <span data-ttu-id="836b2-174">Em alguns países, há uma lógica específica já implementada para a numeração de documentos.</span><span class="sxs-lookup"><span data-stu-id="836b2-174">For some countries, there is a specific logic already implemented for document numbering.</span></span> <span data-ttu-id="836b2-175">Nesse caso, a lógica específica do país substituirá o recurso **Numeração cronológica**.</span><span class="sxs-lookup"><span data-stu-id="836b2-175">In this case, country-specific logic will override the **Chronological numbering** feature.</span></span>

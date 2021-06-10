---
title: Detalhes da folha de pagamento para Posições
description: Este tópico fornece detalhes e um exemplo de consulta para os detalhes da folha de pagamento da entidade Posições no Dynamics 365 Human Resources.
author: jcart
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8918044dbf84e79015dc3bca904f204123a37db8
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6056771"
---
# <a name="payroll-position"></a><span data-ttu-id="694c0-103">Posição na folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="694c0-103">Payroll position</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="694c0-104">Este tópico fornece detalhes e um exemplo de consulta para os detalhes da folha de pagamento da entidade Posições no Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="694c0-104">This topic provides details and an example query for the Payroll details for the Positions entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="694c0-105">Propriedades</span><span class="sxs-lookup"><span data-stu-id="694c0-105">Properties</span></span>

| <span data-ttu-id="694c0-106">Propriedade</span><span class="sxs-lookup"><span data-stu-id="694c0-106">Property</span></span><br><span data-ttu-id="694c0-107">**Nome físico**</span><span class="sxs-lookup"><span data-stu-id="694c0-107">**Physical name**</span></span><br><span data-ttu-id="694c0-108">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="694c0-108">**_Type_**</span></span> | <span data-ttu-id="694c0-109">Uso</span><span class="sxs-lookup"><span data-stu-id="694c0-109">Use</span></span> | <span data-ttu-id="694c0-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="694c0-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="694c0-111">**Horas normais anuais**</span><span class="sxs-lookup"><span data-stu-id="694c0-111">**Annual regular hours**</span></span><br><span data-ttu-id="694c0-112">annualregularhours</span><span class="sxs-lookup"><span data-stu-id="694c0-112">annualregularhours</span></span><br><span data-ttu-id="694c0-113">*Decimal*</span><span class="sxs-lookup"><span data-stu-id="694c0-113">*Decimal*</span></span> | <span data-ttu-id="694c0-114">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="694c0-114">Read-only</span></span><br><span data-ttu-id="694c0-115">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="694c0-115">Required</span></span> | <span data-ttu-id="694c0-116">Horas normais anuais definidas na posição.</span><span class="sxs-lookup"><span data-stu-id="694c0-116">Annual regular hours defined on the position.</span></span>  |
| <span data-ttu-id="694c0-117">**ID da entidade Detalhes da posição de folha de pagamento**</span><span class="sxs-lookup"><span data-stu-id="694c0-117">**Payroll position details entity ID**</span></span><br><span data-ttu-id="694c0-118">payrollpositiondetailsentityid</span><span class="sxs-lookup"><span data-stu-id="694c0-118">payrollpositiondetailsentityid</span></span><br><span data-ttu-id="694c0-119">*Guid*</span><span class="sxs-lookup"><span data-stu-id="694c0-119">*Guid*</span></span> | <span data-ttu-id="694c0-120">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="694c0-120">Required</span></span><br><span data-ttu-id="694c0-121">Gerado pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="694c0-121">System generated.</span></span> | <span data-ttu-id="694c0-122">Um valor GUID gerado pelo sistema para identificar exclusivamente a posição.</span><span class="sxs-lookup"><span data-stu-id="694c0-122">A system-generated GUID value to uniquely identify the position.</span></span>  |
| <span data-ttu-id="694c0-123">**Campo principal**</span><span class="sxs-lookup"><span data-stu-id="694c0-123">**Primary field**</span></span><br><span data-ttu-id="694c0-124">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="694c0-124">mshr_primaryfield</span></span><br><span data-ttu-id="694c0-125">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="694c0-125">*String*</span></span> | <span data-ttu-id="694c0-126">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="694c0-126">Required</span></span><br><span data-ttu-id="694c0-127">Gerado pelo sistema</span><span class="sxs-lookup"><span data-stu-id="694c0-127">System generated</span></span> |  |
| <span data-ttu-id="694c0-128">**Valor de ID de trabalho da posição**</span><span class="sxs-lookup"><span data-stu-id="694c0-128">**Position job ID value**</span></span><br><span data-ttu-id="694c0-129">_mshr_fk_positionjob_id_value</span><span class="sxs-lookup"><span data-stu-id="694c0-129">_mshr_fk_positionjob_id_value</span></span><br><span data-ttu-id="694c0-130">*GUID*</span><span class="sxs-lookup"><span data-stu-id="694c0-130">*GUID*</span></span> | <span data-ttu-id="694c0-131">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="694c0-131">Read-only</span></span><br><span data-ttu-id="694c0-132">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="694c0-132">Required</span></span><br><span data-ttu-id="694c0-133">Chave externa: mshr_PayrollPositionJobEntity da mshr_payrollpositionjobentity</span><span class="sxs-lookup"><span data-stu-id="694c0-133">Foreign key:mshr_PayrollPositionJobEntity of the mshr_payrollpositionjobentity</span></span> |<span data-ttu-id="694c0-134">A ID do trabalho associado à posição.</span><span class="sxs-lookup"><span data-stu-id="694c0-134">The ID of the job associated with the position.</span></span>|
| <span data-ttu-id="694c0-135">**Valor da ID do plano de remuneração fixa**</span><span class="sxs-lookup"><span data-stu-id="694c0-135">**Fixed compensation plan ID value**</span></span><br><span data-ttu-id="694c0-136">_mshr_fk_fixedcompplan_id_value</span><span class="sxs-lookup"><span data-stu-id="694c0-136">_mshr_fk_fixedcompplan_id_value</span></span><br><span data-ttu-id="694c0-137">*GUID*</span><span class="sxs-lookup"><span data-stu-id="694c0-137">*GUID*</span></span> | <span data-ttu-id="694c0-138">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="694c0-138">Read-only</span></span><br><span data-ttu-id="694c0-139">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="694c0-139">Required</span></span><br><span data-ttu-id="694c0-140">Chave estrangeira: mshr_FixedCompPlan_id de mshr_payrollfixedcompensationplanentity</span><span class="sxs-lookup"><span data-stu-id="694c0-140">Foreign key: mshr_FixedCompPlan_id of mshr_payrollfixedcompensationplanentity</span></span>  | <span data-ttu-id="694c0-141">A ID do plano de remuneração fixa associado à posição.</span><span class="sxs-lookup"><span data-stu-id="694c0-141">The ID of the fixed compensation plan associated with the position.</span></span> |
| <span data-ttu-id="694c0-142">**ID do ciclo de pagamento**</span><span class="sxs-lookup"><span data-stu-id="694c0-142">**Pay cycle ID**</span></span><br><span data-ttu-id="694c0-143">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="694c0-143">mshr_primaryfield</span></span><br><span data-ttu-id="694c0-144">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="694c0-144">*String*</span></span> | <span data-ttu-id="694c0-145">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="694c0-145">Read-only</span></span><br><span data-ttu-id="694c0-146">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="694c0-146">Required</span></span> | <span data-ttu-id="694c0-147">O ciclo de pagamento definido na posição.</span><span class="sxs-lookup"><span data-stu-id="694c0-147">The pay cycle defined on the position.</span></span> |
| <span data-ttu-id="694c0-148">**Pago por entidade legal**</span><span class="sxs-lookup"><span data-stu-id="694c0-148">**Paid by legal entity**</span></span><br><span data-ttu-id="694c0-149">paidbylegalentity</span><span class="sxs-lookup"><span data-stu-id="694c0-149">paidbylegalentity</span></span><br><span data-ttu-id="694c0-150">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="694c0-150">*String*</span></span> | <span data-ttu-id="694c0-151">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="694c0-151">Read-only</span></span><br><span data-ttu-id="694c0-152">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="694c0-152">Required</span></span> | <span data-ttu-id="694c0-153">A entidade legal definida na posição responsável pela emissão do pagamento.</span><span class="sxs-lookup"><span data-stu-id="694c0-153">The legal entity defined on the positoin responsible for issuing payment.</span></span> |
| <span data-ttu-id="694c0-154">**ID da posição**</span><span class="sxs-lookup"><span data-stu-id="694c0-154">**Position ID**</span></span><br><span data-ttu-id="694c0-155">mshr_positionid</span><span class="sxs-lookup"><span data-stu-id="694c0-155">mshr_positionid</span></span><br><span data-ttu-id="694c0-156">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="694c0-156">*String*</span></span> | <span data-ttu-id="694c0-157">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="694c0-157">Read-only</span></span><br><span data-ttu-id="694c0-158">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="694c0-158">Required</span></span> | <span data-ttu-id="694c0-159">A ID da posição.</span><span class="sxs-lookup"><span data-stu-id="694c0-159">The ID of the position.</span></span> |
| <span data-ttu-id="694c0-160">**Válida até**</span><span class="sxs-lookup"><span data-stu-id="694c0-160">**Valid to**</span></span><br><span data-ttu-id="694c0-161">validto</span><span class="sxs-lookup"><span data-stu-id="694c0-161">validto</span></span><br><span data-ttu-id="694c0-162">*Compensação de Data/Hora*</span><span class="sxs-lookup"><span data-stu-id="694c0-162">*Date Time Offset*</span></span> | <span data-ttu-id="694c0-163">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="694c0-163">Read-only</span></span><br><span data-ttu-id="694c0-164">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="694c0-164">Required</span></span> |<span data-ttu-id="694c0-165">A data a partir da qual detalhes da posição são válidos.</span><span class="sxs-lookup"><span data-stu-id="694c0-165">The date the position details are valid from.</span></span>  |
| <span data-ttu-id="694c0-166">**Válido a partir de**</span><span class="sxs-lookup"><span data-stu-id="694c0-166">**Valid from**</span></span><br><span data-ttu-id="694c0-167">validfrom</span><span class="sxs-lookup"><span data-stu-id="694c0-167">validfrom</span></span><br><span data-ttu-id="694c0-168">*Compensação de Data/Hora*</span><span class="sxs-lookup"><span data-stu-id="694c0-168">*Date Time Offset*</span></span> | <span data-ttu-id="694c0-169">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="694c0-169">Read-only</span></span><br><span data-ttu-id="694c0-170">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="694c0-170">Required</span></span> |<span data-ttu-id="694c0-171">A data até a qual detalhes da posição são válidos.</span><span class="sxs-lookup"><span data-stu-id="694c0-171">The date the position details are valid to.</span></span>  |

<span data-ttu-id="694c0-172">**Consulta**</span><span class="sxs-lookup"><span data-stu-id="694c0-172">**Query**</span></span>

<span data-ttu-id="694c0-173">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="694c0-173">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollpositionentities?$filter=mshr_positionid eq @positionid and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@positionid='000276'&@asofdate=2021-04-01
```

<span data-ttu-id="694c0-174">**Resposta**</span><span class="sxs-lookup"><span data-stu-id="694c0-174">**Response**</span></span>

```json
{
            "mshr_positionid": "000276",
            "mshr_paycycleid": "w",
            "mshr_annualregularhours": 3000,
            "mshr_paidbylegalentity": "USMF",
            "mshr_validfrom": "2021-03-14T00:00:00Z",
            "mshr_validto": "2154-12-31T00:00:00Z",
            "mshr_primaryfield": "000276 | 3/14/2021",
            "_mshr_fk_job_id_value": "00010094-0000-0000-df00-014105000000",
            "_mshr_fk_fixedcompplan_id_value": "0000029f-0000-0000-d5ff-004105000000",
            "mshr_payrollpositionentityid": "00010097-0000-0000-df00-014105000000"
}
```

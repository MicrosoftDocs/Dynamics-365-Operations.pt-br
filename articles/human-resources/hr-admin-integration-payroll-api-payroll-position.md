---
title: Detalhes da folha de pagamento para Posições
description: Este tópico fornece detalhes e um exemplo de consulta para os detalhes da folha de pagamento da entidade Posições no Dynamics 365 Human Resources.
author: jcart
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7b23ac5d11b18c77109be21afe1570755dccba20
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019313"
---
# <a name="payroll-position"></a><span data-ttu-id="8479c-103">Posição na folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="8479c-103">Payroll position</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="8479c-104">Este tópico fornece detalhes e um exemplo de consulta para os detalhes da folha de pagamento da entidade Posições no Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8479c-104">This topic provides details and an example query for the Payroll details for the Positions entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="8479c-105">Propriedades</span><span class="sxs-lookup"><span data-stu-id="8479c-105">Properties</span></span>

| <span data-ttu-id="8479c-106">Propriedade</span><span class="sxs-lookup"><span data-stu-id="8479c-106">Property</span></span><br><span data-ttu-id="8479c-107">**Nome físico**</span><span class="sxs-lookup"><span data-stu-id="8479c-107">**Physical name**</span></span><br><span data-ttu-id="8479c-108">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="8479c-108">**_Type_**</span></span> | <span data-ttu-id="8479c-109">Uso</span><span class="sxs-lookup"><span data-stu-id="8479c-109">Use</span></span> | <span data-ttu-id="8479c-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="8479c-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="8479c-111">**Horas normais anuais**</span><span class="sxs-lookup"><span data-stu-id="8479c-111">**Annual regular hours**</span></span><br><span data-ttu-id="8479c-112">annualregularhours</span><span class="sxs-lookup"><span data-stu-id="8479c-112">annualregularhours</span></span><br><span data-ttu-id="8479c-113">*Decimal*</span><span class="sxs-lookup"><span data-stu-id="8479c-113">*Decimal*</span></span> | <span data-ttu-id="8479c-114">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="8479c-114">Read-only</span></span><br><span data-ttu-id="8479c-115">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="8479c-115">Required</span></span> | <span data-ttu-id="8479c-116">Horas normais anuais definidas na posição.</span><span class="sxs-lookup"><span data-stu-id="8479c-116">Annual regular hours defined on the position.</span></span>  |
| <span data-ttu-id="8479c-117">**ID da entidade Detalhes da posição de folha de pagamento**</span><span class="sxs-lookup"><span data-stu-id="8479c-117">**Payroll position details entity ID**</span></span><br><span data-ttu-id="8479c-118">payrollpositiondetailsentityid</span><span class="sxs-lookup"><span data-stu-id="8479c-118">payrollpositiondetailsentityid</span></span><br><span data-ttu-id="8479c-119">*Guid*</span><span class="sxs-lookup"><span data-stu-id="8479c-119">*Guid*</span></span> | <span data-ttu-id="8479c-120">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="8479c-120">Required</span></span><br><span data-ttu-id="8479c-121">Gerado pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="8479c-121">System generated.</span></span> | <span data-ttu-id="8479c-122">Um valor GUID gerado pelo sistema para identificar exclusivamente a posição.</span><span class="sxs-lookup"><span data-stu-id="8479c-122">A system-generated GUID value to uniquely identify the position.</span></span>  |
| <span data-ttu-id="8479c-123">**Campo principal**</span><span class="sxs-lookup"><span data-stu-id="8479c-123">**Primary field**</span></span><br><span data-ttu-id="8479c-124">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="8479c-124">mshr_primaryfield</span></span><br><span data-ttu-id="8479c-125">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="8479c-125">*String*</span></span> | <span data-ttu-id="8479c-126">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="8479c-126">Required</span></span><br><span data-ttu-id="8479c-127">Gerado pelo sistema</span><span class="sxs-lookup"><span data-stu-id="8479c-127">System generated</span></span> |  |
| <span data-ttu-id="8479c-128">**Valor de ID de trabalho da posição**</span><span class="sxs-lookup"><span data-stu-id="8479c-128">**Position job ID value**</span></span><br><span data-ttu-id="8479c-129">_mshr_fk_positionjob_id_value</span><span class="sxs-lookup"><span data-stu-id="8479c-129">_mshr_fk_positionjob_id_value</span></span><br><span data-ttu-id="8479c-130">*GUID*</span><span class="sxs-lookup"><span data-stu-id="8479c-130">*GUID*</span></span> | <span data-ttu-id="8479c-131">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="8479c-131">Read-only</span></span><br><span data-ttu-id="8479c-132">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="8479c-132">Required</span></span><br><span data-ttu-id="8479c-133">Chave externa: mshr_PayrollPositionJobEntity da mshr_payrollpositionjobentity</span><span class="sxs-lookup"><span data-stu-id="8479c-133">Foreign key:mshr_PayrollPositionJobEntity of the mshr_payrollpositionjobentity</span></span> |<span data-ttu-id="8479c-134">A ID do trabalho associado à posição.</span><span class="sxs-lookup"><span data-stu-id="8479c-134">The ID of the job associated with the position.</span></span>|
| <span data-ttu-id="8479c-135">**Valor da ID do plano de remuneração fixa**</span><span class="sxs-lookup"><span data-stu-id="8479c-135">**Fixed compensation plan ID value**</span></span><br><span data-ttu-id="8479c-136">_mshr_fk_fixedcompplan_id_value</span><span class="sxs-lookup"><span data-stu-id="8479c-136">_mshr_fk_fixedcompplan_id_value</span></span><br><span data-ttu-id="8479c-137">*GUID*</span><span class="sxs-lookup"><span data-stu-id="8479c-137">*GUID*</span></span> | <span data-ttu-id="8479c-138">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="8479c-138">Read-only</span></span><br><span data-ttu-id="8479c-139">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="8479c-139">Required</span></span><br><span data-ttu-id="8479c-140">Chave estrangeira: mshr_FixedCompPlan_id de mshr_payrollfixedcompensationplanentity</span><span class="sxs-lookup"><span data-stu-id="8479c-140">Foreign key: mshr_FixedCompPlan_id of mshr_payrollfixedcompensationplanentity</span></span>  | <span data-ttu-id="8479c-141">A ID do plano de remuneração fixa associado à posição.</span><span class="sxs-lookup"><span data-stu-id="8479c-141">The ID of the fixed compensation plan associated with the position.</span></span> |
| <span data-ttu-id="8479c-142">**ID do ciclo de pagamento**</span><span class="sxs-lookup"><span data-stu-id="8479c-142">**Pay cycle ID**</span></span><br><span data-ttu-id="8479c-143">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="8479c-143">mshr_primaryfield</span></span><br><span data-ttu-id="8479c-144">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="8479c-144">*String*</span></span> | <span data-ttu-id="8479c-145">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="8479c-145">Read-only</span></span><br><span data-ttu-id="8479c-146">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="8479c-146">Required</span></span> | <span data-ttu-id="8479c-147">O ciclo de pagamento definido na posição.</span><span class="sxs-lookup"><span data-stu-id="8479c-147">The pay cycle defined on the position.</span></span> |
| <span data-ttu-id="8479c-148">**Pago por entidade legal**</span><span class="sxs-lookup"><span data-stu-id="8479c-148">**Paid by legal entity**</span></span><br><span data-ttu-id="8479c-149">paidbylegalentity</span><span class="sxs-lookup"><span data-stu-id="8479c-149">paidbylegalentity</span></span><br><span data-ttu-id="8479c-150">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="8479c-150">*String*</span></span> | <span data-ttu-id="8479c-151">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="8479c-151">Read-only</span></span><br><span data-ttu-id="8479c-152">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="8479c-152">Required</span></span> | <span data-ttu-id="8479c-153">A entidade legal definida na posição responsável pela emissão do pagamento.</span><span class="sxs-lookup"><span data-stu-id="8479c-153">The legal entity defined on the positoin responsible for issuing payment.</span></span> |
| <span data-ttu-id="8479c-154">**ID da posição**</span><span class="sxs-lookup"><span data-stu-id="8479c-154">**Position ID**</span></span><br><span data-ttu-id="8479c-155">mshr_positionid</span><span class="sxs-lookup"><span data-stu-id="8479c-155">mshr_positionid</span></span><br><span data-ttu-id="8479c-156">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="8479c-156">*String*</span></span> | <span data-ttu-id="8479c-157">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="8479c-157">Read-only</span></span><br><span data-ttu-id="8479c-158">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="8479c-158">Required</span></span> | <span data-ttu-id="8479c-159">A ID da posição.</span><span class="sxs-lookup"><span data-stu-id="8479c-159">The ID of the position.</span></span> |
| <span data-ttu-id="8479c-160">**Válida até**</span><span class="sxs-lookup"><span data-stu-id="8479c-160">**Valid to**</span></span><br><span data-ttu-id="8479c-161">validto</span><span class="sxs-lookup"><span data-stu-id="8479c-161">validto</span></span><br><span data-ttu-id="8479c-162">*Compensação de Data/Hora*</span><span class="sxs-lookup"><span data-stu-id="8479c-162">*Date Time Offset*</span></span> | <span data-ttu-id="8479c-163">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="8479c-163">Read-only</span></span><br><span data-ttu-id="8479c-164">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="8479c-164">Required</span></span> |<span data-ttu-id="8479c-165">A data a partir da qual detalhes da posição são válidos.</span><span class="sxs-lookup"><span data-stu-id="8479c-165">The date the position details are valid from.</span></span>  |
| <span data-ttu-id="8479c-166">**Válido a partir de**</span><span class="sxs-lookup"><span data-stu-id="8479c-166">**Valid from**</span></span><br><span data-ttu-id="8479c-167">validfrom</span><span class="sxs-lookup"><span data-stu-id="8479c-167">validfrom</span></span><br><span data-ttu-id="8479c-168">*Compensação de Data/Hora*</span><span class="sxs-lookup"><span data-stu-id="8479c-168">*Date Time Offset*</span></span> | <span data-ttu-id="8479c-169">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="8479c-169">Read-only</span></span><br><span data-ttu-id="8479c-170">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="8479c-170">Required</span></span> |<span data-ttu-id="8479c-171">A data até a qual detalhes da posição são válidos.</span><span class="sxs-lookup"><span data-stu-id="8479c-171">The date the position details are valid to.</span></span>  |

<span data-ttu-id="8479c-172">**Consulta**</span><span class="sxs-lookup"><span data-stu-id="8479c-172">**Query**</span></span>

<span data-ttu-id="8479c-173">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="8479c-173">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollpositionentities?$filter=mshr_positionid eq @positionid and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@positionid='000276'&@asofdate=2021-04-01
```

<span data-ttu-id="8479c-174">**Resposta**</span><span class="sxs-lookup"><span data-stu-id="8479c-174">**Response**</span></span>

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

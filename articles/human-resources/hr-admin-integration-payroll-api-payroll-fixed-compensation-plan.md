---
title: Plano de remuneração fixa da folha de pagamento
description: Este tópico fornece detalhes e um exemplo de consulta da entidade Plano de remuneração fixa da folha de pagamento no Dynamics 365 Human Resources.
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
ms.openlocfilehash: 85cfce6f626090adab422ea6c60fc0778fd1ac67
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021287"
---
# <a name="payroll-fixed-compensation-plan"></a><span data-ttu-id="65fda-103">Plano de remuneração fixa da folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="65fda-103">Payroll fixed compensation plan</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="65fda-104">Este tópico fornece detalhes e um exemplo de consulta da entidade Plano de remuneração fixa da folha de pagamento no Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="65fda-104">This topic provides details and an example query for the Payroll fixed compensation plan entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="65fda-105">Propriedades</span><span class="sxs-lookup"><span data-stu-id="65fda-105">Properties</span></span>

| <span data-ttu-id="65fda-106">Propriedade</span><span class="sxs-lookup"><span data-stu-id="65fda-106">Property</span></span><br><span data-ttu-id="65fda-107">**Nome físico**</span><span class="sxs-lookup"><span data-stu-id="65fda-107">**Physical name**</span></span><br><span data-ttu-id="65fda-108">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="65fda-108">**_Type_**</span></span> | <span data-ttu-id="65fda-109">Uso</span><span class="sxs-lookup"><span data-stu-id="65fda-109">Use</span></span> | <span data-ttu-id="65fda-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="65fda-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="65fda-111">**ID do Funcionário**</span><span class="sxs-lookup"><span data-stu-id="65fda-111">**Employee ID**</span></span><br><span data-ttu-id="65fda-112">mshr_fk_employee_id_value</span><span class="sxs-lookup"><span data-stu-id="65fda-112">mshr_fk_employee_id_value</span></span><br><span data-ttu-id="65fda-113">*GUID*</span><span class="sxs-lookup"><span data-stu-id="65fda-113">*GUID*</span></span> | <span data-ttu-id="65fda-114">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="65fda-114">Read-only</span></span><br><span data-ttu-id="65fda-115">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="65fda-115">Required</span></span><br><span data-ttu-id="65fda-116">Chave estrangeira: mshr_Employee_id da entidade mshr_payrollemployeeentity</span><span class="sxs-lookup"><span data-stu-id="65fda-116">Foreign key:mshr_Employee_id of mshr_payrollemployeeentity entity</span></span>  | <span data-ttu-id="65fda-117">ID do Funcionário</span><span class="sxs-lookup"><span data-stu-id="65fda-117">Employee ID</span></span> |
| <span data-ttu-id="65fda-118">**Taxa de pagamento**</span><span class="sxs-lookup"><span data-stu-id="65fda-118">**Pay rate**</span></span><br><span data-ttu-id="65fda-119">mshr_payrate</span><span class="sxs-lookup"><span data-stu-id="65fda-119">mshr_payrate</span></span><br><span data-ttu-id="65fda-120">*Decimal*</span><span class="sxs-lookup"><span data-stu-id="65fda-120">*Decimal*</span></span> | <span data-ttu-id="65fda-121">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="65fda-121">Read-only</span></span><br><span data-ttu-id="65fda-122">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="65fda-122">Required</span></span> | <span data-ttu-id="65fda-123">A taxa de pagamento definida no plano de remuneração fixa.</span><span class="sxs-lookup"><span data-stu-id="65fda-123">Pay rate defined in fixed compensation plan.</span></span> |
| <span data-ttu-id="65fda-124">**ID do Plano**</span><span class="sxs-lookup"><span data-stu-id="65fda-124">**Plan ID**</span></span><br><span data-ttu-id="65fda-125">mshr_planid</span><span class="sxs-lookup"><span data-stu-id="65fda-125">mshr_planid</span></span><br><span data-ttu-id="65fda-126">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="65fda-126">*String*</span></span> | <span data-ttu-id="65fda-127">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="65fda-127">Read-only</span></span><br><span data-ttu-id="65fda-128">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="65fda-128">Required</span></span> |<span data-ttu-id="65fda-129">Especifica o plano da remuneração.</span><span class="sxs-lookup"><span data-stu-id="65fda-129">Specifies the compensation plan.</span></span>  |
| <span data-ttu-id="65fda-130">**Válido a partir de**</span><span class="sxs-lookup"><span data-stu-id="65fda-130">**Valid from**</span></span><br><span data-ttu-id="65fda-131">mshr_validfrom</span><span class="sxs-lookup"><span data-stu-id="65fda-131">mshr_validfrom</span></span><br><span data-ttu-id="65fda-132">*Compensação de Data/Hora*</span><span class="sxs-lookup"><span data-stu-id="65fda-132">*Date Time Offset*</span></span> |  <span data-ttu-id="65fda-133">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="65fda-133">Read-only</span></span><br><span data-ttu-id="65fda-134">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="65fda-134">Required</span></span> |<span data-ttu-id="65fda-135">Data a partir da qual a remuneração fixa do funcionário é válida.</span><span class="sxs-lookup"><span data-stu-id="65fda-135">Date the employee fixed compensation is valid from.</span></span>  |
| <span data-ttu-id="65fda-136">**Entidade Plano de remuneração fixa da folha de pagamento**</span><span class="sxs-lookup"><span data-stu-id="65fda-136">**Payroll Fixed Compensation Plan entity**</span></span><br><span data-ttu-id="65fda-137">mshr_payrollfixedcompensationplanentityid</span><span class="sxs-lookup"><span data-stu-id="65fda-137">mshr_payrollfixedcompensationplanentityid</span></span><br><span data-ttu-id="65fda-138">*GUID*</span><span class="sxs-lookup"><span data-stu-id="65fda-138">*GUID*</span></span> | <span data-ttu-id="65fda-139">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="65fda-139">Required</span></span><br><span data-ttu-id="65fda-140">Gerado pelo sistema</span><span class="sxs-lookup"><span data-stu-id="65fda-140">Sytem generated</span></span> | <span data-ttu-id="65fda-141">Um valor GUID gerado pelo sistema para identificar exclusivamente o plano de remuneração.</span><span class="sxs-lookup"><span data-stu-id="65fda-141">A system-generated GUID value to uniquely identify the compensation plan.</span></span> |
| <span data-ttu-id="65fda-142">**Frequência de pagamento**</span><span class="sxs-lookup"><span data-stu-id="65fda-142">**Pay frequency**</span></span><br><span data-ttu-id="65fda-143">mshr_payfrequency</span><span class="sxs-lookup"><span data-stu-id="65fda-143">mshr_payfrequency</span></span><br><span data-ttu-id="65fda-144">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="65fda-144">*String*</span></span> | <span data-ttu-id="65fda-145">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="65fda-145">Read-only</span></span><br><span data-ttu-id="65fda-146">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="65fda-146">Required</span></span> |<span data-ttu-id="65fda-147">A frequência com que o funcionário será pago.</span><span class="sxs-lookup"><span data-stu-id="65fda-147">The frequency the employee will be paid.</span></span>  |
| <span data-ttu-id="65fda-148">**Válida até**</span><span class="sxs-lookup"><span data-stu-id="65fda-148">**Valid to**</span></span><br><span data-ttu-id="65fda-149">mshr_validto</span><span class="sxs-lookup"><span data-stu-id="65fda-149">mshr_validto</span></span><br><span data-ttu-id="65fda-150">*Compensação de Data/Hora*</span><span class="sxs-lookup"><span data-stu-id="65fda-150">*Date Time Offset*</span></span> | <span data-ttu-id="65fda-151">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="65fda-151">Read-only</span></span> <br><span data-ttu-id="65fda-152">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="65fda-152">Required</span></span> | <span data-ttu-id="65fda-153">Data até a qual a remuneração fixa do funcionário é válida.</span><span class="sxs-lookup"><span data-stu-id="65fda-153">Date the employee fixed compensation is valid to.</span></span> |
| <span data-ttu-id="65fda-154">**ID da posição**</span><span class="sxs-lookup"><span data-stu-id="65fda-154">**Position ID**</span></span><br><span data-ttu-id="65fda-155">mshr_positionid</span><span class="sxs-lookup"><span data-stu-id="65fda-155">mshr_positionid</span></span><br><span data-ttu-id="65fda-156">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="65fda-156">*String*</span></span> | <span data-ttu-id="65fda-157">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="65fda-157">Read-only</span></span> <br><span data-ttu-id="65fda-158">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="65fda-158">Required</span></span> | <span data-ttu-id="65fda-159">ID da posição associada ao funcionário e ao registro do plano de remuneração fixa.</span><span class="sxs-lookup"><span data-stu-id="65fda-159">Postion ID associated with the employee and fixed compensation plan enrollment.</span></span> |
| <span data-ttu-id="65fda-160">**Moeda**</span><span class="sxs-lookup"><span data-stu-id="65fda-160">**Currency**</span></span><br><span data-ttu-id="65fda-161">mshr_currency</span><span class="sxs-lookup"><span data-stu-id="65fda-161">mshr_currency</span></span><br><span data-ttu-id="65fda-162">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="65fda-162">*String*</span></span> | <span data-ttu-id="65fda-163">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="65fda-163">Read-only</span></span> <br><span data-ttu-id="65fda-164">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="65fda-164">Required</span></span> |<span data-ttu-id="65fda-165">A moeda definida para o plano de remuneração fixa</span><span class="sxs-lookup"><span data-stu-id="65fda-165">The currency defined for the fixed compensation plan</span></span>   |
| <span data-ttu-id="65fda-166">**Número da equipe**</span><span class="sxs-lookup"><span data-stu-id="65fda-166">**Personnel number**</span></span><br><span data-ttu-id="65fda-167">mshr_personnelnumber</span><span class="sxs-lookup"><span data-stu-id="65fda-167">mshr_personnelnumber</span></span><br><span data-ttu-id="65fda-168">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="65fda-168">*String*</span></span> | <span data-ttu-id="65fda-169">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="65fda-169">Read-only</span></span><br><span data-ttu-id="65fda-170">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="65fda-170">Required</span></span> |<span data-ttu-id="65fda-171">O número da equipe exclusiva do funcionário.</span><span class="sxs-lookup"><span data-stu-id="65fda-171">The employee's unique personnel number.</span></span>  |

<span data-ttu-id="65fda-172">**Consulta**</span><span class="sxs-lookup"><span data-stu-id="65fda-172">**Query**</span></span>

<span data-ttu-id="65fda-173">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="65fda-173">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollfixedcompensationplanentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

<span data-ttu-id="65fda-174">**Resposta**</span><span class="sxs-lookup"><span data-stu-id="65fda-174">**Response**</span></span>

```json
{
            "mshr_planid": "GradeC",
            "mshr_personnelnumber": "000041",
            "mshr_payrate": 75200,
            "mshr_positionid": "000276",
            "mshr_validfrom": "2011-04-05T00:00:00Z",
            "mshr_validto": "2154-12-31T00:00:00Z",
            "mshr_payfrequency": "Annual",
            "mshr_currency": "USD",
            "_mshr_fk_employee_id_value": "00000d3c-0000-0000-d5ff-004105000000",
            "_mshr_fk_plan_id_value": "0000070c-0000-0000-b328-fef003000000",
            "_mshr_fk_job_id_value": "00010094-0000-0000-df00-014105000000",
            "mshr_payrollfixedcompensationplanentityid": "0000029f-0000-0000-d5ff-004105000000",
            "_mshr_fk_payroll_id_value": null
}
```

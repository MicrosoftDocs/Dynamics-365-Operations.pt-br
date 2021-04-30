---
title: Plano de remuneração fixa da folha de pagamento
description: Este tópico fornece detalhes e um exemplo de consulta da entidade Plano de remuneração fixa da folha de pagamento no Dynamics 365 Human Resources.
author: jcart
manager: tfehr
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
ms.openlocfilehash: 78a274cc491041d3d917a50bfb433f667cd8c255
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881929"
---
# <a name="payroll-fixed-compensation-plan"></a><span data-ttu-id="7b105-103">Plano de remuneração fixa da folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="7b105-103">Payroll fixed compensation plan</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="7b105-104">Este tópico fornece detalhes e um exemplo de consulta da entidade Plano de remuneração fixa da folha de pagamento no Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="7b105-104">This topic provides details and an example query for the Payroll fixed compensation plan entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="7b105-105">Propriedades</span><span class="sxs-lookup"><span data-stu-id="7b105-105">Properties</span></span>

| <span data-ttu-id="7b105-106">Propriedade</span><span class="sxs-lookup"><span data-stu-id="7b105-106">Property</span></span><br><span data-ttu-id="7b105-107">**Nome físico**</span><span class="sxs-lookup"><span data-stu-id="7b105-107">**Physical name**</span></span><br><span data-ttu-id="7b105-108">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="7b105-108">**_Type_**</span></span> | <span data-ttu-id="7b105-109">Uso</span><span class="sxs-lookup"><span data-stu-id="7b105-109">Use</span></span> | <span data-ttu-id="7b105-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="7b105-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="7b105-111">**ID do Funcionário**</span><span class="sxs-lookup"><span data-stu-id="7b105-111">**Employee ID**</span></span><br><span data-ttu-id="7b105-112">mshr_fk_employee_id_value</span><span class="sxs-lookup"><span data-stu-id="7b105-112">mshr_fk_employee_id_value</span></span><br><span data-ttu-id="7b105-113">*GUID*</span><span class="sxs-lookup"><span data-stu-id="7b105-113">*GUID*</span></span> | <span data-ttu-id="7b105-114">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="7b105-114">Read-only</span></span><br><span data-ttu-id="7b105-115">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="7b105-115">Required</span></span><br><span data-ttu-id="7b105-116">Chave estrangeira: mshr_Employee_id da entidade mshr_payrollemployeeentity</span><span class="sxs-lookup"><span data-stu-id="7b105-116">Foreign key:mshr_Employee_id of mshr_payrollemployeeentity entity</span></span>  | <span data-ttu-id="7b105-117">ID do Funcionário</span><span class="sxs-lookup"><span data-stu-id="7b105-117">Employee ID</span></span> |
| <span data-ttu-id="7b105-118">**Taxa de pagamento**</span><span class="sxs-lookup"><span data-stu-id="7b105-118">**Pay rate**</span></span><br><span data-ttu-id="7b105-119">mshr_payrate</span><span class="sxs-lookup"><span data-stu-id="7b105-119">mshr_payrate</span></span><br><span data-ttu-id="7b105-120">*Decimal*</span><span class="sxs-lookup"><span data-stu-id="7b105-120">*Decimal*</span></span> | <span data-ttu-id="7b105-121">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="7b105-121">Read-only</span></span><br><span data-ttu-id="7b105-122">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="7b105-122">Required</span></span> | <span data-ttu-id="7b105-123">A taxa de pagamento definida no plano de remuneração fixa.</span><span class="sxs-lookup"><span data-stu-id="7b105-123">Pay rate defined in fixed compensation plan.</span></span> |
| <span data-ttu-id="7b105-124">**ID do Plano**</span><span class="sxs-lookup"><span data-stu-id="7b105-124">**Plan ID**</span></span><br><span data-ttu-id="7b105-125">mshr_planid</span><span class="sxs-lookup"><span data-stu-id="7b105-125">mshr_planid</span></span><br><span data-ttu-id="7b105-126">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="7b105-126">*String*</span></span> | <span data-ttu-id="7b105-127">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="7b105-127">Read-only</span></span><br><span data-ttu-id="7b105-128">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="7b105-128">Required</span></span> |<span data-ttu-id="7b105-129">Especifica o plano da remuneração.</span><span class="sxs-lookup"><span data-stu-id="7b105-129">Specifies the compensation plan.</span></span>  |
| <span data-ttu-id="7b105-130">**Válido a partir de**</span><span class="sxs-lookup"><span data-stu-id="7b105-130">**Valid from**</span></span><br><span data-ttu-id="7b105-131">mshr_validfrom</span><span class="sxs-lookup"><span data-stu-id="7b105-131">mshr_validfrom</span></span><br><span data-ttu-id="7b105-132">*Compensação de Data/Hora*</span><span class="sxs-lookup"><span data-stu-id="7b105-132">*Date Time Offset*</span></span> |  <span data-ttu-id="7b105-133">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="7b105-133">Read-only</span></span><br><span data-ttu-id="7b105-134">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="7b105-134">Required</span></span> |<span data-ttu-id="7b105-135">Data a partir da qual a remuneração fixa do funcionário é válida.</span><span class="sxs-lookup"><span data-stu-id="7b105-135">Date the employee fixed compensation is valid from.</span></span>  |
| <span data-ttu-id="7b105-136">**Entidade Plano de remuneração fixa da folha de pagamento**</span><span class="sxs-lookup"><span data-stu-id="7b105-136">**Payroll Fixed Compensation Plan entity**</span></span><br><span data-ttu-id="7b105-137">mshr_payrollfixedcompensationplanentityid</span><span class="sxs-lookup"><span data-stu-id="7b105-137">mshr_payrollfixedcompensationplanentityid</span></span><br><span data-ttu-id="7b105-138">*GUID*</span><span class="sxs-lookup"><span data-stu-id="7b105-138">*GUID*</span></span> | <span data-ttu-id="7b105-139">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="7b105-139">Required</span></span><br><span data-ttu-id="7b105-140">Gerado pelo sistema</span><span class="sxs-lookup"><span data-stu-id="7b105-140">Sytem generated</span></span> | <span data-ttu-id="7b105-141">Um valor GUID gerado pelo sistema para identificar exclusivamente o plano de remuneração.</span><span class="sxs-lookup"><span data-stu-id="7b105-141">A system-generated GUID value to uniquely identify the compensation plan.</span></span> |
| <span data-ttu-id="7b105-142">**Frequência de pagamento**</span><span class="sxs-lookup"><span data-stu-id="7b105-142">**Pay frequency**</span></span><br><span data-ttu-id="7b105-143">mshr_payfrequency</span><span class="sxs-lookup"><span data-stu-id="7b105-143">mshr_payfrequency</span></span><br><span data-ttu-id="7b105-144">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="7b105-144">*String*</span></span> | <span data-ttu-id="7b105-145">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="7b105-145">Read-only</span></span><br><span data-ttu-id="7b105-146">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="7b105-146">Required</span></span> |<span data-ttu-id="7b105-147">A frequência com que o funcionário será pago.</span><span class="sxs-lookup"><span data-stu-id="7b105-147">The frequency the employee will be paid.</span></span>  |
| <span data-ttu-id="7b105-148">**Válida até**</span><span class="sxs-lookup"><span data-stu-id="7b105-148">**Valid to**</span></span><br><span data-ttu-id="7b105-149">mshr_validto</span><span class="sxs-lookup"><span data-stu-id="7b105-149">mshr_validto</span></span><br><span data-ttu-id="7b105-150">*Compensação de Data/Hora*</span><span class="sxs-lookup"><span data-stu-id="7b105-150">*Date Time Offset*</span></span> | <span data-ttu-id="7b105-151">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="7b105-151">Read-only</span></span> <br><span data-ttu-id="7b105-152">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="7b105-152">Required</span></span> | <span data-ttu-id="7b105-153">Data até a qual a remuneração fixa do funcionário é válida.</span><span class="sxs-lookup"><span data-stu-id="7b105-153">Date the employee fixed compensation is valid to.</span></span> |
| <span data-ttu-id="7b105-154">**ID da posição**</span><span class="sxs-lookup"><span data-stu-id="7b105-154">**Position ID**</span></span><br><span data-ttu-id="7b105-155">mshr_positionid</span><span class="sxs-lookup"><span data-stu-id="7b105-155">mshr_positionid</span></span><br><span data-ttu-id="7b105-156">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="7b105-156">*String*</span></span> | <span data-ttu-id="7b105-157">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="7b105-157">Read-only</span></span> <br><span data-ttu-id="7b105-158">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="7b105-158">Required</span></span> | <span data-ttu-id="7b105-159">ID da posição associada ao funcionário e ao registro do plano de remuneração fixa.</span><span class="sxs-lookup"><span data-stu-id="7b105-159">Postion ID associated with the employee and fixed compensation plan enrollment.</span></span> |
| <span data-ttu-id="7b105-160">**Moeda**</span><span class="sxs-lookup"><span data-stu-id="7b105-160">**Currency**</span></span><br><span data-ttu-id="7b105-161">mshr_currency</span><span class="sxs-lookup"><span data-stu-id="7b105-161">mshr_currency</span></span><br><span data-ttu-id="7b105-162">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="7b105-162">*String*</span></span> | <span data-ttu-id="7b105-163">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="7b105-163">Read-only</span></span> <br><span data-ttu-id="7b105-164">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="7b105-164">Required</span></span> |<span data-ttu-id="7b105-165">A moeda definida para o plano de remuneração fixa</span><span class="sxs-lookup"><span data-stu-id="7b105-165">The currency defined for the fixed compensation plan</span></span>   |
| <span data-ttu-id="7b105-166">**Número da equipe**</span><span class="sxs-lookup"><span data-stu-id="7b105-166">**Personnel number**</span></span><br><span data-ttu-id="7b105-167">mshr_personnelnumber</span><span class="sxs-lookup"><span data-stu-id="7b105-167">mshr_personnelnumber</span></span><br><span data-ttu-id="7b105-168">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="7b105-168">*String*</span></span> | <span data-ttu-id="7b105-169">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="7b105-169">Read-only</span></span><br><span data-ttu-id="7b105-170">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="7b105-170">Required</span></span> |<span data-ttu-id="7b105-171">O número da equipe exclusiva do funcionário.</span><span class="sxs-lookup"><span data-stu-id="7b105-171">The employee's unique personnel number.</span></span>  |

<span data-ttu-id="7b105-172">**Consulta**</span><span class="sxs-lookup"><span data-stu-id="7b105-172">**Query**</span></span>

<span data-ttu-id="7b105-173">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="7b105-173">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollfixedcompensationplanentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

<span data-ttu-id="7b105-174">**Resposta**</span><span class="sxs-lookup"><span data-stu-id="7b105-174">**Response**</span></span>

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

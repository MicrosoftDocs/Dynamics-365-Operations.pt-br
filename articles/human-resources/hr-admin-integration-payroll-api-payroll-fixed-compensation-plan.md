---
title: Plano de remuneração fixa da folha de pagamento
description: Este tópico fornece detalhes e um exemplo de consulta da entidade Plano de remuneração fixa da folha de pagamento no Dynamics 365 Human Resources.
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
ms.openlocfilehash: 227082358c59abddd63f4faa4536a8df270a4d80
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059079"
---
# <a name="payroll-fixed-compensation-plan"></a><span data-ttu-id="b5cad-103">Plano de remuneração fixa da folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="b5cad-103">Payroll fixed compensation plan</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="b5cad-104">Este tópico fornece detalhes e um exemplo de consulta da entidade Plano de remuneração fixa da folha de pagamento no Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b5cad-104">This topic provides details and an example query for the Payroll fixed compensation plan entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="b5cad-105">Propriedades</span><span class="sxs-lookup"><span data-stu-id="b5cad-105">Properties</span></span>

| <span data-ttu-id="b5cad-106">Propriedade</span><span class="sxs-lookup"><span data-stu-id="b5cad-106">Property</span></span><br><span data-ttu-id="b5cad-107">**Nome físico**</span><span class="sxs-lookup"><span data-stu-id="b5cad-107">**Physical name**</span></span><br><span data-ttu-id="b5cad-108">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="b5cad-108">**_Type_**</span></span> | <span data-ttu-id="b5cad-109">Uso</span><span class="sxs-lookup"><span data-stu-id="b5cad-109">Use</span></span> | <span data-ttu-id="b5cad-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="b5cad-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="b5cad-111">**ID do Funcionário**</span><span class="sxs-lookup"><span data-stu-id="b5cad-111">**Employee ID**</span></span><br><span data-ttu-id="b5cad-112">mshr_fk_employee_id_value</span><span class="sxs-lookup"><span data-stu-id="b5cad-112">mshr_fk_employee_id_value</span></span><br><span data-ttu-id="b5cad-113">*GUID*</span><span class="sxs-lookup"><span data-stu-id="b5cad-113">*GUID*</span></span> | <span data-ttu-id="b5cad-114">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="b5cad-114">Read-only</span></span><br><span data-ttu-id="b5cad-115">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="b5cad-115">Required</span></span><br><span data-ttu-id="b5cad-116">Chave estrangeira: mshr_Employee_id da entidade mshr_payrollemployeeentity</span><span class="sxs-lookup"><span data-stu-id="b5cad-116">Foreign key:mshr_Employee_id of mshr_payrollemployeeentity entity</span></span>  | <span data-ttu-id="b5cad-117">ID do Funcionário</span><span class="sxs-lookup"><span data-stu-id="b5cad-117">Employee ID</span></span> |
| <span data-ttu-id="b5cad-118">**Taxa de pagamento**</span><span class="sxs-lookup"><span data-stu-id="b5cad-118">**Pay rate**</span></span><br><span data-ttu-id="b5cad-119">mshr_payrate</span><span class="sxs-lookup"><span data-stu-id="b5cad-119">mshr_payrate</span></span><br><span data-ttu-id="b5cad-120">*Decimal*</span><span class="sxs-lookup"><span data-stu-id="b5cad-120">*Decimal*</span></span> | <span data-ttu-id="b5cad-121">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="b5cad-121">Read-only</span></span><br><span data-ttu-id="b5cad-122">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="b5cad-122">Required</span></span> | <span data-ttu-id="b5cad-123">A taxa de pagamento definida no plano de remuneração fixa.</span><span class="sxs-lookup"><span data-stu-id="b5cad-123">Pay rate defined in fixed compensation plan.</span></span> |
| <span data-ttu-id="b5cad-124">**ID do Plano**</span><span class="sxs-lookup"><span data-stu-id="b5cad-124">**Plan ID**</span></span><br><span data-ttu-id="b5cad-125">mshr_planid</span><span class="sxs-lookup"><span data-stu-id="b5cad-125">mshr_planid</span></span><br><span data-ttu-id="b5cad-126">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="b5cad-126">*String*</span></span> | <span data-ttu-id="b5cad-127">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="b5cad-127">Read-only</span></span><br><span data-ttu-id="b5cad-128">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="b5cad-128">Required</span></span> |<span data-ttu-id="b5cad-129">Especifica o plano da remuneração.</span><span class="sxs-lookup"><span data-stu-id="b5cad-129">Specifies the compensation plan.</span></span>  |
| <span data-ttu-id="b5cad-130">**Válido a partir de**</span><span class="sxs-lookup"><span data-stu-id="b5cad-130">**Valid from**</span></span><br><span data-ttu-id="b5cad-131">mshr_validfrom</span><span class="sxs-lookup"><span data-stu-id="b5cad-131">mshr_validfrom</span></span><br><span data-ttu-id="b5cad-132">*Compensação de Data/Hora*</span><span class="sxs-lookup"><span data-stu-id="b5cad-132">*Date Time Offset*</span></span> |  <span data-ttu-id="b5cad-133">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="b5cad-133">Read-only</span></span><br><span data-ttu-id="b5cad-134">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="b5cad-134">Required</span></span> |<span data-ttu-id="b5cad-135">Data a partir da qual a remuneração fixa do funcionário é válida.</span><span class="sxs-lookup"><span data-stu-id="b5cad-135">Date the employee fixed compensation is valid from.</span></span>  |
| <span data-ttu-id="b5cad-136">**Entidade Plano de remuneração fixa da folha de pagamento**</span><span class="sxs-lookup"><span data-stu-id="b5cad-136">**Payroll Fixed Compensation Plan entity**</span></span><br><span data-ttu-id="b5cad-137">mshr_payrollfixedcompensationplanentityid</span><span class="sxs-lookup"><span data-stu-id="b5cad-137">mshr_payrollfixedcompensationplanentityid</span></span><br><span data-ttu-id="b5cad-138">*GUID*</span><span class="sxs-lookup"><span data-stu-id="b5cad-138">*GUID*</span></span> | <span data-ttu-id="b5cad-139">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="b5cad-139">Required</span></span><br><span data-ttu-id="b5cad-140">Gerado pelo sistema</span><span class="sxs-lookup"><span data-stu-id="b5cad-140">Sytem generated</span></span> | <span data-ttu-id="b5cad-141">Um valor GUID gerado pelo sistema para identificar exclusivamente o plano de remuneração.</span><span class="sxs-lookup"><span data-stu-id="b5cad-141">A system-generated GUID value to uniquely identify the compensation plan.</span></span> |
| <span data-ttu-id="b5cad-142">**Frequência de pagamento**</span><span class="sxs-lookup"><span data-stu-id="b5cad-142">**Pay frequency**</span></span><br><span data-ttu-id="b5cad-143">mshr_payfrequency</span><span class="sxs-lookup"><span data-stu-id="b5cad-143">mshr_payfrequency</span></span><br><span data-ttu-id="b5cad-144">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="b5cad-144">*String*</span></span> | <span data-ttu-id="b5cad-145">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="b5cad-145">Read-only</span></span><br><span data-ttu-id="b5cad-146">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="b5cad-146">Required</span></span> |<span data-ttu-id="b5cad-147">A frequência com que o funcionário será pago.</span><span class="sxs-lookup"><span data-stu-id="b5cad-147">The frequency the employee will be paid.</span></span>  |
| <span data-ttu-id="b5cad-148">**Válida até**</span><span class="sxs-lookup"><span data-stu-id="b5cad-148">**Valid to**</span></span><br><span data-ttu-id="b5cad-149">mshr_validto</span><span class="sxs-lookup"><span data-stu-id="b5cad-149">mshr_validto</span></span><br><span data-ttu-id="b5cad-150">*Compensação de Data/Hora*</span><span class="sxs-lookup"><span data-stu-id="b5cad-150">*Date Time Offset*</span></span> | <span data-ttu-id="b5cad-151">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="b5cad-151">Read-only</span></span> <br><span data-ttu-id="b5cad-152">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="b5cad-152">Required</span></span> | <span data-ttu-id="b5cad-153">Data até a qual a remuneração fixa do funcionário é válida.</span><span class="sxs-lookup"><span data-stu-id="b5cad-153">Date the employee fixed compensation is valid to.</span></span> |
| <span data-ttu-id="b5cad-154">**ID da posição**</span><span class="sxs-lookup"><span data-stu-id="b5cad-154">**Position ID**</span></span><br><span data-ttu-id="b5cad-155">mshr_positionid</span><span class="sxs-lookup"><span data-stu-id="b5cad-155">mshr_positionid</span></span><br><span data-ttu-id="b5cad-156">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="b5cad-156">*String*</span></span> | <span data-ttu-id="b5cad-157">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="b5cad-157">Read-only</span></span> <br><span data-ttu-id="b5cad-158">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="b5cad-158">Required</span></span> | <span data-ttu-id="b5cad-159">ID da posição associada ao funcionário e ao registro do plano de remuneração fixa.</span><span class="sxs-lookup"><span data-stu-id="b5cad-159">Postion ID associated with the employee and fixed compensation plan enrollment.</span></span> |
| <span data-ttu-id="b5cad-160">**Moeda**</span><span class="sxs-lookup"><span data-stu-id="b5cad-160">**Currency**</span></span><br><span data-ttu-id="b5cad-161">mshr_currency</span><span class="sxs-lookup"><span data-stu-id="b5cad-161">mshr_currency</span></span><br><span data-ttu-id="b5cad-162">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="b5cad-162">*String*</span></span> | <span data-ttu-id="b5cad-163">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="b5cad-163">Read-only</span></span> <br><span data-ttu-id="b5cad-164">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="b5cad-164">Required</span></span> |<span data-ttu-id="b5cad-165">A moeda definida para o plano de remuneração fixa</span><span class="sxs-lookup"><span data-stu-id="b5cad-165">The currency defined for the fixed compensation plan</span></span>   |
| <span data-ttu-id="b5cad-166">**Número da equipe**</span><span class="sxs-lookup"><span data-stu-id="b5cad-166">**Personnel number**</span></span><br><span data-ttu-id="b5cad-167">mshr_personnelnumber</span><span class="sxs-lookup"><span data-stu-id="b5cad-167">mshr_personnelnumber</span></span><br><span data-ttu-id="b5cad-168">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="b5cad-168">*String*</span></span> | <span data-ttu-id="b5cad-169">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="b5cad-169">Read-only</span></span><br><span data-ttu-id="b5cad-170">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="b5cad-170">Required</span></span> |<span data-ttu-id="b5cad-171">O número da equipe exclusiva do funcionário.</span><span class="sxs-lookup"><span data-stu-id="b5cad-171">The employee's unique personnel number.</span></span>  |

<span data-ttu-id="b5cad-172">**Consulta**</span><span class="sxs-lookup"><span data-stu-id="b5cad-172">**Query**</span></span>

<span data-ttu-id="b5cad-173">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="b5cad-173">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollfixedcompensationplanentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

<span data-ttu-id="b5cad-174">**Resposta**</span><span class="sxs-lookup"><span data-stu-id="b5cad-174">**Response**</span></span>

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

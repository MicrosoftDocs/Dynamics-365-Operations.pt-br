---
title: Endereço do trabalhador da folha de pagamento
description: Este tópico fornece detalhes e um exemplo de consulta da entidade Endereço do trabalhador da folha de pagamento no Dynamics 365 Human Resources.
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
ms.openlocfilehash: 6d93c38b21e953446142fc32cc2a0911616ac61d
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881926"
---
# <a name="payroll-worker-address"></a><span data-ttu-id="c611e-103">Endereço do trabalhador da folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="c611e-103">Payroll worker address</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="c611e-104">Este tópico fornece detalhes e um exemplo de consulta da entidade Endereço do trabalhador da folha de pagamento no Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="c611e-104">This topic provides details and an example query for the Payroll worker address entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="c611e-105">Propriedades</span><span class="sxs-lookup"><span data-stu-id="c611e-105">Properties</span></span>

| <span data-ttu-id="c611e-106">Propriedade</span><span class="sxs-lookup"><span data-stu-id="c611e-106">Property</span></span><br><span data-ttu-id="c611e-107">**Nome físico**</span><span class="sxs-lookup"><span data-stu-id="c611e-107">**Physical name**</span></span><br><span data-ttu-id="c611e-108">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="c611e-108">**_Type_**</span></span> | <span data-ttu-id="c611e-109">Usar</span><span class="sxs-lookup"><span data-stu-id="c611e-109">Use</span></span> | <span data-ttu-id="c611e-110">descrição</span><span class="sxs-lookup"><span data-stu-id="c611e-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="c611e-111">**Cidade**</span><span class="sxs-lookup"><span data-stu-id="c611e-111">**City**</span></span><br><span data-ttu-id="c611e-112">mshr_city</span><span class="sxs-lookup"><span data-stu-id="c611e-112">mshr_city</span></span><br><span data-ttu-id="c611e-113">*Sequência de caracteres*</span><span class="sxs-lookup"><span data-stu-id="c611e-113">*String*</span></span> | <span data-ttu-id="c611e-114">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="c611e-114">Read-only</span></span><br><span data-ttu-id="c611e-115">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="c611e-115">Required</span></span> | <span data-ttu-id="c611e-116">A cidade definida para o endereço.</span><span class="sxs-lookup"><span data-stu-id="c611e-116">The city defined for the address.</span></span>   |
| <span data-ttu-id="c611e-117">**Número da equipe**</span><span class="sxs-lookup"><span data-stu-id="c611e-117">**Personnel number**</span></span><br><span data-ttu-id="c611e-118">mshr_personnelnumber</span><span class="sxs-lookup"><span data-stu-id="c611e-118">mshr_personnelnumber</span></span><br><span data-ttu-id="c611e-119">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="c611e-119">*String*</span></span> | <span data-ttu-id="c611e-120">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="c611e-120">Read-only</span></span><br><span data-ttu-id="c611e-121">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="c611e-121">Required</span></span> | <span data-ttu-id="c611e-122">O número da equipe exclusiva do funcionário.</span><span class="sxs-lookup"><span data-stu-id="c611e-122">The employee's unique personnel number.</span></span>  |
| <span data-ttu-id="c611e-123">**País/região**</span><span class="sxs-lookup"><span data-stu-id="c611e-123">**Country region**</span></span><br><span data-ttu-id="c611e-124">mshr_countryregionid</span><span class="sxs-lookup"><span data-stu-id="c611e-124">mshr_countryregionid</span></span><br><span data-ttu-id="c611e-125">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="c611e-125">*String*</span></span> | <span data-ttu-id="c611e-126">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="c611e-126">Read-only</span></span><br><span data-ttu-id="c611e-127">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="c611e-127">Required</span></span> | <span data-ttu-id="c611e-128">O país ou região definida para o endereço</span><span class="sxs-lookup"><span data-stu-id="c611e-128">The country region defined for the address</span></span>  |
| <span data-ttu-id="c611e-129">**Válido a partir de**</span><span class="sxs-lookup"><span data-stu-id="c611e-129">**Valid from**</span></span><br><span data-ttu-id="c611e-130">mshr_postaladdressvalidfrom</span><span class="sxs-lookup"><span data-stu-id="c611e-130">mshr_postaladdressvalidfrom</span></span><br><span data-ttu-id="c611e-131">*Compensação de Data/Hora*</span><span class="sxs-lookup"><span data-stu-id="c611e-131">*Date Time Offset*</span></span> | <span data-ttu-id="c611e-132">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="c611e-132">Read-only</span></span> <br><span data-ttu-id="c611e-133">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="c611e-133">Required</span></span> | <span data-ttu-id="c611e-134">Data a partir da qual o endereço é válido.</span><span class="sxs-lookup"><span data-stu-id="c611e-134">The date the address is valid from.</span></span> |
| <span data-ttu-id="c611e-135">**Endereço em que trabalhou**</span><span class="sxs-lookup"><span data-stu-id="c611e-135">**Worked in address**</span></span><br><span data-ttu-id="c611e-136">mshr_isworkedinaddressbr>*Int32*</span><span class="sxs-lookup"><span data-stu-id="c611e-136">mshr_isworkedinaddressbr>*Int32*</span></span> | <span data-ttu-id="c611e-137">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="c611e-137">Read-only</span></span><br><span data-ttu-id="c611e-138">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="c611e-138">Required</span></span> | <span data-ttu-id="c611e-139">Indica se o endereço é onde o funcionário trabalha.</span><span class="sxs-lookup"><span data-stu-id="c611e-139">Denotes if the address is where the employee works.</span></span> |
| <span data-ttu-id="c611e-140">**Município**</span><span class="sxs-lookup"><span data-stu-id="c611e-140">**County**</span></span><br><span data-ttu-id="c611e-141">mshr_county</span><span class="sxs-lookup"><span data-stu-id="c611e-141">mshr_county</span></span><br><span data-ttu-id="c611e-142">*Sequência de caracteres*</span><span class="sxs-lookup"><span data-stu-id="c611e-142">*String*</span></span> | <span data-ttu-id="c611e-143">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="c611e-143">Read-only</span></span><br><span data-ttu-id="c611e-144">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="c611e-144">Required</span></span> | <span data-ttu-id="c611e-145">O município definido para o endereço.</span><span class="sxs-lookup"><span data-stu-id="c611e-145">The county defined for the address.</span></span>  |
| <span data-ttu-id="c611e-146">**ID do endereço do trabalhador da folha de pagamento**</span><span class="sxs-lookup"><span data-stu-id="c611e-146">**Payroll worker address ID**</span></span><br><span data-ttu-id="c611e-147">mshr_payrollworkeraddressentityid</span><span class="sxs-lookup"><span data-stu-id="c611e-147">mshr_payrollworkeraddressentityid</span></span><br><span data-ttu-id="c611e-148">*GUID*</span><span class="sxs-lookup"><span data-stu-id="c611e-148">*GUID*</span></span> | <span data-ttu-id="c611e-149">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="c611e-149">Required</span></span><br><span data-ttu-id="c611e-150">Gerado pelo sistema</span><span class="sxs-lookup"><span data-stu-id="c611e-150">System generated</span></span> | <span data-ttu-id="c611e-151">Um valor GUID gerado pelo sistema para identificar exclusivamente o endereço.</span><span class="sxs-lookup"><span data-stu-id="c611e-151">A system-generated GUID value to uniquely identify the address.</span></span>  |
| <span data-ttu-id="c611e-152">**Campo principal**</span><span class="sxs-lookup"><span data-stu-id="c611e-152">**Primary field**</span></span><br><span data-ttu-id="c611e-153">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="c611e-153">mshr_primaryfield</span></span><br><span data-ttu-id="c611e-154">*Sequência de caracteres*</span><span class="sxs-lookup"><span data-stu-id="c611e-154">*String*</span></span> | <span data-ttu-id="c611e-155">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="c611e-155">Read-only</span></span><br><span data-ttu-id="c611e-156">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="c611e-156">Required</span></span> |  |
| <span data-ttu-id="c611e-157">**Rua**</span><span class="sxs-lookup"><span data-stu-id="c611e-157">**Street**</span></span><br><span data-ttu-id="c611e-158">mshr_street</span><span class="sxs-lookup"><span data-stu-id="c611e-158">mshr_street</span></span><br><span data-ttu-id="c611e-159">*Sequência de caracteres*</span><span class="sxs-lookup"><span data-stu-id="c611e-159">*String*</span></span> | <span data-ttu-id="c611e-160">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="c611e-160">Read-only</span></span><br><span data-ttu-id="c611e-161">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="c611e-161">Required</span></span> | <span data-ttu-id="c611e-162">A rua definida para o endereço.</span><span class="sxs-lookup"><span data-stu-id="c611e-162">The street defined for the address.</span></span> |
| <span data-ttu-id="c611e-163">**Válida até**</span><span class="sxs-lookup"><span data-stu-id="c611e-163">**Valid to**</span></span><br><span data-ttu-id="c611e-164">mshr_postaladdressvalidto</span><span class="sxs-lookup"><span data-stu-id="c611e-164">mshr_postaladdressvalidto</span></span><br><span data-ttu-id="c611e-165">*Compensação de Data/Hora*</span><span class="sxs-lookup"><span data-stu-id="c611e-165">*Date Time Offset*</span></span> | <span data-ttu-id="c611e-166">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="c611e-166">Read-only</span></span> <br><span data-ttu-id="c611e-167">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="c611e-167">Required</span></span> | <span data-ttu-id="c611e-168">Data até a qual o endereço é válido.</span><span class="sxs-lookup"><span data-stu-id="c611e-168">The date the address is valid to.</span></span>  |
| <span data-ttu-id="c611e-169">**ID da localização**</span><span class="sxs-lookup"><span data-stu-id="c611e-169">**Location ID**</span></span><br><span data-ttu-id="c611e-170">mshr_locationidbr>*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="c611e-170">mshr_locationidbr>*String*</span></span> | <span data-ttu-id="c611e-171">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="c611e-171">Read-only</span></span> <br><span data-ttu-id="c611e-172">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="c611e-172">Required</span></span> | <span data-ttu-id="c611e-173">A ID do endereço.</span><span class="sxs-lookup"><span data-stu-id="c611e-173">The ID for the address.</span></span>  |
| <span data-ttu-id="c611e-174">**CEP**</span><span class="sxs-lookup"><span data-stu-id="c611e-174">**Postal code**</span></span><br><span data-ttu-id="c611e-175">mshr_zipcode</span><span class="sxs-lookup"><span data-stu-id="c611e-175">mshr_zipcode</span></span><br><span data-ttu-id="c611e-176">*Sequência de caracteres*</span><span class="sxs-lookup"><span data-stu-id="c611e-176">*String*</span></span> | <span data-ttu-id="c611e-177">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="c611e-177">Read-only</span></span> <br><span data-ttu-id="c611e-178">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="c611e-178">Required</span></span> |<span data-ttu-id="c611e-179">O número de identificação definido para o funcionário.</span><span class="sxs-lookup"><span data-stu-id="c611e-179">The identification number defined for the employee.</span></span>  |
| <span data-ttu-id="c611e-180">**Endereço em que morou**</span><span class="sxs-lookup"><span data-stu-id="c611e-180">**Lived in address**</span></span><br><span data-ttu-id="c611e-181">mshr_islivedinaddressbr>*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="c611e-181">mshr_islivedinaddressbr>*String*</span></span> | <span data-ttu-id="c611e-182">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="c611e-182">Read-only</span></span><br><span data-ttu-id="c611e-183">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="c611e-183">Required</span></span> | <span data-ttu-id="c611e-184">Indica se o endereço é onde o funcionário mora.</span><span class="sxs-lookup"><span data-stu-id="c611e-184">Denotes if the address is where the employee lives.</span></span> |
| <span data-ttu-id="c611e-185">**Estado**</span><span class="sxs-lookup"><span data-stu-id="c611e-185">**State**</span></span><br><span data-ttu-id="c611e-186">mshr_state</span><span class="sxs-lookup"><span data-stu-id="c611e-186">mshr_state</span></span><br><span data-ttu-id="c611e-187">*Sequência de caracteres*</span><span class="sxs-lookup"><span data-stu-id="c611e-187">*String*</span></span> | <span data-ttu-id="c611e-188">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="c611e-188">Read-only</span></span><br><span data-ttu-id="c611e-189">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="c611e-189">Required</span></span> | <span data-ttu-id="c611e-190">O estado definido para o endereço.</span><span class="sxs-lookup"><span data-stu-id="c611e-190">The state defined for the address.</span></span>  |

## <a name="example-query"></a><span data-ttu-id="c611e-191">Exemplo de consulta</span><span class="sxs-lookup"><span data-stu-id="c611e-191">Example query</span></span>

<span data-ttu-id="c611e-192">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="c611e-192">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollworkeraddressentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_postaladdressvalidfrom le @asofdate and mshr_postaladdressvalidto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

<span data-ttu-id="c611e-193">**Resposta**</span><span class="sxs-lookup"><span data-stu-id="c611e-193">**Response**</span></span>

```json
{
            "mshr_personnelnumber": "000041",
            "mshr_locationid": "000000538",
            "mshr_islivedinaddress": 200000001,
            "mshr_isworkedinaddress": 200000000,
            "mshr_countryregionid": "USA",
            "mshr_zipcode": "99025",
            "mshr_street": "6543 Cypress Ave",
            "mshr_city": "Tacoma",
            "mshr_state": "WA",
            "mshr_county": "KING",
            "mshr_postaladdressvalidfrom": "2012-09-20T20:14:27Z",
            "mshr_postaladdressvalidto": "2154-12-31T23:59:59Z",
            "mshr_primaryfield": "000041 | 000000538 | 9/20/2012 08:14:27 pm",
            "_mshr_fk_worker_id_value": "00000d3c-0000-0000-d5ff-004105000000",
            "mshr_payrollworkeraddressentityid": "000006f0-0000-0000-f90f-014105000000"

}
```

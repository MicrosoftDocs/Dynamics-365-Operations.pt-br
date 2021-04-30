---
title: Gerar e revisar entidades da folha de pagamento
description: Este tópico descreve como gerar e revisar entidades da folha de pagamento.
author: andreabichsel
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
ms.openlocfilehash: c6e043498d4e36e38575a16c6475a5edfef51fc6
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881927"
---
# <a name="generate-payroll-entities"></a><span data-ttu-id="28c6f-103">Gerar entidades da folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="28c6f-103">Generate payroll entities</span></span>

<span data-ttu-id="28c6f-104">Use esta função OData para gerar as entidades necessárias para a integração da folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="28c6f-104">Use this OData function to generate the entities needed for payroll integration.</span></span> <span data-ttu-id="28c6f-105">Se forem feitas alterações nessas entidades em Human Resources, como a adição de campos personalizados, essa função poderá ser chamada novamente para atualizar os metadados de cada entidade.</span><span class="sxs-lookup"><span data-stu-id="28c6f-105">If any changes are made to these entities in Human Resources, such as adding custom fields, this function can be called again to refresh the metadata of each entity.</span></span> <span data-ttu-id="28c6f-106">A resposta contém uma ID de operação que pode ser monitorada para que você saiba quando o processo de geração foi concluído.</span><span class="sxs-lookup"><span data-stu-id="28c6f-106">The response contains an operation ID that you can monitor so you know when the generation process has completed.</span></span>

<span data-ttu-id="28c6f-107">**Solicitar**</span><span class="sxs-lookup"><span data-stu-id="28c6f-107">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/RefreshHumanResourcesVirtualEntities
```

<span data-ttu-id="28c6f-108">**Corpo**</span><span class="sxs-lookup"><span data-stu-id="28c6f-108">**body**</span></span>

```json
{
    "PhysicalNames" : ["PayrollEmployeeEntity", "HcmWorkerBaseEntity", "PayrollPositionEntity", "PayrollPositionJobEntity", "PayrollWorkerAddressEntity", "HcmJobDetailEntity", "HcmCompFixedPlanTableEntity", "PayrollFixedCompensationPlanEntity", "HcmEmploymentDetailEntity"]
}
```

<span data-ttu-id="28c6f-109">**Resposta**</span><span class="sxs-lookup"><span data-stu-id="28c6f-109">**Response**</span></span>

```json
{
    "AsyncOperationId": "8b98d338-f939-4c86-9a91-80b76b6ab2ea"
}
```

## <a name="review-payroll-entities"></a><span data-ttu-id="28c6f-110">Analise entidades da folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="28c6f-110">Review payroll entities</span></span>

<span data-ttu-id="28c6f-111">Use esta API para recuperar uma lista das entidades que foram geradas com êxito e estão prontas para uso.</span><span class="sxs-lookup"><span data-stu-id="28c6f-111">Use this API to retrieve a list of the entities that have been successfully generated and are ready for use.</span></span>

<span data-ttu-id="28c6f-112">**Solicitar**</span><span class="sxs-lookup"><span data-stu-id="28c6f-112">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_hrvirtualentitycatalogs?$filter=mshr_hasbeengenerated eq true
```

<span data-ttu-id="28c6f-113">**Resposta**</span><span class="sxs-lookup"><span data-stu-id="28c6f-113">**Response**</span></span>

```json
{
      "value": [
        {
            "mshr_physicalname": "PayrollWorkerAddressEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-1c00-005001000000",
            "mshr_refresh": null
        },
        {
            "mshr_physicalname": "HcmJobDetailEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-6400-005001000000",
            "mshr_refresh": null
        },
        {
            "mshr_physicalname": "HcmCompFixedPlanTableEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-6b00-005001000000",
            "mshr_refresh": null
        },
        {
            "mshr_physicalname": "PayrollEmployeeEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-6d00-005001000000",
            "mshr_refresh": null
        },
        {
            "mshr_physicalname": "HcmEmploymentDetailEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-7e00-005001000000",
            "mshr_refresh": null
        },
        {
            "mshr_physicalname": "PayrollFixedCompensationPlanEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-9300-005001000000",
            "mshr_refresh": null
        },
        {
            "mshr_physicalname": "HcmWorkerBaseEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-c000-005001000000",
            "mshr_refresh": null
        },
        {
            "mshr_physicalname": "PayrollPositionJobEntity",
            "mshr_hasbeengenerated": true,
            "mshr_hrvirtualentitycatalogid": "00000603-0000-0000-e700-005001000000",
            "mshr_refresh": null
        }
    ]
}
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
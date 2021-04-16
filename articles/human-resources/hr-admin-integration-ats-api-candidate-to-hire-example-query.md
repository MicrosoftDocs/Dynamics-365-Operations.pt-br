---
title: Exemplo de consulta de candidato a ser contratado
description: Este tópico fornece um exemplo de consulta da entidade de candidato a ser contratado no Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ea6fc745ffb5892a32196394cb28cb5e646b7639
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795060"
---
# <a name="example-query-for-candidate-to-hire"></a><span data-ttu-id="9e7db-103">Exemplo de consulta de candidato a ser contratado</span><span class="sxs-lookup"><span data-stu-id="9e7db-103">Example query for Candidate to hire</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="9e7db-104">Este tópico fornece um exemplo de consulta da entidade de candidato a ser contratado no Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="9e7db-104">This topic provides an example query for the Candidate to hire entity in Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="9e7db-105">Este tópico fornece um exemplo demonstrando como você pode usar *inserções profundas* para criar todos os detalhes de um novo registro de candidato em uma única operação de API.</span><span class="sxs-lookup"><span data-stu-id="9e7db-105">This topic provides an example demonstrating how you can use *deep inserts* to create all the detail of a new candidate record in a single API operation.</span></span> <span data-ttu-id="9e7db-106">Para obter mais informações sobre inserções profundas, consulte [Criar registros de entidades relacionadas em uma operação](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/create-entity-web-api#create-related-entity-records-in-one-operation).</span><span class="sxs-lookup"><span data-stu-id="9e7db-106">For more information about deep inserts, see [Create related entity records in one operation](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/create-entity-web-api#create-related-entity-records-in-one-operation).</span></span>

<span data-ttu-id="9e7db-107">A entidade **mshr_hcmcandidatetohireentity** é única devido à sua relação com a entidade **mshr_dirpersonentity**.</span><span class="sxs-lookup"><span data-stu-id="9e7db-107">The **mshr_hcmcandidatetohireentity** entity is unique because of its relationship to the **mshr_dirpersonentity** entity.</span></span> <span data-ttu-id="9e7db-108">Muitas das propriedades em **mshr_hcmcandidatetohireentity** (por exemplo, **mshr_firstname**, **mshr_lastname** e **mshr_birthdate**) derivam do registro **mshr_dirpersonentity**.</span><span class="sxs-lookup"><span data-stu-id="9e7db-108">Many of the properties on the **mshr_hcmcandidatetohireentity** (for example, **mshr_firstname**, **mshr_lastname**, and **mshr_birthdate**) are derived from the **mshr_dirpersonentity** record.</span></span> <span data-ttu-id="9e7db-109">Se você lançar um novo registro de candidato em **mshr_hcmcandidatetohireentity** sem usar inserções profundas, poderá definir valores para essas propriedades diretamente no registro **mshr_hcmcandidatetohireentity**.</span><span class="sxs-lookup"><span data-stu-id="9e7db-109">If you post a new candidate record to **mshr_hcmcandidatetohireentity** without using deep inserts, you can define values for these properties directly on the **mshr_hcmcandidatetohireentity** record.</span></span> <span data-ttu-id="9e7db-110">O registro **mshr_dirpersonentity associado** é criado implicitamente com os valores definidos para as propriedades.</span><span class="sxs-lookup"><span data-stu-id="9e7db-110">The associated **mshr_dirpersonentity** record is created implicitly with the defined values for the properties.</span></span> <span data-ttu-id="9e7db-111">Em seguida, você pode criar outros registros de entidades relacionadas (como habilidades ou educação) como chamadas separadas da API.</span><span class="sxs-lookup"><span data-stu-id="9e7db-111">You can then create any other related entity records (such as skills or education) as separate API calls.</span></span>

<span data-ttu-id="9e7db-112">Se, no entanto, você quiser usar inserções profundas para criar todas as entidades relacionadas em uma operação, as propriedades específicas da entidade **mshr_dirpersonentity** deverão ser definidas nesse nível aninhado da operação.</span><span class="sxs-lookup"><span data-stu-id="9e7db-112">If, however, you want to use deep inserts to create all related entities in one operation, the properties specific to the **mshr_dirpersonentity** entity must be defined on that nested level of the operation.</span></span>

<span data-ttu-id="9e7db-113">Este exemplo mostra como você pode criar um registro de candidato, o registro de pessoa associada e as habilidades e educação da pessoa em três níveis aninhados usando inserções profundas em uma única operação de API.</span><span class="sxs-lookup"><span data-stu-id="9e7db-113">This example shows how you can create a candidate record, the associated person record, and the person's skills and education in three nested levels using deep inserts in a single API operation.</span></span>

> [!NOTE]
> <span data-ttu-id="9e7db-114">O exemplo não inclui todas as propriedades de cada uma das entidades da API.</span><span class="sxs-lookup"><span data-stu-id="9e7db-114">The example does not include all properties of each of the API entities.</span></span> <span data-ttu-id="9e7db-115">Ele foi simplificado para fins de demonstração.</span><span class="sxs-lookup"><span data-stu-id="9e7db-115">It is simplified for demonstration purposes.</span></span>

<span data-ttu-id="9e7db-116">**Solicitar**</span><span class="sxs-lookup"><span data-stu-id="9e7db-116">**Request**</span></span>

```http

POST [Organization URI]/api/data/v9.1/mshr_hcmcandidatetohireentities
Content-Type: application/json; charset=utf-8
OData-MaxVersion: 4.0
OData-Version: 4.0
Accept: application/json

{
    "mshr_dataareaid": "usmf",
    "mshr_recruitingrequestid": "USMF-000141",
    "mshr_positionid": "000601",
    "mshr_iswillingtorelocate": 200000000,
    "mshr_availabilitydate": "2021-03-18",
    "mshr_comments": "Evelyn's experience is exactly what we need for this position.",
    "mshr_FK_Person_id":
        {
            "mshr_firstname": "Evelyn",
            "mshr_lastname": "Chambers",
            "mshr_namesequencedisplayas": "FirstMiddleLast",
            "mshr_FK_HcmPersonSkillEntity_Person":
            [
                {
                    "mshr_skillid": "CustFocus",
                    "mshr_ratingid": "Skills",
                    "mshr_levelid": "4",
                    "mshr_ratinglevelexaminer": "",
                    "mshr_leveltype": 200000000,
                    "mshr_yearsofexperience": 0,
                    "mshr_verified": 200000000,
                    "mshr_leveldate": "2013-01-01T00:00:00Z"
                },
                {
                    "mshr_skillid": "CashFlow",
                    "mshr_ratingid": "Skills",
                    "mshr_levelid": "4",
                    "mshr_ratinglevelexaminer": "",
                    "mshr_leveltype": 200000000,
                    "mshr_yearsofexperience": 0,
                    "mshr_verified": 200000000,
                    "mshr_leveldate": "2013-01-01T00:00:00Z"
                }
            ],
            "mshr_FK_HcmPersonEducationEntity_Person": [
                {
                    "mshr_creditbasis": 200000000,
                    "mshr_enddate": "2021-02-22T00:00:00Z",
                    "mshr_educationlevelid": "Bachelor",
                    "mshr_creditsearned": 0,
                    "mshr_startdate": "2017-02-21T00:00:00Z",
                    "mshr_creditscompleted": 0,
                    "mshr_educationinstitutionid": "Cottonwood Univ",
                    "mshr_educationdisciplineid": "Business Mgmt",
                    "mshr_durationunit": 200000000
                }              
            ]
        }
}
```

<span data-ttu-id="9e7db-117">**Resposta**</span><span class="sxs-lookup"><span data-stu-id="9e7db-117">**Response**</span></span>

```http

HTTP/1/1 204 No Content
OData-Version: 4.0
OData-EntityId: [Organization URI]/api/data/v9.1/mshr_hcmcandidatetohireentities(00000d2d-0000-0000-7317-005001000000)

```

## <a name="see-also"></a><span data-ttu-id="9e7db-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="9e7db-118">See also</span></span>

[<span data-ttu-id="9e7db-119">Introdução da API de integração do sistema de acompanhamento de candidatos</span><span class="sxs-lookup"><span data-stu-id="9e7db-119">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
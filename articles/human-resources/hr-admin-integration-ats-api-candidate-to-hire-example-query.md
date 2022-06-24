---
title: Exemplo de consulta de candidato a ser contratado
description: Este artigo fornece um exemplo de consulta da entidade Candidato a ser contratado no Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2dd744665d4f0b6c64f4ee45a01c237081018514
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8848332"
---
# <a name="example-query-for-candidate-to-hire"></a>Exemplo de consulta de candidato a ser contratado


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artigo fornece um exemplo de consulta da entidade Candidato a ser contratado no Dynamics 365 Human Resources.

Este artigo fornece um exemplo demonstrando como você pode usar *inserções profundas* para criar todos os detalhes de um novo registro de candidato em uma única operação de API. Para obter mais informações sobre inserções profundas, consulte [Criar registros de entidades relacionadas em uma operação](/powerapps/developer/data-platform/webapi/create-entity-web-api#create-related-entity-records-in-one-operation).

A entidade **mshr_hcmcandidatetohireentity** é única devido à sua relação com a entidade **mshr_dirpersonentity**. Muitas das propriedades em **mshr_hcmcandidatetohireentity** (por exemplo, **mshr_firstname**, **mshr_lastname** e **mshr_birthdate**) derivam do registro **mshr_dirpersonentity**. Se você lançar um novo registro de candidato em **mshr_hcmcandidatetohireentity** sem usar inserções profundas, poderá definir valores para essas propriedades diretamente no registro **mshr_hcmcandidatetohireentity**. O registro **mshr_dirpersonentity associado** é criado implicitamente com os valores definidos para as propriedades. Em seguida, você pode criar outros registros de entidades relacionadas (como habilidades ou educação) como chamadas separadas da API.

Se, no entanto, você quiser usar inserções profundas para criar todas as entidades relacionadas em uma operação, as propriedades específicas da entidade **mshr_dirpersonentity** deverão ser definidas nesse nível aninhado da operação.

Este exemplo mostra como você pode criar um registro de candidato, o registro de pessoa associada e as habilidades e educação da pessoa em três níveis aninhados usando inserções profundas em uma única operação de API.

> [!NOTE]
> O exemplo não inclui todas as propriedades de cada uma das entidades da API. Ele foi simplificado para fins de demonstração.

**Solicitar**

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

**Resposta**

```http

HTTP/1/1 204 No Content
OData-Version: 4.0
OData-EntityId: [Organization URI]/api/data/v9.1/mshr_hcmcandidatetohireentities(00000d2d-0000-0000-7317-005001000000)

```

## <a name="see-also"></a>Consulte também

[Introdução da API de integração do sistema de acompanhamento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>


[!INCLUDE[footer-include](../includes/footer-banner.md)]

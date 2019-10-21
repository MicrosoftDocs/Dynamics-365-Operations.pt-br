---
title: Hierarquia da organização no Common Data Service
description: Este tópico descreve a integração de dados organizacionais entre os aplicativos do Finance and Operations e o Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: fd159b38f69305dcaecb364ba0ccb3befabb3582
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182016"
---
## <a name="organization-hierarchy-in-common-data-service"></a>Hierarquia da organização no Common Data Service

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

Como o Dynamics 365 Finance é um sistema financeiro, a *organização* é um conceito básico. A configuração do sistema começa com a configuração de uma hierarquia da organização. As finanças comerciais podem ser rastreadas em nível organizacional e também em qualquer nível da hierarquia da organização.

Embora o Common Data Service não tenha o conceito de uma hierarquia da organização, ele tem alguns conceitos soltos, como receita total de venda. Como parte da integração do Common Data Service, a estrutura de dados da hierarquia da organização é adicionada ao Common Data Service.

## <a name="data-flow"></a>Fluxo de dados

Um ecossistema comercial que consiste em aplicativos do Finance and Operations e no Common Data Service continuará a ter uma hierarquia da organização. Essa hierarquia da organização é criada nos aplicativos do Finance and Operations, mas é exposta no Common Data Service para fins informativos e de extensibilidade. A ilustração a seguir mostra informações da hierarquia da organização que é exposta no Common Data Service como um fluxo de dados unidirecional de aplicativos do Finance and Operations para o Common Data Service.

![Imagem de arquitetura](media/dual-write-data-flow.png)

## <a name="templates"></a>Modelos

Os mapas de entidades da hierarquia da organização estão disponíveis para sincronização unidirecional de dados de aplicativos do Finance and Operations para o Common Data Service.

[!include [banner](../includes/dual-write-symbols.md)]

## <a name="internal-organization-hierarchy-purpose"></a>Finalidade da hierarquia da organização interna

Este modelo oferece sincronização unidirecional da entidade de Finalidade da Hierarquia da Organização do Finance and Operations para outros aplicativos do Dynamics 365.

<!-- ![architecture image](media/dual-write-purpose.png) -->

Campo de origem | Tipo de mapa | Campo de destino
---|---|---
HIERARCHYTYPE | \> | msdyn\_hierarchypurposetypename
HIERARCHYTYPE | \> | msdyn\_hierarchytype.msdyn\_name
HIERARCHYPURPOSE | \>\> | msdyn\_hierarchypurpose
IMMUTABLE | \>\> | msdyn\_immutable
SETASDEFAULT | \>\> | msdyn\_setasdefault

## <a name="internal-organization-hierarchy-type"></a>Tipo de hierarquia da organização interna

Este modelo oferece sincronização unidirecional da entidade de Tipo de Hierarquia da Organização do Finance and Operations para outros aplicativos do Dynamics 365.

<!-- ![architecture image](media/dual-write-type.png) -->

Campo de origem | Tipo de mapa | Campo de destino
---|---|---
NOME | \> | msdyn\_name

## <a name="internal-organization-hierarchy"></a>Hierarquia da organização interna

Este modelo oferece sincronização unidirecional da entidade de Hierarquia da Organização Publicada do Finance and Operations para outros aplicativos do Dynamics 365.

<!-- ![architecture image](media/dual-write-organization.png) -->

Campo de origem | Tipo de mapa | Campo de destino
---|---|---
VALIDTO | \> | msdyn\_validto
VALIDFROM | \> | msdyn\_validfrom
HIERARCHYTYPE | \> | msdyn\_hierarchytypename
PARENTORGANIZATIONPARTYNUMBER | \> | msdyn\_parentpartyid
CHILDORGANIZATIONPARTYNUMBER | \> | msdyn\_childpartyid
HIERARCHYTYPE | \> | msdyn\_hierarchytypeid.msdyn\_name
CHILDORGANIZATIONPARTYNUMBER | \> | msdyn\_childid.msdyn\_partynumber
PARENTORGANIZATIONPARTYNUMBER | \> | msdyn\_parentid.msdyn\_partynumber

## <a name="internal-organization"></a>Organização interna

As informações internas da organização no Common Data Service vêm de duas entidades, **unidade operacional** e **entidades legais**.

<!-- ![architecture image](media/dual-write-operating-unit.png) -->

<!-- ![architecture image](media/dual-write-legal-entities.png) -->

### <a name="operating-unit"></a>Unidade operacional

Campo de origem | Tipo de mapa | Campo de destino
---|---|---
LANGUAGEID | \> | msdyn\_languageid
NAMEALIAS | \> | msdyn\_namealias
NOME | \> | msdyn\_name
PARTYNUMBER | \> | msdyn\_partynumber
OPERATINGUNITTYPE | \>\> | msdyn\_type

### <a name="legal-entity"></a>Pessoa jurídica em geral

Campo de origem | Tipo de mapa | Campo de destino
---|---|---
NAMEALIAS | \> | msdyn\_namealias
LANGUAGEID | \> | msdyn\_languageid
NOME | \> | msdyn\_name
PARTYNUMBER | \> | msdyn\_partynumber
nenhuma | \>\> | msdyn\_type
LEGALENTITYID | \> | msdyn\_companycode

## <a name="company"></a>Empresa

Fornece sincronização bidirecional de informações da entidade legal (empresa) entre o Finance and Operations e outros aplicativos do Dynamics 365.

<!-- ![architecture image](media/dual-write-company.png) -->

Campo de origem | Tipo de mapa | Campo de destino
---|---|---
NOME | = | cdm\_name
LEGALENTITYID | = | cdm\_companycode

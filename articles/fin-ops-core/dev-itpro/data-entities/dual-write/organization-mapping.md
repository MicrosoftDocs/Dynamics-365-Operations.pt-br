---
title: Hierarquia da organização no Dataverse
description: Este tópico descreve a integração de dados organizacionais entre aplicativos do Finance and Operations e o Dataverse.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: e2b652f11db62eb58ffc2ec2fc4322149e7d45d1
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680063"
---
# <a name="organization-hierarchy-in-dataverse"></a>Hierarquia da organização no Dataverse

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Como o Dynamics 365 Finance é um sistema financeiro, a *organização* é um conceito básico. A configuração do sistema começa com a configuração de uma hierarquia da organização. As finanças comerciais podem ser rastreadas em nível organizacional e também em qualquer nível da hierarquia da organização.

Embora o Dataverse não tenha o conceito de uma hierarquia da organização, ele tem alguns conceitos soltos, como receita total de venda. Como parte da integração do Dataverse, a estrutura de dados da hierarquia da organização é adicionada ao Dataverse.

## <a name="data-flow"></a>Fluxo de dados

Um ecossistema comercial que consiste em aplicativos do Finance and Operations e no Dataverse continuará a ter uma hierarquia da organização. Essa hierarquia da organização é criada nos aplicativos do Finance and Operations, mas é exposta no Dataverse para fins informativos e de extensibilidade. A ilustração a seguir mostra informações da hierarquia da organização que é exposta no Dataverse como um fluxo de dados unidirecional de aplicativos do Finance and Operations para o Dataverse.

![Imagem de arquitetura](media/dual-write-data-flow.png)

Os mapas de tabelas da hierarquia da organização estão disponíveis para sincronização unidirecional de dados de aplicativos do Finance and Operations para o Dataverse.

## <a name="templates"></a>Modelos

As informações do produto contêm todos os dados relacionados ao produto e sua definição, como as dimensões do produto ou as dimensões de rastreamento e armazenamento. Como mostrado na tabela a seguir, é criada uma coleção de mapas de tabelas para sincronizar produtos e as informações relacionadas.

Aplicativos Finance and Operations | Outros aplicativos do Dynamics 365 | descrição
-----------------------|--------------------------------|---
Finalidades da hierarquia da organização | msdyn_internalorganizationhierarchypurposes | Este modelo oferece sincronização unidirecional da entidade Finalidade da hierarquia da organização.
Tipo de hierarquia da organização | msdyn_internalorganizationhierarchytypes | Este modelo oferece sincronização unidirecional da entidade Tipo da hierarquia da organização.
Hierarquia da organização - publicada | msdyn_internalorganizationhierarchies | Este modelo oferece sincronização unidirecional da entidade Hierarquia da organização publicada.
Unidade operacional | msdyn_internalorganizations |
Entidades legais | msdyn_internalorganizations |
Entidades legais | cdm_companies | Oferece sincronização bidirecional de informações da entidade legal (empresa).

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Organization hierarchy purposes](includes/OrganizationHierarchyPurpose-msdyn-internalorganizationhierarchypurposes.md)]

[!include [Organization hierarchy type](includes/OrganizationHierarchyType-msdyn-internalorganizationhierarchytypes.md)]

[!include [Organization hierarchy - published](includes/OrganizationHierarchyPublished-msdyn-internalorganizationhierarchies.md)]

## <a name="internal-organization"></a>Organização interna

As informações internas da organização no Dataverse vêm de duas tabelas, **unidade operacional** e **entidades legais**.

[!include [Operating unit](includes/OperatingUnit-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-Companies.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
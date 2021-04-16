---
title: Hierarquia da organização no Dataverse
description: Este tópico descreve a integração de dados organizacionais entre aplicativos do Finance and Operations e o Dataverse.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 8b147c27b9309b1b3597f1194c415fbb2e2b7ad2
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750803"
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
Finalidades da hierarquia da organização | msdyn_internalorganizationhierarchypurposes | Este modelo oferece sincronização unidirecional da tabela Finalidade da Hierarquia da Organização.
Tipo de hierarquia da organização | msdyn_internalorganizationhierarchytypes | Este modelo oferece sincronização unidirecional da tabela Tipo da Hierarquia da Organização.
Hierarquia da organização - publicada | msdyn_internalorganizationhierarchies | Este modelo oferece sincronização unidirecional da tabela Hierarquia da Organização Publicada.
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
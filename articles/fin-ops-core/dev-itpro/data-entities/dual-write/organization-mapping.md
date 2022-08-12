---
title: Hierarquia da organização no Dataverse
description: Este artigo descreve a integração de dados organizacionais entre os aplicativos de finanças e operações e o Dataverse.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 2f900637855bee3e21916652a373c683e6bf1392
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2022
ms.locfileid: "9112008"
---
# <a name="organization-hierarchy-in-dataverse"></a>Hierarquia da organização no Dataverse

[!include [banner](../../includes/banner.md)]



Como o Dynamics 365 Finance é um sistema financeiro, a *organização* é um conceito básico. A configuração do sistema começa com a configuração de uma hierarquia da organização. As finanças comerciais podem ser rastreadas em nível organizacional e também em qualquer nível da hierarquia da organização.

Embora o Dataverse não tenha o conceito de uma hierarquia da organização, ele tem alguns conceitos soltos, como receita total de venda. Como parte da integração do Dataverse, a estrutura de dados da hierarquia da organização é adicionada ao Dataverse.

## <a name="data-flow"></a>Fluxo de dados

Um ecossistema comercial que consiste em aplicativos de finanças e operações e no Dataverse continuará a ter uma hierarquia da organização. Essa hierarquia da organização é criada nos aplicativos de finanças e operações, mas é exposta no Dataverse para fins informativos e de extensibilidade. A ilustração a seguir mostra informações da hierarquia da organização que é exposta no Dataverse como um fluxo de dados unidirecional de aplicativos de finanças e operações para o Dataverse.

![Imagem de arquitetura.](media/dual-write-data-flow.png)

Os mapas da tabela da hierarquia da organização estão disponíveis para sincronização unidirecional de dados de aplicativos de finanças e operações para o Dataverse.

## <a name="templates"></a>Modelos

Uma organização é um grupo da pessoas que está trabalhando em conjunto para realizar um processo comercial ou atingir uma meta. As hierarquias da organização representam os relacionamentos entre as organizações que compõem sua empresa. Você pode definir os seguintes tipos de organizações internas: entidades legais, unidades operacionais e equipes. Como mostra a tabela a seguir, uma coleção de mapas de tabela é criada para sincronizar entidades legais, unidades operacionais e informações de hierarquia de organização relacionadas.

Aplicativos do Finance and Operations | Aplicativos do Customer Engagement     | Descrição
-----------------------|--------------------------------|---
[Entidades legais](mapping-reference.md#102) | cdm_companies | 
[Entidades legais](mapping-reference.md#142) | msdyn_internalorganizations |
[Unidade operacional](mapping-reference.md#143) | msdyn_internalorganizations |
[Hierarquia da organização - publicada](mapping-reference.md#139) | msdyn_internalorganizationhierarchies | Este modelo oferece sincronização unidirecional da tabela Hierarquia da Organização Publicada.
[Finalidades da hierarquia da organização](mapping-reference.md#140) | msdyn_internalorganizationhierarchypurposes | Este modelo oferece sincronização unidirecional da tabela Finalidade da Hierarquia da Organização.
[Tipo de hierarquia da organização](mapping-reference.md#141) | msdyn_internalorganizationhierarchytypes | Este modelo oferece sincronização unidirecional da tabela Tipo da Hierarquia da Organização.

## <a name="internal-organization"></a>Organização interna

As informações internas da organização no Dataverse vêm de duas tabelas, **Unidade operacional** e **Entidades legais**.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]


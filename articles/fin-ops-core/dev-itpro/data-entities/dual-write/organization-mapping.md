---
title: Hierarquia da organização no Dataverse
description: Este tópico descreve a integração de dados organizacionais entre aplicativos do Finance and Operations e o Dataverse.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: c7ef3a11817d60343503c80d89493262711524b1
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2021
ms.locfileid: "7782299"
---
# <a name="organization-hierarchy-in-dataverse"></a>Hierarquia da organização no Dataverse

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Como o Dynamics 365 Finance é um sistema financeiro, a *organização* é um conceito básico. A configuração do sistema começa com a configuração de uma hierarquia da organização. As finanças comerciais podem ser rastreadas em nível organizacional e também em qualquer nível da hierarquia da organização.

Embora o Dataverse não tenha o conceito de uma hierarquia da organização, ele tem alguns conceitos soltos, como receita total de venda. Como parte da integração do Dataverse, a estrutura de dados da hierarquia da organização é adicionada ao Dataverse.

## <a name="data-flow"></a>Fluxo de dados

Um ecossistema comercial que consiste em aplicativos do Finance and Operations e no Dataverse continuará a ter uma hierarquia da organização. Essa hierarquia da organização é criada nos aplicativos do Finance and Operations, mas é exposta no Dataverse para fins informativos e de extensibilidade. A ilustração a seguir mostra informações da hierarquia da organização que é exposta no Dataverse como um fluxo de dados unidirecional de aplicativos do Finance and Operations para o Dataverse.

![Imagem de arquitetura.](media/dual-write-data-flow.png)

Os mapas de tabelas da hierarquia da organização estão disponíveis para sincronização unidirecional de dados de aplicativos do Finance and Operations para o Dataverse.

## <a name="templates"></a>Modelos

As informações do produto contêm todos os dados relacionados ao produto e sua definição, como as dimensões do produto ou as dimensões de rastreamento e armazenamento. Como mostrado na tabela a seguir, é criada uma coleção de mapas de tabelas para sincronizar produtos e as informações relacionadas.

Aplicativos do Finance and Operations | Aplicativos do Customer Engagement     | descrição
-----------------------|--------------------------------|---
[Entidades legais](mapping-reference.md#102) | cdm_companies | Oferece sincronização bidirecional de informações da entidade legal (empresa).
[Entidades legais](mapping-reference.md#142) | msdyn_internalorganizations |
[Unidade operacional](mapping-reference.md#143) | msdyn_internalorganizations |
[Hierarquia da organização - publicada](mapping-reference.md#139) | msdyn_internalorganizationhierarchies | Este modelo oferece sincronização unidirecional da tabela Hierarquia da Organização Publicada.
[Finalidades da hierarquia da organização](mapping-reference.md#140) | msdyn_internalorganizationhierarchypurposes | Este modelo oferece sincronização unidirecional da tabela Finalidade da Hierarquia da Organização.
[Tipo de hierarquia da organização](mapping-reference.md#141) | msdyn_internalorganizationhierarchytypes | Este modelo oferece sincronização unidirecional da tabela Tipo da Hierarquia da Organização.

## <a name="internal-organization"></a>Organização interna

As informações internas da organização no Dataverse vêm de duas tabelas, **Unidade operacional** e **Entidades legais**.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

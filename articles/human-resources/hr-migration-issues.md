---
title: Problemas conhecidos de mesclagem de infraestrutura do Dynamics 365 Human Resources
description: Este artigo lista problemas que podem ocorrer durante a mesclagem de infraestrutura do Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/27/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3fe21df8be010ace3070ad08ed95f3d3efc7b01d
ms.sourcegitcommit: bdee5e642d417a13abdb778c14ec5f2dbbf8dee7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2022
ms.locfileid: "9838546"
---
# <a name="dynamics-365-human-resources-infrastructure-merge-known-issues"></a>Problemas conhecidos de mesclagem de infraestrutura do Dynamics 365 Human Resources

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]
[!include [preview banner](../includes/preview-banner.md)]

## <a name="shared-dataverse-environments"></a>Ambientes do Dataverse Compartilhados

A estrutura de Gravação Dupla não oferece suporte à vinculação de dois ambientes de aplicativos financeiros e operacionais para o mesmo ambiente do Dataverse. Se você tiver um ambiente do Dataverse que é compartilhado com os dois itens a seguir, deverá duplicar o ambiente do Dataverse ou dividi-lo:

- Um aplicativo de finanças e operações
- Um ambiente de Recursos Humanos atual

## <a name="environment-type-requirements"></a>Requisitos do tipo de recurso

Os tipos de ambiente a seguir são necessários para que você possa fazer a migração:

- Se você não tiver ambientes autônomos de área restrita, você deverá criar um para validar a migração.
- Se você tiver vários ambientes de produção autônomos, um deles poderá ser migrado. Contate o Suporte da Microsoft para marcar outros ambientes como áreas restritas.

## <a name="teams-integration"></a>Integração do Teams

O aplicativo Recursos Humanos no Teams atualmente está sendo deslocado para uma solução da Microsoft Power Platform. Para obter mais informações, consulte [aplicativo Human Resources no Teams](hr-admin-teams-leave-app.md).

## <a name="dual-write-integration"></a>Integração da gravação dupla

A gravação dupla é uma infraestrutura pronta para uso que fornece interação quase em tempo real entre aplicativos de engajamento do cliente e aplicativos de finanças e operações. Se a sua organização usa uma gravação dupla para integrações, você pode ser afetado por alguns dos problemas encontrados. Para obter mais informações sobre tabelas e problemas do Dataverse, consulte [Tabelas do Dataverse](hr-developer-entities.md).


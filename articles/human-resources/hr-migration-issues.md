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
ms.openlocfilehash: 28c2c10a9293d00e26dfcc80ab08b89a122a6135
ms.sourcegitcommit: 088a7b5eb9a3b68710dfe012abf4c24776978750
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2022
ms.locfileid: "9733432"
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

## <a name="licensing"></a>Licenciamento

Não há alterações no licenciamento para o Dynamics 365 Human Resources nas seguintes áreas: 

- **Número mínimo de requisito de compra de licença**
- **Licenças para um ambiente de produção e um ambiente de área restrita** – se você tiver licenças de Recursos Humanos independentes que incluem um ambiente de produção e um ambiente de área restrita, o mesmo número de licenças estará disponível na infraestrutura de finanças e operações.
- **Licenças de área restrita adicionais** – se você comprou licenças de área restrita adicionais para o aplicativo de Recursos Humanos independente, o mesmo número de licenças estará disponível para ambientes de área restrita na infraestrutura de finanças e operações. 

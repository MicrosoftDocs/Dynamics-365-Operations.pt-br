---
title: O usuário pode acessar o Core HR, mas não o Onboard nem o Attract
description: Este tópico explica como resolver o problema onde um usuário pode acessar o Microsoft Dynamics 365 Talent - Core HR, mas não pode acessar o Attract ou o Onboard.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 80b1f8aeabfd033f393463f4be5a61447377f2d9
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2019
ms.locfileid: "2009297"
---
# <a name="user-can-access-core-hr-but-not-onboard-or-attract"></a>O usuário pode acessar o Core HR, mas não o Onboard nem o Attract

[!include [banner](includes/banner.md)]

**Detalhes do ambiente**

- A implantação do Microsoft Dynamics Lifecycle Services (LCS) foi feita pelo usuário A.
- Usuário A adicionou usuário B como um usuário do Microsoft Dynamics 365 Talent: Core HR.

**Emissão**

O usuário B pode acessar Core HR, mas não pode acessar o aplicativo Talent: Attract ou Talent: Onboard. Quando o usuário tenta ir para **Aplicativos de experiência**, ele ou ela é levado para um ambiente de teste, em vez disso.

**Solução**

O usuário B deve receber os direitos para visualizar o ambiente do Microsoft PowerApps que o usuário A criou durante o processo de provisionamento.

Para obter informações, consulte a seção "Fornecendo acesso ao ambiente" em [Talento de provisão](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

**Solução de longo prazo**

Microsoft está considerando atribuir automaticamente os direitos apropriados para Onboard e Attract quando um usuário é adicionado ao Core HR.

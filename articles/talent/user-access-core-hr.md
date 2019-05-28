---
title: O usuário pode acessar o Core HR, mas não o aplicativo Onboard ou Attract
description: Este tópico explica como resolver o problema onde um usuário pode acessar o Microsoft Dynamics 365 for Talent Core HR, mas não pode acessar o aplicativo Attract ou Onboard.
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
ms.openlocfilehash: ece6a81c54ef1421284fc79ab82ed3e31a972255
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1517348"
---
# <a name="user-can-access-core-hr-but-not-the-onboard-or-attract-app"></a>O usuário pode acessar o aplicativo Core HR mas não o Onboard nem o Attract

[!include [banner](includes/banner.md)]

**Detalhes do ambiente**

- A implantação do Microsoft Dynamics Lifecycle Services (LCS) foi feita pelo usuário A.
- Usuário A adicionou usuário B como um usuário do Dynamics 365 for Talent Core HR.

**Saída**

O usuário B pode acessar Core HR, mas não pode acessar o aplicativo Talent: Attract ou Talent: Onboard. Quando o usuário tenta ir para **Aplicativos de experiência**, ele ou ela é levado para um ambiente de teste, em vez disso.

**Solução**

O usuário B deve receber os direitos para visualizar o ambiente do Microsoft PowerApps que o usuário A criou durante o processo de provisionamento.

Para obter informações, consulte a seção "Fornecendo acesso ao ambiente" em [Talento de provisão](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/provisioning-talent).

**Solução de longo prazo**

Microsoft está considerando atribuir automaticamente os direitos apropriados para Onboard e Attract quando um usuário é adicionado ao Core HR.

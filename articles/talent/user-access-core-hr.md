---
title: O usuário pode acessar Recursos Humanos, mas não o Onboard ou o Attract
description: Este tópico explica como resolver o problema em que um usuário pode acessar o Microsoft Dynamics 365 Talent - Recursos Humanos, mas não pode acessar o Attract ou o Onboard.
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
ms.openlocfilehash: 6c384d9a7100982eabd201d910e1bea14355dc1f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4460312"
---
# <a name="user-can-access-human-resources-but-not-onboard-or-attract"></a>O usuário pode acessar Recursos Humanos, mas não o Onboard ou o Attract

[!include [banner](includes/banner.md)]

**Detalhes do ambiente**

- A implantação do Microsoft Dynamics Lifecycle Services (LCS) foi feita pelo usuário A.
- Usuário A adicionou usuário B como um usuário do Microsoft Dynamics 365 Human Resources.

**Emissão**

O usuário B pode acessar Recursos Humanos, mas não pode acessar o aplicativo Talent: Attract ou o Talent: Onboard. Quando o usuário tenta ir para **Aplicativos de experiência**, ele ou ela é levado para um ambiente de teste, em vez disso.

**Solução**

O usuário B deve receber os direitos para visualizar o ambiente do Microsoft Power Apps que o usuário A criou durante o processo de provisionamento.

Para obter informações, consulte a seção "Fornecendo acesso ao ambiente" em [Talento de provisão](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

**Solução de longo prazo**

A Microsoft está considerando atribuir automaticamente os direitos apropriados para Onboard e Attract quando um usuário é adicionado a Recursos Humanos.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
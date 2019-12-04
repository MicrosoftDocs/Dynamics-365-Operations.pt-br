---
title: Não é possível criar um ambiente no Centro de administração do Power Apps
description: Este tópico explica o que fazer se o administrador não conseguir criar um ambiente no Centro de administração do Microsoft Power Apps.
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
ms.openlocfilehash: 5923c59ab5dde13fed0483972e76634031404fd8
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773210"
---
# <a name="cant-create-an-environment-in-the-power-apps-admin-center"></a>Não é possível criar um ambiente no Centro de administração do Power Apps

[!include [banner](includes/banner.md)]

**Emissão**

- O locatário/administrador do ambiente não pode criar um ambiente no Centro de administração do Microsoft Power Apps.
- Uma licença que dá aos usuários o direito de realizar a etapa de criação de ambiente não foi atribuída diretamente ao usuário que está realizando essa etapa.

**Solução**

Verifique se o administrador de locatários atribuiu uma licença válida do Power Apps P2 diretamente para o usuário que executará a etapa da criação do ambiente. Estes são os planos de serviço do Microsoft Dynamics que oferecem esse direito.

| Unidade de manutenção de estoque (SKU) de produto geral       | Plano de serviço do Power Apps P2  |
|------------------------------------------------|----------------------------|
| Microsoft Dynamics 365 for Operations          | Power Apps for Dynamics 365 |
| Microsoft Dynamics 365 plano Enterprise Edition | Power Apps for Dynamics 365 |

Observe que várias SKUs do Microsoft Office também oferecem o direito, junto com SKUs autônomas do plano 2 do Power Apps. O ponto importante é que um desses SKUs deve estar presente.

1. Acesse [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).
2. Crie os ambientes seguindo as instruções em [Talent de provisão](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

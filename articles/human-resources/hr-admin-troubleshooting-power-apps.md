---
title: Não é possível criar um ambiente no Centro de administração do Power Apps
description: Este tópico explica o que fazer se o administrador não conseguir criar um ambiente no Centro de administração do Microsoft Power Apps.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 50a5aac71ec8ed850cfad32bdb1b8d589eb2885a
ms.sourcegitcommit: 7e32e5e39e762a4b1606161cb603a450d13b5251
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2021
ms.locfileid: "7413552"
---
# <a name="cant-create-an-environment-in-the-power-apps-admin-center"></a>Não é possível criar um ambiente no Centro de administração do Power Apps

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Emissão**

- O locatário/administrador do ambiente não pode criar um ambiente no Centro de administração do Microsoft Power Apps.
- O usuário não tem uma licença que concede o direito de criar ambientes.

**Solução**

Verifique se a administração do locatário atribuiu uma licença do Power Apps P2 válida ao usuário que está criando o ambiente. Os seguintes planos de serviço do Microsoft Dynamics fornecem permissões para criar ambientes:

| Unidade de manutenção de estoque (SKU) de produtos geral       | Plano de serviço do Power Apps P2  |
|------------------------------------------------|----------------------------|
| Microsoft Dynamics 365 for Operations          | Power Apps for Dynamics 365 |
| Microsoft Dynamics 365 plano Enterprise Edition | Power Apps for Dynamics 365 |

Observe que várias SKUs do Microsoft Office também oferecem o direito, junto com SKUs autônomas do plano 2 do Power Apps. O ponto importante é que um desses SKUs deve estar presente.

1. Acesse [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).
2. Crie os ambientes seguindo as instruções em [Provisionar o Human Resources](/dynamics365/unified-operations/talent/provisioning-talent).


[!INCLUDE[footer-include](../includes/footer-banner.md)]

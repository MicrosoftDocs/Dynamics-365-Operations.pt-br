---
title: Não é possível criar um ambiente no Centro de administração do Power Apps
description: Este artigo explica o que fazer se o administrador não conseguir criar um ambiente no Centro de administração do Microsoft Power Apps.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 68e6dbcbbc9811211570e968047f5faa8a2c8bd0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4417261"
---
# <a name="cant-create-an-environment-in-the-power-apps-admin-center"></a>Não é possível criar um ambiente no Centro de administração do Power Apps

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
2. Crie os ambientes seguindo as instruções em [Provisionar o Human Resources](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

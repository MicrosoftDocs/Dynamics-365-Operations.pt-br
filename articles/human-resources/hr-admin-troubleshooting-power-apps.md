---
title: Não é possível criar um ambiente no Centro de administração do Power Apps
description: Este artigo explica o que fazer se o administrador não conseguir criar um ambiente no Centro de administração do Microsoft Power Apps.
author: andreabichsel
manager: tfehr
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
ms.openlocfilehash: 664c644c9b34e3489b4134040e165d26202dbd38
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "5111485"
---
# <a name="cant-create-an-environment-in-the-power-apps-admin-center"></a>Não é possível criar um ambiente no Centro de administração do Power Apps

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
2. Crie os ambientes seguindo as instruções em [Provisionar o Human Resources](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

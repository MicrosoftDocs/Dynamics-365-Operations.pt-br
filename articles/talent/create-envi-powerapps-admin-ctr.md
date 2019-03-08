---
title: Não foi possível criar um ambiente na central de administração do PowerApps
description: Este tópico explica o que fazer se o administrador não conseguir criar um ambiente no Centro de administração do Microsoft PowerApps.
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 6f9b7ceef6895b295e6ae5a50d8ac7970497efe5
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "303317"
---
# <a name="cant-create-an-environment-in-the-powerapps-admin-center"></a>Não é possível criar um ambiente no Centro de administração do PowerApps

[!include [banner](includes/banner.md)]

**Saída**

- O locatário/administrador do ambiente não pode criar um ambiente no Centro de administração do Microsoft PowerApps.
- Uma licença que dá aos usuários o direito de realizar a etapa de criação de ambiente não foi atribuída diretamente ao usuário que está realizando essa etapa.

**Solução**

Verifique se o administrador do locatário recebeu uma licença válida do PowerApps P2 diretamente ao usuário que executará a etapa da criação de ordens. Estes são os planos de serviço do Microsoft Dynamics que oferecem esse direito.

| Unidade de manutenção de estoque (SKU) de produto geral       | Plano de serviço do PowerApps P2  |
|------------------------------------------------|----------------------------|
| Microsoft Dynamics 365 for Operations          | PowerApps para Dynamics 365 |
| Microsoft Dynamics 365 plano Enterprise Edition | PowerApps para Dynamics 365 |

Observe que várias SKUs do Microsoft Office também oferecem o direito, junto com SKUs autônomas do plano 2 do PowerApps. O ponto importante é que um desses SKUs deve estar presente.

1. Acesse [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).
2. Crie os ambientes seguindo as instruções em [Talent de provisão](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/provisioning-talent).

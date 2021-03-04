---
title: Encargos diversos de gerenciamento de transporte
description: Este tópico explica como os encargos gerados pelo transporte devem ser associados a um código de encargo.
author: Henrikan
manager: tfehr
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 2b703d770c7f9ea684716368cf1e7dbe5fec8710
ms.sourcegitcommit: fe7ac653efcb1ac6318083f482394b96ed82b4c7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/29/2020
ms.locfileid: "4422653"
---
# <a name="transportation-management-miscellaneous-charges"></a>Encargos diversos de gerenciamento de transporte

[!include [banner](../includes/banner.md)]

Como acontece com todos os encargos diversos, os encargos gerados pelo transporte devem ser associados a um código de encargo. Caso contrário, eles não serão adicionados de volta à ordem como um encargo diverso. O **Código de encargo** determina como a cobrança é contabilizada em relação à ordem e à linha de ordem em que é adicionada.

Acesse **Gerenciamento de transporte > Configurar > Classificação > Encargos diversos** para definir os critérios de qualificação que determinam quando um **Código de encargo** específico é aplicado a uma cobrança.

Você deve ter pelo menos uma configuração para cada configuração **Módulo de encargo** relevante (*Cliente* e *Fornecedor*) em que **Tipo de encargo diverso** é definido como *Nenhum*. Se estiver faltando, o encargo diverso *não* será adicionada à ordem.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
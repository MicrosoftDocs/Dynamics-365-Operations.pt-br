---
title: Encargos diversos de gerenciamento de transporte
description: Este tópico explica como os encargos gerados pelo transporte devem ser associados a um código de encargo.
author: Henrikan
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 53c25f204e98a911e9697f5bb950706555749a55
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828292"
---
# <a name="transportation-management-miscellaneous-charges"></a>Encargos diversos de gerenciamento de transporte

[!include [banner](../includes/banner.md)]

Como acontece com todos os encargos diversos, os encargos gerados pelo transporte devem ser associados a um código de encargo. Caso contrário, eles não serão adicionados de volta à ordem como um encargo diverso. O **Código de encargo** determina como a cobrança é contabilizada em relação à ordem e à linha de ordem em que é adicionada.

Acesse **Gerenciamento de transporte > Configurar > Classificação > Encargos diversos** para definir os critérios de qualificação que determinam quando um **Código de encargo** específico é aplicado a uma cobrança.

Você deve ter pelo menos uma configuração para cada configuração **Módulo de encargo** relevante (*Cliente* e *Fornecedor*) em que **Tipo de encargo diverso** é definido como *Nenhum*. Se estiver faltando, o encargo diverso *não* será adicionada à ordem.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
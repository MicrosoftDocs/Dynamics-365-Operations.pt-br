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
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: cb503072fb76e04aa01ff2d231c756eeb244c65a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5004692"
---
# <a name="transportation-management-miscellaneous-charges"></a>Encargos diversos de gerenciamento de transporte

[!include [banner](../includes/banner.md)]

Como acontece com todos os encargos diversos, os encargos gerados pelo transporte devem ser associados a um código de encargo. Caso contrário, eles não serão adicionados de volta à ordem como um encargo diverso. O **Código de encargo** determina como a cobrança é contabilizada em relação à ordem e à linha de ordem em que é adicionada.

Acesse **Gerenciamento de transporte > Configurar > Classificação > Encargos diversos** para definir os critérios de qualificação que determinam quando um **Código de encargo** específico é aplicado a uma cobrança.

Você deve ter pelo menos uma configuração para cada configuração **Módulo de encargo** relevante (*Cliente* e *Fornecedor*) em que **Tipo de encargo diverso** é definido como *Nenhum*. Se estiver faltando, o encargo diverso *não* será adicionada à ordem.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
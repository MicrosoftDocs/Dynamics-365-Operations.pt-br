---
title: O nome da entrega não é sincronizado depois de alterar o endereço de entrega de uma ordem de compra
description: Depois de você alterar o endereço de entrega no cabeçalho de uma ordem de compra, o nome da entrega não é sincronizado
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 588d1ef6250d249aa4fc9da4f5125e9a34c0255f
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475548"
---
# <a name="the-delivery-name-isnt-synced-after-changing-a-purchase-order-delivery-address"></a>O nome da entrega não é sincronizado depois de alterar o endereço de entrega de uma ordem de compra

## <a name="symptoms"></a>Sintomas

O endereço no cabeçalho de uma ordem de compra é atualizado para um endereço que não é um endereço de entrega. Embora o endereço seja atualizado na ordem de compra, o nome da entrega não é atualizado com base no endereço atualizado.

## <a name="resolution"></a>Resolução

Esse comportamento é por design. O endereço selecionado deve ser classificado como um endereço de entrega. Caso contrário, o nome da entrega não será atualizado com base no endereço selecionado.

---
title: O texto substituído quando um item é configurado na linha da ordem de venda
description: Quando um produto é configurado em uma linha da ordem de venda, o texto modificado é substituído por texto padrão. Altere o texto depois de configurar a linha, não antes.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 20239b9b0eecb355274e909a8b8b39450e468c7e
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475534"
---
# <a name="item-text-is-overwritten-when-a-product-is-configured-on-a-sales-order-line"></a>O texto do item é sobrescrito quando um produto é configurado em uma linha da ordem de venda

## <a name="symptoms"></a>Sintomas

Esse problema ocorre quando você cria uma linha de ordem de venda para um item configurável e, em seguida, modifica o texto do item. Ao configurar o item e selecionar **OK**, o texto será substituído pelo texto padrão.

## <a name="resolution"></a>Resolução

Esse comportamento é esperado. O campo de texto inclui o nome da variante, que é preenchido somente após a configuração da linha. Portanto, você deve alterar o texto depois de configurar a linha, não antes.

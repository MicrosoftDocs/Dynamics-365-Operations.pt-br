---
title: O RM de item não pode ser reservado quando uma ordem de produção é liberada
description: 'Ao liberar uma ordem de produção, você pode receber o erro: "O item RM não pôde ser totalmente reservado". Verifique se a quantidade total está disponível ou reserve itens manualmente.'
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 528895252d661bb012f49190c15853989833064d
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475607"
---
# <a name="item-rm-cant-be-fully-reserved-when-a-production-order-is-released"></a>O RM de item não pode ser totalmente reservado quando uma ordem de produção é liberada

## <a name="symptoms"></a>Sintomas

Se nem todos os itens de linha da BOM estiverem fisicamente disponíveis quando uma ordem de produção for liberada para um depósito e a política **Liberar para o depósito** estiver definida como *Exigir reserva cheia*, você receberá a seguinte mensagem de erro:

> O item RM não pôde ser totalmente reservado. Certifique-se de que a quantidade total esteja disponível ou reserve os itens manualmente se o campo Reserva na linha da BOM estiver definido como Manual ou Iniciado. Não foi possível liberar a ordem para o depósito porque alguns materiais não puderam ser reservados.

## <a name="resolution"></a>Resolução

Esse comportamento é assim por design e está funcionando conforme o esperado. Para corrigir esse problema, siga as orientações fornecidas na mensagem de erro: "Certifique-se de que a quantidade total esteja disponível ou reserve os itens manualmente se o campo Reserva na linha da BOM estiver definido como Manual ou Iniciado".

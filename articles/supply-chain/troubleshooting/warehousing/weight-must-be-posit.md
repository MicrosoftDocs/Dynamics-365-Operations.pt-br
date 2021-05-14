---
title: O peso deve ser positivo
description: O peso deve ser positivo
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSContainerCloseDiag_canClose
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: dcbcde3143cb509b68b277cb7c709263e2659b5b
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924294"
---
# <a name="weight-must-be-positive"></a>O peso deve ser positivo

Código de erro: WeightMustBePositive

## <a name="symptoms"></a>Sintomas

O sistema mostra a seguinte mensagem de erro:

> O peso deve ser positivo.

## <a name="cause"></a>Causa

O campo **Peso Bruto** é definido como *0* (zero) ou um valor negativo.

## <a name="resolution"></a>Resolução

Para especificar um peso, siga uma destas etapas.

- No campo **Peso bruto**, defina um valor. Em seguida, selecione uma unidade na lista suspensa.
- Selecione **Obter peso do sistema** para calcular o valor **Peso bruto**.

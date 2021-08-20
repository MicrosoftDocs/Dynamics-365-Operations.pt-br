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
ms.openlocfilehash: 27ec37e0c0644ff10ece4626d5c136bca3c52ef12f1c6de947afd03003a5368a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6776767"
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

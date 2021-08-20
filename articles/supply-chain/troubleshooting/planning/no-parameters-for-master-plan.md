---
title: Parâmetros para o plano mestre não existem
description: Quando você tenta firmar uma ordem planejada, você recebe uma mensagem de erro que afirma que não existem parâmetros para o plano mestre.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: d039b79684f87e7791fb9dae7cbdc6ced220bc092d9a0ab624616c1c345986da
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6756766"
---
# <a name="parameters-for-the-master-plan-dont-exist"></a>Parâmetros para o plano mestre não existem

Código de erro: SYS25368

## <a name="symptoms"></a>Sintomas

Ao tentar firmar uma ordem planejada, você recebe a seguinte mensagem de erro:

> Os parâmetros do plano mestre %1 não existem.

## <a name="cause"></a>Causa

Devido a problemas de configuração, o sistema não consegue encontrar as configurações do plano especificado.

## <a name="resolution"></a>Resolução

- Acesse **Planejamento mestre \> Configuração \> Planos \> Planos mestres** e certifique-se de que um plano que tenha o nome especificado exista.

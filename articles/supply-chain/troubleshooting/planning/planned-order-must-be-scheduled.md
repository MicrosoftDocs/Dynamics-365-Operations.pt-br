---
title: A ordem de produção planejada deve ser agendada antes de ser firmada
description: Quando tenta firmar uma ordem planejada, você recebe uma mensagem de erro que afirma que a ordem deve ser agendada antes que ela possa ser firmada.
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
ms.openlocfilehash: a360cb3cbd26e1bc1ebb1baf1a6a4d8282c28c5c
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294015"
---
# <a name="planned-production-order-must-be-scheduled-before-it-can-be-firmed"></a>A ordem de produção planejada deve ser agendada antes de ser firmada

Código de erro: SYS309802

## <a name="symptoms"></a>Sintomas

Ao tentar firmar uma ordem planejada, você recebe a seguinte mensagem de erro:

> A ordem de produção planejada deve ser agendada para que possa ser confirmada.

## <a name="cause"></a>Causa

As datas agendadas de início e término não podem ficar em branco.

## <a name="resolution"></a>Resolução

Para especificar as datas de início e término da ordem planejada, siga estas etapas.

1. Vá para **Planejamento mestre \> Planejamento mestre \> Ordens planejadas**.
1. Abra a ordem planejada relevante.
1. Na FastTab **Geral**, na seção **Agendado**, especifique as datas nos campos **Data de início** e **Data de término**.

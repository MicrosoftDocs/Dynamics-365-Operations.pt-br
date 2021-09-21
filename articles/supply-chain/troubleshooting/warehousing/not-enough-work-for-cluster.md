---
title: Não foi encontrado nenhum trabalho suficiente para o cluster após a configuração do perfil
description: Se você configurar um perfil de cluster, poderá receber uma mensagem de erro informando que não é possível encontrar trabalho suficiente. Edite o perfil e defina Ativar posições como Não.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 139fd72e571c8ef83af2fd0e497cf334b6ef0ea4
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475546"
---
# <a name="not-enough-work-found-for-cluster-when-using-system-directed-cluster-picking"></a>Não foi encontrado trabalho suficiente para o cluster ao usar a Separação de cluster direcionado pelo sistema

## <a name="symptoms"></a>Sintomas

Ao usar o processo *Separação de cluster direcionada pelo sistema*, se você configurar um perfil de cluster em que, por exemplo, 10 posições podem ser separadas, o processo funciona conforme planejado quando há trabalho suficiente para separar até 10 posições. No entanto, se houver apenas oito posições a serem escolhidas, você receberá a seguinte mensagem de erro:

> Não é possível encontrar trabalho suficiente para o cluster.

## <a name="resolution"></a>Resolução

Para corrigir esse problema, edite o perfil do cluster e defina a opção **Ativar posições** como *Não*.

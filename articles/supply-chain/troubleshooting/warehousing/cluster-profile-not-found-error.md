---
title: Perfil de cluster não encontrado
description: Ao trabalhar com operações de depósito de entrada, talvez seja exibido um erro informando que o perfil de cluster não foi encontrado. Certifique-se de que os perfis de cluster estejam configurados corretamente.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: bbf9c5bc70c8f3ba1fa26db425249e65e82c0518
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475624"
---
# <a name="cluster-profile-cant-be-found"></a>Não foi possível encontrar o perfil de cluster

## <a name="symptoms"></a>Sintomas

Ao trabalhar com operações de depósito de entrada, talvez seja exibida a seguinte mensagem de erro:

> "A ordem de qualidade %1 foi gerada. Perfil de cluster não encontrado. Verifique a configuração."

Essa mensagem de erro está relacionada a um processo de recebimento em que o gerenciamento de qualidade (QMS) está ativado. Dependendo das configurações de seu ambiente, detalhes adicionais sobre a transação que está gerando a mensagem de erro podem ajudar a corrigir o problema.

## <a name="resolution"></a>Resolução

Primeiro, revise a configuração de separação de cluster e certifique-se de que seus perfis de cluster estejam configurados corretamente. Você não pode usar um item de menu de dispositivo móvel para seleção de cluster, a menos que os perfis de cluster sejam configurados. Dependendo do seu ambiente, você também pode ter que revisar outras configurações relacionadas.

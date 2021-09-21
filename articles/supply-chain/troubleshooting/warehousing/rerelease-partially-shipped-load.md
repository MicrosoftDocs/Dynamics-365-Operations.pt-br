---
title: Não é possível liberar novamente carga parcialmente remetida para o depósito
description: Em versões anteriores, não foi possível lançar novamente um carregamento remetido parcialmente ao usar certas funcionalidades com reservas incompletas. Isso foi corrigido.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 0380e1963a38f2be55b31e06b3845f935661eed2
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475597"
---
# <a name="cant-re-release-a-partially-shipped-load-to-the-warehouse"></a>Não é possível liberar novamente uma carga parcialmente remetida para o depósito

## <a name="symptoms"></a>Sintomas

Não é possível liberar uma carga parcialmente enviada para o depósito. Quando você realiza a liberação para o depósito, uma mensagem "Operação concluída" aparece, mas nada acontece e nenhum trabalho é criado para a quantidade restante. Esse problema ocorre quando você usa a funcionalidade de carregamento de transporte e há uma reserva incompleta.

## <a name="resolution"></a>Resolução

O [problema do KB 470069](https://fix.lcs.dynamics.com/Issue/Details?kb=4574490&bugId=470069&dbType=3&qc=84ce1e09d7032d8b8ef86f5a0c68b86badf3dfaf29686c5ebbe97c53c0957b5f) ("Cargas parcialmente enviadas podem ser colocadas em ciclo e processadas de novo") foi corrigido na [versão 10.0.15](/dynamics365/supply-chain/get-started/whats-new-scm-10-0-15).

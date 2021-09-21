---
title: Não é possível selecionar Alteração de Status do Estoque como Tipo de trabalho
description: Não é possível criar uma linha de modelo de trabalho para Alteração de Status do Estoque porque o tipo de trabalho é usado somente por processos do sistema. Selecione um tipo de trabalho diferente.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: ad7f26f3235d15779583f9cdadeb4e6dca16242a
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475614"
---
# <a name="cant-select-inventory-status-change-in-the-work-type-column"></a>Não é possível selecionar Alteração de Status do Estoque na coluna Tipo de trabalho

## <a name="symptoms"></a>Sintomas

Ao configurar o Microsoft Dynamics 365 Supply Chain Management, você pode receber a seguinte mensagem de erro:

> Não é possível criar uma linha de modelo de trabalho para Alteração de Status do Estoque porque o tipo de trabalho não é válido. Selecione um tipo de trabalho diferente.

## <a name="resolution"></a>Resolução

Esse comportamento é por design. O tipo de trabalho *Alteração do status do estoque* é usado apenas por processos do sistema. Ele não pode ser configurado. Como a lista de tipos de trabalho é fixada como uma enumeração, as entradas extras não podem ser filtradas do menu suspenso **Tipo de trabalho**.

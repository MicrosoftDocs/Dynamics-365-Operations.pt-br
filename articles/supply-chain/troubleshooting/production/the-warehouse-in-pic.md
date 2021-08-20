---
title: O depósito no diário de listas de separação não atualiza em uma linha da BOM.
description: O depósito no diário de listas de separação atualiza em uma linha da lista de materiais (BOM).
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdJournalTransBOM
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 970930bbdd30b57a8374de7810bb3ece8cb19a7010b5ef19d90bfc39d09f172b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6740542"
---
# <a name="the-warehouse-in-the-picking-list-journal-isnt-updated-on-a-bom-line"></a>O depósito no diário de listas de separação atualiza em uma linha da BOM

Número de KB: 4614848

## <a name="symptoms"></a>Sintomas

O depósito no diário de listas de separação atualiza em uma linha da lista de materiais (BOM).

## <a name="resolution"></a>Resolução

O sistema está agindo como esperado. Se uma linha do diário de listas de separação for criada com uma referência (por meio do ID do lote) para uma linha da BOM de produção, o depósito na linha de produção da BOM não será atualizado se a dimensão do depósito na linha de produção do diário da lista de separação for alterada posteriormente.

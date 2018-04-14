---
title: "Atualização em massa de ativos fixos"
description: "Ao usar registros, você poderá alterar as convenções de depreciação para grupos de ativos que fazem parte do mesmo registro."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 3521
ms.assetid: 50207ffb-6b89-4fb9-92e9-928bc0729489
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: b3fb55f1a51652299db8a31274b07f239fbaf28f
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="fixed-asset-mass-update"></a>Atualização em massa de ativos fixos

[!INCLUDE [banner](../includes/banner.md)]

Ao usar registros, você poderá alterar as convenções de depreciação para grupos de ativos que fazem parte do mesmo registro.

Por exemplo, se você estiver nos Estados Unidos e colocou mais de 40% de seus ativos em serviço durante o quarto trimestre do ano, você deverá usar a convenção de depreciação na metade do trimestre. Você pode usar o processo de uma atualização em massa para alterar todos os ativos que exigem a nova convenção de depreciação. 

Ao atualizar a convenção de depreciação para ativos, você exclui todas as transações de depreciação que existem para esses ativos. Você também exclui todas as transações de ajustes de depreciação, transações de depreciação extra e transações de depreciação extraordinária para esses ativos. 

Para atualizar a convenção de depreciação para ativos que já foram descartados, primeiro você deve excluir as transações de alienação existentes. Você também deve excluir todas as transações que foram geradas devido ao processo de alienação. 

Após atualizar a convenção de depreciação para ativos, você poderá processar a depreciação e a depreciação extraordinária para cada ativo. Você também pode fazer ajustes de depreciação manuais, se qualquer ajuste for necessário.







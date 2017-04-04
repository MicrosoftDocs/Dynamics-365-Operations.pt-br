---
title: "Atualização em massa de ativos fixos"
description: "Se você usar registros, você pode alterar as convenções de depreciação para grupos de ativos que fazem parte do mesmo registro."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3521
ms.assetid: 50207ffb-6b89-4fb9-92e9-928bc0729489
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3b16ef53f9fb57a6663db0be1f7e0a57471db2fb
ms.openlocfilehash: 9b40e0225a53da2311e6369ac6af43a502e4e8e9
ms.lasthandoff: 03/31/2017


---

# <a name="fixed-asset-mass-update"></a>Atualização em massa de ativos fixos

Se você usar registros, você pode alterar as convenções de depreciação para grupos de ativos que fazem parte do mesmo registro.

Por exemplo, se você estiver nos Estados Unidos e colocou mais de 40% de seus ativos em serviço durante o quarto trimestre do ano, você deverá usar a convenção de depreciação na metade do trimestre. Você pode usar o processo de uma atualização em massa para alterar todos os ativos que exigem a nova convenção de depreciação. 

Ao atualizar a convenção de depreciação para ativos, você exclui todas as transações de depreciação que existem para esses ativos. Você também exclui todas as transações de ajustes de depreciação, transações de depreciação extra e transações de depreciação extraordinária para esses ativos. 

Para atualizar a convenção de depreciação para ativos que já foram descartados, primeiro você deve excluir as transações de alienação existentes. Você também deve excluir todas as transações que foram geradas devido ao processo de alienação. 

Após atualizar a convenção de depreciação para ativos, você poderá processar a depreciação e a depreciação extraordinária para cada ativo. Você também pode fazer ajustes de depreciação manuais, se qualquer ajuste for necessário.





--- 
title: "Adicionar um cálculo a um modelo de configuração de produto"
description: "Este procedimento mostra adicionar um novo cálculo a um modelo de configuração do produto."
author: YuyuScheller
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 9ac2d9bcc316a57941136c248a0c5ff030a1fe49
ms.contentlocale: pt-br
ms.lasthandoff: 07/28/2017

---
# <a name="add-a-calculation-to-a-product-configuration-model"></a>Adicionar um cálculo a um modelo de configuração de produto

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra adicionar um novo cálculo a um modelo de configuração do produto. Ele mostra como você pode criar uma expressão lógica usando o operador “If” para definir uma altura do alto-falante como 10 para alto-falantes brancos, e 15 para todos os outros acabamentos de gabinetes. O procedimento usa o componente alto-falante avançado na empresa de demonstração USMF.


## <a name="add-a-calculation"></a>Adicionar um cálculo

## <a name="create-calculation-expression"></a>Criar expressão de cálculo
1. Clique em Editar expressão.
2. No campo de ConstraintBody, insira 'If[CabinetFinish=="White", 10, 15]'.
3. Clique em Validar.
4. Clique em Fechar.
5. Clique em OK.



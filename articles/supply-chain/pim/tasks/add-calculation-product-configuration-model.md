---
title: Adicionar um cálculo a um modelo de configuração de produto
description: Este procedimento mostra adicionar um novo cálculo a um modelo de configuração do produto.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 55f8fcfdafb2d5fb5a4d4800221fabf4b2111f86
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3150254"
---
# <a name="add-a-calculation-to-a-product-configuration-model"></a>Adicionar um cálculo a um modelo de configuração de produto

[!include [banner](../../includes/banner.md)]

Este procedimento mostra adicionar um novo cálculo a um modelo de configuração do produto. Ele mostra como você pode criar uma expressão lógica usando o operador “If” para definir uma altura do alto-falante como 10 para alto-falantes brancos, e 15 para todos os outros acabamentos de gabinetes. O procedimento usa o componente alto-falante avançado na empresa de demonstração USMF.


## <a name="add-a-calculation"></a>Adicionar um cálculo

## <a name="create-calculation-expression"></a>Criar expressão de cálculo
1. Clique em Editar expressão.
2. No campo de ConstraintBody, insira 'If[CabinetFinish=="White", 10, 15]'.
3. Clique em Validar.
4. Clique em Fechar.
5. Clique em OK.


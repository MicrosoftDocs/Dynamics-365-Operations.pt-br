---
title: Adicionar um cálculo a um modelo de configuração de produto
description: Este procedimento mostra adicionar um novo cálculo a um modelo de configuração do produto.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 32bc2ac5815c2739147664f1e1df2528178db51e
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213391"
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


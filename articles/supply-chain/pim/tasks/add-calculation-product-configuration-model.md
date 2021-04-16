---
title: Adicionar um cálculo a um modelo de configuração de produto
description: Este procedimento mostra adicionar um novo cálculo a um modelo de configuração do produto.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 268baa4b518f6df52d4393f7278a79cbe1733844
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5812659"
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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
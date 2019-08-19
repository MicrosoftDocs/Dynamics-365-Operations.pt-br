---
title: Adicionar uma restrição de expressão para um modelo de configuração de produto
description: Este procedimento mostra como é possível adicionar uma nova expressão de restrição a um modelo de configuração do produto.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, SysClientPolymorphicCreateSelector, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f67d912b3349d4b5dd861b97533a7722a2b02fa4
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845127"
---
# <a name="add-an-expression-constraint-to-a-product-configuration-model"></a>Adicionar uma restrição de expressão para um modelo de configuração de produto

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como é possível adicionar uma nova expressão de restrição a um modelo de configuração do produto. Mostra como você pode obrigar que essa proteção seja aplicada a um alto-falante, se o usuário selecionou uma grade frontal de metal. O procedimento usa o componente alto-falante avançado na empresa de demonstração USMF.


## <a name="create-an-expression-constraint"></a>Criar uma restrição de expressão
1. Clique em Definição de modelo de variante de produto.
2. Clique em Modelos de configuração do produto.
3. Na lista, localize e selecione o PDV desejado.
    * Este exemplo usa o modelo de alto-falante avançado.  
4. Na lista, clique no link na linha selecionada.
5. Expanda a seção Restrições.
6. Clique em Adicionar.
7. Clique em Criar.
8. No campo Nome, digite um valor.

## <a name="enter-expression"></a>Inserir expressão
1. Clique em Editar expressão.
    * Se você desbloquear a interface do usuário na gravação da tarefa neste estágio, você pode usar IntelliSense e a lista de símbolos para criar a expressão da restrição.  
2. No campo ConstraintBody, insira 'Implies[FrontGrill=="Metal", CornerProtection] '.
    * Esta lógica de expressão declara: Se a grade Frontal for metal, a opção de proteção de canto deve ser marcada.  
3. Clique em Validar.
    * A função Validar executa a expressão de restrição e verifica erros de sintaxe.  
4. Clique em Fechar.
5. Clique em OK.


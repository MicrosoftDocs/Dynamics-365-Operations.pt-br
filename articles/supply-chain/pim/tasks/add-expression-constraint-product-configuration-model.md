---
title: Adicionar uma restrição de expressão para um modelo de configuração de produto
description: Este procedimento mostra como é possível adicionar uma nova expressão de restrição a um modelo de configuração do produto.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, SysClientPolymorphicCreateSelector, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c43d7f768069c5ef201a2823a9aa626b38220073
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422197"
---
# <a name="add-an-expression-constraint-to-a-product-configuration-model"></a>Adicionar uma restrição de expressão para um modelo de configuração de produto

[!include [banner](../../includes/banner.md)]

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


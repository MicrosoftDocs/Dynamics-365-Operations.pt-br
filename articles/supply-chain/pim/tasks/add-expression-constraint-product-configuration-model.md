---
title: Adicionar uma restrição de expressão para um modelo de configuração de produto
description: Este procedimento mostra como é possível adicionar uma nova expressão de restrição a um modelo de configuração do produto.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, SysClientPolymorphicCreateSelector, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 77e8b991a2615a8f5d238acc4655f231edb6ca98
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7569640"
---
# <a name="add-an-expression-constraint-to-a-product-configuration-model"></a>Adicionar uma restrição de expressão para um modelo de configuração de produto

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como é possível adicionar uma nova expressão de restrição a um modelo de configuração do produto. Mostra como você pode obrigar que essa proteção seja aplicada a um alto-falante, se o usuário selecionou uma grade frontal de metal. O procedimento usa o componente alto-falante avançado na empresa de demonstração USMF.

## <a name="create-an-expression-constraint"></a>Criar uma restrição de expressão

1. Acesse **Gerenciamento de informações do produto \> Produtos \> Modelos de configuração do produto**.
3. Na lista, localize e selecione o registro desejado.
    * Este exemplo usa o modelo de alto-falante avançado.  
4. Na lista, selecione o link na linha selecionada.
5. Expanda a seção **Restrições**.
6. Selecione **Adicionar**.
7. Selecione **Criar**.
8. No campo **Nome**, digite um valor.

## <a name="enter-expression"></a>Inserir expressão

1. Selecione **Editar expressão**.
    * Se você desbloquear a interface do usuário na gravação da tarefa neste estágio, você pode usar IntelliSense e a lista de símbolos para criar a expressão da restrição.  
2. No campo **ConstraintBody**, digite 'Implies[FrontGrill=="Metal", CornerProtection] '.
    * Esta lógica de expressão declara: Se a grade Frontal for metal, a opção de proteção de canto deve ser marcada.  
3. Selecione **Validar**.
    * A função Validar executa a expressão de restrição e verifica erros de sintaxe.  
4. Selecione **Fechar**.
5. Selecione **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
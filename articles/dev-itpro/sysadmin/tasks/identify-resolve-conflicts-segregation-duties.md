--- 
title: "Identificar e solucionar conflitos na diferenciação de direitos"
description: "Você pode definir regras para separar tarefas que devem ser executadas por usuários diferentes."
author: maertenm
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysSecSegregationOfDutiesConflict, SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c3a366ea4b558ba4e4af7336992dbb091b0b1414
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="identify-and-resolve-conflicts-in-segregation-of-duties"></a>Identificar e solucionar conflitos na diferenciação de direitos

[!include [task guide banner](../../includes/task-guide-banner.md)]

Você pode definir regras para separar tarefas que devem ser executadas por usuários diferentes. Este conceito é chamado de segregação de direitos. Quando a definição de uma função de segurança ou as atribuições de função de um usuário violam as regras, o conflito será registrado. Todos os conflitos devem ser solucionados pelo administrador. Complete o procedimento a seguir para identificar e solucionar conflitos. A empresa de dados demo usada para criar este procedimento é USMF.


## <a name="verify-whether-user-role-assignments-comply-with-new-rules-for-segregation-of-duties"></a>Verificar se as atribuições de função de usuário estão em conformidade com as novas regras para a diferenciação de direitos
1. Vá para Administração do sistema > Segurança > Diferenciação de direitos > Verificar conformidade das atribuições de funções de usuário.
2. Clique em OK.
    * Uma notificação exibe os resultados da validação.     Se houver um conflito, você pode abrir a página Usuários e alterar as atribuições de função do usuário. Conflitos também são registrados na página Conflitos da diferenciação de direitos.     Para executar o processo de verificação como um trabalho em lotes, selecione Processamento em lotes, e então defina os outros parâmetros de lote. Depois que o trabalho em lotes for executado, você pode revisar os conflitos na página Conflitos da diferenciação de direitos.  

## <a name="view-and-resolve-conflicting-user-role-assignments"></a>Exiba e solucione as atribuições de função do usuário em conflito
1. Vá para Administração do sistema > Segurança > Diferenciação de direitos > Conflitos da diferenciação de direitos.
    * Selecione um conflito e clique em um dos seguintes botões: Negar a atribuição – nega a atribuição do usuário à função de segurança adicional. Se você negar uma atribuição de função automática, o usuário será marcado como excluído da função. O usuário excluído não terá o acesso associado à função concedido, e ele não poderá ser designado à função até que o administrador remova a exclusão.     Permitir a atribuição – Anula o conflito, e permite que o usuário seja designado a ambas as funções de segurança. Se você anular um conflito, você deve inserir um motivo no campo Motivo de anulação.  
2. Feche a página.
3. Vá para Administração do sistema > Segurança > Diferenciação de direitos > Conflitos não solucionados de diferenciação de direitos.
    * Selecione um conflito e clique em um dos seguintes botões: Negar a atribuição – nega a atribuição do usuário à função de segurança adicional. Se você negar uma atribuição de função automática, o usuário será marcado como excluído da função. O usuário excluído não terá o acesso associado à função concedido, e ele não poderá ser designado à função até que o administrador remova a exclusão.     Permitir a atribuição – Anula o conflito, e permite que o usuário seja designado a ambas as funções de segurança. Se você anular um conflito, você deve inserir um motivo no campo Motivo de anulação.    
4. Feche a página.

## <a name="verify-whether-existing-roles-comply-with-new-rules-for-segregation-of-duties"></a>Verificar se as funções existentes estão em conformidade com as novas regras para a diferenciação de direitos
1. Vá para Administração do sistema > Segurança > Diferenciação de direitos > Regras de diferenciação de direitos.
    * Selecione uma regra.  
2. Clique em Validar direitos e funções.
    * Se qualquer função existente viola a regra selecionada, será exibida uma mensagem que contém o nome da função e os nomes dos direitos em conflito. O administrador deve indicar a redução risco de segurança ou alterar a função de forma que não viole as regras da diferenciação de direitos.     Se nenhuma função viola a regra selecionada, uma mensagem indica que todas as funções estão em conformidade.  



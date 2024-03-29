---
title: Identificar e resolver conflitos na diferenciação de direitos
description: Este artigo explica como identificar e resolver conflitos na diferenciação de direitos.
author: peakerbl
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesConflict, SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fd36db5df2b6871d410bb1feaae825909ec9b3ff
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8883467"
---
# <a name="identify-and-resolve-conflicts-in-segregation-of-duties"></a>Identificar e resolver conflitos na diferenciação de direitos

[!include [banner](../../includes/banner.md)]

Este artigo explica como identificar e resolver conflitos na diferenciação de direitos. Você pode definir regras para separar direitos que devem ser executados por usuários diferentes. Este conceito é chamado de segregação de direitos. Quando a definição de uma função de segurança ou as atribuições de função de um usuário violam as regras, o conflito será registrado. Todos os conflitos devem ser solucionados pelo administrador. Complete o procedimento a seguir para identificar e solucionar conflitos.

Depois que uma regra tiver sido adicionada, verifique se todas as funções existentes são compatíveis. 

## <a name="verify-that-existing-roles-and-duties-comply-with-new-rules-for-segregation-of-duties"></a>Verificar se as funções e direitos existentes estão em conformidade com as novas regras para a diferenciação de direitos
1. Acesse **Administração do sistema** > **Segurança** > **Diferenciação de direitos** > **Regras de diferenciação de direitos**.
3. Selecione **Validar direitos e funções**. Se qualquer função existente violar as regras, será exibida uma mensagem que contém o nome da regra, a função e os nomes dos direitos em conflito. As funções conflitantes devem ser modificadas usando a **Configuração de segurança** e não podem incluir tarefas conflitantes. Se nenhuma função viola a regra selecionada, uma mensagem indica que todas as funções estão em conformidade.   

> [!NOTE]
> A validação é executada somente para a regra selecionada. É importante validar a conformidade de cada regra.   

Quando você cria ou modifica uma função, as regras de diferenciação de direitos são automaticamente impostas. Não é possível atribuir tarefas conflitantes a uma função.

Em seguida, verifique se todas as atribuições de funções existentes estão em conformidade.

## <a name="verify-that-user-role-assignments-comply-with-new-rules-for-segregation-of-duties"></a>Verificar se as atribuições de função de usuário estão em conformidade com as novas regras para a diferenciação de direitos
1. Acesse **Administração do sistema > Segurança > Diferenciação de direitos > Verificar conformidade das atribuições de funções de usuário**.
2. Selecione **OK**. Uma notificação exibe os resultados da validação. Os conflitos são registrados na página **Conflitos não resolvidos da diferenciação de direitos**.   

Quando você atribui usuários a funções, as regras de diferenciação de direitos são automaticamente impostas. Se tentar atribuir um usuário a funções que contenham tarefas conflitantes, você receberá uma mensagem de erro. É necessário resolver o conflito negando ou permitindo a atribuição da função adicional. A função adicional será atribuída depois que a atribuição for permitida. 

> [!NOTE]
> No momento, os conflitos não são verificados para os usuários que atribuídos a funções com base nos grupos de domínio do Active Directory.

## <a name="view-and-resolve-conflicting-user-role-assignments"></a>Exiba e solucione as atribuições de função do usuário em conflito
1. Acesse **Administração do sistema** > **Segurança** > **Diferenciação de direitos** > **Conflitos não solucionados de diferenciação de direitos**. 
2. Selecione um conflito e depois selecione um das seguintes ações: 

  - **Negar atribuição**: isso nega a atribuição do usuário à função de segurança adicional. Se você negar uma atribuição de função automática, o usuário será marcado como excluído da função. O usuário excluído não obtém acesso associado à função concedido não pode ser designado à função até que o administrador remova a exclusão. 
-  **Permitir atribuição**: substitui o conflito e permite que o usuário seja designado a função de segurança adicional. Se você anular um conflito, deverá inserir um motivo no campo **Motivo de anulação**. Todas as atribuições de funções substituídas podem ser exibidas na página **Conflitos de diferenciação de direitos**.  

> [!NOTE]
> Se vários conflitos forem listados para o mesmo usuário, selecione o registro do usuário e avalie as funções atribuídas na página **Usuários**. Para evitar esse conflito, valide cada regra depois que ela for adicionada ou modificada.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
---
title: Identificar e resolver conflitos na diferenciação de direitos
description: Este tópico explica como identificar e resolver conflitos na diferenciação de direitos.
author: maertenm
manager: AnnBe
ms.date: 07/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesConflict, SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5c89d27eb8b587e8936258aae3ec1fee4574ccfb
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/02/2019
ms.locfileid: "1851326"
---
# <a name="identify-and-resolve-conflicts-in-segregation-of-duties"></a>Identificar e resolver conflitos na diferenciação de direitos

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este tópico explica como identificar e resolver conflitos na diferenciação de direitos. Você pode definir regras para separar tarefas que devem ser executadas por usuários diferentes. Este conceito é chamado de segregação de direitos. Quando a definição de uma função de segurança ou as atribuições de função de um usuário violam as regras, o conflito será registrado. Todos os conflitos devem ser solucionados pelo administrador. Complete o procedimento a seguir para identificar e solucionar conflitos. A empresa de dados demo usada para criar este procedimento é USMF.


## <a name="verify-whether-user-role-assignments-comply-with-new-rules-for-segregation-of-duties"></a>Verificar se as atribuições de função de usuário estão em conformidade com as novas regras para a diferenciação de direitos
1. Vá para **Painel de navegação > Módulos > Administração do sistema > Segurança > Diferenciação de direitos > Verificar conformidade das atribuições de função ao usuário**.
2. Selecione **OK**. Uma notificação exibe os resultados da validação. Se houver um conflito, você poderá abrir a página **Usuários** e alterar as atribuições de função do usuário. Conflitos também são registrados na página **Conflitos da diferenciação de direitos**. Para executar o processo de verificação como um trabalho em lotes, selecione **Processamento em lotes** e defina os outros parâmetros de lote. Depois que o trabalho em lotes for executado, você poderá revisar os conflitos na página **Conflitos da diferenciação de direitos**.  

## <a name="view-and-resolve-conflicting-user-role-assignments"></a>Exiba e solucione as atribuições de função do usuário em conflito
1. Vá para **Painel de navegação > Módulos > Administração do sistema > Segurança > Diferenciação de direitos > Conflitos da diferenciação de direitos**. Selecione um conflito, depois, um dos seguintes botões: **Negar atribuição – nega a atribuição do usuário à função de segurança adicional**. Se você negar uma atribuição de função automática, o usuário será marcado como excluído da função. O usuário excluído não terá o acesso associado à função concedido, e ele não poderá ser designado à função até que o administrador remova a exclusão. Permitir atribuição – **Anula** o conflito e permite que o usuário seja designado a ambas as funções de segurança. Se você anular um conflito, deverá inserir um motivo no campo **Motivo de anulação**.  
2. Feche a página.
3. Vá para **Painel de navegação > Módulos > Administração do sistema > Segurança > Diferenciação de direitos > Conflitos não resolvidos da diferenciação de direitos**. Selecione um conflito, depois, um dos seguintes botões: **Negar atribuição – nega a atribuição do usuário à função de segurança adicional**. Se você negar uma atribuição de função automática, o usuário será marcado como excluído da função. O usuário excluído não terá o acesso associado à função concedido, e ele não poderá ser designado à função até que o administrador remova a exclusão. Permitir atribuição – **Anula** o conflito e permite que o usuário seja designado a ambas as funções de segurança. Se você anular um conflito, deverá inserir um motivo no campo **Motivo de anulação**.    
4. Feche a página.

## <a name="verify-whether-existing-roles-comply-with-new-rules-for-segregation-of-duties"></a>Verificar se as funções existentes estão em conformidade com as novas regras para a diferenciação de direitos
1. Vá para **Painel de navegação > Módulos > Administração do sistema > Segurança > Diferenciação de direitos > Regras da diferenciação de direitos**. Selecione uma regra.  
2. Selecione **Validar direitos e funções**. Se qualquer função existente viola a regra selecionada, será exibida uma mensagem que contém o nome da função e os nomes dos direitos em conflito. O administrador deve indicar a redução risco de segurança ou alterar a função de forma que não viole as regras da diferenciação de direitos. Se nenhuma função viola a regra selecionada, uma mensagem indica que todas as funções estão em conformidade.  


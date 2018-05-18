--- 
title: "Atribuir usuários a funções de segurança"
description: "Para acessar o Microsoft Dynamics 365 for Finance and Operations, os usuários devem ser atribuídos a funções de segurança."
author: maertenm
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: da96ec8357ea209fd958e32ab438b13e668735df
ms.contentlocale: pt-br
ms.lasthandoff: 03/26/2018

---
# <a name="assign-users-to-security-roles"></a>Atribuir usuários a funções de segurança

[!include [task guide banner](../../includes/task-guide-banner.md)]

Para acessar o Microsoft Dynamics 365 for Finance and Operations, os usuários devem ser atribuídos a funções de segurança. Este processo explica como os administradores de sistemas podem atribuir usuários às funções automaticamente, com base nos dados comerciais. A empresa de dados demo usada para criar este procedimento é USMF.


## <a name="automatically-assign-users-to-roles"></a>Atribuir automaticamente usuários às funções
1. Vá para Administração do sistema > Segurança > Atribuir usuários a funções.
2. Na árvore, selecione "Supervisor de contabilidade".
    * Selecione a função para a qual deseja configurar a regra. Neste exemplo, selecione Supervisor de contabilidade.  
3. Clique em Adicionar regras para abrir a caixa de diálogo suspensa.
4. Na lista, localize e selecione o PDV desejado.
    * Selecione a consulta a ser usada para esta regra.  
5. Na lista, clique no link na linha selecionada.
6. Clique em Editar consulta.
    * Edite a consulta, conforme necessário.  
7. Clique em OK.

## <a name="exclude-users-from-automatic-role-assignment"></a>Excluir usuários de atribuição de função automática
1. Feche a página.
2. Vá para Administração do sistema > Segurança > Atribuir usuários a funções.
3. Na árvore, selecione "Supervisor de contabilidade".
    * Selecione uma função. Para este exemplo, selecione Supervisor de contabilidade.  
4. Clique em Atribuir/excluir usuários manualmente.
5. Na lista, marque a linha selecionada.
    * Selecione um usuário.  
6. Clique em Excluir da função.
    * Clique em Excluir da função para excluir os usuários selecionados da função. Para remover as exclusões, selecione os usuários que você deseja remover, e clique em Redefinir status. Quando você remover uma exclusão redefinindo o status do usuário, a função do usuário será atribuída automaticamente novamente. No entanto, o usuário não está atribuído à função imediatamente ou não será excluído da função quando você redefinir o status. Em vez disso, o usuário é atribuído à função ou removido da função da próxima vez que as regras para a atribuição de função automática são executadas.  



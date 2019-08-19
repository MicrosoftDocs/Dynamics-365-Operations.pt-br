---
title: Atribuir usuários a funções de segurança
description: Para acessar o Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, os usuários devem ser atribuídos às funções de segurança.
author: maertenm
manager: AnnBe
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecRolesEditUsers, SysSecAssignmentQueryLookup, SysQueryForm, SysSecRoleExcludeUsers
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4c0afd0f5754e59307a82af9c9700b36c31edcc4
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/02/2019
ms.locfileid: "1851350"
---
# <a name="assign-users-to-security-roles"></a>Atribuir usuários a funções de segurança

[!include [task guide banner](../../includes/task-guide-banner.md)]

Para acessar o Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, os usuários devem ser atribuídos às funções de segurança. Este processo explica como os administradores de sistemas podem atribuir usuários às funções automaticamente, com base nos dados comerciais. A empresa de dados demo usada para criar este procedimento é USMF.


## <a name="automatically-assign-users-to-roles"></a>Atribuir automaticamente usuários às funções
1. Vá para **Painel de navegação > Módulos > Administração do sistema > Segurança > Atribuir usuários a funções**.
2. Na árvore, selecione "Supervisor de contabilidade". Selecione a função para a qual deseja configurar a regra. Neste exemplo, selecione Supervisor de contabilidade. 
3. Clique em **Adicionar regra** para abrir a caixa de diálogo suspensa.
4. Na lista **Selecionar uma consulta**, localize e selecione o registro desejado. Selecione a consulta a ser usada para esta regra.  
5. Na lista **Nome da regra de associação**, clique no link na linha selecionada.
6. Clique em **Editar consulta**. Edite a consulta, conforme necessário.  
7. Clique em **OK**.

## <a name="exclude-users-from-automatic-role-assignment"></a>Excluir usuários de atribuição de função automática
1. Feche a página.
2. Vá para **Painel de navegação > Módulos > Administração do sistema > Segurança > Atribuir usuários a funções**.
3. Na árvore, selecione "Supervisor de contabilidade". Selecione uma função. Para este exemplo, selecione Supervisor de contabilidade.  
4. No menu **Usuários atribuídos à função**, selecione **Atribuir/excluir usuários manualmente**.
5. Na lista **Atribuir usuários ou excluir usuários da função**, marque a linha selecionada. Selecione um usuário.  
6. No **Painel de ação**, selecione **Excluir da função**.
    
    Clique em **Excluir da função** para excluir os usuários selecionados da função. Para remover as exclusões, selecione os usuários que você deseja remover e clique em **Redefinir status**. Quando você remover uma exclusão redefinindo o status do usuário, a função do usuário será atribuída automaticamente novamente. No entanto, o usuário não está atribuído à função imediatamente ou não será excluído da função quando você redefinir o status. Em vez disso, o usuário é atribuído à função ou removido da função da próxima vez que as regras para a atribuição de função automática são executadas.  

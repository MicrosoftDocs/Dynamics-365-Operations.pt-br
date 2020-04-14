---
title: Atribuir usuários a funções de segurança
description: Para acessar os aplicativos do Finance and Operations, os usuários devem ser atribuídos às funções de segurança.
author: ChrisGarty
manager: AnnBe
ms.date: 11/14/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecRolesEditUsers, SysSecAssignmentQueryLookup, SysQueryForm, SysSecRoleExcludeUsers
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0744f45ac91dfb9b5aae35091e3675202c9144f9
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143527"
---
# <a name="assign-users-to-security-roles"></a>Atribuir usuários a funções de segurança

[!include [banner](../../includes/banner.md)]

Para usar qualquer coisa além das funcionalidades comuns, os usuários devem ser atribuídos a funções de segurança. Este procedimento explica como os administradores do sistema podem atribuir usuários a funções automaticamente com base em dados corporativos. 

## <a name="automatically-assign-users-to-roles"></a>Atribuir automaticamente usuários às funções
1. Vá para **Painel de navegação > Módulos > Administração do sistema > Segurança > Atribuir usuários a funções**.
2. Na árvore, selecione "Supervisor de contabilidade". Selecione a função para a qual deseja configurar a regra. Neste exemplo, selecione Supervisor de contabilidade. 
3. Clique em **Adicionar regra** para abrir a caixa de diálogo suspensa.
4. Na lista **Selecionar uma consulta**, localize e selecione o registro desejado. Selecione a consulta a ser usada para esta regra.  
5. Na lista **Nome da regra de associação**, clique no link na linha selecionada.
6. Clique em **Editar consulta**. Edite a consulta, conforme necessário.  
7. Clique em **OK**.
8. Clique em **Executar atribuição de função automática**.
9. Vá para **Painel de navegação > Módulos > Administração do sistema > Usuários > Usuários** (de preferência em outra guia do navegador).
10. Examine as funções atribuídas para vários usuários para confirmar que a consulta de atribuição de função está correta. Faça os ajustes e execute novamente, se necessário.

## <a name="exclude-users-from-automatic-role-assignment"></a>Excluir usuários de atribuição de função automática
1. Feche a página.
2. Vá para **Painel de navegação > Módulos > Administração do sistema > Segurança > Atribuir usuários a funções**.
3. Na árvore, selecione "Supervisor de contabilidade". Selecione uma função. Para este exemplo, selecione Supervisor de contabilidade.  
4. No menu **Usuários atribuídos à função**, selecione **Atribuir/excluir usuários manualmente**.
5. Na lista **Atribuir usuários ou excluir usuários da função**, marque a linha selecionada. Selecione um usuário.  
6. No **Painel de ação**, selecione **Excluir da função**.
    
    Clique em **Excluir da função** para excluir os usuários selecionados da função. Para remover as exclusões, selecione os usuários que você deseja remover e clique em **Redefinir status**. Quando você remover uma exclusão redefinindo o status do usuário, a função do usuário será atribuída automaticamente novamente. No entanto, o usuário não está atribuído à função imediatamente ou não será excluído da função quando você redefinir o status. Em vez disso, o usuário é atribuído à função ou removido da função da próxima vez que as regras para a atribuição de função automática são executadas.  

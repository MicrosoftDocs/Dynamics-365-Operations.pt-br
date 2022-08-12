---
title: Atribuir usuários a funções de segurança
description: Para acessar os aplicativos de finanças e operações, os usuários devem ser atribuídos a direitos de acesso.
author: Peakerbl
ms.date: 02/09/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysSecRolesEditUsers, SysSecAssignmentQueryLookup, SysQueryForm, SysSecRoleExcludeUsers
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b5e69a79f123daff3f85d0100647615ad818288e
ms.sourcegitcommit: 12b3dbee905f8b2eb2e6c383c822a0fc9fccf063
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2022
ms.locfileid: "9103858"
---
# <a name="manage-users-and-security-roles"></a>Gerenciar usuários e funções de segurança

[!include [banner](../../includes/banner.md)]

Para usar qualquer coisa além das funcionalidades comuns nos aplicativos de finanças e operações, os usuários devem ser atribuídos a direitos de acesso. Você pode atribuir usuários a funções automaticamente, com base em regras e dados comerciais, excluir usuários da atribuição de função automática ou adicionar usuários a funções manualmente.

## <a name="automatically-assign-users-to-roles"></a>Atribuir automaticamente usuários às funções
Este procedimento explica como os administradores do sistema podem atribuir usuários a funções automaticamente com base em dados corporativos. 
1. Acesse **Painel de navegação > Módulos > Administração do sistema > Segurança > Atribuir usuários a funções**.
2. Na árvore, selecione "Supervisor de contabilidade". Selecione a função para a qual deseja configurar a regra. Neste exemplo, selecione Supervisor de contabilidade. 
3. Selecione **Adicionar regra** para abrir o menu de diálogo.
4. Na lista **Selecionar uma consulta**, localize e selecione o registro desejado. Selecione a consulta a ser usada para esta regra.  
5. Na lista **Nome da regra de associação**, clique no link na linha selecionada.
6. Selecione **Editar consulta**. Edite a consulta, conforme necessário.  
7. Selecione **OK**.
8. Selecione **Executar atribuição de função automática**.
9. Acesse **Painel de navegação > Módulos > Administração do sistema > Usuários > Usuários** (de preferência em outra guia do navegador).
10. Examine as funções atribuídas para vários usuários para confirmar que a consulta de atribuição de função está correta. Faça os ajustes e execute novamente, se necessário.

## <a name="exclude-users-from-automatic-role-assignment"></a>Excluir usuários de atribuição de função automática
Este procedimento explica como excluir usuários da atribuição de função automática.

1. Feche a página.
2. Acesse **Painel de navegação > Módulos > Administração do sistema > Segurança > Atribuir usuários a funções**.
3. Na árvore, selecione "Supervisor de contabilidade". Selecione uma função. Para este exemplo, selecione Supervisor de contabilidade.  
4. No menu **Usuários atribuídos à função**, selecione **Atribuir/excluir usuários manualmente**.
5. Na lista **Atribuir usuários ou excluir usuários da função**, marque a linha selecionada. Selecione um usuário.  
6. No **Painel de ação**, selecione **Excluir da função**.
7. Selecione **Excluir da função** para excluir os usuários selecionados da função. Para remover as exclusões, selecione os usuários que você deseja remover e clique em **Redefinir status**. Quando você remover uma exclusão redefinindo o status do usuário, a função do usuário será atribuída automaticamente. No entanto, o usuário não está atribuído à função imediatamente ou não será excluído da função quando você redefinir o status. Em vez disso, o usuário é atribuído à função ou removido da função da próxima vez que as regras para a atribuição de função automática são executadas.  

## <a name="manually-assign-users-to-roles"></a>Atribuir manualmente usuários a funções
Os usuários que são atribuídos manualmente a direitos de acesso também devem ser removidos manualmente pelo administrador. Esses usuários não são removidos das funções por regras para atribuição de função automática.

1. Acesse **Painel de navegação > Módulos > Administração do sistema > Segurança > Atribuir usuários a funções**.
2. Na árvore, selecione uma função e no menu **Usuários atribuídos à função**, selecione **Atribuir/excluir usuários manualmente**.
4. em **Atribuir usuários a ou excluir usuários da função**, os usuários que não receberam a função são listados com o **modo de atribuição** definido como **Nenhum**. Selecione um ou mais usuários aos quais a função deve ser atribuída.
5. No **Painel de ação**, selecione **Atribuir à função**. O **Modo de atribuição** é atualizado para **Manual** e os usuários agora têm uma nova função atribuída.

## <a name="manually-remove-users-from-roles"></a>Remover usuários das funções manualmente
Os usuários que são atribuídos manualmente a direitos de acesso também devem ser removidos manualmente pelo administrador. Esses usuários não são removidos das funções por regras para atribuição de função automática.

1. Acesse **Painel de navegação > Módulos > Administração do sistema > Segurança > Atribuir usuários a funções**.
2. Para remover um usuário, siga estas etapas:
   1. Na árvore, selecione uma função. 
   2. Na área **Usuários atribuídos à função**, selecione o usuário que deve ser removido.
   3. Selecione **Remover**, e o usuário será removido da função.
3. Para remover vários usuários, siga estas etapas:
   1. Na árvore, selecione uma função. 
   2. Na área **Usuários atribuídos à função**, selecione **Atribuir/excluir usuários manualmente**.
   3. Na página **Atribuir usuários a ou excluir usuários da função**, os usuários que não receberam a função têm **Nenhum** na coluna **Modo de atribuição**. Selecione os usuários que devem ser excluídos da função.
   4. No **Painel de ação**, selecione **Excluir da função**. Agora, a coluna **Modo de atribuição** foi atualizada para **Manual** e os usuários foram excluídos da função.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]


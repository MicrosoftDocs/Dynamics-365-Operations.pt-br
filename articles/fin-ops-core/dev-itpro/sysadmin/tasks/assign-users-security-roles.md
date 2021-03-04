---
title: Atribuir usuários a funções de segurança
description: Para acessar os aplicativos do Finance and Operations, os usuários devem ser atribuídos às funções de segurança.
author: Peakerbl
manager: AnnBe
ms.date: 05/06/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecRolesEditUsers, SysSecAssignmentQueryLookup, SysQueryForm, SysSecRoleExcludeUsers
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f78c24e8c2ffe5418ce119e19b7c0193f01f64b8
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679855"
---
# <a name="assign-users-to-security-roles"></a>Atribuir usuários a funções de segurança

[!include [banner](../../includes/banner.md)]

Para usar qualquer coisa além das funcionalidades comuns em aplicativos do Finance and Operations, os usuários devem ser atribuídos a funções de segurança. Você pode atribuir usuários a funções automaticamente, com base em regras e dados comerciais, excluir usuários da atribuição de função automática ou adicionar usuários a funções manualmente.

## <a name="automatically-assign-users-to-roles"></a>Atribuir automaticamente usuários às funções
Este procedimento explica como os administradores do sistema podem atribuir usuários a funções automaticamente com base em dados corporativos. 
1. Vá para **Painel de navegação > Módulos > Administração do sistema > Segurança > Atribuir usuários a funções**.
2. Na árvore, selecione "Supervisor de contabilidade". Selecione a função para a qual deseja configurar a regra. Neste exemplo, selecione Supervisor de contabilidade. 
3. Selecione **Adicionar regra** para abrir o menu de diálogo.
4. Na lista **Selecionar uma consulta**, localize e selecione o registro desejado. Selecione a consulta a ser usada para esta regra.  
5. Na lista **Nome da regra de associação**, clique no link na linha selecionada.
6. Selecione **Editar consulta**. Edite a consulta, conforme necessário.  
7. Selecione **OK**.
8. Selecione **Executar atribuição de função automática**.
9. Vá para **Painel de navegação > Módulos > Administração do sistema > Usuários > Usuários** (de preferência em outra guia do navegador).
10. Examine as funções atribuídas para vários usuários para confirmar que a consulta de atribuição de função está correta. Faça os ajustes e execute novamente, se necessário.

## <a name="exclude-users-from-automatic-role-assignment"></a>Excluir usuários de atribuição de função automática
1. Feche a página.
2. Vá para **Painel de navegação > Módulos > Administração do sistema > Segurança > Atribuir usuários a funções**.
3. Na árvore, selecione "Supervisor de contabilidade". Selecione uma função. Para este exemplo, selecione Supervisor de contabilidade.  
4. No menu **Usuários atribuídos à função**, selecione **Atribuir/excluir usuários manualmente**.
5. Na lista **Atribuir usuários ou excluir usuários da função**, marque a linha selecionada. Selecione um usuário.  
6. No **Painel de ação**, selecione **Excluir da função**.
7. Selecione **Excluir da função** para excluir os usuários selecionados da função. Para remover as exclusões, selecione os usuários que você deseja remover e clique em **Redefinir status**. Quando você remover uma exclusão redefinindo o status do usuário, a função do usuário será atribuída automaticamente. No entanto, o usuário não está atribuído à função imediatamente ou não será excluído da função quando você redefinir o status. Em vez disso, o usuário é atribuído à função ou removido da função da próxima vez que as regras para a atribuição de função automática são executadas.  

## <a name="manually-assign-users-to-roles"></a>Atribuir manualmente usuários a funções
Os usuários que são atribuídos manualmente a direitos de acesso também devem ser removidos manualmente pelo administrador. Esses usuários não são removidos das funções por regras para atribuição de função automática.

1. Vá para **Painel de navegação > Módulos > Administração do sistema > Segurança > Atribuir usuários a funções**.
2. Na árvore, selecione uma função e no menu **Usuários atribuídos à função**, selecione **Atribuir/excluir usuários manualmente**.
4. em **Atribuir usuários a ou excluir usuários da função**, os usuários que não receberam a função são listados com o **modo de atribuição** definido como **Nenhum**. Selecione um ou mais usuários aos quais a função deve ser atribuída.
5. No **Painel de ação**, selecione **Atribuir à função**. O **Modo de atribuição** é atualizado para **Manual** e os usuários agora têm uma nova função atribuída.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
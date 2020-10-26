---
title: Criar novos usuários
description: Os usuários são funcionários internos da sua organização, ou clientes e fornecedores externos, que precisam de acesso ao sistema para realizar seus trabalhos.
author: maertenm
manager: AnnBe
ms.date: 06/08/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysDataAreaSelectLookup, SysSecUserAddRoles, SysUserMSODSUserImport
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5e84130ff2b1cf83b7d2b95eefc72175dc57743c
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3982493"
---
# <a name="create-new-users"></a>Criar novos usuários

[!include [banner](../../includes/banner.md)]

Os usuários são funcionários internos da sua organização ou clientes e fornecedores externos que precisam de acesso ao sistema para realizar seus trabalhos.

## <a name="associate-a-user-with-a-license-new-license-types-only"></a>Associar um usuário a uma licença (somente novos tipos de licença)
Para os clientes que têm um dos novos tipos de licença adicionados em outubro de 2019, os usuários devem ser associados a uma licença. Os usuários associados a uma licença são adicionados automaticamente como usuários do sistema que não têm funções na primeira vez em que entram.

Os administradores do sistema podem [atribuir licenças a usuários](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) no [Centro de administração do Microsoft 365](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide).

## <a name="associate-an-external-user-with-a-license-new-license-types-only"></a>Associar um usuário externo a uma licença (somente novos tipos de licença)
Os usuários externos ao locatário em que o ambiente foi implantado precisam ser representados no diretório de locatários host (Azure Active Directory (Azure AD)) para que possam receber licenças. Esses usuários externos devem ser adicionados ao locatário no Azure AD como usuários convidados para depois poderem receber as licenças apropriadas. Para obter mais informações, consulte [Adicionar usuários de colaboração B2B do Azure Active Directory no portal do Azure](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).

## <a name="add-a-new-user"></a>Adicionar um novo usuário
1. Vá para **Administração do sistema \> Usuários \> Usuários**.
2. No Painel de Ações, selecione **Novo**.
3. No campo **ID do usuário**, insira um identificador exclusivo para o usuário. Um ID de usuário é necessário.  
4. No campo **Nome do usuário**, insira o nome do usuário.  
5. No campo **Domínio**, insira o domínio do usuário.  
6. No campo **Alias** , insira o apelido do usuário.  
7. No campo **Empresa**, selecione a empresa desejada. 
8. Na FastTab **Funções do usuário**, selecione **Atribuir funções** para atribuir usuários a funções de segurança. Para obter mais informações, consulte [Atribuir usuários a funções de segurança](assign-users-security-roles.md).
9. Selecione **OK**.
10. Selecione **Salvar**.

## <a name="import-users"></a>Importar usuários
1. Vá para **Administração do sistema \> Usuários \> Usuários**.
2. No Painel de Ação, selecione **Importar usuários**.
3. Na lista, marque a linha selecionada.
4. Selecione **Importar usuários**.
5. Selecione **Fechar**.


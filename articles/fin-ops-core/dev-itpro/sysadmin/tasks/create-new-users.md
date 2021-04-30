---
title: Criar novos usuários
description: Os usuários são funcionários internos da sua organização, ou clientes e fornecedores externos, que precisam de acesso ao sistema para realizar seus trabalhos.
author: peakerbl
ms.date: 01/12/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysUserManagement, SysDataAreaSelectLookup, SysSecUserAddRoles, SysUserMSODSUserImport
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 88d3f1fba05d944e78e4595018d190c3dc41e076
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2021
ms.locfileid: "5907902"
---
# <a name="create-new-users"></a>Criar usuários

[!include [banner](../../includes/banner.md)]

Para poder acessar os aplicativos do Finance and Operations, você deve ser adicionado à página **Usuários** (**Administração do sistema \> Usuários \> Usuários**). Os usuários incluem funcionários internos da sua organização ou clientes e fornecedores externos. Os usuários podem ser importados ou adicionados manualmente. Todos os usuários devem estar licenciados corretamente para uso em conformidade.

Para obter informações sobre como comprar e obter licença para aplicativos do Finance and Operations, consulte o [Guia de licenciamento do Microsoft Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544&amp;clcid=0x409).

## <a name="assign-a-license-to-a-user"></a>Atribuir uma licença a um usuário
Os administradores do sistema podem [atribuir licenças a usuários](/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) no [Centro de administração do Microsoft 365](/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide).

## <a name="add-an-external-user-in-azure-ad-and-assign-a-license"></a>Adicionar um usuário externo no Azure AD e atribuir uma licença 
Os usuários externos devem ser representados no seu diretório de locatários (Azure Active Directory (Azure AD)) para poderem receber licenças. Esses usuários externos devem ser adicionados ao locatário no Azure AD como usuários convidados para depois poderem receber as licenças apropriadas. Um requisito para aplicativos do Finance and Operations é que a empresa do usuário convidado use o Azure AD. Para obter mais informações, consulte [Adicionar usuários de colaboração B2B do Azure Active Directory no portal do Azure](/azure/active-directory/b2b/add-users-administrator).

## <a name="import-new-users-from-azure-ad"></a>Importar novos usuários do Azure AD 
1. Vá para **Administração do sistema** \> **Usuários** \> **Usuários**.
2. No Painel de Ação, selecione **Importar usuários**.
3. Selecione os usuários que serão importados. A lista inclui usuários do Azure AD que atualmente não são usuários neste ambiente.
4. Selecione **Importar usuários**.
5. Selecione **Fechar**.

> [!NOTE]
> O valor do campo **Empresa** será definido com base na empresa da sessão atual para o administrador. Após a importação, você deve atribuir funções e organizações conforme necessário. Para obter mais informações, consulte [Atribuir usuários a funções de segurança](assign-users-security-roles.md). Também pode ser necessário associar o usuário a uma **Pessoa** e atualizar as opções do usuário, como idioma.

## <a name="manually-add-a-new-user"></a>Adicionar um novo usuário manualmente
1. Vá para **Administração do sistema** \> **Usuários** \> **Usuários**.
2. No Painel de Ações, selecione **Novo**.
3. No campo **ID do usuário**, insira um identificador exclusivo para o usuário.   
4. No campo **Nome do usuário**, insira o nome do usuário.  
5. No campo **Provedor**:
 - Para usuários internos, use o valor padrão. Por exemplo, seu locatário do Azure AD com prefixo https://sts.windows.net/.  
 - Para usuários que não têm o Azure AD, como contas do tipo Service-2-Service, insira um valor de texto básico. Por exemplo, ND. Esse valor ajudará a evitar chamadas de autenticação incorretas que podem resultar em erros se um valor de provedor de identidade válido for usado.  
 - Para usuários externos ou convidados, adicione seu nome de locatário do Azure AD depois de https://sts.windows.net/.
6. No campo **Email**, insira o Email/Nome de princípio completo do usuário.  
7. No campo **Empresa**, selecione a empresa inicial padrão para o usuário. 
8. Selecione **Salvar**.

Os valores para o provedor de identidade e a ID de telemetria serão atualizados com base em uma chamada do [Microsoft Graph](/graph/overview), quando o registro de usuário for salvo. O ID de telemetria baseia-se no ID de objeto/SID (identificador de segurança) do usuário no Azure AD.

> [!NOTE]
> Depois de adicionar um usuário, você deve atribuir funções e organizações conforme aplicável. Para obter mais informações, consulte [Atribuir usuários a funções de segurança](assign-users-security-roles.md). Também pode ser necessário associar o usuário a uma **Pessoa** e atualizar as **Opções do usuário**, como idioma.

## <a name="change-a-user-id"></a>Alterar um ID de usuário
Para alterar um ID de usuário, você deve renomear a chave no banco de dados. Quando você altera um ID de usuário usando este procedimento, todas as configurações de usuário relacionadas são modificadas para usar o novo ID de usuário. Por exemplo, as informações de uso na tabela **SysLastValue** são atualizadas para referenciar o novo ID de usuário.

> [!NOTE]
> O ID de usuário é a chave primária da tabela de informações do usuário. Renomear a chave primária pode levar algum tempo para os usuários existentes porque todas as referências à chave também são atualizadas no banco de dados. 

1. Vá para **Administração do sistema \> Usuários \> Usuários**.
2. Selecione um usuário na lista e selecione **Opções\> Registrar informações**.
3. Selecione **Renomear**.
4. Insira um valor novo e exclusivo para o ID de usuário e selecione **OK**. 
5. Selecione **Sim** para confirmar.

## <a name="additional-resources"></a>Recursos adicionais

Para obter mais opções de implementação de usuários B2B, consulte [Exportar usuários B2B para o Azure AD](../implement-b2b.md).

Para obter informações sobre contas de sistema pré-configuradas, consulte [Contas de sistema pré-configuradas](../pre-configured-system-accounts.md)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
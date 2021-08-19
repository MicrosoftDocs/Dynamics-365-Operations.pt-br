---
title: Configurar autenticação do Azure Active Directory para entrada de PDV
description: Este tópico explica como configurar o Azure Active Directory como o método de autenticação no ponto de venda do Microsoft Dynamics 365 Commerce.
author: boycezhu
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: boycez
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 14d8ac93241d05245ad989bcb3cb35aaf8969164d6cfc6010a8e9d426987a1ca
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6716291"
---
# <a name="configure-azure-active-directory-authentication-for-pos-sign-in"></a>Configurar autenticação do Azure Active Directory para entrada de PDV

[!include [banner](includes/banner.md)]

Este tópico explica como configurar o Azure Active Directory (Azure AD) como o método de autenticação no ponto de venda (PDV) do Microsoft Dynamics 365 Commerce.

Os varejistas que usam o Dynamics 365 Commerce junto com outros serviços em nuvem da Microsoft, como o Microsoft Azure, Microsoft 365 e Microsoft Teams geralmente querem usar o Azure AD para o gerenciamento centralizado de credenciais de usuário para uma experiência de entrada segura e perfeita entre aplicativos. Para usar a autenticação do Azure AD para PDV do Commerce, primeiro você deve configurar o Azure AD como o método de autenticação no Commerce Headquarters.

## <a name="configure-pos-authentication-method"></a>Configurar método de autenticação do PDV

Para configurar o método de autenticação do PDV no Commerce headquarters, siga estas etapas.
    
1. Acesse **Varejo e Comércio \> Configuração do canal \> Configuração do PDV \> Perfis de PDV \> Perfis de funcionalidade** e selecione um perfil de funcionalidade a ser alterado.
1. Na seção **Logon da equipe de PDV** da FastTab **Funções**, selecione uma opção do método de autenticação desejado na lista suspensa **Método de autenticação de logon**.

    O **Método de autenticação de logon** tem três opções:
    
    - **ID e Senha de Pessoal** - essa opção padrão requer que os usuários do PDV insiram uma ID de pessoal e senha para entrar no PDV e na funcionalidade de substituição do gerenciador de acesso.
    - **Azure AD sem o logon único** - essa opção exige que os usuários do PDV usem as credenciais do Azure AD para entrar no PDV e acessar a funcionalidade de substituição gerenciador. Quando o cliente de PDV for atualizado ou reaberto, o usuário de PDV deverá fornecer credenciais do Azure AD para entrar novamente.
    - **Azure AD com o logon único** - quando essa opção é selecionada, os usuários do PDV podem entrar no PDV em Nuvem (CPOs) usando credenciais ativas do Azure AD, que estão sendo usadas por outros aplicativos Web no mesmo navegador da Web, ou entrar no Modern PDV (MPOs) usando credenciais do Azure AD registradas no Windows. Os dois métodos permitem entrada sem a necessidade de inserir credenciais do Azure AD na tela de entrada do PDV. No entanto, o acesso à funcionalidade de substituição do gerenciador PDV ainda exigirá entrada usando credenciais do Azure AD.

1. Acesse **Varejo e Comércio > TI de Varejo e Comércio> Agenda de distribuição** e execute o trabalho **1070 (Configuração do canal)** para sincronizar as configurações de perfil de funcionalidade mais recente para clientes de PDV.

> [!NOTE]
> - A opção do método de autenticação **Azure AD sem logon único** substitui a opção **Azure Active Directory** na versão 10.0.18 e anterior do Commerce.
> - A autenticação do Azure AD requer uma conexão com a Internet ativa e não funcionará quando o PDV estiver off-line.

## <a name="associate-azure-ad-accounts-with-pos-users"></a>Associar contas do Azure AD a usuários do PDV

Para usar o Azure AD como o método de autenticação de PDV, você deve associar contas do Azure AD a usuários de PDV no Commerce Headquarters. 

Para associar contas do Azure AD a usuários do PDV no Commerce Headquarters, siga estas etapas.
    
1. Acesse **Varejo e Comércio > Funcionários > Trabalhadores** e abra um registro de trabalhador.
1. No Painel de Ações, selecione a guia **Commerce**, em **Identidade externa**, selecione **Associar identidade existente**. 
1. Na caixa de diálogo **Usar identidade externa existente**, selecione **Pesquisar usando email**, insira um endereço de email do Azure AD e depois selecione **Pesquisar**.
1. Selecione a conta do Azure AD retornada, em seguida, selecione **OK**.

Após as etapas de configuração acima, os campos **Alias**, **UPN** e **Subidentificador externo** da guia **Commerce** da página de detalhes do trabalhador serão preenchidos.

Você deve executar o trabalho **1060 (Equipe)** no **Varejo e Comércio > TI de Varejo e Comércio > Agenda de distribuição** para sincronizar o usuário PDV mais recente e os dados da conta do Azure AD para o canal.

> [!NOTE]
> Como prática recomendada, depois que as informações do trabalhador, como senha, permissão de PDV, conta associada do Azure AD ou catálogo de endereços do funcionário forem atualizadas no Commerce Headquarters, é altamente recomendável executar o trabalho **1060 (Equipe)** para sincronizar as informações mais recentes do trabalhador com o canal. O cliente PDV pode buscar os dados corretos para a autenticação de usuário e verificações de autorização.

## <a name="pos-lock-register-and-sign-out-with-azure-ad-authentication"></a>Registro e inscrição de bloqueio de PDV com autenticação do Azure AD

Ocorre o seguinte quando o PDV está configurado para usar o método de autenticação do Azure AD:

- A função **Bloquear registro** não estará disponível no aplicativo PDV. 
- A função **Bloqueio automático** se comportará da mesma forma que a função **Logoff automático**.
- Se o usuário do PDV selecionar **Fazer logoff**, será solicitado que ele entre com as credenciais do Azure AD na próxima vez que o PDV for iniciado, independentemente de o início de logon único estar habilitado.

## <a name="manager-override-functionality-with-azure-ad-authentication"></a>Funcionalidade de substituição do gerenciador com autenticação do Azure AD

Quando o PDV estiver configurado para usar a autenticação do Azure AD, a funcionalidade de substituição do gerente abrirá uma caixa de diálogo que solicitará as credenciais do usuário do gerente do Azure AD. Depois que a entrada do gerenciador for aprovada, as credenciais do gerente do Azure AD serão descartadas e as credenciais do usuário anterior do Azure AD serão usadas para operações subsequentes de PDV.

> [!NOTE]
> - Nas versões 10.0.18 e anteriores do Commerce, a função de substituição do gerente não oferece suporte ao Azure AD. Uma ID e senha de pessoal são necessárias mesmo que o PDV seja configurado para usar o método de autenticação do Azure AD.
> - Ao usar CPOS com o navegador Safari Web em um dispositivo Apple iOS, você deve primeiro desativar **Bloquear Pop-ups** nas configurações do Safari para a funcionalidade de substituição do gerenciador para trabalhar com a autenticação do Azure AD. 

## <a name="security-best-practices-for-azure-ad-based-pos-authentication-on-shared-devices"></a>Práticas recomendadas de segurança para autenticação de PDV com base no Azure AD em dispositivos compartilhados

Muitos varejistas configuram seu ambiente de loja de varejo de forma que vários usuários precisem acessar o aplicativo PDV a partir de um dispositivo físico compartilhado. Nesse contexto, enquanto o logon único oferece uma experiência de autenticação conveniente e uniforme, ele também pode criar uma loophole de segurança em que o usuário atual do PDV pode não perceber que as credenciais de outro usuário estão sendo usadas para executar transações ou operações no PDV. Antes de configurar o PDV para usar o método de autenticação do Azure AD, é altamente recomendável rever a política de segurança e as configurações de entrada do dispositivo compartilhado para decidir qual opção é a mais adequada.

- Se o seu ambiente de varejo usar uma conta compartilhada (por exemplo, uma conta local) para a entrada de dispositivo físico, é recomendável usar a opção **Azure AD sem logon único**. Isso garante que cada usuário do PDV forneça credenciais do Azure AD explicitamente para entrar no PDV.
- Se o seu ambiente de varejo exigir que os funcionários usem suas próprias contas do Azure AD para entrar no PDV e o dispositivo físico for hospedado, é recomendável usar a opção **Azure AD com logon único**.

## <a name="additional-resources"></a>Recursos adicionais

[Configurar um trabalhador](tasks/worker.md)

[Criar um perfil de funcionalidade de varejo](retail-functionality-profile.md)


[Configurar a funcionalidade de logon estendido para MPOS e PDV em Nuvem](extended-logon.md)

[Práticas recomendadas de segurança para PDV em Nuvem em ambientes compartilhados](dev-itpro/secure-retail-cloud-pos.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]

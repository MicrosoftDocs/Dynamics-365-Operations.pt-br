---
title: Habilitar a autenticação do Azure Active Directory para acesso ao PDV
description: Este tópico explica como configurar a experiência de logon no ponto de venda (PDV) do Microsoft Dynamics 365 Commerce para que ele use a autenticação do Azure Active Directory.
author: boycezhu
manager: annbe
ms.date: 03/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: boycezhu
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: dfc49585434383385b6b993893d93b95ef888384
ms.sourcegitcommit: ff6dde637d2f5d2bd18a582eb41573d4c69acdd6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2020
ms.locfileid: "3248931"
---
# <a name="enable-azure-active-directory-authentication-for-pos-sign-in"></a>Habilitar a autenticação do Azure Active Directory para acesso ao PDV
[!include [banner](includes/banner.md)]


Muitos clientes que usam o Microsoft Dynamics 365 Commerce também usam outros serviços de nuvem da Microsoft e podem usar o Azure Active Directory (Azure AD) para gerenciar credenciais de usuário desses serviços. Nesses casos, os clientes podem querer usar a mesma conta do Azure AD nos aplicativos. Este tópico explica como configurar a experiência de logon no ponto de venda (PDV) do Commerce para usar a autenticação do Azure AD.

## <a name="configure-azure-ad-authentication"></a>Configurar a autenticação do Azure AD

Para disponibilizar o Azure AD como o método de autenticação para o logon do PDV em uma loja, você deve definir as configurações do perfil de funcionalidade da loja e aplicá-las aos clientes do PDV.

Para configurar um novo perfil de funcionalidade, siga as etapas a seguir.

1. Vá para **Retail e Commerce** \> **Configuração de canal** \> **Configuração do PDV** \> **Perfis de PDV** \> **Perfis de funcionalidade**.
1. Selecione o perfil de funcionalidade a ser alterado.
1. Na FastTab **Funções**, na seção **Logo da equipe do PDV**, altere o valor do campo **Método de autenticação de logon** de **ID e senha de pessoal** para **Azure Active Directory**.

Por padrão, todos os perfis de funcionalidade usam **ID e senha de pessoal** como o método de autenticação do PDV. Portanto, você deve alterar o valor do campo **Método de autenticação de logon** se desejar usar o Azure AD. Toda loja de varejo vinculada ao perfil de funcionalidade selecionado será afetada por essa alteração.

Para aplicar as configurações aos clientes de PDV, siga as etapas a seguir.

1. Vá para **Retail e Commerce** \> **TI de Varejo e Comércio** \> **Agenda de distribuição**.
1. Execute a agenda de distribuição **1070** (**configuração de canal**).

> [!NOTE]
> A autenticação do Azure AD requer uma conexão com a Internet. Não funcionará quando o PDV estiver no modo offline.

## <a name="associate-an-azure-ad-account-with-a-worker"></a>Associar uma conta do Azure AD a um trabalhador

Para que um trabalhador da loja possa usar uma conta do Azure AD para entrar no aplicativo do PDV, a conta do Azure AD deve estar associada a esse trabalhador.

Para associar uma conta do Azure AD a um trabalhador, siga as etapas a seguir.

1. Acesse **Varejo e Comércio** \> **Funcionários** \> **Trabalhadores**.
1. Abra a página de detalhes de um trabalhador.
1. No Painel de Ação, na guia **Commerce**, no grupo **Identidade externa**, selecione **Associar identidade existente**.
1. Na caixa de diálogo **Usar identidade externa existente**, selecione **Pesquisar usando email**, insira um endereço de email do Azure AD e depois selecione **Pesquisar**.
1. Selecione a conta do Azure AD retornada e, em seguida, selecione **OK**.

Os campos **Alias**, **UPN** e **Subidentificador externo** na guia **Commerce** da página de detalhes do trabalhador serão preenchidos.

## <a name="additional-resources"></a>Recursos adicionais

[Configurar a funcionalidade de logon estendido para MPOS e PDV em Nuvem](extended-logon.md)

[Criar um perfil de funcionalidade de varejo](retail-functionality-profile.md)

[Configurar um trabalhador](https://docs.microsoft.com/dynamics365/commerce/tasks/worker)

---
title: Habilitar a autenticação do Azure Active Directory para acesso ao PDV
description: Este tópico explica como configurar a experiência de logon no ponto de venda (PDV) do Microsoft Dynamics 365 Commerce para que ele use a autenticação do Azure Active Directory.
author: boycezhu
manager: annbe
ms.date: 05/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: boycezhu
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: 4f5a02348e8cef44424ae5d6a49de02d762ba245
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410026"
---
# <a name="enable-azure-active-directory-authentication-for-pos-sign-in"></a><span data-ttu-id="c397b-103">Habilitar a autenticação do Azure Active Directory para acesso ao PDV</span><span class="sxs-lookup"><span data-stu-id="c397b-103">Enable Azure Active Directory authentication for POS sign-in</span></span>
[!include [banner](includes/banner.md)]


<span data-ttu-id="c397b-104">Muitos clientes que usam o Microsoft Dynamics 365 Commerce também usam outros serviços de nuvem da Microsoft e podem usar o Azure Active Directory (Azure AD) para gerenciar credenciais de usuário desses serviços.</span><span class="sxs-lookup"><span data-stu-id="c397b-104">Many customers who use Microsoft Dynamics 365 Commerce also use other Microsoft cloud services, and they might use Azure Active Directory (Azure AD) to manage user credentials for those services.</span></span> <span data-ttu-id="c397b-105">Nesses casos, os clientes podem querer usar a mesma conta do Azure AD nos aplicativos.</span><span class="sxs-lookup"><span data-stu-id="c397b-105">In those cases, the customers might want to use the same Azure AD account across applications.</span></span> <span data-ttu-id="c397b-106">Este tópico explica como configurar a experiência de logon no ponto de venda (PDV) do Commerce para usar a autenticação do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c397b-106">This topic explains how to configure the Commerce point of sale (POS) sign-in experience to use Azure AD authentication.</span></span>

## <a name="configure-azure-ad-authentication"></a><span data-ttu-id="c397b-107">Configurar a autenticação do Azure AD</span><span class="sxs-lookup"><span data-stu-id="c397b-107">Configure Azure AD authentication</span></span>

<span data-ttu-id="c397b-108">Para disponibilizar o Azure AD como o método de autenticação para o logon do PDV em uma loja, você deve definir as configurações do perfil de funcionalidade da loja e aplicá-las aos clientes do PDV.</span><span class="sxs-lookup"><span data-stu-id="c397b-108">To make Azure AD available as the authentication method for POS sign-in for a store, you must configure the settings of the store's functionality profile and then apply those setting to POS clients.</span></span>

<span data-ttu-id="c397b-109">Para configurar um novo perfil de funcionalidade, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="c397b-109">To configure a functionality profile, follow these steps.</span></span>

1. <span data-ttu-id="c397b-110">Vá para **Retail e Commerce** \> **Configuração de canal** \> **Configuração do PDV** \> **Perfis de PDV** \> **Perfis de funcionalidade**.</span><span class="sxs-lookup"><span data-stu-id="c397b-110">Go to **Retail and Commerce** \> **Channel setup** \> **POS setup** \> **POS profiles** \> **Functionality profiles**.</span></span>
1. <span data-ttu-id="c397b-111">Selecione o perfil de funcionalidade a ser alterado.</span><span class="sxs-lookup"><span data-stu-id="c397b-111">Select the functionality profile to change.</span></span>
1. <span data-ttu-id="c397b-112">Na FastTab **Funções**, na seção **Logo da equipe do PDV**, altere o valor do campo **Método de autenticação de logon** de **ID e senha de pessoal** para **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="c397b-112">On the **Functions** FastTab, in the **POS staff logon** section, change the value of the **Logon Authentication Method** field from **Personnel ID and Password** to **Azure Active Directory**.</span></span>

<span data-ttu-id="c397b-113">Por padrão, todos os perfis de funcionalidade usam **ID e senha de pessoal** como o método de autenticação do PDV.</span><span class="sxs-lookup"><span data-stu-id="c397b-113">By default, all functionality profiles use **Personnel ID and Password** as the POS authentication method.</span></span> <span data-ttu-id="c397b-114">Portanto, você deve alterar o valor do campo **Método de autenticação de logon** se desejar usar o Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c397b-114">Therefore, you must change the value of the **Logon Authentication Method** field if you want to use Azure AD.</span></span> <span data-ttu-id="c397b-115">Toda loja de varejo vinculada ao perfil de funcionalidade selecionado será afetada por essa alteração.</span><span class="sxs-lookup"><span data-stu-id="c397b-115">Every retail store that is linked to the selected functionality profile will be affected by this change.</span></span>

<span data-ttu-id="c397b-116">Para aplicar as configurações aos clientes de PDV, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="c397b-116">To apply the settings to POS clients, follow these steps.</span></span>

1. <span data-ttu-id="c397b-117">Vá para **Retail e Commerce** \> **TI de Varejo e Comércio** \> **Agenda de distribuição**.</span><span class="sxs-lookup"><span data-stu-id="c397b-117">Go to **Retail and Commerce** \> **Retail and Commerce IT** \> **Distribution schedule**.</span></span>
1. <span data-ttu-id="c397b-118">Execute a agenda de distribuição **1070** (**configuração de canal**).</span><span class="sxs-lookup"><span data-stu-id="c397b-118">Run the **1070** (**Channel configuration**) distribution schedule.</span></span>

> [!NOTE]
> <span data-ttu-id="c397b-119">A autenticação do Azure AD requer uma conexão com a Internet.</span><span class="sxs-lookup"><span data-stu-id="c397b-119">Azure AD authentication requires an internet connection.</span></span> <span data-ttu-id="c397b-120">Não funcionará quando o PDV estiver no modo offline.</span><span class="sxs-lookup"><span data-stu-id="c397b-120">It won't work when POS is in offline mode.</span></span>
> 
> <span data-ttu-id="c397b-121">No momento, a função **substituição do gerente** não oferece suporte ao Azure AD como método de autenticação.</span><span class="sxs-lookup"><span data-stu-id="c397b-121">Currently, the **Manager override** function doesn't support Azure AD as an authentication method.</span></span> <span data-ttu-id="c397b-122">Uma ID de operador e uma senha são necessárias mesmo que o Azure AD esteja configurado como o método de autenticação para a entrada do PDV.</span><span class="sxs-lookup"><span data-stu-id="c397b-122">An operator ID and password are required even if Azure AD is configured as the authentication method for POS sign-in.</span></span>

## <a name="associate-an-azure-ad-account-with-a-worker"></a><span data-ttu-id="c397b-123">Associar uma conta do Azure AD a um trabalhador</span><span class="sxs-lookup"><span data-stu-id="c397b-123">Associate an Azure AD account with a worker</span></span>

<span data-ttu-id="c397b-124">Para que um trabalhador da loja possa usar uma conta do Azure AD para entrar no aplicativo do PDV, a conta do Azure AD deve estar associada a esse trabalhador.</span><span class="sxs-lookup"><span data-stu-id="c397b-124">Before a store worker can use an Azure AD account to sign in to the POS application, the Azure AD account must be associated with that worker.</span></span>

<span data-ttu-id="c397b-125">Para associar uma conta do Azure AD a um trabalhador, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="c397b-125">To associate an Azure AD account with a worker, follow these steps.</span></span>

1. <span data-ttu-id="c397b-126">Acesse **Varejo e Comércio** \> **Funcionários** \> **Trabalhadores**.</span><span class="sxs-lookup"><span data-stu-id="c397b-126">Go to **Retail and Commerce** \> **Employees** \> **Workers**.</span></span>
1. <span data-ttu-id="c397b-127">Abra a página de detalhes de um trabalhador.</span><span class="sxs-lookup"><span data-stu-id="c397b-127">Open the details page for a worker.</span></span>
1. <span data-ttu-id="c397b-128">No Painel de Ação, na guia **Commerce**, no grupo **Identidade externa**, selecione **Associar identidade existente**.</span><span class="sxs-lookup"><span data-stu-id="c397b-128">On the Action Pane, on the **Commerce** tab, in the **External identity** group, select **Associate existing identity**.</span></span>
1. <span data-ttu-id="c397b-129">Na caixa de diálogo **Usar identidade externa existente**, selecione **Pesquisar usando email**, insira um endereço de email do Azure AD e depois selecione **Pesquisar**.</span><span class="sxs-lookup"><span data-stu-id="c397b-129">In the **Use existing external identity** dialog box, select **Search using email**, enter an Azure AD email address, and then select **Search**.</span></span>
1. <span data-ttu-id="c397b-130">Selecione a conta do Azure AD retornada e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="c397b-130">Select the Azure AD account that is returned, and then select **OK**.</span></span>

<span data-ttu-id="c397b-131">Os campos **Alias**, **UPN** e **Subidentificador externo** na guia **Commerce** da página de detalhes do trabalhador serão preenchidos.</span><span class="sxs-lookup"><span data-stu-id="c397b-131">The **Alias**, **UPN**, and **External sub identifier** fields on the **Commerce** tab of the worker's details page will be filled in.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c397b-132">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="c397b-132">Additional resources</span></span>

[<span data-ttu-id="c397b-133">Configurar a funcionalidade de logon estendido para MPOS e PDV em Nuvem</span><span class="sxs-lookup"><span data-stu-id="c397b-133">Set up extended logon functionality for MPOS and Cloud POS</span></span>](extended-logon.md)

[<span data-ttu-id="c397b-134">Criar um perfil de funcionalidade de varejo</span><span class="sxs-lookup"><span data-stu-id="c397b-134">Create a retail functionality profile</span></span>](retail-functionality-profile.md)

[<span data-ttu-id="c397b-135">Configurar um trabalhador</span><span class="sxs-lookup"><span data-stu-id="c397b-135">Configure a worker</span></span>](https://docs.microsoft.com/dynamics365/commerce/tasks/worker)

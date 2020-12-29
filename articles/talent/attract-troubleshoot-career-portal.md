---
title: Os usuários do Attract não podem se candidatar a empregos pelo portal de carreiras
description: Este tópico explica como solucionar um problema em que usuários do Attract não podem se candidatar a empregos pelo portal de carreiras.
author: andreabichsel
manager: AnnBe
ms.date: 09/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-09-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: e1d72bef6d8bbe15e27326f66341915ba44a09b4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4460295"
---
# <a name="attract-users-cant-apply-for-jobs-from-career-portal"></a><span data-ttu-id="8a39e-103">Os usuários do Attract não podem se candidatar a empregos pelo portal de carreiras</span><span class="sxs-lookup"><span data-stu-id="8a39e-103">Attract users can't apply for jobs from career portal</span></span>

[!include [banner](includes/banner.md)]

## <a name="issue"></a><span data-ttu-id="8a39e-104">Problema</span><span class="sxs-lookup"><span data-stu-id="8a39e-104">Issue</span></span>

<span data-ttu-id="8a39e-105">Os usuários do Attract não podem se candidatar a empregos no portal de carreiras.</span><span class="sxs-lookup"><span data-stu-id="8a39e-105">Attract users can't apply for jobs from the career portal.</span></span> <span data-ttu-id="8a39e-106">Ao tentarem se candidatar a um trabalho criado no Dynamics 365 Talent: Attract, o navegador carrega a página continuamente e não conclui a ação.</span><span class="sxs-lookup"><span data-stu-id="8a39e-106">When they try to apply for a job that was created in Dynamics 365 Talent: Attract, the browser loads the page continuously and doesn't complete the action.</span></span>

## <a name="cause"></a><span data-ttu-id="8a39e-107">Causa</span><span class="sxs-lookup"><span data-stu-id="8a39e-107">Cause</span></span>

<span data-ttu-id="8a39e-108">Esse problema ocorre quando a equipe de relacionamento de talento não tem a função de usuário de talento.</span><span class="sxs-lookup"><span data-stu-id="8a39e-108">This problem occurs when the Talent Relationship Team doesn't have the Talent user role.</span></span>

## <a name="resolution"></a><span data-ttu-id="8a39e-109">Resolução</span><span class="sxs-lookup"><span data-stu-id="8a39e-109">Resolution</span></span>

<span data-ttu-id="8a39e-110">Atribua a função de usuário de talento à equipe de relacionamento de talento.</span><span class="sxs-lookup"><span data-stu-id="8a39e-110">Assign the Talent user role to the Talent Relationship Team.</span></span>

1. <span data-ttu-id="8a39e-111">Entre na [central de administração do Power Platform](https://admin.powerplatform.microsoft.com) com uma das seguintes credenciais de administrador:</span><span class="sxs-lookup"><span data-stu-id="8a39e-111">Sign in to the [Power Platform admin center](https://admin.powerplatform.microsoft.com) with any of the following admin credentials:</span></span>

   - <span data-ttu-id="8a39e-112">Administrador do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="8a39e-112">Dynamics 365 admin</span></span>
   - <span data-ttu-id="8a39e-113">Administrador global</span><span class="sxs-lookup"><span data-stu-id="8a39e-113">Global admin</span></span>
   - <span data-ttu-id="8a39e-114">Administrador do Power Platform</span><span class="sxs-lookup"><span data-stu-id="8a39e-114">Power Platform admin</span></span>

2. <span data-ttu-id="8a39e-115">No painel de navegação, selecione **Ambientes** e selecione o ambiente em que você atribuirá a função de usuário de talento à equipe de relacionamento de talento.</span><span class="sxs-lookup"><span data-stu-id="8a39e-115">In the navigation pane, select **Environments**, and then select the environment in which to assign the Talent user role to the Talent Relationship Team.</span></span>

   ![Selecionar ambiente](./media/attract-troubleshoot-career-portal-select-environment.png)

3. <span data-ttu-id="8a39e-117">No painel **Ambientes**, selecione a **URL de ambiente** e entre no portal de administração do ambiente (por exemplo, https:<orgname>. crm.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="8a39e-117">In the **Environments** pane, select the **Environment URL** and sign in to the environment's admin portal (for example, https:<orgname>.crm.dynamics.com).</span></span>

4. <span data-ttu-id="8a39e-118">Selecione **Configurações**, **Sistema** e **Segurança**.</span><span class="sxs-lookup"><span data-stu-id="8a39e-118">Select **Settings**, select **System**, and then select **Security**.</span></span>

   ![Navegue até Segurança](./media/attract-troubleshoot-career-portal-security.png)

5. <span data-ttu-id="8a39e-120">Selecione **Equipes**.</span><span class="sxs-lookup"><span data-stu-id="8a39e-120">Select **Teams**.</span></span>

   ![Selecione Equipes](./media/attract-troubleshoot-career-portal-security-teams.png)

6. <span data-ttu-id="8a39e-122">Procure **Equipe de relacionamento de talento** na caixa de pesquisa e selecione a equipe nos resultados de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="8a39e-122">Search for **Talent Relationship Team** in the search box, and then select the team from the search results.</span></span>

7. <span data-ttu-id="8a39e-123">Selecione **GERENCIAR FUNÇÕES** na faixa de opções.</span><span class="sxs-lookup"><span data-stu-id="8a39e-123">Select **MANAGE ROLES** from the ribbon.</span></span>

8. <span data-ttu-id="8a39e-124">Na caixa de diálogo **Gerenciar Funções da Equipe**, selecione **Usuário de talento** na lista de funções disponíveis e, em seguida, selecione **OK** para aplicar a função.</span><span class="sxs-lookup"><span data-stu-id="8a39e-124">In the **Manage Team Roles** dialog, select **Talent user** from the list of available roles, and then select **OK** to apply the role.</span></span>

   ![Aplicar função](./media/attract-troubleshoot-career-portal-apply-role.png)

9. <span data-ttu-id="8a39e-126">Teste as alterações:</span><span class="sxs-lookup"><span data-stu-id="8a39e-126">Test your changes:</span></span>

   1. <span data-ttu-id="8a39e-127">Entre no portal de carreira em uma nova janela do navegador.</span><span class="sxs-lookup"><span data-stu-id="8a39e-127">Sign in to the career portal from a new browser window.</span></span>
   2. <span data-ttu-id="8a39e-128">Candidatar-se ao emprego no portal de carreiras.</span><span class="sxs-lookup"><span data-stu-id="8a39e-128">Apply for the job from the career portal.</span></span> 
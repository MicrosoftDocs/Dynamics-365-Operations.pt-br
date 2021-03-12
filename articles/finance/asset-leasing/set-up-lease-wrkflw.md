---
title: Configurar fluxos de trabalho de aprovação de arrendamento
description: O tópico explica como configurar um fluxo de trabalho de aprovação que será executado quando um novo arrendamento for criado.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: d2135458873963dc7c930b4bcef0c508c7d9635f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992830"
---
# <a name="set-up-lease-approval-workflows"></a><span data-ttu-id="690f0-103">Configurar fluxos de trabalho de aprovação de arrendamento</span><span class="sxs-lookup"><span data-stu-id="690f0-103">Set up lease approval workflows</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="690f0-104">O tópico explica como configurar um fluxo de trabalho de aprovação que será executado quando um novo arrendamento for criado.</span><span class="sxs-lookup"><span data-stu-id="690f0-104">The topic explains how to set up an approval workflow that will run when a new lease is created.</span></span> <span data-ttu-id="690f0-105">Para obter informações sobre como usar o fluxo de trabalho, consulte [Usar fluxos de trabalho de aprovação de arrendamento](use-create-lease-wrkflw.md).</span><span class="sxs-lookup"><span data-stu-id="690f0-105">For information about how to use the workflow, see [Use lease approval workflows](use-create-lease-wrkflw.md).</span></span> 

1. <span data-ttu-id="690f0-106">Acesse **Arrendamento de ativo \> Configuração \> Fluxo de trabalho de arrendamento**.</span><span class="sxs-lookup"><span data-stu-id="690f0-106">Go to **Asset leasing \> Setup \> Lease workflow**.</span></span>
2. <span data-ttu-id="690f0-107">Na página **Fluxo de trabalho de arrendamento**, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="690f0-107">On the **Lease workflow** page, select **New**.</span></span>
3. <span data-ttu-id="690f0-108">Na caixa de diálogo exibida, em **Tipo do fluxo de trabalho**, selecione o link **Fluxo de trabalho de arrendamento**.</span><span class="sxs-lookup"><span data-stu-id="690f0-108">In the dialog box that appears, under **Workflow type**, select the **Lease workflow** link.</span></span>

    <span data-ttu-id="690f0-109">O aplicativo é aberto.</span><span class="sxs-lookup"><span data-stu-id="690f0-109">The application is opened.</span></span> <span data-ttu-id="690f0-110">Após a execução, entre no Azure Active Directory (Azure AD) para ser redirecionado para o aplicativo de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="690f0-110">After it runs, sign in to Azure Active Directory (Azure AD) to be redirected to the workflow application.</span></span>

4. <span data-ttu-id="690f0-111">Arraste o elemento **Aprovação do fluxo de trabalho de arrendamento** para o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="690f0-111">Drag the **Lease workflow approval** element onto the workflow.</span></span>
5. <span data-ttu-id="690f0-112">Conecte um nó de **Início** para **Aprovação do fluxo de trabalho de arrendamento**.</span><span class="sxs-lookup"><span data-stu-id="690f0-112">Connect one node from **Start** to **Lease workflow approval**.</span></span> <span data-ttu-id="690f0-113">Em seguida, conecte **Aprovação do fluxo de trabalho de arrendamento** a **Final**.</span><span class="sxs-lookup"><span data-stu-id="690f0-113">Then connect **Lease workflow approval** to **End**.</span></span>
6. <span data-ttu-id="690f0-114">Clique duas vezes em **Aprovação do fluxo de trabalho de arrendamento**.</span><span class="sxs-lookup"><span data-stu-id="690f0-114">Double-click **Lease workflow approval**.</span></span>
7. <span data-ttu-id="690f0-115">Selecione **Propriedades** e, em **Configurações básicas**, digite um nome para o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="690f0-115">Select **Properties**, and then, under **Basic settings**, enter a name for the workflow.</span></span>

    <span data-ttu-id="690f0-116">Nesta página, você também pode definir mais parâmetros para o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="690f0-116">On this page, you can also set more parameters for the workflow.</span></span> <span data-ttu-id="690f0-117">Se você tiver ativado **Ações automáticas**, o sistema executará automaticamente uma ação específica.</span><span class="sxs-lookup"><span data-stu-id="690f0-117">If you've turned on **Automatic actions**, the system will automatically take a specific action.</span></span> <span data-ttu-id="690f0-118">As notificações poderão ser enviadas se forem especificadas na guia **Notificações**. Na guia **Configurações avançadas**, você pode especificar um aprovador final, definir um limite de tempo e designar ações específicas que devem ser concluídas.</span><span class="sxs-lookup"><span data-stu-id="690f0-118">Notifications can be sent if they are specified on the **Notifications** tab. On the **Advanced settings** tab, you can specify a final approver, set a time limit, and designate specific actions that must be completed.</span></span>

8. <span data-ttu-id="690f0-119">Ao terminar de definir os parâmetros do fluxo de trabalho, selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="690f0-119">When you've finished setting the workflow parameters, select **Close**.</span></span>
9. <span data-ttu-id="690f0-120">Selecione **Etapa 1** e **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="690f0-120">Select **Step 1**, and then select **Properties**.</span></span>
10. <span data-ttu-id="690f0-121">Em **Configurações básicas**, digite um nome para a etapa, crie uma linha de assunto para a aprovação e especifique instruções para a aprovação.</span><span class="sxs-lookup"><span data-stu-id="690f0-121">Under **Basic settings**, enter a name for the step, create a subject line for the approval, and specify instructions for the approval.</span></span>
11. <span data-ttu-id="690f0-122">Na página **Atribuição**, selecione o tipo de atribuição.</span><span class="sxs-lookup"><span data-stu-id="690f0-122">On the **Assignment** page, select the assignment type.</span></span>
12. <span data-ttu-id="690f0-123">Para atribuir usuários específicos à aprovação, selecione **Usuário**, selecione os usuários que aprovam arrendamentos e selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="690f0-123">To assign specific users to the approval, select **User**, select the users who approve leases, and then select **Close**.</span></span>
13. <span data-ttu-id="690f0-124">Selecione **Salvar e fechar** para criar o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="690f0-124">Select **Save and close** to create the workflow.</span></span> <span data-ttu-id="690f0-125">Depois, quando for solicitado, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="690f0-125">Then, when you're prompted, select **OK**.</span></span>
14. <span data-ttu-id="690f0-126">Na página **Criar fluxo de trabalho**, selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="690f0-126">On the **Create workflow** page, select **Close**.</span></span>
14. <span data-ttu-id="690f0-127">Selecione o novo fluxo de trabalho e depois **Versões**.</span><span class="sxs-lookup"><span data-stu-id="690f0-127">Select the new workflow, and then select **Versions**.</span></span> <span data-ttu-id="690f0-128">Em seguida, selecione **Tornar ativo** para garantir que o fluxo de trabalho esteja ativo.</span><span class="sxs-lookup"><span data-stu-id="690f0-128">Then select **Make active** to ensure that the workflow is active.</span></span>
15. <span data-ttu-id="690f0-129">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="690f0-129">Select **Close**.</span></span> <span data-ttu-id="690f0-130">A nova versão ativa será exibida.</span><span class="sxs-lookup"><span data-stu-id="690f0-130">The new active version appears.</span></span>

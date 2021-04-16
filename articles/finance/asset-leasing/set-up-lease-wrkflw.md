---
title: Configurar fluxos de trabalho de aprovação de arrendamento
description: O tópico explica como configurar um fluxo de trabalho de aprovação que será executado quando um novo arrendamento for criado.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 4d5416b3b24d5fbb3ac46afb3c672212d41d42d5
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5827545"
---
# <a name="set-up-lease-approval-workflows"></a><span data-ttu-id="83122-103">Configurar fluxos de trabalho de aprovação de arrendamento</span><span class="sxs-lookup"><span data-stu-id="83122-103">Set up lease approval workflows</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="83122-104">O tópico explica como configurar um fluxo de trabalho de aprovação que será executado quando um novo arrendamento for criado.</span><span class="sxs-lookup"><span data-stu-id="83122-104">The topic explains how to set up an approval workflow that will run when a new lease is created.</span></span> <span data-ttu-id="83122-105">Para obter informações sobre como usar o fluxo de trabalho, consulte [Usar fluxos de trabalho de aprovação de arrendamento](use-create-lease-wrkflw.md).</span><span class="sxs-lookup"><span data-stu-id="83122-105">For information about how to use the workflow, see [Use lease approval workflows](use-create-lease-wrkflw.md).</span></span> 

1. <span data-ttu-id="83122-106">Acesse **Arrendamento de ativo \> Configuração \> Fluxo de trabalho de arrendamento**.</span><span class="sxs-lookup"><span data-stu-id="83122-106">Go to **Asset leasing \> Setup \> Lease workflow**.</span></span>
2. <span data-ttu-id="83122-107">Na página **Fluxo de trabalho de arrendamento**, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="83122-107">On the **Lease workflow** page, select **New**.</span></span>
3. <span data-ttu-id="83122-108">Na caixa de diálogo exibida, em **Tipo do fluxo de trabalho**, selecione o link **Fluxo de trabalho de arrendamento**.</span><span class="sxs-lookup"><span data-stu-id="83122-108">In the dialog box that appears, under **Workflow type**, select the **Lease workflow** link.</span></span>

    <span data-ttu-id="83122-109">O aplicativo é aberto.</span><span class="sxs-lookup"><span data-stu-id="83122-109">The application is opened.</span></span> <span data-ttu-id="83122-110">Após a execução, entre no Azure Active Directory (Azure AD) para ser redirecionado para o aplicativo de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="83122-110">After it runs, sign in to Azure Active Directory (Azure AD) to be redirected to the workflow application.</span></span>

4. <span data-ttu-id="83122-111">Arraste o elemento **Aprovação do fluxo de trabalho de arrendamento** para o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="83122-111">Drag the **Lease workflow approval** element onto the workflow.</span></span>
5. <span data-ttu-id="83122-112">Conecte um nó de **Início** para **Aprovação do fluxo de trabalho de arrendamento**.</span><span class="sxs-lookup"><span data-stu-id="83122-112">Connect one node from **Start** to **Lease workflow approval**.</span></span> <span data-ttu-id="83122-113">Em seguida, conecte **Aprovação do fluxo de trabalho de arrendamento** a **Final**.</span><span class="sxs-lookup"><span data-stu-id="83122-113">Then connect **Lease workflow approval** to **End**.</span></span>
6. <span data-ttu-id="83122-114">Clique duas vezes em **Aprovação do fluxo de trabalho de arrendamento**.</span><span class="sxs-lookup"><span data-stu-id="83122-114">Double-click **Lease workflow approval**.</span></span>
7. <span data-ttu-id="83122-115">Selecione **Propriedades** e, em **Configurações básicas**, digite um nome para o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="83122-115">Select **Properties**, and then, under **Basic settings**, enter a name for the workflow.</span></span>

    <span data-ttu-id="83122-116">Nesta página, você também pode definir mais parâmetros para o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="83122-116">On this page, you can also set more parameters for the workflow.</span></span> <span data-ttu-id="83122-117">Se você tiver ativado **Ações automáticas**, o sistema executará automaticamente uma ação específica.</span><span class="sxs-lookup"><span data-stu-id="83122-117">If you've turned on **Automatic actions**, the system will automatically take a specific action.</span></span> <span data-ttu-id="83122-118">As notificações poderão ser enviadas se forem especificadas na guia **Notificações**. Na guia **Configurações avançadas**, você pode especificar um aprovador final, definir um limite de tempo e designar ações específicas que devem ser concluídas.</span><span class="sxs-lookup"><span data-stu-id="83122-118">Notifications can be sent if they are specified on the **Notifications** tab. On the **Advanced settings** tab, you can specify a final approver, set a time limit, and designate specific actions that must be completed.</span></span>

8. <span data-ttu-id="83122-119">Ao terminar de definir os parâmetros do fluxo de trabalho, selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="83122-119">When you've finished setting the workflow parameters, select **Close**.</span></span>
9. <span data-ttu-id="83122-120">Selecione **Etapa 1** e **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="83122-120">Select **Step 1**, and then select **Properties**.</span></span>
10. <span data-ttu-id="83122-121">Em **Configurações básicas**, digite um nome para a etapa, crie uma linha de assunto para a aprovação e especifique instruções para a aprovação.</span><span class="sxs-lookup"><span data-stu-id="83122-121">Under **Basic settings**, enter a name for the step, create a subject line for the approval, and specify instructions for the approval.</span></span>
11. <span data-ttu-id="83122-122">Na página **Atribuição**, selecione o tipo de atribuição.</span><span class="sxs-lookup"><span data-stu-id="83122-122">On the **Assignment** page, select the assignment type.</span></span>
12. <span data-ttu-id="83122-123">Para atribuir usuários específicos à aprovação, selecione **Usuário**, selecione os usuários que aprovam arrendamentos e selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="83122-123">To assign specific users to the approval, select **User**, select the users who approve leases, and then select **Close**.</span></span>
13. <span data-ttu-id="83122-124">Selecione **Salvar e fechar** para criar o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="83122-124">Select **Save and close** to create the workflow.</span></span> <span data-ttu-id="83122-125">Depois, quando for solicitado, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="83122-125">Then, when you're prompted, select **OK**.</span></span>
14. <span data-ttu-id="83122-126">Na página **Criar fluxo de trabalho**, selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="83122-126">On the **Create workflow** page, select **Close**.</span></span>
14. <span data-ttu-id="83122-127">Selecione o novo fluxo de trabalho e depois **Versões**.</span><span class="sxs-lookup"><span data-stu-id="83122-127">Select the new workflow, and then select **Versions**.</span></span> <span data-ttu-id="83122-128">Em seguida, selecione **Tornar ativo** para garantir que o fluxo de trabalho esteja ativo.</span><span class="sxs-lookup"><span data-stu-id="83122-128">Then select **Make active** to ensure that the workflow is active.</span></span>
15. <span data-ttu-id="83122-129">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="83122-129">Select **Close**.</span></span> <span data-ttu-id="83122-130">A nova versão ativa será exibida.</span><span class="sxs-lookup"><span data-stu-id="83122-130">The new active version appears.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
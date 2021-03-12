---
title: Configurar a diferenciação de direitos
description: Você pode definir regras para separar tarefas que devem ser executadas por usuários diferentes.
author: peakerbl
manager: AnnBe
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bcbd32131f9980a4f55e91b9d7ad48171069f72e
ms.sourcegitcommit: 316200579dd5b04ad76f276a2ed6b0f55fa8c812
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2021
ms.locfileid: "4826385"
---
# <a name="set-up-segregation-of-duties"></a><span data-ttu-id="a883b-103">Configurar a diferenciação de direitos</span><span class="sxs-lookup"><span data-stu-id="a883b-103">Set up segregation of duties</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a883b-104">Você pode definir regras para separar tarefas que devem ser executadas por usuários diferentes.</span><span class="sxs-lookup"><span data-stu-id="a883b-104">You can set up rules to separate tasks that must be performed by different users.</span></span> <span data-ttu-id="a883b-105">Este conceito é chamado de segregação de direitos.</span><span class="sxs-lookup"><span data-stu-id="a883b-105">This concept is named segregation of duties.</span></span> <span data-ttu-id="a883b-106">Por exemplo, talvez você não queira que a mesma pessoa confirme o recebimento de mercadorias e processe o pagamento ao fornecedor.</span><span class="sxs-lookup"><span data-stu-id="a883b-106">For example, you might not want the same person to acknowledge the receipt of goods and to process payment to the vendor.</span></span> <span data-ttu-id="a883b-107">Diferenciação de direitos ajuda a reduzir o risco de fraude, além de ajudar a detectar erros ou irregularidades.</span><span class="sxs-lookup"><span data-stu-id="a883b-107">Segregation of duties helps you reduce the risk of fraud, and it also helps you detect errors or irregularities.</span></span> <span data-ttu-id="a883b-108">Você também pode usar a diferenciação de direitos para garantir o cumprimento das políticas de controle interno.</span><span class="sxs-lookup"><span data-stu-id="a883b-108">You can also use segregation of duties to enforce internal control policies.</span></span> <span data-ttu-id="a883b-109">Complete o procedimento a seguir para criar uma regra.</span><span class="sxs-lookup"><span data-stu-id="a883b-109">Complete the following procedure to create a rule.</span></span> <span data-ttu-id="a883b-110">Você deve ser um administrador do sistema para concluir o procedimento.</span><span class="sxs-lookup"><span data-stu-id="a883b-110">You must be a system administrator to complete the procedure.</span></span>

1. <span data-ttu-id="a883b-111">Vá para **Administração do sistema** > **Segurança** > **Diferenciação de direitos** > **Regras de diferenciação de direitos**.</span><span class="sxs-lookup"><span data-stu-id="a883b-111">Go to **System administration** > **Security** > **Segregation of duties** > **Segregation of duties rules**.</span></span>
2. <span data-ttu-id="a883b-112">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="a883b-112">Click **New**.</span></span>
3. <span data-ttu-id="a883b-113">No campo **Nome**, digite um valor para a regra.</span><span class="sxs-lookup"><span data-stu-id="a883b-113">In the **Name** field, type a value for the rule.</span></span>
4. <span data-ttu-id="a883b-114">No campo **Primeiro direito**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a883b-114">In the **First duty** field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="a883b-115">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="a883b-115">In the list, find and select the desired record.</span></span> <span data-ttu-id="a883b-116">Selecione a primeira tarefa que é controlada pela regra.</span><span class="sxs-lookup"><span data-stu-id="a883b-116">Select the first duty that is controlled by the rule.</span></span>
6. <span data-ttu-id="a883b-117">No campo **Segundo direito**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a883b-117">In the **Second duty** field, click the drop-down button to open the lookup.</span></span> 
7. <span data-ttu-id="a883b-118">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="a883b-118">In the list, find and select the desired record.</span></span> <span data-ttu-id="a883b-119">Selecione a segunda tarefa que é controlada pela regra.</span><span class="sxs-lookup"><span data-stu-id="a883b-119">Select the second duty that is controlled by the rule.</span></span>
10. <span data-ttu-id="a883b-120">No campo **Gravidade**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="a883b-120">In the **Severity** field, select an option.</span></span> <span data-ttu-id="a883b-121">Selecione a gravidade do risco que ocorre quando o mesmo usuário ou função executam ambas as tarefas.</span><span class="sxs-lookup"><span data-stu-id="a883b-121">Select the severity of the risk that occurs when the same user or role performs both duties.</span></span>  
11. <span data-ttu-id="a883b-122">No campo **Risco de segurança**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="a883b-122">In the **Security risk** field, type a value.</span></span> <span data-ttu-id="a883b-123">Insira uma descrição do risco de segurança.</span><span class="sxs-lookup"><span data-stu-id="a883b-123">Enter a description of the security risk.</span></span>  
12. <span data-ttu-id="a883b-124">No campo **Atenuação de segurança**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="a883b-124">In the **Security mitigation** field, type a value.</span></span> <span data-ttu-id="a883b-125">Insira uma descrição das ações que você toma para atenuar o risco de segurança.</span><span class="sxs-lookup"><span data-stu-id="a883b-125">Enter a description of the actions that you take to mitigate the security risk.</span></span> <span data-ttu-id="a883b-126">Por exemplo, você pode atenuar o risco conduzindo revisões mais detalhadas do processo, conduzindo uma revisão administrativa mensal, ou compartilhando recursos com outros departamentos.</span><span class="sxs-lookup"><span data-stu-id="a883b-126">For example, you can mitigate the risk by conducting more detailed reviews of the process, by conducting a monthly managerial review, or by sharing resources with other departments.</span></span>     
13. <span data-ttu-id="a883b-127">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a883b-127">Click **Save**.</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="a883b-128">A conformidade com as regras de diferenciação de direitos não é verificada quando você cria uma regra.</span><span class="sxs-lookup"><span data-stu-id="a883b-128">Compliance with the rules for segregation of duties is not verified when you create a rule.</span></span> <span data-ttu-id="a883b-129">Você pode criar uma regra que crie um conflito para as funções existentes.</span><span class="sxs-lookup"><span data-stu-id="a883b-129">You can create a rule that creates a conflict for existing roles.</span></span> <span data-ttu-id="a883b-130">As atribuições de funções de usuário existentes também podem estar em conflito com a nova regra.</span><span class="sxs-lookup"><span data-stu-id="a883b-130">Existing user role assignments can also be in conflict with the new rule.</span></span> <span data-ttu-id="a883b-131">Você deve validar a conformidade depois de criar ou modificar uma regra.</span><span class="sxs-lookup"><span data-stu-id="a883b-131">You must validate compliance after you create or modify a rule.</span></span> <span data-ttu-id="a883b-132">Para obter mais informações, consulte [Identificar e resolver conflitos na diferenciação de direitos](identify-resolve-conflicts-segregation-duties.md)</span><span class="sxs-lookup"><span data-stu-id="a883b-132">For more information, see [Identify and resolve conflicts in segregation of duties](identify-resolve-conflicts-segregation-duties.md)</span></span>

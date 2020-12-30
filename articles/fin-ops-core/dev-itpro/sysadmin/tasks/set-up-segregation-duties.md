---
title: Configurar a diferenciação de direitos
description: Você pode definir regras para separar tarefas que devem ser executadas por usuários diferentes.
author: peakerbl
manager: AnnBe
ms.date: 06/25/2019
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
ms.openlocfilehash: 57c7c436c91ab11404cac3ea056b028023a0617a
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4688164"
---
# <a name="set-up-segregation-of-duties"></a><span data-ttu-id="42bba-103">Configurar a diferenciação de direitos</span><span class="sxs-lookup"><span data-stu-id="42bba-103">Set up segregation of duties</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="42bba-104">Você pode definir regras para separar tarefas que devem ser executadas por usuários diferentes.</span><span class="sxs-lookup"><span data-stu-id="42bba-104">You can set up rules to separate tasks that must be performed by different users.</span></span> <span data-ttu-id="42bba-105">Este conceito é chamado de segregação de direitos.</span><span class="sxs-lookup"><span data-stu-id="42bba-105">This concept is named segregation of duties.</span></span> <span data-ttu-id="42bba-106">Por exemplo, você pode não querer que a mesma pessoa confirme o recebimento de mercadorias e processe o pagamento ao fornecedor.</span><span class="sxs-lookup"><span data-stu-id="42bba-106">For example, you might not want the same person both to acknowledge the receipt of goods and to process payment to the vendor.</span></span> <span data-ttu-id="42bba-107">Diferenciação de direitos ajuda a reduzir o risco de fraude, além de ajudar a detectar erros ou irregularidades.</span><span class="sxs-lookup"><span data-stu-id="42bba-107">Segregation of duties helps you reduce the risk of fraud, and it also helps you detect errors or irregularities.</span></span> <span data-ttu-id="42bba-108">Você também pode usar a diferenciação de direitos para garantir o cumprimento das políticas de controle interno.</span><span class="sxs-lookup"><span data-stu-id="42bba-108">You can also use segregation of duties to enforce internal control policies.</span></span> <span data-ttu-id="42bba-109">Complete o procedimento a seguir para criar uma regra.</span><span class="sxs-lookup"><span data-stu-id="42bba-109">Complete the following procedure to create a rule.</span></span> <span data-ttu-id="42bba-110">Você deve ser um administrador do sistema para concluir o procedimento.</span><span class="sxs-lookup"><span data-stu-id="42bba-110">You must be a system administrator to complete the procedure.</span></span> <span data-ttu-id="42bba-111">A empresa de dados demonstrativos utilizada para criar esse procedimento é a DAT.</span><span class="sxs-lookup"><span data-stu-id="42bba-111">The demo data company used to create this procedure is DAT.</span></span> 

1. <span data-ttu-id="42bba-112">Vá para **Painel de navegação > Módulos > Administração do sistema > Segurança > Diferenciação de direitos > Regras da diferenciação de direitos**.</span><span class="sxs-lookup"><span data-stu-id="42bba-112">Go to **Navigation pane > Modules > System administration > Security > Segregation of duties > Segregation of duties rules**.</span></span>
2. <span data-ttu-id="42bba-113">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="42bba-113">Click **New**.</span></span>
3. <span data-ttu-id="42bba-114">No campo **Nome**, digite um valor para a regra.</span><span class="sxs-lookup"><span data-stu-id="42bba-114">In the **Name** field, type a value for the rule.</span></span>
4. <span data-ttu-id="42bba-115">No campo **Primeiro direito**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="42bba-115">In the **First duty** field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="42bba-116">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="42bba-116">In the list, find and select the desired record.</span></span> <span data-ttu-id="42bba-117">Selecione a primeira tarefa que é controlada pela regra.</span><span class="sxs-lookup"><span data-stu-id="42bba-117">Select the first duty that is controlled by the rule.</span></span>
6. <span data-ttu-id="42bba-118">No campo **Segundo direito**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="42bba-118">In the **Second duty** field, click the drop-down button to open the lookup.</span></span> 
7. <span data-ttu-id="42bba-119">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="42bba-119">In the list, find and select the desired record.</span></span> <span data-ttu-id="42bba-120">Selecione a segunda tarefa que é controlada pela regra.</span><span class="sxs-lookup"><span data-stu-id="42bba-120">Select the second duty that is controlled by the rule.</span></span>
10. <span data-ttu-id="42bba-121">No campo **Gravidade**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="42bba-121">In the **Severity** field, select an option.</span></span> <span data-ttu-id="42bba-122">Selecione a gravidade do risco que ocorre quando o mesmo usuário ou função executam ambas as tarefas.</span><span class="sxs-lookup"><span data-stu-id="42bba-122">Select the severity of the risk that occurs when the same user or role performs both duties.</span></span>  
11. <span data-ttu-id="42bba-123">No campo **Risco de segurança**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="42bba-123">In the **Security risk** field, type a value.</span></span> <span data-ttu-id="42bba-124">Insira uma descrição do risco de segurança.</span><span class="sxs-lookup"><span data-stu-id="42bba-124">Enter a description of the security risk.</span></span>  
12. <span data-ttu-id="42bba-125">No campo **Atenuação de segurança**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="42bba-125">In the **Security mitigation** field, type a value.</span></span> <span data-ttu-id="42bba-126">Insira uma descrição das ações que você toma para atenuar o risco de segurança.</span><span class="sxs-lookup"><span data-stu-id="42bba-126">Enter a description of the actions that you take to mitigate the security risk.</span></span> <span data-ttu-id="42bba-127">Por exemplo, você pode atenuar o risco conduzindo revisões mais detalhadas do processo, conduzindo uma revisão administrativa mensal, ou compartilhando recursos com outros departamentos.</span><span class="sxs-lookup"><span data-stu-id="42bba-127">For example, you can mitigate the risk by conducting more detailed reviews of the process, by conducting a monthly managerial review, or by sharing resources with other departments.</span></span>     
13. <span data-ttu-id="42bba-128">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="42bba-128">Click **Save**.</span></span>


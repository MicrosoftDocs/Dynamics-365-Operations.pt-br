--- 
title: "Configurar a diferenciação de direitos"
description: "Você pode definir regras para separar tarefas que devem ser executadas por usuários diferentes."
author: maertenm
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 68e1a4419eaa11a59e1b634deb8e76a2bb9b6fdf
ms.contentlocale: pt-br
ms.lasthandoff: 09/14/2018

---
# <a name="set-up-segregation-of-duties"></a><span data-ttu-id="b126c-103">Configurar a diferenciação de direitos</span><span class="sxs-lookup"><span data-stu-id="b126c-103">Set up segregation of duties</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b126c-104">Você pode definir regras para separar tarefas que devem ser executadas por usuários diferentes.</span><span class="sxs-lookup"><span data-stu-id="b126c-104">You can set up rules to separate tasks that must be performed by different users.</span></span> <span data-ttu-id="b126c-105">Este conceito é chamado de segregação de direitos.</span><span class="sxs-lookup"><span data-stu-id="b126c-105">This concept is named segregation of duties.</span></span> <span data-ttu-id="b126c-106">Por exemplo, você pode não querer que a mesma pessoa confirme o recebimento de mercadorias e processe o pagamento ao fornecedor.</span><span class="sxs-lookup"><span data-stu-id="b126c-106">For example, you might not want the same person both to acknowledge the receipt of goods and to process payment to the vendor.</span></span> <span data-ttu-id="b126c-107">Diferenciação de direitos ajuda a reduzir o risco de fraude, além de ajudar a detectar erros ou irregularidades.</span><span class="sxs-lookup"><span data-stu-id="b126c-107">Segregation of duties helps you reduce the risk of fraud, and it also helps you detect errors or irregularities.</span></span> <span data-ttu-id="b126c-108">Você também pode usar a diferenciação de direitos para garantir o cumprimento das políticas de controle interno.</span><span class="sxs-lookup"><span data-stu-id="b126c-108">You can also use segregation of duties to enforce internal control policies.</span></span> <span data-ttu-id="b126c-109">Complete o procedimento a seguir para criar uma regra.</span><span class="sxs-lookup"><span data-stu-id="b126c-109">Complete the following procedure to create a rule.</span></span> <span data-ttu-id="b126c-110">Você deve ser um administrador do sistema para concluir o procedimento.</span><span class="sxs-lookup"><span data-stu-id="b126c-110">You must be a system administrator to complete the procedure.</span></span> <span data-ttu-id="b126c-111">A empresa de dados demonstrativos utilizada para criar esse procedimento é a DAT.</span><span class="sxs-lookup"><span data-stu-id="b126c-111">The demo data company used to create this procedure is DAT.</span></span> 

1. <span data-ttu-id="b126c-112">Vá para Administração do sistema > Segurança > Diferenciação de direitos > Regras de diferenciação de direitos.</span><span class="sxs-lookup"><span data-stu-id="b126c-112">Go to System administration > Security > Segregation of duties > Segregation of duties rules.</span></span>
2. <span data-ttu-id="b126c-113">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="b126c-113">Click New.</span></span>
3. <span data-ttu-id="b126c-114">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b126c-114">In the Name field, type a value.</span></span>
    * <span data-ttu-id="b126c-115">Insira um nome para a regra.</span><span class="sxs-lookup"><span data-stu-id="b126c-115">Enter a name for the rule.</span></span>  
4. <span data-ttu-id="b126c-116">No campo Primeiro direito, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b126c-116">In the First duty field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="b126c-117">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="b126c-117">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="b126c-118">Selecione a primeira tarefa que é controlada pela regra.</span><span class="sxs-lookup"><span data-stu-id="b126c-118">Select the first duty that is controlled by the rule.</span></span>  
6. <span data-ttu-id="b126c-119">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b126c-119">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="b126c-120">No campo Segundo direito, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b126c-120">In the Second duty field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="b126c-121">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="b126c-121">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="b126c-122">Selecione a segunda tarefa que é controlada pela regra.</span><span class="sxs-lookup"><span data-stu-id="b126c-122">Select the second duty that is controlled by the rule.</span></span>  
9. <span data-ttu-id="b126c-123">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b126c-123">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="b126c-124">No campo Gravidade, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="b126c-124">In the Severity field, select an option.</span></span>
    * <span data-ttu-id="b126c-125">Selecione a gravidade do risco que ocorre quando o mesmo usuário ou função executam ambas as tarefas.</span><span class="sxs-lookup"><span data-stu-id="b126c-125">Select the severity of the risk that occurs when the same user or role performs both duties.</span></span>  
11. <span data-ttu-id="b126c-126">No campo Risco de segurança, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b126c-126">In the Security risk field, type a value.</span></span>
    * <span data-ttu-id="b126c-127">Insira uma descrição do risco de segurança.</span><span class="sxs-lookup"><span data-stu-id="b126c-127">Enter a description of the security risk.</span></span>  
12. <span data-ttu-id="b126c-128">No campo Atenuação de segurança, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b126c-128">In the Security mitigation field, type a value.</span></span>
    * <span data-ttu-id="b126c-129">Insira uma descrição das ações que você toma para atenuar o risco de segurança.</span><span class="sxs-lookup"><span data-stu-id="b126c-129">Enter a description of the actions that you take to mitigate the security risk.</span></span> <span data-ttu-id="b126c-130">Por exemplo, você pode atenuar o risco conduzindo revisões mais detalhadas do processo, conduzindo uma revisão administrativa mensal, ou compartilhando recursos com outros departamentos.</span><span class="sxs-lookup"><span data-stu-id="b126c-130">For example, you can mitigate the risk by conducting more detailed reviews of the process, by conducting a monthly managerial review, or by sharing resources with other departments.</span></span>  
13. <span data-ttu-id="b126c-131">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="b126c-131">Click Save.</span></span>



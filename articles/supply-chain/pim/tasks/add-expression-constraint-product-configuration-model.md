--- 
title: "Adicionar uma restrição de expressão para um modelo de configuração de produto"
description: "Este procedimento mostra como é possível adicionar uma nova expressão de restrição a um modelo de configuração do produto."
author: YuyuScheller
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 8db46c5b8361c96745b440c0d0684e18c06a6c6f
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="add-an-expression-constraint-to-a-product-configuration-model"></a><span data-ttu-id="7879c-103">Adicionar uma restrição de expressão para um modelo de configuração de produto</span><span class="sxs-lookup"><span data-stu-id="7879c-103">Add an expression constraint to a product configuration model</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7879c-104">Este procedimento mostra como é possível adicionar uma nova expressão de restrição a um modelo de configuração do produto.</span><span class="sxs-lookup"><span data-stu-id="7879c-104">This procedure shows how you can add a new constraint expression to a product configuration model.</span></span> <span data-ttu-id="7879c-105">Mostra como você pode obrigar que essa proteção seja aplicada a um alto-falante, se o usuário selecionou uma grade frontal de metal.</span><span class="sxs-lookup"><span data-stu-id="7879c-105">It shows how you can mandate that corner protection must be applied to a speaker if the user has selected a front grill in metal.</span></span> <span data-ttu-id="7879c-106">O procedimento usa o componente alto-falante avançado na empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="7879c-106">The procedure uses the High end speaker component in the demo company USMF.</span></span>


## <a name="create-an-expression-constraint"></a><span data-ttu-id="7879c-107">Criar uma restrição de expressão</span><span class="sxs-lookup"><span data-stu-id="7879c-107">Create an expression constraint</span></span>
1. <span data-ttu-id="7879c-108">Clique em Definição de modelo de variante de produto.</span><span class="sxs-lookup"><span data-stu-id="7879c-108">Click Product variant model definition.</span></span>
2. <span data-ttu-id="7879c-109">Clique em Modelos de configuração do produto.</span><span class="sxs-lookup"><span data-stu-id="7879c-109">Click Product configuration models.</span></span>
3. <span data-ttu-id="7879c-110">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="7879c-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="7879c-111">Este exemplo usa o modelo de alto-falante avançado.</span><span class="sxs-lookup"><span data-stu-id="7879c-111">This example uses the high end speaker model.</span></span>  
4. <span data-ttu-id="7879c-112">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="7879c-112">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="7879c-113">Expanda a seção Restrições.</span><span class="sxs-lookup"><span data-stu-id="7879c-113">Expand the Constraints section.</span></span>
6. <span data-ttu-id="7879c-114">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="7879c-114">Click Add.</span></span>
7. <span data-ttu-id="7879c-115">Clique em Criar.</span><span class="sxs-lookup"><span data-stu-id="7879c-115">Click Create.</span></span>
8. <span data-ttu-id="7879c-116">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7879c-116">In the Name field, type a value.</span></span>

## <a name="enter-expression"></a><span data-ttu-id="7879c-117">Inserir expressão</span><span class="sxs-lookup"><span data-stu-id="7879c-117">Enter expression</span></span>
1. <span data-ttu-id="7879c-118">Clique em Editar expressão.</span><span class="sxs-lookup"><span data-stu-id="7879c-118">Click Edit expression.</span></span>
    * <span data-ttu-id="7879c-119">Se você desbloquear a interface do usuário na gravação da tarefa neste estágio, você pode usar IntelliSense e a lista de símbolos para criar a expressão da restrição.</span><span class="sxs-lookup"><span data-stu-id="7879c-119">If you unlock the user interface in the task recording at this stage, you can use IntelliSense and the list of symbols to build the constraint expression .</span></span>  
2. <span data-ttu-id="7879c-120">No campo ConstraintBody, insira 'Implies[FrontGrill=="Metal", CornerProtection] '.</span><span class="sxs-lookup"><span data-stu-id="7879c-120">In the ConstraintBody field, enter 'Implies[FrontGrill=="Metal", CornerProtection] '.</span></span>
    * <span data-ttu-id="7879c-121">Esta lógica de expressão declara: Se a grade Frontal for metal, a opção de proteção de canto deve ser marcada.</span><span class="sxs-lookup"><span data-stu-id="7879c-121">This expression logic states: If the Front grill is  metal, then the corner protection option must be selected.</span></span>  
3. <span data-ttu-id="7879c-122">Clique em Validar.</span><span class="sxs-lookup"><span data-stu-id="7879c-122">Click Validate.</span></span>
    * <span data-ttu-id="7879c-123">A função Validar executa a expressão de restrição e verifica erros de sintaxe.</span><span class="sxs-lookup"><span data-stu-id="7879c-123">The validate function runs through the constraint expression and checks for syntax errors.</span></span>  
4. <span data-ttu-id="7879c-124">Clique em Fechar.</span><span class="sxs-lookup"><span data-stu-id="7879c-124">Click Close.</span></span>
5. <span data-ttu-id="7879c-125">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="7879c-125">Click OK.</span></span>



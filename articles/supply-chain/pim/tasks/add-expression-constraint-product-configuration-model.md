---
title: Adicionar uma restrição de expressão para um modelo de configuração de produto
description: Este procedimento mostra como é possível adicionar uma nova expressão de restrição a um modelo de configuração do produto.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, SysClientPolymorphicCreateSelector, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 56f94b82f8b2642b12a993bde7d6bb323da79f98
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "360569"
---
# <a name="add-an-expression-constraint-to-a-product-configuration-model"></a><span data-ttu-id="aceef-103">Adicionar uma restrição de expressão para um modelo de configuração de produto</span><span class="sxs-lookup"><span data-stu-id="aceef-103">Add an expression constraint to a product configuration model</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="aceef-104">Este procedimento mostra como é possível adicionar uma nova expressão de restrição a um modelo de configuração do produto.</span><span class="sxs-lookup"><span data-stu-id="aceef-104">This procedure shows how you can add a new constraint expression to a product configuration model.</span></span> <span data-ttu-id="aceef-105">Mostra como você pode obrigar que essa proteção seja aplicada a um alto-falante, se o usuário selecionou uma grade frontal de metal.</span><span class="sxs-lookup"><span data-stu-id="aceef-105">It shows how you can mandate that corner protection must be applied to a speaker if the user has selected a front grill in metal.</span></span> <span data-ttu-id="aceef-106">O procedimento usa o componente alto-falante avançado na empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="aceef-106">The procedure uses the High end speaker component in the demo company USMF.</span></span>


## <a name="create-an-expression-constraint"></a><span data-ttu-id="aceef-107">Criar uma restrição de expressão</span><span class="sxs-lookup"><span data-stu-id="aceef-107">Create an expression constraint</span></span>
1. <span data-ttu-id="aceef-108">Clique em Definição de modelo de variante de produto.</span><span class="sxs-lookup"><span data-stu-id="aceef-108">Click Product variant model definition.</span></span>
2. <span data-ttu-id="aceef-109">Clique em Modelos de configuração do produto.</span><span class="sxs-lookup"><span data-stu-id="aceef-109">Click Product configuration models.</span></span>
3. <span data-ttu-id="aceef-110">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="aceef-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="aceef-111">Este exemplo usa o modelo de alto-falante avançado.</span><span class="sxs-lookup"><span data-stu-id="aceef-111">This example uses the high end speaker model.</span></span>  
4. <span data-ttu-id="aceef-112">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="aceef-112">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="aceef-113">Expanda a seção Restrições.</span><span class="sxs-lookup"><span data-stu-id="aceef-113">Expand the Constraints section.</span></span>
6. <span data-ttu-id="aceef-114">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="aceef-114">Click Add.</span></span>
7. <span data-ttu-id="aceef-115">Clique em Criar.</span><span class="sxs-lookup"><span data-stu-id="aceef-115">Click Create.</span></span>
8. <span data-ttu-id="aceef-116">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="aceef-116">In the Name field, type a value.</span></span>

## <a name="enter-expression"></a><span data-ttu-id="aceef-117">Inserir expressão</span><span class="sxs-lookup"><span data-stu-id="aceef-117">Enter expression</span></span>
1. <span data-ttu-id="aceef-118">Clique em Editar expressão.</span><span class="sxs-lookup"><span data-stu-id="aceef-118">Click Edit expression.</span></span>
    * <span data-ttu-id="aceef-119">Se você desbloquear a interface do usuário na gravação da tarefa neste estágio, você pode usar IntelliSense e a lista de símbolos para criar a expressão da restrição.</span><span class="sxs-lookup"><span data-stu-id="aceef-119">If you unlock the user interface in the task recording at this stage, you can use IntelliSense and the list of symbols to build the constraint expression .</span></span>  
2. <span data-ttu-id="aceef-120">No campo ConstraintBody, insira 'Implies[FrontGrill=="Metal", CornerProtection] '.</span><span class="sxs-lookup"><span data-stu-id="aceef-120">In the ConstraintBody field, enter 'Implies[FrontGrill=="Metal", CornerProtection] '.</span></span>
    * <span data-ttu-id="aceef-121">Esta lógica de expressão declara: Se a grade Frontal for metal, a opção de proteção de canto deve ser marcada.</span><span class="sxs-lookup"><span data-stu-id="aceef-121">This expression logic states: If the Front grill is  metal, then the corner protection option must be selected.</span></span>  
3. <span data-ttu-id="aceef-122">Clique em Validar.</span><span class="sxs-lookup"><span data-stu-id="aceef-122">Click Validate.</span></span>
    * <span data-ttu-id="aceef-123">A função Validar executa a expressão de restrição e verifica erros de sintaxe.</span><span class="sxs-lookup"><span data-stu-id="aceef-123">The validate function runs through the constraint expression and checks for syntax errors.</span></span>  
4. <span data-ttu-id="aceef-124">Clique em Fechar.</span><span class="sxs-lookup"><span data-stu-id="aceef-124">Click Close.</span></span>
5. <span data-ttu-id="aceef-125">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="aceef-125">Click OK.</span></span>


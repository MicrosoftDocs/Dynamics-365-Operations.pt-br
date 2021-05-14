---
title: Adicionar uma restrição de expressão para um modelo de configuração de produto
description: Este procedimento mostra como é possível adicionar uma nova expressão de restrição a um modelo de configuração do produto.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, SysClientPolymorphicCreateSelector, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9cd5475e48cbcd8dcee6b228297f58e364ac503d
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920872"
---
# <a name="add-an-expression-constraint-to-a-product-configuration-model"></a><span data-ttu-id="c62a8-103">Adicionar uma restrição de expressão para um modelo de configuração de produto</span><span class="sxs-lookup"><span data-stu-id="c62a8-103">Add an expression constraint to a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c62a8-104">Este procedimento mostra como é possível adicionar uma nova expressão de restrição a um modelo de configuração do produto.</span><span class="sxs-lookup"><span data-stu-id="c62a8-104">This procedure shows how you can add a new constraint expression to a product configuration model.</span></span> <span data-ttu-id="c62a8-105">Mostra como você pode obrigar que essa proteção seja aplicada a um alto-falante, se o usuário selecionou uma grade frontal de metal.</span><span class="sxs-lookup"><span data-stu-id="c62a8-105">It shows how you can mandate that corner protection must be applied to a speaker if the user has selected a front grill in metal.</span></span> <span data-ttu-id="c62a8-106">O procedimento usa o componente alto-falante avançado na empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="c62a8-106">The procedure uses the High end speaker component in the demo company USMF.</span></span>

## <a name="create-an-expression-constraint"></a><span data-ttu-id="c62a8-107">Criar uma restrição de expressão</span><span class="sxs-lookup"><span data-stu-id="c62a8-107">Create an expression constraint</span></span>

1. <span data-ttu-id="c62a8-108">Vá para **Gerenciamento de informações do produto \> Produtos \> Modelos de configuração do produto**.</span><span class="sxs-lookup"><span data-stu-id="c62a8-108">Go to **Product information management \> Products \> Product configuration models**.</span></span>
3. <span data-ttu-id="c62a8-109">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="c62a8-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="c62a8-110">Este exemplo usa o modelo de alto-falante avançado.</span><span class="sxs-lookup"><span data-stu-id="c62a8-110">This example uses the high end speaker model.</span></span>  
4. <span data-ttu-id="c62a8-111">Na lista, selecione o link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c62a8-111">In the list, select the link in the selected row.</span></span>
5. <span data-ttu-id="c62a8-112">Expanda a seção **Restrições**.</span><span class="sxs-lookup"><span data-stu-id="c62a8-112">Expand the **Constraints** section.</span></span>
6. <span data-ttu-id="c62a8-113">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c62a8-113">Select **Add**.</span></span>
7. <span data-ttu-id="c62a8-114">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="c62a8-114">Select **Create**.</span></span>
8. <span data-ttu-id="c62a8-115">No campo **Nome**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c62a8-115">In the **Name** field, type a value.</span></span>

## <a name="enter-expression"></a><span data-ttu-id="c62a8-116">Inserir expressão</span><span class="sxs-lookup"><span data-stu-id="c62a8-116">Enter expression</span></span>

1. <span data-ttu-id="c62a8-117">Selecione **Editar expressão**.</span><span class="sxs-lookup"><span data-stu-id="c62a8-117">Select **Edit expression**.</span></span>
    * <span data-ttu-id="c62a8-118">Se você desbloquear a interface do usuário na gravação da tarefa neste estágio, você pode usar IntelliSense e a lista de símbolos para criar a expressão da restrição.</span><span class="sxs-lookup"><span data-stu-id="c62a8-118">If you unlock the user interface in the task recording at this stage, you can use IntelliSense and the list of symbols to build the constraint expression .</span></span>  
2. <span data-ttu-id="c62a8-119">No campo **ConstraintBody**, digite 'Implies[FrontGrill=="Metal", CornerProtection] '.</span><span class="sxs-lookup"><span data-stu-id="c62a8-119">In the **ConstraintBody** field, enter 'Implies[FrontGrill=="Metal", CornerProtection] '.</span></span>
    * <span data-ttu-id="c62a8-120">Esta lógica de expressão declara: Se a grade Frontal for metal, a opção de proteção de canto deve ser marcada.</span><span class="sxs-lookup"><span data-stu-id="c62a8-120">This expression logic states: If the Front grill is  metal, then the corner protection option must be selected.</span></span>  
3. <span data-ttu-id="c62a8-121">Selecione **Validar**.</span><span class="sxs-lookup"><span data-stu-id="c62a8-121">Select **Validate**.</span></span>
    * <span data-ttu-id="c62a8-122">A função Validar executa a expressão de restrição e verifica erros de sintaxe.</span><span class="sxs-lookup"><span data-stu-id="c62a8-122">The validate function runs through the constraint expression and checks for syntax errors.</span></span>  
4. <span data-ttu-id="c62a8-123">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="c62a8-123">Select **Close**.</span></span>
5. <span data-ttu-id="c62a8-124">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="c62a8-124">Select **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
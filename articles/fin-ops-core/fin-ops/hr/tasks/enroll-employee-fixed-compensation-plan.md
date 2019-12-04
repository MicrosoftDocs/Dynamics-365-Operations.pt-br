---
title: Inscrever um funcionário em um plano de remuneração fixa
description: A remuneração ou gerente pode atribuir benefícios de funcionários a planos de remuneração fixa ao gerenciar o pagamento base.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMCompFixedEmpl, HRMCompFixedEmplActionDialog, HcmPositionLookup, HRMCompRefPointLookup
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ee0ba197ee47d2a2da2372b12291e5625ddc9ba1
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2190502"
---
# <a name="enroll-an-employee-in-a-fixed-compensation-plan"></a><span data-ttu-id="86559-103">Inscrever um funcionário em um plano de remuneração fixa</span><span class="sxs-lookup"><span data-stu-id="86559-103">Enroll an employee in a fixed compensation plan</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="86559-104">A remuneração ou gerente pode atribuir benefícios de funcionários a planos de remuneração fixa ao gerenciar o pagamento base.</span><span class="sxs-lookup"><span data-stu-id="86559-104">The compensation and benefits manager can assign employees to fixed compensation plans to manage their base pay.</span></span> <span data-ttu-id="86559-105">Este procedimento pressupõe que um plano fixo esteve criado e está ativo, e as regras de qualificação forem definidas para o plano.</span><span class="sxs-lookup"><span data-stu-id="86559-105">This procedure assumes that a fixed plan has been created and is active, and that eligibility rules have been set for the plan.</span></span> <span data-ttu-id="86559-106">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="86559-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="86559-107">Para iniciar o procedimento, vá para Recursos humanos > Trabalhadores > Funcionários > Remuneração > Plano fixo</span><span class="sxs-lookup"><span data-stu-id="86559-107">To begin the procedure, go to Human resources > Workers > Employees > Compensation > Fixed plan</span></span>

1. <span data-ttu-id="86559-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="86559-108">Click New.</span></span>
2. <span data-ttu-id="86559-109">No campo Ação, selecione uma Ação de compensação fixa do tipo Contratar/Recontratar para descrever a alteração na compensação de funcionário.</span><span class="sxs-lookup"><span data-stu-id="86559-109">In the Action field, select a Fixed compensation action of type Hire/Rehire to describe the change in the employee's compensation.</span></span>
3. <span data-ttu-id="86559-110">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="86559-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="86559-111">No campo Posição, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="86559-111">In the Position field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="86559-112">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="86559-112">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="86559-113">O nível que é é exibido em nível de remuneração dos trabalhos na posição.</span><span class="sxs-lookup"><span data-stu-id="86559-113">The level that's displayed is from the Compensation Level of the Job on the Position.</span></span> <span data-ttu-id="86559-114">O nível deve ser definido no trabalho antes da remuneração puder ser atribuída ao funcionário.</span><span class="sxs-lookup"><span data-stu-id="86559-114">The level must be set on the Job before compensation can be assigned to the employee.</span></span>  
6. <span data-ttu-id="86559-115">No campo Plano, selecione o plano de remuneração fixa do funcionário.</span><span class="sxs-lookup"><span data-stu-id="86559-115">In the Plan field, select the fixed compensation plan for the employee.</span></span> <span data-ttu-id="86559-116">A pesquisa do plano é filtrada para mostrar apenas os planos em que o funcionário está qualificado com base nas regras de qualificação.</span><span class="sxs-lookup"><span data-stu-id="86559-116">The Plan lookup is filtered to show only the plans that the employee is eligible for based on the Eligibility rules.</span></span>
7. <span data-ttu-id="86559-117">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="86559-117">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="86559-118">O efetivo e as datas de vencimento para o padrão de remuneração desde o início e fim para a atribuição da posição do funcionário.</span><span class="sxs-lookup"><span data-stu-id="86559-118">The Effective and Expiration dates for the compensation default from the start and end dates for the worker's position assignment.</span></span> <span data-ttu-id="86559-119">É possível ajustar essas datas conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="86559-119">You can adjust these dates as needed.</span></span>  
    * <span data-ttu-id="86559-120">Se o plano de remuneração fixa é um plano de etapa, selecione a etapa que contém a taxa de pagamento correta para o funcionário.</span><span class="sxs-lookup"><span data-stu-id="86559-120">If the Fixed compensation plan is a step plan, select the step containing the correct pay rate for the employee.</span></span> <span data-ttu-id="86559-121">Se o plano de remuneração fixado é um plano de grade ou faixa, insira a taxa de pagamento correta para o funcionário.</span><span class="sxs-lookup"><span data-stu-id="86559-121">If the fixed compensation plan is a grade or a band plan, enter the pay rate for the employee.</span></span> <span data-ttu-id="86559-122">A taxa de pagamento será validada nas configurações de tolerância para o plano, e os pontos de referência mínimo e máximo para o nível de remuneração de trabalho.</span><span class="sxs-lookup"><span data-stu-id="86559-122">The pay rate will be validated against the tolerance settings for the plan, and the minimum and maximum reference points for the job's compensation level.</span></span>  
8. <span data-ttu-id="86559-123">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="86559-123">Click OK.</span></span>

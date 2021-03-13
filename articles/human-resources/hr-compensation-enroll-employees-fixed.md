---
title: Inscrever um funcionário em um plano de remuneração fixa
description: A remuneração ou gerente pode atribuir benefícios de funcionários a planos de remuneração fixa ao gerenciar o pagamento base.
author: andreabichsel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMCompFixedEmpl, HRMCompFixedEmplActionDialog, HcmPositionLookup, HRMCompRefPointLookup, HcmCompensationWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bc8373a4a39a1a212ab445b2b300fbddfe0e4a39
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "5111495"
---
# <a name="enroll-an-employee-in-a-fixed-compensation-plan"></a><span data-ttu-id="ecf42-103">Inscrever um funcionário em um plano de remuneração fixa</span><span class="sxs-lookup"><span data-stu-id="ecf42-103">Enroll an employee in a fixed compensation plan</span></span>

<span data-ttu-id="ecf42-104">A remuneração ou gerente pode atribuir benefícios de funcionários a planos de remuneração fixa ao gerenciar o pagamento base.</span><span class="sxs-lookup"><span data-stu-id="ecf42-104">The compensation and benefits manager can assign employees to fixed compensation plans to manage their base pay.</span></span> <span data-ttu-id="ecf42-105">Este procedimento pressupõe que um plano fixo esteve criado e está ativo, e as regras de qualificação forem definidas para o plano.</span><span class="sxs-lookup"><span data-stu-id="ecf42-105">This procedure assumes that a fixed plan has been created and is active, and that eligibility rules have been set for the plan.</span></span> <span data-ttu-id="ecf42-106">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="ecf42-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="ecf42-107">Para iniciar o procedimento, vá para Recursos humanos > Trabalhadores > Funcionários > Remuneração > Plano fixo</span><span class="sxs-lookup"><span data-stu-id="ecf42-107">To begin the procedure, go to Human resources > Workers > Employees > Compensation > Fixed plan</span></span>

1. <span data-ttu-id="ecf42-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="ecf42-108">Click New.</span></span>
2. <span data-ttu-id="ecf42-109">No campo Ação, selecione uma Ação de compensação fixa do tipo Contratar/Recontratar para descrever a alteração na compensação de funcionário.</span><span class="sxs-lookup"><span data-stu-id="ecf42-109">In the Action field, select a Fixed compensation action of type Hire/Rehire to describe the change in the employee's compensation.</span></span>
3. <span data-ttu-id="ecf42-110">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="ecf42-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="ecf42-111">No campo Posição, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="ecf42-111">In the Position field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="ecf42-112">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="ecf42-112">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ecf42-113">O nível que é é exibido em nível de remuneração dos trabalhos na posição.</span><span class="sxs-lookup"><span data-stu-id="ecf42-113">The level that's displayed is from the Compensation Level of the Job on the Position.</span></span> <span data-ttu-id="ecf42-114">O nível deve ser definido no trabalho antes da remuneração puder ser atribuída ao funcionário.</span><span class="sxs-lookup"><span data-stu-id="ecf42-114">The level must be set on the Job before compensation can be assigned to the employee.</span></span>  
6. <span data-ttu-id="ecf42-115">No campo Plano, selecione o plano de remuneração fixa do funcionário.</span><span class="sxs-lookup"><span data-stu-id="ecf42-115">In the Plan field, select the fixed compensation plan for the employee.</span></span> <span data-ttu-id="ecf42-116">A pesquisa do plano é filtrada para mostrar apenas os planos em que o funcionário está qualificado com base nas regras de qualificação.</span><span class="sxs-lookup"><span data-stu-id="ecf42-116">The Plan lookup is filtered to show only the plans that the employee is eligible for based on the Eligibility rules.</span></span>
7. <span data-ttu-id="ecf42-117">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="ecf42-117">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="ecf42-118">O efetivo e as datas de vencimento para o padrão de remuneração desde o início e fim para a atribuição da posição do funcionário.</span><span class="sxs-lookup"><span data-stu-id="ecf42-118">The Effective and Expiration dates for the compensation default from the start and end dates for the worker's position assignment.</span></span> <span data-ttu-id="ecf42-119">É possível ajustar essas datas conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="ecf42-119">You can adjust these dates as needed.</span></span>  
    * <span data-ttu-id="ecf42-120">Se o plano de remuneração fixa é um plano de etapa, selecione a etapa que contém a taxa de pagamento correta para o funcionário.</span><span class="sxs-lookup"><span data-stu-id="ecf42-120">If the Fixed compensation plan is a step plan, select the step containing the correct pay rate for the employee.</span></span> <span data-ttu-id="ecf42-121">Se o plano de remuneração fixado é um plano de grade ou faixa, insira a taxa de pagamento correta para o funcionário.</span><span class="sxs-lookup"><span data-stu-id="ecf42-121">If the fixed compensation plan is a grade or a band plan, enter the pay rate for the employee.</span></span> <span data-ttu-id="ecf42-122">A taxa de pagamento será validada nas configurações de tolerância para o plano, e os pontos de referência mínimo e máximo para o nível de remuneração de trabalho.</span><span class="sxs-lookup"><span data-stu-id="ecf42-122">The pay rate will be validated against the tolerance settings for the plan, and the minimum and maximum reference points for the job's compensation level.</span></span>  
8. <span data-ttu-id="ecf42-123">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="ecf42-123">Click OK.</span></span>


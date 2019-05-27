---
title: Inscrever um funcionário em um plano de remuneração variável
description: O gerente de remuneração e os benefícios podem inserir funcionários em planos de remuneração variável e calcular os prêmios em dinheiro e não provenientes de pagamento à vista para funcionários.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMCompVarEnrollEmpl
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d120f8bb52252956d75178d2ffac6ab632385e00
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1510511"
---
# <a name="enroll-an-employee-in-a-variable-compensation-plan"></a><span data-ttu-id="86775-103">Inscrever um funcionário em um plano de remuneração variável</span><span class="sxs-lookup"><span data-stu-id="86775-103">Enroll an employee in a variable compensation plan</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="86775-104">O gerente de remuneração e os benefícios podem inserir funcionários em planos de remuneração variável e calcular os prêmios em dinheiro e não provenientes de pagamento à vista para funcionários.</span><span class="sxs-lookup"><span data-stu-id="86775-104">The Compensation and Benefits manager can enroll employees in variable compensation plans to calculate cash and non-cash awards for employees.</span></span> <span data-ttu-id="86775-105">Este procedimento pressupõe que um plano de remuneração variável tenha sido criado com o campo Habilitar inscrição definido como Sim, e que tenham sido criadas regras de qualificação para esse plano de remuneração variável.</span><span class="sxs-lookup"><span data-stu-id="86775-105">This procedure assumes that a variable compensation plan has been created with the Enable enrolment field set to Yes, and that eligibility rules have been created for that variable compensation plan.</span></span> <span data-ttu-id="86775-106">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="86775-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="86775-107">Para iniciar este procedimento, vá para Recursos humanos > Trabalhadores > Funcionários > Remuneração > Inscrição de plano variável</span><span class="sxs-lookup"><span data-stu-id="86775-107">To begin this procedure, go to Human resources > Workers > Employees > Compensation > Variable plan enrolment</span></span>

1. <span data-ttu-id="86775-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="86775-108">Click New.</span></span>
2. <span data-ttu-id="86775-109">No campo Plano, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="86775-109">In the Plan field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="86775-110">A pesquisa do plano será filtrada para mostrar apenas os planos de remuneração variável em que o funcionário está qualificado com base nas regras de qualificação.</span><span class="sxs-lookup"><span data-stu-id="86775-110">The plan lookup will be filtered to only show the variable compensation plans that the employee is eligible for based on the eligibility rules.</span></span>  
3. <span data-ttu-id="86775-111">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="86775-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="86775-112">Alternar a expansão da seção Geral.</span><span class="sxs-lookup"><span data-stu-id="86775-112">Toggle the expansion of the General section.</span></span>
5. <span data-ttu-id="86775-113">No campo Data efetiva, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="86775-113">In the Effective date field, enter a date.</span></span>
6. <span data-ttu-id="86775-114">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="86775-114">Click Save.</span></span>
7. <span data-ttu-id="86775-115">Alternar a expansão da seção Sobreposição.</span><span class="sxs-lookup"><span data-stu-id="86775-115">Toggle the expansion of the Overrides section.</span></span>
    * <span data-ttu-id="86775-116">Opcionalmente, a data de uma regra de contratação pode ser definida para substituir a data de contratação para um funcionário quando a regra de contratação especificada para o plano variável selecionado é porcentagem.</span><span class="sxs-lookup"><span data-stu-id="86775-116">Optionally, a hire rule date can be set to override the hire date for an employee when the hire rule specified for the selected variable plan is Percent.</span></span>  
    * <span data-ttu-id="86775-117">Se o plano variável for uma porcentagem do plano de base, a porcentagem do prêmio pode ser substituída para o funcionário.</span><span class="sxs-lookup"><span data-stu-id="86775-117">If the variable plan is a percent of basis plan, the award percentage can be overridden for the employee.</span></span> <span data-ttu-id="86775-118">Se o plano de remuneração variável for um número de plano de unidades, a o número de unidades pode ser substituído por outro funcionário.</span><span class="sxs-lookup"><span data-stu-id="86775-118">If the variable compensation plan is a number of units plan, the number of units can be overridden for the employee.</span></span>  
    * <span data-ttu-id="86775-119">Se o funcionário é fornecido um valor liso da concessão, o valor pode ser definido aqui.</span><span class="sxs-lookup"><span data-stu-id="86775-119">If the employee should be given a flat amount for their award, the amount can be set here.</span></span>  
8. <span data-ttu-id="86775-120">Ative a expansão da seção Substituições organizacional.</span><span class="sxs-lookup"><span data-stu-id="86775-120">Toggle the expansion of the Organizational overrides section.</span></span>
    * <span data-ttu-id="86775-121">Se o desempenho do funcionário deve ser levado em consideração, no desempenho de departamentos diferentes ou em um departamento diferente daquele atribuído a posição de um funcionário, o departamento pode ser substituído.</span><span class="sxs-lookup"><span data-stu-id="86775-121">If the employee's performance should take into consideration, the performance of different departments, or a department other than the one assigned on the employee's position, the department can be overridden.</span></span> <span data-ttu-id="86775-122">A porcentagem da coluna deve totalizar 100.</span><span class="sxs-lookup"><span data-stu-id="86775-122">The Percent column should total 100.</span></span>  


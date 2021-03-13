---
title: Inscrever um funcionário em um plano de remuneração variável
description: O gerente de remuneração e os benefícios podem inserir funcionários em planos de remuneração variável e calcular os prêmios em dinheiro e não provenientes de pagamento à vista para funcionários.
author: andreabichsel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMCompVarEnrollEmpl, HcmCompensationWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a7a173403e79212be5e4aac36d99f349da159e08
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "5111494"
---
# <a name="enroll-an-employee-in-a-variable-compensation-plan"></a><span data-ttu-id="629c7-103">Inscrever um funcionário em um plano de remuneração variável</span><span class="sxs-lookup"><span data-stu-id="629c7-103">Enroll an employee in a variable compensation plan</span></span>

<span data-ttu-id="629c7-104">O gerente de remuneração e os benefícios podem inserir funcionários em planos de remuneração variável e calcular os prêmios em dinheiro e não provenientes de pagamento à vista para funcionários.</span><span class="sxs-lookup"><span data-stu-id="629c7-104">The Compensation and Benefits manager can enroll employees in variable compensation plans to calculate cash and non-cash awards for employees.</span></span> <span data-ttu-id="629c7-105">Este procedimento pressupõe que um plano de remuneração variável tenha sido criado com o campo Habilitar inscrição definido como Sim, e que tenham sido criadas regras de qualificação para esse plano de remuneração variável.</span><span class="sxs-lookup"><span data-stu-id="629c7-105">This procedure assumes that a variable compensation plan has been created with the Enable enrolment field set to Yes, and that eligibility rules have been created for that variable compensation plan.</span></span> <span data-ttu-id="629c7-106">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="629c7-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="629c7-107">Para iniciar este procedimento, vá para Recursos humanos > Trabalhadores > Funcionários > Remuneração > Inscrição de plano variável</span><span class="sxs-lookup"><span data-stu-id="629c7-107">To begin this procedure, go to Human resources > Workers > Employees > Compensation > Variable plan enrolment</span></span>

1. <span data-ttu-id="629c7-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="629c7-108">Click New.</span></span>
2. <span data-ttu-id="629c7-109">No campo Plano, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="629c7-109">In the Plan field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="629c7-110">A pesquisa do plano será filtrada para mostrar apenas os planos de remuneração variável em que o funcionário está qualificado com base nas regras de qualificação.</span><span class="sxs-lookup"><span data-stu-id="629c7-110">The plan lookup will be filtered to only show the variable compensation plans that the employee is eligible for based on the eligibility rules.</span></span>  
3. <span data-ttu-id="629c7-111">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="629c7-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="629c7-112">Alternar a expansão da seção Geral.</span><span class="sxs-lookup"><span data-stu-id="629c7-112">Toggle the expansion of the General section.</span></span>
5. <span data-ttu-id="629c7-113">No campo Data efetiva, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="629c7-113">In the Effective date field, enter a date.</span></span>
6. <span data-ttu-id="629c7-114">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="629c7-114">Click Save.</span></span>
7. <span data-ttu-id="629c7-115">Alternar a expansão da seção Sobreposição.</span><span class="sxs-lookup"><span data-stu-id="629c7-115">Toggle the expansion of the Overrides section.</span></span>
    * <span data-ttu-id="629c7-116">Opcionalmente, a data de uma regra de contratação pode ser definida para substituir a data de contratação para um funcionário quando a regra de contratação especificada para o plano variável selecionado é porcentagem.</span><span class="sxs-lookup"><span data-stu-id="629c7-116">Optionally, a hire rule date can be set to override the hire date for an employee when the hire rule specified for the selected variable plan is Percent.</span></span>  
    * <span data-ttu-id="629c7-117">Se o plano variável for uma porcentagem do plano de base, a porcentagem do prêmio pode ser substituída para o funcionário.</span><span class="sxs-lookup"><span data-stu-id="629c7-117">If the variable plan is a percent of basis plan, the award percentage can be overridden for the employee.</span></span> <span data-ttu-id="629c7-118">Se o plano de remuneração variável for um número de plano de unidades, a o número de unidades pode ser substituído por outro funcionário.</span><span class="sxs-lookup"><span data-stu-id="629c7-118">If the variable compensation plan is a number of units plan, the number of units can be overridden for the employee.</span></span>  
    * <span data-ttu-id="629c7-119">Se o funcionário é fornecido um valor liso da concessão, o valor pode ser definido aqui.</span><span class="sxs-lookup"><span data-stu-id="629c7-119">If the employee should be given a flat amount for their award, the amount can be set here.</span></span>  
8. <span data-ttu-id="629c7-120">Ative a expansão da seção Substituições organizacional.</span><span class="sxs-lookup"><span data-stu-id="629c7-120">Toggle the expansion of the Organizational overrides section.</span></span>
    * <span data-ttu-id="629c7-121">Se o desempenho do funcionário deve ser levado em consideração, no desempenho de departamentos diferentes ou em um departamento diferente daquele atribuído a posição de um funcionário, o departamento pode ser substituído.</span><span class="sxs-lookup"><span data-stu-id="629c7-121">If the employee's performance should take into consideration, the performance of different departments, or a department other than the one assigned on the employee's position, the department can be overridden.</span></span> <span data-ttu-id="629c7-122">A porcentagem da coluna deve totalizar 100.</span><span class="sxs-lookup"><span data-stu-id="629c7-122">The Percent column should total 100.</span></span>  


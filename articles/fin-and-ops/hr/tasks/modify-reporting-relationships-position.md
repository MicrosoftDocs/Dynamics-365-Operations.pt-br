--- 
title: "Modificar os relacionamentos de subordinação de posições"
description: "Este procedimento mostra como alterar a relação de subordinação de um funcionário."
author: ShielaSogge
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations, Talent
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 764d4c9049d94ebcd55c61654aa2f4133b35bae6
ms.openlocfilehash: 2e52552ec5bce957ac43c2e34ac9a0e42829accd
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2018

---
# <a name="modify-the-reporting-relationships-for-positions"></a><span data-ttu-id="fc1ff-103">Modificar os relacionamentos de subordinação de posições</span><span class="sxs-lookup"><span data-stu-id="fc1ff-103">Modify the reporting relationships for positions</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fc1ff-104">Este procedimento mostra como alterar a relação de subordinação de um funcionário.</span><span class="sxs-lookup"><span data-stu-id="fc1ff-104">This procedure shows how to change the reporting relationship for an employee.</span></span> <span data-ttu-id="fc1ff-105">A relação de subordinação pode ser usada para documentos de roteiros com o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="fc1ff-105">The reporting relationship can be used for routing documents through workflow.</span></span> <span data-ttu-id="fc1ff-106">O procedimento também mostra como atribuir um funcionário às hierarquias adicionais.</span><span class="sxs-lookup"><span data-stu-id="fc1ff-106">The procedure also shows how to assign the employee to additional hierarchies.</span></span> <span data-ttu-id="fc1ff-107">Por exemplo, um funcionário pode fazer parte de uma equipe de projeto com uma relação de subordinação informal a um supervisor do projeto.</span><span class="sxs-lookup"><span data-stu-id="fc1ff-107">For example, an employee might be a part of a project team with an informal reporting relationship to a project supervisor.</span></span> <span data-ttu-id="fc1ff-108">As relações de subordinação adicionais podem ser definidas na posição para acomodar vários cenários de projeto ou de matriz.</span><span class="sxs-lookup"><span data-stu-id="fc1ff-108">Additional reporting relationships can be defined on the position to accommodate various project or matrix scenarios.</span></span> <span data-ttu-id="fc1ff-109">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="fc1ff-109">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="fc1ff-110">Vá para Recursos humanos > Posições > Posições.</span><span class="sxs-lookup"><span data-stu-id="fc1ff-110">Go to Human resources > Positions > Positions.</span></span>
2. <span data-ttu-id="fc1ff-111">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="fc1ff-111">Use the Quick Filter to find records.</span></span> <span data-ttu-id="fc1ff-112">Por exemplo, filtre o campo Posição com um valor de '000091'.</span><span class="sxs-lookup"><span data-stu-id="fc1ff-112">For example, filter on the Position field with a value of '000091'.</span></span>
3. <span data-ttu-id="fc1ff-113">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="fc1ff-113">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="fc1ff-114">Expanda a seção Relatórios para posição.</span><span class="sxs-lookup"><span data-stu-id="fc1ff-114">Expand the Reports to position section.</span></span>
5. <span data-ttu-id="fc1ff-115">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="fc1ff-115">Click New to open the drop dialog.</span></span>
6. <span data-ttu-id="fc1ff-116">No campo Subordinado a, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="fc1ff-116">In the Reports to field, enter or select a value.</span></span>
7. <span data-ttu-id="fc1ff-117">Clique em Criar.</span><span class="sxs-lookup"><span data-stu-id="fc1ff-117">Click Create.</span></span>
8. <span data-ttu-id="fc1ff-118">Expanda a seção Relacionamentos.</span><span class="sxs-lookup"><span data-stu-id="fc1ff-118">Expand the Relationships section.</span></span>
9. <span data-ttu-id="fc1ff-119">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="fc1ff-119">Click Add.</span></span>
10. <span data-ttu-id="fc1ff-120">Marque a caixa de seleção à esquerda da grade.</span><span class="sxs-lookup"><span data-stu-id="fc1ff-120">Select the check box on the left of the grid.</span></span>
11. <span data-ttu-id="fc1ff-121">No campo Nome da hierarquia, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="fc1ff-121">In the Hierarchy name field, enter or select a value.</span></span>
    * <span data-ttu-id="fc1ff-122">Exemplo: Projeto</span><span class="sxs-lookup"><span data-stu-id="fc1ff-122">Example: Project</span></span>  
12. <span data-ttu-id="fc1ff-123">No campo Relatórios para posição, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="fc1ff-123">In the Reports to position field, enter or select a value.</span></span>  <span data-ttu-id="fc1ff-124">Exemplo: 000437</span><span class="sxs-lookup"><span data-stu-id="fc1ff-124">Example:  000437</span></span>
13. <span data-ttu-id="fc1ff-125">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="fc1ff-125">Click Save.</span></span>


